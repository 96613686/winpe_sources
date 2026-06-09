# LoadResourceDLL(HINSTANCE__ * *,ushort const *)

- ea: `0x140008710`
- end: `0x14000894d`
- name: `?LoadResourceDLL@@YAJPEAPEAUHINSTANCE__@@PEBG@Z`
- size: `573`
- prototype: `__int64 __fastcall(HINSTANCE *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callers

- `0x140001cb8`

## callees

- `0x1400011d4`
- `0x140001b34`
- `0x1400036d8`
- `0x140003918`
- `0x140003c2c`
- `0x140007bf8`
- `0x140008710`
- `0x140008e34`
- `0x14000ae32`
- `0x14000ae60`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x140008850`
- `KERNEL32!LoadLibraryExW` at `0x140008850`
- `KERNEL32!IsDebuggerPresent` at `0x1400087a6`
- `KERNEL32!IsDebuggerPresent` at `0x1400088b8`
- `KERNEL32!IsDebuggerPresent` at `0x1400087a6`
- `KERNEL32!IsDebuggerPresent` at `0x1400088b8`
- `KERNEL32!GetLastError` at `0x14000885f`
- `KERNEL32!GetLastError` at `0x14000885f`

## string_xrefs

- `0x140008789`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x14000888e`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x14000876c`: `pszFullPath`
- `0x14000877e`: `AppendFileNameToModulePath`
- `0x140008882`: `LoadResourceDLL`

## pseudocode

```c
__int64 __fastcall LoadResourceDLL(HINSTANCE *a1, const unsigned __int16 *a2)
{
  unsigned __int16 *v3; // rbp
  unsigned int v4; // edx
  unsigned __int16 *v5; // rsi
  signed int ModulePath; // ebx
  const unsigned __int16 *v7; // r15
  const unsigned __int16 *v8; // r12
  unsigned int v9; // r14d
  unsigned __int64 v10; // rdx
  const unsigned __int16 *v11; // r9
  HMODULE Library; // rax
  signed int LastError; // eax
  unsigned int v15; // [rsp+20h] [rbp-268h]
  wchar_t Str[264]; // [rsp+40h] [rbp-248h] BYREF

  v3 = 0;
  memset_0(Str, 0, 0x208u);
  v5 = (unsigned __int16 *)operator new(0x208u);
  if ( !v5 )
  {
    ModulePath = -2147024882;
    v7 = L"pszFullPath";
    v8 = L"CPR";
    v9 = 97;
    goto LABEL_3;
  }
  ModulePath = GetModulePath(Str, v4);
  if ( ModulePath < 0 )
    goto LABEL_19;
  ModulePath = PathCchCombineEx(v5, v10, Str, v11, v15);
  if ( ModulePath < 0 )
  {
    v7 = L"hr";
    v9 = 103;
    v8 = L"CHRA";
LABEL_3:
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      v9,
      L"AppendFileNameToModulePath",
      v8,
      v7,
      ModulePath);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        v9,
        L"AppendFileNameToModulePath",
        v8,
        v7,
        ModulePath);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        v9,
        L"AppendFileNameToModulePath",
        v8,
        v7,
        ModulePath);
    goto LABEL_19;
  }
  Library = LoadLibraryExW(v5, 0, 2u);
  if ( Library )
  {
    *a1 = Library;
  }
  else
  {
    LastError = GetLastError();
    ModulePath = LastError;
    if ( LastError > 0 )
      ModulePath = (unsigned __int16)LastError | 0x80070000;
    if ( ModulePath >= 0 )
      ModulePath = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      0x81u,
      L"LoadResourceDLL",
      L"CBRAEx",
      L"hInst",
      ModulePath);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        129,
        L"LoadResourceDLL",
        L"CBRAEx",
        L"hInst",
        ModulePath);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        129,
        L"LoadResourceDLL",
        L"CBRAEx",
        L"hInst",
        ModulePath);
  }
  v3 = v5;
LABEL_19:
  operator delete(v3);
  return (unsigned int)ModulePath;
}

```

## disassembly

```asm
0x140008710  mov     [rsp+arg_8], rbx
0x140008715  mov     [rsp+arg_10], rbp
0x14000871a  push    rsi
0x14000871b  push    rdi
0x14000871c  push    r12
0x14000871e  push    r14
0x140008720  push    r15
0x140008722  sub     rsp, 260h
0x140008729  mov     rax, cs:__security_cookie
0x140008730  xor     rax, rsp
0x140008733  mov     [rsp+288h+var_38], rax
0x14000873b  mov     rdi, rcx
0x14000873e  mov     ebx, 208h
0x140008743  mov     r8d, ebx; Size
0x140008746  lea     rcx, [rsp+288h+Str]; void *
0x14000874b  xor     edx, edx; Val
0x14000874d  xor     ebp, ebp
0x14000874f  call    memset_0
0x140008754  mov     ecx, ebx; Size
0x140008756  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000875b  mov     rsi, rax
0x14000875e  test    rax, rax
0x140008761  jnz     loc_140008807
0x140008767  mov     ebx, 8007000Eh
0x14000876c  lea     r15, aPszfullpath; "pszFullPath"
0x140008773  lea     r12, aCpr; "CPR"
0x14000877a  lea     r14d, [rbp+61h]
0x14000877e  lea     rsi, aAppendfilename; "AppendFileNameToModulePath"
0x140008785  mov     [rsp+288h+var_260], ebx; int
0x140008789  lea     rdi, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140008790  mov     [rsp+288h+var_268], r15; unsigned __int16 *
0x140008795  mov     r8, rsi; unsigned __int16 *
0x140008798  mov     rcx, rdi; unsigned __int16 *
0x14000879b  mov     r9, r12; unsigned __int16 *
0x14000879e  mov     edx, r14d; unsigned int
0x1400087a1  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400087a6  call    cs:__imp_IsDebuggerPresent
0x1400087ac  test    eax, eax
0x1400087ae  jz      short loc_1400087DF
0x1400087b0  mov     [rsp+288h+var_250], ebx
0x1400087b4  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400087bb  mov     [rsp+288h+var_258], r15
0x1400087c0  mov     r9d, r14d
0x1400087c3  mov     qword ptr [rsp+288h+var_260], r12
0x1400087c8  mov     r8, rdi
0x1400087cb  mov     ecx, 2; unsigned __int8
0x1400087d0  mov     [rsp+288h+var_268], rsi
0x1400087d5  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400087da  jmp     loc_140008917
0x1400087df  mov     dword ptr [rsp+288h+var_258], ebx
0x1400087e3  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400087ea  mov     qword ptr [rsp+288h+var_260], r15
0x1400087ef  mov     r9, rsi
0x1400087f2  mov     r8d, r14d
0x1400087f5  mov     [rsp+288h+var_268], r12
0x1400087fa  mov     rdx, rdi
0x1400087fd  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140008802  jmp     loc_140008917
0x140008807  lea     rcx, [rsp+288h+Str]; Str
0x14000880c  call    ?GetModulePath@@YAJPEAGK@Z; GetModulePath(ushort *,ulong)
0x140008811  mov     ebx, eax
0x140008813  test    eax, eax
0x140008815  js      loc_140008917
0x14000881b  lea     r8, [rsp+288h+Str]; unsigned __int16 *
0x140008820  mov     rcx, rsi; unsigned __int16 *
0x140008823  call    ?PathCchCombineEx@@YAJPEAG_KPEBG2K@Z; PathCchCombineEx(ushort *,unsigned __int64,ushort const *,ushort const *,ulong)
0x140008828  mov     ebx, eax
0x14000882a  test    eax, eax
0x14000882c  jns     short loc_140008847
0x14000882e  lea     r15, aHr; "hr"
0x140008835  mov     r14d, 67h ; 'g'
0x14000883b  lea     r12, aChra; "CHRA"
0x140008842  jmp     loc_14000877E
0x140008847  xor     edx, edx; hFile
0x140008849  mov     rcx, rsi; lpLibFileName
0x14000884c  lea     r8d, [rdx+2]; dwFlags
0x140008850  call    cs:__imp_LoadLibraryExW
0x140008856  test    rax, rax
0x140008859  jnz     loc_140008911
0x14000885f  call    cs:__imp_GetLastError
0x140008865  mov     ebx, eax
0x140008867  test    eax, eax
0x140008869  jle     short loc_140008874
0x14000886b  movzx   ebx, ax
0x14000886e  or      ebx, 80070000h
0x140008874  mov     eax, 80004005h
0x140008879  lea     r12, aCbraex; "CBRAEx"
0x140008880  test    ebx, ebx
0x140008882  lea     r14, aLoadresourcedl; "LoadResourceDLL"
0x140008889  mov     ebp, 81h
0x14000888e  lea     rdi, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140008895  cmovns  ebx, eax
0x140008898  lea     r15, aHinst; "hInst"
0x14000889f  mov     [rsp+288h+var_260], ebx; int
0x1400088a3  mov     r9, r12; unsigned __int16 *
0x1400088a6  mov     r8, r14; unsigned __int16 *
0x1400088a9  mov     [rsp+288h+var_268], r15; unsigned __int16 *
0x1400088ae  mov     edx, ebp; unsigned int
0x1400088b0  mov     rcx, rdi; unsigned __int16 *
0x1400088b3  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400088b8  call    cs:__imp_IsDebuggerPresent
0x1400088be  test    eax, eax
0x1400088c0  jz      short loc_1400088EC
0x1400088c2  mov     [rsp+288h+var_250], ebx
0x1400088c6  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400088cd  mov     [rsp+288h+var_258], r15
0x1400088d2  lea     ecx, [rbp-7Fh]; unsigned __int8
0x1400088d5  mov     qword ptr [rsp+288h+var_260], r12
0x1400088da  mov     r9d, ebp
0x1400088dd  mov     r8, rdi
0x1400088e0  mov     [rsp+288h+var_268], r14
0x1400088e5  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400088ea  jmp     short loc_140008914
0x1400088ec  mov     dword ptr [rsp+288h+var_258], ebx
0x1400088f0  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400088f7  mov     qword ptr [rsp+288h+var_260], r15
0x1400088fc  mov     r9, r14
0x1400088ff  mov     r8d, ebp
0x140008902  mov     [rsp+288h+var_268], r12
0x140008907  mov     rdx, rdi
0x14000890a  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14000890f  jmp     short loc_140008914
0x140008911  mov     [rdi], rax
0x140008914  mov     rbp, rsi
0x140008917  mov     rcx, rbp; Block
0x14000891a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000891f  mov     eax, ebx
0x140008921  mov     rcx, [rsp+288h+var_38]
0x140008929  xor     rcx, rsp; StackCookie
0x14000892c  call    __security_check_cookie
0x140008931  lea     r11, [rsp+288h+var_28]
0x140008939  mov     rbx, [r11+38h]
0x14000893d  mov     rbp, [r11+40h]
0x140008941  mov     rsp, r11
0x140008944  pop     r15
0x140008946  pop     r14
0x140008948  pop     r12
0x14000894a  pop     rdi
0x14000894b  pop     rsi
0x14000894c  retn
```
