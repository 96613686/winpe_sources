# SiCreateVdt(_SU_POOL_OBJECT *,_SP_SPACE_INFO *,ulong,_SP_TIER_INFO * * const,_GUID *)

- ea: `0x1400114f8`
- end: `0x140011633`
- name: `?SiCreateVdt@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_SPACE_INFO@@KQEAPEAU_SP_TIER_INFO@@PEAU_GUID@@@Z`
- size: `315`
- prototype: `__int64 __fastcall(struct _SU_POOL_OBJECT *, struct _SP_SPACE_INFO *, __int64, struct _SP_TIER_INFO **const, struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400105bc`

## callees

- `0x140010360`
- `0x1400114f8`
- `0x14001343c`
- `0x140013ca8`
- `0x140013e6c`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140011618`
- `KERNEL32!LocalFree` at `0x140011618`

## pseudocode

```c
__int64 __fastcall SiCreateVdt(
        struct _SU_POOL_OBJECT *a1,
        struct _SP_SPACE_INFO *a2,
        __int64 a3,
        struct _SP_TIER_INFO **const a4,
        struct _GUID *a5)
{
  bool v5; // zf
  unsigned int Child; // esi
  SP_RESILIENCY_INFO *v9; // r14
  unsigned int TierTemplate; // eax
  _QWORD *v11; // rbx
  int v12; // eax
  SP_RESILIENCY_INFO *v13; // r8
  GUID *v14; // r14
  HLOCAL hMem; // [rsp+68h] [rbp+20h] BYREF

  hMem = a4;
  v5 = *((_QWORD *)a2 + 347) == 0;
  hMem = 0;
  Child = 1;
  if ( !v5 )
  {
    v9 = (struct _SP_SPACE_INFO *)((char *)a2 + 2748);
    if ( *((_DWORD *)a2 + 687) == 3 || (*((_BYTE *)a2 + 2868) & 0x20) != 0 )
    {
      TierTemplate = SuGetTierTemplate(a1, (unsigned int)(*(_DWORD *)v9 != 1) + 1, a3, &hMem);
      v11 = hMem;
      Child = TierTemplate;
      if ( TierTemplate )
      {
        *((_DWORD *)hMem + 654) = 6;
        v11[328] = 0x10000000;
        *((_DWORD *)v11 + 662) = 2;
        v11[332] = 0x10000000;
        *((_DWORD *)v11 + 666) = 60;
        *((_DWORD *)v11 + 677) = 1;
        *((_DWORD *)v11 + 678) = *((_DWORD *)v9 + 5);
        v12 = SP_RESILIENCY_INFO::NumberOfLogicalCopies(v9);
        SP_RESILIENCY_INFO::SetNumberOfCopies(v13, v12 + *((_DWORD *)a2 + 700) - 1);
        v14 = a5;
        Child = SiCreateChild((__int64)a1, (__int64)a2, 0xAu, (__int64)v11, a5);
        if ( !Child )
        {
          *((_DWORD *)v11 + 666) = 0;
          Child = SiCreateChild((__int64)a1, (__int64)a2, 0xAu, (__int64)v11, v14);
        }
      }
      if ( v11 )
        LocalFree(v11);
    }
  }
  return Child;
}

```

## disassembly

```asm
0x1400114f8  mov     rax, rsp
0x1400114fb  mov     [rax+8], rbx
0x1400114ff  mov     [rax+10h], rbp
0x140011503  mov     [rax+20h], r9
0x140011507  push    rsi
0x140011508  push    rdi
0x140011509  push    r14
0x14001150b  sub     rsp, 30h
0x14001150f  cmp     qword ptr [rdx+0AD8h], 0
0x140011517  mov     rdi, rdx
0x14001151a  mov     rbp, rcx
0x14001151d  mov     qword ptr [rax+20h], 0
0x140011525  mov     esi, 1
0x14001152a  jz      loc_14001161E
0x140011530  lea     r14, [rdx+0ABCh]
0x140011537  cmp     dword ptr [r14], 3
0x14001153b  jz      short loc_14001154A
0x14001153d  test    byte ptr [rdx+0B34h], 20h
0x140011544  jz      loc_14001161E
0x14001154a  xor     edx, edx
0x14001154c  lea     r9, [rsp+48h+hMem]
0x140011551  cmp     [r14], esi
0x140011554  setnz   dl
0x140011557  inc     edx
0x140011559  call    ?SuGetTierTemplate@@YAHPEAU_SU_POOL_OBJECT@@W4_SP_RESILIENCY_TYPE@@PEAU_SP_FD_IDS@@PEAPEAU_SP_TIER_INFO@@@Z; SuGetTierTemplate(_SU_POOL_OBJECT *,_SP_RESILIENCY_TYPE,_SP_FD_IDS *,_SP_TIER_INFO * *)
0x14001155e  mov     rbx, [rsp+48h+hMem]
0x140011563  mov     esi, eax
0x140011565  test    eax, eax
0x140011567  jz      loc_140011610
0x14001156d  mov     dword ptr [rbx+0A38h], 6
0x140011577  lea     r8, [rbx+0A84h]
0x14001157e  mov     eax, 10000000h
0x140011583  mov     rcx, r14; this
0x140011586  mov     [rbx+0A40h], rax
0x14001158d  mov     dword ptr [rbx+0A58h], 2
0x140011597  mov     [rbx+0A60h], rax
0x14001159e  mov     dword ptr [rbx+0A68h], 3Ch ; '<'
0x1400115a8  mov     dword ptr [r8+10h], 1
0x1400115b0  mov     eax, [r14+14h]
0x1400115b4  mov     [rbx+0A98h], eax
0x1400115ba  call    ?NumberOfLogicalCopies@SP_RESILIENCY_INFO@@QEAAKXZ; SP_RESILIENCY_INFO::NumberOfLogicalCopies(void)
0x1400115bf  mov     edx, [rdi+0AF0h]
0x1400115c5  mov     rcx, r8; this
0x1400115c8  dec     edx
0x1400115ca  add     edx, eax; unsigned int
0x1400115cc  call    ?SetNumberOfCopies@SP_RESILIENCY_INFO@@QEAAXK@Z; SP_RESILIENCY_INFO::SetNumberOfCopies(ulong)
0x1400115d1  mov     r14, [rsp+48h+arg_20]
0x1400115d6  mov     r9, rbx
0x1400115d9  mov     r8b, 0Ah
0x1400115dc  mov     [rsp+48h+var_28], r14
0x1400115e1  mov     rdx, rdi
0x1400115e4  mov     rcx, rbp
0x1400115e7  call    ?SiCreateChild@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_SPACE_INFO@@W4_SC_SPACE_USAGE@@PEAU_SP_TIER_INFO@@PEAU_GUID@@@Z; SiCreateChild(_SU_POOL_OBJECT *,_SP_SPACE_INFO *,_SC_SPACE_USAGE,_SP_TIER_INFO *,_GUID *)
0x1400115ec  mov     esi, eax
0x1400115ee  test    eax, eax
0x1400115f0  jnz     short loc_140011610
0x1400115f2  mov     r9, rbx
0x1400115f5  mov     [rbx+0A68h], eax
0x1400115fb  mov     r8b, 0Ah
0x1400115fe  mov     [rsp+48h+var_28], r14
0x140011603  mov     rdx, rdi
0x140011606  mov     rcx, rbp
0x140011609  call    ?SiCreateChild@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_SPACE_INFO@@W4_SC_SPACE_USAGE@@PEAU_SP_TIER_INFO@@PEAU_GUID@@@Z; SiCreateChild(_SU_POOL_OBJECT *,_SP_SPACE_INFO *,_SC_SPACE_USAGE,_SP_TIER_INFO *,_GUID *)
0x14001160e  mov     esi, eax
0x140011610  test    rbx, rbx
0x140011613  jz      short loc_14001161E
0x140011615  mov     rcx, rbx; hMem
0x140011618  call    cs:__imp_LocalFree
0x14001161e  mov     rbx, [rsp+48h+arg_0]
0x140011623  mov     eax, esi
0x140011625  mov     rbp, [rsp+48h+arg_8]
0x14001162a  add     rsp, 30h
0x14001162e  pop     r14
0x140011630  pop     rdi
0x140011631  pop     rsi
0x140011632  retn
```
