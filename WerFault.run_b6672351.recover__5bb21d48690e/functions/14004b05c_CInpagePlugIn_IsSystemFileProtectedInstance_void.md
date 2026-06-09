# CInpagePlugIn::IsSystemFileProtectedInstance(void)

- ea: `0x14004b05c`
- end: `0x14004b40e`
- name: `?IsSystemFileProtectedInstance@CInpagePlugIn@@AEAAHXZ`
- size: `946`
- prototype: `__int64 __fastcall(CInpagePlugIn *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x14004adc0`

## callees

- `0x140002490`
- `0x1400030f8`
- `0x140010034`
- `0x140012784`
- `0x140014ee4`
- `0x14004b05c`
- `0x14004b414`
- `0x140061010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_tolower` at `0x14004b0f6`
- `api-ms-win-crt-private-l1-1-0!_o_tolower` at `0x14004b10b`
- `api-ms-win-crt-private-l1-1-0!_o_tolower` at `0x14004b0f6`
- `api-ms-win-crt-private-l1-1-0!_o_tolower` at `0x14004b10b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14004b145`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14004b1a8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14004b36c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14004b381`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14004b145`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14004b1a8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14004b36c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14004b381`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004b164`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004b1c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004b1e9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004b164`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004b1c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004b1e9`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x14004b0d0`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x14004b0d0`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x14004b397`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x14004b397`

## string_xrefs

- `0x14004b17e`: `kernel32.dll`
- `0x14004b11f`: `sfc_os.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CInpagePlugIn::IsSystemFileProtectedInstance(CInpagePlugIn *this)
{
  __int64 v2; // r15
  HMODULE v3; // rsi
  HMODULE v4; // rdi
  unsigned int v5; // r12d
  __int64 v6; // r14
  int v7; // ebx
  HMODULE *v8; // rax
  HMODULE *v9; // rax
  FARPROC v10; // rbx
  __int64 v11; // rcx
  wchar_t *v12; // rdx
  wchar_t *v13; // rax
  wchar_t v14; // r8
  wchar_t *v15; // rcx
  int v17; // [rsp+34h] [rbp-CCh] BYREF
  HMODULE hLibModule; // [rsp+38h] [rbp-C8h] BYREF
  HMODULE v19; // [rsp+40h] [rbp-C0h]
  HMODULE v20; // [rsp+48h] [rbp-B8h]
  __int64 v21; // [rsp+50h] [rbp-B0h]
  FARPROC ProcAddress; // [rsp+58h] [rbp-A8h]
  wchar_t v23[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Buffer[264]; // [rsp+270h] [rbp+170h] BYREF

  memset_0(v23, 0, 0x208u);
  v2 = -1;
  v21 = -1;
  v3 = 0;
  v19 = 0;
  v4 = 0;
  v20 = 0;
  v5 = 0;
  v17 = 260;
  v6 = 258;
  if ( GetWindowsDirectoryW(Buffer, 0x104u) - 1 <= 0x102 )
  {
    v7 = _o_tolower(*((unsigned __int16 *)this + 24));
    if ( (unsigned int)_o_tolower(Buffer[0]) != v7 )
      goto LABEL_30;
    v8 = UtilLoadModFromSystem(&hLibModule, (__int64)L"sfc_os.dll");
    v3 = *v8;
    *v8 = 0;
    v19 = v3;
    if ( hLibModule )
      FreeLibrary(hLibModule);
    if ( !v3 )
      goto LABEL_30;
    ProcAddress = GetProcAddress(v3, "SfcIsFileProtected");
    if ( !ProcAddress )
      goto LABEL_30;
    v9 = UtilLoadModFromSystem(&hLibModule, (__int64)L"kernel32.dll");
    v4 = *v9;
    *v9 = 0;
    v20 = v4;
    if ( hLibModule )
      FreeLibrary(hLibModule);
    if ( !v4
      || (v10 = GetProcAddress(v4, "FindFirstFileNameW")) == 0
      || (hLibModule = (HMODULE)GetProcAddress(v4, "FindNextFileNameW")) == 0
      || (v2 = ((__int64 (__fastcall *)(char *, _QWORD, int *, wchar_t *))v10)((char *)this + 48, 0, &v17, v23),
          v21 = v2,
          v2 == -1) )
    {
LABEL_30:
      v5 = 0;
      goto LABEL_31;
    }
    while ( 1 )
    {
      if ( UtilFileExists(v23) )
      {
        if ( ((unsigned int (__fastcall *)(_QWORD, wchar_t *))ProcAddress)(0, v23)
          && !(unsigned int)CInpagePlugIn::IsWdiHostProcess(this) )
        {
          *((_WORD *)this + 284) = *((_WORD *)this + 24);
          *((_WORD *)this + 285) = 58;
          v11 = 2147483646;
          v12 = v23;
          v13 = (wchar_t *)((char *)this + 572);
          v5 = 0;
          do
          {
            if ( !v11 )
              break;
            v14 = *v12;
            if ( !*v12 )
              break;
            ++v12;
            *v13++ = v14;
            --v11;
            --v6;
          }
          while ( v6 );
          v15 = v13 - 1;
          if ( v6 )
            v15 = v13;
          *v15 = 0;
          if ( v6 )
          {
            v5 = 1;
          }
          else if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_1a5416ce094a32ffbfa11198aa918cdd_Traceguids);
          }
          goto LABEL_31;
        }
      }
      else if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_1a5416ce094a32ffbfa11198aa918cdd_Traceguids);
      }
      memset_0(v23, 0, 0x208u);
      v17 = 260;
      if ( !((unsigned int (__fastcall *)(__int64, int *, wchar_t *))hLibModule)(v2, &v17, v23) )
        goto LABEL_30;
    }
  }
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_1a5416ce094a32ffbfa11198aa918cdd_Traceguids);
  }
LABEL_31:
  if ( v4 )
    FreeLibrary(v4);
  if ( v3 )
    FreeLibrary(v3);
  if ( v2 != -1 )
    FindClose((HANDLE)v2);
  return v5;
}

```

## disassembly

```asm
0x14004b05c  push    rbp
0x14004b05e  push    rbx
0x14004b05f  push    rsi
0x14004b060  push    rdi
0x14004b061  push    r12
0x14004b063  push    r13
0x14004b065  push    r14
0x14004b067  push    r15
0x14004b069  lea     rbp, [rsp-398h]
0x14004b071  sub     rsp, 498h
0x14004b078  mov     rax, cs:__security_cookie
0x14004b07f  xor     rax, rsp
0x14004b082  mov     [rbp+3D0h+var_50], rax
0x14004b089  mov     r13, rcx
0x14004b08c  xor     edx, edx; Val
0x14004b08e  mov     r8d, 208h; Size
0x14004b094  lea     rcx, [rsp+4D0h+var_470]; void *
0x14004b099  call    memset_0
0x14004b09e  or      r15, 0FFFFFFFFFFFFFFFFh
0x14004b0a2  mov     [rsp+4D0h+var_480], r15
0x14004b0a7  xor     eax, eax
0x14004b0a9  mov     esi, eax
0x14004b0ab  mov     [rsp+4D0h+var_490], rax
0x14004b0b0  mov     edi, eax
0x14004b0b2  mov     [rsp+4D0h+var_488], rax
0x14004b0b7  mov     r12d, eax
0x14004b0ba  mov     [rsp+4D0h+var_4A0], eax
0x14004b0be  mov     eax, 104h
0x14004b0c3  mov     [rsp+4D0h+var_49C], eax
0x14004b0c7  mov     edx, eax; uSize
0x14004b0c9  lea     rcx, [rbp+3D0h+Buffer]; lpBuffer
0x14004b0d0  call    cs:__imp_GetWindowsDirectoryW
0x14004b0d7  nop     dword ptr [rax+rax+00h]
0x14004b0dc  dec     eax
0x14004b0de  mov     r14d, 102h
0x14004b0e4  cmp     eax, r14d
0x14004b0e7  ja      loc_14004B3D2
0x14004b0ed  lea     r12, [r13+30h]
0x14004b0f1  movzx   ecx, word ptr [r12]
0x14004b0f6  call    cs:__imp__o_tolower
0x14004b0fd  nop     dword ptr [rax+rax+00h]
0x14004b102  mov     ebx, eax
0x14004b104  movzx   ecx, [rbp+3D0h+Buffer]
0x14004b10b  call    cs:__imp__o_tolower
0x14004b112  nop     dword ptr [rax+rax+00h]
0x14004b117  cmp     eax, ebx
0x14004b119  jnz     loc_14004B35F
0x14004b11f  lea     rdx, aSfcOsDll; "sfc_os.dll"
0x14004b126  lea     rcx, [rsp+4D0h+hLibModule]
0x14004b12b  call    ?UtilLoadModFromSystem@@YA?AV?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@PEB_W@Z; UtilLoadModFromSystem(wchar_t const *)
0x14004b130  mov     rsi, [rax]
0x14004b133  mov     [rax], rdi
0x14004b136  mov     [rsp+4D0h+var_490], rsi
0x14004b13b  mov     rcx, [rsp+4D0h+hLibModule]; hLibModule
0x14004b140  test    rcx, rcx
0x14004b143  jz      short loc_14004B151
0x14004b145  call    cs:__imp_FreeLibrary
0x14004b14c  nop     dword ptr [rax+rax+00h]
0x14004b151  test    rsi, rsi
0x14004b154  jz      loc_14004B35F
0x14004b15a  lea     rdx, aSfcisfileprote; "SfcIsFileProtected"
0x14004b161  mov     rcx, rsi; hModule
0x14004b164  call    cs:__imp_GetProcAddress
0x14004b16b  nop     dword ptr [rax+rax+00h]
0x14004b170  mov     [rsp+4D0h+var_478], rax
0x14004b175  test    rax, rax
0x14004b178  jz      loc_14004B35F
0x14004b17e  lea     rdx, aKernel32Dll; "kernel32.dll"
0x14004b185  lea     rcx, [rsp+4D0h+hLibModule]
0x14004b18a  call    ?UtilLoadModFromSystem@@YA?AV?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@PEB_W@Z; UtilLoadModFromSystem(wchar_t const *)
0x14004b18f  mov     rdi, [rax]
0x14004b192  mov     qword ptr [rax], 0
0x14004b199  mov     [rsp+4D0h+var_488], rdi
0x14004b19e  mov     rcx, [rsp+4D0h+hLibModule]; hLibModule
0x14004b1a3  test    rcx, rcx
0x14004b1a6  jz      short loc_14004B1B4
0x14004b1a8  call    cs:__imp_FreeLibrary
0x14004b1af  nop     dword ptr [rax+rax+00h]
0x14004b1b4  test    rdi, rdi
0x14004b1b7  jz      loc_14004B35F
0x14004b1bd  lea     rdx, aFindfirstfilen; "FindFirstFileNameW"
0x14004b1c4  mov     rcx, rdi; hModule
0x14004b1c7  call    cs:__imp_GetProcAddress
0x14004b1ce  nop     dword ptr [rax+rax+00h]
0x14004b1d3  mov     rbx, rax
0x14004b1d6  test    rax, rax
0x14004b1d9  jz      loc_14004B35F
0x14004b1df  lea     rdx, aFindnextfilena; "FindNextFileNameW"
0x14004b1e6  mov     rcx, rdi; hModule
0x14004b1e9  call    cs:__imp_GetProcAddress
0x14004b1f0  nop     dword ptr [rax+rax+00h]
0x14004b1f5  mov     [rsp+4D0h+hLibModule], rax
0x14004b1fa  test    rax, rax
0x14004b1fd  jz      loc_14004B35F
0x14004b203  lea     r9, [rsp+4D0h+var_470]
0x14004b208  lea     r8, [rsp+4D0h+var_49C]
0x14004b20d  xor     edx, edx
0x14004b20f  mov     rcx, r12
0x14004b212  mov     rax, rbx
0x14004b215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004b21a  mov     r15, rax
0x14004b21d  mov     [rsp+4D0h+var_480], rax
0x14004b222  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14004b226  jz      loc_14004B35F
0x14004b22c  lea     rbx, WPP_GLOBAL_Control
0x14004b233  lea     rcx, [rsp+4D0h+var_470]; wchar_t *
0x14004b238  call    ?UtilFileExists@@YA_NPEB_W@Z; UtilFileExists(wchar_t const *)
0x14004b23d  test    al, al
0x14004b23f  jz      loc_14004B2FF
0x14004b245  lea     rdx, [rsp+4D0h+var_470]
0x14004b24a  xor     ecx, ecx
0x14004b24c  mov     rax, [rsp+4D0h+var_478]
0x14004b251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004b256  test    eax, eax
0x14004b258  jz      loc_14004B326
0x14004b25e  mov     rcx, r13; this
0x14004b261  call    ?IsWdiHostProcess@CInpagePlugIn@@AEAAHXZ; CInpagePlugIn::IsWdiHostProcess(void)
0x14004b266  test    eax, eax
0x14004b268  jnz     loc_14004B326
0x14004b26e  movzx   eax, word ptr [r12]
0x14004b273  mov     [r13+238h], ax
0x14004b27b  mov     word ptr [r13+23Ah], 3Ah ; ':'
0x14004b285  mov     ecx, 7FFFFFFEh
0x14004b28a  lea     rdx, [rsp+4D0h+var_470]
0x14004b28f  lea     rax, [r13+23Ch]
0x14004b296  xor     r12d, r12d
0x14004b299  test    rcx, rcx
0x14004b29c  jz      short loc_14004B2BD
0x14004b29e  movzx   r8d, word ptr [rdx]
0x14004b2a2  test    r8w, r8w
0x14004b2a6  jz      short loc_14004B2BD
0x14004b2a8  add     rdx, 2
0x14004b2ac  mov     [rax], r8w
0x14004b2b0  add     rax, 2
0x14004b2b4  dec     rcx
0x14004b2b7  sub     r14, 1
0x14004b2bb  jnz     short loc_14004B299
0x14004b2bd  lea     rcx, [rax-2]
0x14004b2c1  test    r14, r14
0x14004b2c4  cmovnz  rcx, rax
0x14004b2c8  mov     [rcx], r12w
0x14004b2cc  jnz     loc_14004B3CA
0x14004b2d2  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b2d9  cmp     rcx, rbx
0x14004b2dc  jz      loc_14004B364
0x14004b2e2  test    byte ptr [rcx+1Ch], 1
0x14004b2e6  jz      short loc_14004B364
0x14004b2e8  mov     edx, 19h
0x14004b2ed  lea     r8, WPP_1a5416ce094a32ffbfa11198aa918cdd_Traceguids
0x14004b2f4  mov     rcx, [rcx+10h]
0x14004b2f8  call    WPP_SF_
0x14004b2fd  jmp     short loc_14004B364
0x14004b2ff  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b306  cmp     rcx, rbx
0x14004b309  jz      short loc_14004B326
0x14004b30b  test    byte ptr [rcx+1Ch], 1
0x14004b30f  jz      short loc_14004B326
0x14004b311  mov     edx, 18h
0x14004b316  lea     r8, WPP_1a5416ce094a32ffbfa11198aa918cdd_Traceguids
0x14004b31d  mov     rcx, [rcx+10h]
0x14004b321  call    WPP_SF_
0x14004b326  xor     edx, edx; Val
0x14004b328  mov     r8d, 208h; Size
0x14004b32e  lea     rcx, [rsp+4D0h+var_470]; void *
0x14004b333  call    memset_0
0x14004b338  mov     [rsp+4D0h+var_49C], 104h
0x14004b340  lea     r8, [rsp+4D0h+var_470]
0x14004b345  lea     rdx, [rsp+4D0h+var_49C]
0x14004b34a  mov     rcx, r15
0x14004b34d  mov     rax, [rsp+4D0h+hLibModule]
0x14004b352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004b357  test    eax, eax
0x14004b359  jnz     loc_14004B233
0x14004b35f  mov     r12d, [rsp+4D0h+var_4A0]
0x14004b364  test    rdi, rdi
0x14004b367  jz      short loc_14004B379
0x14004b369  mov     rcx, rdi; hLibModule
0x14004b36c  call    cs:__imp_FreeLibrary
0x14004b373  nop     dword ptr [rax+rax+00h]
0x14004b378  nop
0x14004b379  test    rsi, rsi
0x14004b37c  jz      short loc_14004B38E
0x14004b37e  mov     rcx, rsi; hLibModule
0x14004b381  call    cs:__imp_FreeLibrary
0x14004b388  nop     dword ptr [rax+rax+00h]
0x14004b38d  nop
0x14004b38e  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x14004b392  jz      short loc_14004B3A3
0x14004b394  mov     rcx, r15; hFindFile
0x14004b397  call    cs:__imp_FindClose
0x14004b39e  nop     dword ptr [rax+rax+00h]
0x14004b3a3  mov     eax, r12d
0x14004b3a6  mov     rcx, [rbp+3D0h+var_50]
0x14004b3ad  xor     rcx, rsp; StackCookie
0x14004b3b0  call    __security_check_cookie
0x14004b3b5  add     rsp, 498h
0x14004b3bc  pop     r15
0x14004b3be  pop     r14
0x14004b3c0  pop     r13
0x14004b3c2  pop     r12
0x14004b3c4  pop     rdi
0x14004b3c5  pop     rsi
0x14004b3c6  pop     rbx
0x14004b3c7  pop     rbp
0x14004b3c8  retn
0x14004b3ca  mov     r12d, 1
0x14004b3d0  jmp     short loc_14004B364
0x14004b3d2  lea     rbx, WPP_GLOBAL_Control
0x14004b3d9  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b3e0  cmp     rcx, rbx
0x14004b3e3  jz      loc_14004B364
0x14004b3e9  test    byte ptr [rcx+1Ch], 1
0x14004b3ed  jz      loc_14004B364
0x14004b3f3  mov     edx, 17h
0x14004b3f8  lea     r8, WPP_1a5416ce094a32ffbfa11198aa918cdd_Traceguids
0x14004b3ff  mov     rcx, [rcx+10h]
0x14004b403  call    WPP_SF_
0x14004b408  jmp     loc_14004B364
```
