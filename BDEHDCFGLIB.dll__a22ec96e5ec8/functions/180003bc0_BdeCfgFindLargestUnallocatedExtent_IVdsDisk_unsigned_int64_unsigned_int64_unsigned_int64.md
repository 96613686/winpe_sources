# BdeCfgFindLargestUnallocatedExtent(IVdsDisk *,unsigned __int64,unsigned __int64 *,unsigned __int64 *)

- ea: `0x180003bc0`
- end: `0x180003cf0`
- name: `?BdeCfgFindLargestUnallocatedExtent@@YAJPEAUIVdsDisk@@_KPEA_K2@Z`
- size: `304`
- prototype: `__int64 __fastcall(struct IVdsDisk *, unsigned __int64, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000f430`
- `0x18000fb40`

## callees

- `0x180003bc0`
- `0x180006234`
- `0x18000e2d0`
- `0x18000e750`
- `0x180015010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180003cd0`
- `ole32!CoTaskMemFree` at `0x180003cd0`

## pseudocode

```c
__int64 __fastcall BdeCfgFindLargestUnallocatedExtent(
        struct IVdsDisk *a1,
        unsigned __int64 a2,
        unsigned __int64 *a3,
        unsigned __int64 *a4)
{
  int ExtendedPartitionExtent; // ebx
  unsigned __int64 v8; // r14
  int v9; // esi
  unsigned __int64 v10; // r12
  unsigned __int64 v11; // r13
  char *v12; // rdi
  int v13; // [rsp+20h] [rbp-20h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-18h] BYREF
  unsigned __int64 v15; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int64 v16; // [rsp+38h] [rbp-8h] BYREF

  pv = 0;
  v15 = 0;
  v16 = 0;
  v13 = 0;
  if ( !g_pService )
    return 3231711254LL;
  ExtendedPartitionExtent = BdeCfgpGetExtendedPartitionExtent(a1, &v15, &v16);
  if ( ExtendedPartitionExtent >= 0 )
  {
    ExtendedPartitionExtent = ((__int64 (__fastcall *)(struct IVdsDisk *, LPVOID *, int *))a1->lpVtbl->QueryExtents)(
                                a1,
                                &pv,
                                &v13);
    if ( ExtendedPartitionExtent >= 0 )
    {
      v8 = 0;
      ExtendedPartitionExtent = 1;
      v9 = 0;
      if ( v13 > 0 )
      {
        v10 = v15;
        v11 = v16;
        do
        {
          v12 = (char *)pv + 80 * v9;
          BdeCfgLogEnumExtent(v12);
          if ( *((_DWORD *)v12 + 4) == 1
            && *((_QWORD *)v12 + 4) >= a2
            && *((_QWORD *)v12 + 4) > v8
            && (*((_QWORD *)v12 + 3) < v10 || *((_QWORD *)v12 + 3) >= v10 + v11) )
          {
            BdeCfgLogFoundUnallocatedExtent(v12);
            *a3 = *((_QWORD *)v12 + 3);
            if ( a4 )
              *a4 = *((_QWORD *)v12 + 4);
            v8 = *((_QWORD *)v12 + 4);
            ExtendedPartitionExtent = 0;
          }
          ++v9;
        }
        while ( v9 < v13 );
      }
    }
  }
  if ( pv )
    CoTaskMemFree(pv);
  return (unsigned int)ExtendedPartitionExtent;
}

```

## disassembly

```asm
0x180003bc0  mov     [rsp-38h+arg_0], rbx
0x180003bc5  mov     [rsp-38h+arg_10], r8
0x180003bca  mov     [rsp-38h+arg_8], rdx
0x180003bcf  push    rbp
0x180003bd0  push    rsi
0x180003bd1  push    rdi
0x180003bd2  push    r12
0x180003bd4  push    r13
0x180003bd6  push    r14
0x180003bd8  push    r15
0x180003bda  mov     rbp, rsp
0x180003bdd  sub     rsp, 40h
0x180003be1  xor     r12d, r12d
0x180003be4  mov     r15, r9
0x180003be7  cmp     cs:?g_pService@@3PEAUIVdsService@@EA, r12; IVdsService * g_pService
0x180003bee  mov     rdi, rcx
0x180003bf1  mov     [rbp+pv], r12
0x180003bf5  mov     [rbp+var_10], r12
0x180003bf9  mov     [rbp+var_8], r12
0x180003bfd  mov     [rbp+var_20], r12d
0x180003c01  jnz     short loc_180003C0D
0x180003c03  mov     eax, 0C0A00016h
0x180003c08  jmp     loc_180003CD8
0x180003c0d  lea     r8, [rbp+var_8]; unsigned __int64 *
0x180003c11  lea     rdx, [rbp+var_10]; unsigned __int64 *
0x180003c15  call    ?BdeCfgpGetExtendedPartitionExtent@@YAJPEAUIVdsDisk@@PEA_K1@Z; BdeCfgpGetExtendedPartitionExtent(IVdsDisk *,unsigned __int64 *,unsigned __int64 *)
0x180003c1a  mov     ebx, eax
0x180003c1c  test    eax, eax
0x180003c1e  js      loc_180003CC7
0x180003c24  mov     rax, [rdi]
0x180003c27  lea     r8, [rbp+var_20]
0x180003c2b  lea     rdx, [rbp+pv]
0x180003c2f  mov     rcx, rdi
0x180003c32  mov     rax, [rax+30h]
0x180003c36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c3b  mov     ebx, eax
0x180003c3d  test    eax, eax
0x180003c3f  js      loc_180003CC7
0x180003c45  mov     r14, r12
0x180003c48  mov     ebx, 1
0x180003c4d  mov     esi, r12d
0x180003c50  cmp     [rbp+var_20], r12d
0x180003c54  jle     short loc_180003CC7
0x180003c56  mov     r12, [rbp+var_10]
0x180003c5a  mov     r13, [rbp+var_8]
0x180003c5e  movsxd  rax, esi
0x180003c61  lea     rdi, [rax+rax*4]
0x180003c65  shl     rdi, 4
0x180003c69  add     rdi, [rbp+pv]
0x180003c6d  mov     rcx, rdi
0x180003c70  call    BdeCfgLogEnumExtent
0x180003c75  cmp     dword ptr [rdi+10h], 1
0x180003c79  jnz     short loc_180003CC0
0x180003c7b  mov     rax, [rbp+arg_8]
0x180003c7f  cmp     [rdi+20h], rax
0x180003c83  jb      short loc_180003CC0
0x180003c85  cmp     [rdi+20h], r14
0x180003c89  jbe     short loc_180003CC0
0x180003c8b  cmp     [rdi+18h], r12
0x180003c8f  jb      short loc_180003C9B
0x180003c91  lea     rax, [r12+r13]
0x180003c95  cmp     [rdi+18h], rax
0x180003c99  jb      short loc_180003CC0
0x180003c9b  mov     rcx, rdi
0x180003c9e  call    BdeCfgLogFoundUnallocatedExtent
0x180003ca3  mov     rcx, [rbp+arg_10]
0x180003ca7  mov     rax, [rdi+18h]
0x180003cab  mov     [rcx], rax
0x180003cae  test    r15, r15
0x180003cb1  jz      short loc_180003CBA
0x180003cb3  mov     rax, [rdi+20h]
0x180003cb7  mov     [r15], rax
0x180003cba  mov     r14, [rdi+20h]
0x180003cbe  xor     ebx, ebx
0x180003cc0  inc     esi
0x180003cc2  cmp     esi, [rbp+var_20]
0x180003cc5  jl      short loc_180003C5E
0x180003cc7  mov     rcx, [rbp+pv]; pv
0x180003ccb  test    rcx, rcx
0x180003cce  jz      short loc_180003CD6
0x180003cd0  call    cs:__imp_CoTaskMemFree
0x180003cd6  mov     eax, ebx
0x180003cd8  mov     rbx, [rsp+40h+arg_0]
0x180003ce0  add     rsp, 40h
0x180003ce4  pop     r15
0x180003ce6  pop     r14
0x180003ce8  pop     r13
0x180003cea  pop     r12
0x180003cec  pop     rdi
0x180003ced  pop     rsi
0x180003cee  pop     rbp
0x180003cef  retn
```
