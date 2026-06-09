# ??$RunApiFromBestDll@$$A6AHKPEB_W0PEA_WK0PEAK@Z$01H$$TAEAPEA_W$$TH$$TPEAK@@YAHAEAY01QEB_WPEBDW4FailurePolicy@@$$QEAH$$QEA$$TAEAPEA_W434$$QEAPEAK@Z

- ea: `0x180040ec8`
- end: `0x1800410ed`
- name: `??$RunApiFromBestDll@$$A6AHKPEB_W0PEA_WK0PEAK@Z$01H$$TAEAPEA_W$$TH$$TPEAK@@YAHAEAY01QEB_WPEBDW4FailurePolicy@@$$QEAH$$QEA$$TAEAPEA_W434$$QEAPEAK@Z`
- size: `549`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int *, _QWORD *, _QWORD *, _QWORD *, _DWORD *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18001e110`

## callees

- `0x18001dee8`
- `0x180040ec8`
- `0x18005097c`
- `0x18005b188`
- `0x180065035`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18004107b`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18004107b`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180040fdb`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180040fdb`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180040f47`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180040f47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040f55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040f9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040f55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040f9c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RunApiFromBestDll<int (unsigned long,wchar_t const *,wchar_t const *,wchar_t *,unsigned long,wchar_t const *,unsigned long *),2,int,std::nullptr_t,wchar_t * &,std::nullptr_t,int,std::nullptr_t,unsigned long *>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int *a4,
        _QWORD *a5,
        _QWORD *a6,
        _QWORD *a7,
        _DWORD *a8,
        _QWORD *a9,
        _QWORD *a10)
{
  void **i; // rbx
  void *v12; // rsi
  HMODULE Library; // rax
  HMODULE v14; // rdi
  DWORD LastError; // eax
  signed int v16; // eax
  FARPROC ProcAddress; // rax
  unsigned int v18; // ebx
  _BYTE pExceptionObject[280]; // [rsp+60h] [rbp-118h] BYREF

  for ( i = (void **)off_180090150; ; ++i )
  {
    if ( i == &NetSetupBindPath::`vftable'{for `INetSetupObjectRelationsProvider'} )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          WPP_5aa39ad1df123bafbedc0e28a7fdf70b_Traceguids,
          "LoadStringByReference");
      HResultException::HResultException((HResultException *)pExceptionObject, -2147024770);
      throw (HResultException *)pExceptionObject;
    }
    v12 = *i;
    Library = LoadLibraryExW((LPCWSTR)*i, 0, 0x800u);
    v14 = Library;
    if ( Library )
      break;
    LastError = GetLastError();
    if ( LastError != 2 && LastError != 126 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_5aa39ad1df123bafbedc0e28a7fdf70b_Traceguids, v12);
      v16 = GetLastError();
      if ( v16 > 0 )
        v16 = (unsigned __int16)v16 | 0x80070000;
      HResultException::HResultException((HResultException *)pExceptionObject, v16);
      throw (HResultException *)pExceptionObject;
    }
  }
  ProcAddress = GetProcAddress(Library, "LoadStringByReference");
  if ( !ProcAddress )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_5aa39ad1df123bafbedc0e28a7fdf70b_Traceguids,
        "LoadStringByReference");
    HResultException::HResultException((HResultException *)pExceptionObject, -2147024769);
    throw (HResultException *)pExceptionObject;
  }
  v18 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD))ProcAddress)(
          *a4,
          *a5,
          *a6,
          *a7,
          *a8,
          *a9,
          *a10);
  FreeLibrary(v14);
  return v18;
}

```

## disassembly

```asm
0x180040ec8  push    rbx
0x180040eca  push    rbp
0x180040ecb  push    rsi
0x180040ecc  push    rdi
0x180040ecd  push    r12
0x180040ecf  push    r13
0x180040ed1  push    r14
0x180040ed3  push    r15
0x180040ed5  sub     rsp, 138h
0x180040edc  mov     [rsp+178h+var_128], 0FFFFFFFFFFFFFFFEh
0x180040ee5  mov     r14, r9
0x180040ee8  mov     r15, [rsp+178h+arg_20]
0x180040ef0  mov     rbp, [rsp+178h+arg_28]
0x180040ef8  mov     r12, [rsp+178h+arg_30]
0x180040f00  mov     r13, [rsp+178h+arg_38]
0x180040f08  mov     rax, [rsp+178h+arg_40]
0x180040f10  mov     [rsp+178h+var_130], rax
0x180040f15  mov     rax, [rsp+178h+arg_48]
0x180040f1d  mov     [rsp+178h+var_138], rax
0x180040f22  lea     rbx, off_180090150; "api-ms-win-core-localization-private-l1"...
0x180040f29  lea     rax, ??_7NetSetupBindPath@@6BINetSetupObjectRelationsProvider@@@; const NetSetupBindPath::`vftable'{for `INetSetupObjectRelationsProvider'}
0x180040f30  cmp     rbx, rax
0x180040f33  jz      loc_180041097
0x180040f39  mov     rsi, [rbx]
0x180040f3c  xor     edx, edx; hFile
0x180040f3e  mov     r8d, 800h; dwFlags
0x180040f44  mov     rcx, rsi; lpLibFileName
0x180040f47  call    cs:__imp_LoadLibraryExW
0x180040f4d  mov     rdi, rax
0x180040f50  test    rax, rax
0x180040f53  jnz     short loc_180040FCC
0x180040f55  call    cs:__imp_GetLastError
0x180040f5b  cmp     eax, 2
0x180040f5e  jz      short loc_180040F65
0x180040f60  cmp     eax, 7Eh ; '~'
0x180040f63  jnz     short loc_180040F6B
0x180040f65  add     rbx, 8
0x180040f69  jmp     short loc_180040F29
0x180040f6b  lea     rax, WPP_GLOBAL_Control
0x180040f72  mov     rcx, cs:WPP_GLOBAL_Control
0x180040f79  cmp     rcx, rax
0x180040f7c  jz      short loc_180040F9C
0x180040f7e  cmp     byte ptr [rcx+19h], 2
0x180040f82  jb      short loc_180040F9C
0x180040f84  mov     edx, 0Ch
0x180040f89  mov     r9, rsi
0x180040f8c  lea     r8, WPP_5aa39ad1df123bafbedc0e28a7fdf70b_Traceguids
0x180040f93  mov     rcx, [rcx+10h]
0x180040f97  call    WPP_SF_S
0x180040f9c  call    cs:__imp_GetLastError
0x180040fa2  test    eax, eax
0x180040fa4  jle     short loc_180040FAE
0x180040fa6  movzx   eax, ax
0x180040fa9  or      eax, 80070000h
0x180040fae  mov     edx, eax; int
0x180040fb0  lea     rcx, [rsp+178h+pExceptionObject]; this
0x180040fb5  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180040fba  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180040fc1  lea     rcx, [rsp+178h+pExceptionObject]; pExceptionObject
0x180040fc6  call    _CxxThrowException_0
0x180040fcc  mov     [rsp+178h+var_120], rdi
0x180040fd1  lea     rdx, aLoadstringbyre; "LoadStringByReference"
0x180040fd8  mov     rcx, rdi; hModule
0x180040fdb  call    cs:__imp_GetProcAddress
0x180040fe1  mov     r10, rax
0x180040fe4  test    rax, rax
0x180040fe7  jnz     short loc_18004103E
0x180040fe9  lea     rax, WPP_GLOBAL_Control
0x180040ff0  mov     rcx, cs:WPP_GLOBAL_Control
0x180040ff7  cmp     rcx, rax
0x180040ffa  jz      short loc_18004101D
0x180040ffc  cmp     byte ptr [rcx+19h], 2
0x180041000  jb      short loc_18004101D
0x180041002  lea     edx, [r10+0Bh]
0x180041006  lea     r9, aLoadstringbyre; "LoadStringByReference"
0x18004100d  lea     r8, WPP_5aa39ad1df123bafbedc0e28a7fdf70b_Traceguids
0x180041014  mov     rcx, [rcx+10h]
0x180041018  call    WPP_SF_s
0x18004101d  mov     edx, 8007007Fh; int
0x180041022  lea     rcx, [rsp+178h+pExceptionObject]; this
0x180041027  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18004102c  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180041033  lea     rcx, [rsp+178h+pExceptionObject]; pExceptionObject
0x180041038  call    _CxxThrowException_0
0x18004103e  mov     rax, [rsp+178h+var_138]
0x180041043  mov     rax, [rax]
0x180041046  mov     [rsp+178h+var_148], rax
0x18004104b  mov     rax, [rsp+178h+var_130]
0x180041050  mov     rax, [rax]
0x180041053  mov     [rsp+178h+var_150], rax
0x180041058  mov     eax, [r13+0]
0x18004105c  mov     [rsp+178h+var_158], eax
0x180041060  mov     r9, [r12]
0x180041064  mov     r8, [rbp+0]
0x180041068  mov     rdx, [r15]
0x18004106b  mov     ecx, [r14]
0x18004106e  mov     rax, r10
0x180041071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041076  mov     ebx, eax
0x180041078  mov     rcx, rdi; hLibModule
0x18004107b  call    cs:__imp_FreeLibrary
0x180041081  mov     eax, ebx
0x180041083  add     rsp, 138h
0x18004108a  pop     r15
0x18004108c  pop     r14
0x18004108e  pop     r13
0x180041090  pop     r12
0x180041092  pop     rdi
0x180041093  pop     rsi
0x180041094  pop     rbp
0x180041095  pop     rbx
0x180041096  retn
0x180041097  lea     rax, WPP_GLOBAL_Control
0x18004109e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800410a5  cmp     rcx, rax
0x1800410a8  jz      short loc_1800410CC
0x1800410aa  cmp     byte ptr [rcx+19h], 2
0x1800410ae  jb      short loc_1800410CC
0x1800410b0  mov     edx, 0Dh
0x1800410b5  lea     r9, aLoadstringbyre; "LoadStringByReference"
0x1800410bc  lea     r8, WPP_5aa39ad1df123bafbedc0e28a7fdf70b_Traceguids
0x1800410c3  mov     rcx, [rcx+10h]
0x1800410c7  call    WPP_SF_s
0x1800410cc  mov     edx, 8007007Eh; int
0x1800410d1  lea     rcx, [rsp+178h+pExceptionObject]; this
0x1800410d6  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x1800410db  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x1800410e2  lea     rcx, [rsp+178h+pExceptionObject]; pExceptionObject
0x1800410e7  call    _CxxThrowException_0
```
