# MbbCompleteRequest(_MBB_REQUEST_CONTEXT *,int)

- ea: `0x14000f900`
- end: `0x14000f967`
- name: `?MbbCompleteRequest@@YAXPEAU_MBB_REQUEST_CONTEXT@@H@Z`
- size: `103`
- prototype: `void(struct _MBB_REQUEST_CONTEXT *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400124a0`
- `0x140013220`

## callees

- `0x14000f900`
- `0x14000f970`
- `0x140047e90`

## import_xrefs

- `NDIS!NdisMOidRequestComplete` at `0x14000f935`
- `NDIS!NdisMOidRequestComplete` at `0x14000f935`

## pseudocode

```c
void __fastcall MbbCompleteRequest(struct _MBB_REQUEST_CONTEXT *a1, NDIS_STATUS a2)
{
  struct _NDIS_OID_REQUEST *v2; // rdi
  void *v4; // rax
  __int64 v5; // rcx
  unsigned int v6; // eax

  v2 = (struct _NDIS_OID_REQUEST *)*((_QWORD *)a1 + 11);
  if ( v2 )
  {
    v4 = (void *)((__int64 (__fastcall *)(PNET_DRIVER_GLOBALS, _QWORD))qword_14005F628)(
                   NetDriverGlobals,
                   *((_QWORD *)a1 + 13));
    NdisMOidRequestComplete(v4, v2, a2);
  }
  else
  {
    v5 = *((_QWORD *)a1 + 12);
    v6 = 0;
    if ( !a2 )
      v6 = *(_DWORD *)(v5 + 60) + 32;
    MbbCxCompleteWdfRequest((struct _WWAN_NDIS_OID_REQUEST *)v5, a2, v6);
  }
}

```

## disassembly

```asm
0x14000f900  mov     [rsp+arg_0], rbx
0x14000f905  push    rdi
0x14000f906  sub     rsp, 20h
0x14000f90a  mov     rdi, [rcx+58h]
0x14000f90e  mov     ebx, edx
0x14000f910  test    rdi, rdi
0x14000f913  jz      short loc_14000F943
0x14000f915  mov     rdx, [rcx+68h]
0x14000f919  mov     rcx, cs:NetDriverGlobals
0x14000f920  mov     rax, cs:qword_14005F628
0x14000f927  call    _guard_dispatch_icall
0x14000f92c  mov     r8d, ebx; Status
0x14000f92f  mov     rdx, rdi; OidRequest
0x14000f932  mov     rcx, rax; MiniportAdapterHandle
0x14000f935  call    cs:__imp_NdisMOidRequestComplete
0x14000f93c  nop     dword ptr [rax+rax+00h]
0x14000f941  jmp     short loc_14000F95B
0x14000f943  mov     rcx, [rcx+60h]; struct _WWAN_NDIS_OID_REQUEST *
0x14000f947  xor     eax, eax
0x14000f949  test    ebx, ebx
0x14000f94b  jnz     short loc_14000F953
0x14000f94d  mov     eax, [rcx+3Ch]
0x14000f950  add     eax, 20h ; ' '
0x14000f953  mov     r8d, eax; unsigned __int64
0x14000f956  call    ?MbbCxCompleteWdfRequest@@YAXPEAU_WWAN_NDIS_OID_REQUEST@@H_K@Z; MbbCxCompleteWdfRequest(_WWAN_NDIS_OID_REQUEST *,int,unsigned __int64)
0x14000f95b  mov     rbx, [rsp+28h+arg_0]
0x14000f960  add     rsp, 20h
0x14000f964  pop     rdi
0x14000f965  retn
```
