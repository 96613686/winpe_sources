# CreateCommandLine(ushort const *,ushort const *,ushort const *,ushort const *,int,ushort * *)

- ea: `0x18000743c`
- end: `0x1800074d4`
- name: `?CreateCommandLine@@YAJPEBG000HPEAPEAG@Z`
- size: `152`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180007880`
- `0x180007a40`

## import_xrefs

- `DMCmnUtils!BigStrcat` at `0x1800074a5`
- `DMCmnUtils!BigStrcat` at `0x1800074a5`

## string_xrefs

- `0x180007486`: `DmNotificationBroker.exe`

## pseudocode

```c
__int64 __fastcall CreateCommandLine(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5,
        unsigned __int16 **a6)
{
  const wchar_t *v6; // rax
  unsigned __int16 *v7; // rdx
  __int64 result; // rax

  v6 = L"1";
  if ( !a5 )
    v6 = L"0";
  v7 = BigStrcat(
         0xDu,
         L"\"",
         L"DmNotificationBroker.exe",
         L"\" \"",
         a1,
         L"\" \"",
         a2,
         L"\" \"",
         a3,
         L"\" \"",
         a4,
         L"\" \"",
         v6,
         L"\"");
  result = v7 == 0 ? 0x80004005 : 0;
  *a6 = v7;
  return result;
}

```

## disassembly

```asm
0x18000743c  mov     r11, rsp
0x18000743f  sub     rsp, 78h
0x180007443  cmp     [rsp+78h+arg_20], 0
0x18000744b  lea     r10, a0; "0"
0x180007452  lea     rax, a1; "1"
0x180007459  cmovz   rax, r10
0x18000745d  lea     r10, asc_18000D950; "\""
0x180007464  mov     [r11-10h], r10
0x180007468  mov     [r11-18h], rax
0x18000746c  lea     rax, asc_18000D948; "\" \""
0x180007473  mov     [r11-20h], rax
0x180007477  mov     [r11-28h], r9
0x18000747b  mov     r9, rax
0x18000747e  mov     [r11-30h], rax
0x180007482  mov     [r11-38h], r8
0x180007486  lea     r8, aDmnotification; "DmNotificationBroker.exe"
0x18000748d  mov     [r11-40h], rax
0x180007491  mov     [r11-48h], rdx
0x180007495  mov     rdx, r10
0x180007498  mov     [r11-50h], rax
0x18000749c  mov     [r11-58h], rcx
0x1800074a0  mov     ecx, 0Dh
0x1800074a5  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x1800074ac  nop     dword ptr [rax+rax+00h]
0x1800074b1  mov     rcx, rax
0x1800074b4  mov     rdx, rax
0x1800074b7  neg     rcx
0x1800074ba  mov     rcx, [rsp+78h+arg_28]
0x1800074c2  sbb     eax, eax
0x1800074c4  not     eax
0x1800074c6  and     eax, 80004005h
0x1800074cb  mov     [rcx], rdx
0x1800074ce  add     rsp, 78h
0x1800074d2  retn
```
