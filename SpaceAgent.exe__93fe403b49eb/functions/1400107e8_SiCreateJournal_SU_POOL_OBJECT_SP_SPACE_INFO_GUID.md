# SiCreateJournal(_SU_POOL_OBJECT *,_SP_SPACE_INFO *,_GUID *)

- ea: `0x1400107e8`
- end: `0x140010a62`
- name: `?SiCreateJournal@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_SPACE_INFO@@PEAU_GUID@@@Z`
- size: `634`
- prototype: `__int64 __fastcall(struct _SU_POOL_OBJECT *, struct _SP_SPACE_INFO *, struct _GUID *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1400105bc`

## callees

- `0x1400084ac`
- `0x140010360`
- `0x1400107e8`
- `0x14001343c`
- `0x140013ca8`
- `0x140013e6c`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140010a37`
- `KERNEL32!LocalFree` at `0x140010a45`
- `KERNEL32!LocalFree` at `0x140010a37`
- `KERNEL32!LocalFree` at `0x140010a45`
- `KERNEL32!SetLastError` at `0x1400109c8`
- `KERNEL32!SetLastError` at `0x1400109c8`

## pseudocode

```c
__int64 __fastcall SiCreateJournal(struct _SU_POOL_OBJECT *a1, struct _SP_SPACE_INFO *a2, struct _GUID *a3)
{
  unsigned __int64 v3; // rbx
  int v5; // r14d
  unsigned int Control; // eax
  __int64 v8; // r8
  _QWORD *v9; // r13
  unsigned int Child; // esi
  unsigned int TierTemplate; // eax
  char *v12; // rdi
  __int64 v13; // rcx
  __int64 v14; // r12
  int v15; // eax
  SP_RESILIENCY_INFO *v16; // r8
  GUID *v18; // [rsp+20h] [rbp-48h]
  GUID *v19; // [rsp+20h] [rbp-48h]
  HLOCAL v20; // [rsp+78h] [rbp+10h] BYREF
  struct _GUID *v21; // [rsp+80h] [rbp+18h]
  HLOCAL hMem; // [rsp+88h] [rbp+20h] BYREF

  v21 = a3;
  v3 = *((_QWORD *)a2 + 347);
  v5 = *((_DWORD *)a2 + 687);
  v20 = 0;
  hMem = 0;
  Control = SuGetControl((struct _SP_CONTROL_INFO **)&v20);
  v9 = v20;
  Child = Control;
  if ( !Control )
    goto LABEL_32;
  TierTemplate = SuGetTierTemplate(a1, 0, v8, &hMem);
  v12 = (char *)hMem;
  Child = TierTemplate;
  if ( TierTemplate )
  {
    v13 = 0;
    if ( v3 == -1 )
    {
      LODWORD(v20) = 1;
      if ( !*((_BYTE *)a1 + 2642) || v5 == 3 )
        v3 = 0x40000000;
      else
        v3 = 0;
    }
    else
    {
      LODWORD(v20) = 0;
    }
    if ( v5 == 2 )
    {
      v14 = 0x4000;
    }
    else
    {
      v14 = 0;
      if ( v5 == 3 )
      {
        if ( !v3 )
          v3 = v9[15];
        v13 = v3 != 0 ? 0xE000000 : 0;
        if ( v3 >= 0x40000000 )
          v13 = 603979776;
      }
    }
    if ( v14 + v3 )
    {
      hMem = (HLOCAL)(v13 + v14);
      *((_QWORD *)v12 + 328) = v3 + v13 + v14;
      *(_OWORD *)(v12 + 2648) = *(_OWORD *)((char *)a2 + 2696);
      *(_OWORD *)(v12 + 2664) = *(_OWORD *)((char *)a2 + 2712);
      *((_DWORD *)v12 + 662) = 2;
      *((_QWORD *)v12 + 332) = *((_QWORD *)a1 + 342);
      *((_DWORD *)v12 + 666) = 60;
      *(_OWORD *)(v12 + 2692) = *(_OWORD *)((char *)a2 + 2748);
      *(_QWORD *)(v12 + 2708) = *(_QWORD *)((char *)a2 + 2764);
      *((_DWORD *)v12 + 677) = 1;
      if ( v5 == 3 )
      {
        *((_DWORD *)v12 + 673) = 2;
        *((_DWORD *)v12 + 676) = 1;
      }
      v15 = SP_RESILIENCY_INFO::NumberOfLogicalCopies((struct _SP_SPACE_INFO *)((char *)a2 + 2748));
      SP_RESILIENCY_INFO::SetNumberOfCopies(v16, v15 + *((_DWORD *)a2 + 700) - 1);
      if ( !v3 )
        *((_DWORD *)v12 + 678) = 0x1000000;
      v18 = v21;
      *((_QWORD *)a2 + 347) = v3;
      Child = SiCreateChild((__int64)a1, (__int64)a2, 3u, (__int64)v12, v18);
      if ( !Child )
      {
        if ( v5 == 3 )
        {
LABEL_27:
          *((_QWORD *)v12 + 328) = (char *)hMem + v3;
          *((_DWORD *)v12 + 666) = 0;
          if ( !v3 )
            *((_DWORD *)v12 + 678) = 0x1000000;
          v19 = v21;
          *((_QWORD *)a2 + 347) = v3;
          Child = SiCreateChild((__int64)a1, (__int64)a2, 3u, (__int64)v12, v19);
          goto LABEL_30;
        }
        if ( (_DWORD)v20 )
        {
          v3 = 0;
          SetLastError(0);
          Child = 1;
        }
        else if ( v3 )
        {
          goto LABEL_30;
        }
        if ( v14 )
          goto LABEL_27;
      }
    }
  }
LABEL_30:
  if ( v12 )
    LocalFree(v12);
LABEL_32:
  if ( v9 )
    LocalFree(v9);
  return Child;
}

```

## disassembly

```asm
0x1400107e8  mov     rax, rsp
0x1400107eb  mov     [rax+8], rbx
0x1400107ef  mov     [rax+18h], r8
0x1400107f3  push    rbp
0x1400107f4  push    rsi
0x1400107f5  push    rdi
0x1400107f6  push    r12
0x1400107f8  push    r13
0x1400107fa  push    r14
0x1400107fc  push    r15
0x1400107fe  sub     rsp, 30h
0x140010802  mov     rbx, [rdx+0AD8h]
0x140010809  mov     r15, rcx
0x14001080c  mov     r14d, [rdx+0ABCh]
0x140010813  lea     rcx, [rax+10h]; struct _SP_CONTROL_INFO **
0x140010817  mov     rbp, rdx
0x14001081a  mov     qword ptr [rax+10h], 0
0x140010822  mov     qword ptr [rax+20h], 0
0x14001082a  call    ?SuGetControl@@YAHPEAPEAU_SP_CONTROL_INFO@@@Z; SuGetControl(_SP_CONTROL_INFO * *)
0x14001082f  mov     r13, [rsp+68h+arg_8]
0x140010834  mov     esi, eax
0x140010836  test    eax, eax
0x140010838  jz      loc_140010A3D
0x14001083e  lea     r9, [rsp+68h+hMem]
0x140010846  xor     edx, edx
0x140010848  mov     rcx, r15
0x14001084b  call    ?SuGetTierTemplate@@YAHPEAU_SU_POOL_OBJECT@@W4_SP_RESILIENCY_TYPE@@PEAU_SP_FD_IDS@@PEAPEAU_SP_TIER_INFO@@@Z; SuGetTierTemplate(_SU_POOL_OBJECT *,_SP_RESILIENCY_TYPE,_SP_FD_IDS *,_SP_TIER_INFO * *)
0x140010850  mov     rdi, [rsp+68h+hMem]
0x140010858  mov     esi, eax
0x14001085a  test    eax, eax
0x14001085c  jz      loc_140010A2F
0x140010862  xor     ecx, ecx
0x140010864  mov     r8d, 40000000h
0x14001086a  lea     edx, [rcx+1]
0x14001086d  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140010871  jnz     short loc_14001088F
0x140010873  mov     dword ptr [rsp+68h+arg_8], edx
0x140010877  cmp     [r15+0A52h], cl
0x14001087e  jz      short loc_14001088A
0x140010880  cmp     r14d, 3
0x140010884  jz      short loc_14001088A
0x140010886  xor     ebx, ebx
0x140010888  jmp     short loc_140010893
0x14001088a  mov     rbx, r8
0x14001088d  jmp     short loc_140010893
0x14001088f  mov     dword ptr [rsp+68h+arg_8], ecx
0x140010893  mov     r9d, 2
0x140010899  cmp     r14d, r9d
0x14001089c  jnz     short loc_1400108A6
0x14001089e  mov     r12d, 4000h
0x1400108a4  jmp     short loc_1400108D1
0x1400108a6  xor     r12d, r12d
0x1400108a9  cmp     r14d, 3
0x1400108ad  jnz     short loc_1400108D1
0x1400108af  test    rbx, rbx
0x1400108b2  jnz     short loc_1400108B8
0x1400108b4  mov     rbx, [r13+78h]
0x1400108b8  xor     eax, eax
0x1400108ba  cmp     rax, rbx
0x1400108bd  mov     eax, 24000000h
0x1400108c2  sbb     rcx, rcx
0x1400108c5  and     ecx, 0E000000h
0x1400108cb  cmp     rbx, r8
0x1400108ce  cmovnb  ecx, eax
0x1400108d1  lea     rax, [r12+rbx]
0x1400108d5  test    rax, rax
0x1400108d8  jz      loc_140010A2F
0x1400108de  lea     rax, [rcx+r12]
0x1400108e2  mov     [rsp+68h+hMem], rax
0x1400108ea  lea     r8, [rdi+0A84h]
0x1400108f1  add     rax, rbx
0x1400108f4  mov     [rdi+0A40h], rax
0x1400108fb  movups  xmm0, xmmword ptr [rbp+0A88h]
0x140010902  movups  xmmword ptr [rdi+0A58h], xmm0
0x140010909  movups  xmm1, xmmword ptr [rbp+0A98h]
0x140010910  movups  xmmword ptr [rdi+0A68h], xmm1
0x140010917  mov     [rdi+0A58h], r9d
0x14001091e  mov     rax, [r15+0AB0h]
0x140010925  mov     [rdi+0A60h], rax
0x14001092c  lea     rax, [rbp+0ABCh]
0x140010933  mov     dword ptr [rdi+0A68h], 3Ch ; '<'
0x14001093d  movups  xmm0, xmmword ptr [rax]
0x140010940  movups  xmmword ptr [r8], xmm0
0x140010944  movsd   xmm1, qword ptr [rax+10h]
0x140010949  movsd   qword ptr [r8+10h], xmm1
0x14001094f  mov     [rdi+0A94h], edx
0x140010955  cmp     r14d, 3
0x140010959  jnz     short loc_140010964
0x14001095b  mov     [r8], r9d
0x14001095e  mov     [rdi+0A90h], edx
0x140010964  mov     rcx, rax; this
0x140010967  call    ?NumberOfLogicalCopies@SP_RESILIENCY_INFO@@QEAAKXZ; SP_RESILIENCY_INFO::NumberOfLogicalCopies(void)
0x14001096c  mov     edx, [rbp+0AF0h]
0x140010972  mov     rcx, r8; this
0x140010975  dec     edx
0x140010977  add     edx, eax; unsigned int
0x140010979  call    ?SetNumberOfCopies@SP_RESILIENCY_INFO@@QEAAXK@Z; SP_RESILIENCY_INFO::SetNumberOfCopies(ulong)
0x14001097e  test    rbx, rbx
0x140010981  jnz     short loc_14001098D
0x140010983  mov     dword ptr [rdi+0A98h], 1000000h
0x14001098d  mov     rax, [rsp+68h+arg_10]
0x140010995  mov     r9, rdi
0x140010998  mov     r8b, 3
0x14001099b  mov     [rsp+68h+var_48], rax
0x1400109a0  mov     rdx, rbp
0x1400109a3  mov     [rbp+0AD8h], rbx
0x1400109aa  mov     rcx, r15
0x1400109ad  call    ?SiCreateChild@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_SPACE_INFO@@W4_SC_SPACE_USAGE@@PEAU_SP_TIER_INFO@@PEAU_GUID@@@Z; SiCreateChild(_SU_POOL_OBJECT *,_SP_SPACE_INFO *,_SC_SPACE_USAGE,_SP_TIER_INFO *,_GUID *)
0x1400109b2  mov     esi, eax
0x1400109b4  test    eax, eax
0x1400109b6  jnz     short loc_140010A2F
0x1400109b8  cmp     r14d, 3
0x1400109bc  jz      short loc_1400109DD
0x1400109be  cmp     dword ptr [rsp+68h+arg_8], eax
0x1400109c2  jz      short loc_1400109D3
0x1400109c4  xor     ebx, ebx
0x1400109c6  xor     ecx, ecx; dwErrCode
0x1400109c8  call    cs:__imp_SetLastError
0x1400109ce  lea     esi, [rbx+1]
0x1400109d1  jmp     short loc_1400109D8
0x1400109d3  test    rbx, rbx
0x1400109d6  jnz     short loc_140010A2F
0x1400109d8  test    r12, r12
0x1400109db  jz      short loc_140010A2F
0x1400109dd  mov     rax, [rsp+68h+hMem]
0x1400109e5  add     rax, rbx
0x1400109e8  mov     [rdi+0A40h], rax
0x1400109ef  mov     dword ptr [rdi+0A68h], 0
0x1400109f9  test    rbx, rbx
0x1400109fc  jnz     short loc_140010A08
0x1400109fe  mov     dword ptr [rdi+0A98h], 1000000h
0x140010a08  mov     rax, [rsp+68h+arg_10]
0x140010a10  mov     r9, rdi
0x140010a13  mov     r8b, 3
0x140010a16  mov     [rsp+68h+var_48], rax
0x140010a1b  mov     rdx, rbp
0x140010a1e  mov     [rbp+0AD8h], rbx
0x140010a25  mov     rcx, r15
0x140010a28  call    ?SiCreateChild@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_SPACE_INFO@@W4_SC_SPACE_USAGE@@PEAU_SP_TIER_INFO@@PEAU_GUID@@@Z; SiCreateChild(_SU_POOL_OBJECT *,_SP_SPACE_INFO *,_SC_SPACE_USAGE,_SP_TIER_INFO *,_GUID *)
0x140010a2d  mov     esi, eax
0x140010a2f  test    rdi, rdi
0x140010a32  jz      short loc_140010A3D
0x140010a34  mov     rcx, rdi; hMem
0x140010a37  call    cs:__imp_LocalFree
0x140010a3d  test    r13, r13
0x140010a40  jz      short loc_140010A4B
0x140010a42  mov     rcx, r13; hMem
0x140010a45  call    cs:__imp_LocalFree
0x140010a4b  mov     rbx, [rsp+68h+arg_0]
0x140010a50  mov     eax, esi
0x140010a52  add     rsp, 30h
0x140010a56  pop     r15
0x140010a58  pop     r14
0x140010a5a  pop     r13
0x140010a5c  pop     r12
0x140010a5e  pop     rdi
0x140010a5f  pop     rsi
0x140010a60  pop     rbp
0x140010a61  retn
```
