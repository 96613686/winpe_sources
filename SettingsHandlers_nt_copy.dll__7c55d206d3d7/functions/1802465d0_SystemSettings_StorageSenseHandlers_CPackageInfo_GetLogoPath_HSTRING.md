# SystemSettings::StorageSenseHandlers::CPackageInfo::GetLogoPath(HSTRING__ * *)

- ea: `0x1802465d0`
- end: `0x180246861`
- name: `?GetLogoPath@CPackageInfo@StorageSenseHandlers@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `657`
- prototype: `int(SystemSettings::StorageSenseHandlers::CPackageInfo *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000c840`
- `0x18000d44c`
- `0x180011bb0`
- `0x180245c5c`
- `0x1802465d0`
- `0x180289010`

## import_xrefs

- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x18024680d`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x18024680d`
- `api-ms-win-appmodel-runtime-l1-1-0!OpenPackageInfoByFullName` at `0x1802466ec`
- `api-ms-win-appmodel-runtime-l1-1-0!OpenPackageInfoByFullName` at `0x1802466ec`
- `api-ms-win-appmodel-runtime-internal-l1-1-0!GetPackageContext` at `0x180246728`
- `api-ms-win-appmodel-runtime-internal-l1-1-0!GetPackageContext` at `0x180246728`
- `api-ms-win-appmodel-runtime-internal-l1-1-0!GetPackagePropertyString` at `0x180246788`
- `api-ms-win-appmodel-runtime-internal-l1-1-0!GetPackagePropertyString` at `0x1802467c1`
- `api-ms-win-appmodel-runtime-internal-l1-1-0!GetPackagePropertyString` at `0x180246788`
- `api-ms-win-appmodel-runtime-internal-l1-1-0!GetPackagePropertyString` at `0x1802467c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802466a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18024681f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802466a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18024681f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802466d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802467e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180246830`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802466d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802467e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180246830`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::StorageSenseHandlers::CPackageInfo::GetLogoPath(
        SystemSettings::StorageSenseHandlers::CPackageInfo *this,
        HSTRING *a2)
{
  signed int FullyQualifiedFilePath; // ebx
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, _QWORD, HSTRING *); // rbx
  __int64 (__fastcall *v7)(SystemSettings::StorageSenseHandlers::CPackageInfo *, HSTRING *); // rbx
  const WCHAR *StringRawBuffer; // rax
  LONG v9; // eax
  int PackageContext; // eax
  int PackagePropertyString; // eax
  int v12; // eax
  SystemSettings::StorageSenseHandlers *v13; // rax
  HSTRING string; // [rsp+20h] [rbp-E0h] BYREF
  int v16; // [rsp+28h] [rbp-D8h] BYREF
  int v17; // [rsp+2Ch] [rbp-D4h] BYREF
  int v18; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v19; // [rsp+38h] [rbp-C8h] BYREF
  PACKAGE_INFO_REFERENCE packageInfoReference; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v21[264]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v22[264]; // [rsp+260h] [rbp+160h] BYREF

  *a2 = 0;
  v16 = 0;
  FullyQualifiedFilePath = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 4) + 56LL))(
                             *((_QWORD *)this + 4),
                             &v16);
  if ( FullyQualifiedFilePath >= 0 )
  {
    string = 0;
    if ( v16 == 1 )
    {
      v5 = *((_QWORD *)this + 4);
      v6 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v5 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
      FullyQualifiedFilePath = v6(v5, 0, &string);
      if ( FullyQualifiedFilePath >= 0 )
        FullyQualifiedFilePath = (*(__int64 (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)string + 56LL))(string, a2);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
    }
    else
    {
      packageInfoReference = 0;
      v7 = *(__int64 (__fastcall **)(SystemSettings::StorageSenseHandlers::CPackageInfo *, HSTRING *))(*(_QWORD *)this + 80LL);
      WindowsDeleteString(0);
      string = 0;
      FullyQualifiedFilePath = v7(this, &string);
      if ( FullyQualifiedFilePath >= 0 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        v9 = OpenPackageInfoByFullName(StringRawBuffer, 0, &packageInfoReference);
        FullyQualifiedFilePath = v9;
        if ( v9 > 0 )
          FullyQualifiedFilePath = (unsigned __int16)v9 | 0x80070000;
        if ( FullyQualifiedFilePath >= 0 )
        {
          v19 = 0;
          PackageContext = GetPackageContext(packageInfoReference, 0, 0, &v19);
          FullyQualifiedFilePath = PackageContext;
          if ( PackageContext > 0 )
            FullyQualifiedFilePath = (unsigned __int16)PackageContext | 0x80070000;
          if ( FullyQualifiedFilePath >= 0 )
          {
            memset_0(v21, 0, 0x208u);
            memset_0(v22, 0, 0x208u);
            v17 = 260;
            PackagePropertyString = GetPackagePropertyString(v19, 10, &v17, v21);
            FullyQualifiedFilePath = PackagePropertyString;
            if ( PackagePropertyString > 0 )
              FullyQualifiedFilePath = (unsigned __int16)PackagePropertyString | 0x80070000;
            if ( FullyQualifiedFilePath >= 0 )
            {
              v18 = 260;
              v12 = GetPackagePropertyString(v19, 14, &v18, v22);
              FullyQualifiedFilePath = v12;
              if ( v12 > 0 )
                FullyQualifiedFilePath = (unsigned __int16)v12 | 0x80070000;
              if ( FullyQualifiedFilePath >= 0 )
              {
                v13 = (SystemSettings::StorageSenseHandlers *)WindowsGetStringRawBuffer(string, 0);
                FullyQualifiedFilePath = SystemSettings::StorageSenseHandlers::GetFullyQualifiedFilePath(
                                           v13,
                                           v22,
                                           v21,
                                           a2,
                                           (HSTRING *)string);
              }
            }
          }
          ClosePackageInfo(packageInfoReference);
        }
      }
      WindowsDeleteString(string);
    }
  }
  WindowsGetStringRawBuffer(*a2, 0);
  return (unsigned int)FullyQualifiedFilePath;
}

```

## disassembly

```asm
0x1802465d0  mov     [rsp-8+arg_10], rbx
0x1802465d5  push    rbp
0x1802465d6  push    rsi
0x1802465d7  push    rdi
0x1802465d8  lea     rbp, [rsp-380h]
0x1802465e0  sub     rsp, 480h
0x1802465e7  mov     rax, cs:__security_cookie
0x1802465ee  xor     rax, rsp
0x1802465f1  mov     [rbp+390h+var_20], rax
0x1802465f8  mov     rsi, rdx
0x1802465fb  mov     rdi, rcx
0x1802465fe  mov     qword ptr [rdx], 0
0x180246605  mov     [rsp+490h+var_468], 0
0x18024660d  mov     rcx, [rcx+20h]
0x180246611  mov     rax, [rcx]
0x180246614  lea     rdx, [rsp+490h+var_468]
0x180246619  mov     rax, [rax+38h]
0x18024661d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180246622  mov     ebx, eax
0x180246624  test    eax, eax
0x180246626  js      loc_18024682B
0x18024662c  mov     [rsp+490h+string], 0
0x180246635  cmp     [rsp+490h+var_468], 1
0x18024663a  jnz     short loc_18024668E
0x18024663c  mov     rdi, [rdi+20h]
0x180246640  mov     rax, [rdi]
0x180246643  mov     rbx, [rax+30h]
0x180246647  lea     rcx, [rsp+490h+string]
0x18024664c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180246651  lea     r8, [rsp+490h+string]
0x180246656  xor     edx, edx
0x180246658  mov     rcx, rdi
0x18024665b  mov     rax, rbx
0x18024665e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180246663  mov     ebx, eax
0x180246665  test    eax, eax
0x180246667  js      short loc_18024667F
0x180246669  mov     rcx, [rsp+490h+string]
0x18024666e  mov     rax, [rcx]
0x180246671  mov     rdx, rsi
0x180246674  mov     rax, [rax+38h]
0x180246678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024667d  mov     ebx, eax
0x18024667f  lea     rcx, [rsp+490h+string]
0x180246684  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180246689  jmp     loc_18024682B
0x18024668e  mov     [rsp+490h+packageInfoReference], 0
0x180246697  mov     rax, [rdi]
0x18024669a  mov     rbx, [rax+50h]
0x18024669e  xor     ecx, ecx; string
0x1802466a0  call    cs:__imp_WindowsDeleteString
0x1802466a7  nop     dword ptr [rax+rax+00h]
0x1802466ac  mov     [rsp+490h+string], 0; HSTRING *
0x1802466b5  lea     rdx, [rsp+490h+string]
0x1802466ba  mov     rcx, rdi
0x1802466bd  mov     rax, rbx
0x1802466c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802466c5  mov     ebx, eax
0x1802466c7  test    eax, eax
0x1802466c9  js      loc_18024681A
0x1802466cf  xor     edx, edx; length
0x1802466d1  mov     rcx, [rsp+490h+string]; string
0x1802466d6  call    cs:__imp_WindowsGetStringRawBuffer
0x1802466dd  nop     dword ptr [rax+rax+00h]
0x1802466e2  lea     r8, [rsp+490h+packageInfoReference]; packageInfoReference
0x1802466e7  xor     edx, edx; reserved
0x1802466e9  mov     rcx, rax; packageFullName
0x1802466ec  call    cs:__imp_OpenPackageInfoByFullName
0x1802466f3  nop     dword ptr [rax+rax+00h]
0x1802466f8  mov     ebx, eax
0x1802466fa  mov     edi, 80070000h
0x1802466ff  test    eax, eax
0x180246701  jle     short loc_180246708
0x180246703  movzx   ebx, ax
0x180246706  or      ebx, edi
0x180246708  test    ebx, ebx
0x18024670a  js      loc_18024681A
0x180246710  mov     [rsp+490h+var_458], 0
0x180246719  lea     r9, [rsp+490h+var_458]
0x18024671e  xor     r8d, r8d
0x180246721  xor     edx, edx
0x180246723  mov     rcx, [rsp+490h+packageInfoReference]
0x180246728  call    cs:__imp_GetPackageContext
0x18024672f  nop     dword ptr [rax+rax+00h]
0x180246734  mov     ebx, eax
0x180246736  test    eax, eax
0x180246738  jle     short loc_18024673F
0x18024673a  movzx   ebx, ax
0x18024673d  or      ebx, edi
0x18024673f  test    ebx, ebx
0x180246741  js      loc_180246808
0x180246747  mov     ebx, 208h
0x18024674c  mov     r8d, ebx; Size
0x18024674f  xor     edx, edx; Val
0x180246751  lea     rcx, [rsp+490h+var_440]; void *
0x180246756  call    memset_0
0x18024675b  mov     r8d, ebx; Size
0x18024675e  xor     edx, edx; Val
0x180246760  lea     rcx, [rbp+390h+var_230]; void *
0x180246767  call    memset_0
0x18024676c  mov     [rsp+490h+var_464], 104h
0x180246774  lea     r9, [rsp+490h+var_440]
0x180246779  lea     r8, [rsp+490h+var_464]
0x18024677e  mov     edx, 0Ah
0x180246783  mov     rcx, [rsp+490h+var_458]
0x180246788  call    cs:__imp_GetPackagePropertyString
0x18024678f  nop     dword ptr [rax+rax+00h]
0x180246794  mov     ebx, eax
0x180246796  test    eax, eax
0x180246798  jle     short loc_18024679F
0x18024679a  movzx   ebx, ax
0x18024679d  or      ebx, edi
0x18024679f  test    ebx, ebx
0x1802467a1  js      short loc_180246808
0x1802467a3  mov     [rsp+490h+var_460], 104h
0x1802467ab  lea     r9, [rbp+390h+var_230]
0x1802467b2  lea     r8, [rsp+490h+var_460]
0x1802467b7  mov     edx, 0Eh
0x1802467bc  mov     rcx, [rsp+490h+var_458]
0x1802467c1  call    cs:__imp_GetPackagePropertyString
0x1802467c8  nop     dword ptr [rax+rax+00h]
0x1802467cd  mov     ebx, eax
0x1802467cf  test    eax, eax
0x1802467d1  jle     short loc_1802467D8
0x1802467d3  movzx   ebx, ax
0x1802467d6  or      ebx, edi
0x1802467d8  test    ebx, ebx
0x1802467da  js      short loc_180246808
0x1802467dc  xor     edx, edx; length
0x1802467de  mov     rcx, [rsp+490h+string]; string
0x1802467e3  call    cs:__imp_WindowsGetStringRawBuffer
0x1802467ea  nop     dword ptr [rax+rax+00h]
0x1802467ef  mov     r9, rsi; string
0x1802467f2  lea     r8, [rsp+490h+var_440]; unsigned __int16 *
0x1802467f7  lea     rdx, [rbp+390h+var_230]; unsigned __int16 *
0x1802467fe  mov     rcx, rax; this
0x180246801  call    ?GetFullyQualifiedFilePath@StorageSenseHandlers@SystemSettings@@YAJPEBG00PEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::GetFullyQualifiedFilePath(ushort const *,ushort const *,ushort const *,HSTRING__ * *)
0x180246806  mov     ebx, eax
0x180246808  mov     rcx, [rsp+490h+packageInfoReference]; packageInfoReference
0x18024680d  call    cs:__imp_ClosePackageInfo
0x180246814  nop     dword ptr [rax+rax+00h]
0x180246819  nop
0x18024681a  mov     rcx, [rsp+490h+string]; string
0x18024681f  call    cs:__imp_WindowsDeleteString
0x180246826  nop     dword ptr [rax+rax+00h]
0x18024682b  xor     edx, edx; length
0x18024682d  mov     rcx, [rsi]; string
0x180246830  call    cs:__imp_WindowsGetStringRawBuffer
0x180246837  nop     dword ptr [rax+rax+00h]
0x18024683c  mov     eax, ebx
0x18024683e  mov     rcx, [rbp+390h+var_20]
0x180246845  xor     rcx, rsp; StackCookie
0x180246848  call    __security_check_cookie
0x18024684d  mov     rbx, [rsp+490h+arg_10]
0x180246855  add     rsp, 480h
0x18024685c  pop     rdi
0x18024685d  pop     rsi
0x18024685e  pop     rbp
0x18024685f  retn
```
