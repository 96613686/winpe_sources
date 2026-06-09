# FreeRootKeyConfig(_ROOT_KEY_HEADER)

- ea: `0x180004ee0`
- end: `0x180004f35`
- name: `?FreeRootKeyConfig@@YAXU_ROOT_KEY_HEADER@@@Z`
- size: `85`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180004d5c`
- `0x180004e20`

## callees

- `0x180004ee0`
- `0x180010950`

## pseudocode

```c
void __fastcall FreeRootKeyConfig(_QWORD *a1)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx

  v2 = (void *)a1[4];
  if ( v2 )
    SIDKeyProvFree(v2);
  v3 = (void *)a1[5];
  if ( v3 )
    SIDKeyProvFree(v3);
  v4 = (void *)a1[15];
  if ( v4 )
    SIDKeyProvFree(v4);
  v5 = (void *)a1[7];
  if ( v5 )
    SIDKeyProvFree(v5);
  v6 = (void *)a1[8];
  if ( v6 )
    SIDKeyProvFree(v6);
}

```

## disassembly

```asm
0x180004ee0  push    rbx
0x180004ee2  sub     rsp, 20h
0x180004ee6  mov     rbx, rcx
0x180004ee9  mov     rcx, [rcx+20h]; lpMem
0x180004eed  test    rcx, rcx
0x180004ef0  jz      short loc_180004EF7
0x180004ef2  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x180004ef7  mov     rcx, [rbx+28h]; lpMem
0x180004efb  test    rcx, rcx
0x180004efe  jz      short loc_180004F05
0x180004f00  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x180004f05  mov     rcx, [rbx+78h]; lpMem
0x180004f09  test    rcx, rcx
0x180004f0c  jz      short loc_180004F13
0x180004f0e  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x180004f13  mov     rcx, [rbx+38h]; lpMem
0x180004f17  test    rcx, rcx
0x180004f1a  jz      short loc_180004F21
0x180004f1c  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x180004f21  mov     rcx, [rbx+40h]; lpMem
0x180004f25  test    rcx, rcx
0x180004f28  jz      short loc_180004F2F
0x180004f2a  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x180004f2f  add     rsp, 20h
0x180004f33  pop     rbx
0x180004f34  retn
```
