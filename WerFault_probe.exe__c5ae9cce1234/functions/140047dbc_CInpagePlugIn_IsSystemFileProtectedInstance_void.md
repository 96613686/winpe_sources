# CInpagePlugIn::IsSystemFileProtectedInstance(void)

- ea: `0x140047dbc`
- end: `0x140048123`
- name: `?IsSystemFileProtectedInstance@CInpagePlugIn@@AEAAHXZ`
- size: `871`
- prototype: `__int64 __fastcall(CInpagePlugIn *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x140047b20`

## callees

- `0x140002470`
- `0x1400030a8`
- `0x14000fa08`
- `0x140011f24`
- `0x14001444c`
- `0x140047dbc`
- `0x14004812c`
- `0x14005d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_tolower` at `0x140047e50`
- `api-ms-win-crt-private-l1-1-0!_o_tolower` at `0x140047e5f`
- `api-ms-win-crt-private-l1-1-0!_o_tolower` at `0x140047e50`
- `api-ms-win-crt-private-l1-1-0!_o_tolower` at `0x140047e5f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140047e93`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140047eea`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14004809c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400480ab`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140047e93`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140047eea`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14004809c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400480ab`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140047eac`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140047f03`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140047f1f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140047eac`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140047f03`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140047f1f`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x140047e30`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x140047e30`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1400480bb`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1400480bb`

## string_xrefs

- `0x140047ec0`: `kernel32.dll`
- `0x140047e6d`: `sfc_os.dll`

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
    v8 = (HMODULE *)UtilLoadModFromSystem(&hLibModule, L"sfc_os.dll");
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
    v9 = (HMODULE *)UtilLoadModFromSystem(&hLibModule, L"kernel32.dll");
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
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_1a5416ce094a32ffbfa11198aa918cdd_Traceguids);
          }
          goto LABEL_31;
        }
      }
      else if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_1a5416ce094a32ffbfa11198aa918cdd_Traceguids);
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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_1a5416ce094a32ffbfa11198aa918cdd_Traceguids);
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
0x140047dbc  push    rbp
0x140047dbe  push    rbx
0x140047dbf  push    rsi
0x140047dc0  push    rdi
0x140047dc1  push    r12
0x140047dc3  push    r13
0x140047dc5  push    r14
0x140047dc7  push    r15
0x140047dc9  lea     rbp, [rsp-398h]
0x140047dd1  sub     rsp, 498h
0x140047dd8  mov     rax, cs:__security_cookie
0x140047ddf  xor     rax, rsp
0x140047de2  mov     [rbp+3D0h+var_50], rax
0x140047de9  mov     r13, rcx
0x140047dec  xor     edx, edx; Val
0x140047dee  mov     r8d, 208h; Size
0x140047df4  lea     rcx, [rsp+4D0h+var_470]; void *
0x140047df9  call    memset_0
0x140047dfe  or      r15, 0FFFFFFFFFFFFFFFFh
0x140047e02  mov     [rsp+4D0h+var_480], r15
0x140047e07  xor     eax, eax
0x140047e09  mov     esi, eax
0x140047e0b  mov     [rsp+4D0h+var_490], rax
0x140047e10  mov     edi, eax
0x140047e12  mov     [rsp+4D0h+var_488], rax
0x140047e17  mov     r12d, eax
0x140047e1a  mov     [rsp+4D0h+var_4A0], eax
0x140047e1e  mov     eax, 104h
0x140047e23  mov     [rsp+4D0h+var_49C], eax
0x140047e27  mov     edx, eax; uSize
0x140047e29  lea     rcx, [rbp+3D0h+Buffer]; lpBuffer
0x140047e30  call    cs:__imp_GetWindowsDirectoryW
0x140047e36  dec     eax
0x140047e38  mov     r14d, 102h
0x140047e3e  cmp     eax, r14d
0x140047e41  ja      loc_1400480EF
0x140047e47  lea     r12, [r13+30h]
0x140047e4b  movzx   ecx, word ptr [r12]
0x140047e50  call    cs:__imp__o_tolower
0x140047e56  mov     ebx, eax
0x140047e58  movzx   ecx, [rbp+3D0h+Buffer]
0x140047e5f  call    cs:__imp__o_tolower
0x140047e65  cmp     eax, ebx
0x140047e67  jnz     loc_14004808F
0x140047e6d  lea     rdx, aSfcOsDll; "sfc_os.dll"
0x140047e74  lea     rcx, [rsp+4D0h+hLibModule]
0x140047e79  call    ?UtilLoadModFromSystem@@YA?AV?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@PEB_W@Z; UtilLoadModFromSystem(wchar_t const *)
0x140047e7e  mov     rsi, [rax]
0x140047e81  mov     [rax], rdi
0x140047e84  mov     [rsp+4D0h+var_490], rsi
0x140047e89  mov     rcx, [rsp+4D0h+hLibModule]; hLibModule
0x140047e8e  test    rcx, rcx
0x140047e91  jz      short loc_140047E99
0x140047e93  call    cs:__imp_FreeLibrary
0x140047e99  test    rsi, rsi
0x140047e9c  jz      loc_14004808F
0x140047ea2  lea     rdx, aSfcisfileprote; "SfcIsFileProtected"
0x140047ea9  mov     rcx, rsi; hModule
0x140047eac  call    cs:__imp_GetProcAddress
0x140047eb2  mov     [rsp+4D0h+var_478], rax
0x140047eb7  test    rax, rax
0x140047eba  jz      loc_14004808F
0x140047ec0  lea     rdx, aKernel32Dll; "kernel32.dll"
0x140047ec7  lea     rcx, [rsp+4D0h+hLibModule]
0x140047ecc  call    ?UtilLoadModFromSystem@@YA?AV?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@PEB_W@Z; UtilLoadModFromSystem(wchar_t const *)
0x140047ed1  mov     rdi, [rax]
0x140047ed4  mov     qword ptr [rax], 0
0x140047edb  mov     [rsp+4D0h+var_488], rdi
0x140047ee0  mov     rcx, [rsp+4D0h+hLibModule]; hLibModule
0x140047ee5  test    rcx, rcx
0x140047ee8  jz      short loc_140047EF0
0x140047eea  call    cs:__imp_FreeLibrary
0x140047ef0  test    rdi, rdi
0x140047ef3  jz      loc_14004808F
0x140047ef9  lea     rdx, aFindfirstfilen; "FindFirstFileNameW"
0x140047f00  mov     rcx, rdi; hModule
0x140047f03  call    cs:__imp_GetProcAddress
0x140047f09  mov     rbx, rax
0x140047f0c  test    rax, rax
0x140047f0f  jz      loc_14004808F
0x140047f15  lea     rdx, aFindnextfilena; "FindNextFileNameW"
0x140047f1c  mov     rcx, rdi; hModule
0x140047f1f  call    cs:__imp_GetProcAddress
0x140047f25  mov     [rsp+4D0h+hLibModule], rax
0x140047f2a  test    rax, rax
0x140047f2d  jz      loc_14004808F
0x140047f33  lea     r9, [rsp+4D0h+var_470]
0x140047f38  lea     r8, [rsp+4D0h+var_49C]
0x140047f3d  xor     edx, edx
0x140047f3f  mov     rcx, r12
0x140047f42  mov     rax, rbx
0x140047f45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047f4a  mov     r15, rax
0x140047f4d  mov     [rsp+4D0h+var_480], rax
0x140047f52  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140047f56  jz      loc_14004808F
0x140047f5c  lea     rbx, WPP_GLOBAL_Control
0x140047f63  lea     rcx, [rsp+4D0h+var_470]; wchar_t *
0x140047f68  call    ?UtilFileExists@@YA_NPEB_W@Z; UtilFileExists(wchar_t const *)
0x140047f6d  test    al, al
0x140047f6f  jz      loc_14004802F
0x140047f75  lea     rdx, [rsp+4D0h+var_470]
0x140047f7a  xor     ecx, ecx
0x140047f7c  mov     rax, [rsp+4D0h+var_478]
0x140047f81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047f86  test    eax, eax
0x140047f88  jz      loc_140048056
0x140047f8e  mov     rcx, r13; this
0x140047f91  call    ?IsWdiHostProcess@CInpagePlugIn@@AEAAHXZ; CInpagePlugIn::IsWdiHostProcess(void)
0x140047f96  test    eax, eax
0x140047f98  jnz     loc_140048056
0x140047f9e  movzx   eax, word ptr [r12]
0x140047fa3  mov     [r13+238h], ax
0x140047fab  mov     word ptr [r13+23Ah], 3Ah ; ':'
0x140047fb5  mov     ecx, 7FFFFFFEh
0x140047fba  lea     rdx, [rsp+4D0h+var_470]
0x140047fbf  lea     rax, [r13+23Ch]
0x140047fc6  xor     r12d, r12d
0x140047fc9  test    rcx, rcx
0x140047fcc  jz      short loc_140047FED
0x140047fce  movzx   r8d, word ptr [rdx]
0x140047fd2  test    r8w, r8w
0x140047fd6  jz      short loc_140047FED
0x140047fd8  add     rdx, 2
0x140047fdc  mov     [rax], r8w
0x140047fe0  add     rax, 2
0x140047fe4  dec     rcx
0x140047fe7  sub     r14, 1
0x140047feb  jnz     short loc_140047FC9
0x140047fed  lea     rcx, [rax-2]
0x140047ff1  test    r14, r14
0x140047ff4  cmovnz  rcx, rax
0x140047ff8  mov     [rcx], r12w
0x140047ffc  jnz     loc_1400480E7
0x140048002  mov     rcx, cs:WPP_GLOBAL_Control
0x140048009  cmp     rcx, rbx
0x14004800c  jz      loc_140048094
0x140048012  test    byte ptr [rcx+1Ch], 1
0x140048016  jz      short loc_140048094
0x140048018  mov     edx, 19h
0x14004801d  lea     r8, WPP_1a5416ce094a32ffbfa11198aa918cdd_Traceguids
0x140048024  mov     rcx, [rcx+10h]
0x140048028  call    WPP_SF_
0x14004802d  jmp     short loc_140048094
0x14004802f  mov     rcx, cs:WPP_GLOBAL_Control
0x140048036  cmp     rcx, rbx
0x140048039  jz      short loc_140048056
0x14004803b  test    byte ptr [rcx+1Ch], 1
0x14004803f  jz      short loc_140048056
0x140048041  mov     edx, 18h
0x140048046  lea     r8, WPP_1a5416ce094a32ffbfa11198aa918cdd_Traceguids
0x14004804d  mov     rcx, [rcx+10h]
0x140048051  call    WPP_SF_
0x140048056  xor     edx, edx; Val
0x140048058  mov     r8d, 208h; Size
0x14004805e  lea     rcx, [rsp+4D0h+var_470]; void *
0x140048063  call    memset_0
0x140048068  mov     [rsp+4D0h+var_49C], 104h
0x140048070  lea     r8, [rsp+4D0h+var_470]
0x140048075  lea     rdx, [rsp+4D0h+var_49C]
0x14004807a  mov     rcx, r15
0x14004807d  mov     rax, [rsp+4D0h+hLibModule]
0x140048082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140048087  test    eax, eax
0x140048089  jnz     loc_140047F63
0x14004808f  mov     r12d, [rsp+4D0h+var_4A0]
0x140048094  test    rdi, rdi
0x140048097  jz      short loc_1400480A3
0x140048099  mov     rcx, rdi; hLibModule
0x14004809c  call    cs:__imp_FreeLibrary
0x1400480a2  nop
0x1400480a3  test    rsi, rsi
0x1400480a6  jz      short loc_1400480B2
0x1400480a8  mov     rcx, rsi; hLibModule
0x1400480ab  call    cs:__imp_FreeLibrary
0x1400480b1  nop
0x1400480b2  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x1400480b6  jz      short loc_1400480C1
0x1400480b8  mov     rcx, r15; hFindFile
0x1400480bb  call    cs:__imp_FindClose
0x1400480c1  mov     eax, r12d
0x1400480c4  mov     rcx, [rbp+3D0h+var_50]
0x1400480cb  xor     rcx, rsp; StackCookie
0x1400480ce  call    __security_check_cookie
0x1400480d3  add     rsp, 498h
0x1400480da  pop     r15
0x1400480dc  pop     r14
0x1400480de  pop     r13
0x1400480e0  pop     r12
0x1400480e2  pop     rdi
0x1400480e3  pop     rsi
0x1400480e4  pop     rbx
0x1400480e5  pop     rbp
0x1400480e6  retn
0x1400480e7  mov     r12d, 1
0x1400480ed  jmp     short loc_140048094
0x1400480ef  lea     rbx, WPP_GLOBAL_Control
0x1400480f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400480fd  cmp     rcx, rbx
0x140048100  jz      short loc_140048094
0x140048102  test    byte ptr [rcx+1Ch], 1
0x140048106  jz      short loc_140048094
0x140048108  mov     edx, 17h
0x14004810d  lea     r8, WPP_1a5416ce094a32ffbfa11198aa918cdd_Traceguids
0x140048114  mov     rcx, [rcx+10h]
0x140048118  call    WPP_SF_
0x14004811d  jmp     loc_140048094
```
