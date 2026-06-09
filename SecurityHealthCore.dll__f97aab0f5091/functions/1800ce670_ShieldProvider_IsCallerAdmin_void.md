# ShieldProvider::IsCallerAdmin(void)

- ea: `0x1800ce670`
- end: `0x1800ce737`
- name: `?IsCallerAdmin@ShieldProvider@@YA_NXZ`
- size: `199`
- prototype: `bool __fastcall(ShieldProvider *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800cc160`

## callees

- `0x18000d7fc`
- `0x1800ce670`
- `0x1800df118`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800ce6ed`
- `KERNEL32!GetLastError` at `0x1800ce6ed`
- `KERNEL32!CloseHandle` at `0x1800ce728`
- `KERNEL32!CloseHandle` at `0x1800ce728`
- `KERNEL32!GetCurrentThread` at `0x1800ce682`
- `KERNEL32!GetCurrentThread` at `0x1800ce682`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ce697`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ce697`

## pseudocode

```c
char __fastcall ShieldProvider::IsCallerAdmin(ShieldProvider *this)
{
  HANDLE CurrentThread; // rax
  void *v2; // r8
  unsigned int v3; // r9d
  signed int LastError; // eax
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  unsigned int v8; // [rsp+20h] [rbp-8h]
  char v9; // [rsp+30h] [rbp+8h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  v9 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xAu, 0, &TokenHandle) )
  {
    LastError = CommonUtil::UtilCheckTokenMembershipByRid((CommonUtil *)&v9, (bool *)TokenHandle, v2, v3, v8);
    if ( LastError < 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v6 = 13;
LABEL_11:
        WPP_SF_d(v5[2], v6, WPP_825a29c5516139c581f113666145a611_Traceguids, (unsigned int)LastError);
      }
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v5 = WPP_GLOBAL_Control;
    v6 = 14;
    goto LABEL_11;
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v9;
}

```

## disassembly

```asm
0x1800ce670  sub     rsp, 28h
0x1800ce674  mov     [rsp+28h+arg_0], 0
0x1800ce679  mov     [rsp+28h+TokenHandle], 0
0x1800ce682  call    cs:__imp_GetCurrentThread
0x1800ce688  xor     r8d, r8d; OpenAsSelf
0x1800ce68b  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1800ce690  mov     rcx, rax; ThreadHandle
0x1800ce693  lea     edx, [r8+0Ah]; DesiredAccess
0x1800ce697  call    cs:__imp_OpenThreadToken
0x1800ce69d  test    eax, eax
0x1800ce69f  jz      short loc_1800CE6D4
0x1800ce6a1  mov     rdx, [rsp+28h+TokenHandle]; bool *
0x1800ce6a6  lea     rcx, [rsp+28h+arg_0]; this
0x1800ce6ab  call    ?UtilCheckTokenMembershipByRid@CommonUtil@@YAJPEA_NPEAXKK@Z; CommonUtil::UtilCheckTokenMembershipByRid(bool *,void *,ulong,ulong)
0x1800ce6b0  test    eax, eax
0x1800ce6b2  jns     short loc_1800CE71E
0x1800ce6b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ce6bb  lea     rdx, WPP_GLOBAL_Control
0x1800ce6c2  cmp     rcx, rdx
0x1800ce6c5  jz      short loc_1800CE71E
0x1800ce6c7  test    byte ptr [rcx+1Ch], 1
0x1800ce6cb  jz      short loc_1800CE71E
0x1800ce6cd  mov     edx, 0Dh
0x1800ce6d2  jmp     short loc_1800CE70B
0x1800ce6d4  mov     rax, cs:WPP_GLOBAL_Control
0x1800ce6db  lea     rdx, WPP_GLOBAL_Control
0x1800ce6e2  cmp     rax, rdx
0x1800ce6e5  jz      short loc_1800CE71E
0x1800ce6e7  test    byte ptr [rax+1Ch], 1
0x1800ce6eb  jz      short loc_1800CE71E
0x1800ce6ed  call    cs:__imp_GetLastError
0x1800ce6f3  test    eax, eax
0x1800ce6f5  jle     short loc_1800CE6FF
0x1800ce6f7  movzx   eax, ax
0x1800ce6fa  or      eax, 80070000h
0x1800ce6ff  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ce706  mov     edx, 0Eh
0x1800ce70b  mov     rcx, [rcx+10h]
0x1800ce70f  lea     r8, WPP_825a29c5516139c581f113666145a611_Traceguids
0x1800ce716  mov     r9d, eax
0x1800ce719  call    WPP_SF_d
0x1800ce71e  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x1800ce723  test    rcx, rcx
0x1800ce726  jz      short loc_1800CE72E
0x1800ce728  call    cs:__imp_CloseHandle
0x1800ce72e  mov     al, [rsp+28h+arg_0]
0x1800ce732  add     rsp, 28h
0x1800ce736  retn
```
