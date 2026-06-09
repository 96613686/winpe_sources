# sqlite3_collate_unicode_en_us_ignorecase_ignorekanatype_ignorewidth

- ea: `0x1800af380`
- end: `0x1800af3cb`
- name: `sqlite3_collate_unicode_en_us_ignorecase_ignorekanatype_ignorewidth`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800af3bd`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800af3bd`

## pseudocode

```c
__int64 __fastcall sqlite3_collate_unicode_en_us_ignorecase_ignorekanatype_ignorewidth(
        __int64 a1,
        int a2,
        const WCHAR *a3,
        int a4,
        const WCHAR *a5)
{
  return (unsigned int)(CompareStringEx(
                          L"en-US",
                          0x30001u,
                          a3,
                          (unsigned __int64)a2 >> 1,
                          a5,
                          (unsigned __int64)a4 >> 1,
                          0,
                          0,
                          0)
                      - 2);
}

```

## disassembly

```asm
0x1800af380  mov     r11, rsp
0x1800af383  sub     rsp, 58h
0x1800af387  xor     ecx, ecx
0x1800af389  movsxd  rax, r9d
0x1800af38c  mov     [r11-18h], rcx
0x1800af390  mov     [r11-20h], rcx
0x1800af394  mov     [r11-28h], rcx
0x1800af398  lea     rcx, LocaleName; "en-US"
0x1800af39f  shr     rax, 1
0x1800af3a2  mov     [rsp+58h+cchCount2], eax; cchCount2
0x1800af3a6  mov     rax, [rsp+58h+arg_20]
0x1800af3ae  movsxd  r9, edx
0x1800af3b1  mov     edx, 30001h; dwCmpFlags
0x1800af3b6  shr     r9, 1; cchCount1
0x1800af3b9  mov     [r11-38h], rax
0x1800af3bd  call    cs:__imp_CompareStringEx
0x1800af3c3  sub     eax, 2
0x1800af3c6  add     rsp, 58h
0x1800af3ca  retn
```
