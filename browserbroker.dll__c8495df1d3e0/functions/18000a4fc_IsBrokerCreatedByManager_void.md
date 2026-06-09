# IsBrokerCreatedByManager(void)

- ea: `0x18000a4fc`
- end: `0x18000a61d`
- name: `?IsBrokerCreatedByManager@@YA_NXZ`
- size: `289`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008060`

## callees

- `0x180002ce0`
- `0x18000a4fc`
- `0x180021060`
- `0x1800213b8`
- `0x180025704`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000a5d5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000a5d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a5f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a5f0`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000a51e`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000a51e`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000a558`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000a5f8`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000a558`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000a5f8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000a535`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000a535`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000a54a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000a54a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a5e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a5e5`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000a5bf`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000a5bf`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
bool IsBrokerCreatedByManager(void)
{
  bool v0; // bl
  HANDLE CurrentThread; // rax
  unsigned int v2; // edx
  LPWSTR StringSid; // [rsp+20h] [rbp-E0h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE Sid[256]; // [rsp+30h] [rbp-D0h] BYREF

  v0 = 0;
  if ( CoImpersonateClient() >= 0 )
  {
    TokenHandle = 0;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
    {
      if ( CoRevertToSelf() >= 0 )
      {
        LODWORD(StringSid) = 0;
        if ( (int)TokenIntegrityRIDFromToken(TokenHandle) >= 0
          && !(unsigned int)TokenIsAppContainerHR(TokenHandle)
          && !GetTokenPackageSID(TokenHandle, v2, Sid) )
        {
          StringSid = 0;
          if ( ConvertSidToStringSidW(Sid, &StringSid) )
          {
            v0 = (unsigned int)_o__wcsicmp(
                                 StringSid,
                                 L"S-1-15-2-3624051433-2125758914-1423191267-1740899205-1073925389-3782572162-737981194") == 0;
            LocalFree(StringSid);
          }
        }
      }
      CloseHandle(TokenHandle);
    }
    else
    {
      CoRevertToSelf();
    }
  }
  return v0;
}

```

## disassembly

```asm
0x18000a4fc  mov     [rsp-8+arg_0], rbx
0x18000a501  push    rbp
0x18000a502  lea     rbp, [rsp-40h]
0x18000a507  sub     rsp, 140h
0x18000a50e  mov     rax, cs:__security_cookie
0x18000a515  xor     rax, rsp
0x18000a518  mov     [rbp+40h+var_10], rax
0x18000a51c  xor     bl, bl
0x18000a51e  call    cs:__imp_CoImpersonateClient
0x18000a524  test    eax, eax
0x18000a526  js      loc_18000A5FE
0x18000a52c  mov     [rsp+140h+TokenHandle], 0
0x18000a535  call    cs:__imp_GetCurrentThread
0x18000a53b  xor     r8d, r8d; OpenAsSelf
0x18000a53e  lea     r9, [rsp+140h+TokenHandle]; TokenHandle
0x18000a543  mov     rcx, rax; ThreadHandle
0x18000a546  lea     edx, [r8+8]; DesiredAccess
0x18000a54a  call    cs:__imp_OpenThreadToken
0x18000a550  test    eax, eax
0x18000a552  jz      loc_18000A5F8
0x18000a558  call    cs:__imp_CoRevertToSelf
0x18000a55e  test    eax, eax
0x18000a560  js      loc_18000A5EB
0x18000a566  mov     rcx, [rsp+140h+TokenHandle]; TokenHandle
0x18000a56b  lea     rdx, [rsp+140h+StringSid]
0x18000a570  mov     dword ptr [rsp+140h+StringSid], 0
0x18000a578  call    _TokenIntegrityRIDFromToken
0x18000a57d  test    eax, eax
0x18000a57f  js      short loc_18000A5EB
0x18000a581  cmp     dword ptr [rsp+140h+StringSid], 2000h
0x18000a589  jnb     short loc_18000A5EB
0x18000a58b  mov     rcx, [rsp+140h+TokenHandle]; TokenHandle
0x18000a590  call    ?TokenIsAppContainerHR@@YAJPEAX@Z; TokenIsAppContainerHR(void *)
0x18000a595  test    eax, eax
0x18000a597  jnz     short loc_18000A5EB
0x18000a599  mov     rcx, [rsp+140h+TokenHandle]; void *
0x18000a59e  lea     r8, [rsp+140h+Sid]; void *
0x18000a5a3  call    ?GetTokenPackageSID@@YAJPEAXK0@Z; GetTokenPackageSID(void *,ulong,void *)
0x18000a5a8  test    eax, eax
0x18000a5aa  jnz     short loc_18000A5EB
0x18000a5ac  lea     rdx, [rsp+140h+StringSid]; StringSid
0x18000a5b1  mov     [rsp+140h+StringSid], 0
0x18000a5ba  lea     rcx, [rsp+140h+Sid]; Sid
0x18000a5bf  call    cs:__imp_ConvertSidToStringSidW
0x18000a5c5  test    eax, eax
0x18000a5c7  jz      short loc_18000A5EB
0x18000a5c9  mov     rcx, [rsp+140h+StringSid]
0x18000a5ce  lea     rdx, aS1152362405143; "S-1-15-2-3624051433-2125758914-14231912"...
0x18000a5d5  call    cs:__imp__o__wcsicmp
0x18000a5db  mov     rcx, [rsp+140h+StringSid]; hMem
0x18000a5e0  test    eax, eax
0x18000a5e2  setz    bl
0x18000a5e5  call    cs:__imp_LocalFree
0x18000a5eb  mov     rcx, [rsp+140h+TokenHandle]; hObject
0x18000a5f0  call    cs:__imp_CloseHandle
0x18000a5f6  jmp     short loc_18000A5FE
0x18000a5f8  call    cs:__imp_CoRevertToSelf
0x18000a5fe  mov     al, bl
0x18000a600  mov     rcx, [rbp+40h+var_10]
0x18000a604  xor     rcx, rsp; StackCookie
0x18000a607  call    __security_check_cookie
0x18000a60c  mov     rbx, [rsp+140h+arg_0]
0x18000a614  add     rsp, 140h
0x18000a61b  pop     rbp
0x18000a61c  retn
```
