# SystemSettings::PenSettings::_anonymous_namespace_::IsFontSupported

- ea: `0x18001684c`
- end: `0x1800168ad`
- name: `SystemSettings::PenSettings::_anonymous_namespace_::IsFontSupported`
- size: `97`
- prototype: `__int64 __fastcall(LPCWCH lpString2)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015000`

## callees

- `0x18001684c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180016886`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180016886`

## pseudocode

```c
char __fastcall SystemSettings::PenSettings::_anonymous_namespace_::IsFontSupported(LPCWCH lpString2)
{
  LPCWCH *v1; // rbx
  LPCWCH *v3; // rdi

  v1 = (LPCWCH *)qword_18007CAE8;
  v3 = (LPCWCH *)xmmword_18007CAF0;
  while ( v1 != v3 )
  {
    if ( CompareStringOrdinal(*v1, -1, lpString2, -1, 0) == 2 )
      return 1;
    ++v1;
  }
  return 0;
}

```

## disassembly

```asm
0x18001684c  mov     [rsp+arg_0], rbx
0x180016851  mov     [rsp+arg_8], rsi
0x180016856  push    rdi
0x180016857  sub     rsp, 30h
0x18001685b  mov     rbx, cs:qword_18007CAE8
0x180016862  mov     rsi, rcx
0x180016865  mov     rdi, qword ptr cs:xmmword_18007CAF0
0x18001686c  cmp     rbx, rdi
0x18001686f  jz      short loc_18001689B
0x180016871  mov     rcx, [rbx]; lpString1
0x180016874  or      r9d, 0FFFFFFFFh; cchCount2
0x180016878  or      edx, r9d; cchCount1
0x18001687b  mov     [rsp+38h+bIgnoreCase], 0; bIgnoreCase
0x180016883  mov     r8, rsi; lpString2
0x180016886  call    cs:__imp_CompareStringOrdinal
0x18001688c  cmp     eax, 2
0x18001688f  jz      short loc_180016897
0x180016891  add     rbx, 8
0x180016895  jmp     short loc_18001686C
0x180016897  mov     al, 1
0x180016899  jmp     short loc_18001689D
0x18001689b  xor     al, al
0x18001689d  mov     rbx, [rsp+38h+arg_0]
0x1800168a2  mov     rsi, [rsp+38h+arg_8]
0x1800168a7  add     rsp, 30h
0x1800168ab  pop     rdi
0x1800168ac  retn
```
