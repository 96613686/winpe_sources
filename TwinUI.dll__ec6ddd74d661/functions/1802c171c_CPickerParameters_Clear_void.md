# CPickerParameters::Clear(void)

- ea: `0x1802c171c`
- end: `0x1802c1884`
- name: `?Clear@CPickerParameters@@QEAAXXZ`
- size: `360`
- prototype: `void __fastcall(CPickerParameters *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1801382ec`
- `0x1802c0958`
- `0x1802c0c44`

## callees

- `0x180167ffc`
- `0x1802c171c`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802c179a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802c17b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802c17d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802c17f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802c1812`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802c182d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802c1848`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802c1866`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802c179a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802c17b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802c17d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802c17f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802c1812`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802c182d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802c1848`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802c1866`

## pseudocode

```c
void __fastcall CPickerParameters::Clear(CPickerParameters *this)
{
  __int64 v2; // rcx
  HSTRING v3; // rcx
  HSTRING v4; // rcx
  HSTRING v5; // rcx
  HSTRING v6; // rcx
  HSTRING v7; // rcx
  HSTRING v8; // rcx
  HSTRING v9; // rcx

  SafeRelease<IShellItemArray>((char *)this + 32);
  SafeRelease<IShellItemArray>((char *)this + 40);
  SafeRelease<IShellItemArray>((char *)this + 48);
  SafeRelease<IShellItemArray>((char *)this + 56);
  SafeRelease<IShellItemArray>((char *)this + 64);
  SafeRelease<IShellItemArray>((char *)this + 72);
  SafeRelease<IShellItemArray>((char *)this + 80);
  SafeRelease<IShellItemArray>((char *)this + 88);
  v2 = *((_QWORD *)this + 13);
  *((_QWORD *)this + 13) = 0;
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  SafeRelease<IShellItemArray>((char *)this + 96);
  WindowsDeleteString(*((HSTRING *)this + 18));
  v3 = (HSTRING)*((_QWORD *)this + 19);
  *((_QWORD *)this + 18) = 0;
  WindowsDeleteString(v3);
  v4 = (HSTRING)*((_QWORD *)this + 20);
  *((_QWORD *)this + 19) = 0;
  WindowsDeleteString(v4);
  v5 = (HSTRING)*((_QWORD *)this + 21);
  *((_QWORD *)this + 20) = 0;
  WindowsDeleteString(v5);
  v6 = (HSTRING)*((_QWORD *)this + 22);
  *((_QWORD *)this + 21) = 0;
  WindowsDeleteString(v6);
  v7 = (HSTRING)*((_QWORD *)this + 15);
  *((_QWORD *)this + 22) = 0;
  WindowsDeleteString(v7);
  v8 = (HSTRING)*((_QWORD *)this + 16);
  *((_QWORD *)this + 15) = 0;
  WindowsDeleteString(v8);
  v9 = (HSTRING)*((_QWORD *)this + 17);
  *((_QWORD *)this + 16) = 0;
  WindowsDeleteString(v9);
  *((_QWORD *)this + 17) = 0;
}

```

## disassembly

```asm
0x1802c171c  push    rbx
0x1802c171e  sub     rsp, 20h
0x1802c1722  mov     rbx, rcx
0x1802c1725  add     rcx, 20h ; ' '
0x1802c1729  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x1802c172e  lea     rcx, [rbx+28h]
0x1802c1732  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x1802c1737  lea     rcx, [rbx+30h]
0x1802c173b  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x1802c1740  lea     rcx, [rbx+38h]
0x1802c1744  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x1802c1749  lea     rcx, [rbx+40h]
0x1802c174d  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x1802c1752  lea     rcx, [rbx+48h]
0x1802c1756  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x1802c175b  lea     rcx, [rbx+50h]
0x1802c175f  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x1802c1764  lea     rcx, [rbx+58h]
0x1802c1768  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x1802c176d  mov     rcx, [rbx+68h]
0x1802c1771  mov     qword ptr [rbx+68h], 0
0x1802c1779  test    rcx, rcx
0x1802c177c  jz      short loc_1802C178A
0x1802c177e  mov     rax, [rcx]
0x1802c1781  mov     rax, [rax+10h]
0x1802c1785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c178a  lea     rcx, [rbx+60h]
0x1802c178e  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x1802c1793  mov     rcx, [rbx+90h]; string
0x1802c179a  call    cs:__imp_WindowsDeleteString
0x1802c17a1  nop     dword ptr [rax+rax+00h]
0x1802c17a6  mov     rcx, [rbx+98h]; string
0x1802c17ad  mov     qword ptr [rbx+90h], 0
0x1802c17b8  call    cs:__imp_WindowsDeleteString
0x1802c17bf  nop     dword ptr [rax+rax+00h]
0x1802c17c4  mov     rcx, [rbx+0A0h]; string
0x1802c17cb  mov     qword ptr [rbx+98h], 0
0x1802c17d6  call    cs:__imp_WindowsDeleteString
0x1802c17dd  nop     dword ptr [rax+rax+00h]
0x1802c17e2  mov     rcx, [rbx+0A8h]; string
0x1802c17e9  mov     qword ptr [rbx+0A0h], 0
0x1802c17f4  call    cs:__imp_WindowsDeleteString
0x1802c17fb  nop     dword ptr [rax+rax+00h]
0x1802c1800  mov     rcx, [rbx+0B0h]; string
0x1802c1807  mov     qword ptr [rbx+0A8h], 0
0x1802c1812  call    cs:__imp_WindowsDeleteString
0x1802c1819  nop     dword ptr [rax+rax+00h]
0x1802c181e  mov     rcx, [rbx+78h]; string
0x1802c1822  mov     qword ptr [rbx+0B0h], 0
0x1802c182d  call    cs:__imp_WindowsDeleteString
0x1802c1834  nop     dword ptr [rax+rax+00h]
0x1802c1839  mov     rcx, [rbx+80h]; string
0x1802c1840  mov     qword ptr [rbx+78h], 0
0x1802c1848  call    cs:__imp_WindowsDeleteString
0x1802c184f  nop     dword ptr [rax+rax+00h]
0x1802c1854  mov     rcx, [rbx+88h]; string
0x1802c185b  mov     qword ptr [rbx+80h], 0
0x1802c1866  call    cs:__imp_WindowsDeleteString
0x1802c186d  nop     dword ptr [rax+rax+00h]
0x1802c1872  mov     qword ptr [rbx+88h], 0
0x1802c187d  add     rsp, 20h
0x1802c1881  pop     rbx
0x1802c1882  retn
```
