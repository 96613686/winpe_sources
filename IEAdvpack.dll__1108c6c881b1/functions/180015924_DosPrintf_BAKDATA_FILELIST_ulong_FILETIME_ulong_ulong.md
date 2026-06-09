# DosPrintf(_BAKDATA *,_FILELIST *,ulong,_FILETIME,ulong,ulong)

- ea: `0x180015924`
- end: `0x1800159d9`
- name: `?DosPrintf@@YAHPEAU_BAKDATA@@PEAU_FILELIST@@KU_FILETIME@@KK@Z`
- size: `181`
- prototype: `__int64 __fastcall(const WCHAR *, LPCWSTR *, int, struct _FILETIME, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800156b8`

## callees

- `0x1800035c8`
- `0x180015924`
- `0x18001b980`

## import_xrefs

- `KERNEL32!WritePrivateProfileStringW` at `0x1800159b6`
- `KERNEL32!WritePrivateProfileStringW` at `0x1800159b6`

## pseudocode

```c
__int64 __fastcall DosPrintf(
        const WCHAR *a1,
        LPCWSTR *a2,
        int a3,
        struct _FILETIME a4,
        unsigned int a5,
        unsigned int a6)
{
  __int64 v7; // rbx
  DWORD dwLowDateTime; // [rsp+28h] [rbp-850h]
  DWORD dwHighDateTime; // [rsp+30h] [rbp-848h]
  int v15; // [rsp+48h] [rbp-830h]
  WCHAR String[1024]; // [rsp+50h] [rbp-828h] BYREF

  v7 = -1;
  v15 = -1;
  dwHighDateTime = a4.dwHighDateTime;
  dwLowDateTime = a4.dwLowDateTime;
  StringCchPrintfW(
    String,
    0x400u,
    L"%lx,%lx,%lx,%lx,%lx,%lx,%d",
    *((unsigned int *)a2 + 3),
    a3,
    dwLowDateTime,
    dwHighDateTime,
    a5,
    a6,
    v15);
  do
    ++v7;
  while ( String[v7] );
  WritePrivateProfileStringW(L"backup", *a2, String, a1 + 6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180015924  push    rbx
0x180015926  push    rsi
0x180015927  push    rdi
0x180015928  sub     rsp, 860h
0x18001592f  mov     rax, cs:__security_cookie
0x180015936  xor     rax, rsp
0x180015939  mov     [rsp+878h+var_28], rax
0x180015941  mov     eax, [rsp+878h+arg_28]
0x180015948  mov     rdi, rdx
0x18001594b  mov     rdx, r9
0x18001594e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180015952  mov     [rsp+878h+var_830], ebx
0x180015956  mov     rsi, rcx
0x180015959  mov     [rsp+878h+var_838], eax
0x18001595d  lea     rcx, [rsp+878h+String]; unsigned __int16 *
0x180015962  mov     eax, [rsp+878h+arg_20]
0x180015969  mov     [rsp+878h+var_840], eax
0x18001596d  shr     rdx, 20h
0x180015971  mov     [rsp+878h+var_848], edx
0x180015975  mov     edx, 400h; unsigned __int64
0x18001597a  mov     [rsp+878h+var_850], r9d
0x18001597f  mov     r9d, [rdi+0Ch]
0x180015983  mov     [rsp+878h+var_858], r8d
0x180015988  lea     r8, aLxLxLxLxLxLxD; "%lx,%lx,%lx,%lx,%lx,%lx,%d"
0x18001598f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180015994  lea     rax, [rsp+878h+String]
0x180015999  inc     rbx
0x18001599c  cmp     word ptr [rax+rbx*2], 0
0x1800159a1  jnz     short loc_180015999
0x1800159a3  mov     rdx, [rdi]; lpKeyName
0x1800159a6  lea     r9, [rsi+0Ch]; lpFileName
0x1800159aa  lea     r8, [rsp+878h+String]; lpString
0x1800159af  lea     rcx, c_szIE4SECTIONNAME; "backup"
0x1800159b6  call    cs:__imp_WritePrivateProfileStringW
0x1800159bc  mov     eax, ebx
0x1800159be  mov     rcx, [rsp+878h+var_28]
0x1800159c6  xor     rcx, rsp; StackCookie
0x1800159c9  call    __security_check_cookie
0x1800159ce  add     rsp, 860h
0x1800159d5  pop     rdi
0x1800159d6  pop     rsi
0x1800159d7  pop     rbx
0x1800159d8  retn
```
