# LoadMainText(ushort const *,ushort *,ulong)

- ea: `0x18000425c`
- end: `0x180004345`
- name: `?LoadMainText@@YAJPEBGPEAGK@Z`
- size: `233`
- prototype: `int(const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800043d8`

## callees

- `0x180002590`
- `0x18000425c`
- `0x18000434c`
- `0x180007040`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800042c7`
- `KERNEL32!GetLastError` at `0x1800042c7`
- `USER32!LoadStringW` at `0x1800042bd`
- `USER32!LoadStringW` at `0x1800042bd`

## string_xrefs

- `0x180004316`: `MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n`

## pseudocode

```c
__int64 __fastcall LoadMainText(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  int v4; // eax
  int v5; // r9d
  unsigned int v6; // ebx
  signed int LastError; // eax
  WCHAR Buffer[1024]; // [rsp+30h] [rbp-818h] BYREF

  if ( !a1 )
  {
    v4 = -2147024809;
    v5 = 39;
    v6 = -2147024809;
LABEL_11:
    DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "LoadMainText", v5, v4);
    return v6;
  }
  if ( !a2 )
  {
    v4 = -2147024809;
    v5 = 40;
    v6 = -2147024809;
    goto LABEL_11;
  }
  if ( LoadStringW(g_hInstance, 0x3F3u, Buffer, 1024) )
  {
    v4 = StringCchPrintfW(a2, 0x800u, Buffer, a1);
    v6 = v4;
    if ( v4 < 0 )
    {
      v5 = 55;
      goto LABEL_11;
    }
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "LoadMainText", 48, v6);
  }
  return v6;
}

```

## disassembly

```asm
0x18000425c  mov     [rsp+arg_10], rbx
0x180004261  push    rdi
0x180004262  sub     rsp, 840h
0x180004269  mov     rax, cs:__security_cookie
0x180004270  xor     rax, rsp
0x180004273  mov     [rsp+848h+var_18], rax
0x18000427b  mov     rbx, rdx
0x18000427e  mov     rdi, rcx
0x180004281  test    rcx, rcx
0x180004284  jnz     short loc_180004293
0x180004286  mov     eax, 80070057h
0x18000428b  lea     r9d, [rcx+27h]
0x18000428f  mov     ebx, eax
0x180004291  jmp     short loc_180004309
0x180004293  test    rbx, rbx
0x180004296  jnz     short loc_1800042A7
0x180004298  mov     eax, 80070057h
0x18000429d  mov     r9d, 28h ; '('
0x1800042a3  mov     ebx, eax
0x1800042a5  jmp     short loc_180004309
0x1800042a7  mov     rcx, cs:g_hInstance; hInstance
0x1800042ae  lea     r8, [rsp+848h+Buffer]; lpBuffer
0x1800042b3  mov     r9d, 400h; cchBufferMax
0x1800042b9  lea     edx, [r9-0Dh]; uID
0x1800042bd  call    cs:__imp_LoadStringW
0x1800042c3  test    eax, eax
0x1800042c5  jnz     short loc_1800042E8
0x1800042c7  call    cs:__imp_GetLastError
0x1800042cd  mov     ebx, eax
0x1800042cf  test    eax, eax
0x1800042d1  jle     short loc_1800042DC
0x1800042d3  movzx   ebx, ax
0x1800042d6  or      ebx, 80070000h
0x1800042dc  mov     [rsp+848h+var_828], ebx
0x1800042e0  mov     r9d, 30h ; '0'
0x1800042e6  jmp     short loc_18000430D
0x1800042e8  mov     r9, rdi
0x1800042eb  lea     r8, [rsp+848h+Buffer]; unsigned __int16 *
0x1800042f0  mov     edx, 800h; unsigned __int64
0x1800042f5  mov     rcx, rbx; unsigned __int16 *
0x1800042f8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800042fd  mov     ebx, eax
0x1800042ff  test    eax, eax
0x180004301  jns     short loc_180004322
0x180004303  mov     r9d, 37h ; '7'
0x180004309  mov     [rsp+848h+var_828], eax
0x18000430d  lea     r8, aLoadmaintext; "LoadMainText"
0x180004314  xor     ecx, ecx; Level
0x180004316  lea     rdx, aMsiCofireError; "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n"
0x18000431d  call    ?DebugPrint@@YAXKPEBDZZ; DebugPrint(ulong,char const *,...)
0x180004322  mov     eax, ebx
0x180004324  mov     rcx, [rsp+848h+var_18]
0x18000432c  xor     rcx, rsp; StackCookie
0x18000432f  call    __security_check_cookie
0x180004334  mov     rbx, [rsp+848h+arg_10]
0x18000433c  add     rsp, 840h
0x180004343  pop     rdi
0x180004344  retn
```
