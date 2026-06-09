# SiCreateSst(_SU_POOL_OBJECT *,_SP_SPACE_INFO *,ulong,_SP_TIER_INFO * * const,_GUID *)

- ea: `0x140011248`
- end: `0x140011472`
- name: `?SiCreateSst@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_SPACE_INFO@@KQEAPEAU_SP_TIER_INFO@@PEAU_GUID@@@Z`
- size: `554`
- prototype: `__int64 __fastcall(struct _SU_POOL_OBJECT *, struct _SP_SPACE_INFO *, __int64, struct _SP_TIER_INFO **const, struct _GUID *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x14000fb94`
- `0x1400105bc`

## callees

- `0x140010360`
- `0x140011248`
- `0x1400116cc`
- `0x14001343c`
- `0x140013ca8`
- `0x140013e6c`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140011459`
- `KERNEL32!LocalFree` at `0x140011459`
- `KERNEL32!SetLastError` at `0x140011424`
- `KERNEL32!SetLastError` at `0x140011424`
- `KERNEL32!GetLastError` at `0x140011415`
- `KERNEL32!GetLastError` at `0x140011415`

## pseudocode

```c
__int64 __fastcall SiCreateSst(
        struct _SU_POOL_OBJECT *a1,
        struct _SP_SPACE_INFO *a2,
        __int64 a3,
        struct _SP_TIER_INFO **const a4,
        struct _GUID *a5)
{
  bool v5; // cf
  unsigned int v7; // r14d
  unsigned int Child; // ebx
  char *v11; // rcx
  SP_RESILIENCY_INFO *v12; // r12
  struct _SP_TIER_INFO *v13; // rax
  int v14; // r13d
  __int64 i; // rdi
  struct _SP_TIER_INFO *v16; // r9
  unsigned int TierTemplate; // eax
  char *v18; // rdi
  int v19; // eax
  SP_RESILIENCY_INFO *v20; // r8
  GUID *v21; // r14
  _OWORD *v23; // [rsp+30h] [rbp-58h]
  HLOCAL hMem; // [rsp+90h] [rbp+8h] BYREF

  v5 = *((_DWORD *)a1 + 661) < 0x16u;
  v7 = a3;
  hMem = 0;
  Child = 1;
  if ( !v5 && *((_BYTE *)a1 + 2726) )
  {
    if ( (_DWORD)a3 )
    {
      v13 = a4[(unsigned int)SiFindHighestFaultTolerance(0, (unsigned int)a3, a4)];
      v11 = (char *)v13 + 2648;
      v12 = (struct _SP_TIER_INFO *)((char *)v13 + 2692);
    }
    else
    {
      v11 = (char *)a2 + 2696;
      v12 = (struct _SP_SPACE_INFO *)((char *)a2 + 2748);
    }
    v23 = v11;
    if ( (unsigned int)(*(_DWORD *)v12 - 2) <= 1 )
    {
      v14 = 0;
      for ( i = 0; (unsigned int)i < v7; i = (unsigned int)(i + 1) )
      {
        v16 = a4[i];
        if ( *((_DWORD *)v16 + 654) == 5 )
        {
          if ( !*((_QWORD *)v16 + 328) )
            return Child;
          v14 = 1;
          Child = SiCreateChild((__int64)a1, (__int64)a2, 7u, (__int64)v16, a5);
          if ( !Child )
            return Child;
        }
      }
      if ( !v14 )
      {
        TierTemplate = SuGetTierTemplate(a1, 0, a3, &hMem);
        v18 = (char *)hMem;
        Child = TierTemplate;
        if ( TierTemplate )
        {
          *((_DWORD *)hMem + 654) = 5;
          *((_QWORD *)v18 + 328) = 0x10000000;
          *(_OWORD *)(v18 + 2648) = *v23;
          *(_OWORD *)(v18 + 2664) = v23[1];
          *((_DWORD *)v18 + 662) = 2;
          *((_QWORD *)v18 + 332) = 0x10000000;
          *((_DWORD *)v18 + 666) = 60;
          *(_OWORD *)(v18 + 2692) = *(_OWORD *)v12;
          *(_QWORD *)(v18 + 2708) = *((_QWORD *)v12 + 2);
          *((_DWORD *)v18 + 673) = 2;
          *((_DWORD *)v18 + 676) = 1;
          *((_DWORD *)v18 + 677) = 1;
          v19 = SP_RESILIENCY_INFO::NumberOfLogicalCopies(v12);
          SP_RESILIENCY_INFO::SetNumberOfCopies(v20, v19 + *((_DWORD *)a2 + 700) - 1);
          v21 = a5;
          Child = SiCreateChild((__int64)a1, (__int64)a2, 7u, (__int64)v18, a5);
          if ( !Child )
          {
            if ( GetLastError() == -2132344809 )
            {
              SetLastError(0);
              Child = 1;
            }
            else
            {
              *((_DWORD *)v18 + 666) = 0;
              Child = SiCreateChild((__int64)a1, (__int64)a2, 7u, (__int64)v18, v21);
            }
          }
        }
        if ( v18 )
          LocalFree(v18);
      }
    }
  }
  return Child;
}

```

## disassembly

```asm
0x140011248  mov     rax, rsp
0x14001124b  push    rbx
0x14001124c  push    rbp
0x14001124d  push    rsi
0x14001124e  push    rdi
0x14001124f  push    r12
0x140011251  push    r13
0x140011253  push    r14
0x140011255  push    r15
0x140011257  sub     rsp, 48h
0x14001125b  cmp     dword ptr [rcx+0A54h], 16h
0x140011262  mov     r15, r9
0x140011265  mov     r14d, r8d
0x140011268  mov     qword ptr [rax+8], 0
0x140011270  mov     rbp, rdx
0x140011273  mov     rsi, rcx
0x140011276  mov     ebx, 1
0x14001127b  jb      loc_14001145F
0x140011281  cmp     byte ptr [rcx+0AA6h], 0
0x140011288  jz      loc_14001145F
0x14001128e  test    r8d, r8d
0x140011291  jnz     short loc_1400112A3
0x140011293  lea     rcx, [rdx+0A88h]
0x14001129a  lea     r12, [rdx+0ABCh]
0x1400112a1  jmp     short loc_1400112C4
0x1400112a3  mov     r8, r15
0x1400112a6  mov     edx, r14d
0x1400112a9  xor     ecx, ecx
0x1400112ab  call    ?SiFindHighestFaultTolerance@@YAKW4_SP_RESILIENCY_TYPE@@KQEAPEAU_SP_TIER_INFO@@@Z; SiFindHighestFaultTolerance(_SP_RESILIENCY_TYPE,ulong,_SP_TIER_INFO * * const)
0x1400112b0  mov     edx, eax
0x1400112b2  mov     rax, [r15+rdx*8]
0x1400112b6  lea     rcx, [rax+0A58h]
0x1400112bd  lea     r12, [rax+0A84h]
0x1400112c4  mov     eax, [r12]
0x1400112c8  sub     eax, 2
0x1400112cb  mov     [rsp+88h+var_58], rcx
0x1400112d0  cmp     eax, ebx
0x1400112d2  ja      loc_14001145F
0x1400112d8  xor     r13d, r13d
0x1400112db  xor     edi, edi
0x1400112dd  cmp     edi, r14d
0x1400112e0  jnb     short loc_14001132D
0x1400112e2  mov     r9, [r15+rdi*8]
0x1400112e6  cmp     dword ptr [r9+0A38h], 5
0x1400112ee  jnz     short loc_140011329
0x1400112f0  cmp     qword ptr [r9+0A40h], 0
0x1400112f8  jz      loc_14001145F
0x1400112fe  mov     rax, [rsp+88h+arg_20]
0x140011306  mov     r8b, 7
0x140011309  mov     rdx, rbp
0x14001130c  mov     [rsp+88h+var_68], rax
0x140011311  mov     rcx, rsi
0x140011314  mov     r13d, 1
0x14001131a  call    ?SiCreateChild@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_SPACE_INFO@@W4_SC_SPACE_USAGE@@PEAU_SP_TIER_INFO@@PEAU_GUID@@@Z; SiCreateChild(_SU_POOL_OBJECT *,_SP_SPACE_INFO *,_SC_SPACE_USAGE,_SP_TIER_INFO *,_GUID *)
0x14001131f  mov     ebx, eax
0x140011321  test    eax, eax
0x140011323  jz      loc_14001145F
0x140011329  inc     edi
0x14001132b  jmp     short loc_1400112DD
0x14001132d  test    r13d, r13d
0x140011330  jnz     loc_14001145F
0x140011336  lea     r9, [rsp+88h+hMem]
0x14001133e  xor     edx, edx
0x140011340  mov     rcx, rsi
0x140011343  call    ?SuGetTierTemplate@@YAHPEAU_SU_POOL_OBJECT@@W4_SP_RESILIENCY_TYPE@@PEAU_SP_FD_IDS@@PEAPEAU_SP_TIER_INFO@@@Z; SuGetTierTemplate(_SU_POOL_OBJECT *,_SP_RESILIENCY_TYPE,_SP_FD_IDS *,_SP_TIER_INFO * *)
0x140011348  mov     rdi, [rsp+88h+hMem]
0x140011350  mov     ebx, eax
0x140011352  test    eax, eax
0x140011354  jz      loc_140011451
0x14001135a  mov     rax, [rsp+88h+var_58]
0x14001135f  lea     r8, [rdi+0A84h]
0x140011366  mov     dword ptr [rdi+0A38h], 5
0x140011370  lea     r15d, [r13+1]
0x140011374  mov     ecx, 10000000h
0x140011379  mov     [rdi+0A40h], rcx
0x140011380  movups  xmm0, xmmword ptr [rax]
0x140011383  movups  xmmword ptr [rdi+0A58h], xmm0
0x14001138a  movups  xmm1, xmmword ptr [rax+10h]
0x14001138e  lea     eax, [r13+2]
0x140011392  movups  xmmword ptr [rdi+0A68h], xmm1
0x140011399  mov     [rdi+0A58h], eax
0x14001139f  mov     [rdi+0A60h], rcx
0x1400113a6  mov     rcx, r12; this
0x1400113a9  mov     dword ptr [rdi+0A68h], 3Ch ; '<'
0x1400113b3  movups  xmm0, xmmword ptr [r12]
0x1400113b8  movups  xmmword ptr [r8], xmm0
0x1400113bc  movsd   xmm1, qword ptr [r12+10h]
0x1400113c3  movsd   qword ptr [r8+10h], xmm1
0x1400113c9  mov     [r8], eax
0x1400113cc  mov     [rdi+0A90h], r15d
0x1400113d3  mov     [rdi+0A94h], r15d
0x1400113da  call    ?NumberOfLogicalCopies@SP_RESILIENCY_INFO@@QEAAKXZ; SP_RESILIENCY_INFO::NumberOfLogicalCopies(void)
0x1400113df  mov     edx, [rbp+0AF0h]
0x1400113e5  mov     rcx, r8; this
0x1400113e8  dec     edx
0x1400113ea  add     edx, eax; unsigned int
0x1400113ec  call    ?SetNumberOfCopies@SP_RESILIENCY_INFO@@QEAAXK@Z; SP_RESILIENCY_INFO::SetNumberOfCopies(ulong)
0x1400113f1  mov     r14, [rsp+88h+arg_20]
0x1400113f9  mov     r9, rdi
0x1400113fc  mov     r8b, 7
0x1400113ff  mov     [rsp+88h+var_68], r14
0x140011404  mov     rdx, rbp
0x140011407  mov     rcx, rsi
0x14001140a  call    ?SiCreateChild@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_SPACE_INFO@@W4_SC_SPACE_USAGE@@PEAU_SP_TIER_INFO@@PEAU_GUID@@@Z; SiCreateChild(_SU_POOL_OBJECT *,_SP_SPACE_INFO *,_SC_SPACE_USAGE,_SP_TIER_INFO *,_GUID *)
0x14001140f  mov     ebx, eax
0x140011411  test    eax, eax
0x140011413  jnz     short loc_140011451
0x140011415  call    cs:__imp_GetLastError
0x14001141b  cmp     eax, 80E70017h
0x140011420  jnz     short loc_14001142F
0x140011422  xor     ecx, ecx; dwErrCode
0x140011424  call    cs:__imp_SetLastError
0x14001142a  mov     ebx, r15d
0x14001142d  jmp     short loc_140011451
0x14001142f  mov     r9, rdi
0x140011432  mov     dword ptr [rdi+0A68h], 0
0x14001143c  mov     r8b, 7
0x14001143f  mov     [rsp+88h+var_68], r14
0x140011444  mov     rdx, rbp
0x140011447  mov     rcx, rsi
0x14001144a  call    ?SiCreateChild@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_SPACE_INFO@@W4_SC_SPACE_USAGE@@PEAU_SP_TIER_INFO@@PEAU_GUID@@@Z; SiCreateChild(_SU_POOL_OBJECT *,_SP_SPACE_INFO *,_SC_SPACE_USAGE,_SP_TIER_INFO *,_GUID *)
0x14001144f  mov     ebx, eax
0x140011451  test    rdi, rdi
0x140011454  jz      short loc_14001145F
0x140011456  mov     rcx, rdi; hMem
0x140011459  call    cs:__imp_LocalFree
0x14001145f  mov     eax, ebx
0x140011461  add     rsp, 48h
0x140011465  pop     r15
0x140011467  pop     r14
0x140011469  pop     r13
0x14001146b  pop     r12
0x14001146d  pop     rdi
0x14001146e  pop     rsi
0x14001146f  pop     rbp
0x140011470  pop     rbx
0x140011471  retn
```
