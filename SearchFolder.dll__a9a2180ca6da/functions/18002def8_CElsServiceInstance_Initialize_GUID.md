# CElsServiceInstance::Initialize(_GUID)

- ea: `0x18002def8`
- end: `0x18002dfc3`
- name: `?Initialize@CElsServiceInstance@@IEAAJU_GUID@@@Z`
- size: `203`
- prototype: `__int64 __fastcall(PMAPPING_SERVICE_INFO *prgServices, struct _GUID *__struct_ptr)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180029d08`
- `0x18002d70c`

## callees

- `0x180006900`
- `0x1800076dc`
- `0x18002def8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002df37`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002df37`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002df96`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002df96`
- `ext-ms-win-els-elscore-l1-1-0!MappingGetServices` at `0x18002df72`
- `ext-ms-win-els-elscore-l1-1-0!MappingGetServices` at `0x18002df72`

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
0x18002def8  mov     [rsp+arg_10], rbx
0x18002defd  mov     [rsp+arg_18], rsi
0x18002df02  push    rdi
0x18002df03  sub     rsp, 90h
0x18002df0a  mov     rax, cs:__security_cookie
0x18002df11  xor     rax, rsp
0x18002df14  mov     [rsp+98h+var_18], rax
0x18002df1c  movups  xmm0, xmmword ptr [rdx]
0x18002df1f  xor     edi, edi
0x18002df21  mov     rbx, rcx
0x18002df24  movdqu  [rsp+98h+var_28], xmm0
0x18002df2a  cmp     [rcx+0Ch], dil
0x18002df2e  jnz     short loc_18002DF9C
0x18002df30  lea     rcx, ?s_srwElsServiceLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18002df37  call    cs:__imp_AcquireSRWLockExclusive
0x18002df3d  cmp     [rbx+0Ch], dil
0x18002df41  jnz     short loc_18002DF8F
0x18002df43  mov     edi, 50h ; 'P'
0x18002df48  lea     rcx, [rsp+98h+pOptions]; void *
0x18002df4d  mov     r8d, edi; Size
0x18002df50  xor     edx, edx; Val
0x18002df52  call    memset_0
0x18002df57  lea     rax, [rsp+98h+var_28]
0x18002df5c  mov     [rsp+98h+pOptions.Size], rdi
0x18002df61  lea     r8, [rbx+8]; pdwServicesCount
0x18002df65  mov     [rsp+98h+pOptions.pGuid], rax
0x18002df6a  mov     rdx, rbx; prgServices
0x18002df6d  lea     rcx, [rsp+98h+pOptions]; pOptions
0x18002df72  call    cs:__imp_MappingGetServices
0x18002df78  mov     edi, eax
0x18002df7a  test    eax, eax
0x18002df7c  js      short loc_18002DF8F
0x18002df7e  cmp     dword ptr [rbx+8], 0
0x18002df82  jbe     short loc_18002DF8A
0x18002df84  mov     byte ptr [rbx+0Ch], 1
0x18002df88  jmp     short loc_18002DF8F
0x18002df8a  mov     edi, 80004005h
0x18002df8f  lea     rcx, ?s_srwElsServiceLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18002df96  call    cs:__imp_ReleaseSRWLockExclusive
0x18002df9c  mov     eax, edi
0x18002df9e  mov     rcx, [rsp+98h+var_18]
0x18002dfa6  xor     rcx, rsp; StackCookie
0x18002dfa9  call    __security_check_cookie
0x18002dfae  lea     r11, [rsp+98h+var_8]
0x18002dfb6  mov     rbx, [r11+20h]
0x18002dfba  mov     rsi, [r11+28h]
0x18002dfbe  mov     rsp, r11
0x18002dfc1  pop     rdi
0x18002dfc2  retn
```
