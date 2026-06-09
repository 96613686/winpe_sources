# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180028938`
- end: `0x1800289e1`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `169`
- prototype: `char __fastcall(wil::details_abi::FeatureStateData *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x1800289e8`

## callees

- `0x180026f90`
- `0x180028938`
- `0x180028ab8`
- `0x180028b0c`
- `0x180028b64`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180028974`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180028974`

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
0x180028938  mov     [rsp+arg_18], rbx
0x18002893d  push    rbp
0x18002893e  push    rsi
0x18002893f  push    rdi
0x180028940  sub     rsp, 30h
0x180028944  mov     rbp, r9
0x180028947  mov     ebx, r8d
0x18002894a  mov     esi, edx
0x18002894c  mov     rdi, rcx
0x18002894f  cmp     r8d, 0FEh
0x180028956  jz      short loc_1800289CD
0x180028958  cmp     ebx, 0C8h
0x18002895e  jb      short loc_180028974
0x180028960  cmp     ebx, 100h
0x180028966  jl      short loc_180028970
0x180028968  cmp     ebx, 200h
0x18002896e  jb      short loc_180028974
0x180028970  xor     al, al
0x180028972  jmp     short loc_1800289D4
0x180028974  call    cs:__imp_AcquireSRWLockExclusive
0x18002897a  mov     [rsp+48h+var_28], rdi
0x18002897f  cmp     ebx, 7
0x180028982  ja      short loc_18002898E
0x180028984  mov     eax, 0CCh
0x180028989  bt      eax, ebx
0x18002898c  jb      short loc_1800289AE
0x18002898e  lea     eax, [rbx-100h]
0x180028994  cmp     eax, 7Fh
0x180028997  jbe     short loc_1800289AE
0x180028999  mov     r9d, ebp
0x18002899c  lea     rcx, [rdi+48h]
0x1800289a0  mov     r8d, esi
0x1800289a3  mov     edx, ebx
0x1800289a5  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800289aa  mov     bl, al
0x1800289ac  jmp     short loc_1800289BF
0x1800289ae  mov     r8d, esi
0x1800289b1  lea     rcx, [rdi+8]
0x1800289b5  mov     edx, ebx
0x1800289b7  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800289bc  mov     bl, [rdi+40h]
0x1800289bf  lea     rcx, [rsp+48h+var_28]
0x1800289c4  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800289c9  mov     al, bl
0x1800289cb  jmp     short loc_1800289D4
0x1800289cd  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800289d2  mov     al, 1
0x1800289d4  mov     rbx, [rsp+48h+arg_18]
0x1800289d9  add     rsp, 30h
0x1800289dd  pop     rdi
0x1800289de  pop     rsi
0x1800289df  pop     rbp
0x1800289e0  retn
```
