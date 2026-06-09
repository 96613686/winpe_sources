# tlx::replace<void *,long (*)(void *),&MesHandleFree(void *),0>(tlx::auto_xxx<void *,long (*)(void *),&MesHandleFree(void *),0> &)

- ea: `0x18001e8e8`
- end: `0x18001e90f`
- name: `??$replace@PEAXP6AJPEAX@Z$1?MesHandleFree@@YAJ0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AJPEAX@Z$1?MesHandleFree@@YAJ0@Z$0A@@0@@Z`
- size: `39`
- prototype: `void **__fastcall(void **)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18001de40`
- `0x18001dfc0`
- `0x18001e144`
- `0x18001e2ec`
- `0x18001e48c`
- `0x18001e5bc`
- `0x18001e6ec`

## callees

- `0x18001e8e8`

## import_xrefs

- `RPCRT4!MesHandleFree` at `0x18001e8f9`
- `RPCRT4!MesHandleFree` at `0x18001e8f9`

## pseudocode

```c
void **__fastcall tlx::replace<void *,long (*)(void *),&long MesHandleFree(void *),0>(void **a1)
{
  void *v2; // rcx

  v2 = *a1;
  if ( v2 )
    MesHandleFree(v2);
  *a1 = 0;
  return a1;
}

```

## disassembly

```asm
0x18001e8e8  push    rbx
0x18001e8ea  sub     rsp, 20h
0x18001e8ee  mov     rbx, rcx
0x18001e8f1  mov     rcx, [rcx]; Handle
0x18001e8f4  test    rcx, rcx
0x18001e8f7  jz      short loc_18001E8FF
0x18001e8f9  call    cs:__imp_MesHandleFree
0x18001e8ff  mov     qword ptr [rbx], 0
0x18001e906  mov     rax, rbx
0x18001e909  add     rsp, 20h
0x18001e90d  pop     rbx
0x18001e90e  retn
```
