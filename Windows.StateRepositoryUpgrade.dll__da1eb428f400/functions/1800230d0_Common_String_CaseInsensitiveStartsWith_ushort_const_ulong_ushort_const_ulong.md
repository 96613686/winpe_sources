# Common::String::CaseInsensitiveStartsWith(ushort const *,ulong,ushort const *,ulong)

- ea: `0x1800230d0`
- end: `0x180023107`
- name: `?CaseInsensitiveStartsWith@String@Common@@SAHPEBGK0K@Z`
- size: `55`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800232c8`

## callees

- `0x1800230d0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800230f2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800230f2`

## pseudocode

```c
__int64 __fastcall Common::String::CaseInsensitiveStartsWith(
        const unsigned __int16 *a1,
        unsigned int a2,
        const unsigned __int16 *a3)
{
  unsigned int v3; // ebx

  if ( a2 < 0xF )
    return 0;
  v3 = 1;
  if ( CompareStringOrdinal(a1, 15, L"%AppRepository%", 15, 1) != 2 )
    return 0;
  return v3;
}

```

## disassembly

```asm
0x1800230d0  push    rbx
0x1800230d2  sub     rsp, 30h
0x1800230d6  mov     eax, 0Fh
0x1800230db  cmp     edx, eax
0x1800230dd  jb      short loc_1800230FD
0x1800230df  lea     ebx, [rax-0Eh]
0x1800230e2  mov     r9d, eax; cchCount2
0x1800230e5  lea     r8, ?appRepositoryPrefix@StateRepository@@3QBGB; "%AppRepository%"
0x1800230ec  mov     [rsp+38h+bIgnoreCase], ebx; bIgnoreCase
0x1800230f0  mov     edx, eax; cchCount1
0x1800230f2  call    cs:__imp_CompareStringOrdinal
0x1800230f8  cmp     eax, 2
0x1800230fb  jz      short loc_1800230FF
0x1800230fd  xor     ebx, ebx
0x1800230ff  mov     eax, ebx
0x180023101  add     rsp, 30h
0x180023105  pop     rbx
0x180023106  retn
```
