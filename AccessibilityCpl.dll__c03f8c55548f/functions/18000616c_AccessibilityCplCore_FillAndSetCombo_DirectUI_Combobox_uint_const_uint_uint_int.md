# AccessibilityCplCore::FillAndSetCombo(DirectUI::Combobox *,uint const *,uint,uint,int)

- ea: `0x18000616c`
- end: `0x1800063b8`
- name: `?FillAndSetCombo@AccessibilityCplCore@@AEAAXPEAVCombobox@DirectUI@@PEBIIIH@Z`
- size: `588`
- prototype: `void __fastcall(AccessibilityCplCore *__hidden this, struct DirectUI::Combobox *, const unsigned int *, unsigned int, unsigned int, int)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180018a28`
- `0x180018fe8`
- `0x180019c5c`

## callees

- `0x18000616c`
- `0x18001a6c0`
- `0x18001a724`
- `0x18002d220`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180006257`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800062a7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800062fe`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180006322`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180006257`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800062a7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800062fe`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180006322`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180006219`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180006219`
- `USER32!SendMessageW` at `0x1800061e8`
- `USER32!SendMessageW` at `0x180006388`
- `USER32!SendMessageW` at `0x1800061e8`
- `USER32!SendMessageW` at `0x180006388`
- `DUI70!?AddString@Combobox@DirectUI@@QEAAHPEBG@Z` at `0x180006358`
- `DUI70!?AddString@Combobox@DirectUI@@QEAAHPEBG@Z` at `0x180006358`

## pseudocode

```c
void __fastcall AccessibilityCplCore::FillAndSetCombo(
        AccessibilityCplCore *this,
        struct DirectUI::Combobox *a2,
        const unsigned int *a3,
        unsigned int a4,
        unsigned int a5,
        int a6)
{
  __int64 i; // rcx
  unsigned int v10; // r13d
  HWND v11; // rax
  __int64 j; // rsi
  size_t *v13; // r8
  unsigned int v14; // ecx
  __int64 v15; // r9
  unsigned int v16; // r14d
  HWND v17; // rax
  WCHAR *v18; // [rsp+20h] [rbp-E0h]
  WCHAR LCData[4]; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v20; // [rsp+38h] [rbp-C8h]
  WCHAR Buffer[104]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR v22[104]; // [rsp+110h] [rbp+10h] BYREF

  for ( i = 0; (unsigned int)i < a4; i = (unsigned int)(i + 1) )
  {
    if ( a3[i] >= a5 )
      break;
  }
  v10 = a4 - 1;
  if ( (unsigned int)i < a4 )
    v10 = i;
  v11 = (HWND)(*(__int64 (__fastcall **)(struct DirectUI::Combobox *))(*(_QWORD *)a2 + 360LL))(a2);
  SendMessageW(v11, 0x14Bu, 0, 0);
  for ( j = 0; (unsigned int)j < a4; j = (unsigned int)(j + 1) )
  {
    *(_QWORD *)LCData = 0;
    v20 = 0;
    if ( !GetLocaleInfoW(0x400u, 0xEu, LCData, 5) )
      StringCopyWorkerW(LCData, 2u, v13, L".", (size_t)v18);
    v14 = a3[j];
    if ( v14 < 0x1D4C0 )
    {
      if ( v14 >= 0xEA60 )
      {
        LoadStringW(g_hinst, 6u, v22, 100);
        goto LABEL_18;
      }
      v16 = v14 / 0x3E8;
      if ( v14 % 0x3E8 / 0x64 || a6 )
      {
        LoadStringW(g_hinst, 2u, Buffer, 100);
        v18 = LCData;
        StringCchPrintfW(v22, 0x64u, Buffer, v16);
        goto LABEL_18;
      }
      LoadStringW(g_hinst, 7u, Buffer, 100);
      v15 = v16;
    }
    else
    {
      LoadStringW(g_hinst, 5u, Buffer, 100);
      v15 = a3[j] / 0x3E8 / 0x3C;
    }
    StringCchPrintfW(v22, 0x64u, Buffer, v15);
LABEL_18:
    DirectUI::Combobox::AddString(a2, v22);
  }
  v17 = (HWND)(*(__int64 (__fastcall **)(struct DirectUI::Combobox *))(*(_QWORD *)a2 + 360LL))(a2);
  SendMessageW(v17, 0x14Eu, v10, 0);
}

```

## disassembly

```asm
0x18000616c  mov     [rsp-8+arg_0], rbx
0x180006171  push    rbp
0x180006172  push    rsi
0x180006173  push    rdi
0x180006174  push    r12
0x180006176  push    r13
0x180006178  push    r14
0x18000617a  push    r15
0x18000617c  lea     rbp, [rsp-0F0h]
0x180006184  sub     rsp, 1F0h
0x18000618b  mov     rax, cs:__security_cookie
0x180006192  xor     rax, rsp
0x180006195  mov     [rbp+120h+var_40], rax
0x18000619c  xor     ecx, ecx
0x18000619e  mov     ebx, r9d
0x1800061a1  mov     r12, r8
0x1800061a4  mov     rdi, rdx
0x1800061a7  test    r9d, r9d
0x1800061aa  jz      short loc_1800061BE
0x1800061ac  mov     edx, [rbp+120h+arg_20]
0x1800061b2  cmp     [r8+rcx*4], edx
0x1800061b6  jnb     short loc_1800061BE
0x1800061b8  inc     ecx
0x1800061ba  cmp     ecx, ebx
0x1800061bc  jb      short loc_1800061B2
0x1800061be  mov     rax, [rdi]
0x1800061c1  lea     r13d, [r9-1]
0x1800061c5  cmp     ecx, ebx
0x1800061c7  cmovb   r13d, ecx
0x1800061cb  mov     rcx, rdi
0x1800061ce  mov     rax, [rax+168h]
0x1800061d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061da  mov     rcx, rax; hWnd
0x1800061dd  xor     r9d, r9d; lParam
0x1800061e0  xor     r8d, r8d; wParam
0x1800061e3  mov     edx, 14Bh; Msg
0x1800061e8  call    cs:__imp_SendMessageW
0x1800061ee  xor     esi, esi
0x1800061f0  test    ebx, ebx
0x1800061f2  jz      loc_180006368
0x1800061f8  lea     r15d, [rsi+64h]
0x1800061fc  xor     eax, eax
0x1800061fe  lea     r8, [rsp+220h+LCData]; lpLCData
0x180006203  mov     ecx, 400h; Locale
0x180006208  mov     qword ptr [rsp+220h+LCData], rax
0x18000620d  mov     [rsp+220h+var_1E8], ax
0x180006212  lea     r9d, [rax+5]; cchData
0x180006216  lea     edx, [rax+0Eh]; LCType
0x180006219  call    cs:__imp_GetLocaleInfoW
0x18000621f  test    eax, eax
0x180006221  jnz     short loc_180006237
0x180006223  lea     r9, pszSrc; "."
0x18000622a  lea     edx, [rax+2]; cchDest
0x18000622d  lea     rcx, [rsp+220h+LCData]; pszDest
0x180006232  call    StringCopyWorkerW
0x180006237  mov     ecx, [r12+rsi*4]
0x18000623b  cmp     ecx, 1D4C0h
0x180006241  jb      short loc_18000628C
0x180006243  mov     rcx, cs:g_hinst; hInstance
0x18000624a  lea     r8, [rsp+220h+Buffer]; lpBuffer
0x18000624f  mov     r9d, r15d; cchBufferMax
0x180006252  mov     edx, 5; uID
0x180006257  call    cs:__imp_LoadStringW
0x18000625d  mov     eax, 10624DD3h
0x180006262  mul     dword ptr [r12+rsi*4]
0x180006266  mov     eax, 88888889h
0x18000626b  shr     edx, 6
0x18000626e  mul     edx
0x180006270  shr     edx, 5
0x180006273  mov     r9d, edx
0x180006276  lea     r8, [rsp+220h+Buffer]; unsigned __int16 *
0x18000627b  mov     rdx, r15; unsigned __int64
0x18000627e  lea     rcx, [rbp+120h+var_110]; unsigned __int16 *
0x180006282  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006287  jmp     loc_180006351
0x18000628c  cmp     ecx, 0EA60h
0x180006292  jb      short loc_1800062B2
0x180006294  mov     rcx, cs:g_hinst; hInstance
0x18000629b  lea     r8, [rbp+120h+var_110]; lpBuffer
0x18000629f  mov     r9d, r15d; cchBufferMax
0x1800062a2  mov     edx, 6; uID
0x1800062a7  call    cs:__imp_LoadStringW
0x1800062ad  jmp     loc_180006351
0x1800062b2  mov     eax, 10624DD3h
0x1800062b7  mul     ecx
0x1800062b9  mov     r14d, edx
0x1800062bc  shr     r14d, 6
0x1800062c0  imul    eax, r14d, 3E8h
0x1800062c7  sub     ecx, eax
0x1800062c9  mov     eax, 51EB851Fh
0x1800062ce  mul     ecx
0x1800062d0  mov     r15d, edx
0x1800062d3  shr     r15d, 5
0x1800062d7  test    r15d, r15d
0x1800062da  jnz     short loc_18000630C
0x1800062dc  cmp     [rbp+120h+arg_28], r15d
0x1800062e3  jnz     short loc_18000630C
0x1800062e5  mov     rcx, cs:g_hinst; hInstance
0x1800062ec  lea     r8, [rsp+220h+Buffer]; lpBuffer
0x1800062f1  mov     r15d, 64h ; 'd'
0x1800062f7  mov     r9d, r15d; cchBufferMax
0x1800062fa  lea     edx, [r15-5Dh]; uID
0x1800062fe  call    cs:__imp_LoadStringW
0x180006304  mov     r9d, r14d
0x180006307  jmp     loc_180006276
0x18000630c  mov     rcx, cs:g_hinst; hInstance
0x180006313  lea     r8, [rsp+220h+Buffer]; lpBuffer
0x180006318  mov     r9d, 64h ; 'd'; cchBufferMax
0x18000631e  lea     edx, [r9-62h]; uID
0x180006322  call    cs:__imp_LoadStringW
0x180006328  mov     [rsp+220h+var_1F8], r15d
0x18000632d  lea     rax, [rsp+220h+LCData]
0x180006332  mov     r15d, 64h ; 'd'
0x180006338  mov     [rsp+220h+var_200], rax
0x18000633d  mov     edx, r15d; unsigned __int64
0x180006340  lea     r8, [rsp+220h+Buffer]; unsigned __int16 *
0x180006345  mov     r9d, r14d
0x180006348  lea     rcx, [rbp+120h+var_110]; unsigned __int16 *
0x18000634c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006351  lea     rdx, [rbp+120h+var_110]
0x180006355  mov     rcx, rdi
0x180006358  call    cs:__imp_?AddString@Combobox@DirectUI@@QEAAHPEBG@Z; DirectUI::Combobox::AddString(ushort const *)
0x18000635e  inc     esi
0x180006360  cmp     esi, ebx
0x180006362  jb      loc_1800061FC
0x180006368  mov     rax, [rdi]
0x18000636b  mov     rcx, rdi
0x18000636e  mov     rax, [rax+168h]
0x180006375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000637a  mov     rcx, rax; hWnd
0x18000637d  mov     r8d, r13d; wParam
0x180006380  xor     r9d, r9d; lParam
0x180006383  mov     edx, 14Eh; Msg
0x180006388  call    cs:__imp_SendMessageW
0x18000638e  mov     rcx, [rbp+120h+var_40]
0x180006395  xor     rcx, rsp; StackCookie
0x180006398  call    __security_check_cookie
0x18000639d  mov     rbx, [rsp+220h+arg_0]
0x1800063a5  add     rsp, 1F0h
0x1800063ac  pop     r15
0x1800063ae  pop     r14
0x1800063b0  pop     r13
0x1800063b2  pop     r12
0x1800063b4  pop     rdi
0x1800063b5  pop     rsi
0x1800063b6  pop     rbp
0x1800063b7  retn
```
