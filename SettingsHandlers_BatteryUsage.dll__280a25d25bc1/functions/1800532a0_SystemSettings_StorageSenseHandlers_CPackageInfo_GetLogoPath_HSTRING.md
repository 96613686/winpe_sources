# SystemSettings::StorageSenseHandlers::CPackageInfo::GetLogoPath(HSTRING__ * *)

- ea: `0x1800532a0`
- end: `0x1800534f4`
- name: `?GetLogoPath@CPackageInfo@StorageSenseHandlers@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `596`
- prototype: `int(SystemSettings::StorageSenseHandlers::CPackageInfo *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800028d0`
- `0x1800033a0`
- `0x180004cfc`
- `0x180052848`
- `0x1800532a0`
- `0x18005a010`

## import_xrefs

- `api-ms-win-appmodel-runtime-l1-1-0!OpenPackageInfoByFullName` at `0x1800533b0`
- `api-ms-win-appmodel-runtime-l1-1-0!OpenPackageInfoByFullName` at `0x1800533b0`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x1800534b3`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x1800534b3`
- `api-ms-win-appmodel-runtime-internal-l1-1-0!GetPackagePropertyString` at `0x180053440`
- `api-ms-win-appmodel-runtime-internal-l1-1-0!GetPackagePropertyString` at `0x180053473`
- `api-ms-win-appmodel-runtime-internal-l1-1-0!GetPackagePropertyString` at `0x180053440`
- `api-ms-win-appmodel-runtime-internal-l1-1-0!GetPackagePropertyString` at `0x180053473`
- `api-ms-win-appmodel-runtime-internal-l1-1-0!GetPackageContext` at `0x1800533e6`
- `api-ms-win-appmodel-runtime-internal-l1-1-0!GetPackageContext` at `0x1800533e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053370`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800534bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053370`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800534bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800533a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005348f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800534ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800533a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005348f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800534ca`

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
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&string);
      FullyQualifiedFilePath = v6(v5, 0, &string);
      if ( FullyQualifiedFilePath >= 0 )
        FullyQualifiedFilePath = (*(__int64 (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)string + 56LL))(string, a2);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&string);
    }
    else
    {
      packageInfoReference = 0;
      v7 = *(__int64 (__fastcall **)(SystemSettings::StorageSenseHandlers::CPackageInfo *, HSTRING *))(*(_QWORD *)this + 72LL);
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
0x1800532a0  mov     [rsp-8+arg_10], rbx
0x1800532a5  push    rbp
0x1800532a6  push    rsi
0x1800532a7  push    rdi
0x1800532a8  lea     rbp, [rsp-380h]
0x1800532b0  sub     rsp, 480h
0x1800532b7  mov     rax, cs:__security_cookie
0x1800532be  xor     rax, rsp
0x1800532c1  mov     [rbp+390h+var_20], rax
0x1800532c8  mov     rsi, rdx
0x1800532cb  mov     rdi, rcx
0x1800532ce  mov     qword ptr [rdx], 0
0x1800532d5  mov     [rsp+490h+var_468], 0
0x1800532dd  mov     rcx, [rcx+20h]
0x1800532e1  mov     rax, [rcx]
0x1800532e4  lea     rdx, [rsp+490h+var_468]
0x1800532e9  mov     rax, [rax+38h]
0x1800532ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800532f2  mov     ebx, eax
0x1800532f4  test    eax, eax
0x1800532f6  js      loc_1800534C5
0x1800532fc  mov     [rsp+490h+string], 0
0x180053305  cmp     [rsp+490h+var_468], 1
0x18005330a  jnz     short loc_18005335E
0x18005330c  mov     rdi, [rdi+20h]
0x180053310  mov     rax, [rdi]
0x180053313  mov     rbx, [rax+30h]
0x180053317  lea     rcx, [rsp+490h+string]
0x18005331c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180053321  lea     r8, [rsp+490h+string]
0x180053326  xor     edx, edx
0x180053328  mov     rcx, rdi
0x18005332b  mov     rax, rbx
0x18005332e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053333  mov     ebx, eax
0x180053335  test    eax, eax
0x180053337  js      short loc_18005334F
0x180053339  mov     rcx, [rsp+490h+string]
0x18005333e  mov     rax, [rcx]
0x180053341  mov     rdx, rsi
0x180053344  mov     rax, [rax+38h]
0x180053348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005334d  mov     ebx, eax
0x18005334f  lea     rcx, [rsp+490h+string]
0x180053354  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180053359  jmp     loc_1800534C5
0x18005335e  mov     [rsp+490h+packageInfoReference], 0
0x180053367  mov     rax, [rdi]
0x18005336a  mov     rbx, [rax+48h]
0x18005336e  xor     ecx, ecx; string
0x180053370  call    cs:__imp_WindowsDeleteString
0x180053376  mov     [rsp+490h+string], 0; HSTRING *
0x18005337f  lea     rdx, [rsp+490h+string]
0x180053384  mov     rcx, rdi
0x180053387  mov     rax, rbx
0x18005338a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005338f  mov     ebx, eax
0x180053391  test    eax, eax
0x180053393  js      loc_1800534BA
0x180053399  xor     edx, edx; length
0x18005339b  mov     rcx, [rsp+490h+string]; string
0x1800533a0  call    cs:__imp_WindowsGetStringRawBuffer
0x1800533a6  lea     r8, [rsp+490h+packageInfoReference]; packageInfoReference
0x1800533ab  xor     edx, edx; reserved
0x1800533ad  mov     rcx, rax; packageFullName
0x1800533b0  call    cs:__imp_OpenPackageInfoByFullName
0x1800533b6  mov     ebx, eax
0x1800533b8  mov     edi, 80070000h
0x1800533bd  test    eax, eax
0x1800533bf  jle     short loc_1800533C6
0x1800533c1  movzx   ebx, ax
0x1800533c4  or      ebx, edi
0x1800533c6  test    ebx, ebx
0x1800533c8  js      loc_1800534BA
0x1800533ce  mov     [rsp+490h+var_458], 0
0x1800533d7  lea     r9, [rsp+490h+var_458]
0x1800533dc  xor     r8d, r8d
0x1800533df  xor     edx, edx
0x1800533e1  mov     rcx, [rsp+490h+packageInfoReference]
0x1800533e6  call    cs:__imp_GetPackageContext
0x1800533ec  mov     ebx, eax
0x1800533ee  test    eax, eax
0x1800533f0  jle     short loc_1800533F7
0x1800533f2  movzx   ebx, ax
0x1800533f5  or      ebx, edi
0x1800533f7  test    ebx, ebx
0x1800533f9  js      loc_1800534AE
0x1800533ff  mov     ebx, 208h
0x180053404  mov     r8d, ebx; Size
0x180053407  xor     edx, edx; Val
0x180053409  lea     rcx, [rsp+490h+var_440]; void *
0x18005340e  call    memset_0
0x180053413  mov     r8d, ebx; Size
0x180053416  xor     edx, edx; Val
0x180053418  lea     rcx, [rbp+390h+var_230]; void *
0x18005341f  call    memset_0
0x180053424  mov     [rsp+490h+var_464], 104h
0x18005342c  lea     r9, [rsp+490h+var_440]
0x180053431  lea     r8, [rsp+490h+var_464]
0x180053436  mov     edx, 0Ah
0x18005343b  mov     rcx, [rsp+490h+var_458]
0x180053440  call    cs:__imp_GetPackagePropertyString
0x180053446  mov     ebx, eax
0x180053448  test    eax, eax
0x18005344a  jle     short loc_180053451
0x18005344c  movzx   ebx, ax
0x18005344f  or      ebx, edi
0x180053451  test    ebx, ebx
0x180053453  js      short loc_1800534AE
0x180053455  mov     [rsp+490h+var_460], 104h
0x18005345d  lea     r9, [rbp+390h+var_230]
0x180053464  lea     r8, [rsp+490h+var_460]
0x180053469  mov     edx, 0Eh
0x18005346e  mov     rcx, [rsp+490h+var_458]
0x180053473  call    cs:__imp_GetPackagePropertyString
0x180053479  mov     ebx, eax
0x18005347b  test    eax, eax
0x18005347d  jle     short loc_180053484
0x18005347f  movzx   ebx, ax
0x180053482  or      ebx, edi
0x180053484  test    ebx, ebx
0x180053486  js      short loc_1800534AE
0x180053488  xor     edx, edx; length
0x18005348a  mov     rcx, [rsp+490h+string]; string
0x18005348f  call    cs:__imp_WindowsGetStringRawBuffer
0x180053495  mov     r9, rsi; string
0x180053498  lea     r8, [rsp+490h+var_440]; unsigned __int16 *
0x18005349d  lea     rdx, [rbp+390h+var_230]; unsigned __int16 *
0x1800534a4  mov     rcx, rax; this
0x1800534a7  call    ?GetFullyQualifiedFilePath@StorageSenseHandlers@SystemSettings@@YAJPEBG00PEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::GetFullyQualifiedFilePath(ushort const *,ushort const *,ushort const *,HSTRING__ * *)
0x1800534ac  mov     ebx, eax
0x1800534ae  mov     rcx, [rsp+490h+packageInfoReference]; packageInfoReference
0x1800534b3  call    cs:__imp_ClosePackageInfo
0x1800534b9  nop
0x1800534ba  mov     rcx, [rsp+490h+string]; string
0x1800534bf  call    cs:__imp_WindowsDeleteString
0x1800534c5  xor     edx, edx; length
0x1800534c7  mov     rcx, [rsi]; string
0x1800534ca  call    cs:__imp_WindowsGetStringRawBuffer
0x1800534d0  mov     eax, ebx
0x1800534d2  mov     rcx, [rbp+390h+var_20]
0x1800534d9  xor     rcx, rsp; StackCookie
0x1800534dc  call    __security_check_cookie
0x1800534e1  mov     rbx, [rsp+490h+arg_10]
0x1800534e9  add     rsp, 480h
0x1800534f0  pop     rdi
0x1800534f1  pop     rsi
0x1800534f2  pop     rbp
0x1800534f3  retn
```
