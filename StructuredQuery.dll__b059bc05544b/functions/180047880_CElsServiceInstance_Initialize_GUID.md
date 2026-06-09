# CElsServiceInstance::Initialize(_GUID)

- ea: `0x180047880`
- end: `0x1800478e3`
- name: `?Initialize@CElsServiceInstance@@IEAAJU_GUID@@@Z`
- size: `99`
- prototype: `__int64 __fastcall(PMAPPING_SERVICE_INFO *prgServices, struct _GUID *__struct_ptr)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180047390`
- `0x180047790`
- `0x18006fb04`

## callees

- `0x180047880`
- `0x18005daf0`
- `0x18005e740`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008a7b3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008a7b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008a812`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008a812`
- `ext-ms-win-els-elscore-l1-1-0!MappingGetServices` at `0x18008a7ee`
- `ext-ms-win-els-elscore-l1-1-0!MappingGetServices` at `0x18008a7ee`

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
0x180047880  mov     [rsp+arg_10], rbx
0x180047885  mov     [rsp+arg_18], rsi
0x18004788a  push    rdi
0x18004788b  sub     rsp, 90h
0x180047892  mov     rax, cs:__security_cookie
0x180047899  xor     rax, rsp
0x18004789c  mov     [rsp+98h+var_18], rax
0x1800478a4  movups  xmm0, xmmword ptr [rdx]
0x1800478a7  xor     edi, edi
0x1800478a9  mov     rbx, rcx
0x1800478ac  movdqu  [rsp+98h+var_28], xmm0
0x1800478b2  cmp     [rcx+0Ch], dil
0x1800478b6  jz      loc_18008A7AC
0x1800478bc  mov     eax, edi
0x1800478be  mov     rcx, [rsp+98h+var_18]
0x1800478c6  xor     rcx, rsp; StackCookie
0x1800478c9  call    __security_check_cookie
0x1800478ce  lea     r11, [rsp+98h+var_8]
0x1800478d6  mov     rbx, [r11+20h]
0x1800478da  mov     rsi, [r11+28h]
0x1800478de  mov     rsp, r11
0x1800478e1  pop     rdi
0x1800478e2  retn
0x18008a7ac  lea     rcx, ?s_srwElsServiceLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18008a7b3  call    cs:__imp_AcquireSRWLockExclusive
0x18008a7b9  cmp     [rbx+0Ch], dil
0x18008a7bd  jnz     short loc_18008A80B
0x18008a7bf  mov     edi, 50h ; 'P'
0x18008a7c4  lea     rcx, [rsp+98h+pOptions]; void *
0x18008a7c9  mov     r8d, edi; Size
0x18008a7cc  xor     edx, edx; Val
0x18008a7ce  call    memset_0
0x18008a7d3  lea     rax, [rsp+98h+var_28]
0x18008a7d8  mov     [rsp+98h+pOptions.Size], rdi
0x18008a7dd  lea     r8, [rbx+8]; pdwServicesCount
0x18008a7e1  mov     [rsp+98h+pOptions.pGuid], rax
0x18008a7e6  mov     rdx, rbx; prgServices
0x18008a7e9  lea     rcx, [rsp+98h+pOptions]; pOptions
0x18008a7ee  call    cs:__imp_MappingGetServices
0x18008a7f4  mov     edi, eax
0x18008a7f6  test    eax, eax
0x18008a7f8  js      short loc_18008A80B
0x18008a7fa  cmp     dword ptr [rbx+8], 0
0x18008a7fe  jbe     short loc_18008A806
0x18008a800  mov     byte ptr [rbx+0Ch], 1
0x18008a804  jmp     short loc_18008A80B
0x18008a806  mov     edi, 80004005h
0x18008a80b  lea     rcx, ?s_srwElsServiceLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18008a812  call    cs:__imp_ReleaseSRWLockExclusive
0x18008a818  nop
0x18008a819  jmp     loc_1800478BC
```
