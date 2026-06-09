# SiCreateCacheLog(_SU_POOL_OBJECT *,_SP_SPACE_INFO *,ulong,_SP_TIER_INFO * * const,_GUID *)

- ea: `0x140010104`
- end: `0x140010357`
- name: `?SiCreateCacheLog@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_SPACE_INFO@@KQEAPEAU_SP_TIER_INFO@@PEAU_GUID@@@Z`
- size: `595`
- prototype: `__int64 __fastcall(struct _SU_POOL_OBJECT *, struct _SP_SPACE_INFO *, unsigned int, struct _SP_TIER_INFO **const, struct _GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1400105bc`

## callees

- `0x1400084ac`
- `0x140010104`
- `0x140010360`
- `0x1400116cc`
- `0x14001343c`
- `0x140013ca8`
- `0x140013e6c`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14001032c`
- `KERNEL32!LocalFree` at `0x14001033a`
- `KERNEL32!LocalFree` at `0x14001032c`
- `KERNEL32!LocalFree` at `0x14001033a`
- `KERNEL32!SetLastError` at `0x1400102f5`
- `KERNEL32!SetLastError` at `0x1400102f5`

## pseudocode

```c
__int64 __fastcall SiCreateCacheLog(
        struct _SU_POOL_OBJECT *a1,
        struct _SP_SPACE_INFO *a2,
        unsigned int a3,
        struct _SP_TIER_INFO **const a4,
        struct _GUID *a5)
{
  unsigned __int64 v5; // rbx
  unsigned int Control; // eax
  _QWORD *v9; // rbp
  unsigned int Child; // esi
  __int64 v11; // rdx
  int v12; // r12d
  __int64 v13; // rdx
  __int64 v14; // r8
  unsigned int TierTemplate; // eax
  char *v16; // rdi
  int v17; // r13d
  __int64 v18; // rax
  __int64 v19; // rcx
  _DWORD *v20; // r8
  __int64 v21; // rax
  __int64 v22; // rax
  int v23; // eax
  SP_RESILIENCY_INFO *v24; // r8
  struct _GUID *v25; // rbx
  __int64 v26; // r8
  __int64 v27; // r8
  HLOCAL hMem; // [rsp+78h] [rbp+10h] BYREF
  unsigned int HighestFaultTolerance; // [rsp+80h] [rbp+18h]
  HLOCAL v31; // [rsp+88h] [rbp+20h] BYREF

  v31 = a4;
  HighestFaultTolerance = a3;
  v5 = *((_QWORD *)a2 + 347);
  v31 = 0;
  hMem = 0;
  Control = SuGetControl((struct _SP_CONTROL_INFO **)&v31);
  v9 = v31;
  Child = Control;
  if ( !Control )
    goto LABEL_22;
  HighestFaultTolerance = SiFindHighestFaultTolerance(0, 0, 0);
  v12 = SiFindHighestFaultTolerance((unsigned int)(v11 + 3), v11, 0);
  TierTemplate = SuGetTierTemplate(a1, v13, v14, &hMem);
  v16 = (char *)hMem;
  Child = TierTemplate;
  if ( TierTemplate )
  {
    v17 = 0;
    if ( v5 == -1 )
    {
      if ( *((_BYTE *)a1 + 2642) && v12 == -1 )
        goto LABEL_20;
      v17 = 1;
      v5 = 0x40000000;
    }
    v18 = 0;
    if ( v12 != -1 )
    {
      if ( !v5 )
        v5 = v9[15];
      v18 = v5 != 0 ? 0xE000000 : 0;
      if ( v5 >= 0x40000000 )
      {
        v18 = 603979776;
LABEL_13:
        v19 = HighestFaultTolerance;
        v20 = (char *)hMem + 2692;
        *((_DWORD *)hMem + 654) = 3;
        *((_QWORD *)v16 + 328) = v5 + v18;
        v21 = *(_QWORD *)(8 * v19);
        *(_OWORD *)(v16 + 2648) = *(_OWORD *)(v21 + 2648);
        *(_OWORD *)(v16 + 2664) = *(_OWORD *)(v21 + 2664);
        *((_DWORD *)v16 + 662) = 2;
        *((_QWORD *)v16 + 332) = *((_QWORD *)a1 + 342);
        *((_DWORD *)v16 + 666) = 60;
        v22 = *(_QWORD *)(8 * v19);
        *(_OWORD *)(v16 + 2692) = *(_OWORD *)(v22 + 2692);
        *(_QWORD *)(v16 + 2708) = *(_QWORD *)(v22 + 2708);
        *((_DWORD *)v16 + 677) = 1;
        if ( *((_DWORD *)v16 + 673) == 3 )
        {
          *v20 = 2;
          *((_DWORD *)v16 + 676) = 1;
        }
        v23 = SP_RESILIENCY_INFO::NumberOfLogicalCopies((SP_RESILIENCY_INFO *)(*(_QWORD *)(8 * v19) + 2692LL));
        SP_RESILIENCY_INFO::SetNumberOfCopies(v24, v23 + *((_DWORD *)a2 + 700) - 1);
        *((_QWORD *)a2 + 347) = v5;
        v25 = a5;
        LOBYTE(v26) = 5;
        Child = SiCreateChild(a1, a2, v26, v16, a5);
        if ( !Child )
        {
          if ( v12 == -1 )
          {
            if ( v17 )
            {
              SetLastError(0);
              Child = 1;
            }
          }
          else
          {
            *((_DWORD *)v16 + 666) = 0;
            LOBYTE(v27) = 5;
            Child = SiCreateChild(a1, a2, v27, v16, v25);
          }
        }
        goto LABEL_20;
      }
    }
    if ( v5 )
      goto LABEL_13;
  }
LABEL_20:
  if ( v16 )
    LocalFree(v16);
LABEL_22:
  if ( v9 )
    LocalFree(v9);
  return Child;
}

```

## disassembly

```asm
0x140010104  mov     rax, rsp
0x140010107  mov     [rax+8], rbx
0x14001010b  mov     [rax+20h], r9
0x14001010f  mov     [rax+18h], r8d
0x140010113  push    rbp
0x140010114  push    rsi
0x140010115  push    rdi
0x140010116  push    r12
0x140010118  push    r13
0x14001011a  push    r14
0x14001011c  push    r15
0x14001011e  sub     rsp, 30h
0x140010122  mov     rbx, [rdx+0AD8h]
0x140010129  mov     r14, rcx
0x14001012c  lea     rcx, [rax+20h]; struct _SP_CONTROL_INFO **
0x140010130  mov     qword ptr [rax+20h], 0
0x140010138  mov     r15, rdx
0x14001013b  mov     qword ptr [rax+10h], 0
0x140010143  call    ?SuGetControl@@YAHPEAPEAU_SP_CONTROL_INFO@@@Z; SuGetControl(_SP_CONTROL_INFO * *)
0x140010148  mov     rbp, [rsp+68h+arg_18]
0x140010150  mov     esi, eax
0x140010152  test    eax, eax
0x140010154  jz      loc_140010332
0x14001015a  xor     r8d, r8d
0x14001015d  xor     edx, edx
0x14001015f  xor     ecx, ecx
0x140010161  call    ?SiFindHighestFaultTolerance@@YAKW4_SP_RESILIENCY_TYPE@@KQEAPEAU_SP_TIER_INFO@@@Z; SiFindHighestFaultTolerance(_SP_RESILIENCY_TYPE,ulong,_SP_TIER_INFO * * const)
0x140010166  xor     r8d, r8d
0x140010169  mov     [rsp+68h+arg_10], eax
0x140010170  lea     ecx, [rdx+3]
0x140010173  call    ?SiFindHighestFaultTolerance@@YAKW4_SP_RESILIENCY_TYPE@@KQEAPEAU_SP_TIER_INFO@@@Z; SiFindHighestFaultTolerance(_SP_RESILIENCY_TYPE,ulong,_SP_TIER_INFO * * const)
0x140010178  lea     r9, [rsp+68h+hMem]
0x14001017d  mov     rcx, r14
0x140010180  mov     r12d, eax
0x140010183  call    ?SuGetTierTemplate@@YAHPEAU_SU_POOL_OBJECT@@W4_SP_RESILIENCY_TYPE@@PEAU_SP_FD_IDS@@PEAPEAU_SP_TIER_INFO@@@Z; SuGetTierTemplate(_SU_POOL_OBJECT *,_SP_RESILIENCY_TYPE,_SP_FD_IDS *,_SP_TIER_INFO * *)
0x140010188  mov     rdi, [rsp+68h+hMem]
0x14001018d  mov     esi, eax
0x14001018f  test    eax, eax
0x140010191  jz      loc_140010324
0x140010197  xor     r13d, r13d
0x14001019a  or      ecx, 0FFFFFFFFh
0x14001019d  mov     r8d, 40000000h
0x1400101a3  lea     edx, [r13+1]
0x1400101a7  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1400101ab  jnz     short loc_1400101C5
0x1400101ad  cmp     [r14+0A52h], r13b
0x1400101b4  jz      short loc_1400101BF
0x1400101b6  cmp     r12d, ecx
0x1400101b9  jz      loc_140010324
0x1400101bf  mov     r13d, edx
0x1400101c2  mov     rbx, r8
0x1400101c5  xor     eax, eax
0x1400101c7  cmp     r12d, ecx
0x1400101ca  jz      short loc_1400101EC
0x1400101cc  test    rbx, rbx
0x1400101cf  jnz     short loc_1400101D5
0x1400101d1  mov     rbx, [rbp+78h]
0x1400101d5  cmp     rax, rbx
0x1400101d8  sbb     rax, rax
0x1400101db  and     eax, 0E000000h
0x1400101e0  cmp     rbx, r8
0x1400101e3  jb      short loc_1400101EC
0x1400101e5  mov     eax, 24000000h
0x1400101ea  jmp     short loc_1400101F5
0x1400101ec  test    rbx, rbx
0x1400101ef  jz      loc_140010324
0x1400101f5  mov     ecx, [rsp+68h+arg_10]
0x1400101fc  lea     r8, [rdi+0A84h]
0x140010203  mov     dword ptr [rdi+0A38h], 3
0x14001020d  add     rax, rbx
0x140010210  mov     [rdi+0A40h], rax
0x140010217  mov     r9d, 2
0x14001021d  mov     rax, ds:0[rcx*8]
0x140010225  movups  xmm0, xmmword ptr [rax+0A58h]
0x14001022c  movups  xmmword ptr [rdi+0A58h], xmm0
0x140010233  movups  xmm1, xmmword ptr [rax+0A68h]
0x14001023a  movups  xmmword ptr [rdi+0A68h], xmm1
0x140010241  mov     [rdi+0A58h], r9d
0x140010248  mov     rax, [r14+0AB0h]
0x14001024f  mov     [rdi+0A60h], rax
0x140010256  mov     dword ptr [rdi+0A68h], 3Ch ; '<'
0x140010260  mov     rax, ds:0[rcx*8]
0x140010268  movups  xmm0, xmmword ptr [rax+0A84h]
0x14001026f  movups  xmmword ptr [r8], xmm0
0x140010273  movsd   xmm1, qword ptr [rax+0A94h]
0x14001027b  movsd   qword ptr [r8+10h], xmm1
0x140010281  mov     [rdi+0A94h], edx
0x140010287  cmp     dword ptr [r8], 3
0x14001028b  jnz     short loc_140010296
0x14001028d  mov     [r8], r9d
0x140010290  mov     [rdi+0A90h], edx
0x140010296  mov     rcx, ds:0[rcx*8]
0x14001029e  add     rcx, 0A84h; this
0x1400102a5  call    ?NumberOfLogicalCopies@SP_RESILIENCY_INFO@@QEAAKXZ; SP_RESILIENCY_INFO::NumberOfLogicalCopies(void)
0x1400102aa  mov     edx, [r15+0AF0h]
0x1400102b1  mov     rcx, r8; this
0x1400102b4  dec     edx
0x1400102b6  add     edx, eax; unsigned int
0x1400102b8  call    ?SetNumberOfCopies@SP_RESILIENCY_INFO@@QEAAXK@Z; SP_RESILIENCY_INFO::SetNumberOfCopies(ulong)
0x1400102bd  mov     [r15+0AD8h], rbx
0x1400102c4  mov     r9, rdi
0x1400102c7  mov     rbx, [rsp+68h+arg_20]
0x1400102cf  mov     r8b, 5
0x1400102d2  mov     rdx, r15
0x1400102d5  mov     [rsp+68h+var_48], rbx
0x1400102da  mov     rcx, r14
0x1400102dd  call    ?SiCreateChild@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_SPACE_INFO@@W4_SC_SPACE_USAGE@@PEAU_SP_TIER_INFO@@PEAU_GUID@@@Z; SiCreateChild(_SU_POOL_OBJECT *,_SP_SPACE_INFO *,_SC_SPACE_USAGE,_SP_TIER_INFO *,_GUID *)
0x1400102e2  mov     esi, eax
0x1400102e4  test    eax, eax
0x1400102e6  jnz     short loc_140010324
0x1400102e8  cmp     r12d, 0FFFFFFFFh
0x1400102ec  jnz     short loc_140010302
0x1400102ee  test    r13d, r13d
0x1400102f1  jz      short loc_140010324
0x1400102f3  xor     ecx, ecx; dwErrCode
0x1400102f5  call    cs:__imp_SetLastError
0x1400102fb  mov     esi, 1
0x140010300  jmp     short loc_140010324
0x140010302  mov     r9, rdi
0x140010305  mov     dword ptr [rdi+0A68h], 0
0x14001030f  mov     r8b, 5
0x140010312  mov     [rsp+68h+var_48], rbx
0x140010317  mov     rdx, r15
0x14001031a  mov     rcx, r14
0x14001031d  call    ?SiCreateChild@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_SPACE_INFO@@W4_SC_SPACE_USAGE@@PEAU_SP_TIER_INFO@@PEAU_GUID@@@Z; SiCreateChild(_SU_POOL_OBJECT *,_SP_SPACE_INFO *,_SC_SPACE_USAGE,_SP_TIER_INFO *,_GUID *)
0x140010322  mov     esi, eax
0x140010324  test    rdi, rdi
0x140010327  jz      short loc_140010332
0x140010329  mov     rcx, rdi; hMem
0x14001032c  call    cs:__imp_LocalFree
0x140010332  test    rbp, rbp
0x140010335  jz      short loc_140010340
0x140010337  mov     rcx, rbp; hMem
0x14001033a  call    cs:__imp_LocalFree
0x140010340  mov     rbx, [rsp+68h+arg_0]
0x140010345  mov     eax, esi
0x140010347  add     rsp, 30h
0x14001034b  pop     r15
0x14001034d  pop     r14
0x14001034f  pop     r13
0x140010351  pop     r12
0x140010353  pop     rdi
0x140010354  pop     rsi
0x140010355  pop     rbp
0x140010356  retn
```
