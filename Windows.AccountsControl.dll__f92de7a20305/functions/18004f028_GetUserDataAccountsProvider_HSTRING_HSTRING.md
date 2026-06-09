# GetUserDataAccountsProvider(HSTRING__ *,HSTRING__ * *)

- ea: `0x18004f028`
- end: `0x18004f11a`
- name: `?GetUserDataAccountsProvider@@YAJPEAUHSTRING__@@PEAPEAU1@@Z`
- size: `242`
- prototype: `__int64 __fastcall(HSTRING, HSTRING *)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800446f0`
- `0x18004bc70`

## callees

- `0x180006eac`
- `0x180011ffc`
- `0x18004e6f8`
- `0x18004e924`
- `0x18004ece0`
- `0x18004f028`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f051`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f102`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f051`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f102`

## string_xrefs

- `0x18004f078`: `onecoreuap\shell\accountscontrol\api\mailcontactscalendarsyncuiapilib\appextensionhelpers.cpp`
- `0x18004f0b7`: `onecoreuap\shell\accountscontrol\api\mailcontactscalendarsyncuiapilib\appextensionhelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetUserDataAccountsProvider(HSTRING a1, HSTRING *a2)
{
  int PackageFamilyNameForUda; // eax
  unsigned int v5; // ebx
  __int64 v6; // rcx
  int AppsByExtension; // eax
  __int64 v8; // rdx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+8h]
  __int64 v12; // [rsp+38h] [rbp+18h] BYREF
  HSTRING string; // [rsp+40h] [rbp+20h] BYREF

  *a2 = 0;
  string = 0;
  WindowsDeleteString(0);
  string = 0;
  PackageFamilyNameForUda = GetPackageFamilyNameForUda(a1, &string);
  v5 = PackageFamilyNameForUda;
  if ( PackageFamilyNameForUda >= 0 )
  {
    if ( string )
    {
      v12 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v12);
      AppsByExtension = FindAppsByExtension(v6, &v12);
      v5 = AppsByExtension;
      if ( AppsByExtension < 0 )
      {
        v8 = 99;
LABEL_6:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v8,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\appextensionhelpers.cpp",
          (const char *)(unsigned int)AppsByExtension,
          savedregs);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v12);
        goto LABEL_11;
      }
      AppsByExtension = GetMatchingProviderForUda(string, v12, a2);
      v5 = AppsByExtension;
      if ( AppsByExtension < 0 )
      {
        v8 = 101;
        goto LABEL_6;
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v12);
    }
    v5 = 0;
    goto LABEL_11;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5E,
    (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\appextensionhelpers.cpp",
    (const char *)(unsigned int)PackageFamilyNameForUda,
    savedregs);
LABEL_11:
  WindowsDeleteString(string);
  return v5;
}

```

## disassembly

```asm
0x18004f028  mov     [rsp-8+arg_0], rbx
0x18004f02d  mov     [rsp-8+arg_18], rdi
0x18004f032  push    rbp; int
0x18004f033  mov     rbp, rsp
0x18004f036  sub     rsp, 20h
0x18004f03a  mov     rdi, rdx
0x18004f03d  mov     rbx, rcx
0x18004f040  mov     qword ptr [rdx], 0
0x18004f047  mov     [rbp+string], 0
0x18004f04f  xor     ecx, ecx; string
0x18004f051  call    cs:__imp_WindowsDeleteString
0x18004f057  mov     [rbp+string], 0
0x18004f05f  lea     rdx, [rbp+string]; HSTRING *
0x18004f063  mov     rcx, rbx; HSTRING
0x18004f066  call    ?GetPackageFamilyNameForUda@@YAJPEAUHSTRING__@@PEAPEAU1@@Z; GetPackageFamilyNameForUda(HSTRING__ *,HSTRING__ * *)
0x18004f06b  mov     ebx, eax
0x18004f06d  test    eax, eax
0x18004f06f  jns     short loc_18004F08B
0x18004f071  mov     rcx, [rbp+8]; this
0x18004f075  mov     r9d, eax; char *
0x18004f078  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\accountscontrol\\api"...
0x18004f07f  mov     edx, 5Eh ; '^'; void *
0x18004f084  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f089  jmp     short loc_18004F0FE
0x18004f08b  cmp     [rbp+string], 0
0x18004f090  jz      short loc_18004F0FC
0x18004f092  mov     [rbp+arg_8], 0
0x18004f09a  lea     rcx, [rbp+arg_8]
0x18004f09e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004f0a3  lea     rdx, [rbp+arg_8]
0x18004f0a7  call    ?FindAppsByExtension@@YAJPEBGPEAPEAU?$IVectorView@PEAVApplicationExtension@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@@Z; FindAppsByExtension(ushort const *,Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::ApplicationExtension *> * *)
0x18004f0ac  mov     ebx, eax
0x18004f0ae  test    eax, eax
0x18004f0b0  jns     short loc_18004F0D6
0x18004f0b2  mov     edx, 63h ; 'c'; void *
0x18004f0b7  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\accountscontrol\\api"...
0x18004f0be  mov     r9d, eax; char *
0x18004f0c1  mov     rcx, [rbp+8]; this
0x18004f0c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f0ca  nop
0x18004f0cb  lea     rcx, [rbp+arg_8]
0x18004f0cf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004f0d4  jmp     short loc_18004F0FE
0x18004f0d6  mov     r8, rdi
0x18004f0d9  mov     rdx, [rbp+arg_8]
0x18004f0dd  mov     rcx, [rbp+string]; string
0x18004f0e1  call    ?GetMatchingProviderForUda@@YAJPEAUHSTRING__@@PEAU?$IVectorView@PEAVApplicationExtension@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@PEAPEAU1@@Z; GetMatchingProviderForUda(HSTRING__ *,Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::ApplicationExtension *> *,HSTRING__ * *)
0x18004f0e6  mov     ebx, eax
0x18004f0e8  test    eax, eax
0x18004f0ea  jns     short loc_18004F0F3
0x18004f0ec  mov     edx, 65h ; 'e'
0x18004f0f1  jmp     short loc_18004F0B7
0x18004f0f3  lea     rcx, [rbp+arg_8]
0x18004f0f7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004f0fc  xor     ebx, ebx
0x18004f0fe  mov     rcx, [rbp+string]; string
0x18004f102  call    cs:__imp_WindowsDeleteString
0x18004f108  mov     eax, ebx
0x18004f10a  mov     rbx, [rsp+20h+arg_0]
0x18004f10f  mov     rdi, [rsp+20h+arg_18]
0x18004f114  add     rsp, 20h
0x18004f118  pop     rbp
0x18004f119  retn
```
