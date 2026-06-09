# BfRemoveCloudFileECPs

- ea: `0x140022e5c`
- end: `0x140022ed4`
- name: `BfRemoveCloudFileECPs`
- size: `120`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140002904`

## callees

- `0x140012504`
- `0x140022e5c`

## import_xrefs

- `FLTMGR!FltFreeExtraCreateParameterList` at `0x140022ec6`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x140022ec6`

## pseudocode

```c
void __fastcall BfRemoveCloudFileECPs(__int64 a1, struct _ECP_LIST *a2, char a3, char a4, char a5)
{
  if ( a2 )
  {
    if ( a4 )
      BfRemoveEcp(a1, a2, &GUID_ECP_NETWORK_OPEN_CONTEXT);
    if ( a5 )
      BfRemoveEcp(a1, a2, &GUID_ECP_CLOUDFILES_ATTRIBUTION);
    if ( a3 )
      FltFreeExtraCreateParameterList(*(PFLT_FILTER *)(a1 + 8), a2);
  }
}

```

## disassembly

```asm
0x140022e5c  test    rdx, rdx
0x140022e5f  jnz     short loc_140022E63
0x140022e61  retn
0x140022e63  mov     [rsp+arg_0], rbx
0x140022e68  mov     [rsp+arg_8], rsi
0x140022e6d  push    rdi
0x140022e6e  sub     rsp, 20h
0x140022e72  mov     sil, r8b
0x140022e75  mov     rbx, rdx
0x140022e78  mov     rdi, rcx
0x140022e7b  test    r9b, r9b
0x140022e7e  jnz     short loc_140022E9D
0x140022e80  cmp     [rsp+28h+arg_20], 0
0x140022e85  jnz     short loc_140022EAB
0x140022e87  test    sil, sil
0x140022e8a  jnz     short loc_140022EBF
0x140022e8c  mov     rbx, [rsp+28h+arg_0]
0x140022e91  mov     rsi, [rsp+28h+arg_8]
0x140022e96  add     rsp, 20h
0x140022e9a  pop     rdi
0x140022e9b  retn
0x140022e9d  lea     r8, GUID_ECP_NETWORK_OPEN_CONTEXT
0x140022ea4  call    BfRemoveEcp
0x140022ea9  jmp     short loc_140022E80
0x140022eab  lea     r8, GUID_ECP_CLOUDFILES_ATTRIBUTION
0x140022eb2  mov     rdx, rbx
0x140022eb5  mov     rcx, rdi
0x140022eb8  call    BfRemoveEcp
0x140022ebd  jmp     short loc_140022E87
0x140022ebf  mov     rcx, [rdi+8]; Filter
0x140022ec3  mov     rdx, rbx; EcpList
0x140022ec6  call    cs:__imp_FltFreeExtraCreateParameterList
0x140022ecd  nop     dword ptr [rax+rax+00h]
0x140022ed2  jmp     short loc_140022E8C
```
