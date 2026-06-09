# SiCreateCacheLines(_SU_POOL_OBJECT *,_SP_SPACE_INFO *,ulong,_SP_TIER_INFO * * const,_GUID *)

- ea: `0x14000fed8`
- end: `0x1400100fd`
- name: `?SiCreateCacheLines@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_SPACE_INFO@@KQEAPEAU_SP_TIER_INFO@@PEAU_GUID@@@Z`
- size: `549`
- prototype: `__int64 __fastcall(struct _SU_POOL_OBJECT *, struct _SP_SPACE_INFO *, __int64, struct _SP_TIER_INFO **const, struct _GUID *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1400105bc`

## callees

- `0x1400084ac`
- `0x14000fed8`
- `0x140010360`
- `0x14001343c`
- `0x140013ca8`
- `0x140013e6c`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1400100cf`
- `KERNEL32!LocalFree` at `0x1400100dd`
- `KERNEL32!LocalFree` at `0x1400100cf`
- `KERNEL32!LocalFree` at `0x1400100dd`
- `KERNEL32!SetLastError` at `0x14000ff86`
- `KERNEL32!SetLastError` at `0x140010086`
- `KERNEL32!SetLastError` at `0x14000ff86`
- `KERNEL32!SetLastError` at `0x140010086`

## pseudocode

```c
__int64 __fastcall SiCreateCacheLines(
        struct _SU_POOL_OBJECT *a1,
        struct _SP_SPACE_INFO *a2,
        __int64 a3,
        struct _SP_TIER_INFO **const a4,
        struct _GUID *a5)
{
  __int64 v5; // rbx
  __int64 v7; // r12
  unsigned int Control; // eax
  __int64 v10; // r8
  HLOCAL v11; // r13
  unsigned int Child; // esi
  int v13; // r15d
  int v14; // r14d
  unsigned int TierTemplate; // eax
  _QWORD *v16; // rbp
  int v17; // eax
  int v18; // eax
  SP_RESILIENCY_INFO *v19; // r8
  __int64 v20; // r8
  __int64 v21; // r8
  struct _GUID *v22; // rax
  HLOCAL hMem; // [rsp+78h] [rbp+10h] BYREF
  HLOCAL v26; // [rsp+88h] [rbp+20h] BYREF

  v26 = a4;
  v5 = *((_QWORD *)a2 + 347);
  v7 = *((_QWORD *)a2 + 348);
  v26 = 0;
  hMem = 0;
  Control = SuGetControl((struct _SP_CONTROL_INFO **)&v26);
  v11 = v26;
  Child = Control;
  if ( !Control )
    goto LABEL_23;
  v13 = *((_DWORD *)a2 + 687);
  if ( v5 == -1 )
  {
    if ( v13 != 3 )
    {
      *((_QWORD *)a2 + 347) = 0;
      goto LABEL_23;
    }
    v5 = 0x40000000;
    v14 = 1;
LABEL_9:
    if ( v5 == v7 )
    {
      SetLastError(0x57u);
      Child = 0;
      goto LABEL_23;
    }
    goto LABEL_11;
  }
  v14 = 0;
  if ( v13 == 3 )
  {
    if ( v5 )
      goto LABEL_9;
    v5 = *((_QWORD *)v26 + 15);
    if ( v5 )
      goto LABEL_9;
  }
LABEL_11:
  *((_QWORD *)a2 + 347) = v5;
  if ( v5 )
  {
    TierTemplate = SuGetTierTemplate(a1, (unsigned int)(v13 != 1) + 1, v10, &hMem);
    v16 = hMem;
    Child = TierTemplate;
    if ( TierTemplate )
    {
      *((_DWORD *)hMem + 654) = 7;
      v16[328] = v5;
      *((_DWORD *)v16 + 662) = 2 - (v7 != 0);
      v16[332] = *((_QWORD *)a1 + 342);
      v17 = 52;
      if ( !v7 )
        v17 = 60;
      *((_DWORD *)v16 + 666) = v17;
      *((_DWORD *)v16 + 677) = -1;
      *((_DWORD *)v16 + 678) = *((_DWORD *)a2 + 692);
      v18 = SP_RESILIENCY_INFO::NumberOfLogicalCopies((struct _SP_SPACE_INFO *)((char *)a2 + 2748));
      SP_RESILIENCY_INFO::SetNumberOfCopies(v19, v18 + *((_DWORD *)a2 + 700) - 1);
      LOBYTE(v20) = 11;
      Child = SiCreateChild(a1, a2, v20, v16, a5);
      if ( !Child )
      {
        if ( v13 == 3 || v7 )
        {
          v22 = a5;
          *((_DWORD *)v16 + 666) = 0;
          LOBYTE(v21) = 11;
          *((_DWORD *)v16 + 677) = -1;
          Child = SiCreateChild(a1, a2, v21, v16, v22);
        }
        else if ( v14 )
        {
          *((_QWORD *)a2 + 347) = 0;
          SetLastError(0);
          Child = 1;
        }
      }
    }
    if ( v16 )
      LocalFree(v16);
  }
LABEL_23:
  if ( v11 )
    LocalFree(v11);
  return Child;
}

```

## disassembly

```asm
0x14000fed8  mov     rax, rsp
0x14000fedb  mov     [rax+18h], rbx
0x14000fedf  mov     [rax+20h], r9
0x14000fee3  mov     [rax+8], rcx
0x14000fee7  push    rbp
0x14000fee8  push    rsi
0x14000fee9  push    rdi
0x14000feea  push    r12
0x14000feec  push    r13
0x14000feee  push    r14
0x14000fef0  push    r15
0x14000fef2  sub     rsp, 30h
0x14000fef6  mov     rbx, [rdx+0AD8h]
0x14000fefd  mov     rbp, rcx
0x14000ff00  mov     r12, [rdx+0AE0h]
0x14000ff07  lea     rcx, [rax+20h]; struct _SP_CONTROL_INFO **
0x14000ff0b  mov     rdi, rdx
0x14000ff0e  mov     qword ptr [rax+20h], 0
0x14000ff16  mov     qword ptr [rax+10h], 0
0x14000ff1e  call    ?SuGetControl@@YAHPEAPEAU_SP_CONTROL_INFO@@@Z; SuGetControl(_SP_CONTROL_INFO * *)
0x14000ff23  mov     r13, [rsp+68h+arg_18]
0x14000ff2b  mov     esi, eax
0x14000ff2d  test    eax, eax
0x14000ff2f  jz      loc_1400100D5
0x14000ff35  mov     r15d, [rdi+0ABCh]
0x14000ff3c  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14000ff40  jnz     short loc_14000FF65
0x14000ff42  cmp     r15d, 3
0x14000ff46  jz      short loc_14000FF58
0x14000ff48  mov     qword ptr [rdi+0AD8h], 0
0x14000ff53  jmp     loc_1400100D5
0x14000ff58  mov     ebx, 40000000h
0x14000ff5d  mov     r14d, 1
0x14000ff63  jmp     short loc_14000FF7C
0x14000ff65  xor     r14d, r14d
0x14000ff68  cmp     r15d, 3
0x14000ff6c  jnz     short loc_14000FF93
0x14000ff6e  test    rbx, rbx
0x14000ff71  jnz     short loc_14000FF7C
0x14000ff73  mov     rbx, [r13+78h]
0x14000ff77  test    rbx, rbx
0x14000ff7a  jz      short loc_14000FF93
0x14000ff7c  cmp     rbx, r12
0x14000ff7f  jnz     short loc_14000FF93
0x14000ff81  mov     ecx, 57h ; 'W'; dwErrCode
0x14000ff86  call    cs:__imp_SetLastError
0x14000ff8c  xor     esi, esi
0x14000ff8e  jmp     loc_1400100D5
0x14000ff93  mov     [rdi+0AD8h], rbx
0x14000ff9a  test    rbx, rbx
0x14000ff9d  jz      loc_1400100D5
0x14000ffa3  xor     edx, edx
0x14000ffa5  lea     r9, [rsp+68h+hMem]
0x14000ffaa  cmp     r15d, 1
0x14000ffae  mov     rcx, rbp
0x14000ffb1  setnz   dl
0x14000ffb4  inc     edx
0x14000ffb6  call    ?SuGetTierTemplate@@YAHPEAU_SU_POOL_OBJECT@@W4_SP_RESILIENCY_TYPE@@PEAU_SP_FD_IDS@@PEAPEAU_SP_TIER_INFO@@@Z; SuGetTierTemplate(_SU_POOL_OBJECT *,_SP_RESILIENCY_TYPE,_SP_FD_IDS *,_SP_TIER_INFO * *)
0x14000ffbb  mov     rbp, [rsp+68h+hMem]
0x14000ffc0  mov     esi, eax
0x14000ffc2  test    eax, eax
0x14000ffc4  jz      loc_1400100C7
0x14000ffca  mov     dword ptr [rbp+0A38h], 7
0x14000ffd4  lea     r8, [rbp+0A84h]
0x14000ffdb  mov     [rbp+0A40h], rbx
0x14000ffe2  mov     rax, r12
0x14000ffe5  mov     rbx, [rsp+68h+arg_0]
0x14000ffea  neg     rax
0x14000ffed  sbb     edx, edx
0x14000ffef  add     edx, 2
0x14000fff2  mov     [rbp+0A58h], edx
0x14000fff8  test    r12, r12
0x14000fffb  mov     rax, [rbx+0AB0h]
0x140010002  mov     [rbp+0A60h], rax
0x140010009  mov     eax, 34h ; '4'
0x14001000e  lea     ecx, [rax+8]
0x140010011  cmovz   eax, ecx
0x140010014  lea     rcx, [rdi+0ABCh]; this
0x14001001b  mov     [rbp+0A68h], eax
0x140010021  mov     dword ptr [r8+10h], 0FFFFFFFFh
0x140010029  mov     eax, [rcx+14h]
0x14001002c  mov     [rbp+0A98h], eax
0x140010032  call    ?NumberOfLogicalCopies@SP_RESILIENCY_INFO@@QEAAKXZ; SP_RESILIENCY_INFO::NumberOfLogicalCopies(void)
0x140010037  mov     edx, [rdi+0AF0h]
0x14001003d  mov     rcx, r8; this
0x140010040  dec     edx
0x140010042  add     edx, eax; unsigned int
0x140010044  call    ?SetNumberOfCopies@SP_RESILIENCY_INFO@@QEAAXK@Z; SP_RESILIENCY_INFO::SetNumberOfCopies(ulong)
0x140010049  mov     rax, [rsp+68h+arg_20]
0x140010051  mov     r9, rbp
0x140010054  mov     r8b, 0Bh
0x140010057  mov     [rsp+68h+var_48], rax
0x14001005c  mov     rdx, rdi
0x14001005f  mov     rcx, rbx
0x140010062  call    ?SiCreateChild@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_SPACE_INFO@@W4_SC_SPACE_USAGE@@PEAU_SP_TIER_INFO@@PEAU_GUID@@@Z; SiCreateChild(_SU_POOL_OBJECT *,_SP_SPACE_INFO *,_SC_SPACE_USAGE,_SP_TIER_INFO *,_GUID *)
0x140010067  mov     esi, eax
0x140010069  test    eax, eax
0x14001006b  jnz     short loc_1400100C7
0x14001006d  cmp     r15d, 3
0x140010071  jz      short loc_140010093
0x140010073  test    r12, r12
0x140010076  jnz     short loc_140010093
0x140010078  test    r14d, r14d
0x14001007b  jz      short loc_1400100C7
0x14001007d  xor     ecx, ecx; dwErrCode
0x14001007f  mov     [rdi+0AD8h], r12
0x140010086  call    cs:__imp_SetLastError
0x14001008c  lea     esi, [r12+1]
0x140010091  jmp     short loc_1400100C7
0x140010093  mov     rax, [rsp+68h+arg_20]
0x14001009b  mov     r9, rbp
0x14001009e  mov     dword ptr [rbp+0A68h], 0
0x1400100a8  mov     r8b, 0Bh
0x1400100ab  mov     rdx, rdi
0x1400100ae  mov     [rsp+68h+var_48], rax
0x1400100b3  mov     rcx, rbx
0x1400100b6  mov     dword ptr [rbp+0A94h], 0FFFFFFFFh
0x1400100c0  call    ?SiCreateChild@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_SPACE_INFO@@W4_SC_SPACE_USAGE@@PEAU_SP_TIER_INFO@@PEAU_GUID@@@Z; SiCreateChild(_SU_POOL_OBJECT *,_SP_SPACE_INFO *,_SC_SPACE_USAGE,_SP_TIER_INFO *,_GUID *)
0x1400100c5  mov     esi, eax
0x1400100c7  test    rbp, rbp
0x1400100ca  jz      short loc_1400100D5
0x1400100cc  mov     rcx, rbp; hMem
0x1400100cf  call    cs:__imp_LocalFree
0x1400100d5  test    r13, r13
0x1400100d8  jz      short loc_1400100E3
0x1400100da  mov     rcx, r13; hMem
0x1400100dd  call    cs:__imp_LocalFree
0x1400100e3  mov     rbx, [rsp+68h+arg_10]
0x1400100eb  mov     eax, esi
0x1400100ed  add     rsp, 30h
0x1400100f1  pop     r15
0x1400100f3  pop     r14
0x1400100f5  pop     r13
0x1400100f7  pop     r12
0x1400100f9  pop     rdi
0x1400100fa  pop     rsi
0x1400100fb  pop     rbp
0x1400100fc  retn
```
