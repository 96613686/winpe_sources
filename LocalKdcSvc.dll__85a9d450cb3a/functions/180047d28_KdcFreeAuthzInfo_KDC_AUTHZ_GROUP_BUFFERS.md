# KdcFreeAuthzInfo(_KDC_AUTHZ_GROUP_BUFFERS *)

- ea: `0x180047d28`
- end: `0x180047dca`
- name: `?KdcFreeAuthzInfo@@YAXPEAU_KDC_AUTHZ_GROUP_BUFFERS@@@Z`
- size: `162`
- prototype: `void __fastcall(struct _KDC_AUTHZ_GROUP_BUFFERS *)`
- caller_count: `7`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180013b14`
- `0x18001ce44`
- `0x180020b34`
- `0x180021400`
- `0x180024ffc`
- `0x1800276cc`
- `0x180045730`

## callees

- `0x180003908`
- `0x180047d28`
- `0x18005a090`

## import_xrefs

- `SAMSRV!SamIFree_SAMPR_ULONG_ARRAY` at `0x180047d77`
- `SAMSRV!SamIFree_SAMPR_ULONG_ARRAY` at `0x180047d77`
- `SAMSRV!SamIFreeSidArray` at `0x180047d80`
- `SAMSRV!SamIFreeSidArray` at `0x180047d80`
- `SAMSRV!SamIFreeAuthzSecurityAttributesInfo` at `0x180047dac`
- `SAMSRV!SamIFreeAuthzSecurityAttributesInfo` at `0x180047dac`

## pseudocode

```c
void __fastcall KdcFreeAuthzInfo(struct _KDC_AUTHZ_GROUP_BUFFERS *a1)
{
  void *v2; // rcx
  __int64 i; // rdi
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx

  v2 = (void *)*((_QWORD *)a1 + 5);
  if ( v2 )
    MIDL_user_free(v2);
  if ( *((_QWORD *)a1 + 2) )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)a1 + 2); i = (unsigned int)(i + 1) )
    {
      v4 = *(void **)(*((_QWORD *)a1 + 2) + 8 * i);
      if ( v4 )
        MIDL_user_free(v4);
    }
    MIDL_user_free(*((void **)a1 + 2));
  }
  SamIFree_SAMPR_ULONG_ARRAY((char *)a1 + 24);
  SamIFreeSidArray(*(_QWORD *)a1);
  v5 = (void *)*((_QWORD *)a1 + 6);
  if ( v5 )
    MIDL_user_free(v5);
  v6 = (void *)*((_QWORD *)a1 + 7);
  if ( v6 )
    MIDL_user_free(v6);
  if ( *((_DWORD *)a1 + 17) )
    SamIFreeAuthzSecurityAttributesInfo();
  memset_0(a1, 0, 0x50u);
}

```

## disassembly

```asm
0x180047d28  mov     [rsp+arg_0], rbx
0x180047d2d  push    rdi
0x180047d2e  sub     rsp, 20h
0x180047d32  mov     rbx, rcx
0x180047d35  mov     rcx, [rcx+28h]; void *
0x180047d39  test    rcx, rcx
0x180047d3c  jz      short loc_180047D43
0x180047d3e  call    MIDL_user_free
0x180047d43  cmp     qword ptr [rbx+10h], 0
0x180047d48  jz      short loc_180047D73
0x180047d4a  xor     edi, edi
0x180047d4c  cmp     [rbx+8], edi
0x180047d4f  jbe     short loc_180047D6A
0x180047d51  mov     rax, [rbx+10h]
0x180047d55  mov     rcx, [rax+rdi*8]; void *
0x180047d59  test    rcx, rcx
0x180047d5c  jz      short loc_180047D63
0x180047d5e  call    MIDL_user_free
0x180047d63  inc     edi
0x180047d65  cmp     edi, [rbx+8]
0x180047d68  jb      short loc_180047D51
0x180047d6a  mov     rcx, [rbx+10h]; void *
0x180047d6e  call    MIDL_user_free
0x180047d73  lea     rcx, [rbx+18h]
0x180047d77  call    cs:__imp_SamIFree_SAMPR_ULONG_ARRAY
0x180047d7d  mov     rcx, [rbx]
0x180047d80  call    cs:__imp_SamIFreeSidArray
0x180047d86  mov     rcx, [rbx+30h]; void *
0x180047d8a  test    rcx, rcx
0x180047d8d  jz      short loc_180047D94
0x180047d8f  call    MIDL_user_free
0x180047d94  mov     rcx, [rbx+38h]; void *
0x180047d98  test    rcx, rcx
0x180047d9b  jz      short loc_180047DA2
0x180047d9d  call    MIDL_user_free
0x180047da2  lea     rcx, [rbx+40h]
0x180047da6  cmp     dword ptr [rcx+4], 0
0x180047daa  jz      short loc_180047DB2
0x180047dac  call    cs:__imp_SamIFreeAuthzSecurityAttributesInfo
0x180047db2  xor     edx, edx; Val
0x180047db4  mov     rcx, rbx; void *
0x180047db7  lea     r8d, [rdx+50h]; Size
0x180047dbb  mov     rbx, [rsp+28h+arg_0]
0x180047dc0  add     rsp, 20h
0x180047dc4  pop     rdi
0x180047dc5  jmp     memset_0
```
