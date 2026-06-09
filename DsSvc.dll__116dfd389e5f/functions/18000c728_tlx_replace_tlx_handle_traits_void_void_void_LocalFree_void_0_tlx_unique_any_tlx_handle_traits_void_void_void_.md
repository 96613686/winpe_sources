# tlx::replace<tlx::handle_traits<void *,void * (*)(void *),&LocalFree(void *),0>>(tlx::unique_any<tlx::handle_traits<void *,void * (*)(void *),&LocalFree(void *),0>> &)

- ea: `0x18000c728`
- end: `0x18000c74f`
- name: `??$replace@U?$handle_traits@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@U?$handle_traits@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@0@@Z`
- size: `39`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ca4c`
- `0x18000f740`
- `0x1800109d8`
- `0x180012f20`
- `0x1800198f8`
- `0x180019a94`

## callees

- `0x18000c728`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c740`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c740`

## pseudocode

```c
void **__fastcall tlx::replace<tlx::handle_traits<void *,void * (*)(void *),&void * LocalFree(void *),0>>(void **a1)
{
  void *v2; // rcx

  v2 = *a1;
  *a1 = 0;
  if ( v2 )
    LocalFree(v2);
  return a1;
}

```

## disassembly

```asm
0x18000c728  push    rbx
0x18000c72a  sub     rsp, 20h
0x18000c72e  mov     rbx, rcx
0x18000c731  mov     rcx, [rcx]; hMem
0x18000c734  mov     qword ptr [rbx], 0
0x18000c73b  test    rcx, rcx
0x18000c73e  jz      short loc_18000C746
0x18000c740  call    cs:__imp_LocalFree
0x18000c746  mov     rax, rbx
0x18000c749  add     rsp, 20h
0x18000c74d  pop     rbx
0x18000c74e  retn
```
