# CElsServiceInstance::Initialize(_GUID)

- ea: `0x180065b50`
- end: `0x180065c1b`
- name: `?Initialize@CElsServiceInstance@@IEAAJU_GUID@@@Z`
- size: `203`
- prototype: `__int64 __fastcall(PMAPPING_SERVICE_INFO *prgServices, struct _GUID *__struct_ptr)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180063a34`
- `0x18006557c`

## callees

- `0x180043c30`
- `0x1800446fc`
- `0x180065b50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180065b8f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180065b8f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180065bee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180065bee`
- `ext-ms-win-els-elscore-l1-1-0!MappingGetServices` at `0x180065bca`
- `ext-ms-win-els-elscore-l1-1-0!MappingGetServices` at `0x180065bca`

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
0x180065b50  mov     [rsp+arg_10], rbx
0x180065b55  mov     [rsp+arg_18], rsi
0x180065b5a  push    rdi
0x180065b5b  sub     rsp, 90h
0x180065b62  mov     rax, cs:__security_cookie
0x180065b69  xor     rax, rsp
0x180065b6c  mov     [rsp+98h+var_18], rax
0x180065b74  movups  xmm0, xmmword ptr [rdx]
0x180065b77  xor     edi, edi
0x180065b79  mov     rbx, rcx
0x180065b7c  movdqu  [rsp+98h+var_28], xmm0
0x180065b82  cmp     [rcx+0Ch], dil
0x180065b86  jnz     short loc_180065BF4
0x180065b88  lea     rcx, ?s_srwElsServiceLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x180065b8f  call    cs:__imp_AcquireSRWLockExclusive
0x180065b95  cmp     [rbx+0Ch], dil
0x180065b99  jnz     short loc_180065BE7
0x180065b9b  mov     edi, 50h ; 'P'
0x180065ba0  lea     rcx, [rsp+98h+pOptions]; void *
0x180065ba5  mov     r8d, edi; Size
0x180065ba8  xor     edx, edx; Val
0x180065baa  call    memset_0
0x180065baf  lea     rax, [rsp+98h+var_28]
0x180065bb4  mov     [rsp+98h+pOptions.Size], rdi
0x180065bb9  lea     r8, [rbx+8]; pdwServicesCount
0x180065bbd  mov     [rsp+98h+pOptions.pGuid], rax
0x180065bc2  mov     rdx, rbx; prgServices
0x180065bc5  lea     rcx, [rsp+98h+pOptions]; pOptions
0x180065bca  call    cs:__imp_MappingGetServices
0x180065bd0  mov     edi, eax
0x180065bd2  test    eax, eax
0x180065bd4  js      short loc_180065BE7
0x180065bd6  cmp     dword ptr [rbx+8], 0
0x180065bda  jbe     short loc_180065BE2
0x180065bdc  mov     byte ptr [rbx+0Ch], 1
0x180065be0  jmp     short loc_180065BE7
0x180065be2  mov     edi, 80004005h
0x180065be7  lea     rcx, ?s_srwElsServiceLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x180065bee  call    cs:__imp_ReleaseSRWLockExclusive
0x180065bf4  mov     eax, edi
0x180065bf6  mov     rcx, [rsp+98h+var_18]
0x180065bfe  xor     rcx, rsp; StackCookie
0x180065c01  call    __security_check_cookie
0x180065c06  lea     r11, [rsp+98h+var_8]
0x180065c0e  mov     rbx, [r11+20h]
0x180065c12  mov     rsi, [r11+28h]
0x180065c16  mov     rsp, r11
0x180065c19  pop     rdi
0x180065c1a  retn
```
