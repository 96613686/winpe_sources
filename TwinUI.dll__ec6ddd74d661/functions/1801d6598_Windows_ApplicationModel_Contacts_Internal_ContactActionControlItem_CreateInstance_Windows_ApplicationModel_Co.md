# Windows::ApplicationModel::Contacts::Internal::ContactActionControlItem_CreateInstance(Windows::ApplicationModel::Contacts::IContact2 *,HSTRING__ *,HSTRING__ *,Windows::ApplicationModel::Contacts::Internal::IContactActionControlItem * *)

- ea: `0x1801d6598`
- end: `0x1801d6948`
- name: `?ContactActionControlItem_CreateInstance@Internal@Contacts@ApplicationModel@Windows@@YAJPEAUIContact2@234@PEAUHSTRING__@@1PEAPEAUIContactActionControlItem@1234@@Z`
- size: `944`
- prototype: `int(Windows::ApplicationModel::Contacts::Internal *__hidden this, struct Windows::ApplicationModel::Contacts::IContact2 *, HSTRING, HSTRING, struct Windows::ApplicationModel::Contacts::Internal::IContactActionControlItem **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801cc070`

## callees

- `0x180009dd0`
- `0x18001c710`
- `0x180142e10`
- `0x1801d44c0`
- `0x1801d6598`
- `0x1801d6950`
- `0x1801e1b10`
- `0x1801e1bac`
- `0x1801e1f84`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801d662c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801d662c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d667f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d6696`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d6759`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d6768`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d6830`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d68f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d667f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d6696`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d6759`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d6768`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d6830`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d68f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801d65e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801d65e4`

## pseudocode

```c
__int64 __fastcall Windows::ApplicationModel::Contacts::Internal::ContactActionControlItem_CreateInstance(
        Windows::ApplicationModel::Contacts::Internal *this,
        struct Windows::ApplicationModel::Contacts::IContact2 *a2,
        HSTRING a3,
        void **a4)
{
  struct Windows::ApplicationModel::Contacts::IContact2 *v4; // rdi
  const WCHAR *StringRawBuffer; // rax
  char v7; // r12
  int Instance; // esi
  __int64 v9; // r14
  unsigned int v10; // r15d
  HSTRING *v11; // r9
  int v12; // eax
  HSTRING v13; // rbx
  HSTRING v14; // rdi
  __int64 v15; // rsi
  struct Windows::ApplicationModel::Contacts::IContactAddress **v16; // r8
  HSTRING *v17; // r8
  __int64 v18; // rdi
  HSTRING v19; // rsi
  __int64 v20; // rbx
  HSTRING v22; // [rsp+50h] [rbp-B0h] BYREF
  UINT32 length; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING string; // [rsp+60h] [rbp-A0h] BYREF
  void **v25; // [rsp+68h] [rbp-98h]
  Windows::ApplicationModel::Contacts::Internal *v26; // [rsp+70h] [rbp-90h]
  struct Windows::ApplicationModel::Contacts::IContact2 *v27; // [rsp+78h] [rbp-88h]
  __int64 v28; // [rsp+80h] [rbp-80h] BYREF
  __int64 v29[4]; // [rsp+88h] [rbp-78h] BYREF
  const WCHAR *v30; // [rsp+A8h] [rbp-58h]
  HSTRING_HEADER v31; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v32; // [rsp+C8h] [rbp-38h]
  HSTRING_HEADER v33; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v34; // [rsp+E8h] [rbp-18h]
  HSTRING_HEADER hstringHeader; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v36; // [rsp+108h] [rbp+8h]

  v4 = a2;
  v27 = a2;
  v26 = this;
  v25 = a4;
  length = 0;
  StringRawBuffer = WindowsGetStringRawBuffer((HSTRING)a2, &length);
  v30 = StringRawBuffer;
  v7 = 0;
  Instance = -2147024809;
  v9 = 0;
  while ( !v7 )
  {
    if ( CompareStringOrdinal(StringRawBuffer, length, (&off_1803F9760)[2 * v9], -1, 1) == 2 )
    {
      v7 = 1;
      v10 = *((_DWORD *)&off_1803F9760 + 4 * v9 + 2);
      if ( v10 < 2 )
        goto LABEL_8;
      if ( v10 == 2 )
      {
        v22 = 0;
        WindowsDeleteString(0);
        v22 = 0;
        Instance = Windows::ApplicationModel::Contacts::Internal::DeserializeEmailActivationContext(
                     a3,
                     (HSTRING)&v22,
                     v17);
        if ( Instance >= 0 )
        {
          v32 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v31, &pszDefault, 1u, 0);
          v18 = v32;
          v19 = v22;
          v34 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v33, &pszDefault, 1u, 0);
          v20 = v34;
          v36 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, &pszDefault, 1u, 0);
          Instance = Windows::ApplicationModel::Contacts::Internal::ContactActionControlItem_CreateInstance(
                       2,
                       v26,
                       v36,
                       v27,
                       v20,
                       v19,
                       v18,
                       0,
                       0,
                       v25);
        }
        WindowsDeleteString(v22);
        goto LABEL_19;
      }
      if ( v10 == 3 )
      {
        v22 = 0;
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v22);
        Instance = Windows::ApplicationModel::Contacts::Internal::DeserializeMapActivationContext(a3, &v22, v16);
        if ( Instance >= 0 )
        {
          v29[0] = (__int64)v22;
          v32 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v31, &pszDefault, 1u, 0);
          v29[2] = v32;
          v29[3] = (__int64)v26;
          string = 0;
          v28 = 0;
          v29[1] = (__int64)v4;
          Instance = Microsoft::WRL::Details::MakeAndInitialize<Windows::ApplicationModel::Contacts::Internal::MapActionControlItem,Windows::ApplicationModel::Contacts::Internal::IContactActionControlItem,Windows::ApplicationModel::Contacts::IContact2 * &,HSTRING__ * &,HSTRING__ * &,Windows::ApplicationModel::Contacts::IContactAddress * &,IShellItem * &,Windows::ApplicationModel::Contacts::Internal::IContactPreferenceManager * &>(
                       v25,
                       (__int64)v29,
                       (__int64)&v28,
                       (__int64)&string);
        }
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v22);
        goto LABEL_19;
      }
      if ( v10 - 4 <= 1 )
      {
LABEL_8:
        WindowsDeleteString(0);
        string = 0;
        WindowsDeleteString(0);
        v22 = 0;
        v12 = Windows::ApplicationModel::Contacts::Internal::DeserializeServiceActivationContext(
                a3,
                (HSTRING)&v22,
                &string,
                v11);
        v13 = v22;
        Instance = v12;
        v14 = string;
        if ( v12 >= 0 )
        {
          v36 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, &pszDefault, 1u, 0);
          v15 = v36;
          v34 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v33, &pszDefault, 1u, 0);
          Instance = Windows::ApplicationModel::Contacts::Internal::ContactActionControlItem_CreateInstance(
                       v10,
                       v26,
                       v34,
                       v27,
                       v15,
                       v13,
                       v14,
                       0,
                       0,
                       v25);
        }
        WindowsDeleteString(v14);
        WindowsDeleteString(v13);
      }
    }
    else
    {
      v7 = 0;
    }
LABEL_19:
    v4 = v27;
    StringRawBuffer = v30;
    if ( (unsigned __int64)++v9 >= 6 )
      return (unsigned int)Instance;
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1801d6598  push    rbp
0x1801d659a  push    rbx
0x1801d659b  push    rsi
0x1801d659c  push    rdi
0x1801d659d  push    r12
0x1801d659f  push    r13
0x1801d65a1  push    r14
0x1801d65a3  push    r15
0x1801d65a5  lea     rbp, [rsp-28h]
0x1801d65aa  sub     rsp, 128h
0x1801d65b1  mov     rax, cs:__security_cookie
0x1801d65b8  xor     rax, rsp
0x1801d65bb  mov     [rbp+60h+var_50], rax
0x1801d65bf  mov     rdi, rdx
0x1801d65c2  mov     [rsp+160h+var_E8], rdx
0x1801d65c7  mov     [rsp+160h+var_F0], rcx
0x1801d65cc  lea     rdx, [rsp+160h+length]; length
0x1801d65d1  xor     r15d, r15d
0x1801d65d4  mov     [rsp+160h+var_F8], r9
0x1801d65d9  mov     rcx, rdi; string
0x1801d65dc  mov     [rsp+160h+length], r15d
0x1801d65e1  mov     r13, r8
0x1801d65e4  call    cs:__imp_WindowsGetStringRawBuffer
0x1801d65eb  nop     dword ptr [rax+rax+00h]
0x1801d65f0  mov     [rbp+60h+var_B8], rax
0x1801d65f4  mov     r12b, r15b
0x1801d65f7  mov     esi, 80070057h
0x1801d65fc  lea     rcx, off_1803F9760; "Windows.Contact.Call"
0x1801d6603  mov     r14d, r15d
0x1801d6606  test    r12b, r12b
0x1801d6609  jnz     loc_1801D6925
0x1801d660f  mov     edx, [rsp+160h+length]; cchCount1
0x1801d6613  mov     rbx, r14
0x1801d6616  add     rbx, rbx
0x1801d6619  mov     [rsp+160h+bIgnoreCase], 1; bIgnoreCase
0x1801d6621  or      r9d, 0FFFFFFFFh; cchCount2
0x1801d6625  mov     r8, [rcx+rbx*8]; lpString2
0x1801d6629  mov     rcx, rax; lpString1
0x1801d662c  call    cs:__imp_CompareStringOrdinal
0x1801d6633  nop     dword ptr [rax+rax+00h]
0x1801d6638  cmp     eax, 2
0x1801d663b  jnz     loc_1801D6905
0x1801d6641  lea     r15, off_1803F9760; "Windows.Contact.Call"
0x1801d6648  mov     r12b, 1
0x1801d664b  mov     r15d, [r15+rbx*8+8]
0x1801d6650  mov     ecx, r15d
0x1801d6653  test    r15d, r15d
0x1801d6656  jz      short loc_1801D667D
0x1801d6658  sub     ecx, 1
0x1801d665b  jz      short loc_1801D667D
0x1801d665d  sub     ecx, 1
0x1801d6660  jz      loc_1801D6826
0x1801d6666  sub     ecx, 1
0x1801d6669  jz      loc_1801D677C
0x1801d666f  sub     ecx, 1
0x1801d6672  jz      short loc_1801D667D
0x1801d6674  cmp     ecx, 1
0x1801d6677  jnz     loc_1801D6774
0x1801d667d  xor     ecx, ecx; string
0x1801d667f  call    cs:__imp_WindowsDeleteString
0x1801d6686  nop     dword ptr [rax+rax+00h]
0x1801d668b  xor     ecx, ecx; string
0x1801d668d  mov     [rsp+160h+string], 0
0x1801d6696  call    cs:__imp_WindowsDeleteString
0x1801d669d  nop     dword ptr [rax+rax+00h]
0x1801d66a2  lea     r8, [rsp+160h+string]; HSTRING *
0x1801d66a7  mov     [rsp+160h+var_110], 0
0x1801d66b0  lea     rdx, [rsp+160h+var_110]; HSTRING
0x1801d66b5  mov     rcx, r13; this
0x1801d66b8  call    ?DeserializeServiceActivationContext@Internal@Contacts@ApplicationModel@Windows@@YAJPEAUHSTRING__@@PEAPEAU5@1@Z; Windows::ApplicationModel::Contacts::Internal::DeserializeServiceActivationContext(HSTRING__ *,HSTRING__ * *,HSTRING__ * *)
0x1801d66bd  mov     rbx, [rsp+160h+var_110]
0x1801d66c2  mov     esi, eax
0x1801d66c4  mov     rdi, [rsp+160h+string]
0x1801d66c9  test    eax, eax
0x1801d66cb  js      loc_1801D6756
0x1801d66d1  xor     r9d, r9d; unsigned int
0x1801d66d4  mov     [rbp+60h+var_58], 0
0x1801d66dc  lea     rdx, pszDefault; sourceString
0x1801d66e3  lea     rcx, [rbp+60h+hstringHeader]; hstringHeader
0x1801d66e7  lea     r8d, [r9+1]; unsigned int
0x1801d66eb  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801d66f0  mov     rsi, [rbp+60h+var_58]
0x1801d66f4  lea     rdx, pszDefault; sourceString
0x1801d66fb  xor     r9d, r9d; unsigned int
0x1801d66fe  mov     [rbp+60h+var_78], 0
0x1801d6706  lea     rcx, [rbp+60h+var_90]; hstringHeader
0x1801d670a  lea     r8d, [r9+1]; unsigned int
0x1801d670e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801d6713  mov     rax, [rsp+160h+var_F8]
0x1801d6718  mov     ecx, r15d
0x1801d671b  mov     r9, [rsp+160h+var_E8]
0x1801d6720  mov     r8, [rbp+60h+var_78]
0x1801d6724  mov     rdx, [rsp+160h+var_F0]
0x1801d6729  mov     [rsp+160h+var_118], rax
0x1801d672e  mov     [rsp+160h+var_120], 0
0x1801d6737  mov     [rsp+160h+var_128], 0
0x1801d6740  mov     [rsp+160h+var_130], rdi
0x1801d6745  mov     [rsp+160h+var_138], rbx
0x1801d674a  mov     qword ptr [rsp+160h+bIgnoreCase], rsi
0x1801d674f  call    ?ContactActionControlItem_CreateInstance@Internal@Contacts@ApplicationModel@Windows@@YAJW4ControlType@1234@PEAUIContact2@234@PEAUHSTRING__@@2222PEAUIShellItem@@PEAUIContactPreferenceManager@1234@PEAPEAUIContactActionControlItem@1234@@Z; Windows::ApplicationModel::Contacts::Internal::ContactActionControlItem_CreateInstance(Windows::ApplicationModel::Contacts::Internal::ControlType,Windows::ApplicationModel::Contacts::IContact2 *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,IShellItem *,Windows::ApplicationModel::Contacts::Internal::IContactPreferenceManager *,Windows::ApplicationModel::Contacts::Internal::IContactActionControlItem * *)
0x1801d6754  mov     esi, eax
0x1801d6756  mov     rcx, rdi; string
0x1801d6759  call    cs:__imp_WindowsDeleteString
0x1801d6760  nop     dword ptr [rax+rax+00h]
0x1801d6765  mov     rcx, rbx; string
0x1801d6768  call    cs:__imp_WindowsDeleteString
0x1801d676f  nop     dword ptr [rax+rax+00h]
0x1801d6774  xor     r15d, r15d
0x1801d6777  jmp     loc_1801D6908
0x1801d677c  xor     r15d, r15d
0x1801d677f  lea     rcx, [rsp+160h+var_110]
0x1801d6784  mov     [rsp+160h+var_110], r15
0x1801d6789  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801d678e  lea     rdx, [rsp+160h+var_110]; HSTRING
0x1801d6793  mov     rcx, r13; this
0x1801d6796  call    ?DeserializeMapActivationContext@Internal@Contacts@ApplicationModel@Windows@@YAJPEAUHSTRING__@@PEAPEAUIContactAddress@234@@Z; Windows::ApplicationModel::Contacts::Internal::DeserializeMapActivationContext(HSTRING__ *,Windows::ApplicationModel::Contacts::IContactAddress * *)
0x1801d679b  mov     esi, eax
0x1801d679d  test    eax, eax
0x1801d679f  js      short loc_1801D6817
0x1801d67a1  mov     rax, [rsp+160h+var_110]
0x1801d67a6  lea     r8d, [r15+1]; unsigned int
0x1801d67aa  xor     r9d, r9d; unsigned int
0x1801d67ad  mov     [rbp+60h+var_D8], rax
0x1801d67b1  lea     rdx, pszDefault; sourceString
0x1801d67b8  mov     [rbp+60h+var_98], r15
0x1801d67bc  lea     rcx, [rbp+60h+var_B0]; hstringHeader
0x1801d67c0  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801d67c5  mov     rax, [rbp+60h+var_98]
0x1801d67c9  lea     r9, [rbp+60h+var_D0]
0x1801d67cd  mov     rcx, [rsp+160h+var_F8]; void **
0x1801d67d2  lea     r8, [rbp+60h+var_C8]
0x1801d67d6  mov     [rbp+60h+var_C8], rax
0x1801d67da  lea     rdx, [rbp+60h+var_C0]
0x1801d67de  mov     rax, [rsp+160h+var_F0]
0x1801d67e3  mov     [rbp+60h+var_C0], rax
0x1801d67e7  lea     rax, [rsp+160h+string]
0x1801d67ec  mov     [rsp+160h+var_130], rax; __int64
0x1801d67f1  lea     rax, [rbp+60h+var_E0]
0x1801d67f5  mov     [rsp+160h+var_138], rax; __int64
0x1801d67fa  lea     rax, [rbp+60h+var_D8]
0x1801d67fe  mov     qword ptr [rsp+160h+bIgnoreCase], rax; __int64
0x1801d6803  mov     [rsp+160h+string], r15
0x1801d6808  mov     [rbp+60h+var_E0], r15
0x1801d680c  mov     [rbp+60h+var_D0], rdi
0x1801d6810  call    ??$MakeAndInitialize@VMapActionControlItem@Internal@Contacts@ApplicationModel@Windows@@UIContactActionControlItem@2345@AEAPEAUIContact2@345@AEAPEAUHSTRING__@@AEAPEAU8@AEAPEAUIContactAddress@345@AEAPEAUIShellItem@@AEAPEAUIContactPreferenceManager@2345@@Details@WRL@Microsoft@@YAJPEAPEAUIContactActionControlItem@Internal@Contacts@ApplicationModel@Windows@@AEAPEAUIContact2@567@AEAPEAUHSTRING__@@2AEAPEAUIContactAddress@567@AEAPEAUIShellItem@@AEAPEAUIContactPreferenceManager@4567@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::ApplicationModel::Contacts::Internal::MapActionControlItem,Windows::ApplicationModel::Contacts::Internal::IContactActionControlItem,Windows::ApplicationModel::Contacts::IContact2 * &,HSTRING__ * &,HSTRING__ * &,Windows::ApplicationModel::Contacts::IContactAddress * &,IShellItem * &,Windows::ApplicationModel::Contacts::Internal::IContactPreferenceManager * &>(Windows::ApplicationModel::Contacts::Internal::IContactActionControlItem * *,Windows::ApplicationModel::Contacts::IContact2 * &,HSTRING__ * &,HSTRING__ * &,Windows::ApplicationModel::Contacts::IContactAddress * &,IShellItem * &,Windows::ApplicationModel::Contacts::Internal::IContactPreferenceManager * &)
0x1801d6815  mov     esi, eax
0x1801d6817  lea     rcx, [rsp+160h+var_110]
0x1801d681c  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801d6821  jmp     loc_1801D6908
0x1801d6826  xor     r15d, r15d
0x1801d6829  xor     ecx, ecx; string
0x1801d682b  mov     [rsp+160h+var_110], r15
0x1801d6830  call    cs:__imp_WindowsDeleteString
0x1801d6837  nop     dword ptr [rax+rax+00h]
0x1801d683c  lea     rdx, [rsp+160h+var_110]; HSTRING
0x1801d6841  mov     [rsp+160h+var_110], r15
0x1801d6846  mov     rcx, r13; this
0x1801d6849  call    ?DeserializeEmailActivationContext@Internal@Contacts@ApplicationModel@Windows@@YAJPEAUHSTRING__@@PEAPEAU5@@Z; Windows::ApplicationModel::Contacts::Internal::DeserializeEmailActivationContext(HSTRING__ *,HSTRING__ * *)
0x1801d684e  mov     esi, eax
0x1801d6850  test    eax, eax
0x1801d6852  js      loc_1801D68F2
0x1801d6858  xor     r9d, r9d; unsigned int
0x1801d685b  mov     [rbp+60h+var_98], r15
0x1801d685f  lea     r8d, [r15+1]; unsigned int
0x1801d6863  lea     rdx, pszDefault; sourceString
0x1801d686a  lea     rcx, [rbp+60h+var_B0]; hstringHeader
0x1801d686e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801d6873  mov     rdi, [rbp+60h+var_98]
0x1801d6877  lea     r8d, [r15+1]; unsigned int
0x1801d687b  mov     rsi, [rsp+160h+var_110]
0x1801d6880  lea     rdx, pszDefault; sourceString
0x1801d6887  xor     r9d, r9d; unsigned int
0x1801d688a  mov     [rbp+60h+var_78], r15
0x1801d688e  lea     rcx, [rbp+60h+var_90]; hstringHeader
0x1801d6892  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801d6897  mov     rbx, [rbp+60h+var_78]
0x1801d689b  lea     r8d, [r15+1]; unsigned int
0x1801d689f  xor     r9d, r9d; unsigned int
0x1801d68a2  mov     [rbp+60h+var_58], r15
0x1801d68a6  lea     rdx, pszDefault; sourceString
0x1801d68ad  lea     rcx, [rbp+60h+hstringHeader]; hstringHeader
0x1801d68b1  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801d68b6  mov     rax, [rsp+160h+var_F8]
0x1801d68bb  lea     ecx, [r15+2]
0x1801d68bf  mov     r9, [rsp+160h+var_E8]
0x1801d68c4  mov     r8, [rbp+60h+var_58]
0x1801d68c8  mov     rdx, [rsp+160h+var_F0]
0x1801d68cd  mov     [rsp+160h+var_118], rax
0x1801d68d2  mov     [rsp+160h+var_120], r15
0x1801d68d7  mov     [rsp+160h+var_128], r15
0x1801d68dc  mov     [rsp+160h+var_130], rdi
0x1801d68e1  mov     [rsp+160h+var_138], rsi
0x1801d68e6  mov     qword ptr [rsp+160h+bIgnoreCase], rbx
0x1801d68eb  call    ?ContactActionControlItem_CreateInstance@Internal@Contacts@ApplicationModel@Windows@@YAJW4ControlType@1234@PEAUIContact2@234@PEAUHSTRING__@@2222PEAUIShellItem@@PEAUIContactPreferenceManager@1234@PEAPEAUIContactActionControlItem@1234@@Z; Windows::ApplicationModel::Contacts::Internal::ContactActionControlItem_CreateInstance(Windows::ApplicationModel::Contacts::Internal::ControlType,Windows::ApplicationModel::Contacts::IContact2 *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,IShellItem *,Windows::ApplicationModel::Contacts::Internal::IContactPreferenceManager *,Windows::ApplicationModel::Contacts::Internal::IContactActionControlItem * *)
0x1801d68f0  mov     esi, eax
0x1801d68f2  mov     rcx, [rsp+160h+var_110]; string
0x1801d68f7  call    cs:__imp_WindowsDeleteString
0x1801d68fe  nop     dword ptr [rax+rax+00h]
0x1801d6903  jmp     short loc_1801D6908
0x1801d6905  mov     r12b, r15b
0x1801d6908  mov     rdi, [rsp+160h+var_E8]
0x1801d690d  lea     rcx, off_1803F9760; "Windows.Contact.Call"
0x1801d6914  mov     rax, [rbp+60h+var_B8]
0x1801d6918  inc     r14
0x1801d691b  cmp     r14, 6
0x1801d691f  jb      loc_1801D6606
0x1801d6925  mov     eax, esi
0x1801d6927  mov     rcx, [rbp+60h+var_50]
0x1801d692b  xor     rcx, rsp; StackCookie
0x1801d692e  call    __security_check_cookie
0x1801d6933  add     rsp, 128h
0x1801d693a  pop     r15
0x1801d693c  pop     r14
0x1801d693e  pop     r13
0x1801d6940  pop     r12
0x1801d6942  pop     rdi
0x1801d6943  pop     rsi
0x1801d6944  pop     rbx
0x1801d6945  pop     rbp
0x1801d6946  retn
```
