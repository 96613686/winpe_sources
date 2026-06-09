# BdeCfgCreatePrimaryPartitionAdjustedSize(IVdsCreatePartitionEx *,_CREATE_PARTITION_PARAMETERS *,IVdsAsync * *,unsigned __int64,unsigned __int64,unsigned __int64)

- ea: `0x180002f54`
- end: `0x180003006`
- name: `?BdeCfgCreatePrimaryPartitionAdjustedSize@@YAJPEAUIVdsCreatePartitionEx@@PEAU_CREATE_PARTITION_PARAMETERS@@PEAPEAUIVdsAsync@@_K33@Z`
- size: `178`
- prototype: `__int64 __fastcall(struct IVdsCreatePartitionEx *, struct _CREATE_PARTITION_PARAMETERS *, struct IVdsAsync **, __int64, unsigned __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180002d24`
- `0x180003010`

## callees

- `0x180002f54`
- `0x180006104`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall BdeCfgCreatePrimaryPartitionAdjustedSize(
        struct IVdsCreatePartitionEx *a1,
        struct _CREATE_PARTITION_PARAMETERS *a2,
        struct IVdsAsync **a3,
        __int64 a4,
        unsigned __int64 a5,
        unsigned __int64 a6)
{
  unsigned __int64 v10; // rbx
  __int64 result; // rax
  unsigned int v12; // [rsp+60h] [rbp+8h] BYREF

  v12 = 0;
  if ( !a1 || !a2 || !a3 )
    return 2147500035LL;
  v10 = a5;
  if ( !a5 || !a6 )
    return 2147942487LL;
  result = BdeCfgpGetDiskAlignment(a6, &v12);
  if ( (int)result >= 0 )
  {
    if ( v12 < v10 )
      return ((__int64 (__fastcall *)(struct IVdsCreatePartitionEx *, __int64, unsigned __int64, _QWORD, struct _CREATE_PARTITION_PARAMETERS *, struct IVdsAsync **))a1->lpVtbl->CreatePartitionEx)(
               a1,
               a4,
               v10 - v12,
               0,
               a2,
               a3);
    else
      return 3231711259LL;
  }
  return result;
}

```

## disassembly

```asm
0x180002f54  mov     rax, rsp
0x180002f57  mov     [rax+10h], rbx
0x180002f5b  mov     [rax+18h], rbp
0x180002f5f  push    rsi
0x180002f60  push    rdi
0x180002f61  push    r14
0x180002f63  sub     rsp, 40h
0x180002f67  mov     dword ptr [rax+8], 0
0x180002f6e  mov     rbp, r9
0x180002f71  mov     rdi, r8
0x180002f74  mov     rsi, rdx
0x180002f77  mov     r14, rcx
0x180002f7a  test    rcx, rcx
0x180002f7d  jz      short loc_180002FEE
0x180002f7f  test    rdx, rdx
0x180002f82  jz      short loc_180002FEE
0x180002f84  test    r8, r8
0x180002f87  jz      short loc_180002FEE
0x180002f89  mov     rbx, [rsp+58h+arg_20]
0x180002f91  test    rbx, rbx
0x180002f94  jz      short loc_180002FE7
0x180002f96  mov     rcx, [rsp+58h+arg_28]; unsigned __int64
0x180002f9e  test    rcx, rcx
0x180002fa1  jz      short loc_180002FE7
0x180002fa3  lea     rdx, [rax+8]; unsigned int *
0x180002fa7  call    ?BdeCfgpGetDiskAlignment@@YAJ_KPEAK@Z; BdeCfgpGetDiskAlignment(unsigned __int64,ulong *)
0x180002fac  test    eax, eax
0x180002fae  js      short loc_180002FF3
0x180002fb0  mov     ecx, [rsp+58h+arg_0]
0x180002fb4  cmp     rcx, rbx
0x180002fb7  jb      short loc_180002FC0
0x180002fb9  mov     eax, 0C0A0001Bh
0x180002fbe  jmp     short loc_180002FF3
0x180002fc0  mov     rax, [r14]
0x180002fc3  sub     rbx, rcx
0x180002fc6  mov     [rsp+58h+var_30], rdi
0x180002fcb  xor     r9d, r9d
0x180002fce  mov     r8, rbx
0x180002fd1  mov     [rsp+58h+var_38], rsi
0x180002fd6  mov     rdx, rbp
0x180002fd9  mov     rcx, r14
0x180002fdc  mov     rax, [rax+18h]
0x180002fe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fe5  jmp     short loc_180002FF3
0x180002fe7  mov     eax, 80070057h
0x180002fec  jmp     short loc_180002FF3
0x180002fee  mov     eax, 80004003h
0x180002ff3  mov     rbx, [rsp+58h+arg_8]
0x180002ff8  mov     rbp, [rsp+58h+arg_10]
0x180002ffd  add     rsp, 40h
0x180003001  pop     r14
0x180003003  pop     rdi
0x180003004  pop     rsi
0x180003005  retn
```
