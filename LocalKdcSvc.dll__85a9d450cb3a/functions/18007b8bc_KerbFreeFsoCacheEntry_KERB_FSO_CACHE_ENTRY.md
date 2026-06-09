# KerbFreeFsoCacheEntry(_KERB_FSO_CACHE_ENTRY *)

- ea: `0x18007b8bc`
- end: `0x18007b942`
- name: `?KerbFreeFsoCacheEntry@@YAXPEAU_KERB_FSO_CACHE_ENTRY@@@Z`
- size: `134`
- prototype: `void __fastcall(struct _KERB_FSO_CACHE_ENTRY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18007b790`

## callees

- `0x18007b754`
- `0x18007b8bc`
- `0x18009c010`

## import_xrefs

- `ntdll!RtlDeleteResource` at `0x18007b91f`
- `ntdll!RtlDeleteResource` at `0x18007b91f`

## pseudocode

```c
void __fastcall KerbFreeFsoCacheEntry(struct _KERB_FSO_CACHE_ENTRY *a1)
{
  _QWORD *v1; // rdi
  struct _KERB_FSO_BINDING_HANDLE *v3; // rcx

  v1 = (_QWORD *)((char *)a1 + 136);
  if ( *((_QWORD *)a1 + 19) )
    (*((void (__fastcall **)(_QWORD))FsoFunctions + 1))(*v1);
  if ( *((_QWORD *)a1 + 21) )
    (*((void (__fastcall **)(_QWORD))FsoFunctions + 1))(*v1);
  v3 = (struct _KERB_FSO_BINDING_HANDLE *)*((_QWORD *)a1 + 23);
  if ( v3 )
    KerbDereferenceFsoBindingHandle(v3);
  RtlDeleteResource((PRTL_RESOURCE)((char *)a1 + 24));
  (*((void (__fastcall **)(struct _KERB_FSO_CACHE_ENTRY *))FsoFunctions + 1))(a1);
}

```

## disassembly

```asm
0x18007b8bc  mov     [rsp+arg_0], rbx
0x18007b8c1  push    rdi
0x18007b8c2  sub     rsp, 20h
0x18007b8c6  cmp     qword ptr [rcx+98h], 0
0x18007b8ce  lea     rdi, [rcx+88h]
0x18007b8d5  mov     rbx, rcx
0x18007b8d8  jz      short loc_18007B8ED
0x18007b8da  mov     rax, cs:?FsoFunctions@@3PEBU_KERB_FSO_COMMON_FUNCTION_TABLE@@EB; _KERB_FSO_COMMON_FUNCTION_TABLE const * const FsoFunctions
0x18007b8e1  mov     rcx, [rdi]
0x18007b8e4  mov     rax, [rax+8]
0x18007b8e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b8ed  cmp     qword ptr [rbx+0A8h], 0
0x18007b8f5  jz      short loc_18007B90A
0x18007b8f7  mov     rax, cs:?FsoFunctions@@3PEBU_KERB_FSO_COMMON_FUNCTION_TABLE@@EB; _KERB_FSO_COMMON_FUNCTION_TABLE const * const FsoFunctions
0x18007b8fe  mov     rcx, [rdi]
0x18007b901  mov     rax, [rax+8]
0x18007b905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b90a  mov     rcx, [rbx+0B8h]; struct _KERB_FSO_BINDING_HANDLE *
0x18007b911  test    rcx, rcx
0x18007b914  jz      short loc_18007B91B
0x18007b916  call    ?KerbDereferenceFsoBindingHandle@@YAXPEAU_KERB_FSO_BINDING_HANDLE@@@Z; KerbDereferenceFsoBindingHandle(_KERB_FSO_BINDING_HANDLE *)
0x18007b91b  lea     rcx, [rbx+18h]; Resource
0x18007b91f  call    cs:__imp_RtlDeleteResource
0x18007b925  mov     rax, cs:?FsoFunctions@@3PEBU_KERB_FSO_COMMON_FUNCTION_TABLE@@EB; _KERB_FSO_COMMON_FUNCTION_TABLE const * const FsoFunctions
0x18007b92c  mov     rcx, rbx
0x18007b92f  mov     rax, [rax+8]
0x18007b933  mov     rbx, [rsp+28h+arg_0]
0x18007b938  add     rsp, 20h
0x18007b93c  pop     rdi
0x18007b93d  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
