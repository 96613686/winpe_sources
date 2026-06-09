# SiCreateReadCache(_SU_POOL_OBJECT *,_SP_SPACE_INFO *,ulong,_SP_TIER_INFO * * const,_GUID *)

- ea: `0x140010a68`
- end: `0x140010b56`
- name: `?SiCreateReadCache@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_SPACE_INFO@@KQEAPEAU_SP_TIER_INFO@@PEAU_GUID@@@Z`
- size: `238`
- prototype: `__int64 __fastcall(struct _SU_POOL_OBJECT *, struct _SP_SPACE_INFO *, __int64, struct _SP_TIER_INFO **const, struct _GUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400105bc`

## callees

- `0x140010360`
- `0x140010a68`
- `0x14001343c`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140010b41`
- `KERNEL32!LocalFree` at `0x140010b41`

## pseudocode

```c
__int64 __fastcall SiCreateReadCache(
        struct _SU_POOL_OBJECT *a1,
        struct _SP_SPACE_INFO *a2,
        __int64 a3,
        struct _SP_TIER_INFO **const a4,
        struct _GUID *a5)
{
  __int64 v5; // rbp
  unsigned int Child; // edi
  unsigned int TierTemplate; // eax
  _QWORD *v10; // rbx
  HLOCAL v11; // r9
  GUID *v12; // rax
  HLOCAL hMem; // [rsp+88h] [rbp+20h] BYREF

  hMem = a4;
  v5 = *((_QWORD *)a2 + 349);
  hMem = 0;
  Child = 1;
  if ( v5 )
  {
    TierTemplate = SuGetTierTemplate(a1, 0, a3, &hMem);
    v10 = hMem;
    Child = TierTemplate;
    if ( TierTemplate )
    {
      v11 = hMem;
      *((_DWORD *)hMem + 654) = 2;
      v10[328] = v5;
      *((_DWORD *)v10 + 662) = 2;
      v12 = a5;
      v10[332] = 0x40000000;
      *((_DWORD *)v10 + 666) = 60;
      *(_QWORD *)((char *)v10 + 2668) = 1;
      *((_DWORD *)v10 + 669) = 1;
      *(_QWORD *)((char *)v10 + 2692) = 1;
      *((_DWORD *)v10 + 675) = 1;
      *((_DWORD *)v10 + 676) = 1;
      *((_DWORD *)v10 + 677) = 1;
      *((_QWORD *)a2 + 349) = v5;
      Child = SiCreateChild((__int64)a1, (__int64)a2, 4u, (__int64)v11, v12);
    }
    if ( v10 )
      LocalFree(v10);
  }
  return Child;
}

```

## disassembly

```asm
0x140010a68  mov     rax, rsp
0x140010a6b  mov     [rax+20h], r9
0x140010a6f  push    rbx
0x140010a70  push    rbp
0x140010a71  push    rsi
0x140010a72  push    rdi
0x140010a73  push    r12
0x140010a75  push    r14
0x140010a77  sub     rsp, 38h
0x140010a7b  mov     rbp, [rdx+0AE8h]
0x140010a82  mov     r12d, 1
0x140010a88  mov     qword ptr [rax+20h], 0
0x140010a90  mov     rsi, rdx
0x140010a93  mov     r14, rcx
0x140010a96  mov     edi, r12d
0x140010a99  test    rbp, rbp
0x140010a9c  jz      loc_140010B47
0x140010aa2  lea     r9, [rax+20h]
0x140010aa6  xor     edx, edx
0x140010aa8  call    ?SuGetTierTemplate@@YAHPEAU_SU_POOL_OBJECT@@W4_SP_RESILIENCY_TYPE@@PEAU_SP_FD_IDS@@PEAPEAU_SP_TIER_INFO@@@Z; SuGetTierTemplate(_SU_POOL_OBJECT *,_SP_RESILIENCY_TYPE,_SP_FD_IDS *,_SP_TIER_INFO * *)
0x140010aad  mov     rbx, [rsp+68h+hMem]
0x140010ab5  mov     edi, eax
0x140010ab7  test    eax, eax
0x140010ab9  jz      short loc_140010B39
0x140010abb  lea     eax, [r12+1]
0x140010ac0  mov     r9, rbx
0x140010ac3  mov     [rbx+0A38h], eax
0x140010ac9  mov     r8b, 4
0x140010acc  mov     [rbx+0A40h], rbp
0x140010ad3  mov     rdx, rsi
0x140010ad6  mov     [rbx+0A58h], eax
0x140010adc  mov     rcx, r14
0x140010adf  mov     rax, [rsp+68h+arg_20]
0x140010ae7  mov     qword ptr [rbx+0A60h], 40000000h
0x140010af2  mov     dword ptr [rbx+0A68h], 3Ch ; '<'
0x140010afc  mov     [rbx+0A6Ch], r12
0x140010b03  mov     [rbx+0A74h], r12d
0x140010b0a  mov     [rbx+0A84h], r12
0x140010b11  mov     [rbx+0A8Ch], r12d
0x140010b18  mov     [rbx+0A90h], r12d
0x140010b1f  mov     [rbx+0A94h], r12d
0x140010b26  mov     [rsi+0AE8h], rbp
0x140010b2d  mov     [rsp+68h+var_48], rax
0x140010b32  call    ?SiCreateChild@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_SPACE_INFO@@W4_SC_SPACE_USAGE@@PEAU_SP_TIER_INFO@@PEAU_GUID@@@Z; SiCreateChild(_SU_POOL_OBJECT *,_SP_SPACE_INFO *,_SC_SPACE_USAGE,_SP_TIER_INFO *,_GUID *)
0x140010b37  mov     edi, eax
0x140010b39  test    rbx, rbx
0x140010b3c  jz      short loc_140010B47
0x140010b3e  mov     rcx, rbx; hMem
0x140010b41  call    cs:__imp_LocalFree
0x140010b47  mov     eax, edi
0x140010b49  add     rsp, 38h
0x140010b4d  pop     r14
0x140010b4f  pop     r12
0x140010b51  pop     rdi
0x140010b52  pop     rsi
0x140010b53  pop     rbp
0x140010b54  pop     rbx
0x140010b55  retn
```
