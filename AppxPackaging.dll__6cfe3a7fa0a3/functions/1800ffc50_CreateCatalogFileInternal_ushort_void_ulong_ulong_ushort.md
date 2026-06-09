# CreateCatalogFileInternal(ushort *,void (*)(ulong,ulong,ushort *))

- ea: `0x1800ffc50`
- end: `0x18010009c`
- name: `?CreateCatalogFileInternal@@YAJPEAGP6AXKK0@Z@Z`
- size: `1100`
- prototype: `int(unsigned __int16 *, void (*)(unsigned int, unsigned int, unsigned __int16 *))`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180090d60`

## callees

- `0x18006a900`
- `0x1800ad008`
- `0x1800ffc50`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800ffd17`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800ffd6a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800ffdbd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800ffe10`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800ffe68`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800ffeb3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800fffaa`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800fffd3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18010000a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18010003f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180100074`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800ffd17`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800ffd6a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800ffdbd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800ffe10`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800ffe68`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800ffeb3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800fffaa`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800fffd3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18010000a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18010003f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180100074`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800ffc7d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800ffc7d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800ffca0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800ffca0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ffce0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ffd33`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ffd86`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ffdd9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ffe2c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ffce0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ffd33`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ffd86`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ffdd9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ffe2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ffedb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fff31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fff6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ffedb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fff31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fff6d`

## string_xrefs

- `0x1800ffc76`: `wintrust.dll`
- `0x1800ffcd6`: `CryptCATCDFOpen`
- `0x1800ffc99`: `Wintrust.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreateCatalogFileInternal(
        unsigned __int16 *a1,
        void (*a2)(unsigned int, unsigned int, unsigned __int16 *))
{
  HMODULE v4; // rbx
  HMODULE ModuleHandleW; // rdi
  HMODULE Library; // rax
  const char *v7; // r9
  FARPROC ProcAddress; // rsi
  const char *v10; // r9
  unsigned int v11; // edi
  const char *v12; // r9
  FARPROC v13; // r14
  const char *v14; // r9
  FARPROC v15; // r12
  const char *v16; // r9
  FARPROC v17; // r13
  const char *v18; // r9
  __int64 v19; // rbp
  const char *v20; // r9
  __int64 v21; // rdi
  DWORD LastError; // eax
  __int64 (__fastcall *v23)(__int64, __int64, __int64, __int64); // r14
  DWORD v24; // eax
  __int64 v25; // rsi
  DWORD v26; // eax
  const char *v27; // r9
  unsigned int v28; // [rsp+20h] [rbp-68h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  __int64 v30; // [rsp+A0h] [rbp+18h] BYREF
  FARPROC v31; // [rsp+A8h] [rbp+20h]

  v4 = 0;
  ModuleHandleW = GetModuleHandleW(L"wintrust.dll");
  if ( !ModuleHandleW )
  {
    Library = LoadLibraryExW(L"Wintrust.dll", 0, 0x800u);
    ModuleHandleW = Library;
    if ( !Library )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x81,
               (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\crypto\\src\\cataloghelper.cpp",
               v7);
    v4 = Library;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "CryptCATCDFOpen");
  if ( ProcAddress )
  {
    v13 = GetProcAddress(ModuleHandleW, "CryptCATCDFEnumCatAttributes");
    if ( v13 )
    {
      v15 = GetProcAddress(ModuleHandleW, "CryptCATCDFClose");
      if ( v15 )
      {
        v17 = GetProcAddress(ModuleHandleW, "CryptCATCDFEnumMembersByCDFTagEx");
        if ( v17 )
        {
          v31 = GetProcAddress(ModuleHandleW, "CryptCATCDFEnumAttributesWithCDFTag");
          if ( v31 )
          {
            v19 = ((__int64 (__fastcall *)(unsigned __int16 *, void (*)(unsigned int, unsigned int, unsigned __int16 *)))ProcAddress)(
                    a1,
                    a2);
            if ( v19 )
            {
              v21 = 0;
              do
              {
                v21 = ((__int64 (__fastcall *)(__int64, __int64, void (*)(unsigned int, unsigned int, unsigned __int16 *)))v13)(
                        v19,
                        v21,
                        a2);
                LastError = GetLastError();
                if ( LastError )
                {
                  v11 = wil::details::in1diag3::Return_Win32(
                          retaddr,
                          (void *)0xA3,
                          (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\crypto\\src\\cataloghelper.cpp",
                          (const char *)LastError,
                          v28);
                  if ( v4 )
                    FreeLibrary(v4);
                  return v11;
                }
              }
              while ( v21 );
              v30 = 0;
              v23 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64))v31;
LABEL_33:
              v21 = ((__int64 (__fastcall *)(__int64, __int64, void (*)(unsigned int, unsigned int, unsigned __int16 *), __int64 *))v17)(
                      v19,
                      v21,
                      a2,
                      &v30);
              v24 = GetLastError();
              if ( v24 )
              {
                v11 = wil::details::in1diag3::Return_Win32(
                        retaddr,
                        (void *)0xB3,
                        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\crypto\\src\\cataloghelper.cpp",
                        (const char *)v24,
                        1u);
                if ( v4 )
                  FreeLibrary(v4);
              }
              else if ( v21 )
              {
                v25 = 0;
                while ( 1 )
                {
                  v25 = v23(v19, v21, v30, v25);
                  v26 = GetLastError();
                  if ( v26 )
                    break;
                  if ( !v25 )
                    goto LABEL_33;
                }
                v11 = wil::details::in1diag3::Return_Win32(
                        retaddr,
                        (void *)0xC2,
                        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\crypto\\src\\cataloghelper.cpp",
                        (const char *)v26,
                        (unsigned int)a2);
                if ( v4 )
                  FreeLibrary(v4);
              }
              else
              {
                if ( ((unsigned int (__fastcall *)(__int64))v15)(v19) )
                {
                  if ( v4 )
                    FreeLibrary(v4);
                  return 0;
                }
                v11 = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0xCC,
                        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\crypto\\src\\cataloghelper.cpp",
                        v27);
                if ( v4 )
                  FreeLibrary(v4);
              }
            }
            else
            {
              v11 = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x9C,
                      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\crypto\\src\\cataloghelper.cpp",
                      v20);
              if ( v4 )
                FreeLibrary(v4);
            }
          }
          else
          {
            v11 = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x98,
                    (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\crypto\\src\\cataloghelper.cpp",
                    v18);
            if ( v4 )
              FreeLibrary(v4);
          }
        }
        else
        {
          v11 = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x94,
                  (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\crypto\\src\\cataloghelper.cpp",
                  v16);
          if ( v4 )
            FreeLibrary(v4);
        }
      }
      else
      {
        v11 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x90,
                (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\crypto\\src\\cataloghelper.cpp",
                v14);
        if ( v4 )
          FreeLibrary(v4);
      }
    }
    else
    {
      v11 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x8C,
              (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\crypto\\src\\cataloghelper.cpp",
              v12);
      if ( v4 )
        FreeLibrary(v4);
    }
  }
  else
  {
    v11 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x88,
            (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\crypto\\src\\cataloghelper.cpp",
            v10);
    if ( v4 )
      FreeLibrary(v4);
  }
  return v11;
}

```

## disassembly

```asm
0x1800ffc50  mov     rax, rsp
0x1800ffc53  push    rbp
0x1800ffc54  push    rsi
0x1800ffc55  push    rdi
0x1800ffc56  push    r12
0x1800ffc58  push    r13
0x1800ffc5a  push    r14
0x1800ffc5c  push    r15
0x1800ffc5e  sub     rsp, 50h
0x1800ffc62  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x1800ffc6a  mov     [rax+8], rbx
0x1800ffc6e  mov     r15, rdx
0x1800ffc71  mov     rbp, rcx
0x1800ffc74  xor     ebx, ebx
0x1800ffc76  lea     rcx, aWintrustDll_1; "wintrust.dll"
0x1800ffc7d  call    cs:__imp_GetModuleHandleW
0x1800ffc84  nop     dword ptr [rax+rax+00h]
0x1800ffc89  mov     rdi, rax
0x1800ffc8c  test    rax, rax
0x1800ffc8f  jnz     short loc_1800FFCD6
0x1800ffc91  xor     edx, edx; hFile
0x1800ffc93  mov     r8d, 800h; dwFlags
0x1800ffc99  lea     rcx, aWintrustDll_0; "Wintrust.dll"
0x1800ffca0  call    cs:__imp_LoadLibraryExW
0x1800ffca7  nop     dword ptr [rax+rax+00h]
0x1800ffcac  mov     rdi, rax
0x1800ffcaf  test    rax, rax
0x1800ffcb2  jnz     short loc_1800FFCD3
0x1800ffcb4  mov     rcx, [rsp+88h]; this
0x1800ffcbc  lea     r8, aOnecorePrintsc_171; "onecore\\printscan\\appxpackaging\\lib"...
0x1800ffcc3  mov     edx, 81h; void *
0x1800ffcc8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800ffccd  nop
0x1800ffcce  jmp     loc_180100083
0x1800ffcd3  mov     rbx, rax
0x1800ffcd6  lea     rdx, aCryptcatcdfope; "CryptCATCDFOpen"
0x1800ffcdd  mov     rcx, rdi; hModule
0x1800ffce0  call    cs:__imp_GetProcAddress
0x1800ffce7  nop     dword ptr [rax+rax+00h]
0x1800ffcec  mov     rsi, rax
0x1800ffcef  test    rax, rax
0x1800ffcf2  jnz     short loc_1800FFD29
0x1800ffcf4  mov     rcx, [rsp+88h]; this
0x1800ffcfc  lea     r8, aOnecorePrintsc_171; "onecore\\printscan\\appxpackaging\\lib"...
0x1800ffd03  mov     edx, 88h; void *
0x1800ffd08  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800ffd0d  mov     edi, eax
0x1800ffd0f  test    rbx, rbx
0x1800ffd12  jz      short loc_1800FFD24
0x1800ffd14  mov     rcx, rbx; hLibModule
0x1800ffd17  call    cs:__imp_FreeLibrary
0x1800ffd1e  nop     dword ptr [rax+rax+00h]
0x1800ffd23  nop
0x1800ffd24  jmp     loc_180100081
0x1800ffd29  lea     rdx, aCryptcatcdfenu; "CryptCATCDFEnumCatAttributes"
0x1800ffd30  mov     rcx, rdi; hModule
0x1800ffd33  call    cs:__imp_GetProcAddress
0x1800ffd3a  nop     dword ptr [rax+rax+00h]
0x1800ffd3f  mov     r14, rax
0x1800ffd42  test    rax, rax
0x1800ffd45  jnz     short loc_1800FFD7C
0x1800ffd47  mov     rcx, [rsp+88h]; this
0x1800ffd4f  lea     r8, aOnecorePrintsc_171; "onecore\\printscan\\appxpackaging\\lib"...
0x1800ffd56  mov     edx, 8Ch; void *
0x1800ffd5b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800ffd60  mov     edi, eax
0x1800ffd62  test    rbx, rbx
0x1800ffd65  jz      short loc_1800FFD77
0x1800ffd67  mov     rcx, rbx; hLibModule
0x1800ffd6a  call    cs:__imp_FreeLibrary
0x1800ffd71  nop     dword ptr [rax+rax+00h]
0x1800ffd76  nop
0x1800ffd77  jmp     loc_180100081
0x1800ffd7c  lea     rdx, aCryptcatcdfclo; "CryptCATCDFClose"
0x1800ffd83  mov     rcx, rdi; hModule
0x1800ffd86  call    cs:__imp_GetProcAddress
0x1800ffd8d  nop     dword ptr [rax+rax+00h]
0x1800ffd92  mov     r12, rax
0x1800ffd95  test    rax, rax
0x1800ffd98  jnz     short loc_1800FFDCF
0x1800ffd9a  mov     rcx, [rsp+88h]; this
0x1800ffda2  lea     r8, aOnecorePrintsc_171; "onecore\\printscan\\appxpackaging\\lib"...
0x1800ffda9  mov     edx, 90h; void *
0x1800ffdae  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800ffdb3  mov     edi, eax
0x1800ffdb5  test    rbx, rbx
0x1800ffdb8  jz      short loc_1800FFDCA
0x1800ffdba  mov     rcx, rbx; hLibModule
0x1800ffdbd  call    cs:__imp_FreeLibrary
0x1800ffdc4  nop     dword ptr [rax+rax+00h]
0x1800ffdc9  nop
0x1800ffdca  jmp     loc_180100081
0x1800ffdcf  lea     rdx, aCryptcatcdfenu_1; "CryptCATCDFEnumMembersByCDFTagEx"
0x1800ffdd6  mov     rcx, rdi; hModule
0x1800ffdd9  call    cs:__imp_GetProcAddress
0x1800ffde0  nop     dword ptr [rax+rax+00h]
0x1800ffde5  mov     r13, rax
0x1800ffde8  test    rax, rax
0x1800ffdeb  jnz     short loc_1800FFE22
0x1800ffded  mov     rcx, [rsp+88h]; this
0x1800ffdf5  lea     r8, aOnecorePrintsc_171; "onecore\\printscan\\appxpackaging\\lib"...
0x1800ffdfc  mov     edx, 94h; void *
0x1800ffe01  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800ffe06  mov     edi, eax
0x1800ffe08  test    rbx, rbx
0x1800ffe0b  jz      short loc_1800FFE1D
0x1800ffe0d  mov     rcx, rbx; hLibModule
0x1800ffe10  call    cs:__imp_FreeLibrary
0x1800ffe17  nop     dword ptr [rax+rax+00h]
0x1800ffe1c  nop
0x1800ffe1d  jmp     loc_180100081
0x1800ffe22  lea     rdx, aCryptcatcdfenu_0; "CryptCATCDFEnumAttributesWithCDFTag"
0x1800ffe29  mov     rcx, rdi; hModule
0x1800ffe2c  call    cs:__imp_GetProcAddress
0x1800ffe33  nop     dword ptr [rax+rax+00h]
0x1800ffe38  mov     [rsp+88h+arg_18], rax
0x1800ffe40  test    rax, rax
0x1800ffe43  jnz     short loc_1800FFE7A
0x1800ffe45  mov     rcx, [rsp+88h]; this
0x1800ffe4d  lea     r8, aOnecorePrintsc_171; "onecore\\printscan\\appxpackaging\\lib"...
0x1800ffe54  mov     edx, 98h; void *
0x1800ffe59  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800ffe5e  mov     edi, eax
0x1800ffe60  test    rbx, rbx
0x1800ffe63  jz      short loc_1800FFE75
0x1800ffe65  mov     rcx, rbx; hLibModule
0x1800ffe68  call    cs:__imp_FreeLibrary
0x1800ffe6f  nop     dword ptr [rax+rax+00h]
0x1800ffe74  nop
0x1800ffe75  jmp     loc_180100081
0x1800ffe7a  mov     rdx, r15
0x1800ffe7d  mov     rcx, rbp
0x1800ffe80  mov     rax, rsi
0x1800ffe83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ffe88  mov     rbp, rax
0x1800ffe8b  test    rax, rax
0x1800ffe8e  jnz     short loc_1800FFEC5
0x1800ffe90  mov     rcx, [rsp+88h]; this
0x1800ffe98  lea     r8, aOnecorePrintsc_171; "onecore\\printscan\\appxpackaging\\lib"...
0x1800ffe9f  mov     edx, 9Ch; void *
0x1800ffea4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800ffea9  mov     edi, eax
0x1800ffeab  test    rbx, rbx
0x1800ffeae  jz      short loc_1800FFEC0
0x1800ffeb0  mov     rcx, rbx; hLibModule
0x1800ffeb3  call    cs:__imp_FreeLibrary
0x1800ffeba  nop     dword ptr [rax+rax+00h]
0x1800ffebf  nop
0x1800ffec0  jmp     loc_180100081
0x1800ffec5  xor     edi, edi
0x1800ffec7  mov     r8, r15
0x1800ffeca  mov     rdx, rdi
0x1800ffecd  mov     rcx, rbp
0x1800ffed0  mov     rax, r14
0x1800ffed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ffed8  mov     rdi, rax
0x1800ffedb  call    cs:__imp_GetLastError
0x1800ffee2  nop     dword ptr [rax+rax+00h]
0x1800ffee7  test    eax, eax
0x1800ffee9  jnz     loc_18010004E
0x1800ffeef  test    rdi, rdi
0x1800ffef2  jnz     short loc_1800FFEC7
0x1800ffef4  mov     [rsp+88h+arg_10], rdi
0x1800ffefc  mov     r14, [rsp+88h+arg_18]
0x1800fff04  mov     [rsp+88h+var_60], 0
0x1800fff0d  mov     [rsp+88h+var_68], 1; unsigned int
0x1800fff15  lea     r9, [rsp+88h+arg_10]
0x1800fff1d  mov     r8, r15
0x1800fff20  mov     rdx, rdi
0x1800fff23  mov     rcx, rbp
0x1800fff26  mov     rax, r13
0x1800fff29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fff2e  mov     rdi, rax
0x1800fff31  call    cs:__imp_GetLastError
0x1800fff38  nop     dword ptr [rax+rax+00h]
0x1800fff3d  test    eax, eax
0x1800fff3f  jnz     loc_180100019
0x1800fff45  test    rdi, rdi
0x1800fff48  jz      short loc_1800FFFBC
0x1800fff4a  xor     esi, esi
0x1800fff4c  mov     qword ptr [rsp+88h+var_68], r15; unsigned int
0x1800fff51  mov     r9, rsi
0x1800fff54  mov     r8, [rsp+88h+arg_10]
0x1800fff5c  mov     rdx, rdi
0x1800fff5f  mov     rcx, rbp
0x1800fff62  mov     rax, r14
0x1800fff65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fff6a  mov     rsi, rax
0x1800fff6d  call    cs:__imp_GetLastError
0x1800fff74  nop     dword ptr [rax+rax+00h]
0x1800fff79  test    eax, eax
0x1800fff7b  jnz     short loc_1800FFF84
0x1800fff7d  test    rsi, rsi
0x1800fff80  jnz     short loc_1800FFF4C
0x1800fff82  jmp     short loc_1800FFF04
0x1800fff84  mov     rcx, [rsp+88h]; this
0x1800fff8c  mov     r9d, eax; char *
0x1800fff8f  lea     r8, aOnecorePrintsc_171; "onecore\\printscan\\appxpackaging\\lib"...
0x1800fff96  mov     edx, 0C2h; void *
0x1800fff9b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800fffa0  mov     edi, eax
0x1800fffa2  test    rbx, rbx
0x1800fffa5  jz      short loc_1800FFFB7
0x1800fffa7  mov     rcx, rbx; hLibModule
0x1800fffaa  call    cs:__imp_FreeLibrary
0x1800fffb1  nop     dword ptr [rax+rax+00h]
0x1800fffb6  nop
0x1800fffb7  jmp     loc_180100081
0x1800fffbc  mov     rcx, rbp
0x1800fffbf  mov     rax, r12
0x1800fffc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fffc7  test    eax, eax
0x1800fffc9  jz      short loc_1800FFFE7
0x1800fffcb  test    rbx, rbx
0x1800fffce  jz      short loc_1800FFFE0
0x1800fffd0  mov     rcx, rbx; hLibModule
0x1800fffd3  call    cs:__imp_FreeLibrary
0x1800fffda  nop     dword ptr [rax+rax+00h]
0x1800fffdf  nop
0x1800fffe0  xor     eax, eax
0x1800fffe2  jmp     loc_180100083
0x1800fffe7  mov     rcx, [rsp+88h]; this
0x1800fffef  lea     r8, aOnecorePrintsc_171; "onecore\\printscan\\appxpackaging\\lib"...
0x1800ffff6  mov     edx, 0CCh; void *
0x1800ffffb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180100000  mov     edi, eax
0x180100002  test    rbx, rbx
0x180100005  jz      short loc_180100017
0x180100007  mov     rcx, rbx; hLibModule
0x18010000a  call    cs:__imp_FreeLibrary
0x180100011  nop     dword ptr [rax+rax+00h]
0x180100016  nop
0x180100017  jmp     short loc_180100081
0x180100019  mov     rcx, [rsp+88h]; this
0x180100021  mov     r9d, eax; char *
0x180100024  lea     r8, aOnecorePrintsc_171; "onecore\\printscan\\appxpackaging\\lib"...
0x18010002b  mov     edx, 0B3h; void *
0x180100030  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180100035  mov     edi, eax
0x180100037  test    rbx, rbx
0x18010003a  jz      short loc_18010004C
0x18010003c  mov     rcx, rbx; hLibModule
0x18010003f  call    cs:__imp_FreeLibrary
0x180100046  nop     dword ptr [rax+rax+00h]
0x18010004b  nop
0x18010004c  jmp     short loc_180100081
0x18010004e  mov     rcx, [rsp+88h]; this
0x180100056  mov     r9d, eax; char *
0x180100059  lea     r8, aOnecorePrintsc_171; "onecore\\printscan\\appxpackaging\\lib"...
0x180100060  mov     edx, 0A3h; void *
0x180100065  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18010006a  mov     edi, eax
0x18010006c  test    rbx, rbx
0x18010006f  jz      short loc_180100081
0x180100071  mov     rcx, rbx; hLibModule
0x180100074  call    cs:__imp_FreeLibrary
0x18010007b  nop     dword ptr [rax+rax+00h]
0x180100080  nop
0x180100081  mov     eax, edi
0x180100083  mov     rbx, [rsp+88h+arg_0]
0x18010008b  add     rsp, 50h
0x18010008f  pop     r15
0x180100091  pop     r14
0x180100093  pop     r13
0x180100095  pop     r12
0x180100097  pop     rdi
0x180100098  pop     rsi
0x180100099  pop     rbp
0x18010009a  retn
```
