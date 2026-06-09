# setupLookaside

- ea: `0x18005be2c`
- end: `0x18005c07b`
- name: `setupLookaside`
- size: `591`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180001fbc`
- `0x18008ddf0`

## callees

- `0x18000aac0`
- `0x18000bd90`
- `0x18000c440`
- `0x180047b8c`
- `0x180047ba4`
- `0x18005be2c`
- `0x180066ffc`

## pseudocode

```c
__int64 __fastcall setupLookaside(__int64 a1, _QWORD *a2, int a3, int a4)
{
  __int64 v5; // rbx
  __int64 v6; // rbp
  int v8; // edx
  int v10; // esi
  int v11; // eax
  __int64 v12; // rbp
  _QWORD *v13; // rbx
  __int64 v14; // rdx
  int v15; // r8d
  __int64 v16; // r9
  __int64 v17; // r10
  int v18; // ecx
  int v19; // edx
  _QWORD *v20; // r11
  _QWORD *v21; // rax
  int v22; // edx
  _QWORD *v23; // r8
  _QWORD *v24; // rax
  int v25; // r11d
  bool v26; // r9

  v5 = a4;
  v6 = a3;
  if ( (int)sqlite3LookasideUsed(a1, 0) > 0 )
    return (unsigned int)(v8 + 5);
  if ( *(_BYTE *)(a1 + 424) != (_BYTE)v8 )
    sqlite3_free(*(_QWORD *)(a1 + 488));
  v10 = 0;
  if ( (int)(v6 & 0xFFFFFFF8) > 8 )
    v10 = v6 & 0xFFFFFFF8;
  v11 = 0;
  if ( (int)v5 >= 0 )
    v11 = v5;
  if ( !v10 || !v11 )
  {
    LOWORD(v10) = 0;
    v13 = 0;
    v15 = 0;
    goto LABEL_22;
  }
  v12 = v5 * v6;
  if ( a2 )
  {
    v13 = a2;
  }
  else
  {
    sqlite3BeginBenignMalloc();
    v13 = (_QWORD *)sqlite3Malloc(v12);
    sqlite3EndBenignMalloc();
    if ( v13 )
      v12 = (int)sqlite3MallocSize(v13, v14);
  }
  v15 = v10;
  if ( v10 < 384 )
  {
    if ( v10 >= 256 )
    {
      LODWORD(v16) = v12 / (v10 + 128);
      LODWORD(v17) = (v12 - v10 * (int)v16) / 128;
      goto LABEL_23;
    }
    if ( v10 > 0 )
    {
      LODWORD(v17) = 0;
      LODWORD(v16) = v12 / v10;
      goto LABEL_23;
    }
LABEL_22:
    LODWORD(v17) = 0;
    LODWORD(v16) = 0;
    goto LABEL_23;
  }
  v16 = v12 / (v10 + 384);
  v17 = (v12 - v10 * (int)v16) / 128;
LABEL_23:
  *(_QWORD *)(a1 + 488) = v13;
  v18 = 1;
  *(_QWORD *)(a1 + 448) = 0;
  *(_QWORD *)(a1 + 456) = 0;
  *(_WORD *)(a1 + 420) = v10;
  *(_WORD *)(a1 + 422) = v10;
  if ( v13 )
  {
    if ( (int)v16 > 0 )
    {
      v19 = 0;
      v20 = 0;
      do
      {
        *v13 = v20;
        v21 = v13;
        *(_QWORD *)(a1 + 448) = v13;
        ++v19;
        v13 = (_QWORD *)((char *)v13 + v15);
        v20 = v21;
      }
      while ( v19 < (int)v16 );
    }
    *(_QWORD *)(a1 + 464) = 0;
    *(_QWORD *)(a1 + 472) = 0;
    *(_QWORD *)(a1 + 480) = v13;
    if ( (int)v17 > 0 )
    {
      v22 = 0;
      v23 = 0;
      do
      {
        *v13 = v23;
        v24 = v13;
        *(_QWORD *)(a1 + 464) = v13;
        ++v22;
        v13 += 16;
        v23 = v24;
      }
      while ( v22 < (int)v17 );
    }
    v25 = v17 + v16;
    v26 = a2 == 0;
    v18 = 0;
  }
  else
  {
    *(_QWORD *)(a1 + 488) = 0;
    v25 = 0;
    *(_WORD *)(a1 + 420) = 0;
    v26 = 0;
    *(_QWORD *)(a1 + 464) = 0;
    v13 = 0;
    *(_QWORD *)(a1 + 472) = 0;
    *(_QWORD *)(a1 + 480) = 0;
  }
  *(_QWORD *)(a1 + 496) = v13;
  *(_DWORD *)(a1 + 416) = v18;
  *(_BYTE *)(a1 + 424) = v26;
  *(_DWORD *)(a1 + 428) = v25;
  *(_QWORD *)(a1 + 504) = *(_QWORD *)(a1 + 496);
  return 0;
}

```

## disassembly

```asm
0x18005be2c  push    rbx
0x18005be2e  push    rbp
0x18005be2f  push    rsi
0x18005be30  push    rdi
0x18005be31  push    r12
0x18005be33  push    r14
0x18005be35  sub     rsp, 28h
0x18005be39  mov     r14, rdx
0x18005be3c  movsxd  rbx, r9d
0x18005be3f  xor     edx, edx
0x18005be41  movsxd  rbp, r8d
0x18005be44  mov     rdi, rcx
0x18005be47  call    sqlite3LookasideUsed
0x18005be4c  test    eax, eax
0x18005be4e  jle     short loc_18005BE58
0x18005be50  lea     eax, [rdx+5]
0x18005be53  jmp     loc_18005C06E
0x18005be58  cmp     [rdi+1A8h], dl
0x18005be5e  jz      short loc_18005BE6C
0x18005be60  mov     rcx, [rdi+1E8h]
0x18005be67  call    sqlite3_free
0x18005be6c  xor     esi, esi
0x18005be6e  mov     eax, ebp
0x18005be70  and     eax, 0FFFFFFF8h
0x18005be73  mov     r12d, 80h
0x18005be79  cmp     eax, 8
0x18005be7c  cmovg   esi, eax
0x18005be7f  xor     eax, eax
0x18005be81  test    ebx, ebx
0x18005be83  cmovns  eax, ebx
0x18005be86  test    esi, esi
0x18005be88  jz      loc_18005BF48
0x18005be8e  test    eax, eax
0x18005be90  jz      loc_18005BF48
0x18005be96  imul    rbp, rbx
0x18005be9a  test    r14, r14
0x18005be9d  jnz     short loc_18005BEC6
0x18005be9f  call    sqlite3BeginBenignMalloc
0x18005bea4  mov     rcx, rbp
0x18005bea7  call    sqlite3Malloc
0x18005beac  mov     rbx, rax
0x18005beaf  call    sqlite3EndBenignMalloc
0x18005beb4  test    rbx, rbx
0x18005beb7  jz      short loc_18005BEC9
0x18005beb9  mov     rcx, rbx
0x18005bebc  call    sqlite3MallocSize
0x18005bec1  movsxd  rbp, eax
0x18005bec4  jmp     short loc_18005BEC9
0x18005bec6  mov     rbx, r14
0x18005bec9  mov     r8d, esi
0x18005becc  cmp     esi, 180h
0x18005bed2  jl      short loc_18005BF00
0x18005bed4  lea     eax, [rsi+180h]
0x18005beda  movsxd  rcx, eax
0x18005bedd  mov     rax, rbp
0x18005bee0  cqo
0x18005bee2  idiv    rcx
0x18005bee5  mov     ecx, eax
0x18005bee7  mov     r9, rax
0x18005beea  imul    ecx, esi
0x18005beed  movsxd  rdx, ecx
0x18005bef0  sub     rbp, rdx
0x18005bef3  mov     rax, rbp
0x18005bef6  cqo
0x18005bef8  idiv    r12
0x18005befb  mov     r10, rax
0x18005befe  jmp     short loc_18005BF55
0x18005bf00  cmp     esi, 100h
0x18005bf06  jl      short loc_18005BF31
0x18005bf08  lea     eax, [rsi+80h]
0x18005bf0e  movsxd  rcx, eax
0x18005bf11  mov     rax, rbp
0x18005bf14  cqo
0x18005bf16  idiv    rcx
0x18005bf19  mov     r9d, eax
0x18005bf1c  imul    eax, esi
0x18005bf1f  cdqe
0x18005bf21  sub     rbp, rax
0x18005bf24  mov     rax, rbp
0x18005bf27  cqo
0x18005bf29  idiv    r12
0x18005bf2c  mov     r10d, eax
0x18005bf2f  jmp     short loc_18005BF55
0x18005bf31  test    esi, esi
0x18005bf33  jle     short loc_18005BF4F
0x18005bf35  mov     rax, rbp
0x18005bf38  movsxd  rcx, esi
0x18005bf3b  cqo
0x18005bf3d  idiv    rcx
0x18005bf40  xor     r10d, r10d
0x18005bf43  mov     r9d, eax
0x18005bf46  jmp     short loc_18005BF55
0x18005bf48  xor     esi, esi
0x18005bf4a  xor     ebx, ebx
0x18005bf4c  xor     r8d, r8d
0x18005bf4f  xor     r10d, r10d
0x18005bf52  xor     r9d, r9d
0x18005bf55  mov     [rdi+1E8h], rbx
0x18005bf5c  mov     ecx, 1
0x18005bf61  mov     qword ptr [rdi+1C0h], 0
0x18005bf6c  mov     qword ptr [rdi+1C8h], 0
0x18005bf77  mov     [rdi+1A4h], si
0x18005bf7e  mov     [rdi+1A6h], si
0x18005bf85  test    rbx, rbx
0x18005bf88  jz      short loc_18005C001
0x18005bf8a  test    r9d, r9d
0x18005bf8d  jle     short loc_18005BFB1
0x18005bf8f  xor     edx, edx
0x18005bf91  movsxd  r8, r8d
0x18005bf94  xor     r11d, r11d
0x18005bf97  mov     [rbx], r11
0x18005bf9a  mov     rax, rbx
0x18005bf9d  mov     [rdi+1C0h], rbx
0x18005bfa4  add     edx, ecx
0x18005bfa6  add     rbx, r8
0x18005bfa9  mov     r11, rax
0x18005bfac  cmp     edx, r9d
0x18005bfaf  jl      short loc_18005BF97
0x18005bfb1  mov     qword ptr [rdi+1D0h], 0
0x18005bfbc  mov     qword ptr [rdi+1D8h], 0
0x18005bfc7  mov     [rdi+1E0h], rbx
0x18005bfce  test    r10d, r10d
0x18005bfd1  jle     short loc_18005BFF2
0x18005bfd3  xor     edx, edx
0x18005bfd5  xor     r8d, r8d
0x18005bfd8  mov     [rbx], r8
0x18005bfdb  mov     rax, rbx
0x18005bfde  mov     [rdi+1D0h], rbx
0x18005bfe5  add     edx, ecx
0x18005bfe7  add     rbx, r12
0x18005bfea  mov     r8, rax
0x18005bfed  cmp     edx, r10d
0x18005bff0  jl      short loc_18005BFD8
0x18005bff2  test    r14, r14
0x18005bff5  lea     r11d, [r10+r9]
0x18005bff9  setz    r9b
0x18005bffd  xor     ecx, ecx
0x18005bfff  jmp     short loc_18005C03E
0x18005c001  xor     eax, eax
0x18005c003  mov     qword ptr [rdi+1E8h], 0
0x18005c00e  xor     r11d, r11d
0x18005c011  mov     [rdi+1A4h], ax
0x18005c018  xor     r9b, r9b
0x18005c01b  mov     qword ptr [rdi+1D0h], 0
0x18005c026  xor     ebx, ebx
0x18005c028  mov     qword ptr [rdi+1D8h], 0
0x18005c033  mov     qword ptr [rdi+1E0h], 0
0x18005c03e  mov     eax, 1F0h
0x18005c043  mov     r8, rdi
0x18005c046  mov     r10, rdi
0x18005c049  mov     [rax+rdi], rbx
0x18005c04d  lea     edx, [rax-50h]
0x18005c050  mov     [rdx+rdi], ecx
0x18005c053  mov     [rdi+1A8h], r9b
0x18005c05a  mov     [rdi+1ACh], r11d
0x18005c061  mov     rax, [rax+rdi]
0x18005c065  mov     [rdi+1F8h], rax
0x18005c06c  xor     eax, eax
0x18005c06e  add     rsp, 28h
0x18005c072  pop     r14
0x18005c074  pop     r12
0x18005c076  pop     rdi
0x18005c077  pop     rsi
0x18005c078  pop     rbp
0x18005c079  pop     rbx
0x18005c07a  retn
```
