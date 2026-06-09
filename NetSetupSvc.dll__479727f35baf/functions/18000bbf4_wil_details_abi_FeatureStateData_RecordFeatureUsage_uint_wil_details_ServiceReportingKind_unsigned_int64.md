# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000bbf4`
- end: `0x18000bc9d`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `169`
- prototype: `char __fastcall(wil::details_abi::FeatureStateData *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18000bca4`

## callees

- `0x180008eb8`
- `0x18000bbf4`
- `0x18000bd90`
- `0x18000bde4`
- `0x18000be3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bc30`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bc30`

## pseudocode

```c
char __fastcall wil::details_abi::FeatureStateData::RecordFeatureUsage(
        wil::details_abi::FeatureStateData *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4)
{
  int v9; // eax
  char v10; // bl
  RTL_SRWLOCK *v11; // [rsp+20h] [rbp-28h] BYREF

  if ( a3 == 254 )
  {
    wil::details_abi::FeatureStateData::RecordUsage(a1);
    return 1;
  }
  else if ( a3 < 0xC8 || (int)a3 >= 256 && a3 < 0x200 )
  {
    AcquireSRWLockExclusive((PSRWLOCK)a1);
    v11 = (RTL_SRWLOCK *)a1;
    if ( a3 <= 7 && (v9 = 204, _bittest(&v9, a3)) || a3 - 256 <= 0x7F )
    {
      wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,0>::RecordUsage(
        (char *)a1 + 8,
        a3,
        a2);
      v10 = *((_BYTE *)a1 + 64);
    }
    else
    {
      v10 = wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,2>::RecordUsage(
              (char *)a1 + 72,
              a3,
              a2,
              a4,
              v11);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
    return v10;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x18000bbf4  mov     [rsp+arg_18], rbx
0x18000bbf9  push    rbp
0x18000bbfa  push    rsi
0x18000bbfb  push    rdi
0x18000bbfc  sub     rsp, 30h
0x18000bc00  mov     rbp, r9
0x18000bc03  mov     ebx, r8d
0x18000bc06  mov     esi, edx
0x18000bc08  mov     rdi, rcx
0x18000bc0b  cmp     r8d, 0FEh
0x18000bc12  jz      short loc_18000BC89
0x18000bc14  cmp     ebx, 0C8h
0x18000bc1a  jb      short loc_18000BC30
0x18000bc1c  cmp     ebx, 100h
0x18000bc22  jl      short loc_18000BC2C
0x18000bc24  cmp     ebx, 200h
0x18000bc2a  jb      short loc_18000BC30
0x18000bc2c  xor     al, al
0x18000bc2e  jmp     short loc_18000BC90
0x18000bc30  call    cs:__imp_AcquireSRWLockExclusive
0x18000bc36  mov     [rsp+48h+var_28], rdi
0x18000bc3b  cmp     ebx, 7
0x18000bc3e  ja      short loc_18000BC4A
0x18000bc40  mov     eax, 0CCh
0x18000bc45  bt      eax, ebx
0x18000bc48  jb      short loc_18000BC6A
0x18000bc4a  lea     eax, [rbx-100h]
0x18000bc50  cmp     eax, 7Fh
0x18000bc53  jbe     short loc_18000BC6A
0x18000bc55  mov     r9d, ebp
0x18000bc58  lea     rcx, [rdi+48h]
0x18000bc5c  mov     r8d, esi
0x18000bc5f  mov     edx, ebx
0x18000bc61  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000bc66  mov     bl, al
0x18000bc68  jmp     short loc_18000BC7B
0x18000bc6a  mov     r8d, esi
0x18000bc6d  lea     rcx, [rdi+8]
0x18000bc71  mov     edx, ebx
0x18000bc73  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000bc78  mov     bl, [rdi+40h]
0x18000bc7b  lea     rcx, [rsp+48h+var_28]
0x18000bc80  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000bc85  mov     al, bl
0x18000bc87  jmp     short loc_18000BC90
0x18000bc89  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000bc8e  mov     al, 1
0x18000bc90  mov     rbx, [rsp+48h+arg_18]
0x18000bc95  add     rsp, 30h
0x18000bc99  pop     rdi
0x18000bc9a  pop     rsi
0x18000bc9b  pop     rbp
0x18000bc9c  retn
```
