# EnsureACILCanReadFile(ushort const *,ushort const *)

- ea: `0x4076da`
- end: `0x407777`
- name: `?EnsureACILCanReadFile@@YGJPBG0@Z`
- size: `157`
- prototype: `int __fastcall(int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x403ffd`

## callees

- `0x402df9`
- `0x4076da`
- `0x40cb60`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x40774b`
- `KERNEL32!CloseHandle` at `0x40774b`
- `KERNEL32!CreateFileW` at `0x40772a`
- `KERNEL32!CreateFileW` at `0x40772a`
- `KERNEL32!GetLastError` at `0x407753`
- `KERNEL32!GetLastError` at `0x407753`
- `iertutil!__imp_?SetWindowsHandleAccess@@YGJPAXKK@Z` at `0x407742`
- `iertutil!__imp_?SetWindowsHandleAccess@@YGJPAXKK@Z` at `0x407742`

## pseudocode

```c
int __fastcall EnsureACILCanReadFile(int a1, int a2)
{
  signed int v2; // esi
  HANDLE FileW; // eax
  void *v4; // edi
  signed int LastError; // eax
  WCHAR FileName[260]; // [esp+4h] [ebp-20Ch] BYREF

  v2 = StringCchPrintfW(FileName, 0x104u, (wchar_t *)L"%s\\%s", a1, a2);
  if ( v2 >= 0 )
  {
    FileW = CreateFileW(FileName, 0x1F0000u, 0, 0, 3u, 0x2000000u, 0);
    v4 = FileW;
    if ( FileW == (HANDLE)-1 )
    {
      LastError = GetLastError();
      v2 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        return LastError;
    }
    else
    {
      v2 = SetWindowsHandleAccess(FileW, 0x1240u, 0x1200A9u);
      CloseHandle(v4);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x4076da  mov     edi, edi
0x4076dc  push    ebp
0x4076dd  mov     ebp, esp
0x4076df  sub     esp, 20Ch
0x4076e5  mov     eax, ___security_cookie
0x4076ea  xor     eax, ebp
0x4076ec  mov     [ebp+var_4], eax
0x4076ef  push    esi
0x4076f0  push    edx
0x4076f1  push    ecx
0x4076f2  push    offset aSS; "%s\\%s"
0x4076f7  lea     eax, [ebp+FileName]
0x4076fd  push    104h; unsigned int
0x407702  push    eax; Buffer
0x407703  call    ?StringCchPrintfW@@YAJPAGIPBGZZ; StringCchPrintfW(ushort *,uint,ushort const *,...)
0x407708  mov     esi, eax
0x40770a  add     esp, 14h
0x40770d  test    esi, esi
0x40770f  js      short loc_407768
0x407711  push    edi
0x407712  xor     eax, eax
0x407714  push    eax; hTemplateFile
0x407715  push    2000000h; dwFlagsAndAttributes
0x40771a  push    3; dwCreationDisposition
0x40771c  push    eax; lpSecurityAttributes
0x40771d  push    eax; dwShareMode
0x40771e  push    1F0000h; dwDesiredAccess
0x407723  lea     eax, [ebp+FileName]
0x407729  push    eax; lpFileName
0x40772a  call    ds:__imp__CreateFileW@28; CreateFileW(x,x,x,x,x,x,x)
0x407730  mov     edi, eax
0x407732  cmp     edi, 0FFFFFFFFh
0x407735  jz      short loc_407753
0x407737  push    1200A9h
0x40773c  push    1240h
0x407741  push    edi
0x407742  call    ds:__imp_?SetWindowsHandleAccess@@YGJPAXKK@Z; SetWindowsHandleAccess(void *,ulong,ulong)
0x407748  push    edi; hObject
0x407749  mov     esi, eax
0x40774b  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x407751  jmp     short loc_407767
0x407753  call    ds:__imp__GetLastError@0; GetLastError()
0x407759  movzx   esi, ax
0x40775c  or      esi, 80070000h
0x407762  test    eax, eax
0x407764  cmovle  esi, eax
0x407767  pop     edi
0x407768  mov     ecx, [ebp+var_4]
0x40776b  mov     eax, esi
0x40776d  xor     ecx, ebp; StackCookie
0x40776f  pop     esi
0x407770  call    @__security_check_cookie@4; __security_check_cookie(x)
0x407775  leave
0x407776  retn
```
