# AMovieSetupUnregisterServer

- ea: `0x1800029c8`
- end: `0x180002a4a`
- name: `AMovieSetupUnregisterServer`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800023c4`

## callees

- `0x180001460`
- `0x180002330`
- `0x180002a50`

## import_xrefs

- `ole32!StringFromGUID2` at `0x1800029fa`
- `ole32!StringFromGUID2` at `0x1800029fa`

## string_xrefs

- `0x180002a0a`: `CLSID\%ls`

## pseudocode

```c
LSTATUS __fastcall AMovieSetupUnregisterServer(GUID *a1)
{
  GUID rguid; // [rsp+20h] [rbp-288h] BYREF
  OLECHAR sz[40]; // [rsp+30h] [rbp-278h] BYREF
  wchar_t Buffer[264]; // [rsp+80h] [rbp-228h] BYREF

  rguid = *a1;
  StringFromGUID2(&rguid, sz, 39);
  StringCchPrintfW(Buffer, 0x104u, L"CLSID\\%ls", sz);
  return EliminateSubKey(HKEY_CLASSES_ROOT, Buffer);
}

```

## disassembly

```asm
0x1800029c8  sub     rsp, 2A8h
0x1800029cf  mov     rax, cs:__security_cookie
0x1800029d6  xor     rax, rsp
0x1800029d9  mov     [rsp+2A8h+var_18], rax
0x1800029e1  movups  xmm0, xmmword ptr [rcx]
0x1800029e4  mov     r8d, 27h ; '''; cchMax
0x1800029ea  lea     rdx, [rsp+2A8h+sz]; lpsz
0x1800029ef  lea     rcx, [rsp+2A8h+rguid]; rguid
0x1800029f4  movdqu  xmmword ptr [rsp+2A8h+rguid.Data1], xmm0
0x1800029fa  call    cs:__imp_StringFromGUID2
0x180002a00  lea     r9, [rsp+2A8h+sz]
0x180002a05  mov     edx, 104h; unsigned __int64
0x180002a0a  lea     r8, aClsidLs; "CLSID\\%ls"
0x180002a11  lea     rcx, [rsp+2A8h+Buffer]; Buffer
0x180002a19  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002a1e  lea     rdx, [rsp+2A8h+Buffer]; lpSubKey
0x180002a26  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180002a2d  call    EliminateSubKey
0x180002a32  mov     rcx, [rsp+2A8h+var_18]
0x180002a3a  xor     rcx, rsp; StackCookie
0x180002a3d  call    __security_check_cookie
0x180002a42  add     rsp, 2A8h
0x180002a49  retn
```
