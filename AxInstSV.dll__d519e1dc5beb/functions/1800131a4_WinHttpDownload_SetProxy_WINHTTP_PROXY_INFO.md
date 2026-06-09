# WinHttpDownload::SetProxy(_WINHTTP_PROXY_INFO *)

- ea: `0x1800131a4`
- end: `0x180013295`
- name: `?SetProxy@WinHttpDownload@@AEAAJPEAU_WINHTTP_PROXY_INFO@@@Z`
- size: `241`
- prototype: `int(WinHttpDownload *__hidden this, struct _WINHTTP_PROXY_INFO *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180012408`
- `0x180012c24`
- `0x1800130d4`

## callees

- `0x18000725c`
- `0x1800131a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013243`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013243`
- `WINHTTP!WinHttpSetOption` at `0x18001321a`
- `WINHTTP!WinHttpSetOption` at `0x180013235`
- `WINHTTP!WinHttpSetOption` at `0x18001321a`
- `WINHTTP!WinHttpSetOption` at `0x180013235`

## string_xrefs

- `0x1800131dc`: `Setting Proxy: %s | Bypass: %s | AccessType: %d`

## pseudocode

```c
__int64 __fastcall WinHttpDownload::SetProxy(WinHttpDownload *this, struct _WINHTTP_PROXY_INFO *a2)
{
  __int64 v4; // rdx
  const wchar_t *v5; // rax
  unsigned int v6; // ebx
  signed int LastError; // eax
  __int64 v9; // [rsp+28h] [rbp-20h]
  int v10; // [rsp+30h] [rbp-18h]

  if ( a2 && (v4 = *((_QWORD *)a2 + 1)) != 0 )
  {
    v5 = L"(none)";
    if ( *((_QWORD *)a2 + 2) )
      v5 = (const wchar_t *)*((_QWORD *)a2 + 2);
    v10 = *((_DWORD *)this + 22);
    AxISEvents::DebugMsg(
      (AxISEvents *)&qword_180021AD8,
      2u,
      4u,
      L"Setting Proxy: %s | Bypass: %s | AccessType: %d",
      v4,
      v5,
      v10);
    if ( WinHttpSetOption(*((HINTERNET *)this + 7), 0x26u, a2, 0x18u)
      && WinHttpSetOption(*((HINTERNET *)this + 9), 0x26u, a2, 0x18u) )
    {
      return 0;
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      LODWORD(v9) = v6;
      AxISEvents::DebugMsg(
        (AxISEvents *)&qword_180021AD8,
        2u,
        4u,
        L" WinHttpSetOption WINHTTP_OPTION_PROXY failed Proxy %s, Error 0x%x",
        *((_QWORD *)a2 + 1),
        v9);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v6;
}

```

## disassembly

```asm
0x1800131a4  mov     r11, rsp
0x1800131a7  mov     [r11+8], rbx
0x1800131ab  push    rdi
0x1800131ac  sub     rsp, 40h
0x1800131b0  mov     rdi, rdx
0x1800131b3  mov     rbx, rcx
0x1800131b6  test    rdx, rdx
0x1800131b9  jz      loc_180013283
0x1800131bf  mov     rdx, [rdx+8]
0x1800131c3  test    rdx, rdx
0x1800131c6  jz      loc_180013283
0x1800131cc  mov     r8d, [rcx+58h]
0x1800131d0  lea     rax, aNone; "(none)"
0x1800131d7  cmp     qword ptr [rdi+10h], 0
0x1800131dc  lea     r9, aSettingProxySB; "Setting Proxy: %s | Bypass: %s | Access"...
0x1800131e3  mov     [r11-18h], r8d
0x1800131e7  lea     rcx, qword_180021AD8; this
0x1800131ee  cmovnz  rax, [rdi+10h]
0x1800131f3  mov     [r11-20h], rax
0x1800131f7  mov     [r11-28h], rdx
0x1800131fb  mov     edx, 2; unsigned int
0x180013200  lea     r8d, [rdx+2]; unsigned __int8
0x180013204  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x180013209  mov     rcx, [rbx+38h]; hInternet
0x18001320d  mov     r9d, 18h; dwBufferLength
0x180013213  mov     r8, rdi; lpBuffer
0x180013216  lea     edx, [r9+0Eh]; dwOption
0x18001321a  call    cs:__imp_WinHttpSetOption
0x180013220  test    eax, eax
0x180013222  jz      short loc_180013243
0x180013224  mov     rcx, [rbx+48h]; hInternet
0x180013228  mov     r9d, 18h; dwBufferLength
0x18001322e  mov     r8, rdi; lpBuffer
0x180013231  lea     edx, [r9+0Eh]; dwOption
0x180013235  call    cs:__imp_WinHttpSetOption
0x18001323b  test    eax, eax
0x18001323d  jz      short loc_180013243
0x18001323f  xor     ebx, ebx
0x180013241  jmp     short loc_180013288
0x180013243  call    cs:__imp_GetLastError
0x180013249  mov     ebx, eax
0x18001324b  test    eax, eax
0x18001324d  jle     short loc_180013258
0x18001324f  movzx   ebx, ax
0x180013252  or      ebx, 80070000h
0x180013258  mov     rax, [rdi+8]
0x18001325c  lea     r9, aWinhttpsetopti_1; " WinHttpSetOption WINHTTP_OPTION_PROXY "...
0x180013263  mov     edx, 2; unsigned int
0x180013268  mov     dword ptr [rsp+48h+var_20], ebx
0x18001326c  lea     rcx, qword_180021AD8; this
0x180013273  mov     [rsp+48h+var_28], rax
0x180013278  lea     r8d, [rdx+2]; unsigned __int8
0x18001327c  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x180013281  jmp     short loc_180013288
0x180013283  mov     ebx, 80070057h
0x180013288  mov     eax, ebx
0x18001328a  mov     rbx, [rsp+48h+arg_0]
0x18001328f  add     rsp, 40h
0x180013293  pop     rdi
0x180013294  retn
```
