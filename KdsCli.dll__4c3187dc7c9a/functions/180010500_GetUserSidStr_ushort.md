# GetUserSidStr(ushort * *)

- ea: `0x180010500`
- end: `0x18001061e`
- name: `?GetUserSidStr@@YAJPEAPEAG@Z`
- size: `286`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a9f0`

## callees

- `0x180010304`
- `0x180010500`
- `0x180010708`
- `0x180010950`
- `0x18001a450`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180010598`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180010598`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800105f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800105f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800105a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800105a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001060a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001060a`

## string_xrefs

- `0x180010542`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyutil.cxx`
- `0x180010577`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyutil.cxx`
- `0x1800105ae`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyutil.cxx`

## pseudocode

```c
__int64 __fastcall GetUserSidStr(unsigned __int16 **a1)
{
  signed int v2; // eax
  unsigned int v3; // ebx
  signed int TokenUserSid; // eax
  DWORD LastError; // eax
  PSID Sid; // [rsp+38h] [rbp+10h] BYREF
  LPWSTR StringSid; // [rsp+40h] [rbp+18h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp+20h] BYREF

  StringSid = 0;
  hObject = 0;
  Sid = 0;
  v2 = OpenCallerToken(0xCu, &hObject);
  v3 = v2;
  if ( v2 >= 0 )
  {
    TokenUserSid = GetTokenUserSid(hObject, &Sid);
    v3 = TokenUserSid;
    if ( TokenUserSid >= 0 )
    {
      if ( ConvertSidToStringSidW(Sid, &StringSid) )
      {
        *a1 = StringSid;
        StringSid = 0;
      }
      else
      {
        LastError = GetLastError();
        SidKeyDebugTraceError(
          LastError,
          "GetLastError()",
          "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyutil.cxx",
          0x11Du);
        v3 = -2147024809;
      }
    }
    else
    {
      SidKeyDebugTraceError(
        TokenUserSid,
        "hr",
        "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyutil.cxx",
        0x113u);
    }
    if ( Sid )
      SIDKeyProvFree(Sid);
  }
  else
  {
    SidKeyDebugTraceError(v2, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyutil.cxx", 0x10Bu);
  }
  if ( StringSid )
    LocalFree(StringSid);
  if ( hObject )
    CloseHandle(hObject);
  return v3;
}

```

## disassembly

```asm
0x180010500  mov     rax, rsp
0x180010503  mov     [rax+8], rbx
0x180010507  push    r14
0x180010509  sub     rsp, 20h
0x18001050d  mov     r14, rcx
0x180010510  mov     qword ptr [rax+18h], 0
0x180010518  mov     ecx, 0Ch; DesiredAccess
0x18001051d  mov     qword ptr [rax+20h], 0
0x180010525  lea     rdx, [rax+20h]; void **
0x180010529  mov     qword ptr [rax+10h], 0
0x180010531  call    ?OpenCallerToken@@YAJKPEAPEAX@Z; OpenCallerToken(ulong,void * *)
0x180010536  mov     ebx, eax
0x180010538  test    eax, eax
0x18001053a  jns     short loc_18001055C
0x18001053c  mov     r9d, 10Bh; unsigned int
0x180010542  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180010549  lea     rdx, aHr; "hr"
0x180010550  mov     ecx, eax; unsigned int
0x180010552  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180010557  jmp     loc_1800105ED
0x18001055c  mov     rcx, [rsp+28h+hObject]; TokenHandle
0x180010561  lea     rdx, [rsp+28h+Sid]
0x180010566  call    GetTokenUserSid
0x18001056b  mov     ebx, eax
0x18001056d  test    eax, eax
0x18001056f  jns     short loc_18001058E
0x180010571  mov     r9d, 113h; unsigned int
0x180010577  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18001057e  lea     rdx, aHr; "hr"
0x180010585  mov     ecx, eax; unsigned int
0x180010587  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18001058c  jmp     short loc_1800105DB
0x18001058e  mov     rcx, [rsp+28h+Sid]; Sid
0x180010593  lea     rdx, [rsp+28h+StringSid]; StringSid
0x180010598  call    cs:__imp_ConvertSidToStringSidW
0x18001059e  test    eax, eax
0x1800105a0  jnz     short loc_1800105CA
0x1800105a2  call    cs:__imp_GetLastError
0x1800105a8  mov     r9d, 11Dh; unsigned int
0x1800105ae  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x1800105b5  mov     ecx, eax; unsigned int
0x1800105b7  lea     rdx, aGetlasterror; "GetLastError()"
0x1800105be  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800105c3  mov     ebx, 80070057h
0x1800105c8  jmp     short loc_1800105DB
0x1800105ca  mov     rax, [rsp+28h+StringSid]
0x1800105cf  mov     [r14], rax
0x1800105d2  mov     [rsp+28h+StringSid], 0
0x1800105db  cmp     [rsp+28h+Sid], 0
0x1800105e1  jz      short loc_1800105ED
0x1800105e3  mov     rcx, [rsp+28h+Sid]; lpMem
0x1800105e8  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x1800105ed  mov     rcx, [rsp+28h+StringSid]; hMem
0x1800105f2  test    rcx, rcx
0x1800105f5  jz      short loc_1800105FD
0x1800105f7  call    cs:__imp_LocalFree
0x1800105fd  cmp     [rsp+28h+hObject], 0
0x180010603  jz      short loc_180010610
0x180010605  mov     rcx, [rsp+28h+hObject]; hObject
0x18001060a  call    cs:__imp_CloseHandle
0x180010610  mov     eax, ebx
0x180010612  mov     rbx, [rsp+28h+arg_0]
0x180010617  add     rsp, 20h
0x18001061b  pop     r14
0x18001061d  retn
```
