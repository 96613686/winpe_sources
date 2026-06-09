# ShieldProvider::IsCallerLocalSystem(void)

- ea: `0x1800ce740`
- end: `0x1800ce829`
- name: `?IsCallerLocalSystem@ShieldProvider@@YA_NXZ`
- size: `233`
- prototype: `bool __fastcall(ShieldProvider *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180071ff0`
- `0x180085f08`
- `0x1800c93a0`
- `0x1800cc544`

## callees

- `0x180004710`
- `0x18000e288`
- `0x1800ce740`
- `0x1800df094`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800ce785`
- `KERNEL32!GetLastError` at `0x1800ce785`
- `KERNEL32!CloseHandle` at `0x1800ce808`
- `KERNEL32!CloseHandle` at `0x1800ce808`
- `KERNEL32!GetCurrentThread` at `0x1800ce766`
- `KERNEL32!GetCurrentThread` at `0x1800ce766`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ce77b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ce77b`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800ce7c4`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800ce7c4`

## pseudocode

```c
bool __fastcall ShieldProvider::IsCallerLocalSystem(ShieldProvider *this)
{
  bool v1; // bl
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  bool v4; // sf
  void *v5; // r9
  _BYTE v7[4]; // [rsp+20h] [rbp-78h] BYREF
  DWORD cbSid; // [rsp+24h] [rbp-74h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-70h] BYREF
  _BYTE pSid[80]; // [rsp+30h] [rbp-68h] BYREF

  v1 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
    goto LABEL_6;
  LastError = GetLastError();
  v4 = LastError < 0;
  if ( LastError > 0 )
  {
    LastError = (unsigned __int16)LastError | 0x80070000;
    v4 = LastError < 0;
  }
  if ( !v4 )
  {
LABEL_6:
    cbSid = 68;
    if ( CreateWellKnownSid(WinLocalSystemSid, 0, pSid, &cbSid) || (int)HrGetLastError() >= 0 )
    {
      v7[0] = 0;
      if ( CommonUtil::UtilCheckTokenMembership((CommonUtil *)v7, (bool *)TokenHandle, pSid, v5) >= 0 )
      {
        if ( v7[0] )
          v1 = 1;
      }
    }
  }
  else
  {
    v1 = LastError == -2147023888;
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v1;
}

```

## disassembly

```asm
0x1800ce740  push    rbx
0x1800ce742  sub     rsp, 90h
0x1800ce749  mov     rax, cs:__security_cookie
0x1800ce750  xor     rax, rsp
0x1800ce753  mov     [rsp+98h+var_18], rax
0x1800ce75b  xor     bl, bl
0x1800ce75d  mov     [rsp+98h+TokenHandle], 0
0x1800ce766  call    cs:__imp_GetCurrentThread
0x1800ce76c  xor     r8d, r8d; OpenAsSelf
0x1800ce76f  lea     r9, [rsp+98h+TokenHandle]; TokenHandle
0x1800ce774  mov     rcx, rax; ThreadHandle
0x1800ce777  lea     edx, [r8+8]; DesiredAccess
0x1800ce77b  call    cs:__imp_OpenThreadToken
0x1800ce781  test    eax, eax
0x1800ce783  jnz     short loc_1800CE7AD
0x1800ce785  call    cs:__imp_GetLastError
0x1800ce78b  test    eax, eax
0x1800ce78d  jle     short loc_1800CE799
0x1800ce78f  movzx   eax, ax
0x1800ce792  or      eax, 80070000h
0x1800ce797  test    eax, eax
0x1800ce799  jns     short loc_1800CE7AD
0x1800ce79b  cmp     eax, 800703F0h
0x1800ce7a0  movzx   ebx, bl
0x1800ce7a3  mov     ecx, 1
0x1800ce7a8  cmovz   ebx, ecx
0x1800ce7ab  jmp     short loc_1800CE7FE
0x1800ce7ad  xor     edx, edx; DomainSid
0x1800ce7af  mov     [rsp+98h+cbSid], 44h ; 'D'
0x1800ce7b7  lea     r9, [rsp+98h+cbSid]; cbSid
0x1800ce7bc  lea     r8, [rsp+98h+pSid]; pSid
0x1800ce7c1  lea     ecx, [rdx+16h]; WellKnownSidType
0x1800ce7c4  call    cs:__imp_CreateWellKnownSid
0x1800ce7ca  test    eax, eax
0x1800ce7cc  jnz     short loc_1800CE7D7
0x1800ce7ce  call    HrGetLastError
0x1800ce7d3  test    eax, eax
0x1800ce7d5  js      short loc_1800CE7FE
0x1800ce7d7  mov     rdx, [rsp+98h+TokenHandle]; bool *
0x1800ce7dc  lea     r8, [rsp+98h+pSid]; void *
0x1800ce7e1  lea     rcx, [rsp+98h+var_78]; this
0x1800ce7e6  mov     [rsp+98h+var_78], bl
0x1800ce7ea  call    ?UtilCheckTokenMembership@CommonUtil@@YAJPEA_NPEAX1@Z; CommonUtil::UtilCheckTokenMembership(bool *,void *,void *)
0x1800ce7ef  test    eax, eax
0x1800ce7f1  js      short loc_1800CE7FE
0x1800ce7f3  cmp     [rsp+98h+var_78], bl
0x1800ce7f7  jz      short loc_1800CE7FE
0x1800ce7f9  mov     ebx, 1
0x1800ce7fe  mov     rcx, [rsp+98h+TokenHandle]; hObject
0x1800ce803  test    rcx, rcx
0x1800ce806  jz      short loc_1800CE80E
0x1800ce808  call    cs:__imp_CloseHandle
0x1800ce80e  mov     al, bl
0x1800ce810  mov     rcx, [rsp+98h+var_18]
0x1800ce818  xor     rcx, rsp; StackCookie
0x1800ce81b  call    __security_check_cookie
0x1800ce820  add     rsp, 90h
0x1800ce827  pop     rbx
0x1800ce828  retn
```
