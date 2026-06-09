# FreeServerConfig(_KDS_CONFIGURATION *)

- ea: `0x180006d90`
- end: `0x180006db4`
- name: `?FreeServerConfig@@YAXPEAU_KDS_CONFIGURATION@@@Z`
- size: `36`
- prototype: `void __fastcall(struct _KDS_CONFIGURATION *lpMem)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180004a00`
- `0x180007060`

## callees

- `0x180006d90`
- `0x180010950`

## pseudocode

```c
void __fastcall FreeServerConfig(struct _KDS_CONFIGURATION *lpMem)
{
  void *v2; // rcx

  v2 = (void *)*((_QWORD *)lpMem + 8);
  if ( v2 )
    SIDKeyProvFree(v2);
  SIDKeyProvFree(lpMem);
}

```

## disassembly

```asm
0x180006d90  push    rbx
0x180006d92  sub     rsp, 20h
0x180006d96  mov     rbx, rcx
0x180006d99  mov     rcx, [rcx+40h]; lpMem
0x180006d9d  test    rcx, rcx
0x180006da0  jz      short loc_180006DA7
0x180006da2  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x180006da7  mov     rcx, rbx; lpMem
0x180006daa  add     rsp, 20h
0x180006dae  pop     rbx
0x180006daf  jmp     ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
```
