# win_musl::CreateTemporaryFileName(void)

- ea: `0x18005bb04`
- end: `0x18005be60`
- name: `?CreateTemporaryFileName@win_musl@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ`
- size: `860`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18005b7c0`
- `0x1800a932c`

## callees

- `0x18001a810`
- `0x18001c900`
- `0x18004f8f0`
- `0x18005b040`
- `0x18005bb04`
- `0x18005d308`
- `0x180067218`
- `0x18007dbe0`
- `0x1800cce54`
- `0x1800df3ec`
- `0x1800df448`
- `0x180117740`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18005bcea`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18005bcea`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x18005bb7b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x18005bb7b`

## string_xrefs

- `0x18005bb74`: `windows.storage.dll`
- `0x18005bc00`: `\Temp\Microsoft\OPC`

## pseudocode

```c
// Hidden C++ exception states: #wind=41
__int64 __fastcall win_musl::CreateTemporaryFileName(__int64 a1)
{
  HMODULE LibraryW; // rax
  HINSTANCE v3; // rdx
  HMODULE v4; // rbx
  int v5; // eax
  __int64 v6; // r8
  __int64 v7; // r9
  _WORD *v8; // rcx
  PVOID *v9; // rdx
  void **v10; // rdx
  unsigned int v11; // eax
  __int64 v12; // rbx
  void *v13; // rcx
  __int64 v14; // rbx
  void *v15; // rsi
  _WORD *v17; // [rsp+38h] [rbp-89h] BYREF
  _QWORD v18[4]; // [rsp+40h] [rbp-81h] BYREF
  _BYTE v19[8]; // [rsp+60h] [rbp-61h] BYREF
  void *Block[2]; // [rsp+68h] [rbp-59h]
  __int64 v21; // [rsp+78h] [rbp-49h]
  unsigned __int64 v22; // [rsp+80h] [rbp-41h]
  _BYTE v23[8]; // [rsp+88h] [rbp-39h] BYREF
  void *v24; // [rsp+90h] [rbp-31h]
  __int64 v25; // [rsp+A0h] [rbp-21h]
  unsigned __int64 v26; // [rsp+A8h] [rbp-19h]
  _BYTE v27[8]; // [rsp+B0h] [rbp-11h] BYREF
  void *v28; // [rsp+B8h] [rbp-9h]
  __int64 v29; // [rsp+C8h] [rbp+7h]
  unsigned __int64 v30; // [rsp+D0h] [rbp+Fh]
  _BYTE v31[8]; // [rsp+D8h] [rbp+17h] BYREF
  void *v32; // [rsp+E0h] [rbp+1Fh]
  __int64 v33; // [rsp+F0h] [rbp+2Fh]
  unsigned __int64 v34; // [rsp+F8h] [rbp+37h]

  v18[2] = -2;
  v18[0] = a1;
  if ( !byte_1801C5078 )
  {
    v18[0] = &CriticalSection;
    win_musl::CriticalSection::Enter((win_musl::CriticalSection *)&CriticalSection);
    if ( byte_1801C5078 )
    {
LABEL_30:
      win_musl::Locker<win_musl::CriticalSection *>::~Locker<win_musl::CriticalSection *>(v18);
      goto LABEL_31;
    }
    LibraryW = LoadLibraryW(L"windows.storage.dll");
    v4 = 0;
    if ( LibraryW )
      v4 = LibraryW;
    v18[3] = v4;
    win_musl::InitializeFolderFunctions(v4, v3);
    if ( !qword_1801C5070 )
    {
LABEL_28:
      byte_1801C5078 = 1;
      if ( v4 )
        FreeLibrary(v4);
      goto LABEL_30;
    }
    v17 = 0;
    v5 = qword_1801C5070(&FOLDERID_LocalAppDataLow, 0x8000, 0, &v17);
    v7 = (unsigned int)v5;
    v8 = v17;
    if ( v5 >= 0 && v17 && *v17 )
    {
      std::wstring::assign(&qword_1801C4DF8, v17);
      if ( qword_1801C5068 )
      {
        std::wstring::append(&qword_1801C4DF8, L"\\Temp\\Microsoft\\OPC");
        v10 = &qword_1801C4E00;
        if ( (unsigned __int64)qword_1801C4E18 >= 8 )
          v10 = (void **)qword_1801C4E00;
        v11 = ((__int64 (__fastcall *)(_QWORD, void **, _QWORD))qword_1801C5068)(0, v10, 0);
        if ( v11 && v11 != 80 && v11 != 183 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, WPP_19bef02e3ac534d429c766cc30011c2a_Traceguids, v11);
          std::wstring::assign(&qword_1801C4DF8, v17);
        }
      }
      byte_1801C4DB4 = 1;
    }
    else
    {
      v9 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      {
LABEL_24:
        if ( v8 )
        {
          if ( win_musl::close_sh_free::pSHFree )
            win_musl::close_sh_free::pSHFree(v8, v9, v6, v7);
          v17 = 0;
        }
        goto LABEL_28;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        10,
        WPP_19bef02e3ac534d429c766cc30011c2a_Traceguids,
        (unsigned int)v5);
    }
    v8 = v17;
    goto LABEL_24;
  }
LABEL_31:
  if ( byte_1801C4DB4 )
  {
    v12 = std::wstring::wstring(v23, L".tmp");
    std::wstring::wstring(v19, L"DDT");
    win_musl::CreateTemporaryFileName(a1, &qword_1801C4DF8, v19, v12);
    if ( v22 >= 8 )
      operator delete(Block[0]);
    v22 = 7;
    v21 = 0;
    LOWORD(Block[0]) = 0;
    if ( v26 >= 8 )
    {
      v13 = v24;
LABEL_44:
      operator delete(v13);
    }
  }
  else
  {
    *(_OWORD *)Block = 0;
    v21 = 0;
    win_musl::CreateTemporaryPath(v19);
    v14 = std::wstring::wstring(v23, L".tmp");
    std::wstring::wstring(v31, L"DDT");
    v15 = Block[0];
    std::wstring::wstring(v27, Block[0]);
    win_musl::CreateTemporaryFileName(a1, v27, v31, v14);
    if ( v30 >= 8 )
      operator delete(v28);
    v30 = 7;
    v29 = 0;
    LOWORD(v28) = 0;
    if ( v34 >= 8 )
      operator delete(v32);
    v34 = 7;
    v33 = 0;
    LOWORD(v32) = 0;
    if ( v26 >= 8 )
      operator delete(v24);
    v26 = 7;
    v25 = 0;
    LOWORD(v24) = 0;
    if ( v15 )
    {
      v13 = v15;
      goto LABEL_44;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18005bb04  mov     rax, rsp
0x18005bb07  push    rbp
0x18005bb08  push    rdi
0x18005bb09  push    r14
0x18005bb0b  lea     rbp, [rax-5Fh]
0x18005bb0f  sub     rsp, 100h
0x18005bb16  mov     [rbp+57h+var_C8], 0FFFFFFFFFFFFFFFEh
0x18005bb1e  mov     [rax+10h], rbx
0x18005bb22  mov     [rax+18h], rsi
0x18005bb26  mov     rax, cs:__security_cookie
0x18005bb2d  xor     rax, rsp
0x18005bb30  mov     [rbp+57h+var_18], rax
0x18005bb34  mov     rdi, rcx
0x18005bb37  mov     [rsp+110h+var_D8], rcx
0x18005bb3c  xor     r14d, r14d
0x18005bb3f  mov     al, cs:byte_1801C5078
0x18005bb45  lea     rsi, qword_1801C4DF8
0x18005bb4c  test    al, al
0x18005bb4e  jnz     loc_18005BCFB
0x18005bb54  lea     rcx, CriticalSection; this
0x18005bb5b  mov     [rsp+110h+var_D8], rcx
0x18005bb60  call    ?Enter@CriticalSection@win_musl@@QEAAXXZ; win_musl::CriticalSection::Enter(void)
0x18005bb65  nop
0x18005bb66  mov     al, cs:byte_1801C5078
0x18005bb6c  test    al, al
0x18005bb6e  jnz     loc_18005BCF1
0x18005bb74  lea     rcx, aWindowsStorage; "windows.storage.dll"
0x18005bb7b  call    cs:__imp_LoadLibraryW
0x18005bb81  mov     ebx, r14d
0x18005bb84  test    rax, rax
0x18005bb87  cmovnz  rbx, rax
0x18005bb8b  mov     [rbp+57h+var_C0], rbx
0x18005bb8f  mov     rcx, rbx; hModule
0x18005bb92  call    ?InitializeFolderFunctions@win_musl@@YAXPEAUHINSTANCE__@@@Z; win_musl::InitializeFolderFunctions(HINSTANCE__ *)
0x18005bb97  mov     rax, cs:qword_1801C5070
0x18005bb9e  test    rax, rax
0x18005bba1  jz      loc_18005BCDB
0x18005bba7  mov     [rsp+110h+var_E0], r14
0x18005bbac  lea     r9, [rsp+110h+var_E0]
0x18005bbb1  xor     r8d, r8d
0x18005bbb4  mov     edx, 8000h
0x18005bbb9  lea     rcx, FOLDERID_LocalAppDataLow
0x18005bbc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bbc5  mov     r9d, eax
0x18005bbc8  mov     rcx, [rsp+110h+var_E0]
0x18005bbcd  test    eax, eax
0x18005bbcf  js      loc_18005BC8D
0x18005bbd5  test    rcx, rcx
0x18005bbd8  jz      loc_18005BC8D
0x18005bbde  cmp     [rcx], r14w
0x18005bbe2  jz      loc_18005BC8D
0x18005bbe8  mov     rdx, rcx
0x18005bbeb  mov     rcx, rsi
0x18005bbee  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAAAEAV12@PEB_W@Z; std::wstring::assign(wchar_t const *)
0x18005bbf3  cmp     cs:qword_1801C5068, r14
0x18005bbfa  jz      loc_18005BC84
0x18005bc00  lea     rdx, ?gc_TempFileFolder@win_musl@@3QB_WB; "\\Temp\\Microsoft\\OPC"
0x18005bc07  mov     rcx, rsi
0x18005bc0a  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAAAEAV12@PEB_W@Z; std::wstring::append(wchar_t const *)
0x18005bc0f  lea     rdx, qword_1801C4E00
0x18005bc16  cmp     cs:qword_1801C4E18, 8
0x18005bc1e  cmovnb  rdx, cs:qword_1801C4E00
0x18005bc26  xor     r8d, r8d
0x18005bc29  xor     ecx, ecx
0x18005bc2b  mov     rax, cs:qword_1801C5068
0x18005bc32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bc37  test    eax, eax
0x18005bc39  jz      short loc_18005BC84
0x18005bc3b  cmp     eax, 50h ; 'P'
0x18005bc3e  jz      short loc_18005BC84
0x18005bc40  cmp     eax, 0B7h
0x18005bc45  jz      short loc_18005BC84
0x18005bc47  lea     rdx, WPP_GLOBAL_Control
0x18005bc4e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bc55  cmp     rcx, rdx
0x18005bc58  jz      short loc_18005BC77
0x18005bc5a  test    byte ptr [rcx+44h], 1
0x18005bc5e  jz      short loc_18005BC77
0x18005bc60  lea     edx, [r14+0Bh]
0x18005bc64  mov     r9d, eax
0x18005bc67  lea     r8, WPP_19bef02e3ac534d429c766cc30011c2a_Traceguids
0x18005bc6e  mov     rcx, [rcx+38h]
0x18005bc72  call    WPP_SF_d
0x18005bc77  mov     rdx, [rsp+110h+var_E0]
0x18005bc7c  mov     rcx, rsi
0x18005bc7f  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAAAEAV12@PEB_W@Z; std::wstring::assign(wchar_t const *)
0x18005bc84  mov     cs:byte_1801C4DB4, 1
0x18005bc8b  jmp     short loc_18005BCBB
0x18005bc8d  lea     rdx, WPP_GLOBAL_Control
0x18005bc94  mov     rax, cs:WPP_GLOBAL_Control
0x18005bc9b  cmp     rax, rdx
0x18005bc9e  jz      short loc_18005BCC0
0x18005bca0  test    byte ptr [rax+44h], 1
0x18005bca4  jz      short loc_18005BCC0
0x18005bca6  mov     edx, 0Ah
0x18005bcab  lea     r8, WPP_19bef02e3ac534d429c766cc30011c2a_Traceguids
0x18005bcb2  mov     rcx, [rax+38h]
0x18005bcb6  call    WPP_SF_d
0x18005bcbb  mov     rcx, [rsp+110h+var_E0]
0x18005bcc0  test    rcx, rcx
0x18005bcc3  jz      short loc_18005BCDB
0x18005bcc5  mov     rax, cs:?pSHFree@close_sh_free@win_musl@@2P6AXPEAX@ZEA; void (*win_musl::close_sh_free::pSHFree)(void *)
0x18005bccc  test    rax, rax
0x18005bccf  jz      short loc_18005BCD6
0x18005bcd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bcd6  mov     [rsp+110h+var_E0], r14
0x18005bcdb  mov     cs:byte_1801C5078, 1
0x18005bce2  test    rbx, rbx
0x18005bce5  jz      short loc_18005BCF1
0x18005bce7  mov     rcx, rbx; hLibModule
0x18005bcea  call    cs:__imp_FreeLibrary
0x18005bcf0  nop
0x18005bcf1  lea     rcx, [rsp+110h+var_D8]
0x18005bcf6  call    ??1?$Locker@PEAVCriticalSection@win_musl@@@win_musl@@QEAA@XZ; win_musl::Locker<win_musl::CriticalSection *>::~Locker<win_musl::CriticalSection *>(void)
0x18005bcfb  mov     al, cs:byte_1801C4DB4
0x18005bd01  test    al, al
0x18005bd03  jz      short loc_18005BD72
0x18005bd05  lea     rdx, aTmp; ".tmp"
0x18005bd0c  lea     rcx, [rbp+57h+var_90]
0x18005bd10  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x18005bd15  mov     rbx, rax
0x18005bd18  lea     rdx, aDdt; "DDT"
0x18005bd1f  lea     rcx, [rbp+57h+var_B8]
0x18005bd23  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x18005bd28  nop
0x18005bd29  mov     r9, rbx
0x18005bd2c  lea     r8, [rbp+57h+var_B8]
0x18005bd30  mov     rdx, rsi
0x18005bd33  mov     rcx, rdi
0x18005bd36  call    ?CreateTemporaryFileName@win_musl@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@AEBV23@00@Z; win_musl::CreateTemporaryFileName(std::wstring const &,std::wstring const &,std::wstring const &)
0x18005bd3b  nop
0x18005bd3c  cmp     [rbp+57h+var_98], 8
0x18005bd41  jb      short loc_18005BD4C
0x18005bd43  mov     rcx, [rbp+57h+Block]; Block
0x18005bd47  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005bd4c  mov     ebx, 7
0x18005bd51  mov     [rbp+57h+var_98], rbx
0x18005bd55  mov     [rbp+57h+var_A0], r14
0x18005bd59  mov     word ptr [rbp+57h+Block], r14w
0x18005bd5e  cmp     [rbp+57h+var_70], 8
0x18005bd63  jb      loc_18005BE39
0x18005bd69  mov     rcx, [rbp+57h+var_88]
0x18005bd6d  jmp     loc_18005BE34
0x18005bd72  xorps   xmm0, xmm0
0x18005bd75  movdqu  xmmword ptr [rbp+57h+Block], xmm0
0x18005bd7a  mov     [rbp+57h+var_A0], r14
0x18005bd7e  lea     rcx, [rbp+57h+var_B8]
0x18005bd82  call    ?CreateTemporaryPath@win_musl@@YAXAEAV?$vector@_WV?$allocator@_W@std@@@std@@@Z; win_musl::CreateTemporaryPath(std::vector<wchar_t> &)
0x18005bd87  lea     rdx, aTmp; ".tmp"
0x18005bd8e  lea     rcx, [rbp+57h+var_90]
0x18005bd92  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x18005bd97  mov     rbx, rax
0x18005bd9a  lea     rdx, aDdt; "DDT"
0x18005bda1  lea     rcx, [rbp+57h+var_40]
0x18005bda5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x18005bdaa  nop
0x18005bdab  mov     rsi, [rbp+57h+Block]
0x18005bdaf  mov     rdx, rsi
0x18005bdb2  lea     rcx, [rbp+57h+var_68]
0x18005bdb6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x18005bdbb  nop
0x18005bdbc  mov     r9, rbx
0x18005bdbf  lea     r8, [rbp+57h+var_40]
0x18005bdc3  lea     rdx, [rbp+57h+var_68]
0x18005bdc7  mov     rcx, rdi
0x18005bdca  call    ?CreateTemporaryFileName@win_musl@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@AEBV23@00@Z; win_musl::CreateTemporaryFileName(std::wstring const &,std::wstring const &,std::wstring const &)
0x18005bdcf  nop
0x18005bdd0  cmp     [rbp+57h+var_48], 8
0x18005bdd5  jb      short loc_18005BDE0
0x18005bdd7  mov     rcx, [rbp+57h+var_60]; Block
0x18005bddb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005bde0  mov     ebx, 7
0x18005bde5  mov     [rbp+57h+var_48], rbx
0x18005bde9  mov     [rbp+57h+var_50], r14
0x18005bded  mov     word ptr [rbp+57h+var_60], r14w
0x18005bdf2  cmp     [rbp+57h+var_20], 8
0x18005bdf7  jb      short loc_18005BE02
0x18005bdf9  mov     rcx, [rbp+57h+var_38]; Block
0x18005bdfd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005be02  mov     [rbp+57h+var_20], rbx
0x18005be06  mov     [rbp+57h+var_28], r14
0x18005be0a  mov     word ptr [rbp+57h+var_38], r14w
0x18005be0f  cmp     [rbp+57h+var_70], 8
0x18005be14  jb      short loc_18005BE1F
0x18005be16  mov     rcx, [rbp+57h+var_88]; Block
0x18005be1a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005be1f  mov     [rbp+57h+var_70], rbx
0x18005be23  mov     [rbp+57h+var_78], r14
0x18005be27  mov     word ptr [rbp+57h+var_88], r14w
0x18005be2c  test    rsi, rsi
0x18005be2f  jz      short loc_18005BE39
0x18005be31  mov     rcx, rsi; Block
0x18005be34  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005be39  mov     rax, rdi
0x18005be3c  mov     rcx, [rbp+57h+var_18]
0x18005be40  xor     rcx, rsp; StackCookie
0x18005be43  call    __security_check_cookie
0x18005be48  lea     r11, [rsp+110h+var_10]
0x18005be50  mov     rbx, [r11+28h]
0x18005be54  mov     rsi, [r11+30h]
0x18005be58  mov     rsp, r11
0x18005be5b  pop     r14
0x18005be5d  pop     rdi
0x18005be5e  pop     rbp
0x18005be5f  retn
```
