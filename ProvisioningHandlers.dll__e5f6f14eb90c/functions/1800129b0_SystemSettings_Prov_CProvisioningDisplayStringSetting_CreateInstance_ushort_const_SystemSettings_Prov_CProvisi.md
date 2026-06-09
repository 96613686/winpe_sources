# SystemSettings::Prov::CProvisioningDisplayStringSetting::CreateInstance(ushort const *,SystemSettings::Prov::CProvisioningDisplayStringSetting * *)

- ea: `0x1800129b0`
- end: `0x180012aed`
- name: `?CreateInstance@CProvisioningDisplayStringSetting@Prov@SystemSettings@@SAJPEBGPEAPEAV123@@Z`
- size: `317`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, struct SystemSettings::Prov::CProvisioningDisplayStringSetting **)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001d764`
- `0x18001da3c`

## callees

- `0x1800034b8`
- `0x1800067fc`
- `0x1800087ec`
- `0x18000f7a0`
- `0x180010500`
- `0x1800129b0`
- `0x18001e484`
- `0x18001ed70`
- `0x18001ef78`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::Prov::CProvisioningDisplayStringSetting::CreateInstance(
        STRSAFE_PCNZWCH pszSrc,
        struct SystemSettings::Prov::CProvisioningDisplayStringSetting **a2)
{
  struct SystemSettings::Prov::CProvisioningDisplayStringSetting *v4; // rbp
  SystemSettings::Prov::CProvisioningDisplayStringSetting *v5; // rax
  struct SystemSettings::Prov::CProvisioningDisplayStringSetting *v6; // rsi
  unsigned int v7; // edi
  __int64 v8; // r9
  __int64 v9; // rdx
  unsigned __int64 v10; // rbx
  int v11; // eax
  size_t v12; // rdx
  wchar_t *v13; // rcx
  int cchToCopy; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  struct SystemSettings::Prov::CProvisioningDisplayStringSetting *v17; // [rsp+68h] [rbp+10h] BYREF
  SystemSettings::Prov::CProvisioningDisplayStringSetting *v18; // [rsp+70h] [rbp+18h] BYREF

  *a2 = 0;
  v4 = 0;
  v17 = 0;
  v5 = (SystemSettings::Prov::CProvisioningDisplayStringSetting *)operator new(
                                                                    0x100u,
                                                                    (const struct std::nothrow_t *)std::nothrow);
  v18 = v5;
  v6 = 0;
  if ( v5 )
  {
    v4 = (struct SystemSettings::Prov::CProvisioningDisplayStringSetting *)SystemSettings::Prov::CProvisioningDisplayStringSetting::CProvisioningDisplayStringSetting(v5);
    v17 = v4;
    v18 = 0;
    v6 = v4;
  }
  Microsoft::WRL::Details::MakeAllocator<Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>>::~MakeAllocator<Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>>(&v18);
  if ( v6 )
  {
    if ( pszSrc )
    {
      v10 = -1;
      do
        ++v10;
      while ( pszSrc[v10] );
      v11 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
              (__int64)v6 + 208,
              v10);
      v7 = v11;
      if ( v11 < 0 )
      {
        v8 = (unsigned int)v11;
        v9 = 216;
        goto LABEL_16;
      }
      v12 = v10 + 1;
      if ( v10 != -1 )
      {
        v13 = (wchar_t *)*((_QWORD *)v6 + 26);
        if ( v12 > 0x7FFFFFFF || v10 > 0x7FFFFFFE )
          *v13 = 0;
        else
          StringCopyWorkerW_0(v13, v12, 0, pszSrc, v10);
      }
      *((_QWORD *)v6 + 27) = v10;
    }
    else
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)v6 + 208);
    }
    v17 = 0;
    *a2 = v4;
    v7 = 0;
    goto LABEL_19;
  }
  v7 = -2147024882;
  v8 = 2147942414LL;
  v9 = 215;
LABEL_16:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
    (const char *)v8,
    cchToCopy);
LABEL_19:
  Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease((__int64 *)&v17);
  return v7;
}

```

## disassembly

```asm
0x1800129b0  mov     [rsp+arg_0], rbx
0x1800129b5  mov     [rsp+arg_18], rbp
0x1800129ba  push    rsi
0x1800129bb  push    rdi
0x1800129bc  push    r12
0x1800129be  push    r14
0x1800129c0  push    r15
0x1800129c2  sub     rsp, 30h
0x1800129c6  mov     r15, rdx
0x1800129c9  mov     r14, rcx
0x1800129cc  xor     r12d, r12d
0x1800129cf  mov     [rdx], r12
0x1800129d2  mov     ebp, r12d
0x1800129d5  mov     [rsp+58h+arg_8], r12
0x1800129da  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800129e1  mov     ecx, 100h; unsigned __int64
0x1800129e6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800129eb  mov     [rsp+58h+arg_10], rax
0x1800129f0  mov     esi, r12d
0x1800129f3  test    rax, rax
0x1800129f6  jz      short loc_180012A10
0x1800129f8  mov     rcx, rax; this
0x1800129fb  call    ??0CProvisioningDisplayStringSetting@Prov@SystemSettings@@QEAA@XZ; SystemSettings::Prov::CProvisioningDisplayStringSetting::CProvisioningDisplayStringSetting(void)
0x180012a00  mov     rbp, rax
0x180012a03  mov     [rsp+58h+arg_8], rax
0x180012a08  mov     [rsp+58h+arg_10], r12
0x180012a0d  mov     rsi, rax
0x180012a10  lea     rcx, [rsp+58h+arg_10]
0x180012a15  call    ??1?$MakeAllocator@V?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$VectorOptions@PEAUIInspectable@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>>::~MakeAllocator<Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>>(void)
0x180012a1a  test    rsi, rsi
0x180012a1d  jnz     short loc_180012A2E
0x180012a1f  mov     edi, 8007000Eh
0x180012a24  mov     r9d, edi
0x180012a27  mov     edx, 0D7h
0x180012a2c  jmp     short loc_180012A9F
0x180012a2e  test    r14, r14
0x180012a31  jz      short loc_180012AB2
0x180012a33  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180012a37  inc     rbx
0x180012a3a  cmp     [r14+rbx*2], r12w
0x180012a3f  jnz     short loc_180012A37
0x180012a41  mov     rdx, rbx
0x180012a44  lea     rcx, [rsi+0D0h]
0x180012a4b  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x180012a50  mov     edi, eax
0x180012a52  test    eax, eax
0x180012a54  js      short loc_180012A97
0x180012a56  lea     rdx, [rbx+1]; cchDest
0x180012a5a  test    rdx, rdx
0x180012a5d  jz      short loc_180012A8E
0x180012a5f  mov     rcx, [rsi+0D0h]; pszDest
0x180012a66  cmp     rdx, 7FFFFFFFh
0x180012a6d  ja      short loc_180012A8A
0x180012a6f  cmp     rbx, 7FFFFFFEh
0x180012a76  ja      short loc_180012A8A
0x180012a78  mov     qword ptr [rsp+58h+cchToCopy], rbx; cchToCopy
0x180012a7d  mov     r9, r14; pszSrc
0x180012a80  xor     r8d, r8d; pcchNewDestLength
0x180012a83  call    StringCopyWorkerW_0
0x180012a88  jmp     short loc_180012A8E
0x180012a8a  mov     [rcx], r12w
0x180012a8e  mov     [rsi+0D8h], rbx
0x180012a95  jmp     short loc_180012ABE
0x180012a97  mov     r9d, eax; char *
0x180012a9a  mov     edx, 0D8h; void *
0x180012a9f  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\systemsettings"...
0x180012aa6  mov     rcx, [rsp+58h]; this
0x180012aab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012ab0  jmp     short loc_180012AC9
0x180012ab2  lea     rcx, [rsi+0D0h]
0x180012ab9  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180012abe  mov     [rsp+58h+arg_8], r12
0x180012ac3  mov     [r15], rbp
0x180012ac6  mov     edi, r12d
0x180012ac9  lea     rcx, [rsp+58h+arg_8]
0x180012ace  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180012ad3  mov     eax, edi
0x180012ad5  mov     rbx, [rsp+58h+arg_0]
0x180012ada  mov     rbp, [rsp+58h+arg_18]
0x180012adf  add     rsp, 30h
0x180012ae3  pop     r15
0x180012ae5  pop     r14
0x180012ae7  pop     r12
0x180012ae9  pop     rdi
0x180012aea  pop     rsi
0x180012aeb  retn
```
