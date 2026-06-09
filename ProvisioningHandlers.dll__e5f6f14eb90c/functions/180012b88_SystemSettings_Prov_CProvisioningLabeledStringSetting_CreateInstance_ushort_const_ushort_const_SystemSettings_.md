# SystemSettings::Prov::CProvisioningLabeledStringSetting::CreateInstance(ushort const *,ushort const *,SystemSettings::Prov::CProvisioningLabeledStringSetting * *)

- ea: `0x180012b88`
- end: `0x180012d4c`
- name: `?CreateInstance@CProvisioningLabeledStringSetting@Prov@SystemSettings@@SAJPEBG0PEAPEAV123@@Z`
- size: `452`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, STRSAFE_PCNZWCH, struct SystemSettings::Prov::CProvisioningLabeledStringSetting **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001d940`

## callees

- `0x1800034b8`
- `0x1800067fc`
- `0x1800087ec`
- `0x18000f8d4`
- `0x180010500`
- `0x180012b88`
- `0x18001e484`
- `0x18001ed70`
- `0x18001ef78`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::Prov::CProvisioningLabeledStringSetting::CreateInstance(
        STRSAFE_PCNZWCH pszSrc,
        STRSAFE_PCNZWCH a2,
        struct SystemSettings::Prov::CProvisioningLabeledStringSetting **a3)
{
  struct SystemSettings::Prov::CProvisioningLabeledStringSetting *v6; // rbp
  SystemSettings::Prov::CProvisioningLabeledStringSetting *v7; // rax
  struct SystemSettings::Prov::CProvisioningLabeledStringSetting *v8; // rbx
  int v9; // ebx
  __int64 v10; // rdx
  char *v11; // r14
  unsigned __int64 v12; // rdi
  unsigned __int64 v13; // rsi
  size_t v14; // rdx
  wchar_t *v15; // rcx
  unsigned __int64 v16; // r9
  int v17; // eax
  size_t v18; // rdx
  wchar_t *v19; // rcx
  int cchToCopy; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  struct SystemSettings::Prov::CProvisioningLabeledStringSetting *v23; // [rsp+80h] [rbp+18h] BYREF
  SystemSettings::Prov::CProvisioningLabeledStringSetting *v24; // [rsp+88h] [rbp+20h] BYREF

  *a3 = 0;
  v6 = 0;
  v23 = 0;
  v7 = (SystemSettings::Prov::CProvisioningLabeledStringSetting *)operator new(
                                                                    0x118u,
                                                                    (const struct std::nothrow_t *)std::nothrow);
  v24 = v7;
  v8 = 0;
  if ( v7 )
  {
    v6 = (struct SystemSettings::Prov::CProvisioningLabeledStringSetting *)SystemSettings::Prov::CProvisioningLabeledStringSetting::CProvisioningLabeledStringSetting(v7);
    v23 = v6;
    v24 = 0;
    v8 = v6;
  }
  Microsoft::WRL::Details::MakeAllocator<Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>>::~MakeAllocator<Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>>(&v24);
  if ( v8 )
  {
    v11 = (char *)v8 + 208;
    v12 = -1;
    if ( pszSrc )
    {
      v13 = -1;
      do
        ++v13;
      while ( pszSrc[v13] );
      v9 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
             (__int64)v8 + 208,
             v13);
      if ( v9 < 0 )
      {
        v10 = 183;
        goto LABEL_16;
      }
      v14 = v13 + 1;
      if ( v13 != -1 )
      {
        v15 = *(wchar_t **)v11;
        if ( v14 > 0x7FFFFFFF || v13 > 0x7FFFFFFE )
          *v15 = 0;
        else
          StringCopyWorkerW_0(v15, v14, 0, pszSrc, v13);
      }
      *((_QWORD *)v11 + 1) = v13;
    }
    else
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)v8 + 208);
    }
    if ( a2 )
    {
      do
        ++v12;
      while ( a2[v12] );
      v17 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
              (__int64)v6 + 232,
              v12);
      v9 = v17;
      if ( v17 < 0 )
      {
        v16 = (unsigned int)v17;
        v10 = 184;
        goto LABEL_17;
      }
      v18 = v12 + 1;
      if ( v12 != -1 )
      {
        v19 = (wchar_t *)*((_QWORD *)v6 + 29);
        if ( v18 > 0x7FFFFFFF || v12 > 0x7FFFFFFE )
          *v19 = 0;
        else
          StringCopyWorkerW_0(v19, v18, 0, a2, v12);
      }
      *((_QWORD *)v6 + 30) = v12;
    }
    else
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)v6 + 232);
    }
    v23 = 0;
    *a3 = v6;
    v9 = 0;
    goto LABEL_31;
  }
  v9 = -2147024882;
  v10 = 182;
LABEL_16:
  v16 = (unsigned int)v9;
LABEL_17:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
    (const char *)v16,
    cchToCopy);
LABEL_31:
  Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease((__int64 *)&v23);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180012b88  mov     rax, rsp
0x180012b8b  mov     [rax+8], rbx
0x180012b8f  push    rbp
0x180012b90  push    rsi
0x180012b91  push    rdi
0x180012b92  push    r12
0x180012b94  push    r13
0x180012b96  push    r14
0x180012b98  push    r15
0x180012b9a  sub     rsp, 30h
0x180012b9e  mov     r13, r8
0x180012ba1  mov     r12, rdx
0x180012ba4  mov     r15, rcx
0x180012ba7  xor     esi, esi
0x180012ba9  mov     [r8], rsi
0x180012bac  mov     ebp, esi
0x180012bae  mov     [rax+18h], rsi
0x180012bb2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180012bb9  mov     ecx, 118h; unsigned __int64
0x180012bbe  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180012bc3  mov     [rsp+68h+arg_18], rax
0x180012bcb  mov     ebx, esi
0x180012bcd  test    rax, rax
0x180012bd0  jz      short loc_180012BF0
0x180012bd2  mov     rcx, rax; this
0x180012bd5  call    ??0CProvisioningLabeledStringSetting@Prov@SystemSettings@@QEAA@XZ; SystemSettings::Prov::CProvisioningLabeledStringSetting::CProvisioningLabeledStringSetting(void)
0x180012bda  mov     rbp, rax
0x180012bdd  mov     [rsp+68h+arg_10], rax
0x180012be5  mov     [rsp+68h+arg_18], rsi
0x180012bed  mov     rbx, rax
0x180012bf0  lea     rcx, [rsp+68h+arg_18]
0x180012bf8  call    ??1?$MakeAllocator@V?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$VectorOptions@PEAUIInspectable@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>>::~MakeAllocator<Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>>(void)
0x180012bfd  test    rbx, rbx
0x180012c00  jnz     short loc_180012C0E
0x180012c02  mov     ebx, 8007000Eh
0x180012c07  mov     edx, 0B6h
0x180012c0c  jmp     short loc_180012C7E
0x180012c0e  lea     r14, [rbx+0D0h]
0x180012c15  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180012c19  test    r15, r15
0x180012c1c  jz      short loc_180012C97
0x180012c1e  mov     rsi, rdi
0x180012c21  xor     eax, eax
0x180012c23  inc     rsi
0x180012c26  cmp     [r15+rsi*2], ax
0x180012c2b  jnz     short loc_180012C23
0x180012c2d  mov     rdx, rsi
0x180012c30  mov     rcx, r14
0x180012c33  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x180012c38  mov     ebx, eax
0x180012c3a  xor     eax, eax
0x180012c3c  test    ebx, ebx
0x180012c3e  js      short loc_180012C79
0x180012c40  lea     rdx, [rsi+1]; cchDest
0x180012c44  test    rdx, rdx
0x180012c47  jz      short loc_180012C73
0x180012c49  mov     rcx, [r14]; pszDest
0x180012c4c  cmp     rdx, 7FFFFFFFh
0x180012c53  ja      short loc_180012C70
0x180012c55  cmp     rsi, 7FFFFFFEh
0x180012c5c  ja      short loc_180012C70
0x180012c5e  mov     qword ptr [rsp+68h+cchToCopy], rsi; cchToCopy
0x180012c63  mov     r9, r15; pszSrc
0x180012c66  xor     r8d, r8d; pcchNewDestLength
0x180012c69  call    StringCopyWorkerW_0
0x180012c6e  jmp     short loc_180012C73
0x180012c70  mov     [rcx], ax
0x180012c73  mov     [r14+8], rsi
0x180012c77  jmp     short loc_180012C9F
0x180012c79  mov     edx, 0B7h; void *
0x180012c7e  mov     r9d, ebx; char *
0x180012c81  mov     rcx, [rsp+68h]; this
0x180012c86  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\systemsettings"...
0x180012c8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012c92  jmp     loc_180012D27
0x180012c97  mov     rcx, r14
0x180012c9a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180012c9f  lea     rsi, [rbp+0E8h]
0x180012ca6  xor     r14d, r14d
0x180012ca9  test    r12, r12
0x180012cac  jz      short loc_180012D10
0x180012cae  inc     rdi
0x180012cb1  cmp     [r12+rdi*2], r14w
0x180012cb6  jnz     short loc_180012CAE
0x180012cb8  mov     rdx, rdi
0x180012cbb  mov     rcx, rsi
0x180012cbe  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x180012cc3  mov     ebx, eax
0x180012cc5  test    eax, eax
0x180012cc7  js      short loc_180012D03
0x180012cc9  lea     rdx, [rdi+1]; cchDest
0x180012ccd  test    rdx, rdx
0x180012cd0  jz      short loc_180012CFD
0x180012cd2  mov     rcx, [rsi]; pszDest
0x180012cd5  cmp     rdx, 7FFFFFFFh
0x180012cdc  ja      short loc_180012CF9
0x180012cde  cmp     rdi, 7FFFFFFEh
0x180012ce5  ja      short loc_180012CF9
0x180012ce7  mov     qword ptr [rsp+68h+cchToCopy], rdi; cchToCopy
0x180012cec  mov     r9, r12; pszSrc
0x180012cef  xor     r8d, r8d; pcchNewDestLength
0x180012cf2  call    StringCopyWorkerW_0
0x180012cf7  jmp     short loc_180012CFD
0x180012cf9  mov     [rcx], r14w
0x180012cfd  mov     [rsi+8], rdi
0x180012d01  jmp     short loc_180012D18
0x180012d03  mov     r9d, eax
0x180012d06  mov     edx, 0B8h
0x180012d0b  jmp     loc_180012C81
0x180012d10  mov     rcx, rsi
0x180012d13  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180012d18  mov     [rsp+68h+arg_10], r14
0x180012d20  mov     [r13+0], rbp
0x180012d24  mov     ebx, r14d
0x180012d27  lea     rcx, [rsp+68h+arg_10]
0x180012d2f  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180012d34  mov     eax, ebx
0x180012d36  mov     rbx, [rsp+68h+arg_0]
0x180012d3b  add     rsp, 30h
0x180012d3f  pop     r15
0x180012d41  pop     r14
0x180012d43  pop     r13
0x180012d45  pop     r12
0x180012d47  pop     rdi
0x180012d48  pop     rsi
0x180012d49  pop     rbp
0x180012d4a  retn
```
