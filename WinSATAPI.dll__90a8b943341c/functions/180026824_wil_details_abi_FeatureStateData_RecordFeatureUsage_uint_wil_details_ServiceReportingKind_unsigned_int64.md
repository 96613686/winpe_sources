# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180026824`
- end: `0x1800268ec`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x1800268f4`

## callees

- `0x1800233cc`
- `0x180026824`
- `0x1800269d8`
- `0x180026a10`
- `0x180026a48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180026870`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180026870`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall wil::details_abi::FeatureStateData::RecordFeatureUsage(
        wil::details_abi::FeatureStateData *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4)
{
  int v9; // eax
  char v10; // bl
  wil::details_abi::FeatureStateData *v11; // [rsp+20h] [rbp-18h] BYREF
  __int64 v12; // [rsp+28h] [rbp-10h]

  v12 = -2;
  if ( a3 == 254 )
  {
    wil::details_abi::FeatureStateData::RecordUsage(a1);
    return 1;
  }
  else if ( a3 < 0xC8 || (int)a3 >= 256 && a3 < 0x200 )
  {
    AcquireSRWLockExclusive((PSRWLOCK)a1);
    v11 = a1;
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
              v11,
              v12);
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
0x180026824  mov     rax, rsp
0x180026827  push    rdi
0x180026828  sub     rsp, 30h
0x18002682c  mov     qword ptr [rax-10h], 0FFFFFFFFFFFFFFFEh
0x180026834  mov     [rax+8], rbx
0x180026838  mov     [rax+10h], rbp
0x18002683c  mov     [rax+18h], rsi
0x180026840  mov     rbp, r9
0x180026843  mov     ebx, r8d
0x180026846  mov     esi, edx
0x180026848  mov     rdi, rcx
0x18002684b  cmp     r8d, 0FEh
0x180026852  jz      short loc_1800268CF
0x180026854  cmp     ebx, 0C8h
0x18002685a  jb      short loc_180026870
0x18002685c  cmp     ebx, 100h
0x180026862  jl      short loc_18002686C
0x180026864  cmp     ebx, 200h
0x18002686a  jb      short loc_180026870
0x18002686c  xor     al, al
0x18002686e  jmp     short loc_1800268D6
0x180026870  call    cs:__imp_AcquireSRWLockExclusive
0x180026877  nop     dword ptr [rax+rax+00h]
0x18002687c  mov     [rsp+38h+var_18], rdi
0x180026881  cmp     ebx, 7
0x180026884  ja      short loc_180026890
0x180026886  mov     eax, 0CCh
0x18002688b  bt      eax, ebx
0x18002688e  jb      short loc_1800268B0
0x180026890  lea     eax, [rbx-100h]
0x180026896  cmp     eax, 7Fh
0x180026899  jbe     short loc_1800268B0
0x18002689b  lea     rcx, [rdi+48h]
0x18002689f  mov     r9d, ebp
0x1800268a2  mov     r8d, esi
0x1800268a5  mov     edx, ebx
0x1800268a7  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800268ac  mov     bl, al
0x1800268ae  jmp     short loc_1800268C1
0x1800268b0  mov     r8d, esi
0x1800268b3  mov     edx, ebx
0x1800268b5  lea     rcx, [rdi+8]
0x1800268b9  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800268be  mov     bl, [rdi+40h]
0x1800268c1  lea     rcx, [rsp+38h+var_18]
0x1800268c6  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800268cb  mov     al, bl
0x1800268cd  jmp     short loc_1800268D6
0x1800268cf  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800268d4  mov     al, 1
0x1800268d6  mov     rbx, [rsp+38h+arg_0]
0x1800268db  mov     rbp, [rsp+38h+arg_8]
0x1800268e0  mov     rsi, [rsp+38h+arg_10]
0x1800268e5  add     rsp, 30h
0x1800268e9  pop     rdi
0x1800268ea  retn
```
