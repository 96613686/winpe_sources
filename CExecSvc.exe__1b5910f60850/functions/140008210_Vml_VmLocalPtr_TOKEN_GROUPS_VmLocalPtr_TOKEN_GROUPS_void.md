# Vml::VmLocalPtr<_TOKEN_GROUPS>::~VmLocalPtr<_TOKEN_GROUPS>(void)

- ea: `0x140008210`
- end: `0x140008227`
- name: `??1?$VmLocalPtr@U_TOKEN_GROUPS@@@Vml@@QEAA@XZ`
- size: `23`
- prototype: `HLOCAL __fastcall(void **)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400229fe`
- `0x1400230eb`

## callees

- `0x140008210`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000821c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000821c`

## pseudocode

```c
HLOCAL __fastcall Vml::VmLocalPtr<_TOKEN_GROUPS>::~VmLocalPtr<_TOKEN_GROUPS>(void **a1)
{
  void *v1; // rcx
  HLOCAL result; // rax

  v1 = *a1;
  if ( v1 )
    return LocalFree(v1);
  return result;
}

```

## disassembly

```asm
0x140008210  sub     rsp, 28h
0x140008214  mov     rcx, [rcx]; hMem
0x140008217  test    rcx, rcx
0x14000821a  jz      short loc_140008222
0x14000821c  call    cs:__imp_LocalFree
0x140008222  add     rsp, 28h
0x140008226  retn
```
