# IsLowbox(int *)

- ea: `0x180010624`
- end: `0x180010700`
- name: `?IsLowbox@@YAJPEAH@Z`
- size: `220`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800196cc`
- `0x180019bec`

## callees

- `0x180010624`
- `0x180010708`
- `0x18001a450`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800106a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800106a1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010697`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010697`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800106ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800106ef`

## string_xrefs

- `0x180010662`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyutil.cxx`
- `0x1800106ad`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyutil.cxx`

## pseudocode

```c
__int64 __fastcall IsLowbox(int *a1)
{
  BOOL v2; // edi
  signed int v3; // eax
  signed int LastError; // ebx
  bool v5; // zf
  int TokenInformation; // [rsp+50h] [rbp+8h] BYREF
  DWORD ReturnLength; // [rsp+58h] [rbp+10h] BYREF
  HANDLE TokenHandle; // [rsp+60h] [rbp+18h] BYREF

  TokenHandle = 0;
  v2 = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  v3 = OpenCallerToken(8u, &TokenHandle);
  LastError = v3;
  if ( v3 >= 0 )
  {
    if ( GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
    {
      v2 = TokenInformation != 0;
    }
    else
    {
      LastError = GetLastError();
      SidKeyDebugTraceError(
        LastError,
        "dwReturn",
        "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyutil.cxx",
        0x3D8u);
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    SidKeyDebugTraceError(v3, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyutil.cxx", 0x3CCu);
  }
  v5 = TokenHandle == 0;
  *a1 = v2;
  if ( !v5 )
    CloseHandle(TokenHandle);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180010624  mov     rax, rsp
0x180010627  push    rbx
0x180010628  push    rdi
0x180010629  push    r14
0x18001062b  sub     rsp, 30h
0x18001062f  mov     r14, rcx
0x180010632  mov     qword ptr [rax+18h], 0
0x18001063a  xor     edi, edi
0x18001063c  mov     dword ptr [rax+8], 0
0x180010643  lea     rdx, [rax+18h]; void **
0x180010647  mov     dword ptr [rax+10h], 0
0x18001064e  lea     ecx, [rdi+8]; DesiredAccess
0x180010651  call    ?OpenCallerToken@@YAJKPEAPEAX@Z; OpenCallerToken(ulong,void * *)
0x180010656  mov     ebx, eax
0x180010658  test    eax, eax
0x18001065a  jns     short loc_180010679
0x18001065c  mov     r9d, 3CCh; unsigned int
0x180010662  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180010669  lea     rdx, aHr; "hr"
0x180010670  mov     ecx, eax; unsigned int
0x180010672  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180010677  jmp     short loc_1800106DF
0x180010679  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x18001067e  lea     rax, [rsp+48h+arg_8]
0x180010683  mov     r9d, 4; TokenInformationLength
0x180010689  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18001068e  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x180010693  lea     edx, [r9+19h]; TokenInformationClass
0x180010697  call    cs:__imp_GetTokenInformation
0x18001069d  test    eax, eax
0x18001069f  jnz     short loc_1800106D3
0x1800106a1  call    cs:__imp_GetLastError
0x1800106a7  mov     r9d, 3D8h; unsigned int
0x1800106ad  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x1800106b4  mov     ecx, eax; unsigned int
0x1800106b6  lea     rdx, aDwreturn; "dwReturn"
0x1800106bd  mov     ebx, eax
0x1800106bf  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800106c4  test    ebx, ebx
0x1800106c6  jle     short loc_1800106DF
0x1800106c8  movzx   ebx, bx
0x1800106cb  or      ebx, 80070000h
0x1800106d1  jmp     short loc_1800106DF
0x1800106d3  cmp     [rsp+48h+TokenInformation], edi
0x1800106d7  mov     eax, 1
0x1800106dc  cmovnz  edi, eax
0x1800106df  cmp     [rsp+48h+TokenHandle], 0
0x1800106e5  mov     [r14], edi
0x1800106e8  jz      short loc_1800106F5
0x1800106ea  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x1800106ef  call    cs:__imp_CloseHandle
0x1800106f5  mov     eax, ebx
0x1800106f7  add     rsp, 30h
0x1800106fb  pop     r14
0x1800106fd  pop     rdi
0x1800106fe  pop     rbx
0x1800106ff  retn
```
