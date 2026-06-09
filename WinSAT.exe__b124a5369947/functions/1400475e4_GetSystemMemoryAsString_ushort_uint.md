# GetSystemMemoryAsString(ushort *,uint)

- ea: `0x1400475e4`
- end: `0x140047749`
- name: `?GetSystemMemoryAsString@@YAJPEAGI@Z`
- size: `357`
- prototype: `__int64 __fastcall(PWSTR pszBuf, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14004d960`

## callees

- `0x140003611`
- `0x1400475e4`
- `0x140056cec`
- `0x140113220`
- `0x14011a010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140047656`
- `KERNEL32!GetProcAddress` at `0x140047656`
- `KERNEL32!FreeLibrary` at `0x14004770a`
- `KERNEL32!FreeLibrary` at `0x14004771d`
- `KERNEL32!FreeLibrary` at `0x14004770a`
- `KERNEL32!FreeLibrary` at `0x14004771d`
- `KERNEL32!GlobalMemoryStatusEx` at `0x1400476a4`
- `KERNEL32!GlobalMemoryStatusEx` at `0x1400476a4`
- `KERNEL32!LoadLibraryW` at `0x14004763d`
- `KERNEL32!LoadLibraryW` at `0x14004763d`
- `KERNEL32!GetLastError` at `0x140047664`
- `KERNEL32!GetLastError` at `0x140047664`
- `KERNEL32!SetLastError` at `0x1400476be`
- `KERNEL32!SetLastError` at `0x1400476be`
- `SHLWAPI!StrFormatByteSizeW` at `0x1400476ee`
- `SHLWAPI!StrFormatByteSizeW` at `0x1400476ee`

## string_xrefs

- `0x140047636`: `Shlwapi.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetSystemMemoryAsString(PWSTR pszBuf)
{
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rbx
  DWORDLONG ullTotalPhys; // rcx
  int v5; // ebx
  LONGLONG qdw; // [rsp+30h] [rbp-39h] BYREF
  HMODULE hLibModule[5]; // [rsp+38h] [rbp-31h] BYREF
  unsigned int (__fastcall *v9)(LONGLONG *); // [rsp+60h] [rbp-9h]
  struct _MEMORYSTATUSEX Buffer; // [rsp+70h] [rbp+7h] BYREF

  *pszBuf = 0;
  qdw = 0;
  memset(hLibModule, 0, sizeof(hLibModule));
  v9 = 0;
  mlib::KernelAPIs::LoadLibraryW((mlib::KernelAPIs *)hLibModule);
  LibraryW = LoadLibraryW(L"Shlwapi.dll");
  if ( !LibraryW )
  {
    ProcAddress = 0;
LABEL_4:
    GetLastError();
    goto LABEL_5;
  }
  ProcAddress = GetProcAddress(LibraryW, "StrFormatByteSizeEx");
  if ( !ProcAddress )
    goto LABEL_4;
LABEL_5:
  if ( v9 && v9(&qdw) )
  {
    ullTotalPhys = qdw << 10;
    goto LABEL_10;
  }
  memset_0(&Buffer, 0, sizeof(Buffer));
  Buffer.dwLength = 64;
  if ( GlobalMemoryStatusEx(&Buffer) )
  {
    ullTotalPhys = Buffer.ullTotalPhys;
LABEL_10:
    qdw = ullTotalPhys;
    if ( ProcAddress )
    {
      v5 = ((__int64 (__fastcall *)(DWORDLONG, __int64, PWSTR))ProcAddress)(ullTotalPhys, 1, pszBuf);
      if ( v5 >= 0 )
      {
LABEL_15:
        if ( hLibModule[0] )
          FreeLibrary(hLibModule[0]);
        return (unsigned int)v5;
      }
    }
    else
    {
      SetLastError(0x32u);
    }
    v5 = 0;
    if ( !StrFormatByteSizeW(qdw, pszBuf, 0x10u) )
      v5 = -2147467259;
    goto LABEL_15;
  }
  if ( hLibModule[0] )
    FreeLibrary(hLibModule[0]);
  return 2147500037LL;
}

```

## disassembly

```asm
0x1400475e4  mov     [rsp-8+arg_8], rbx
0x1400475e9  mov     [rsp-8+arg_10], rdi
0x1400475ee  push    rbp
0x1400475ef  lea     rbp, [rsp-57h]
0x1400475f4  sub     rsp, 0C0h
0x1400475fb  mov     rax, cs:__security_cookie
0x140047602  xor     rax, rsp
0x140047605  mov     [rbp+57h+var_10], rax
0x140047609  mov     rdi, rcx
0x14004760c  xor     eax, eax
0x14004760e  mov     [rcx], ax
0x140047611  mov     [rbp+57h+qdw], rax
0x140047615  mov     [rbp+57h+hLibModule], rax
0x140047619  mov     [rbp+57h+var_80], rax
0x14004761d  mov     [rbp+57h+var_78], rax
0x140047621  mov     [rbp+57h+var_70], rax
0x140047625  mov     [rbp+57h+var_68], rax
0x140047629  mov     [rbp+57h+var_60], rax
0x14004762d  lea     rcx, [rbp+57h+hLibModule]; this
0x140047631  call    ?LoadLibraryW@KernelAPIs@mlib@@QEAAKXZ; mlib::KernelAPIs::LoadLibraryW(void)
0x140047636  lea     rcx, aShlwapiDll_0; "Shlwapi.dll"
0x14004763d  call    cs:__imp_LoadLibraryW
0x140047643  test    rax, rax
0x140047646  jnz     short loc_14004764C
0x140047648  xor     ebx, ebx
0x14004764a  jmp     short loc_140047664
0x14004764c  lea     rdx, aStrformatbytes; "StrFormatByteSizeEx"
0x140047653  mov     rcx, rax; hModule
0x140047656  call    cs:__imp_GetProcAddress
0x14004765c  mov     rbx, rax
0x14004765f  test    rax, rax
0x140047662  jnz     short loc_14004766A
0x140047664  call    cs:__imp_GetLastError
0x14004766a  mov     rax, [rbp+57h+var_60]
0x14004766e  test    rax, rax
0x140047671  jz      short loc_14004768A
0x140047673  lea     rcx, [rbp+57h+qdw]
0x140047677  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004767c  test    eax, eax
0x14004767e  jz      short loc_14004768A
0x140047680  mov     rcx, [rbp+57h+qdw]
0x140047684  shl     rcx, 0Ah
0x140047688  jmp     short loc_1400476B2
0x14004768a  xor     edx, edx; Val
0x14004768c  lea     r8d, [rdx+40h]; Size
0x140047690  lea     rcx, [rbp+57h+Buffer]; void *
0x140047694  call    memset_0
0x140047699  mov     [rbp+57h+Buffer.dwLength], 40h ; '@'
0x1400476a0  lea     rcx, [rbp+57h+Buffer]; lpBuffer
0x1400476a4  call    cs:__imp_GlobalMemoryStatusEx
0x1400476aa  test    eax, eax
0x1400476ac  jz      short loc_140047714
0x1400476ae  mov     rcx, [rbp+57h+Buffer.ullTotalPhys]
0x1400476b2  mov     [rbp+57h+qdw], rcx
0x1400476b6  test    rbx, rbx
0x1400476b9  jnz     short loc_1400476C6
0x1400476bb  lea     ecx, [rbx+32h]; dwErrCode
0x1400476be  call    cs:__imp_SetLastError
0x1400476c4  jmp     short loc_1400476E1
0x1400476c6  mov     r9d, 10h
0x1400476cc  mov     r8, rdi
0x1400476cf  lea     edx, [r9-0Fh]
0x1400476d3  mov     rax, rbx
0x1400476d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400476db  mov     ebx, eax
0x1400476dd  test    eax, eax
0x1400476df  jns     short loc_140047701
0x1400476e1  mov     r8d, 10h; cchBuf
0x1400476e7  mov     rdx, rdi; pszBuf
0x1400476ea  mov     rcx, [rbp+57h+qdw]; qdw
0x1400476ee  call    cs:__imp_StrFormatByteSizeW
0x1400476f4  xor     ebx, ebx
0x1400476f6  mov     ecx, 80004005h
0x1400476fb  test    rax, rax
0x1400476fe  cmovz   ebx, ecx
0x140047701  mov     rcx, [rbp+57h+hLibModule]; hLibModule
0x140047705  test    rcx, rcx
0x140047708  jz      short loc_140047710
0x14004770a  call    cs:__imp_FreeLibrary
0x140047710  mov     eax, ebx
0x140047712  jmp     short loc_140047728
0x140047714  mov     rcx, [rbp+57h+hLibModule]; hLibModule
0x140047718  test    rcx, rcx
0x14004771b  jz      short loc_140047723
0x14004771d  call    cs:__imp_FreeLibrary
0x140047723  mov     eax, 80004005h
0x140047728  mov     rcx, [rbp+57h+var_10]
0x14004772c  xor     rcx, rsp; StackCookie
0x14004772f  call    __security_check_cookie
0x140047734  lea     r11, [rsp+0C0h+var_s0]
0x14004773c  mov     rbx, [r11+18h]
0x140047740  mov     rdi, [r11+20h]
0x140047744  mov     rsp, r11
0x140047747  pop     rbp
0x140047748  retn
```
