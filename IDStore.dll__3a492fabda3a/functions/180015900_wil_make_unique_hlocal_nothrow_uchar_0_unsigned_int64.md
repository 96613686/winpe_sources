# wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)

- ea: `0x180015900`
- end: `0x180015940`
- name: `??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z`
- size: `64`
- prototype: `_QWORD *__fastcall(_QWORD *, SIZE_T)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800158b8`
- `0x180018ac4`

## callees

- `0x180015900`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015912`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015912`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_hlocal_nothrow<unsigned char [0]>(_QWORD *a1, SIZE_T a2)
{
  _BYTE *v4; // rax
  _BYTE *v5; // rdx

  v4 = LocalAlloc(0, a2);
  *a1 = v4;
  if ( v4 )
  {
    v5 = &v4[a2];
    while ( v4 != v5 )
      *v4++ = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180015900  mov     [rsp+arg_0], rbx
0x180015905  push    rdi
0x180015906  sub     rsp, 20h
0x18001590a  mov     rbx, rcx
0x18001590d  mov     rdi, rdx
0x180015910  xor     ecx, ecx; uFlags
0x180015912  call    cs:__imp_LocalAlloc
0x180015918  mov     [rbx], rax
0x18001591b  test    rax, rax
0x18001591e  jz      short loc_180015932
0x180015920  lea     rdx, [rax+rdi]
0x180015924  jmp     short loc_18001592D
0x180015926  xor     ecx, ecx
0x180015928  mov     [rax], cl
0x18001592a  inc     rax
0x18001592d  cmp     rax, rdx
0x180015930  jnz     short loc_180015926
0x180015932  mov     rax, rbx
0x180015935  mov     rbx, [rsp+28h+arg_0]
0x18001593a  add     rsp, 20h
0x18001593e  pop     rdi
0x18001593f  retn
```
