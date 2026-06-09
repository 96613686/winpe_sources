# tlx::replace<ushort *,void * (*)(void *),&LocalFree(void *),0>(tlx::auto_xxx<ushort *,void * (*)(void *),&LocalFree(void *),0> &)

- ea: `0x180004b4c`
- end: `0x180004b73`
- name: `??$replace@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@YAPEAPEAGAEAV?$auto_xxx@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@0@@Z`
- size: `39`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800052b0`
- `0x180012900`
- `0x1800138f0`
- `0x180015020`

## callees

- `0x180004b4c`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180004b5d`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180004b5d`

## pseudocode

```c
void **__fastcall tlx::replace<unsigned short *,void * (*)(void *),&void * LocalFree(void *),0>(void **a1)
{
  void *v2; // rcx

  v2 = *a1;
  if ( v2 )
    LocalFree(v2);
  *a1 = 0;
  return a1;
}

```

## disassembly

```asm
0x180004b4c  push    rbx
0x180004b4e  sub     rsp, 20h
0x180004b52  mov     rbx, rcx
0x180004b55  mov     rcx, [rcx]; hMem
0x180004b58  test    rcx, rcx
0x180004b5b  jz      short loc_180004B63
0x180004b5d  call    cs:__imp_LocalFree
0x180004b63  mov     qword ptr [rbx], 0
0x180004b6a  mov     rax, rbx
0x180004b6d  add     rsp, 20h
0x180004b71  pop     rbx
0x180004b72  retn
```
