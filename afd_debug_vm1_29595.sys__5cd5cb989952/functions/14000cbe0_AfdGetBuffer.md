# AfdGetBuffer

- ea: `0x14000cbe0`
- end: `0x14000ce60`
- name: `AfdGetBuffer`
- size: `640`
- prototype: `__int64 __fastcall(SIZE_T Length)`
- caller_count: `12`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14000c0d0`
- `0x14001bb20`
- `0x14001f120`
- `0x1400277f0`
- `0x14002b8b0`
- `0x14003586c`
- `0x14003ae50`
- `0x14003e410`
- `0x1400406dc`
- `0x140041038`
- `0x140041eac`
- `0x140053c90`

## callees

- `0x14000cbe0`
- `0x140010948`
- `0x1400129d0`
- `0x140013140`
- `0x14002bf60`

## import_xrefs

- `ntoskrnl!PsChargeProcessPoolQuota` at `0x14000ccb6`
- `ntoskrnl!PsChargeProcessPoolQuota` at `0x14000cdbe`
- `ntoskrnl!PsChargeProcessPoolQuota` at `0x14000ccb6`
- `ntoskrnl!PsChargeProcessPoolQuota` at `0x14000cdbe`
- `ntoskrnl!ExAllocatePool3` at `0x14000cd9a`
- `ntoskrnl!ExAllocatePool3` at `0x14000cd9a`
- `ntoskrnl!ExRaiseStatus` at `0x14000ccff`
- `ntoskrnl!ExRaiseStatus` at `0x14000ce1d`
- `ntoskrnl!ExRaiseStatus` at `0x14000ccff`
- `ntoskrnl!ExRaiseStatus` at `0x14000ce1d`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14000cc8a`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14000cc8a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cdd8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cdd8`

## pseudocode

```c
__int64 __fastcall AfdGetBuffer(SIZE_T Length, unsigned int a2, struct _KPROCESS *a3, char a4)
{
  char *v7; // rcx
  ULONG_PTR v8; // rdi
  char *v9; // rbx
  const signed __int16 *v10; // rax
  __int64 v11; // rbx
  int v12; // esi
  __int64 result; // rax
  unsigned __int8 v14; // r14
  unsigned int v15; // r15d
  unsigned int v16; // eax
  unsigned int v17; // r13d
  void *Pool3; // rbp
  int v19; // esi
  __int64 v20; // rax
  __int64 v21; // rcx
  _QWORD v22[2]; // [rsp+30h] [rbp-38h] BYREF

  if ( a2 > (unsigned int)AfdStandardAddressLength || (unsigned int)Length > (unsigned int)AfdHugeBufferSize )
  {
    if ( a2 > 0xFFFF )
      goto LABEL_33;
    v14 = AfdTdiStackSize;
    v15 = 4;
    if ( (_DWORD)Length )
      v15 = Length;
    v16 = AfdCalculateBufferSize(v15);
    if ( v16 >= v15
      && v16 >= a2
      && (v22[1] = 0, v22[0] = 1, v17 = v16, (Pool3 = (void *)ExAllocatePool3(66, v16, 1113876033, v22, 1)) != 0) )
    {
      if ( !a3 || (v19 = PsChargeProcessPoolQuota(a3, (POOL_TYPE)512, v17), v19 >= 0) )
      {
        v20 = AfdInitializeBuffer(Pool3, v15, a2, v14);
        v21 = v20;
        if ( v20 )
        {
          *(_DWORD *)(v20 + 68) = 0;
          *(_QWORD *)(v20 + 80) = *(_QWORD *)(v20 + 56);
          *(_DWORD *)(v20 + 88) = 0;
        }
        return v21;
      }
      ExFreePoolWithTag(Pool3, 0x42646641u);
    }
    else
    {
LABEL_33:
      v19 = -1073741670;
    }
    if ( (a4 & 1) != 0 )
      ExRaiseStatus(v19);
    return 0;
  }
  if ( (unsigned int)Length > (unsigned int)AfdSmallBufferSize )
  {
    if ( (unsigned int)Length > (unsigned int)AfdMediumBufferSize )
    {
      if ( (unsigned int)Length > (unsigned int)AfdLargeBufferSize )
      {
        v7 = (char *)AfdPplHugeBufferPool;
        v8 = AfdPplHugeBufferSize;
      }
      else
      {
        v7 = (char *)AfdPplLargeBufferPool;
        v8 = AfdPplLargeBufferSize;
      }
    }
    else
    {
      v7 = (char *)AfdPplMediumBufferPool;
      v8 = AfdPplMediumBufferSize;
    }
  }
  else
  {
    v7 = (char *)AfdPplSmallBufferPool;
    v8 = AfdPplSmallBufferSize;
  }
  v9 = &v7[128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1)];
  if ( !v9[176] )
    PplpLazyInitializeLookasideList((__int64)v7, (__int64)(v9 + 64));
  v10 = (const signed __int16 *)ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v9 + 64));
  v11 = (__int64)v10;
  if ( v10 )
  {
    if ( _bittest16(v10 + 48, 8u) || !a3 || (v12 = PsChargeProcessPoolQuota(a3, (POOL_TYPE)512, v8), v12 >= 0) )
    {
      *(_QWORD *)(v11 + 80) = *(_QWORD *)(v11 + 56);
      result = v11;
      *(_DWORD *)(v11 + 68) = 0;
      *(_DWORD *)(v11 + 88) = 0;
      return result;
    }
    AfdFreeBuffer(v11, 0);
  }
  else
  {
    v12 = -1073741670;
  }
  if ( (a4 & 1) != 0 )
    ExRaiseStatus(v12);
  return 0;
}

```

## disassembly

```asm
0x14000cbe0  push    rbx
0x14000cbe2  push    rsi
0x14000cbe3  push    rdi
0x14000cbe4  push    r12
0x14000cbe6  sub     rsp, 48h
0x14000cbea  cmp     edx, cs:AfdStandardAddressLength
0x14000cbf0  mov     r12d, r9d
0x14000cbf3  mov     rsi, r8
0x14000cbf6  mov     ebx, edx
0x14000cbf8  ja      loc_14000CD19
0x14000cbfe  cmp     ecx, cs:AfdHugeBufferSize
0x14000cc04  ja      loc_14000CD19
0x14000cc0a  cmp     ecx, cs:AfdSmallBufferSize
0x14000cc10  ja      short loc_14000CC22
0x14000cc12  mov     rcx, cs:AfdPplSmallBufferPool
0x14000cc19  mov     rdi, cs:AfdPplSmallBufferSize
0x14000cc20  jmp     short loc_14000CC60
0x14000cc22  cmp     ecx, cs:AfdMediumBufferSize
0x14000cc28  ja      short loc_14000CC3A
0x14000cc2a  mov     rcx, cs:AfdPplMediumBufferPool
0x14000cc31  mov     rdi, cs:AfdPplMediumBufferSize
0x14000cc38  jmp     short loc_14000CC60
0x14000cc3a  cmp     ecx, cs:AfdLargeBufferSize
0x14000cc40  ja      short loc_14000CC52
0x14000cc42  mov     rcx, cs:AfdPplLargeBufferPool
0x14000cc49  mov     rdi, cs:AfdPplLargeBufferSize
0x14000cc50  jmp     short loc_14000CC60
0x14000cc52  mov     rcx, cs:AfdPplHugeBufferPool
0x14000cc59  mov     rdi, cs:AfdPplHugeBufferSize
0x14000cc60  mov     eax, gs:1A4h
0x14000cc68  lea     ebx, [rax+1]
0x14000cc6b  shl     rbx, 7
0x14000cc6f  add     rbx, rcx
0x14000cc72  movzx   eax, byte ptr [rbx+0B0h]
0x14000cc79  test    al, al
0x14000cc7b  jnz     short loc_14000CC86
0x14000cc7d  lea     rdx, [rbx+40h]
0x14000cc81  call    PplpLazyInitializeLookasideList
0x14000cc86  lea     rcx, [rbx+40h]; Lookaside
0x14000cc8a  call    cs:__imp_ExAllocateFromLookasideListEx
0x14000cc91  nop     dword ptr [rax+rax+00h]
0x14000cc96  mov     rbx, rax
0x14000cc99  test    rax, rax
0x14000cc9c  jz      short loc_14000CCF2
0x14000cc9e  bt      word ptr [rax+60h], 8
0x14000cca4  jb      short loc_14000CCD4
0x14000cca6  test    rsi, rsi
0x14000cca9  jz      short loc_14000CCD4
0x14000ccab  mov     r8, rdi; Amount
0x14000ccae  mov     edx, 200h; PoolType
0x14000ccb3  mov     rcx, rsi; Process
0x14000ccb6  call    cs:__imp_PsChargeProcessPoolQuota
0x14000ccbd  nop     dword ptr [rax+rax+00h]
0x14000ccc2  mov     esi, eax
0x14000ccc4  test    eax, eax
0x14000ccc6  jns     short loc_14000CCD4
0x14000ccc8  xor     edx, edx
0x14000ccca  mov     rcx, rbx
0x14000cccd  call    AfdFreeBuffer
0x14000ccd2  jmp     short loc_14000CCF7
0x14000ccd4  mov     rax, [rbx+38h]
0x14000ccd8  xor     edi, edi
0x14000ccda  mov     [rbx+50h], rax
0x14000ccde  mov     rax, rbx
0x14000cce1  mov     [rbx+44h], edi
0x14000cce4  mov     [rbx+58h], edi
0x14000cce7  add     rsp, 48h
0x14000cceb  pop     r12
0x14000cced  pop     rdi
0x14000ccee  pop     rsi
0x14000ccef  pop     rbx
0x14000ccf0  retn
0x14000ccf2  mov     esi, 0C000009Ah
0x14000ccf7  test    r12b, 1
0x14000ccfb  jz      short loc_14000CD0C
0x14000ccfd  mov     ecx, esi; Status
0x14000ccff  call    cs:__imp_ExRaiseStatus
0x14000cd0c  xor     eax, eax
0x14000cd0e  add     rsp, 48h
0x14000cd12  pop     r12
0x14000cd14  pop     rdi
0x14000cd15  pop     rsi
0x14000cd16  pop     rbx
0x14000cd17  retn
0x14000cd19  mov     [rsp+68h+arg_0], rbp
0x14000cd1e  xor     edi, edi
0x14000cd20  mov     [rsp+68h+arg_8], r13
0x14000cd25  mov     [rsp+68h+arg_10], r14
0x14000cd2d  mov     [rsp+68h+var_28], r15
0x14000cd32  cmp     ebx, 0FFFFh
0x14000cd38  ja      loc_14000CE10
0x14000cd3e  movzx   r14d, cs:AfdTdiStackSize
0x14000cd46  test    ecx, ecx
0x14000cd48  mov     r15d, 4
0x14000cd4e  movzx   r8d, r14b
0x14000cd52  cmovnz  r15d, ecx
0x14000cd56  mov     ecx, r15d; Length
0x14000cd59  call    AfdCalculateBufferSize
0x14000cd5e  cmp     eax, r15d
0x14000cd61  jb      loc_14000CE10
0x14000cd67  cmp     eax, ebx
0x14000cd69  jb      loc_14000CE10
0x14000cd6f  lea     r9, [rsp+68h+var_38]
0x14000cd74  mov     edx, eax
0x14000cd76  mov     r8d, 42646641h
0x14000cd7c  mov     [rsp+68h+var_30], rdi
0x14000cd81  mov     ecx, 42h ; 'B'
0x14000cd86  mov     [rsp+68h+var_38], 1
0x14000cd8f  mov     r13d, eax
0x14000cd92  mov     [rsp+68h+var_48], 1
0x14000cd9a  call    cs:__imp_ExAllocatePool3
0x14000cda1  nop     dword ptr [rax+rax+00h]
0x14000cda6  mov     rbp, rax
0x14000cda9  test    rax, rax
0x14000cdac  jz      short loc_14000CE10
0x14000cdae  test    rsi, rsi
0x14000cdb1  jz      short loc_14000CDE6
0x14000cdb3  mov     r8d, r13d; Amount
0x14000cdb6  mov     edx, 200h; PoolType
0x14000cdbb  mov     rcx, rsi; Process
0x14000cdbe  call    cs:__imp_PsChargeProcessPoolQuota
0x14000cdc5  nop     dword ptr [rax+rax+00h]
0x14000cdca  mov     esi, eax
0x14000cdcc  test    eax, eax
0x14000cdce  jns     short loc_14000CDE6
0x14000cdd0  mov     edx, 42646641h; Tag
0x14000cdd5  mov     rcx, rbp; P
0x14000cdd8  call    cs:__imp_ExFreePoolWithTag
0x14000cddf  nop     dword ptr [rax+rax+00h]
0x14000cde4  jmp     short loc_14000CE15
0x14000cde6  movzx   r9d, r14b
0x14000cdea  mov     r8d, ebx
0x14000cded  mov     edx, r15d
0x14000cdf0  mov     rcx, rbp
0x14000cdf3  call    AfdInitializeBuffer
0x14000cdf8  mov     rcx, rax
0x14000cdfb  test    rax, rax
0x14000cdfe  jz      short loc_14000CE2D
0x14000ce00  mov     [rax+44h], edi
0x14000ce03  mov     rax, [rax+38h]
0x14000ce07  mov     [rcx+50h], rax
0x14000ce0b  mov     [rcx+58h], edi
0x14000ce0e  jmp     short loc_14000CE2D
0x14000ce10  mov     esi, 0C000009Ah
0x14000ce15  test    r12b, 1
0x14000ce19  jz      short loc_14000CE2A
0x14000ce1b  mov     ecx, esi; Status
0x14000ce1d  call    cs:__imp_ExRaiseStatus
0x14000ce2a  mov     rcx, rdi
0x14000ce2d  mov     r14, [rsp+68h+arg_10]
0x14000ce35  mov     rax, rcx
0x14000ce38  mov     r13, [rsp+68h+arg_8]
0x14000ce3d  mov     rbp, [rsp+68h+arg_0]
0x14000ce42  mov     r15, [rsp+68h+var_28]
0x14000ce47  add     rsp, 48h
0x14000ce4b  pop     r12
0x14000ce4d  pop     rdi
0x14000ce4e  pop     rsi
0x14000ce4f  pop     rbx
0x14000ce50  retn
```
