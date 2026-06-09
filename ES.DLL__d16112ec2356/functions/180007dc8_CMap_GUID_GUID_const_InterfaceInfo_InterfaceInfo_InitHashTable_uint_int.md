# CMap<_GUID,_GUID const &,InterfaceInfo *,InterfaceInfo *>::InitHashTable(uint,int)

- ea: `0x180007dc8`
- end: `0x180007e65`
- name: `?InitHashTable@?$CMap@U_GUID@@AEBU1@PEAVInterfaceInfo@@PEAV2@@@QEAAJIH@Z`
- size: `157`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180006b10`

## callees

- `0x180007dc8`
- `0x1800434c6`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007e0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007e0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007e56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007e56`

## pseudocode

```c
__int64 __fastcall CMap<_GUID,_GUID const &,InterfaceInfo *,InterfaceInfo *>::InitHashTable(
        __int64 a1,
        unsigned int a2)
{
  int v2; // r8d
  void *v4; // rcx
  unsigned __int64 v5; // rdi
  void *v6; // rax
  __int64 result; // rax

  v2 = 0;
  if ( a2 > 0x11 )
  {
    do
      ++v2;
    while ( *((_DWORD *)`Map<unsigned short *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::grow'::`2'::rgprime + v2) < a2 );
  }
  v4 = *(void **)a1;
  v5 = *((unsigned int *)`Map<unsigned short *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::grow'::`2'::rgprime + v2);
  if ( v4 )
  {
    CoTaskMemFree(v4);
    *(_QWORD *)a1 = 0;
  }
  v6 = CoTaskMemAlloc(saturated_mul(v5, 8u));
  *(_QWORD *)a1 = v6;
  if ( !v6 )
    return 2147942414LL;
  memset_0(v6, 0, 8 * v5);
  result = 0;
  *(_DWORD *)(a1 + 8) = v5;
  return result;
}

```

## disassembly

```asm
0x180007dc8  mov     [rsp+arg_0], rbx
0x180007dcd  mov     [rsp+arg_8], rsi
0x180007dd2  push    rdi
0x180007dd3  sub     rsp, 20h
0x180007dd7  xor     r8d, r8d
0x180007dda  lea     rdi, ?rgprime@?1??grow@?$Map@PEAGPEAUIDispatch@@VHashWSTR@@VCNonFailFastingAllocator@@@@AEAAJXZ@4QBIB; uint const near * const `Map<ushort *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::grow(void)'::`2'::rgprime
0x180007de1  mov     rbx, rcx
0x180007de4  cmp     edx, 11h
0x180007de7  ja      short loc_180007E49
0x180007de9  mov     rcx, [rcx]; pv
0x180007dec  movsxd  rax, r8d
0x180007def  mov     edi, [rdi+rax*4]
0x180007df2  test    rcx, rcx
0x180007df5  jnz     short loc_180007E56
0x180007df7  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180007dfe  mov     eax, 8
0x180007e03  mul     rdi
0x180007e06  cmovb   rax, rcx
0x180007e0a  mov     rcx, rax; cb
0x180007e0d  call    cs:__imp_CoTaskMemAlloc
0x180007e13  mov     [rbx], rax
0x180007e16  test    rax, rax
0x180007e19  jz      short loc_180007E42
0x180007e1b  lea     r8, ds:0[rdi*8]; Size
0x180007e23  xor     edx, edx; Val
0x180007e25  mov     rcx, rax; void *
0x180007e28  call    memset_0
0x180007e2d  xor     eax, eax
0x180007e2f  mov     [rbx+8], edi
0x180007e32  mov     rbx, [rsp+28h+arg_0]
0x180007e37  mov     rsi, [rsp+28h+arg_8]
0x180007e3c  add     rsp, 20h
0x180007e40  pop     rdi
0x180007e41  retn
0x180007e42  mov     eax, 8007000Eh
0x180007e47  jmp     short loc_180007E32
0x180007e49  inc     r8d
0x180007e4c  movsxd  rax, r8d
0x180007e4f  cmp     [rdi+rax*4], edx
0x180007e52  jb      short loc_180007E49
0x180007e54  jmp     short loc_180007DE9
0x180007e56  call    cs:__imp_CoTaskMemFree
0x180007e5c  mov     qword ptr [rbx], 0
0x180007e63  jmp     short loc_180007DF7
```
