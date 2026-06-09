# DataStoreCache::MRTTransformerData::ResolveText(HSTRING__ *,DataStoreCache::MRTTransformerData::TextType,bool)

- ea: `0x18000f898`
- end: `0x18000fba2`
- name: `?ResolveText@MRTTransformerData@DataStoreCache@@AEAA?AVHString@Wrappers@WRL@Microsoft@@PEAUHSTRING__@@W4TextType@12@_N@Z`
- size: `778`
- prototype: `struct Microsoft::WRL::Wrappers::HString __high(HSTRING, enum DataStoreCache::MRTTransformerData::TextType, bool)`
- caller_count: `5`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000f7a0`
- `0x1800fb360`
- `0x18017eb50`
- `0x18036b3b0`
- `0x18036b4a0`

## callees

- `0x18000f898`
- `0x18000fba8`
- `0x18001dac0`
- `0x180030fbc`
- `0x1800385d0`
- `0x18009fec0`
- `0x1800a0360`
- `0x1801a3324`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f9d4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f9d4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000fa12`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000fa12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18000f921`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18000fa52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18000f921`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18000fa52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f90e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f992`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f9b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000fa37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000fa98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000fab6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f90e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f992`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f9b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000fa37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000fa98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000fab6`

## string_xrefs

- `0x18000f94c`: `shellcommon\shell\datastorecache\transformers\mrttransformer\lib\mrttransformer.cpp`
- `0x18000fa63`: `shellcommon\shell\datastorecache\transformers\mrttransformer\lib\mrttransformer.cpp`
- `0x18000fae8`: `shellcommon\shell\datastorecache\transformers\mrttransformer\lib\mrttransformer.cpp`
- `0x18000fb20`: `shellcommon\shell\datastorecache\transformers\mrttransformer\lib\mrttransformer.cpp`
- `0x18000fb58`: `shellcommon\shell\datastorecache\transformers\mrttransformer\lib\mrttransformer.cpp`
- `0x18000fb90`: `shellcommon\shell\datastorecache\transformers\mrttransformer\lib\mrttransformer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
HSTRING *__fastcall DataStoreCache::MRTTransformerData::ResolveText(
        __int64 a1,
        HSTRING *a2,
        ShellMRTHelper::Common *a3,
        int a4,
        char a5)
{
  bool v9; // r15
  bool IsResolvableStringReference; // al
  HRESULT v11; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  HSTRING *v15; // rbx
  int v16; // esi
  int v17; // esi
  int v18; // esi
  HSTRING v19; // rsi
  HRESULT v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  _BYTE v25[128]; // [rsp+30h] [rbp-31h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+57h]
  HSTRING string; // [rsp+C0h] [rbp+5Fh] BYREF
  HSTRING *v28; // [rsp+C8h] [rbp+67h]

  v28 = a2;
  *a2 = 0;
  v9 = 1;
  if ( !*(_QWORD *)(a1 + 136) )
    v9 = *(_QWORD *)(a1 + 144) != 0;
  IsResolvableStringReference = ShellMRTHelper::Common::IsResolvableStringReference(a3, (HSTRING)a2);
  if ( v9 && IsResolvableStringReference )
  {
    v13 = *(_QWORD *)(a1 + 136);
    v14 = a1 + 112;
    if ( v13 )
      DataStoreCache::MRTHelperForPackage::MRTHelperForPackage(v25, v13, v14);
    else
      DataStoreCache::MRTHelperForPriFile::MRTHelperForPriFile(v25, *(_QWORD *)(a1 + 144), v14);
    v15 = (HSTRING *)DataStoreCache::MRTHelper::ResolveString(v25, &string, a3);
    WindowsDeleteString(*a2);
    *a2 = 0;
    *a2 = *v15;
    *v15 = 0;
    WindowsDeleteString(string);
    DataStoreCache::MRTHelper::~MRTHelper((DataStoreCache::MRTHelper *)v25);
    if ( a5 )
    {
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 200));
      if ( a4 )
      {
        v16 = a4 - 1;
        if ( v16 )
        {
          v17 = v16 - 1;
          if ( v17 )
          {
            v18 = v17 - 1;
            if ( v18 )
            {
              if ( v18 == 1 )
              {
                string = *a2;
                v21 = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)(a1 + 184), &string);
                if ( v21 < 0 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0x7A,
                    (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\mrttransformer\\lib\\mrttransformer.cpp",
                    (const char *)(unsigned int)v21,
                    1);
              }
            }
            else
            {
              string = *a2;
              v22 = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)(a1 + 176), &string);
              if ( v22 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x77,
                  (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\mrttransformer\\lib\\mrttransformer.cpp",
                  (const char *)(unsigned int)v22,
                  1);
            }
          }
          else
          {
            string = *a2;
            v23 = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)(a1 + 168), &string);
            if ( v23 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x74,
                (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\mrttransformer\\lib\\mrttransformer.cpp",
                (const char *)(unsigned int)v23,
                1);
          }
        }
        else
        {
          string = *a2;
          v24 = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)(a1 + 160), &string);
          if ( v24 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x71,
              (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\mrttransformer\\lib\\mrttransformer.cpp",
              (const char *)(unsigned int)v24,
              1);
        }
      }
      else
      {
        v19 = *a2;
        if ( !*a2 || (v20 = 0, v19 != *(HSTRING *)(a1 + 152)) )
        {
          WindowsDeleteString(*(HSTRING *)(a1 + 152));
          *(_QWORD *)(a1 + 152) = 0;
          v20 = WindowsDuplicateString(v19, (HSTRING *)(a1 + 152));
        }
        if ( v20 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6E,
            (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\mrttransformer\\lib\\mrttransformer.cpp",
            (const char *)(unsigned int)v20,
            1);
      }
      if ( a1 != -200 )
        ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 200));
    }
  }
  else if ( !a3 || a3 != (ShellMRTHelper::Common *)*a2 )
  {
    WindowsDeleteString(*a2);
    *a2 = 0;
    v11 = WindowsDuplicateString((HSTRING)a3, a2);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x57,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\mrttransformer\\lib\\mrttransformer.cpp",
        (const char *)(unsigned int)v11,
        1);
  }
  return a2;
}

```

## disassembly

```asm
0x18000f898  mov     [rsp-8+arg_10], rbx
0x18000f89d  mov     [rsp-8+arg_8], rdx
0x18000f8a2  push    rbp
0x18000f8a3  push    rsi
0x18000f8a4  push    rdi
0x18000f8a5  push    r14
0x18000f8a7  push    r15
0x18000f8a9  lea     rbp, [rsp-2Fh]
0x18000f8ae  sub     rsp, 90h
0x18000f8b5  mov     esi, r9d
0x18000f8b8  mov     rbx, r8
0x18000f8bb  mov     rdi, rdx
0x18000f8be  mov     r14, rcx
0x18000f8c1  mov     [rbp+4Fh+var_90], 0
0x18000f8c8  mov     qword ptr [rdx], 0
0x18000f8cf  mov     r15d, 1
0x18000f8d5  mov     [rbp+4Fh+var_90], r15d
0x18000f8d9  cmp     qword ptr [rcx+88h], 0
0x18000f8e1  jnz     short loc_18000F8F0
0x18000f8e3  cmp     qword ptr [rcx+90h], 0
0x18000f8eb  jnz     short loc_18000F8F0
0x18000f8ed  xor     r15b, r15b
0x18000f8f0  mov     rcx, rbx; this
0x18000f8f3  call    ?IsResolvableStringReference@Common@ShellMRTHelper@@YA_NPEAUHSTRING__@@@Z; ShellMRTHelper::Common::IsResolvableStringReference(HSTRING__ *)
0x18000f8f8  test    r15b, r15b
0x18000f8fb  jz      short loc_18000F901
0x18000f8fd  test    al, al
0x18000f8ff  jnz     short loc_18000F95E
0x18000f901  test    rbx, rbx
0x18000f904  jz      short loc_18000F90B
0x18000f906  cmp     rbx, [rdi]
0x18000f909  jz      short loc_18000F92B
0x18000f90b  mov     rcx, [rdi]; string
0x18000f90e  call    cs:__imp_WindowsDeleteString
0x18000f914  mov     qword ptr [rdi], 0
0x18000f91b  mov     rdx, rdi; newString
0x18000f91e  mov     rcx, rbx; string
0x18000f921  call    cs:__imp_WindowsDuplicateString
0x18000f927  test    eax, eax
0x18000f929  js      short loc_18000F945
0x18000f92b  mov     rax, rdi
0x18000f92e  mov     rbx, [rsp+0B0h+arg_10]
0x18000f936  add     rsp, 90h
0x18000f93d  pop     r15
0x18000f93f  pop     r14
0x18000f941  pop     rdi
0x18000f942  pop     rsi
0x18000f943  pop     rbp
0x18000f944  retn
0x18000f945  mov     rcx, [rbp+57h]; this
0x18000f949  mov     r9d, eax; char *
0x18000f94c  lea     r8, aShellcommonShe_14; "shellcommon\\shell\\datastorecache\\tra"...
0x18000f953  mov     edx, 57h ; 'W'; void *
0x18000f958  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000f95e  mov     rdx, [r14+88h]
0x18000f965  lea     r8, [r14+70h]
0x18000f969  lea     rcx, [rbp+4Fh+var_80]
0x18000f96d  test    rdx, rdx
0x18000f970  jz      loc_18000FA75
0x18000f976  call    ??0MRTHelperForPackage@DataStoreCache@@QEAA@PEAUHSTRING__@@AEBV?$shared_ptr@VImpersonator@UserHelpers@@@std@@@Z; DataStoreCache::MRTHelperForPackage::MRTHelperForPackage(HSTRING__ *,std::shared_ptr<UserHelpers::Impersonator> const &)
0x18000f97b  nop
0x18000f97c  mov     r8, rbx
0x18000f97f  lea     rdx, [rbp+4Fh+string]
0x18000f983  lea     rcx, [rbp+4Fh+var_80]
0x18000f987  call    ?ResolveString@MRTHelper@DataStoreCache@@QEAA?AVHString@Wrappers@WRL@Microsoft@@PEAUHSTRING__@@@Z; DataStoreCache::MRTHelper::ResolveString(HSTRING__ *)
0x18000f98c  mov     rbx, rax
0x18000f98f  mov     rcx, [rdi]; string
0x18000f992  call    cs:__imp_WindowsDeleteString
0x18000f998  mov     qword ptr [rdi], 0
0x18000f99f  mov     rcx, [rbx]
0x18000f9a2  mov     [rdi], rcx
0x18000f9a5  mov     qword ptr [rbx], 0
0x18000f9ac  mov     rcx, [rbp+4Fh+string]; string
0x18000f9b0  call    cs:__imp_WindowsDeleteString
0x18000f9b6  nop
0x18000f9b7  lea     rcx, [rbp+4Fh+var_80]; this
0x18000f9bb  call    ??1MRTHelper@DataStoreCache@@UEAA@XZ; DataStoreCache::MRTHelper::~MRTHelper(void)
0x18000f9c0  cmp     [rbp+4Fh+arg_20], 0
0x18000f9c4  jz      loc_18000F92B
0x18000f9ca  lea     rbx, [r14+0C8h]
0x18000f9d1  mov     rcx, rbx; SRWLock
0x18000f9d4  call    cs:__imp_AcquireSRWLockExclusive
0x18000f9da  mov     [rbp+4Fh+var_88], rbx
0x18000f9de  test    esi, esi
0x18000f9e0  jz      short loc_18000FA1D
0x18000f9e2  sub     esi, 1
0x18000f9e5  jz      loc_18000FB6A
0x18000f9eb  sub     esi, 1
0x18000f9ee  jz      loc_18000FB32
0x18000f9f4  sub     esi, 1
0x18000f9f7  jz      loc_18000FAFA
0x18000f9fd  cmp     esi, 1
0x18000fa00  jz      loc_18000FAC2
0x18000fa06  test    rbx, rbx
0x18000fa09  jz      loc_18000F92B
0x18000fa0f  mov     rcx, rbx; SRWLock
0x18000fa12  call    cs:__imp_ReleaseSRWLockExclusive
0x18000fa18  jmp     loc_18000F92B
0x18000fa1d  mov     rsi, [rdi]
0x18000fa20  test    rsi, rsi
0x18000fa23  jz      short loc_18000FA30
0x18000fa25  xor     eax, eax
0x18000fa27  cmp     rsi, [r14+98h]
0x18000fa2e  jz      short loc_18000FA58
0x18000fa30  mov     rcx, [r14+98h]; string
0x18000fa37  call    cs:__imp_WindowsDeleteString
0x18000fa3d  mov     qword ptr [r14+98h], 0
0x18000fa48  lea     rdx, [r14+98h]; newString
0x18000fa4f  mov     rcx, rsi; string
0x18000fa52  call    cs:__imp_WindowsDuplicateString
0x18000fa58  mov     rcx, [rbp+57h]; this
0x18000fa5c  test    eax, eax
0x18000fa5e  jns     short loc_18000FA06
0x18000fa60  mov     r9d, eax; char *
0x18000fa63  lea     r8, aShellcommonShe_14; "shellcommon\\shell\\datastorecache\\tra"...
0x18000fa6a  mov     edx, 6Eh ; 'n'; void *
0x18000fa6f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000fa75  mov     rdx, [r14+90h]
0x18000fa7c  call    ??0MRTHelperForPriFile@DataStoreCache@@QEAA@PEAUHSTRING__@@AEBV?$shared_ptr@VImpersonator@UserHelpers@@@std@@@Z; DataStoreCache::MRTHelperForPriFile::MRTHelperForPriFile(HSTRING__ *,std::shared_ptr<UserHelpers::Impersonator> const &)
0x18000fa81  nop
0x18000fa82  mov     r8, rbx
0x18000fa85  lea     rdx, [rbp+4Fh+string]
0x18000fa89  lea     rcx, [rbp+4Fh+var_80]
0x18000fa8d  call    ?ResolveString@MRTHelper@DataStoreCache@@QEAA?AVHString@Wrappers@WRL@Microsoft@@PEAUHSTRING__@@@Z; DataStoreCache::MRTHelper::ResolveString(HSTRING__ *)
0x18000fa92  mov     rbx, rax
0x18000fa95  mov     rcx, [rdi]; string
0x18000fa98  call    cs:__imp_WindowsDeleteString
0x18000fa9e  mov     qword ptr [rdi], 0
0x18000faa5  mov     rcx, [rbx]
0x18000faa8  mov     [rdi], rcx
0x18000faab  mov     qword ptr [rbx], 0
0x18000fab2  mov     rcx, [rbp+4Fh+string]; string
0x18000fab6  call    cs:__imp_WindowsDeleteString
0x18000fabc  nop
0x18000fabd  jmp     loc_18000F9B7
0x18000fac2  mov     rax, [rdi]
0x18000fac5  mov     [rbp+4Fh+string], rax
0x18000fac9  lea     rcx, [r14+0B8h]; newString
0x18000fad0  lea     rdx, [rbp+4Fh+string]; HSTRING *
0x18000fad4  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18000fad9  mov     rcx, [rbp+57h]; this
0x18000fadd  test    eax, eax
0x18000fadf  jns     loc_18000FA06
0x18000fae5  mov     r9d, eax; char *
0x18000fae8  lea     r8, aShellcommonShe_14; "shellcommon\\shell\\datastorecache\\tra"...
0x18000faef  mov     edx, 7Ah ; 'z'; void *
0x18000faf4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000fafa  mov     rax, [rdi]
0x18000fafd  mov     [rbp+4Fh+string], rax
0x18000fb01  lea     rcx, [r14+0B0h]; newString
0x18000fb08  lea     rdx, [rbp+4Fh+string]; HSTRING *
0x18000fb0c  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18000fb11  mov     rcx, [rbp+57h]; this
0x18000fb15  test    eax, eax
0x18000fb17  jns     loc_18000FA06
0x18000fb1d  mov     r9d, eax; char *
0x18000fb20  lea     r8, aShellcommonShe_14; "shellcommon\\shell\\datastorecache\\tra"...
0x18000fb27  mov     edx, 77h ; 'w'; void *
0x18000fb2c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000fb32  mov     rax, [rdi]
0x18000fb35  mov     [rbp+4Fh+string], rax
0x18000fb39  lea     rcx, [r14+0A8h]; newString
0x18000fb40  lea     rdx, [rbp+4Fh+string]; HSTRING *
0x18000fb44  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18000fb49  mov     rcx, [rbp+57h]; this
0x18000fb4d  test    eax, eax
0x18000fb4f  jns     loc_18000FA06
0x18000fb55  mov     r9d, eax; char *
0x18000fb58  lea     r8, aShellcommonShe_14; "shellcommon\\shell\\datastorecache\\tra"...
0x18000fb5f  mov     edx, 74h ; 't'; void *
0x18000fb64  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000fb6a  mov     rax, [rdi]
0x18000fb6d  mov     [rbp+4Fh+string], rax
0x18000fb71  lea     rcx, [r14+0A0h]; newString
0x18000fb78  lea     rdx, [rbp+4Fh+string]; HSTRING *
0x18000fb7c  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18000fb81  mov     rcx, [rbp+57h]; this
0x18000fb85  test    eax, eax
0x18000fb87  jns     loc_18000FA06
0x18000fb8d  mov     r9d, eax; char *
0x18000fb90  lea     r8, aShellcommonShe_14; "shellcommon\\shell\\datastorecache\\tra"...
0x18000fb97  mov     edx, 71h ; 'q'; void *
0x18000fb9c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
