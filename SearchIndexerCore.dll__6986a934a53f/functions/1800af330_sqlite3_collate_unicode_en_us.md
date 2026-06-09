# sqlite3_collate_unicode_en_us

- ea: `0x1800af330`
- end: `0x1800af378`
- name: `sqlite3_collate_unicode_en_us`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800af36a`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800af36a`

## pseudocode

```c
__int64 __fastcall sqlite3_collate_unicode_en_us(__int64 a1, int a2, const WCHAR *a3, int a4, const WCHAR *a5)
{
  return (unsigned int)(CompareStringEx(
                          L"en-US",
                          0,
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
0x1800af330  mov     r11, rsp
0x1800af333  sub     rsp, 58h
0x1800af337  xor     ecx, ecx
0x1800af339  movsxd  rax, r9d
0x1800af33c  mov     [r11-18h], rcx
0x1800af340  mov     [r11-20h], rcx
0x1800af344  mov     [r11-28h], rcx
0x1800af348  lea     rcx, LocaleName; "en-US"
0x1800af34f  shr     rax, 1
0x1800af352  mov     [rsp+58h+cchCount2], eax; cchCount2
0x1800af356  mov     rax, [rsp+58h+arg_20]
0x1800af35e  movsxd  r9, edx
0x1800af361  xor     edx, edx; dwCmpFlags
0x1800af363  shr     r9, 1; cchCount1
0x1800af366  mov     [r11-38h], rax
0x1800af36a  call    cs:__imp_CompareStringEx
0x1800af370  sub     eax, 2
0x1800af373  add     rsp, 58h
0x1800af377  retn
```
