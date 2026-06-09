# CSearchScopeSelectorService::SetCurrentSelection(ushort const *,int)

- ea: `0x1800245c0`
- end: `0x1800247bc`
- name: `?SetCurrentSelection@CSearchScopeSelectorService@@UEAAJPEBGH@Z`
- size: `508`
- prototype: `int(CSearchScopeSelectorService *__hidden this, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800120dc`
- `0x180013db4`
- `0x1800152e8`
- `0x180020e1c`
- `0x1800245c0`
- `0x180025194`
- `0x18002590c`
- `0x180026454`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024661`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024679`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800246ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024661`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024679`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800246ed`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024617`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800246b9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024707`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024617`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800246b9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024707`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSearchScopeSelectorService::SetCurrentSelection(HSTRING *this, const unsigned __int16 *a2, int a3)
{
  const WCHAR *StringRawBuffer; // rdi
  HSTRING v5; // r8
  const WCHAR *v6; // rax
  const unsigned __int16 *v7; // rsi
  unsigned __int64 i; // r14
  int ApplicationDisplayName; // edi
  const WCHAR *v10; // rax
  CSearchScopeSelectorService *v11; // rcx
  unsigned __int16 *v13; // [rsp+30h] [rbp-30h] BYREF
  __int64 v14; // [rsp+38h] [rbp-28h]
  __int64 v15; // [rsp+40h] [rbp-20h]
  const WCHAR *v16; // [rsp+48h] [rbp-18h] BYREF
  __int64 v17; // [rsp+50h] [rbp-10h]
  __int64 v18; // [rsp+58h] [rbp-8h]

  StringRawBuffer = a2;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  if ( CompareStringOrdinal(a2, -1, L"Windows.UI.Search.CurrentApp", -1, 0) == 2 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v16);
    v17 = -1;
    v18 = -1;
    if ( (int)GetCurrentAppToSearch((IUnknown *)*(this - 8)) < 0 )
    {
      if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                           (Microsoft::WRL::Wrappers::Details *)this[2],
                           0,
                           v5)
        && (v6 = WindowsGetStringRawBuffer(this[2], 0), (unsigned int)IsAppScope(v6)) )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(this[2], 0);
      }
      else
      {
        StringRawBuffer = L"Windows.UI.Search";
      }
    }
    else
    {
      StringRawBuffer = v16;
    }
  }
  v7 = StringRawBuffer;
  for ( i = 0; i < 5; ++i )
  {
    if ( v7 != StringRawBuffer )
      break;
    if ( CompareStringOrdinal(StringRawBuffer, -1, off_180083E10[2 * i], -1, 0) == 2 )
      v7 = off_180083E10[2 * i + 1];
  }
  if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                        (Microsoft::WRL::Wrappers::Details *)this[2],
                        0,
                        v5)
    || (ApplicationDisplayName = 0,
        v10 = WindowsGetStringRawBuffer(this[2], 0),
        CompareStringOrdinal(v7, -1, v10, -1, 0) != 2) )
  {
    if ( *((_BYTE *)this + 184) )
    {
      v13 = 0;
      v14 = 0;
      v15 = 0;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v13);
      v14 = -1;
      v15 = -1;
      ApplicationDisplayName = CSearchScopeSelectorService::_GetApplicationDisplayName(v11, v7, &v13);
      if ( ApplicationDisplayName >= 0 )
        ApplicationDisplayName = CSearchScopeSelectorService::_SetCurrentScope(
                                   (CSearchScopeSelectorService *)(this - 10),
                                   v7,
                                   v13,
                                   a3 != 0);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v13);
    }
    else
    {
      ApplicationDisplayName = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                                 this + 24,
                                 v7,
                                 -1);
    }
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v16);
  return (unsigned int)ApplicationDisplayName;
}

```

## disassembly

```asm
0x1800245c0  mov     rax, rsp
0x1800245c3  mov     [rax+8], rbx
0x1800245c7  mov     [rax+10h], rsi
0x1800245cb  mov     [rax+18h], r8d
0x1800245cf  push    rbp
0x1800245d0  push    rdi
0x1800245d1  push    r12
0x1800245d3  push    r14
0x1800245d5  push    r15
0x1800245d7  mov     rbp, rsp
0x1800245da  sub     rsp, 60h
0x1800245de  mov     rdi, rdx
0x1800245e1  mov     rbx, rcx
0x1800245e4  mov     [rbp+var_18], 0
0x1800245ec  mov     [rbp+var_10], 0
0x1800245f4  mov     [rbp+var_8], 0
0x1800245fc  mov     dword ptr [rax-68h], 0
0x180024603  or      r15, 0FFFFFFFFFFFFFFFFh
0x180024607  mov     r9d, r15d; cchCount2
0x18002460a  lea     r8, c_szSearchPaneCurrentAppAppId; "Windows.UI.Search.CurrentApp"
0x180024611  mov     edx, r15d; cchCount1
0x180024614  mov     rcx, rdi; lpString1
0x180024617  call    cs:__imp_CompareStringOrdinal
0x18002461d  cmp     eax, 2
0x180024620  jnz     short loc_18002468B
0x180024622  lea     rcx, [rbp+var_18]
0x180024626  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002462b  mov     [rbp+var_10], r15
0x18002462f  mov     [rbp+var_8], r15
0x180024633  lea     r8, [rbp+var_18]
0x180024637  mov     dl, 1
0x180024639  mov     rcx, [rbx-40h]; punk
0x18002463d  call    GetCurrentAppToSearch
0x180024642  test    eax, eax
0x180024644  js      short loc_18002464C
0x180024646  mov     rdi, [rbp+var_18]
0x18002464a  jmp     short loc_18002468B
0x18002464c  xor     edx, edx; HSTRING
0x18002464e  mov     rcx, [rbx+10h]; this
0x180024652  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x180024657  test    eax, eax
0x180024659  jz      short loc_180024684
0x18002465b  xor     edx, edx; length
0x18002465d  mov     rcx, [rbx+10h]; string
0x180024661  call    cs:__imp_WindowsGetStringRawBuffer
0x180024667  mov     rcx, rax; lpString1
0x18002466a  call    IsAppScope
0x18002466f  test    eax, eax
0x180024671  jz      short loc_180024684
0x180024673  xor     edx, edx; length
0x180024675  mov     rcx, [rbx+10h]; string
0x180024679  call    cs:__imp_WindowsGetStringRawBuffer
0x18002467f  mov     rdi, rax
0x180024682  jmp     short loc_18002468B
0x180024684  lea     rdi, c_szSearchResultsAppId; "Windows.UI.Search"
0x18002468b  mov     rsi, rdi
0x18002468e  xor     r14d, r14d
0x180024691  lea     r12, off_180083E10; "Microsoft.Windows.Cortana_cw5n1h2txyewy"...
0x180024698  cmp     rsi, rdi
0x18002469b  jnz     short loc_1800246D2
0x18002469d  mov     r15, r14
0x1800246a0  add     r15, r15
0x1800246a3  mov     [rsp+60h+bIgnoreCase], 0; bIgnoreCase
0x1800246ab  or      r9d, 0FFFFFFFFh; cchCount2
0x1800246af  mov     r8, [r12+r15*8]; lpString2
0x1800246b3  or      edx, r9d; cchCount1
0x1800246b6  mov     rcx, rdi; lpString1
0x1800246b9  call    cs:__imp_CompareStringOrdinal
0x1800246bf  cmp     eax, 2
0x1800246c2  jnz     short loc_1800246C9
0x1800246c4  mov     rsi, [r12+r15*8+8]
0x1800246c9  inc     r14
0x1800246cc  cmp     r14, 5
0x1800246d0  jb      short loc_180024698
0x1800246d2  xor     edx, edx; HSTRING
0x1800246d4  mov     rcx, [rbx+10h]; this
0x1800246d8  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x1800246dd  test    eax, eax
0x1800246df  mov     r12d, [rbp+arg_10]
0x1800246e3  jz      short loc_180024718
0x1800246e5  xor     edi, edi
0x1800246e7  xor     edx, edx; length
0x1800246e9  mov     rcx, [rbx+10h]; string
0x1800246ed  call    cs:__imp_WindowsGetStringRawBuffer
0x1800246f3  mov     [rsp+60h+bIgnoreCase], edi; bIgnoreCase
0x1800246f7  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800246fb  mov     r9d, r15d; cchCount2
0x1800246fe  mov     r8, rax; lpString2
0x180024701  mov     edx, r15d; cchCount1
0x180024704  mov     rcx, rsi; lpString1
0x180024707  call    cs:__imp_CompareStringOrdinal
0x18002470d  cmp     eax, 2
0x180024710  jz      loc_180024798
0x180024716  jmp     short loc_18002471C
0x180024718  or      r15, 0FFFFFFFFFFFFFFFFh
0x18002471c  cmp     byte ptr [rbx+0B8h], 0
0x180024723  jz      short loc_180024784
0x180024725  mov     [rbp+var_30], 0
0x18002472d  mov     [rbp+var_28], 0
0x180024735  mov     [rbp+var_20], 0
0x18002473d  lea     rcx, [rbp+var_30]
0x180024741  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180024746  mov     [rbp+var_28], r15
0x18002474a  mov     [rbp+var_20], r15
0x18002474e  lea     r8, [rbp+var_30]; unsigned __int16 **
0x180024752  mov     rdx, rsi; unsigned __int16 *
0x180024755  call    ?_GetApplicationDisplayName@CSearchScopeSelectorService@@AEAAJPEBGPEAPEAG@Z; CSearchScopeSelectorService::_GetApplicationDisplayName(ushort const *,ushort * *)
0x18002475a  mov     edi, eax
0x18002475c  test    eax, eax
0x18002475e  js      short loc_180024779
0x180024760  test    r12d, r12d
0x180024763  setnz   r9b; bool
0x180024767  mov     r8, [rbp+var_30]; unsigned __int16 *
0x18002476b  mov     rdx, rsi; lpString1
0x18002476e  lea     rcx, [rbx-50h]; this
0x180024772  call    ?_SetCurrentScope@CSearchScopeSelectorService@@AEAAJPEBG0_N@Z; CSearchScopeSelectorService::_SetCurrentScope(ushort const *,ushort const *,bool)
0x180024777  mov     edi, eax
0x180024779  lea     rcx, [rbp+var_30]
0x18002477d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180024782  jmp     short loc_180024798
0x180024784  lea     rcx, [rbx+0C0h]
0x18002478b  mov     r8, r15
0x18002478e  mov     rdx, rsi
0x180024791  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180024796  mov     edi, eax
0x180024798  lea     rcx, [rbp+var_18]
0x18002479c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800247a1  mov     eax, edi
0x1800247a3  lea     r11, [rsp+60h+var_s0]
0x1800247a8  mov     rbx, [r11+30h]
0x1800247ac  mov     rsi, [r11+38h]
0x1800247b0  mov     rsp, r11
0x1800247b3  pop     r15
0x1800247b5  pop     r14
0x1800247b7  pop     r12
0x1800247b9  pop     rdi
0x1800247ba  pop     rbp
0x1800247bb  retn
```
