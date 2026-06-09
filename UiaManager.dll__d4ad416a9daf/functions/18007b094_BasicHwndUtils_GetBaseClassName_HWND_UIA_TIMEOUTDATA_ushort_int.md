# BasicHwndUtils::GetBaseClassName(HWND__ *,UIA_TIMEOUTDATA &,ushort *,int)

- ea: `0x18007b094`
- end: `0x18007b17d`
- name: `?GetBaseClassName@BasicHwndUtils@@SAJPEAUHWND__@@AEAUUIA_TIMEOUTDATA@@PEAGH@Z`
- size: `233`
- prototype: `__int64 __fastcall(HWND, struct UIA_TIMEOUTDATA *, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18007bdc4`

## callees

- `0x1800124a4`
- `0x180023d0c`
- `0x18002b7cc`
- `0x18007b094`
- `0x18007bb2c`
- `0x18007c42c`

## import_xrefs

- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RealGetWindowClassW` at `0x18007b142`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!RealGetWindowClassW` at `0x18007b142`

## string_xrefs

- `0x18007b158`: `onecore\windows\accessibletech\common\basichwndutils.cpp`
- `0x18007b151`: `GetRealWindowClass: Unable to get Real class name when attempting to create a Proxy`

## pseudocode

```c
int __fastcall BasicHwndUtils::GetBaseClassName(HWND a1, struct UIA_TIMEOUTDATA *a2, unsigned __int16 *a3)
{
  const char *v7; // [rsp+20h] [rbp-28h]
  __int64 v8[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a3 = 0;
  if ( !BasicUiaUtils::IsDesktop() )
    return 0;
  if ( !BasicHwndUtils::IsKnownBadWmGetObjectImpl(a1, a2) )
  {
    v8[0] = 0;
    if ( (int)BasicHwndUtils::UIASendMessageTimeout(a2, a1, 0x3Du, 0, -12, v8) >= 0
      && SLODWORD(v8[0]) >= 0x10000
      && (unsigned int)(LODWORD(v8[0]) - 0x10000) < 0x20 )
    {
      return StringCchCopyW(a3, 0x100u, (const unsigned __int16 *)(&IndexedClassNames)[SLODWORD(v8[0]) - 0x10000]);
    }
  }
  if ( RealGetWindowClassW(a1, a3, 0xFFu) )
    return 0;
  else
    return wil::details::in1diag3::Return_GetLastErrorMsg(
             retaddr,
             (void *)0x723,
             (unsigned int)"onecore\\windows\\accessibletech\\common\\basichwndutils.cpp",
             "GetRealWindowClass: Unable to get Real class name when attempting to create a Proxy",
             v7);
}

```

## disassembly

```asm
0x18007b094  mov     [rsp+arg_0], rbx
0x18007b099  mov     [rsp+arg_8], rsi
0x18007b09e  push    rdi
0x18007b09f  sub     rsp, 40h
0x18007b0a3  xor     eax, eax
0x18007b0a5  mov     rdi, r8
0x18007b0a8  mov     [r8], ax
0x18007b0ac  mov     rsi, rdx
0x18007b0af  mov     rbx, rcx
0x18007b0b2  call    ?IsDesktop@BasicUiaUtils@@SA_NXZ; BasicUiaUtils::IsDesktop(void)
0x18007b0b7  test    al, al
0x18007b0b9  jz      loc_18007B16B
0x18007b0bf  mov     rdx, rsi; struct UIA_TIMEOUTDATA *
0x18007b0c2  mov     rcx, rbx; HWND
0x18007b0c5  call    ?IsKnownBadWmGetObjectImpl@BasicHwndUtils@@SA_NPEAUHWND__@@AEBUUIA_TIMEOUTDATA@@@Z; BasicHwndUtils::IsKnownBadWmGetObjectImpl(HWND__ *,UIA_TIMEOUTDATA const &)
0x18007b0ca  test    al, al
0x18007b0cc  jnz     short loc_18007B136
0x18007b0ce  xor     r9d, r9d; unsigned __int64
0x18007b0d1  mov     [rsp+48h+var_18], 0
0x18007b0da  lea     rax, [rsp+48h+var_18]
0x18007b0df  mov     rdx, rbx; HWND
0x18007b0e2  mov     [rsp+48h+var_20], rax; __int64 *
0x18007b0e7  mov     rcx, rsi; struct UIA_TIMEOUTDATA *
0x18007b0ea  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFF4h; __int64
0x18007b0f3  lea     r8d, [r9+3Dh]; unsigned int
0x18007b0f7  call    ?UIASendMessageTimeout@BasicHwndUtils@@SAJAEBUUIA_TIMEOUTDATA@@PEAUHWND__@@I_K_JPEA_J@Z; BasicHwndUtils::UIASendMessageTimeout(UIA_TIMEOUTDATA const &,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x18007b0fc  test    eax, eax
0x18007b0fe  js      short loc_18007B136
0x18007b100  movsxd  rcx, dword ptr [rsp+48h+var_18]
0x18007b105  cmp     ecx, 10000h
0x18007b10b  jl      short loc_18007B136
0x18007b10d  lea     eax, [rcx-10000h]
0x18007b113  cmp     eax, 20h ; ' '
0x18007b116  jnb     short loc_18007B136
0x18007b118  lea     rax, ?IndexedClassNames@@3PAPEBGA; ushort const * near * IndexedClassNames
0x18007b11f  mov     edx, 100h; unsigned __int64
0x18007b124  mov     r8, [rax+rcx*8-80000h]; unsigned __int16 *
0x18007b12c  mov     rcx, rdi; unsigned __int16 *
0x18007b12f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007b134  jmp     short loc_18007B16D
0x18007b136  mov     r8d, 0FFh; cchClassNameMax
0x18007b13c  mov     rdx, rdi; ptszClassName
0x18007b13f  mov     rcx, rbx; hwnd
0x18007b142  call    cs:__imp_RealGetWindowClassW
0x18007b148  test    eax, eax
0x18007b14a  jnz     short loc_18007B16B
0x18007b14c  mov     rcx, [rsp+48h]; this
0x18007b151  lea     r9, aGetrealwindowc; "GetRealWindowClass: Unable to get Real "...
0x18007b158  lea     r8, aOnecoreWindows_10; "onecore\\windows\\accessibletech\\commo"...
0x18007b15f  mov     edx, 723h; void *
0x18007b164  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18007b169  jmp     short loc_18007B16D
0x18007b16b  xor     eax, eax
0x18007b16d  mov     rbx, [rsp+48h+arg_0]
0x18007b172  mov     rsi, [rsp+48h+arg_8]
0x18007b177  add     rsp, 40h
0x18007b17b  pop     rdi
0x18007b17c  retn
```
