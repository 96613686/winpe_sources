# _IsNetworkConnectionUnmetered(void)

- ea: `0x180062684`
- end: `0x1800628c5`
- name: `?_IsNetworkConnectionUnmetered@@YA_NXZ`
- size: `577`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180061e88`
- `0x180062644`

## callees

- `0x180003a00`
- `0x180012a98`
- `0x18003771c`
- `0x180062684`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180062701`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180062701`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800626bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800626bf`

## string_xrefs

- `0x180062860`: `onecore\base\languageoverlay\common\policyutils.cpp`
- `0x180062875`: `onecore\base\languageoverlay\common\policyutils.cpp`
- `0x18006288a`: `onecore\base\languageoverlay\common\policyutils.cpp`
- `0x18006289e`: `onecore\base\languageoverlay\common\policyutils.cpp`
- `0x1800628b2`: `onecore\base\languageoverlay\common\policyutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
char _IsNetworkConnectionUnmetered(void)
{
  HRESULT v0; // eax
  int v1; // edx
  unsigned int v2; // r8d
  int ActivationFactory; // eax
  wil::details::in1diag3 *v4; // rcx
  int v5; // eax
  __int64 v6; // rcx
  int v7; // eax
  int v8; // eax
  int v9; // eax
  __int64 v10; // rcx
  char v11; // bl
  _QWORD *v12; // rcx
  char result; // al
  int v14; // [rsp+20h] [rbp-58h] BYREF
  _QWORD *v15; // [rsp+28h] [rbp-50h] BYREF
  int v16; // [rsp+30h] [rbp-48h] BYREF
  __int64 v17; // [rsp+38h] [rbp-40h] BYREF
  __int64 v18; // [rsp+40h] [rbp-38h] BYREF
  HSTRING_HEADER v19; // [rsp+48h] [rbp-30h] BYREF
  HSTRING v20; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v15 = 0;
  v20 = 0;
  v0 = WindowsCreateStringReference(L"Windows.Networking.Connectivity.NetworkInformation", 0x32u, &v19, &v20);
  try
  {
    if ( v0 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v0, v1, v2);
    }
    else
    {
      ActivationFactory = RoGetActivationFactory(v20, &GUID_5074f851_950d_4165_9c15_365619481eea, &v15);
      v4 = retaddr;
      if ( ActivationFactory >= 0 )
      {
        v18 = 0;
        v5 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *))(*v15 + 56LL))(v15, &v18);
        if ( v5 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xFB,
            (unsigned int)"onecore\\base\\languageoverlay\\common\\policyutils.cpp",
            (const char *)(unsigned int)v5,
            v14);
        v16 = 0;
        v6 = v18;
        if ( !v18 )
          goto LABEL_13;
        v17 = 0;
        v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v18 + 72LL))(v18, &v17);
        if ( v7 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x101,
            (unsigned int)"onecore\\base\\languageoverlay\\common\\policyutils.cpp",
            (const char *)(unsigned int)v7,
            v14);
        LOBYTE(v14) = 0;
        v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v17 + 56LL))(v17, &v14);
        if ( v8 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x104,
            (unsigned int)"onecore\\base\\languageoverlay\\common\\policyutils.cpp",
            (const char *)(unsigned int)v8,
            v14);
        if ( !(_BYTE)v14 )
        {
          v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v17 + 48LL))(v17, &v16);
          if ( v9 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x108,
              (unsigned int)"onecore\\base\\languageoverlay\\common\\policyutils.cpp",
              (const char *)(unsigned int)v9,
              v14);
        }
        v10 = v17;
        if ( v17 )
        {
          v17 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        }
        v11 = 1;
        v6 = v18;
        if ( v16 != 1 )
LABEL_13:
          v11 = 0;
        if ( v6 )
        {
          v18 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
        }
        v12 = v15;
        if ( v15 )
        {
          v15 = 0;
          (*(void (__fastcall **)(_QWORD *, _QWORD))(*v12 + 16LL))(v12, *v12);
        }
        return v11;
      }
    }
    wil::details::in1diag3::Throw_Hr(
      v4,
      (void *)0xF8,
      (unsigned int)"onecore\\base\\languageoverlay\\common\\policyutils.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v14);
  }
  catch ( ... )
  {
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180062684  mov     r11, rsp
0x180062687  push    rbx
0x180062688  sub     rsp, 70h
0x18006268c  mov     rax, cs:__security_cookie
0x180062693  xor     rax, rsp
0x180062696  mov     [rsp+78h+var_10], rax
0x18006269b  mov     qword ptr [r11-50h], 0
0x1800626a3  mov     qword ptr [r11-18h], 0
0x1800626ab  lea     r9, [r11-18h]; string
0x1800626af  lea     r8, [r11-30h]; hstringHeader
0x1800626b3  mov     edx, 32h ; '2'; length
0x1800626b8  lea     rcx, ?RuntimeClass_Windows_Networking_Connectivity_NetworkInformation@@3QBGB; "Windows.Networking.Connectivity.Network"...
0x1800626bf  call    cs:__imp_WindowsCreateStringReference
0x1800626c5  test    eax, eax
0x1800626c7  js      loc_180062855
0x1800626cd  mov     rbx, [rsp+78h+var_18]
0x1800626d2  mov     rcx, [rsp+78h+var_50]
0x1800626d7  test    rcx, rcx
0x1800626da  jz      short loc_1800626F2
0x1800626dc  mov     [rsp+78h+var_50], 0
0x1800626e5  mov     rax, [rcx]
0x1800626e8  mov     rax, [rax+10h]
0x1800626ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800626f1  nop
0x1800626f2  lea     r8, [rsp+78h+var_50]
0x1800626f7  lea     rdx, _GUID_5074f851_950d_4165_9c15_365619481eea
0x1800626fe  mov     rcx, rbx
0x180062701  call    cs:__imp_RoGetActivationFactory
0x180062707  mov     rcx, [rsp+78h]
0x18006270c  test    eax, eax
0x18006270e  js      loc_18006285D
0x180062714  mov     [rsp+78h+var_38], 0
0x18006271d  mov     rcx, [rsp+78h+var_50]
0x180062722  mov     rax, [rcx]
0x180062725  lea     rdx, [rsp+78h+var_38]
0x18006272a  mov     rax, [rax+38h]
0x18006272e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062733  mov     rcx, [rsp+78h]; this
0x180062738  test    eax, eax
0x18006273a  js      loc_180062872
0x180062740  mov     [rsp+78h+var_48], 0
0x180062748  mov     rcx, [rsp+78h+var_38]
0x18006274d  test    rcx, rcx
0x180062750  jz      loc_1800627FF
0x180062756  mov     [rsp+78h+var_40], 0
0x18006275f  mov     rax, [rcx]
0x180062762  lea     rdx, [rsp+78h+var_40]
0x180062767  mov     rax, [rax+48h]
0x18006276b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062770  mov     rcx, [rsp+78h]; this
0x180062775  test    eax, eax
0x180062777  js      loc_180062887
0x18006277d  mov     byte ptr [rsp+78h+var_58], 0; int
0x180062782  mov     rcx, [rsp+78h+var_40]
0x180062787  mov     rax, [rcx]
0x18006278a  lea     rdx, [rsp+78h+var_58]
0x18006278f  mov     rax, [rax+38h]
0x180062793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062798  mov     rcx, [rsp+78h]; this
0x18006279d  test    eax, eax
0x18006279f  js      loc_18006289B
0x1800627a5  cmp     byte ptr [rsp+78h+var_58], 0
0x1800627aa  jnz     short loc_1800627CF
0x1800627ac  mov     rcx, [rsp+78h+var_40]
0x1800627b1  mov     rax, [rcx]
0x1800627b4  lea     rdx, [rsp+78h+var_48]
0x1800627b9  mov     rax, [rax+30h]
0x1800627bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800627c2  mov     rcx, [rsp+78h]; this
0x1800627c7  test    eax, eax
0x1800627c9  js      loc_1800628AF
0x1800627cf  mov     rcx, [rsp+78h+var_40]
0x1800627d4  test    rcx, rcx
0x1800627d7  jz      short loc_1800627EF
0x1800627d9  mov     [rsp+78h+var_40], 0
0x1800627e2  mov     rax, [rcx]
0x1800627e5  mov     rax, [rax+10h]
0x1800627e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800627ee  nop
0x1800627ef  mov     ebx, 1
0x1800627f4  mov     rcx, [rsp+78h+var_38]
0x1800627f9  cmp     [rsp+78h+var_48], ebx
0x1800627fd  jz      short loc_180062801
0x1800627ff  xor     bl, bl
0x180062801  test    rcx, rcx
0x180062804  jz      short loc_18006281C
0x180062806  mov     [rsp+78h+var_38], 0
0x18006280f  mov     rax, [rcx]
0x180062812  mov     rax, [rax+10h]
0x180062816  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006281b  nop
0x18006281c  mov     rcx, [rsp+78h+var_50]
0x180062821  test    rcx, rcx
0x180062824  jz      short loc_18006283C
0x180062826  mov     [rsp+78h+var_50], 0
0x18006282f  mov     rdx, [rcx]
0x180062832  mov     rax, [rdx+10h]
0x180062836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006283b  nop
0x18006283c  mov     al, bl
0x18006283e  jmp     short loc_180062842
0x180062840  xor     al, al
0x180062842  mov     rcx, [rsp+78h+var_10]
0x180062847  xor     rcx, rsp; StackCookie
0x18006284a  call    __security_check_cookie
0x18006284f  add     rsp, 70h
0x180062853  pop     rbx
0x180062854  retn
0x180062855  mov     ecx, eax; this
0x180062857  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18006285c  nop
0x18006285d  mov     r9d, eax; char *
0x180062860  lea     r8, aOnecoreBaseLan_24; "onecore\\base\\languageoverlay\\common"...
0x180062867  mov     edx, 0F8h; void *
0x18006286c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180062872  mov     r9d, eax; char *
0x180062875  lea     r8, aOnecoreBaseLan_24; "onecore\\base\\languageoverlay\\common"...
0x18006287c  mov     edx, 0FBh; void *
0x180062881  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180062887  mov     r9d, eax; char *
0x18006288a  lea     r8, aOnecoreBaseLan_24; "onecore\\base\\languageoverlay\\common"...
0x180062891  mov     edx, 101h; void *
0x180062896  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006289b  mov     r9d, eax; char *
0x18006289e  lea     r8, aOnecoreBaseLan_24; "onecore\\base\\languageoverlay\\common"...
0x1800628a5  mov     edx, 104h; void *
0x1800628aa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800628af  mov     r9d, eax; char *
0x1800628b2  lea     r8, aOnecoreBaseLan_24; "onecore\\base\\languageoverlay\\common"...
0x1800628b9  mov     edx, 108h; void *
0x1800628be  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
