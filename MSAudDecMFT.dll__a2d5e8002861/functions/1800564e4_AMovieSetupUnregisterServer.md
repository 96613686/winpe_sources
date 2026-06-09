# AMovieSetupUnregisterServer

- ea: `0x1800564e4`
- end: `0x18005656d`
- name: `AMovieSetupUnregisterServer`
- size: `137`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800566d8`

## callees

- `0x18004d320`
- `0x180056188`
- `0x180056574`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180056516`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180056516`

## string_xrefs

- `0x18005652c`: `CLSID\%ls`

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
0x1800564e4  sub     rsp, 2A8h
0x1800564eb  mov     rax, cs:__security_cookie
0x1800564f2  xor     rax, rsp
0x1800564f5  mov     [rsp+2A8h+var_18], rax
0x1800564fd  movups  xmm0, xmmword ptr [rcx]
0x180056500  mov     r8d, 27h ; '''; cchMax
0x180056506  lea     rdx, [rsp+2A8h+sz]; lpsz
0x18005650b  lea     rcx, [rsp+2A8h+rguid]; rguid
0x180056510  movdqu  xmmword ptr [rsp+2A8h+rguid.Data1], xmm0
0x180056516  call    cs:__imp_StringFromGUID2
0x18005651d  nop     dword ptr [rax+rax+00h]
0x180056522  lea     r9, [rsp+2A8h+sz]
0x180056527  mov     edx, 104h; unsigned __int64
0x18005652c  lea     r8, aClsidLs; "CLSID\\%ls"
0x180056533  lea     rcx, [rsp+2A8h+Buffer]; Buffer
0x18005653b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180056540  lea     rdx, [rsp+2A8h+Buffer]
0x180056548  mov     rcx, 0FFFFFFFF80000000h
0x18005654f  call    EliminateSubKey
0x180056554  mov     rcx, [rsp+2A8h+var_18]
0x18005655c  xor     rcx, rsp; StackCookie
0x18005655f  call    __security_check_cookie
0x180056564  add     rsp, 2A8h
0x18005656b  retn
```
