# BCryptIumBuildClaimPadding

- ea: `0x1400124e8`
- end: `0x140012604`
- name: `BCryptIumBuildClaimPadding`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140013124`

## callees

- `0x140003ad6`
- `0x1400124e8`
- `0x140037b10`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x14001258a`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x14001258a`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1400125eb`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1400125eb`

## string_xrefs

- `0x1400125dd`: `onecore\ds\security\cryptoapi\ncrypt\ium\trustlet\bcryptiumkeyattest.cxx`

## pseudocode

```c
__int64 __fastcall BCryptIumBuildClaimPadding(int a1, __int64 a2, _QWORD *a3, unsigned int *a4)
{
  unsigned int v7; // ebx
  __int64 v8; // r8
  __int64 v9; // rcx
  _WORD *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  unsigned int v13; // ebp
  unsigned int v14; // r14d
  _DWORD *v15; // rax
  _DWORD *v16; // rdi

  *a3 = 0;
  *a4 = 0;
  v7 = 0;
  if ( a1 )
  {
    if ( a1 != 8 )
    {
      v7 = -1073741595;
      v8 = 814;
LABEL_4:
      v9 = v7;
LABEL_16:
      VBS_ATTEST_TRACE_ERROR_IN(
        v9,
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\trustlet\\bcryptiumkeyattest.cxx",
        v8);
      goto LABEL_17;
    }
    v10 = *(_WORD **)a2;
    if ( !*(_QWORD *)a2 )
    {
      v9 = 2147942487LL;
      v7 = -2147024809;
      goto LABEL_15;
    }
    v11 = 512;
    do
    {
      if ( !*v10 )
        break;
      ++v10;
      --v11;
    }
    while ( v11 );
    v7 = v11 == 0 ? 0x80070057 : 0;
    v12 = (512 - v11) & -(__int64)(v11 != 0);
    if ( !v11 )
    {
      v9 = v7;
LABEL_15:
      v8 = 777;
      goto LABEL_16;
    }
    v13 = 2 * v12 + 2;
    v14 = 2 * v12 + 18;
    v15 = LocalAlloc(0, v14);
    v16 = v15;
    if ( !v15 )
    {
      v7 = -1073741801;
      v8 = 794;
      goto LABEL_4;
    }
    *v15 = 0;
    v15[1] = 8;
    v15[2] = v13;
    v15[3] = *(_DWORD *)(a2 + 8);
    memcpy_0(v15 + 4, *(const void **)a2, v13);
    *a4 = v14;
    *a3 = v16;
  }
LABEL_17:
  LocalFree(0);
  return v7;
}

```

## disassembly

```asm
0x1400124e8  push    rbx
0x1400124ea  push    rbp
0x1400124eb  push    rsi
0x1400124ec  push    rdi
0x1400124ed  push    r12
0x1400124ef  push    r13
0x1400124f1  push    r14
0x1400124f3  push    r15
0x1400124f5  sub     rsp, 28h
0x1400124f9  xor     r13d, r13d
0x1400124fc  mov     r15, r9
0x1400124ff  mov     [r8], r13
0x140012502  mov     r12, r8
0x140012505  mov     [r9], r13d
0x140012508  mov     rsi, rdx
0x14001250b  mov     ebx, r13d
0x14001250e  test    ecx, ecx
0x140012510  jz      loc_1400125E9
0x140012516  cmp     ecx, 8
0x140012519  jz      short loc_14001252D
0x14001251b  mov     ebx, 0C00000E5h
0x140012520  mov     r8d, 32Eh
0x140012526  mov     ecx, ebx
0x140012528  jmp     loc_1400125DD
0x14001252d  mov     rax, [rdx]
0x140012530  test    rax, rax
0x140012533  jz      loc_1400125D0
0x140012539  mov     r8d, 200h
0x14001253f  mov     edx, r8d
0x140012542  cmp     [rax], r13w
0x140012546  jz      short loc_140012552
0x140012548  add     rax, 2
0x14001254c  sub     rdx, 1
0x140012550  jnz     short loc_140012542
0x140012552  mov     rax, rdx
0x140012555  neg     rax
0x140012558  mov     rax, rdx
0x14001255b  sbb     ebx, ebx
0x14001255d  sub     r8, rdx
0x140012560  not     ebx
0x140012562  and     ebx, 80070057h
0x140012568  neg     rax
0x14001256b  sbb     rcx, rcx
0x14001256e  and     rcx, r8
0x140012571  test    rdx, rdx
0x140012574  jnz     short loc_14001257A
0x140012576  mov     ecx, ebx
0x140012578  jmp     short loc_1400125D7
0x14001257a  lea     ebp, ds:2[rcx*2]
0x140012581  xor     ecx, ecx; uFlags
0x140012583  lea     r14d, [rbp+10h]
0x140012587  mov     edx, r14d; uBytes
0x14001258a  call    cs:__imp_LocalAlloc
0x140012590  mov     rdi, rax
0x140012593  test    rax, rax
0x140012596  jnz     short loc_1400125A5
0x140012598  mov     ebx, 0C0000017h
0x14001259d  mov     r8d, 31Ah
0x1400125a3  jmp     short loc_140012526
0x1400125a5  mov     [rax], r13d
0x1400125a8  lea     rcx, [rdi+10h]; void *
0x1400125ac  mov     dword ptr [rax+4], 8
0x1400125b3  mov     [rax+8], ebp
0x1400125b6  mov     eax, [rsi+8]
0x1400125b9  mov     [rdi+0Ch], eax
0x1400125bc  mov     rdx, [rsi]; Src
0x1400125bf  mov     r8d, ebp; Size
0x1400125c2  call    memcpy_0
0x1400125c7  mov     [r15], r14d
0x1400125ca  mov     [r12], rdi
0x1400125ce  jmp     short loc_1400125E9
0x1400125d0  mov     ecx, 80070057h
0x1400125d5  mov     ebx, ecx
0x1400125d7  mov     r8d, 309h
0x1400125dd  lea     rdx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1400125e4  call    VBS_ATTEST_TRACE_ERROR_IN
0x1400125e9  xor     ecx, ecx; hMem
0x1400125eb  call    cs:__imp_LocalFree
0x1400125f1  mov     eax, ebx
0x1400125f3  add     rsp, 28h
0x1400125f7  pop     r15
0x1400125f9  pop     r14
0x1400125fb  pop     r13
0x1400125fd  pop     r12
0x1400125ff  pop     rdi
0x140012600  pop     rsi
0x140012601  pop     rbp
0x140012602  pop     rbx
0x140012603  retn
```
