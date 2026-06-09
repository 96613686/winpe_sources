# sqlite3_collate_unicode_en_us_linguistic_ignorecase

- ea: `0x18004c0f0`
- end: `0x18004c13c`
- name: `sqlite3_collate_unicode_en_us_linguistic_ignorecase`
- size: `76`
- prototype: `__int64 __fastcall(int, int, int, int, LPCWCH)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18004c12e`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18004c12e`

## pseudocode

```c
__int64 __fastcall sqlite3_collate_unicode_en_us_linguistic_ignorecase(
        __int64 a1,
        int a2,
        const WCHAR *a3,
        int a4,
        LPCWCH lpString2)
{
  return (unsigned int)(CompareStringEx(
                          L"en-US",
                          0x10u,
                          a3,
                          (unsigned __int64)a2 >> 1,
                          lpString2,
                          (unsigned __int64)a4 >> 1,
                          0,
                          0,
                          0)
                      - 2);
}

```

## disassembly

```asm
0x18004c0f0  sub     rsp, 58h
0x18004c0f4  xor     ecx, ecx
0x18004c0f6  movsxd  rax, r9d
0x18004c0f9  mov     [rsp+58h+lParam], rcx; lParam
0x18004c0fe  mov     [rsp+58h+lpReserved], rcx; lpReserved
0x18004c103  mov     [rsp+58h+lpVersionInformation], rcx; lpVersionInformation
0x18004c108  lea     rcx, LocaleName; "en-US"
0x18004c10f  shr     rax, 1
0x18004c112  mov     [rsp+58h+cchCount2], eax; cchCount2
0x18004c116  mov     rax, [rsp+58h+arg_20]
0x18004c11e  movsxd  r9, edx
0x18004c121  mov     edx, 10h; dwCmpFlags
0x18004c126  shr     r9, 1; cchCount1
0x18004c129  mov     [rsp+58h+lpString2], rax; lpString2
0x18004c12e  call    cs:__imp_CompareStringEx
0x18004c134  sub     eax, 2
0x18004c137  add     rsp, 58h
0x18004c13b  retn
```
