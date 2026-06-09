# GetY2KCompliantDate

- ea: `0x18002c160`
- end: `0x18002c1d8`
- name: `GetY2KCompliantDate`
- size: `120`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800254e0`

## callees

- `0x18000abe4`
- `0x18002c160`

## import_xrefs

- `KERNEL32!GetDateFormatW` at `0x18002c1c0`
- `KERNEL32!GetDateFormatW` at `0x18002c1c0`

## pseudocode

```c
int __fastcall GetY2KCompliantDate(__int64 a1, __int64 a2, const SYSTEMTIME *a3, WCHAR *a4)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_04fb59550d79390d980a26525e0212b0_Traceguids);
  }
  return GetDateFormatW(0x400u, 0x40u, a3, 0, a4, 260);
}

```

## disassembly

```asm
0x18002c160  mov     [rsp+arg_0], rbx
0x18002c165  push    rdi
0x18002c166  sub     rsp, 30h
0x18002c16a  mov     rbx, r9
0x18002c16d  mov     rdi, r8
0x18002c170  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c177  lea     rax, WPP_GLOBAL_Control
0x18002c17e  cmp     rcx, rax
0x18002c181  jz      short loc_18002C1A4
0x18002c183  test    byte ptr [rcx+1Ch], 2
0x18002c187  jz      short loc_18002C1A4
0x18002c189  cmp     byte ptr [rcx+19h], 5
0x18002c18d  jb      short loc_18002C1A4
0x18002c18f  mov     rcx, [rcx+10h]
0x18002c193  lea     r8, WPP_04fb59550d79390d980a26525e0212b0_Traceguids
0x18002c19a  mov     edx, 1Ch
0x18002c19f  call    WPP_SF_
0x18002c1a4  xor     r9d, r9d; lpFormat
0x18002c1a7  mov     [rsp+38h+cchDate], 104h; cchDate
0x18002c1af  mov     r8, rdi; lpDate
0x18002c1b2  mov     [rsp+38h+lpDateStr], rbx; lpDateStr
0x18002c1b7  mov     ecx, 400h; Locale
0x18002c1bc  lea     edx, [r9+40h]; dwFlags
0x18002c1c0  call    cs:__imp_GetDateFormatW
0x18002c1c7  nop     dword ptr [rax+rax+00h]
0x18002c1cc  mov     rbx, [rsp+38h+arg_0]
0x18002c1d1  add     rsp, 30h
0x18002c1d5  pop     rdi
0x18002c1d6  retn
```
