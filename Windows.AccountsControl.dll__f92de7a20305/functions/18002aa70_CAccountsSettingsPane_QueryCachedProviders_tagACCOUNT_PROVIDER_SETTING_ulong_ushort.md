# CAccountsSettingsPane::QueryCachedProviders(tagACCOUNT_PROVIDER_SETTING * *,ulong *,ushort * *)

- ea: `0x18002aa70`
- end: `0x18002aced`
- name: `?QueryCachedProviders@CAccountsSettingsPane@@UEAAJPEAPEAUtagACCOUNT_PROVIDER_SETTING@@PEAKPEAPEAG@Z`
- size: `637`
- prototype: `__int64 __fastcall(CAccountsSettingsPane *__hidden this, struct tagACCOUNT_PROVIDER_SETTING **, unsigned int *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000c16c`
- `0x180011ffc`
- `0x180018f90`
- `0x18001c434`
- `0x18001d3d0`
- `0x1800211c4`
- `0x18002aa70`
- `0x18002b004`
- `0x180030004`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002aabd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002aabd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002aaf1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002aaf1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18002aacb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18002aacb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002aca5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002aca5`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CAccountsSettingsPane::QueryCachedProviders(
        CAccountsSettingsPane *this,
        struct tagACCOUNT_PROVIDER_SETTING **a2,
        unsigned int *a3,
        unsigned __int16 **a4)
{
  unsigned __int16 **v4; // rdi
  unsigned int v6; // r15d
  int v7; // esi
  unsigned __int16 *v8; // r12
  char *v9; // rbx
  __int64 v10; // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v12; // rdx
  struct Windows::Security::Credentials::IWebAccountProvider *v13; // r14
  void *v14; // rcx
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, _QWORD, unsigned __int64 *); // rbx
  int v17; // eax
  unsigned __int64 v18; // rcx
  struct tagACCOUNT_PROVIDER_SETTING *v19; // rax
  unsigned __int64 v20; // rdi
  __int64 (__fastcall *v21)(unsigned __int64, struct Windows::Security::Credentials::IWebAccountProvider **); // rbx
  CAccountsSettingsPane *v22; // rcx
  int v23; // ebx
  unsigned int v24; // edx
  void *v25; // rcx
  int v26; // ebx
  void *v27; // r10
  struct Windows::Security::Credentials::IWebAccountProvider *v29; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int64 v30; // [rsp+38h] [rbp-30h] BYREF
  struct tagACCOUNT_PROVIDER_SETTING *v31; // [rsp+40h] [rbp-28h] BYREF
  unsigned __int16 *v32; // [rsp+48h] [rbp-20h] BYREF
  __int64 v33; // [rsp+50h] [rbp-18h]
  __int64 v34; // [rsp+58h] [rbp-10h]
  unsigned __int64 v35; // [rsp+B0h] [rbp+48h] BYREF
  struct tagACCOUNT_PROVIDER_SETTING **v36; // [rsp+B8h] [rbp+50h]
  unsigned int *v37; // [rsp+C0h] [rbp+58h]
  unsigned __int16 **v38; // [rsp+C8h] [rbp+60h]

  v38 = a4;
  v37 = a3;
  v36 = a2;
  v4 = a4;
  v6 = 0;
  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  v7 = 0;
  v8 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v9 = (char *)this + 32;
  AcquireSRWLockShared((PSRWLOCK)this + 4);
  v35 = (unsigned __int64)v9;
  if ( !WindowsIsStringEmpty(*((HSTRING *)this + 5)) )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v32);
    v10 = -1;
    v33 = -1;
    v34 = -1;
    StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 5), 0);
    do
      ++v10;
    while ( StringRawBuffer[v10] );
    v7 = _AllocStringWorker<CTCoAllocPolicy>(&v32, v12, StringRawBuffer);
    v8 = v32;
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v35);
  if ( v7 >= 0 )
  {
    LODWORD(v35) = 0;
    v7 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64 *))(**((_QWORD **)this + 6) + 56LL))(
           *((_QWORD *)this + 6),
           &v35);
    if ( v7 >= 0 )
    {
      if ( !(_DWORD)v35 )
      {
LABEL_23:
        v32 = 0;
        v34 = 0;
        v33 = 0;
        *v4 = v8;
        goto LABEL_24;
      }
      v13 = 0;
      v29 = 0;
      v30 = 0;
      v7 = ULongLongMult((unsigned int)v35, 0x10u, &v30);
      if ( v7 >= 0 )
      {
        v7 = CTCoAllocPolicy::Alloc(v14, 1u, v30, (void **)&v29);
        v13 = v29;
      }
      if ( v7 >= 0 )
      {
        while ( v6 < (unsigned int)v35 )
        {
          v30 = 0;
          v15 = *((_QWORD *)this + 6);
          v16 = *(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int64 *))(*(_QWORD *)v15 + 48LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
          v17 = v16(v15, v6, &v30);
          v18 = v6;
          if ( v17 < 0 )
            goto LABEL_18;
          v19 = (struct Windows::Security::Credentials::IWebAccountProvider *)((char *)v13 + 16 * v6);
          v31 = v19;
          v20 = v30;
          *(_QWORD *)v19 = 0;
          *((_QWORD *)v19 + 1) = 0;
          v29 = 0;
          v21 = *(__int64 (__fastcall **)(unsigned __int64, struct Windows::Security::Credentials::IWebAccountProvider **))(*(_QWORD *)v20 + 48LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
          v23 = v21(v20, &v29);
          if ( v23 >= 0 )
            v23 = CAccountsSettingsPane::_PopulateAccountProviderSetting(v22, v29, v31);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
          if ( v23 < 0 )
          {
            v18 = v6;
LABEL_18:
            v13 = 0;
            v29 = 0;
            v31 = 0;
            v26 = ULongLongMult(v18, 0x10u, (unsigned __int64 *)&v31);
            if ( v26 >= 0 )
            {
              v26 = CTCoAllocPolicy::Realloc(v25, v24, v27, (unsigned __int64)v31, (void **)&v29);
              v13 = v29;
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
            if ( v26 < 0 )
            {
              v7 = v26;
              CoTaskMemFree(v13);
              goto LABEL_24;
            }
            break;
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
          ++v6;
        }
        *v37 = v6;
        *v36 = v13;
        v4 = v38;
        goto LABEL_23;
      }
    }
  }
LABEL_24:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v32);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002aa70  mov     [rsp-40h+arg_18], r9
0x18002aa75  mov     [rsp-40h+arg_10], r8
0x18002aa7a  mov     [rsp-40h+arg_8], rdx
0x18002aa7f  push    rbp
0x18002aa80  push    rbx
0x18002aa81  push    rsi
0x18002aa82  push    rdi
0x18002aa83  push    r12
0x18002aa85  push    r13
0x18002aa87  push    r14
0x18002aa89  push    r15
0x18002aa8b  mov     rbp, rsp
0x18002aa8e  sub     rsp, 68h
0x18002aa92  mov     rdi, r9
0x18002aa95  mov     r13, rcx
0x18002aa98  xor     r15d, r15d
0x18002aa9b  mov     [rdx], r15
0x18002aa9e  mov     [r8], r15d
0x18002aaa1  mov     [r9], r15
0x18002aaa4  mov     esi, r15d
0x18002aaa7  mov     r12d, r15d
0x18002aaaa  mov     [rbp+var_20], r15
0x18002aaae  mov     [rbp+var_18], r15
0x18002aab2  mov     [rbp+var_10], r15
0x18002aab6  lea     rbx, [rcx+20h]
0x18002aaba  mov     rcx, rbx; SRWLock
0x18002aabd  call    cs:__imp_AcquireSRWLockShared
0x18002aac3  mov     [rbp+arg_0], rbx
0x18002aac7  mov     rcx, [r13+28h]; string
0x18002aacb  call    cs:__imp_WindowsIsStringEmpty
0x18002aad1  nop
0x18002aad2  test    eax, eax
0x18002aad4  jnz     short loc_18002AB1C
0x18002aad6  lea     rcx, [rbp+var_20]
0x18002aada  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002aadf  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002aae3  mov     [rbp+var_18], rbx
0x18002aae7  mov     [rbp+var_10], rbx
0x18002aaeb  xor     edx, edx; length
0x18002aaed  mov     rcx, [r13+28h]; string
0x18002aaf1  call    cs:__imp_WindowsGetStringRawBuffer
0x18002aaf7  nop
0x18002aaf8  inc     rbx
0x18002aafb  cmp     [rax+rbx*2], r15w
0x18002ab00  jnz     short loc_18002AAF8
0x18002ab02  lea     rcx, [rbp+var_20]
0x18002ab06  mov     [rsp+68h+var_40], rcx
0x18002ab0b  mov     r9, rbx
0x18002ab0e  mov     r8, rax
0x18002ab11  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18002ab16  mov     esi, eax
0x18002ab18  mov     r12, [rbp+var_20]
0x18002ab1c  lea     rcx, [rbp+arg_0]
0x18002ab20  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002ab25  test    esi, esi
0x18002ab27  js      loc_18002ACD1
0x18002ab2d  mov     dword ptr [rbp+arg_0], r15d
0x18002ab31  mov     rcx, [r13+30h]
0x18002ab35  mov     rax, [rcx]
0x18002ab38  lea     rdx, [rbp+arg_0]
0x18002ab3c  mov     rax, [rax+38h]
0x18002ab40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab45  mov     esi, eax
0x18002ab47  test    eax, eax
0x18002ab49  js      loc_18002ACD1
0x18002ab4f  mov     eax, dword ptr [rbp+arg_0]
0x18002ab52  test    eax, eax
0x18002ab54  jz      loc_18002ACC2
0x18002ab5a  mov     r14, r15
0x18002ab5d  mov     [rbp+var_38], r15
0x18002ab61  mov     [rbp+var_30], r15
0x18002ab65  mov     ecx, eax; unsigned __int64
0x18002ab67  lea     r8, [rbp+var_30]; unsigned __int64 *
0x18002ab6b  mov     edx, 10h; unsigned __int64
0x18002ab70  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18002ab75  mov     esi, eax
0x18002ab77  test    eax, eax
0x18002ab79  js      short loc_18002AB93
0x18002ab7b  lea     r9, [rbp+var_38]; void **
0x18002ab7f  mov     r8, [rbp+var_30]; unsigned __int64
0x18002ab83  mov     edx, 1; unsigned int
0x18002ab88  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18002ab8d  mov     esi, eax
0x18002ab8f  mov     r14, [rbp+var_38]
0x18002ab93  test    esi, esi
0x18002ab95  js      loc_18002ACD1
0x18002ab9b  cmp     r15d, dword ptr [rbp+arg_0]
0x18002ab9f  jnb     loc_18002ACAD
0x18002aba5  mov     [rbp+var_30], 0
0x18002abad  mov     rdi, [r13+30h]
0x18002abb1  mov     rax, [rdi]
0x18002abb4  mov     rbx, [rax+30h]
0x18002abb8  lea     rcx, [rbp+var_30]
0x18002abbc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002abc1  lea     r8, [rbp+var_30]
0x18002abc5  mov     edx, r15d
0x18002abc8  mov     rcx, rdi
0x18002abcb  mov     rax, rbx
0x18002abce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002abd3  mov     ecx, r15d
0x18002abd6  test    eax, eax
0x18002abd8  js      short loc_18002AC57
0x18002abda  mov     eax, ecx
0x18002abdc  shl     rax, 4
0x18002abe0  add     rax, r14
0x18002abe3  mov     [rbp+var_28], rax
0x18002abe7  mov     rdi, [rbp+var_30]
0x18002abeb  mov     qword ptr [rax], 0
0x18002abf2  mov     qword ptr [rax+8], 0
0x18002abfa  mov     [rbp+var_38], 0
0x18002ac02  mov     rax, [rdi]
0x18002ac05  mov     rbx, [rax+30h]
0x18002ac09  lea     rcx, [rbp+var_38]
0x18002ac0d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002ac12  lea     rdx, [rbp+var_38]
0x18002ac16  mov     rcx, rdi
0x18002ac19  mov     rax, rbx
0x18002ac1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac21  mov     ebx, eax
0x18002ac23  test    eax, eax
0x18002ac25  js      short loc_18002AC36
0x18002ac27  mov     r8, [rbp+var_28]; struct tagACCOUNT_PROVIDER_SETTING *
0x18002ac2b  mov     rdx, [rbp+var_38]; struct Windows::Security::Credentials::IWebAccountProvider *
0x18002ac2f  call    ?_PopulateAccountProviderSetting@CAccountsSettingsPane@@AEAAJPEAUIWebAccountProvider@Credentials@Security@Windows@@PEAUtagACCOUNT_PROVIDER_SETTING@@@Z; CAccountsSettingsPane::_PopulateAccountProviderSetting(Windows::Security::Credentials::IWebAccountProvider *,tagACCOUNT_PROVIDER_SETTING *)
0x18002ac34  mov     ebx, eax
0x18002ac36  lea     rcx, [rbp+var_38]
0x18002ac3a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002ac3f  test    ebx, ebx
0x18002ac41  js      short loc_18002AC54
0x18002ac43  lea     rcx, [rbp+var_30]
0x18002ac47  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002ac4c  inc     r15d
0x18002ac4f  jmp     loc_18002AB9B
0x18002ac54  mov     ecx, r15d; unsigned __int64
0x18002ac57  mov     r10, r14
0x18002ac5a  xor     r14d, r14d
0x18002ac5d  mov     [rbp+var_38], r14
0x18002ac61  mov     [rbp+var_28], r14
0x18002ac65  lea     r8, [rbp+var_28]; unsigned __int64 *
0x18002ac69  lea     edx, [r14+10h]; unsigned __int64
0x18002ac6d  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18002ac72  mov     ebx, eax
0x18002ac74  test    eax, eax
0x18002ac76  js      short loc_18002AC93
0x18002ac78  lea     rax, [rbp+var_38]
0x18002ac7c  mov     [rsp+68h+var_48], rax; void **
0x18002ac81  mov     r9, [rbp+var_28]; unsigned __int64
0x18002ac85  mov     r8, r10; void *
0x18002ac88  call    ?Realloc@CTCoAllocPolicy@@SAJPEAXK0_KPEAPEAX@Z; CTCoAllocPolicy::Realloc(void *,ulong,void *,unsigned __int64,void * *)
0x18002ac8d  mov     ebx, eax
0x18002ac8f  mov     r14, [rbp+var_38]
0x18002ac93  lea     rcx, [rbp+var_30]
0x18002ac97  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002ac9c  test    ebx, ebx
0x18002ac9e  jns     short loc_18002ACAD
0x18002aca0  mov     esi, ebx
0x18002aca2  mov     rcx, r14; pv
0x18002aca5  call    cs:__imp_CoTaskMemFree
0x18002acab  jmp     short loc_18002ACD1
0x18002acad  mov     rax, [rbp+arg_10]
0x18002acb1  mov     [rax], r15d
0x18002acb4  mov     rax, [rbp+arg_8]
0x18002acb8  mov     [rax], r14
0x18002acbb  mov     rdi, [rbp+arg_18]
0x18002acbf  xor     r15d, r15d
0x18002acc2  mov     [rbp+var_20], r15
0x18002acc6  mov     [rbp+var_10], r15
0x18002acca  mov     [rbp+var_18], r15
0x18002acce  mov     [rdi], r12
0x18002acd1  lea     rcx, [rbp+var_20]
0x18002acd5  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002acda  mov     eax, esi
0x18002acdc  add     rsp, 68h
0x18002ace0  pop     r15
0x18002ace2  pop     r14
0x18002ace4  pop     r13
0x18002ace6  pop     r12
0x18002ace8  pop     rdi
0x18002ace9  pop     rsi
0x18002acea  pop     rbx
0x18002aceb  pop     rbp
0x18002acec  retn
```
