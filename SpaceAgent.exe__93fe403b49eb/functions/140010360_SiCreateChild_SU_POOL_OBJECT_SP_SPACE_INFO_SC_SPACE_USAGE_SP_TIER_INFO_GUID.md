# SiCreateChild(_SU_POOL_OBJECT *,_SP_SPACE_INFO *,_SC_SPACE_USAGE,_SP_TIER_INFO *,_GUID *)

- ea: `0x140010360`
- end: `0x1400105b6`
- name: `?SiCreateChild@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_SPACE_INFO@@W4_SC_SPACE_USAGE@@PEAU_SP_TIER_INFO@@PEAU_GUID@@@Z`
- size: `598`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int8, __int64, GUID *)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x14000fed8`
- `0x140010104`
- `0x140010694`
- `0x1400107e8`
- `0x140010a68`
- `0x140011248`
- `0x1400114f8`

## callees

- `0x140010360`
- `0x140010b5c`
- `0x14001ed92`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140010597`
- `KERNEL32!LocalFree` at `0x140010597`
- `KERNEL32!SetLastError` at `0x1400103a8`
- `KERNEL32!SetLastError` at `0x140010464`
- `KERNEL32!SetLastError` at `0x1400103a8`
- `KERNEL32!SetLastError` at `0x140010464`
- `KERNEL32!LocalAlloc` at `0x140010429`
- `KERNEL32!LocalAlloc` at `0x140010429`
- `RPCRT4!UuidCreate` at `0x140010458`
- `RPCRT4!UuidCreate` at `0x140010458`

## pseudocode

```c
__int64 __fastcall SiCreateChild(__int64 a1, __int64 a2, unsigned __int8 a3, __int64 a4, GUID *a5)
{
  GUID *v5; // r15
  int v7; // r12d
  DWORD v10; // ecx
  unsigned int Space; // edi
  __int64 v12; // rax
  unsigned __int64 v13; // r8
  unsigned int v14; // r14d
  char *v15; // rax
  char *v16; // rbx
  RPC_STATUS v17; // eax
  struct _SP_TIER_INFO **v18; // r9
  unsigned int v19; // r8d
  struct _SP_TIER_INFO *v21; // [rsp+68h] [rbp+20h] BYREF

  v21 = (struct _SP_TIER_INFO *)a4;
  v5 = a5;
  v7 = a3;
  *a5 = GUID_NULL;
  if ( *(_DWORD *)(a4 + 2692) != 3 )
  {
    v12 = *(_QWORD *)(a4 + 2656);
    if ( v12 == -1 )
    {
      v12 = *(_QWORD *)(a1 + 2736);
      *(_QWORD *)(a4 + 2656) = v12;
    }
    v13 = v12
        + *(_QWORD *)(a1 + 2736)
        - 1LL
        - (unsigned __int64)(v12 + *(_QWORD *)(a1 + 2736) - 1LL) % *(_QWORD *)(a1 + 2736);
    *(_QWORD *)(a4 + 2656) = v13;
    *(_QWORD *)(a4 + 2624) = v13 + *(_QWORD *)(a4 + 2624) - 1LL - (v13 + *(_QWORD *)(a4 + 2624) - 1LL) % v13;
    v14 = 16 * *(_DWORD *)(a2 + 2740) + 3032;
    v15 = (char *)LocalAlloc(0x40u, v14);
    v16 = v15;
    if ( !v15 )
    {
      v10 = 1450;
      goto LABEL_3;
    }
    *(_DWORD *)v15 = 3032;
    *((_DWORD *)v15 + 1) = v14;
    *(_OWORD *)(v15 + 8) = *(_OWORD *)(a1 + 40);
    v17 = UuidCreate((UUID *)(v15 + 24));
    if ( v17 )
    {
      SetLastError(v17);
      Space = 0;
LABEL_22:
      LocalFree(v16);
      return Space;
    }
    v16[2600] = v7;
    *(_OWORD *)(v16 + 2696) = *(_OWORD *)(a4 + 2648);
    *(_OWORD *)(v16 + 2712) = *(_OWORD *)(a4 + 2664);
    *((_DWORD *)v16 + 685) = *(_DWORD *)(a2 + 2740);
    *((_DWORD *)v16 + 686) = 3032;
    *(_OWORD *)(v16 + 2748) = *(_OWORD *)(a4 + 2692);
    *(_QWORD *)(v16 + 2764) = *(_QWORD *)(a4 + 2708);
    *(_OWORD *)(v16 + 2808) = *(_OWORD *)(a2 + 24);
    *((_DWORD *)v16 + 700) = *(_DWORD *)(a2 + 2800);
    memcpy_0(v16 + 3032, (const void *)(a2 + *(unsigned int *)(a2 + 2744)), 16LL * *(unsigned int *)(a2 + 2740));
    if ( v7 != 3 )
    {
      if ( v7 == 4 )
      {
        *((_QWORD *)v16 + 349) = *(_QWORD *)(a2 + 2792);
LABEL_17:
        if ( (_BYTE)v7 == 3 )
        {
          v18 = 0;
          *((_QWORD *)v16 + 333) = *(_QWORD *)(a4 + 2624);
          v19 = 0;
        }
        else
        {
          v18 = &v21;
          v19 = 1;
        }
        Space = SiCreateSpace((struct _SU_POOL_OBJECT *)a1, (struct _SP_SPACE_INFO *)v16, v19, v18);
        if ( Space )
          *v5 = *(GUID *)(v16 + 24);
        goto LABEL_22;
      }
      if ( v7 != 5 )
      {
        if ( v7 == 11 )
        {
          *((_QWORD *)v16 + 347) = *(_QWORD *)(a2 + 2776);
          *((_QWORD *)v16 + 348) = *(_QWORD *)(a2 + 2784);
        }
        goto LABEL_17;
      }
    }
    *((_QWORD *)v16 + 347) = *(_QWORD *)(a2 + 2776);
    goto LABEL_17;
  }
  v10 = 50;
LABEL_3:
  SetLastError(v10);
  return 0;
}

```

## disassembly

```asm
0x140010360  mov     [rsp+arg_0], rbx
0x140010365  mov     [rsp+arg_8], rbp
0x14001036a  mov     [rsp+arg_18], r9
0x14001036f  push    rsi
0x140010370  push    rdi
0x140010371  push    r12
0x140010373  push    r14
0x140010375  push    r15
0x140010377  sub     rsp, 20h
0x14001037b  mov     r15, [rsp+48h+arg_20]
0x140010380  mov     rdi, r9
0x140010383  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x14001038a  movzx   r12d, r8b
0x14001038e  mov     rsi, rdx
0x140010391  mov     rbp, rcx
0x140010394  movdqu  xmmword ptr [r15], xmm0
0x140010399  cmp     dword ptr [r9+0A84h], 3
0x1400103a1  jnz     short loc_1400103B5
0x1400103a3  mov     ecx, 32h ; '2'; dwErrCode
0x1400103a8  call    cs:__imp_SetLastError
0x1400103ae  xor     edi, edi
0x1400103b0  jmp     loc_14001059D
0x1400103b5  mov     rax, [r9+0A60h]
0x1400103bc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400103c0  jnz     short loc_1400103D0
0x1400103c2  mov     rax, [rcx+0AB0h]
0x1400103c9  mov     [r9+0A60h], rax
0x1400103d0  mov     rcx, [rcx+0AB0h]
0x1400103d7  xor     edx, edx
0x1400103d9  lea     r8, [rcx-1]
0x1400103dd  add     r8, rax
0x1400103e0  mov     rax, r8
0x1400103e3  div     rcx
0x1400103e6  sub     r8, rdx
0x1400103e9  xor     edx, edx
0x1400103eb  mov     [r9+0A60h], r8
0x1400103f2  mov     rcx, [r9+0A40h]
0x1400103f9  dec     rcx
0x1400103fc  add     rcx, r8
0x1400103ff  mov     rax, rcx
0x140010402  div     r8
0x140010405  sub     rcx, rdx
0x140010408  mov     [r9+0A40h], rcx
0x14001040f  mov     ecx, 40h ; '@'; uFlags
0x140010414  mov     r14d, [rsi+0AB4h]
0x14001041b  shl     r14d, 4
0x14001041f  add     r14d, 0BD8h
0x140010426  mov     edx, r14d; uBytes
0x140010429  call    cs:__imp_LocalAlloc
0x14001042f  mov     rbx, rax
0x140010432  test    rax, rax
0x140010435  jnz     short loc_140010441
0x140010437  mov     ecx, 5AAh
0x14001043c  jmp     loc_1400103A8
0x140010441  mov     dword ptr [rax], 0BD8h
0x140010447  lea     rcx, [rax+18h]; Uuid
0x14001044b  mov     [rax+4], r14d
0x14001044f  movups  xmm0, xmmword ptr [rbp+28h]
0x140010453  movdqu  xmmword ptr [rax+8], xmm0
0x140010458  call    cs:__imp_UuidCreate
0x14001045e  test    eax, eax
0x140010460  jz      short loc_140010471
0x140010462  mov     ecx, eax; dwErrCode
0x140010464  call    cs:__imp_SetLastError
0x14001046a  xor     edi, edi
0x14001046c  jmp     loc_140010594
0x140010471  mov     [rbx+0A28h], r12b
0x140010478  lea     rcx, [rbx+0BD8h]; void *
0x14001047f  movups  xmm0, xmmword ptr [rdi+0A58h]
0x140010486  movups  xmmword ptr [rbx+0A88h], xmm0
0x14001048d  movups  xmm1, xmmword ptr [rdi+0A68h]
0x140010494  movups  xmmword ptr [rbx+0A98h], xmm1
0x14001049b  mov     eax, [rsi+0AB4h]
0x1400104a1  mov     [rbx+0AB4h], eax
0x1400104a7  mov     dword ptr [rbx+0AB8h], 0BD8h
0x1400104b1  movups  xmm0, xmmword ptr [rdi+0A84h]
0x1400104b8  movups  xmmword ptr [rbx+0ABCh], xmm0
0x1400104bf  movsd   xmm1, qword ptr [rdi+0A94h]
0x1400104c7  movsd   qword ptr [rbx+0ACCh], xmm1
0x1400104cf  movups  xmm0, xmmword ptr [rsi+18h]
0x1400104d3  movdqu  xmmword ptr [rbx+0AF8h], xmm0
0x1400104db  mov     eax, [rsi+0AF0h]
0x1400104e1  mov     [rbx+0AF0h], eax
0x1400104e7  mov     r8d, [rsi+0AB4h]
0x1400104ee  mov     edx, [rsi+0AB8h]
0x1400104f4  shl     r8, 4; Size
0x1400104f8  add     rdx, rsi; Src
0x1400104fb  call    memcpy_0
0x140010500  mov     ecx, r12d
0x140010503  sub     ecx, 3
0x140010506  jz      short loc_140010545
0x140010508  sub     ecx, 1
0x14001050b  jz      short loc_140010535
0x14001050d  sub     ecx, 1
0x140010510  jz      short loc_140010545
0x140010512  cmp     ecx, 6
0x140010515  jnz     short loc_140010553
0x140010517  mov     rax, [rsi+0AD8h]
0x14001051e  mov     [rbx+0AD8h], rax
0x140010525  mov     rax, [rsi+0AE0h]
0x14001052c  mov     [rbx+0AE0h], rax
0x140010533  jmp     short loc_140010553
0x140010535  mov     rax, [rsi+0AE8h]
0x14001053c  mov     [rbx+0AE8h], rax
0x140010543  jmp     short loc_140010553
0x140010545  mov     rax, [rsi+0AD8h]
0x14001054c  mov     [rbx+0AD8h], rax
0x140010553  mov     rdx, rbx; struct _SP_SPACE_INFO *
0x140010556  mov     rcx, rbp; struct _SU_POOL_OBJECT *
0x140010559  cmp     r12b, 3
0x14001055d  jnz     short loc_140010575
0x14001055f  mov     rax, [rdi+0A40h]
0x140010566  xor     r9d, r9d
0x140010569  mov     [rbx+0A68h], rax
0x140010570  xor     r8d, r8d
0x140010573  jmp     short loc_140010580
0x140010575  lea     r9, [rsp+48h+arg_18]; struct _SP_TIER_INFO **
0x14001057a  mov     r8d, 1; unsigned int
0x140010580  call    ?SiCreateSpace@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SP_SPACE_INFO@@KQEAPEAU_SP_TIER_INFO@@@Z; SiCreateSpace(_SU_POOL_OBJECT *,_SP_SPACE_INFO *,ulong,_SP_TIER_INFO * * const)
0x140010585  mov     edi, eax
0x140010587  test    eax, eax
0x140010589  jz      short loc_140010594
0x14001058b  movups  xmm0, xmmword ptr [rbx+18h]
0x14001058f  movdqu  xmmword ptr [r15], xmm0
0x140010594  mov     rcx, rbx; hMem
0x140010597  call    cs:__imp_LocalFree
0x14001059d  mov     rbx, [rsp+48h+arg_0]
0x1400105a2  mov     eax, edi
0x1400105a4  mov     rbp, [rsp+48h+arg_8]
0x1400105a9  add     rsp, 20h
0x1400105ad  pop     r15
0x1400105af  pop     r14
0x1400105b1  pop     r12
0x1400105b3  pop     rdi
0x1400105b4  pop     rsi
0x1400105b5  retn
```
