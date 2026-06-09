# SiCreateDrt(_SU_POOL_OBJECT *,_SP_SPACE_INFO *,ulong,_SP_TIER_INFO * * const,_GUID *)

- ea: `0x140010694`
- end: `0x1400107e0`
- name: `?SiCreateDrt@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_SPACE_INFO@@KQEAPEAU_SP_TIER_INFO@@PEAU_GUID@@@Z`
- size: `332`
- prototype: `__int64 __fastcall(struct _SU_POOL_OBJECT *, struct _SP_SPACE_INFO *, __int64, struct _SP_TIER_INFO **const, struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400105bc`

## callees

- `0x140010360`
- `0x140010694`
- `0x14001343c`
- `0x140013ca8`
- `0x140013e6c`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1400107c5`
- `KERNEL32!LocalFree` at `0x1400107c5`

## pseudocode

```c
__int64 __fastcall SiCreateDrt(
        struct _SU_POOL_OBJECT *a1,
        struct _SP_SPACE_INFO *a2,
        __int64 a3,
        struct _SP_TIER_INFO **const a4,
        struct _GUID *a5)
{
  SP_RESILIENCY_INFO *v5; // r14
  unsigned int Child; // edi
  unsigned int TierTemplate; // eax
  char *v10; // rbx
  int v11; // eax
  SP_RESILIENCY_INFO *v12; // r8
  GUID *v13; // r14
  HLOCAL hMem; // [rsp+68h] [rbp+20h] BYREF

  v5 = (struct _SP_SPACE_INFO *)((char *)a2 + 2748);
  hMem = 0;
  Child = 1;
  if ( *((_DWORD *)a2 + 687) == 2 )
  {
    TierTemplate = SuGetTierTemplate(a1, 0, a3, &hMem);
    v10 = (char *)hMem;
    Child = TierTemplate;
    if ( TierTemplate )
    {
      *((_DWORD *)hMem + 654) = 4;
      *((_QWORD *)v10 + 328) = *((_QWORD *)a1 + 342);
      *(_OWORD *)(v10 + 2648) = *(_OWORD *)((char *)a2 + 2696);
      *(_OWORD *)(v10 + 2664) = *(_OWORD *)((char *)a2 + 2712);
      *((_DWORD *)v10 + 662) = 2;
      *((_QWORD *)v10 + 332) = *((_QWORD *)a1 + 342);
      *((_DWORD *)v10 + 666) = 60;
      *(_OWORD *)(v10 + 2692) = *(_OWORD *)v5;
      *(_QWORD *)(v10 + 2708) = *((_QWORD *)v5 + 2);
      *((_DWORD *)v10 + 677) = 1;
      v11 = SP_RESILIENCY_INFO::NumberOfLogicalCopies(v5);
      SP_RESILIENCY_INFO::SetNumberOfCopies(v12, v11 + *((_DWORD *)a2 + 700) - 1);
      v13 = a5;
      Child = SiCreateChild((__int64)a1, (__int64)a2, 6u, (__int64)v10, a5);
      if ( !Child )
      {
        *((_DWORD *)v10 + 666) = 0;
        Child = SiCreateChild((__int64)a1, (__int64)a2, 6u, (__int64)v10, v13);
      }
    }
    if ( v10 )
      LocalFree(v10);
  }
  return Child;
}

```

## disassembly

```asm
0x140010694  mov     rax, rsp
0x140010697  mov     [rax+8], rbx
0x14001069b  mov     [rax+10h], rbp
0x14001069f  mov     [rax+20h], r9
0x1400106a3  push    rsi
0x1400106a4  push    rdi
0x1400106a5  push    r14
0x1400106a7  sub     rsp, 30h
0x1400106ab  lea     r14, [rdx+0ABCh]
0x1400106b2  mov     qword ptr [rax+20h], 0
0x1400106ba  cmp     dword ptr [r14], 2
0x1400106be  mov     rsi, rdx
0x1400106c1  mov     rbp, rcx
0x1400106c4  mov     edi, 1
0x1400106c9  jnz     loc_1400107CB
0x1400106cf  lea     r9, [rax+20h]
0x1400106d3  xor     edx, edx
0x1400106d5  call    ?SuGetTierTemplate@@YAHPEAU_SU_POOL_OBJECT@@W4_SP_RESILIENCY_TYPE@@PEAU_SP_FD_IDS@@PEAPEAU_SP_TIER_INFO@@@Z; SuGetTierTemplate(_SU_POOL_OBJECT *,_SP_RESILIENCY_TYPE,_SP_FD_IDS *,_SP_TIER_INFO * *)
0x1400106da  mov     rbx, [rsp+48h+hMem]
0x1400106df  mov     edi, eax
0x1400106e1  test    eax, eax
0x1400106e3  jz      loc_1400107BD
0x1400106e9  mov     dword ptr [rbx+0A38h], 4
0x1400106f3  lea     r8, [rbx+0A84h]
0x1400106fa  mov     rax, [rbp+0AB0h]
0x140010701  mov     rcx, r14; this
0x140010704  mov     [rbx+0A40h], rax
0x14001070b  movups  xmm0, xmmword ptr [rsi+0A88h]
0x140010712  movups  xmmword ptr [rbx+0A58h], xmm0
0x140010719  movups  xmm1, xmmword ptr [rsi+0A98h]
0x140010720  movups  xmmword ptr [rbx+0A68h], xmm1
0x140010727  mov     dword ptr [rbx+0A58h], 2
0x140010731  mov     rax, [rbp+0AB0h]
0x140010738  mov     [rbx+0A60h], rax
0x14001073f  mov     dword ptr [rbx+0A68h], 3Ch ; '<'
0x140010749  movups  xmm0, xmmword ptr [r14]
0x14001074d  movups  xmmword ptr [r8], xmm0
0x140010751  movsd   xmm1, qword ptr [r14+10h]
0x140010757  movsd   qword ptr [r8+10h], xmm1
0x14001075d  mov     dword ptr [rbx+0A94h], 1
0x140010767  call    ?NumberOfLogicalCopies@SP_RESILIENCY_INFO@@QEAAKXZ; SP_RESILIENCY_INFO::NumberOfLogicalCopies(void)
0x14001076c  mov     edx, [rsi+0AF0h]
0x140010772  mov     rcx, r8; this
0x140010775  dec     edx
0x140010777  add     edx, eax; unsigned int
0x140010779  call    ?SetNumberOfCopies@SP_RESILIENCY_INFO@@QEAAXK@Z; SP_RESILIENCY_INFO::SetNumberOfCopies(ulong)
0x14001077e  mov     r14, [rsp+48h+arg_20]
0x140010783  mov     r9, rbx
0x140010786  mov     r8b, 6
0x140010789  mov     [rsp+48h+var_28], r14
0x14001078e  mov     rdx, rsi
0x140010791  mov     rcx, rbp
0x140010794  call    ?SiCreateChild@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_SPACE_INFO@@W4_SC_SPACE_USAGE@@PEAU_SP_TIER_INFO@@PEAU_GUID@@@Z; SiCreateChild(_SU_POOL_OBJECT *,_SP_SPACE_INFO *,_SC_SPACE_USAGE,_SP_TIER_INFO *,_GUID *)
0x140010799  mov     edi, eax
0x14001079b  test    eax, eax
0x14001079d  jnz     short loc_1400107BD
0x14001079f  mov     r9, rbx
0x1400107a2  mov     [rbx+0A68h], eax
0x1400107a8  mov     r8b, 6
0x1400107ab  mov     [rsp+48h+var_28], r14
0x1400107b0  mov     rdx, rsi
0x1400107b3  mov     rcx, rbp
0x1400107b6  call    ?SiCreateChild@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_SPACE_INFO@@W4_SC_SPACE_USAGE@@PEAU_SP_TIER_INFO@@PEAU_GUID@@@Z; SiCreateChild(_SU_POOL_OBJECT *,_SP_SPACE_INFO *,_SC_SPACE_USAGE,_SP_TIER_INFO *,_GUID *)
0x1400107bb  mov     edi, eax
0x1400107bd  test    rbx, rbx
0x1400107c0  jz      short loc_1400107CB
0x1400107c2  mov     rcx, rbx; hMem
0x1400107c5  call    cs:__imp_LocalFree
0x1400107cb  mov     rbx, [rsp+48h+arg_0]
0x1400107d0  mov     eax, edi
0x1400107d2  mov     rbp, [rsp+48h+arg_8]
0x1400107d7  add     rsp, 30h
0x1400107db  pop     r14
0x1400107dd  pop     rdi
0x1400107de  pop     rsi
0x1400107df  retn
```
