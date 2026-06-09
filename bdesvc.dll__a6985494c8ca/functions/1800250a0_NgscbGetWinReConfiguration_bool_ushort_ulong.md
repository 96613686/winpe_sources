# NgscbGetWinReConfiguration(bool *,ushort *,ulong)

- ea: `0x1800250a0`
- end: `0x1800252a6`
- name: `?NgscbGetWinReConfiguration@@YAJPEA_NPEAGK@Z`
- size: `518`
- prototype: `int(bool *, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x180032f60`
- `0x18004d7f0`

## callees

- `0x180009f60`
- `0x18000dd60`
- `0x1800250a0`
- `0x18002d600`
- `0x18002e628`
- `0x180034070`
- `0x180034d28`
- `0x18007e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180025138`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180025138`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180025279`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180025279`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002519b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002519b`

## string_xrefs

- `0x180025191`: `WinReGetConfig`
- `0x18002512b`: `reinfo.dll`

## pseudocode

```c
__int64 __fastcall NgscbGetWinReConfiguration(bool *a1, unsigned __int16 *a2, unsigned int a3)
{
  unsigned __int64 v3; // r14
  unsigned int KnownLastErrorHR; // ebx
  HMODULE Library; // rax
  HMODULE v8; // rbp
  FARPROC ProcAddress; // rax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v13; // [rsp+30h] [rbp-ED8h] BYREF
  int v14; // [rsp+38h] [rbp-ED0h]
  unsigned __int16 v15[1556]; // [rsp+2A8h] [rbp-C60h] BYREF

  v3 = a3;
  memset_0(&v13, 0, 0xEA0u);
  KnownLastErrorHR = 0;
  *a1 = 0;
  if ( a2 )
    memset_0(a2, 0, 2LL * (unsigned int)v3);
  if ( MEMORY[0x7FFE02D4] && (unsigned __int8)NgscbGet_TEST_DWORDOverrideHelper(L"ReportWinREAvailable") )
  {
    *a1 = 0;
    return KnownLastErrorHR;
  }
  Library = LoadLibraryExW(L"reinfo.dll", 0, 0x800u);
  v8 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "WinReGetConfig");
    if ( ProcAddress )
    {
      v13 = 3744;
      if ( ((unsigned int (__fastcall *)(_QWORD, __int64 *))ProcAddress)(0, &v13) )
      {
        *a1 = v14 != 0;
        if ( !a2 )
          goto LABEL_24;
        KnownLastErrorHR = StringCchCopyW(a2, v3, v15);
        if ( !KnownLastErrorHR )
          goto LABEL_24;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
          goto LABEL_24;
        v11 = 337;
      }
      else
      {
        KnownLastErrorHR = NgscbGetKnownLastErrorHR();
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
          goto LABEL_24;
        v11 = 336;
      }
    }
    else
    {
      KnownLastErrorHR = NgscbGetKnownLastErrorHR();
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
        goto LABEL_24;
      v11 = 335;
    }
    WPP_SF_d(v10[2], v11, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, KnownLastErrorHR);
LABEL_24:
    FreeLibrary(v8);
    return KnownLastErrorHR;
  }
  KnownLastErrorHR = NgscbGetKnownLastErrorHR();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      334,
      WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
      KnownLastErrorHR);
  return KnownLastErrorHR;
}

```

## disassembly

```asm
0x1800250a0  push    rbx
0x1800250a2  push    rbp
0x1800250a3  push    rsi
0x1800250a4  push    rdi
0x1800250a5  push    r14
0x1800250a7  sub     rsp, 0EE0h
0x1800250ae  mov     rax, cs:__security_cookie
0x1800250b5  xor     rax, rsp
0x1800250b8  mov     [rsp+0F08h+var_38], rax
0x1800250c0  mov     r14d, r8d
0x1800250c3  mov     rsi, rdx
0x1800250c6  mov     rdi, rcx
0x1800250c9  xor     edx, edx; Val
0x1800250cb  mov     r8d, 0EA0h; Size
0x1800250d1  lea     rcx, [rsp+0F08h+var_ED8]; void *
0x1800250d6  call    memset_0
0x1800250db  xor     ebx, ebx
0x1800250dd  mov     [rdi], bl
0x1800250df  test    rsi, rsi
0x1800250e2  jz      short loc_1800250F4
0x1800250e4  mov     r8d, r14d
0x1800250e7  xor     edx, edx; Val
0x1800250e9  add     r8, r8; Size
0x1800250ec  mov     rcx, rsi; void *
0x1800250ef  call    memset_0
0x1800250f4  mov     [rsp+0F08h+var_EE8], ebx
0x1800250f8  cmp     ds:7FFE02D4h, bl
0x1800250ff  jz      short loc_180025129
0x180025101  lea     rdx, [rsp+0F08h+var_EE8]
0x180025106  lea     rcx, aReportwinreava; "ReportWinREAvailable"
0x18002510d  call    NgscbGet_TEST_DWORDOverrideHelper
0x180025112  test    al, al
0x180025114  jz      short loc_180025129
0x180025116  cmp     [rsp+0F08h+var_EE8], ebx
0x18002511a  jnz     short loc_180025120
0x18002511c  xor     al, al
0x18002511e  jmp     short loc_180025122
0x180025120  mov     al, 1
0x180025122  mov     [rdi], al
0x180025124  jmp     loc_180025285
0x180025129  xor     edx, edx; hFile
0x18002512b  lea     rcx, LibFileName; "reinfo.dll"
0x180025132  mov     r8d, 800h; dwFlags
0x180025138  call    cs:__imp_LoadLibraryExW
0x18002513f  nop     dword ptr [rax+rax+00h]
0x180025144  mov     rbp, rax
0x180025147  test    rax, rax
0x18002514a  jnz     short loc_180025191
0x18002514c  call    ?NgscbGetKnownLastErrorHR@@YAJXZ; NgscbGetKnownLastErrorHR(void)
0x180025151  mov     ebx, eax
0x180025153  mov     rcx, cs:WPP_GLOBAL_Control
0x18002515a  lea     rax, WPP_GLOBAL_Control
0x180025161  cmp     rcx, rax
0x180025164  jz      loc_180025285
0x18002516a  test    byte ptr [rcx+1Ch], 40h
0x18002516e  jz      loc_180025285
0x180025174  mov     rcx, [rcx+10h]
0x180025178  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x18002517f  mov     edx, 14Eh
0x180025184  mov     r9d, ebx
0x180025187  call    WPP_SF_d
0x18002518c  jmp     loc_180025285
0x180025191  lea     rdx, aWinregetconfig; "WinReGetConfig"
0x180025198  mov     rcx, rbp; hModule
0x18002519b  call    cs:__imp_GetProcAddress
0x1800251a2  nop     dword ptr [rax+rax+00h]
0x1800251a7  test    rax, rax
0x1800251aa  jnz     short loc_1800251DE
0x1800251ac  call    ?NgscbGetKnownLastErrorHR@@YAJXZ; NgscbGetKnownLastErrorHR(void)
0x1800251b1  mov     ebx, eax
0x1800251b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800251ba  lea     rax, WPP_GLOBAL_Control
0x1800251c1  cmp     rcx, rax
0x1800251c4  jz      loc_180025276
0x1800251ca  test    byte ptr [rcx+1Ch], 40h
0x1800251ce  jz      loc_180025276
0x1800251d4  mov     edx, 14Fh
0x1800251d9  jmp     loc_180025263
0x1800251de  lea     rdx, [rsp+0F08h+var_ED8]
0x1800251e3  mov     [rsp+0F08h+var_ED8], 0EA0h
0x1800251ec  xor     ecx, ecx
0x1800251ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800251f3  test    eax, eax
0x1800251f5  jnz     short loc_18002521E
0x1800251f7  call    ?NgscbGetKnownLastErrorHR@@YAJXZ; NgscbGetKnownLastErrorHR(void)
0x1800251fc  mov     ebx, eax
0x1800251fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180025205  lea     rax, WPP_GLOBAL_Control
0x18002520c  cmp     rcx, rax
0x18002520f  jz      short loc_180025276
0x180025211  test    byte ptr [rcx+1Ch], 40h
0x180025215  jz      short loc_180025276
0x180025217  mov     edx, 150h
0x18002521c  jmp     short loc_180025263
0x18002521e  cmp     [rsp+0F08h+var_ED0], ebx
0x180025222  setnz   al
0x180025225  mov     [rdi], al
0x180025227  test    rsi, rsi
0x18002522a  jz      short loc_180025276
0x18002522c  mov     rdx, r14; unsigned __int64
0x18002522f  lea     r8, [rsp+0F08h+var_C60]; unsigned __int16 *
0x180025237  mov     rcx, rsi; unsigned __int16 *
0x18002523a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002523f  mov     ebx, eax
0x180025241  test    eax, eax
0x180025243  jz      short loc_180025276
0x180025245  mov     rcx, cs:WPP_GLOBAL_Control
0x18002524c  lea     rax, WPP_GLOBAL_Control
0x180025253  cmp     rcx, rax
0x180025256  jz      short loc_180025276
0x180025258  test    byte ptr [rcx+1Ch], 40h
0x18002525c  jz      short loc_180025276
0x18002525e  mov     edx, 151h
0x180025263  mov     rcx, [rcx+10h]
0x180025267  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x18002526e  mov     r9d, ebx
0x180025271  call    WPP_SF_d
0x180025276  mov     rcx, rbp; hLibModule
0x180025279  call    cs:__imp_FreeLibrary
0x180025280  nop     dword ptr [rax+rax+00h]
0x180025285  mov     eax, ebx
0x180025287  mov     rcx, [rsp+0F08h+var_38]
0x18002528f  xor     rcx, rsp; StackCookie
0x180025292  call    __security_check_cookie
0x180025297  add     rsp, 0EE0h
0x18002529e  pop     r14
0x1800252a0  pop     rdi
0x1800252a1  pop     rsi
0x1800252a2  pop     rbp
0x1800252a3  pop     rbx
0x1800252a4  retn
```
