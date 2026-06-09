# BfRemoveCloudFileECPs

- ea: `0x140022f4c`
- end: `0x140022fc4`
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
- `0x140022f4c`

## import_xrefs

- `FLTMGR!FltFreeExtraCreateParameterList` at `0x140022fb6`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x140022fb6`

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
0x140022f4c  test    rdx, rdx
0x140022f4f  jnz     short loc_140022F53
0x140022f51  retn
0x140022f53  mov     [rsp+arg_0], rbx
0x140022f58  mov     [rsp+arg_8], rsi
0x140022f5d  push    rdi
0x140022f5e  sub     rsp, 20h
0x140022f62  mov     sil, r8b
0x140022f65  mov     rbx, rdx
0x140022f68  mov     rdi, rcx
0x140022f6b  test    r9b, r9b
0x140022f6e  jnz     short loc_140022F8D
0x140022f70  cmp     [rsp+28h+arg_20], 0
0x140022f75  jnz     short loc_140022F9B
0x140022f77  test    sil, sil
0x140022f7a  jnz     short loc_140022FAF
0x140022f7c  mov     rbx, [rsp+28h+arg_0]
0x140022f81  mov     rsi, [rsp+28h+arg_8]
0x140022f86  add     rsp, 20h
0x140022f8a  pop     rdi
0x140022f8b  retn
0x140022f8d  lea     r8, GUID_ECP_NETWORK_OPEN_CONTEXT
0x140022f94  call    BfRemoveEcp
0x140022f99  jmp     short loc_140022F70
0x140022f9b  lea     r8, GUID_ECP_CLOUDFILES_ATTRIBUTION
0x140022fa2  mov     rdx, rbx
0x140022fa5  mov     rcx, rdi
0x140022fa8  call    BfRemoveEcp
0x140022fad  jmp     short loc_140022F77
0x140022faf  mov     rcx, [rdi+8]; Filter
0x140022fb3  mov     rdx, rbx; EcpList
0x140022fb6  call    cs:__imp_FltFreeExtraCreateParameterList
0x140022fbd  nop     dword ptr [rax+rax+00h]
0x140022fc2  jmp     short loc_140022F7C
```
