# CMultilingualSpeller::CalculateUserMultilingualLanguages(void)

- ea: `0x1802727ec`
- end: `0x180272a8d`
- name: `?CalculateUserMultilingualLanguages@CMultilingualSpeller@@QEAAJXZ`
- size: `673`
- prototype: `__int64 __fastcall(CMultilingualSpeller *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1802732bc`

## callees

- `0x180048d5c`
- `0x1800f9d0c`
- `0x180110888`
- `0x1801136d0`
- `0x18013bad0`
- `0x18013beb8`
- `0x18013c90a`
- `0x1802727c4`
- `0x1802727ec`
- `0x180272a94`
- `0x18027a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180272a29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180272a29`
- `api-ms-win-core-localization-l1-2-0!ResolveLocaleName` at `0x180272947`
- `api-ms-win-core-localization-l1-2-0!ResolveLocaleName` at `0x180272947`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x18027295c`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x18027295c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180272861`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180272861`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180272933`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180272933`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180272904`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180272a51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180272904`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180272a51`

## pseudocode

```c
__int64 __fastcall CMultilingualSpeller::CalculateUserMultilingualLanguages(CMultilingualSpeller *this)
{
  CMultilingualSpeller *v1; // rsi
  __int64 v2; // rbx
  int ActivationFactory; // ebx
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, __int64 *); // rbx
  int v6; // eax
  HSTRING v7; // rcx
  unsigned int v8; // r15d
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, _QWORD, HSTRING *); // rbx
  const WCHAR *StringRawBuffer; // rax
  LCID v12; // eax
  int v13; // r14d
  CSpellCheckScripts *v14; // r13
  __int64 v15; // rdi
  __int64 v16; // rcx
  unsigned int v17; // esi
  int v18; // eax
  unsigned int v19; // edx
  unsigned int v20; // eax
  CSpellerGlobalState *v21; // rcx
  signed int LastError; // eax
  unsigned int v24; // [rsp+20h] [rbp-E0h] BYREF
  HSTRING string; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v26; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v27; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v28; // [rsp+40h] [rbp-C0h] BYREF
  CMultilingualSpeller *v29; // [rsp+48h] [rbp-B8h]
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v31; // [rsp+68h] [rbp-98h]
  WCHAR LocaleName[88]; // [rsp+70h] [rbp-90h] BYREF

  v29 = this;
  v1 = this;
  v27 = 0;
  v31 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.System.UserProfile.GlobalizationPreferences",
    0x34u,
    0x33u);
  v2 = v31;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
  ActivationFactory = RoGetActivationFactory(v2, &GUID_01bf4326_ed37_4e96_b0e9_c1340d1ea158, &v27);
  if ( ActivationFactory >= 0 )
  {
    v4 = v27;
    v26 = 0;
    v5 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v27 + 72LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
    ActivationFactory = v5(v4, &v26);
    if ( ActivationFactory >= 0 )
    {
      v24 = 0;
      ActivationFactory = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v26 + 56LL))(v26, &v24);
      if ( ActivationFactory >= 0 )
      {
        v6 = v24;
        if ( v24 > 4 )
        {
          v6 = 4;
          v24 = 4;
        }
        v7 = 0;
        v8 = 0;
        string = 0;
        if ( v6 )
        {
          do
          {
            if ( ActivationFactory < 0 )
              break;
            v9 = v26;
            v10 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v26 + 48LL);
            WindowsDeleteString(v7);
            string = 0;
            ActivationFactory = v10(v9, v8, &string);
            if ( ActivationFactory >= 0 )
            {
              StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
              if ( !ResolveLocaleName(StringRawBuffer, LocaleName, 85)
                || (v12 = LocaleNameToLCID(LocaleName, 0), (v13 = v12) == 0) )
              {
                LastError = GetLastError();
                ActivationFactory = LastError;
                if ( LastError > 0 )
                  ActivationFactory = (unsigned __int16)LastError | 0x80070000;
                goto LABEL_22;
              }
              v28 = 0;
              ActivationFactory = CMultilingualSpeller::GetScript(v12, &v28, LocaleName);
              if ( ActivationFactory >= 0 )
              {
                v14 = (CSpellCheckScripts *)operator new(0x10u);
                *((_QWORD *)v14 + 1) = v28;
                *(_DWORD *)v14 = v13;
                v15 = *(_QWORD *)v1;
                v16 = *(_QWORD *)v1;
                v17 = *(_DWORD *)(*(_QWORD *)v1 + 4LL);
                v18 = CSpellArray<CSpellCheckScripts *>::EnsureSize(v16, v17 + 1);
                ActivationFactory = v18;
                if ( !v18 )
                {
                  v20 = *(_DWORD *)(v15 + 4);
                  if ( v17 < v20 )
                    memmove_0(
                      (void *)(*(_QWORD *)(v15 + 16) + (v17 + 1) * *(_DWORD *)(v15 + 8)),
                      (const void *)(*(_QWORD *)(v15 + 16) + v17 * *(_DWORD *)(v15 + 8)),
                      *(_DWORD *)(v15 + 8) * (v20 - v17));
                  *(_QWORD *)(*(_DWORD *)(v15 + 8) * v17 + *(_QWORD *)(v15 + 16)) = v14;
                  ++*(_DWORD *)(v15 + 4);
LABEL_16:
                  v1 = v29;
                  v21 = (CSpellerGlobalState *)*((_QWORD *)v29 + 1);
                  if ( v21 )
                    ActivationFactory = CSpellerGlobalState::AddNewInputMethod(v21, v13, &string);
                  goto LABEL_22;
                }
                if ( v18 >= 0 )
                  goto LABEL_16;
                CSpellCheckScripts::`scalar deleting destructor'(v14, v19);
                v1 = v29;
              }
            }
LABEL_22:
            v7 = string;
            ++v8;
          }
          while ( v8 < v24 );
        }
        WindowsDeleteString(v7);
      }
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x1802727ec  push    rbp
0x1802727ee  push    rbx
0x1802727ef  push    rsi
0x1802727f0  push    rdi
0x1802727f1  push    r12
0x1802727f3  push    r13
0x1802727f5  push    r14
0x1802727f7  push    r15
0x1802727f9  lea     rbp, [rsp-38h]
0x1802727fe  sub     rsp, 138h
0x180272805  mov     rax, cs:__security_cookie
0x18027280c  xor     rax, rsp
0x18027280f  mov     [rbp+70h+var_50], rax
0x180272813  xor     r12d, r12d
0x180272816  mov     [rsp+170h+var_128], rcx
0x18027281b  mov     rsi, rcx
0x18027281e  mov     [rsp+170h+var_138], r12
0x180272823  lea     rdx, ?RuntimeClass_Windows_System_UserProfile_GlobalizationPreferences@@3QBGB; "Windows.System.UserProfile.Globalizatio"...
0x18027282a  mov     [rsp+170h+var_108], r12
0x18027282f  lea     rcx, [rsp+170h+hstringHeader]; hstringHeader
0x180272834  lea     r9d, [r12+33h]; unsigned int
0x180272839  lea     r8d, [r12+34h]; unsigned int
0x18027283e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180272843  mov     rbx, [rsp+170h+var_108]
0x180272848  lea     rcx, [rsp+170h+var_138]
0x18027284d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180272852  lea     r8, [rsp+170h+var_138]
0x180272857  mov     rcx, rbx
0x18027285a  lea     rdx, _GUID_01bf4326_ed37_4e96_b0e9_c1340d1ea158
0x180272861  call    cs:__imp_RoGetActivationFactory
0x180272867  mov     ebx, eax
0x180272869  test    eax, eax
0x18027286b  js      loc_180272A61
0x180272871  mov     rdi, [rsp+170h+var_138]
0x180272876  lea     rcx, [rsp+170h+var_140]
0x18027287b  mov     [rsp+170h+var_140], r12
0x180272880  mov     rax, [rdi]
0x180272883  mov     rbx, [rax+48h]
0x180272887  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18027288c  lea     rdx, [rsp+170h+var_140]
0x180272891  mov     rcx, rdi
0x180272894  mov     rax, rbx
0x180272897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18027289c  mov     ebx, eax
0x18027289e  test    eax, eax
0x1802728a0  js      loc_180272A57
0x1802728a6  mov     rcx, [rsp+170h+var_140]
0x1802728ab  lea     rdx, [rsp+170h+var_150]
0x1802728b0  mov     [rsp+170h+var_150], r12d
0x1802728b5  mov     rax, [rcx]
0x1802728b8  mov     rax, [rax+38h]
0x1802728bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802728c1  mov     ebx, eax
0x1802728c3  test    eax, eax
0x1802728c5  js      loc_180272A57
0x1802728cb  mov     eax, [rsp+170h+var_150]
0x1802728cf  cmp     eax, 4
0x1802728d2  jbe     short loc_1802728DD
0x1802728d4  lea     eax, [r12+4]
0x1802728d9  mov     [rsp+170h+var_150], eax
0x1802728dd  mov     rcx, r12; string
0x1802728e0  mov     r15d, r12d
0x1802728e3  mov     [rsp+170h+string], rcx
0x1802728e8  test    eax, eax
0x1802728ea  jz      loc_180272A51
0x1802728f0  test    ebx, ebx
0x1802728f2  js      loc_180272A51
0x1802728f8  mov     rdi, [rsp+170h+var_140]
0x1802728fd  mov     rax, [rdi]
0x180272900  mov     rbx, [rax+30h]
0x180272904  call    cs:__imp_WindowsDeleteString
0x18027290a  lea     r8, [rsp+170h+string]
0x18027290f  mov     [rsp+170h+string], r12
0x180272914  mov     edx, r15d
0x180272917  mov     rcx, rdi
0x18027291a  mov     rax, rbx
0x18027291d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180272922  mov     ebx, eax
0x180272924  test    eax, eax
0x180272926  js      loc_180272A3E
0x18027292c  mov     rcx, [rsp+170h+string]; string
0x180272931  xor     edx, edx; length
0x180272933  call    cs:__imp_WindowsGetStringRawBuffer
0x180272939  mov     r8d, 55h ; 'U'; cchLocaleName
0x18027293f  lea     rdx, [rsp+170h+LocaleName]; lpLocaleName
0x180272944  mov     rcx, rax; lpNameToResolve
0x180272947  call    cs:__imp_ResolveLocaleName
0x18027294d  test    eax, eax
0x18027294f  jz      loc_180272A29
0x180272955  xor     edx, edx; dwFlags
0x180272957  lea     rcx, [rsp+170h+LocaleName]; lpName
0x18027295c  call    cs:__imp_LocaleNameToLCID
0x180272962  mov     r14d, eax
0x180272965  test    eax, eax
0x180272967  jz      loc_180272A29
0x18027296d  lea     r8, [rsp+170h+LocaleName]; unsigned __int16 *
0x180272972  mov     [rsp+170h+var_130], r12
0x180272977  lea     rdx, [rsp+170h+var_130]; unsigned __int16 **
0x18027297c  mov     ecx, eax; unsigned int
0x18027297e  call    ?GetScript@CMultilingualSpeller@@SAJKPEAPEAGPEAG@Z; CMultilingualSpeller::GetScript(ulong,ushort * *,ushort *)
0x180272983  mov     ebx, eax
0x180272985  test    eax, eax
0x180272987  js      loc_180272A3E
0x18027298d  mov     ecx, 10h; Size
0x180272992  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180272997  mov     rcx, [rsp+170h+var_130]
0x18027299c  mov     r13, rax
0x18027299f  mov     [rax+8], rcx
0x1802729a3  mov     [rax], r14d
0x1802729a6  mov     rdi, [rsi]
0x1802729a9  mov     rcx, rdi
0x1802729ac  mov     esi, [rdi+4]
0x1802729af  lea     edx, [rsi+1]
0x1802729b2  call    ?EnsureSize@?$CSpellArray@PEAVCSpellCheckScripts@@@@AEAAJJ@Z; CSpellArray<CSpellCheckScripts *>::EnsureSize(long)
0x1802729b7  mov     ebx, eax
0x1802729b9  test    eax, eax
0x1802729bb  jnz     short loc_180272A18
0x1802729bd  mov     eax, [rdi+4]
0x1802729c0  cmp     esi, eax
0x1802729c2  jnb     short loc_1802729E7
0x1802729c4  mov     ecx, [rdi+8]
0x1802729c7  sub     eax, esi
0x1802729c9  imul    eax, ecx
0x1802729cc  mov     edx, ecx
0x1802729ce  imul    edx, esi
0x1802729d1  mov     r8d, eax; Size
0x1802729d4  lea     eax, [rsi+1]
0x1802729d7  add     rdx, [rdi+10h]; Src
0x1802729db  imul    ecx, eax
0x1802729de  add     rcx, [rdi+10h]; void *
0x1802729e2  call    memmove_0
0x1802729e7  imul    esi, [rdi+8]
0x1802729eb  mov     rax, [rdi+10h]
0x1802729ef  mov     [rsi+rax], r13
0x1802729f3  inc     dword ptr [rdi+4]
0x1802729f6  xor     r12d, r12d
0x1802729f9  mov     rsi, [rsp+170h+var_128]
0x1802729fe  mov     rcx, [rsi+8]; this
0x180272a02  test    rcx, rcx
0x180272a05  jz      short loc_180272A3E
0x180272a07  lea     r8, [rsp+170h+string]; struct Microsoft::WRL::Wrappers::HString *
0x180272a0c  mov     edx, r14d; unsigned int
0x180272a0f  call    ?AddNewInputMethod@CSpellerGlobalState@@QEAAJKPEAVHString@Wrappers@WRL@Microsoft@@@Z; CSpellerGlobalState::AddNewInputMethod(ulong,Microsoft::WRL::Wrappers::HString *)
0x180272a14  mov     ebx, eax
0x180272a16  jmp     short loc_180272A3E
0x180272a18  jns     short loc_1802729F9
0x180272a1a  mov     rcx, r13; this
0x180272a1d  call    ??_GCSpellCheckScripts@@QEAAPEAXI@Z; CSpellCheckScripts::`scalar deleting destructor'(uint)
0x180272a22  mov     rsi, [rsp+170h+var_128]
0x180272a27  jmp     short loc_180272A3E
0x180272a29  call    cs:__imp_GetLastError
0x180272a2f  mov     ebx, eax
0x180272a31  test    eax, eax
0x180272a33  jle     short loc_180272A3E
0x180272a35  movzx   ebx, ax
0x180272a38  or      ebx, 80070000h
0x180272a3e  mov     rcx, [rsp+170h+string]; string
0x180272a43  inc     r15d
0x180272a46  cmp     r15d, [rsp+170h+var_150]
0x180272a4b  jb      loc_1802728F0
0x180272a51  call    cs:__imp_WindowsDeleteString
0x180272a57  lea     rcx, [rsp+170h+var_140]
0x180272a5c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180272a61  lea     rcx, [rsp+170h+var_138]
0x180272a66  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180272a6b  mov     eax, ebx
0x180272a6d  mov     rcx, [rbp+70h+var_50]
0x180272a71  xor     rcx, rsp; StackCookie
0x180272a74  call    __security_check_cookie
0x180272a79  add     rsp, 138h
0x180272a80  pop     r15
0x180272a82  pop     r14
0x180272a84  pop     r13
0x180272a86  pop     r12
0x180272a88  pop     rdi
0x180272a89  pop     rsi
0x180272a8a  pop     rbx
0x180272a8b  pop     rbp
0x180272a8c  retn
```
