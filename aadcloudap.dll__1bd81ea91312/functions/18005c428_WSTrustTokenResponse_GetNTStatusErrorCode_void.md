# WSTrustTokenResponse::GetNTStatusErrorCode(void)

- ea: `0x18005c428`
- end: `0x18005c558`
- name: `?GetNTStatusErrorCode@WSTrustTokenResponse@@QEAAJXZ`
- size: `304`
- prototype: `__int64 __fastcall(WSTrustTokenResponse *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002bc04`
- `0x1800315f8`

## callees

- `0x18005c428`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005c44f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005c464`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005c483`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005c498`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005c4b1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005c4d0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005c4e5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005c4fa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005c50f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005c52b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005c44f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005c464`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005c483`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005c498`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005c4b1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005c4d0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005c4e5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005c4fa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005c50f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005c52b`

## string_xrefs

- `0x18005c448`: `UnsupportedSecurityToken`
- `0x18005c47c`: `InvalidSecurity`
- `0x18005c491`: `InvalidSecurityToken`
- `0x18005c4de`: `SecurityTokenUnavailable`
- `0x18005c4f3`: `InternalServiceFault`

## pseudocode

```c
__int64 __fastcall WSTrustTokenResponse::GetNTStatusErrorCode(WSTrustTokenResponse *this)
{
  unsigned int v2; // ebx
  __int64 v3; // rcx

  v2 = -1073741595;
  v3 = *((_QWORD *)this + 4);
  if ( *(_DWORD *)(v3 - 16) )
  {
    if ( !(unsigned int)_o__wcsicmp(v3, L"UnsupportedSecurityToken")
      || !(unsigned int)_o__wcsicmp(*((_QWORD *)this + 4), L"UnsupportedAlgorithm") )
    {
      return (unsigned int)-1073741637;
    }
    if ( (unsigned int)_o__wcsicmp(*((_QWORD *)this + 4), L"InvalidSecurity") )
    {
      if ( (unsigned int)_o__wcsicmp(*((_QWORD *)this + 4), L"InvalidSecurityToken") )
      {
        if ( !(unsigned int)_o__wcsicmp(*((_QWORD *)this + 4), L"FailedAuthentication") )
          return (unsigned int)-1073741715;
        if ( (unsigned int)_o__wcsicmp(*((_QWORD *)this + 4), L"FailedCheck")
          && (unsigned int)_o__wcsicmp(*((_QWORD *)this + 4), L"SecurityTokenUnavailable")
          && (unsigned int)_o__wcsicmp(*((_QWORD *)this + 4), L"InternalServiceFault") )
        {
          if ( !(unsigned int)_o__wcsicmp(*((_QWORD *)this + 4), L"FailedAuthentication.ExpiredPassword") )
            return (unsigned int)-1073741711;
          if ( (unsigned int)_o__wcsicmp(*((_QWORD *)this + 4), L"Unknown") )
            return v2;
        }
      }
      return (unsigned int)-1073741616;
    }
    return (unsigned int)-1073741715;
  }
  if ( *((_DWORD *)this + 2) >= 0x190u )
    return (unsigned int)-1073741252;
  return v2;
}

```

## disassembly

```asm
0x18005c428  mov     [rsp+arg_0], rbx
0x18005c42d  push    rdi
0x18005c42e  sub     rsp, 20h
0x18005c432  mov     rdi, rcx
0x18005c435  mov     ebx, 0C00000E5h
0x18005c43a  mov     rcx, [rcx+20h]
0x18005c43e  cmp     dword ptr [rcx-10h], 0
0x18005c442  jz      loc_18005C53C
0x18005c448  lea     rdx, aUnsupportedsec; "UnsupportedSecurityToken"
0x18005c44f  call    cs:__imp__o__wcsicmp
0x18005c455  test    eax, eax
0x18005c457  jz      short loc_18005C46E
0x18005c459  mov     rcx, [rdi+20h]
0x18005c45d  lea     rdx, aUnsupportedalg; "UnsupportedAlgorithm"
0x18005c464  call    cs:__imp__o__wcsicmp
0x18005c46a  test    eax, eax
0x18005c46c  jnz     short loc_18005C478
0x18005c46e  mov     ebx, 0C00000BBh
0x18005c473  jmp     loc_18005C54B
0x18005c478  mov     rcx, [rdi+20h]
0x18005c47c  lea     rdx, aInvalidsecurit_0; "InvalidSecurity"
0x18005c483  call    cs:__imp__o__wcsicmp
0x18005c489  test    eax, eax
0x18005c48b  jz      short loc_18005C4BB
0x18005c48d  mov     rcx, [rdi+20h]
0x18005c491  lea     rdx, aInvalidsecurit; "InvalidSecurityToken"
0x18005c498  call    cs:__imp__o__wcsicmp
0x18005c49e  test    eax, eax
0x18005c4a0  jz      loc_18005C535
0x18005c4a6  mov     rcx, [rdi+20h]
0x18005c4aa  lea     rdx, aFailedauthenti_0; "FailedAuthentication"
0x18005c4b1  call    cs:__imp__o__wcsicmp
0x18005c4b7  test    eax, eax
0x18005c4b9  jnz     short loc_18005C4C5
0x18005c4bb  mov     ebx, 0C000006Dh
0x18005c4c0  jmp     loc_18005C54B
0x18005c4c5  mov     rcx, [rdi+20h]
0x18005c4c9  lea     rdx, aFailedcheck; "FailedCheck"
0x18005c4d0  call    cs:__imp__o__wcsicmp
0x18005c4d6  test    eax, eax
0x18005c4d8  jz      short loc_18005C535
0x18005c4da  mov     rcx, [rdi+20h]
0x18005c4de  lea     rdx, aSecuritytokenu; "SecurityTokenUnavailable"
0x18005c4e5  call    cs:__imp__o__wcsicmp
0x18005c4eb  test    eax, eax
0x18005c4ed  jz      short loc_18005C535
0x18005c4ef  mov     rcx, [rdi+20h]
0x18005c4f3  lea     rdx, aInternalservic; "InternalServiceFault"
0x18005c4fa  call    cs:__imp__o__wcsicmp
0x18005c500  test    eax, eax
0x18005c502  jz      short loc_18005C535
0x18005c504  mov     rcx, [rdi+20h]
0x18005c508  lea     rdx, aFailedauthenti; "FailedAuthentication.ExpiredPassword"
0x18005c50f  call    cs:__imp__o__wcsicmp
0x18005c515  test    eax, eax
0x18005c517  jnz     short loc_18005C520
0x18005c519  mov     ebx, 0C0000071h
0x18005c51e  jmp     short loc_18005C54B
0x18005c520  mov     rcx, [rdi+20h]
0x18005c524  lea     rdx, aUnknown_0; "Unknown"
0x18005c52b  call    cs:__imp__o__wcsicmp
0x18005c531  test    eax, eax
0x18005c533  jnz     short loc_18005C54B
0x18005c535  mov     ebx, 0C00000D0h
0x18005c53a  jmp     short loc_18005C54B
0x18005c53c  cmp     dword ptr [rdi+8], 190h
0x18005c543  mov     eax, 0C000023Ch
0x18005c548  cmovnb  ebx, eax
0x18005c54b  mov     eax, ebx
0x18005c54d  mov     rbx, [rsp+28h+arg_0]
0x18005c552  add     rsp, 20h
0x18005c556  pop     rdi
0x18005c557  retn
```
