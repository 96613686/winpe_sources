# CAccountsSettingsPane::QueryCachedAccounts(tagACCOUNT_SETTING * *,ulong *,ushort * *)

- ea: `0x18002a400`
- end: `0x18002a626`
- name: `?QueryCachedAccounts@CAccountsSettingsPane@@UEAAJPEAPEAUtagACCOUNT_SETTING@@PEAKPEAPEAG@Z`
- size: `550`
- prototype: `__int64 __fastcall(CAccountsSettingsPane *__hidden this, struct tagACCOUNT_SETTING **, unsigned int *, unsigned __int16 **)`
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
- `0x18002a400`
- `0x18002b004`
- `0x1800303c8`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002a44d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002a44d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002a481`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002a481`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18002a45b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18002a45b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a5de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a5de`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CAccountsSettingsPane::QueryCachedAccounts(
        CAccountsSettingsPane *this,
        struct tagACCOUNT_SETTING **a2,
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
  char *v13; // r14
  void *v14; // rcx
  __int64 v15; // rdi
  int (__fastcall *v16)(__int64, _QWORD, struct Windows::UI::ApplicationSettings::IWebAccountCommand **); // rbx
  CAccountsSettingsPane *v17; // rcx
  unsigned int v18; // edx
  void *v19; // rcx
  int v20; // ebx
  void *v21; // r10
  void *v23; // [rsp+30h] [rbp-38h] BYREF
  struct Windows::UI::ApplicationSettings::IWebAccountCommand *v24; // [rsp+38h] [rbp-30h] BYREF
  unsigned __int64 v25; // [rsp+40h] [rbp-28h] BYREF
  unsigned __int16 *v26; // [rsp+48h] [rbp-20h] BYREF
  __int64 v27; // [rsp+50h] [rbp-18h]
  __int64 v28; // [rsp+58h] [rbp-10h]
  unsigned __int64 v29; // [rsp+B0h] [rbp+48h] BYREF
  struct tagACCOUNT_SETTING **v30; // [rsp+B8h] [rbp+50h]
  unsigned int *v31; // [rsp+C0h] [rbp+58h]
  unsigned __int16 **v32; // [rsp+C8h] [rbp+60h]

  v32 = a4;
  v31 = a3;
  v30 = a2;
  v4 = a4;
  v6 = 0;
  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  v7 = 0;
  v8 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v9 = (char *)this + 32;
  AcquireSRWLockShared((PSRWLOCK)this + 4);
  v29 = (unsigned __int64)v9;
  if ( !WindowsIsStringEmpty(*((HSTRING *)this + 5)) )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v26);
    v10 = -1;
    v27 = -1;
    v28 = -1;
    StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 5), 0);
    do
      ++v10;
    while ( StringRawBuffer[v10] );
    v7 = _AllocStringWorker<CTCoAllocPolicy>(&v26, v12, StringRawBuffer);
    v8 = v26;
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v29);
  if ( v7 >= 0 )
  {
    LODWORD(v29) = 0;
    v7 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64 *))(**((_QWORD **)this + 7) + 56LL))(
           *((_QWORD *)this + 7),
           &v29);
    if ( v7 >= 0 )
    {
      if ( !(_DWORD)v29 )
      {
LABEL_20:
        v26 = 0;
        v28 = 0;
        v27 = 0;
        *v4 = v8;
        goto LABEL_21;
      }
      v13 = 0;
      v23 = 0;
      v24 = 0;
      v7 = ULongLongMult((unsigned int)v29, 0x28u, (unsigned __int64 *)&v24);
      if ( v7 >= 0 )
      {
        v7 = CTCoAllocPolicy::Alloc(v14, 1u, (unsigned __int64)v24, &v23);
        v13 = (char *)v23;
      }
      if ( v7 >= 0 )
      {
        while ( v6 < (unsigned int)v29 )
        {
          v24 = 0;
          v15 = *((_QWORD *)this + 7);
          v16 = *(int (__fastcall **)(__int64, _QWORD, struct Windows::UI::ApplicationSettings::IWebAccountCommand **))(*(_QWORD *)v15 + 48LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
          if ( v16(v15, v6, &v24) < 0
            || (int)CAccountsSettingsPane::_PopulateAccountSetting(v17, v24, (struct tagACCOUNT_SETTING *)&v13[40 * v6]) < 0 )
          {
            v13 = 0;
            v23 = 0;
            v25 = 0;
            v20 = ULongLongMult(v6, 0x28u, &v25);
            if ( v20 >= 0 )
            {
              v20 = CTCoAllocPolicy::Realloc(v19, v18, v21, v25, &v23);
              v13 = (char *)v23;
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
            if ( v20 < 0 )
            {
              v7 = v20;
              CoTaskMemFree(v13);
              goto LABEL_21;
            }
            break;
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
          ++v6;
        }
        *v31 = v6;
        *v30 = (struct tagACCOUNT_SETTING *)v13;
        v4 = v32;
        goto LABEL_20;
      }
    }
  }
LABEL_21:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v26);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002a400  mov     [rsp-40h+arg_18], r9
0x18002a405  mov     [rsp-40h+arg_10], r8
0x18002a40a  mov     [rsp-40h+arg_8], rdx
0x18002a40f  push    rbp
0x18002a410  push    rbx
0x18002a411  push    rsi
0x18002a412  push    rdi
0x18002a413  push    r12
0x18002a415  push    r13
0x18002a417  push    r14
0x18002a419  push    r15
0x18002a41b  mov     rbp, rsp
0x18002a41e  sub     rsp, 68h
0x18002a422  mov     rdi, r9
0x18002a425  mov     r13, rcx
0x18002a428  xor     r15d, r15d
0x18002a42b  mov     [rdx], r15
0x18002a42e  mov     [r8], r15d
0x18002a431  mov     [r9], r15
0x18002a434  mov     esi, r15d
0x18002a437  mov     r12d, r15d
0x18002a43a  mov     [rbp+var_20], r15
0x18002a43e  mov     [rbp+var_18], r15
0x18002a442  mov     [rbp+var_10], r15
0x18002a446  lea     rbx, [rcx+20h]
0x18002a44a  mov     rcx, rbx; SRWLock
0x18002a44d  call    cs:__imp_AcquireSRWLockShared
0x18002a453  mov     [rbp+arg_0], rbx
0x18002a457  mov     rcx, [r13+28h]; string
0x18002a45b  call    cs:__imp_WindowsIsStringEmpty
0x18002a461  nop
0x18002a462  test    eax, eax
0x18002a464  jnz     short loc_18002A4AC
0x18002a466  lea     rcx, [rbp+var_20]
0x18002a46a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002a46f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002a473  mov     [rbp+var_18], rbx
0x18002a477  mov     [rbp+var_10], rbx
0x18002a47b  xor     edx, edx; length
0x18002a47d  mov     rcx, [r13+28h]; string
0x18002a481  call    cs:__imp_WindowsGetStringRawBuffer
0x18002a487  nop
0x18002a488  inc     rbx
0x18002a48b  cmp     [rax+rbx*2], r15w
0x18002a490  jnz     short loc_18002A488
0x18002a492  lea     rcx, [rbp+var_20]
0x18002a496  mov     [rsp+68h+var_40], rcx
0x18002a49b  mov     r9, rbx
0x18002a49e  mov     r8, rax
0x18002a4a1  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18002a4a6  mov     esi, eax
0x18002a4a8  mov     r12, [rbp+var_20]
0x18002a4ac  lea     rcx, [rbp+arg_0]
0x18002a4b0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002a4b5  test    esi, esi
0x18002a4b7  js      loc_18002A60A
0x18002a4bd  mov     dword ptr [rbp+arg_0], r15d
0x18002a4c1  mov     rcx, [r13+38h]
0x18002a4c5  mov     rax, [rcx]
0x18002a4c8  lea     rdx, [rbp+arg_0]
0x18002a4cc  mov     rax, [rax+38h]
0x18002a4d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a4d5  mov     esi, eax
0x18002a4d7  test    eax, eax
0x18002a4d9  js      loc_18002A60A
0x18002a4df  mov     eax, dword ptr [rbp+arg_0]
0x18002a4e2  test    eax, eax
0x18002a4e4  jz      loc_18002A5FB
0x18002a4ea  mov     r14, r15
0x18002a4ed  mov     [rbp+var_38], r15
0x18002a4f1  mov     [rbp+var_30], r15
0x18002a4f5  mov     ecx, eax; unsigned __int64
0x18002a4f7  lea     r8, [rbp+var_30]; unsigned __int64 *
0x18002a4fb  mov     edx, 28h ; '('; unsigned __int64
0x18002a500  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18002a505  mov     esi, eax
0x18002a507  test    eax, eax
0x18002a509  js      short loc_18002A523
0x18002a50b  lea     r9, [rbp+var_38]; void **
0x18002a50f  mov     r8, [rbp+var_30]; unsigned __int64
0x18002a513  mov     edx, 1; unsigned int
0x18002a518  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18002a51d  mov     esi, eax
0x18002a51f  mov     r14, [rbp+var_38]
0x18002a523  test    esi, esi
0x18002a525  js      loc_18002A60A
0x18002a52b  cmp     r15d, dword ptr [rbp+arg_0]
0x18002a52f  jnb     loc_18002A5E6
0x18002a535  mov     [rbp+var_30], 0
0x18002a53d  mov     rdi, [r13+38h]
0x18002a541  mov     rax, [rdi]
0x18002a544  mov     rbx, [rax+30h]
0x18002a548  lea     rcx, [rbp+var_30]
0x18002a54c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002a551  lea     r8, [rbp+var_30]
0x18002a555  mov     edx, r15d
0x18002a558  mov     rcx, rdi
0x18002a55b  mov     rax, rbx
0x18002a55e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a563  mov     ebx, r15d
0x18002a566  test    eax, eax
0x18002a568  js      short loc_18002A58D
0x18002a56a  lea     rax, [rbx+rbx*4]
0x18002a56e  lea     r8, [r14+rax*8]; struct tagACCOUNT_SETTING *
0x18002a572  mov     rdx, [rbp+var_30]; struct Windows::UI::ApplicationSettings::IWebAccountCommand *
0x18002a576  call    ?_PopulateAccountSetting@CAccountsSettingsPane@@AEAAJPEAUIWebAccountCommand@ApplicationSettings@UI@Windows@@PEAUtagACCOUNT_SETTING@@@Z; CAccountsSettingsPane::_PopulateAccountSetting(Windows::UI::ApplicationSettings::IWebAccountCommand *,tagACCOUNT_SETTING *)
0x18002a57b  test    eax, eax
0x18002a57d  js      short loc_18002A58D
0x18002a57f  lea     rcx, [rbp+var_30]
0x18002a583  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002a588  inc     r15d
0x18002a58b  jmp     short loc_18002A52B
0x18002a58d  mov     r10, r14
0x18002a590  xor     r14d, r14d
0x18002a593  mov     [rbp+var_38], r14
0x18002a597  mov     [rbp+var_28], r14
0x18002a59b  lea     r8, [rbp+var_28]; unsigned __int64 *
0x18002a59f  lea     edx, [r14+28h]; unsigned __int64
0x18002a5a3  mov     rcx, rbx; unsigned __int64
0x18002a5a6  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18002a5ab  mov     ebx, eax
0x18002a5ad  test    eax, eax
0x18002a5af  js      short loc_18002A5CC
0x18002a5b1  lea     rax, [rbp+var_38]
0x18002a5b5  mov     [rsp+68h+var_48], rax; void **
0x18002a5ba  mov     r9, [rbp+var_28]; unsigned __int64
0x18002a5be  mov     r8, r10; void *
0x18002a5c1  call    ?Realloc@CTCoAllocPolicy@@SAJPEAXK0_KPEAPEAX@Z; CTCoAllocPolicy::Realloc(void *,ulong,void *,unsigned __int64,void * *)
0x18002a5c6  mov     ebx, eax
0x18002a5c8  mov     r14, [rbp+var_38]
0x18002a5cc  lea     rcx, [rbp+var_30]
0x18002a5d0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002a5d5  test    ebx, ebx
0x18002a5d7  jns     short loc_18002A5E6
0x18002a5d9  mov     esi, ebx
0x18002a5db  mov     rcx, r14; pv
0x18002a5de  call    cs:__imp_CoTaskMemFree
0x18002a5e4  jmp     short loc_18002A60A
0x18002a5e6  mov     rax, [rbp+arg_10]
0x18002a5ea  mov     [rax], r15d
0x18002a5ed  mov     rax, [rbp+arg_8]
0x18002a5f1  mov     [rax], r14
0x18002a5f4  mov     rdi, [rbp+arg_18]
0x18002a5f8  xor     r15d, r15d
0x18002a5fb  mov     [rbp+var_20], r15
0x18002a5ff  mov     [rbp+var_10], r15
0x18002a603  mov     [rbp+var_18], r15
0x18002a607  mov     [rdi], r12
0x18002a60a  lea     rcx, [rbp+var_20]
0x18002a60e  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002a613  mov     eax, esi
0x18002a615  add     rsp, 68h
0x18002a619  pop     r15
0x18002a61b  pop     r14
0x18002a61d  pop     r13
0x18002a61f  pop     r12
0x18002a621  pop     rdi
0x18002a622  pop     rsi
0x18002a623  pop     rbx
0x18002a624  pop     rbp
0x18002a625  retn
```
