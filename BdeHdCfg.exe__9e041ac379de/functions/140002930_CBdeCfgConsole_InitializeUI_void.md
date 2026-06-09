# CBdeCfgConsole::InitializeUI(void)

- ea: `0x140002930`
- end: `0x1400029bc`
- name: `?InitializeUI@CBdeCfgConsole@@QEAAJXZ`
- size: `140`
- prototype: `__int64 __fastcall(CBdeCfgConsole *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140001bf4`

## callees

- `0x1400016f3`
- `0x140002930`
- `0x140003f84`
- `0x140004460`

## import_xrefs

- `KERNEL32!GetConsoleOutputCP` at `0x14000295e`
- `KERNEL32!GetConsoleOutputCP` at `0x14000295e`
- `KERNEL32!SetThreadPreferredUILanguages` at `0x14000299a`
- `KERNEL32!SetThreadPreferredUILanguages` at `0x14000299a`
- `msvcrt!_wsetlocale` at `0x14000298a`
- `msvcrt!_wsetlocale` at `0x14000298a`

## pseudocode

```c
__int64 __fastcall CBdeCfgConsole::InitializeUI(CBdeCfgConsole *this)
{
  UINT ConsoleOutputCP; // eax
  int v2; // ebx
  wchar_t Locale[264]; // [rsp+20h] [rbp-228h] BYREF

  memset_0(Locale, 0, 0x208u);
  ConsoleOutputCP = GetConsoleOutputCP();
  v2 = StringCchPrintfW(Locale, 0x104u, L".%d", ConsoleOutputCP);
  if ( v2 >= 0 )
  {
    _wsetlocale(0, Locale);
    SetThreadPreferredUILanguages(0x100u, 0, 0);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140002930  push    rbx
0x140002932  sub     rsp, 240h
0x140002939  mov     rax, cs:__security_cookie
0x140002940  xor     rax, rsp
0x140002943  mov     [rsp+248h+var_18], rax
0x14000294b  xor     edx, edx; Val
0x14000294d  mov     r8d, 208h; Size
0x140002953  lea     rcx, [rsp+248h+Locale]; void *
0x140002958  call    memset_0
0x14000295d  nop
0x14000295e  call    cs:__imp_GetConsoleOutputCP
0x140002964  mov     r9d, eax
0x140002967  lea     r8, aD; ".%d"
0x14000296e  mov     edx, 104h; unsigned __int64
0x140002973  lea     rcx, [rsp+248h+Locale]; unsigned __int16 *
0x140002978  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000297d  mov     ebx, eax
0x14000297f  test    eax, eax
0x140002981  js      short loc_1400029A1
0x140002983  lea     rdx, [rsp+248h+Locale]; Locale
0x140002988  xor     ecx, ecx; Category
0x14000298a  call    cs:__imp__wsetlocale
0x140002990  xor     r8d, r8d; pulNumLanguages
0x140002993  xor     edx, edx; pwszLanguagesBuffer
0x140002995  mov     ecx, 100h; dwFlags
0x14000299a  call    cs:__imp_SetThreadPreferredUILanguages
0x1400029a0  nop
0x1400029a1  mov     eax, ebx
0x1400029a3  mov     rcx, [rsp+248h+var_18]
0x1400029ab  xor     rcx, rsp; StackCookie
0x1400029ae  call    __security_check_cookie
0x1400029b3  add     rsp, 240h
0x1400029ba  pop     rbx
0x1400029bb  retn
0x140004604  push    rbp
0x140004606  sub     rsp, 20h
0x14000460a  mov     rbp, rdx
0x14000460d  add     rsp, 20h
0x140004611  pop     rbp
0x140004612  retn
```
