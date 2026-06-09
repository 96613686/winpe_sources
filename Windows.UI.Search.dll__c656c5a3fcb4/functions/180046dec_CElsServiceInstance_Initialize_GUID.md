# CElsServiceInstance::Initialize(_GUID)

- ea: `0x180046dec`
- end: `0x180046eb7`
- name: `?Initialize@CElsServiceInstance@@IEAAJU_GUID@@@Z`
- size: `203`
- prototype: `__int64 __fastcall(PMAPPING_SERVICE_INFO *prgServices, struct _GUID *__struct_ptr)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180044b70`
- `0x180046818`
- `0x1800758e0`

## callees

- `0x1800030b6`
- `0x180046dec`
- `0x180076c50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180046e2b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180046e2b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180046e8a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180046e8a`
- `elscore!MappingGetServices` at `0x180046e66`
- `elscore!MappingGetServices` at `0x180046e66`

## pseudocode

```c
__int64 __fastcall CElsServiceInstance::Initialize(PMAPPING_SERVICE_INFO *prgServices, struct _GUID *a2)
{
  HRESULT Services; // edi
  _MAPPING_ENUM_OPTIONS pOptions; // [rsp+20h] [rbp-78h] BYREF
  __int128 v6; // [rsp+70h] [rbp-28h] BYREF

  Services = 0;
  v6 = (__int128)*a2;
  if ( !*((_BYTE *)prgServices + 12) )
  {
    AcquireSRWLockExclusive(&s_srwElsServiceLock);
    if ( !*((_BYTE *)prgServices + 12) )
    {
      memset_0(&pOptions, 0, sizeof(pOptions));
      pOptions.Size = 80;
      pOptions.pGuid = (GUID *)&v6;
      Services = MappingGetServices(&pOptions, prgServices, (DWORD *)prgServices + 2);
      if ( Services >= 0 )
      {
        if ( *((_DWORD *)prgServices + 2) )
          *((_BYTE *)prgServices + 12) = 1;
        else
          Services = -2147467259;
      }
    }
    ReleaseSRWLockExclusive(&s_srwElsServiceLock);
  }
  return (unsigned int)Services;
}

```

## disassembly

```asm
0x180046dec  mov     [rsp+arg_10], rbx
0x180046df1  mov     [rsp+arg_18], rsi
0x180046df6  push    rdi
0x180046df7  sub     rsp, 90h
0x180046dfe  mov     rax, cs:__security_cookie
0x180046e05  xor     rax, rsp
0x180046e08  mov     [rsp+98h+var_18], rax
0x180046e10  movups  xmm0, xmmword ptr [rdx]
0x180046e13  xor     edi, edi
0x180046e15  mov     rbx, rcx
0x180046e18  movdqu  [rsp+98h+var_28], xmm0
0x180046e1e  cmp     [rcx+0Ch], dil
0x180046e22  jnz     short loc_180046E90
0x180046e24  lea     rcx, ?s_srwElsServiceLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x180046e2b  call    cs:__imp_AcquireSRWLockExclusive
0x180046e31  cmp     [rbx+0Ch], dil
0x180046e35  jnz     short loc_180046E83
0x180046e37  mov     edi, 50h ; 'P'
0x180046e3c  lea     rcx, [rsp+98h+pOptions]; void *
0x180046e41  mov     r8d, edi; Size
0x180046e44  xor     edx, edx; Val
0x180046e46  call    memset_0
0x180046e4b  lea     rax, [rsp+98h+var_28]
0x180046e50  mov     [rsp+98h+pOptions.Size], rdi
0x180046e55  lea     r8, [rbx+8]; pdwServicesCount
0x180046e59  mov     [rsp+98h+pOptions.pGuid], rax
0x180046e5e  mov     rdx, rbx; prgServices
0x180046e61  lea     rcx, [rsp+98h+pOptions]; pOptions
0x180046e66  call    cs:__imp_MappingGetServices
0x180046e6c  mov     edi, eax
0x180046e6e  test    eax, eax
0x180046e70  js      short loc_180046E83
0x180046e72  cmp     dword ptr [rbx+8], 0
0x180046e76  jbe     short loc_180046E7E
0x180046e78  mov     byte ptr [rbx+0Ch], 1
0x180046e7c  jmp     short loc_180046E83
0x180046e7e  mov     edi, 80004005h
0x180046e83  lea     rcx, ?s_srwElsServiceLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x180046e8a  call    cs:__imp_ReleaseSRWLockExclusive
0x180046e90  mov     eax, edi
0x180046e92  mov     rcx, [rsp+98h+var_18]
0x180046e9a  xor     rcx, rsp; StackCookie
0x180046e9d  call    __security_check_cookie
0x180046ea2  lea     r11, [rsp+98h+var_8]
0x180046eaa  mov     rbx, [r11+20h]
0x180046eae  mov     rsi, [r11+28h]
0x180046eb2  mov     rsp, r11
0x180046eb5  pop     rdi
0x180046eb6  retn
```
