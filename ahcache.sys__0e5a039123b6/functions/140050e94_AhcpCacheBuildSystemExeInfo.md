# AhcpCacheBuildSystemExeInfo

- ea: `0x140050e94`
- end: `0x1400513b7`
- name: `AhcpCacheBuildSystemExeInfo`
- size: `1315`
- prototype: `__int64 __fastcall(_QWORD *, void *, void *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14004c3a0`

## callees

- `0x140007b40`
- `0x140007e40`
- `0x14003e364`
- `0x140050e94`
- `0x140054ca8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14005127c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400512d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005134b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005127c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400512d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005134b`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400510f0`
- `ntoskrnl!KeGetCurrentIrql` at `0x140051164`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400511e4`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400512ea`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400510f0`
- `ntoskrnl!KeGetCurrentIrql` at `0x140051164`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400511e4`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400512ea`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140051114`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14005118b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140051202`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14005123a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140051293`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14005130b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140051114`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14005118b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140051202`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14005123a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140051293`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14005130b`

## string_xrefs

- `0x140051386`: `AhcpCacheBuildSystemExeInfo`

## pseudocode

```c
__int64 __fastcall AhcpCacheBuildSystemExeInfo(_QWORD *a1, void *a2, void *a3, int a4)
{
  unsigned __int64 v4; // r10
  unsigned __int64 v6; // rcx
  POOL_TYPE v9; // r14d
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // rbp
  unsigned __int64 v12; // rcx
  unsigned int v13; // ebx
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // r8
  unsigned __int64 v16; // rax
  unsigned __int64 v17; // rbx
  unsigned __int64 v19; // rax
  unsigned __int64 v20; // rcx
  unsigned __int64 v21; // rdx
  SIZE_T v22; // r12
  unsigned __int64 v23; // rax
  unsigned __int64 v24; // rcx
  unsigned __int64 v25; // rax
  unsigned __int64 v26; // rax
  unsigned int v27; // ecx
  size_t v28; // rsi
  unsigned __int64 v29; // rcx
  size_t v30; // rax
  size_t v31; // rcx
  size_t v32; // rax
  __int64 v33; // rbx
  void *v34; // r13
  SIZE_T v35; // rbx
  KIRQL CurrentIrql; // al
  POOL_TYPE v37; // ecx
  PVOID v38; // rax
  void *v39; // r12
  __int64 v40; // rbx
  void *v41; // r13
  SIZE_T v42; // rbx
  KIRQL v43; // al
  POOL_TYPE v44; // ecx
  PVOID v45; // rax
  void *v46; // rbp
  __int64 v47; // rbx
  void *v48; // r12
  SIZE_T v49; // rbx
  PVOID v50; // rax
  void *v51; // rbp
  PVOID PoolWithTag; // rax
  size_t v53; // r8
  PVOID v54; // rax
  size_t v55; // r8
  SIZE_T v56; // r13
  PVOID v57; // rax
  size_t v58; // r8
  int v59; // eax
  BOOL v60; // [rsp+38h] [rbp-50h]
  BOOL Src; // [rsp+90h] [rbp+8h] BYREF

  v4 = a1[1];
  a1[4] = 0;
  v6 = 0;
  v60 = 0;
  Src = 0;
  v9 = 512;
  while ( v6 <= v4 )
  {
    v10 = v6 + 8;
    if ( v6 + 8 < v6 )
      break;
    if ( v10 > v4 )
      break;
    v14 = *(_QWORD *)(v6 + a1[5]);
    a1[4] = v10;
    v15 = v10 + HIDWORD(v14);
    if ( v15 < v10 )
      break;
    if ( v15 + 3 < v15 )
      break;
    v6 = (v15 + 3) & 0xFFFFFFFFFFFFFFFCuLL;
    if ( v6 > v4 )
      break;
    if ( (_DWORD)v14 == 512 )
    {
      v16 = HIDWORD(v14);
      if ( (unsigned int)v16 <= 4 )
      {
        if ( (unsigned int)v16 >= 4 )
        {
          LODWORD(v16) = 4;
          goto LABEL_17;
        }
        if ( (_DWORD)v16 )
        {
LABEL_17:
          if ( v10 <= v4 )
          {
            v17 = (unsigned int)v16 + v10;
            if ( v17 >= v10 && v17 <= v4 )
            {
              memmove(&Src, (const void *)(v10 + a1[5]), (unsigned int)v16);
              a1[4] = v17;
              return 0;
            }
          }
          return (unsigned int)-1073741811;
        }
        return 0;
      }
      return (unsigned int)-1073741675;
    }
    a1[4] = v6;
  }
  if ( !a4 )
  {
    v59 = AhcCheckSystemExe(&Src, a2, a3);
    v13 = v59;
    if ( v59 < 0 )
    {
      AslLogCallPrintf(1, "AhcpCacheBuildSystemExeInfo", 2346, "Failed to check system exe [%x]", v59);
      return v13;
    }
    v60 = Src;
  }
  v11 = a1[1];
  a1[4] = v11;
  Src = 0;
  if ( (v11 & 3) != 0 )
    return (unsigned int)-1073741811;
  v12 = v11 + 8;
  if ( v11 + 8 < v11 )
    return (unsigned int)-1073741811;
  if ( v12 > a1[2] )
  {
    v33 = a1[3] - 1LL;
    if ( v12 + v33 < v12 )
      return (unsigned int)-1073741675;
    v34 = (void *)a1[5];
    v35 = (v12 + v33) & ~v33;
    CurrentIrql = KeGetCurrentIrql();
    v37 = 512;
    if ( v34 )
    {
      if ( CurrentIrql != 2 )
        v37 = PagedPool;
      PoolWithTag = ExAllocatePoolWithTag(v37, v35, 0x7274534Du);
      v39 = PoolWithTag;
      if ( !PoolWithTag )
        return (unsigned int)-1073741801;
      memset(PoolWithTag, 0, v35);
      v53 = v35;
      if ( v11 < v35 )
        v53 = v11;
      memmove(v39, v34, v53);
      ExFreePoolWithTag(v34, 0x7274534Du);
    }
    else
    {
      if ( CurrentIrql != 2 )
        v37 = PagedPool;
      v38 = ExAllocatePoolWithTag(v37, v35, 0x7274534Du);
      v39 = v38;
      if ( !v38 )
        return (unsigned int)-1073741801;
      memset(v38, 0, v35);
    }
    a1[5] = v39;
    a1[2] = v35;
  }
  *(_QWORD *)(a1[4] + a1[5]) = 0x400000200LL;
  v19 = a1[4];
  v20 = v19 + 8;
  if ( v19 + 8 < v19 )
  {
LABEL_24:
    a1[4] = -1;
    return (unsigned int)-1073741675;
  }
  a1[4] = v20;
  v21 = v19 + 12;
  v22 = a1[1];
  if ( v22 <= v20 )
    v22 = v19 + 8;
  a1[1] = v22;
  if ( v21 < v20 )
    return (unsigned int)-1073741811;
  if ( v21 > a1[2] )
  {
    v40 = a1[3] - 1LL;
    if ( v21 + v40 < v21 )
      return (unsigned int)-1073741675;
    v41 = (void *)a1[5];
    v42 = (v21 + v40) & ~v40;
    v43 = KeGetCurrentIrql();
    v44 = 512;
    if ( v41 )
    {
      if ( v43 != 2 )
        v44 = PagedPool;
      v54 = ExAllocatePoolWithTag(v44, v42, 0x7274534Du);
      v46 = v54;
      if ( v54 )
      {
        memset(v54, 0, v42);
        v55 = v42;
        if ( v22 < v42 )
          v55 = v22;
        memmove(v46, v41, v55);
        ExFreePoolWithTag(v41, 0x7274534Du);
        goto LABEL_56;
      }
    }
    else
    {
      if ( v43 != 2 )
        v44 = PagedPool;
      v45 = ExAllocatePoolWithTag(v44, v42, 0x7274534Du);
      v46 = v45;
      if ( v45 )
      {
        memset(v45, 0, v42);
LABEL_56:
        a1[5] = v46;
        a1[2] = v42;
        goto LABEL_32;
      }
    }
    return (unsigned int)-1073741801;
  }
LABEL_32:
  *(_DWORD *)(a1[4] + a1[5]) = v60;
  v23 = a1[4];
  v24 = v23 + 4;
  if ( v23 + 4 < v23 )
    goto LABEL_24;
  a1[4] = v24;
  v13 = 0;
  v25 = a1[1];
  if ( v25 <= v24 )
    v25 = v24;
  a1[1] = v25;
  v26 = v24;
  v27 = v24 & 3;
  if ( v27 )
  {
    v28 = 4LL - v27;
    if ( v28 )
    {
      v29 = v28 + v26;
      if ( v28 + v26 < v26 )
        return (unsigned int)-1073741811;
      if ( v29 <= a1[2] )
      {
LABEL_39:
        memmove((void *)(a1[5] + a1[4]), &Src, v28);
        v30 = a1[4];
        v31 = v28 + v30;
        if ( v28 + v30 >= v30 )
        {
          a1[4] = v31;
          v32 = a1[1];
          if ( v32 <= v31 )
            v32 = v31;
          a1[1] = v32;
          return 0;
        }
        goto LABEL_24;
      }
      v47 = a1[3] - 1LL;
      if ( v29 + v47 < v29 )
        return (unsigned int)-1073741675;
      v48 = (void *)a1[5];
      v49 = (v29 + v47) & ~v47;
      if ( v48 )
      {
        v56 = a1[1];
        if ( KeGetCurrentIrql() != 2 )
          v9 = PagedPool;
        v57 = ExAllocatePoolWithTag(v9, v49, 0x7274534Du);
        v51 = v57;
        if ( v57 )
        {
          memset(v57, 0, v49);
          v58 = v49;
          if ( v56 < v49 )
            v58 = v56;
          memmove(v51, v48, v58);
          ExFreePoolWithTag(v48, 0x7274534Du);
          goto LABEL_63;
        }
      }
      else
      {
        if ( KeGetCurrentIrql() != 2 )
          v9 = PagedPool;
        v50 = ExAllocatePoolWithTag(v9, v49, 0x7274534Du);
        v51 = v50;
        if ( v50 )
        {
          memset(v50, 0, v49);
LABEL_63:
          a1[5] = v51;
          a1[2] = v49;
          goto LABEL_39;
        }
      }
      return (unsigned int)-1073741801;
    }
  }
  return v13;
}

```

## disassembly

```asm
0x140050e94  push    rbx
0x140050e96  push    rbp
0x140050e97  push    rsi
0x140050e98  push    rdi
0x140050e99  push    r12
0x140050e9b  push    r13
0x140050e9d  push    r14
0x140050e9f  push    r15
0x140050ea1  sub     rsp, 48h
0x140050ea5  mov     r10, [rcx+8]
0x140050ea9  xor     eax, eax
0x140050eab  mov     [rcx+20h], rax
0x140050eaf  mov     rdi, rcx
0x140050eb2  xor     ecx, ecx
0x140050eb4  mov     qword ptr [rsp+88h+var_50], rax
0x140050eb9  mov     r11, r8
0x140050ebc  mov     [rsp+88h+Src], eax
0x140050ec3  mov     rbx, rdx
0x140050ec6  mov     r14d, 200h
0x140050ecc  cmp     rcx, r10
0x140050ecf  ja      short loc_140050EDA
0x140050ed1  lea     rdx, [rcx+8]
0x140050ed5  cmp     rdx, rcx
0x140050ed8  jnb     short loc_140050F21
0x140050eda  test    r9d, r9d
0x140050edd  jz      loc_14005135C
0x140050ee3  mov     rbp, [rdi+8]
0x140050ee7  mov     esi, 4
0x140050eec  mov     [rdi+20h], rbp
0x140050ef0  mov     dword ptr [rsp+88h+var_58], r14d
0x140050ef5  mov     dword ptr [rsp+88h+var_58+4], esi
0x140050ef9  mov     [rsp+88h+Src], 0
0x140050f04  test    bpl, 3
0x140050f08  jnz     short loc_140050F17
0x140050f0a  lea     rcx, [rbp+8]
0x140050f0e  cmp     rcx, rbp
0x140050f11  jnb     loc_140050FCE
0x140050f17  mov     ebx, 0C000000Dh
0x140050f1c  jmp     loc_140050FA7
0x140050f21  cmp     rdx, r10
0x140050f24  ja      short loc_140050EDA
0x140050f26  mov     rax, [rdi+28h]
0x140050f2a  mov     rax, [rcx+rax]
0x140050f2e  mov     [rdi+20h], rdx
0x140050f32  mov     r8, rax
0x140050f35  shr     r8, 20h
0x140050f39  add     r8, rdx
0x140050f3c  cmp     r8, rdx
0x140050f3f  jb      short loc_140050EDA
0x140050f41  lea     rcx, [r8+3]
0x140050f45  cmp     rcx, r8
0x140050f48  jb      short loc_140050EDA
0x140050f4a  and     rcx, 0FFFFFFFFFFFFFFFCh
0x140050f4e  cmp     rcx, r10
0x140050f51  ja      short loc_140050EDA
0x140050f53  cmp     eax, r14d
0x140050f56  jz      short loc_140050F61
0x140050f58  mov     [rdi+20h], rcx
0x140050f5c  jmp     loc_140050ECC
0x140050f61  shr     rax, 20h
0x140050f65  mov     esi, 4
0x140050f6a  cmp     eax, esi
0x140050f6c  ja      short loc_140050FC7
0x140050f6e  jnb     short loc_140050FBB
0x140050f70  test    eax, eax
0x140050f72  jz      short loc_140050FA5
0x140050f74  mov     rcx, rdx
0x140050f77  cmp     rdx, r10
0x140050f7a  ja      short loc_140050F17
0x140050f7c  mov     r8d, eax; Size
0x140050f7f  lea     rbx, [r8+rdx]
0x140050f83  cmp     rbx, rdx
0x140050f86  jb      short loc_140050F17
0x140050f88  cmp     rbx, r10
0x140050f8b  ja      short loc_140050F17
0x140050f8d  mov     rdx, [rdi+28h]
0x140050f91  add     rdx, rcx; Src
0x140050f94  lea     rcx, [rsp+88h+Src]; void *
0x140050f9c  call    memmove
0x140050fa1  mov     [rdi+20h], rbx
0x140050fa5  xor     ebx, ebx
0x140050fa7  mov     eax, ebx
0x140050fa9  add     rsp, 48h
0x140050fad  pop     r15
0x140050faf  pop     r14
0x140050fb1  pop     r13
0x140050fb3  pop     r12
0x140050fb5  pop     rdi
0x140050fb6  pop     rsi
0x140050fb7  pop     rbp
0x140050fb8  pop     rbx
0x140050fb9  retn
0x140050fbb  mov     eax, esi
0x140050fbd  jmp     short loc_140050F74
0x140050fbf  mov     qword ptr [rdi+20h], 0FFFFFFFFFFFFFFFFh
0x140050fc7  mov     ebx, 0C0000095h
0x140050fcc  jmp     short loc_140050FA7
0x140050fce  mov     r15d, 1
0x140050fd4  mov     r12d, 7274534Dh
0x140050fda  cmp     rcx, [rdi+10h]
0x140050fde  ja      loc_1400510D2
0x140050fe4  mov     rcx, [rdi+28h]
0x140050fe8  mov     rax, [rsp+88h+var_58]
0x140050fed  mov     rdx, [rdi+20h]
0x140050ff1  mov     [rdx+rcx], rax
0x140050ff5  mov     rax, [rdi+20h]
0x140050ff9  lea     rcx, [rax+8]
0x140050ffd  cmp     rcx, rax
0x140051000  jb      short loc_140050FBF
0x140051002  mov     [rdi+20h], rcx
0x140051006  lea     rdx, [rcx+4]
0x14005100a  mov     r12, [rdi+8]
0x14005100e  cmp     r12, rcx
0x140051011  cmovbe  r12, rcx
0x140051015  mov     [rdi+8], r12
0x140051019  cmp     rdx, rcx
0x14005101c  jb      loc_140050F17
0x140051022  cmp     rdx, [rdi+10h]
0x140051026  ja      loc_140051146
0x14005102c  mov     rcx, [rdi+20h]
0x140051030  mov     rax, [rdi+28h]
0x140051034  mov     rdx, qword ptr [rsp+88h+var_50]
0x140051039  mov     [rcx+rax], edx
0x14005103c  mov     rax, [rdi+20h]
0x140051040  lea     rcx, [rax+4]
0x140051044  cmp     rcx, rax
0x140051047  jb      loc_140050FBF
0x14005104d  mov     [rdi+20h], rcx
0x140051051  mov     ebx, 0
0x140051056  mov     rax, [rdi+8]
0x14005105a  cmp     rax, rcx
0x14005105d  cmovbe  rax, rcx
0x140051061  mov     [rdi+8], rax
0x140051065  mov     rax, rcx
0x140051068  and     ecx, 3
0x14005106b  jz      loc_140050FA7
0x140051071  sub     rsi, rcx
0x140051074  jz      loc_140050FA7
0x14005107a  lea     rcx, [rsi+rax]
0x14005107e  cmp     rcx, rax
0x140051081  jb      loc_140050F17
0x140051087  cmp     rcx, [rdi+10h]
0x14005108b  ja      loc_1400511BD
0x140051091  mov     rcx, [rdi+20h]
0x140051095  lea     rdx, [rsp+88h+Src]; Src
0x14005109d  add     rcx, [rdi+28h]; void *
0x1400510a1  mov     r8, rsi; Size
0x1400510a4  call    memmove
0x1400510a9  mov     rax, [rdi+20h]
0x1400510ad  lea     rcx, [rsi+rax]
0x1400510b1  cmp     rcx, rax
0x1400510b4  jb      loc_140050FBF
0x1400510ba  mov     [rdi+20h], rcx
0x1400510be  mov     rax, [rdi+8]
0x1400510c2  cmp     rax, rcx
0x1400510c5  cmovbe  rax, rcx
0x1400510c9  mov     [rdi+8], rax
0x1400510cd  jmp     loc_140050FA5
0x1400510d2  mov     rbx, [rdi+18h]
0x1400510d6  dec     rbx
0x1400510d9  lea     rax, [rcx+rbx]
0x1400510dd  cmp     rax, rcx
0x1400510e0  jb      loc_140050FC7
0x1400510e6  mov     r13, [rdi+28h]
0x1400510ea  not     rbx
0x1400510ed  and     rbx, rax
0x1400510f0  call    cs:__imp_KeGetCurrentIrql
0x1400510f7  nop     dword ptr [rax+rax+00h]
0x1400510fc  mov     ecx, r14d
0x1400510ff  mov     r8d, r12d; Tag
0x140051102  mov     rdx, rbx; NumberOfBytes
0x140051105  test    r13, r13
0x140051108  jnz     loc_140051234
0x14005110e  cmp     al, 2
0x140051110  cmovnz  ecx, r15d; PoolType
0x140051114  call    cs:__imp_ExAllocatePoolWithTag
0x14005111b  nop     dword ptr [rax+rax+00h]
0x140051120  mov     r12, rax
0x140051123  test    rax, rax
0x140051126  jz      loc_1400513AD
0x14005112c  mov     r8, rbx; Size
0x14005112f  xor     edx, edx; Val
0x140051131  mov     rcx, rax; void *
0x140051134  call    memset
0x140051139  mov     [rdi+28h], r12
0x14005113d  mov     [rdi+10h], rbx
0x140051141  jmp     loc_140050FE4
0x140051146  mov     rbx, [rdi+18h]
0x14005114a  dec     rbx
0x14005114d  lea     rax, [rdx+rbx]
0x140051151  cmp     rax, rdx
0x140051154  jb      loc_140050FC7
0x14005115a  mov     r13, [rdi+28h]
0x14005115e  not     rbx
0x140051161  and     rbx, rax
0x140051164  call    cs:__imp_KeGetCurrentIrql
0x14005116b  nop     dword ptr [rax+rax+00h]
0x140051170  mov     ecx, r14d
0x140051173  mov     r8d, 7274534Dh; Tag
0x140051179  mov     rdx, rbx; NumberOfBytes
0x14005117c  test    r13, r13
0x14005117f  jnz     loc_14005128D
0x140051185  cmp     al, 2
0x140051187  cmovnz  ecx, r15d; PoolType
0x14005118b  call    cs:__imp_ExAllocatePoolWithTag
0x140051192  nop     dword ptr [rax+rax+00h]
0x140051197  mov     rbp, rax
0x14005119a  test    rax, rax
0x14005119d  jz      loc_1400513AD
0x1400511a3  mov     r8, rbx; Size
0x1400511a6  xor     edx, edx; Val
0x1400511a8  mov     rcx, rax; void *
0x1400511ab  call    memset
0x1400511b0  mov     [rdi+28h], rbp
0x1400511b4  mov     [rdi+10h], rbx
0x1400511b8  jmp     loc_14005102C
0x1400511bd  mov     rbx, [rdi+18h]
0x1400511c1  dec     rbx
0x1400511c4  lea     rax, [rcx+rbx]
0x1400511c8  cmp     rax, rcx
0x1400511cb  jb      loc_140050FC7
0x1400511d1  mov     r12, [rdi+28h]
0x1400511d5  not     rbx
0x1400511d8  and     rbx, rax
0x1400511db  test    r12, r12
0x1400511de  jnz     loc_1400512E6
0x1400511e4  call    cs:__imp_KeGetCurrentIrql
0x1400511eb  nop     dword ptr [rax+rax+00h]
0x1400511f0  mov     r8d, 7274534Dh; Tag
0x1400511f6  mov     rdx, rbx; NumberOfBytes
0x1400511f9  cmp     al, 2
0x1400511fb  cmovnz  r14d, r15d
0x1400511ff  mov     ecx, r14d; PoolType
0x140051202  call    cs:__imp_ExAllocatePoolWithTag
0x140051209  nop     dword ptr [rax+rax+00h]
0x14005120e  mov     rbp, rax
0x140051211  test    rax, rax
0x140051214  jz      loc_1400513AD
0x14005121a  mov     r8, rbx; Size
0x14005121d  xor     edx, edx; Val
0x14005121f  mov     rcx, rax; void *
0x140051222  call    memset
0x140051227  mov     [rdi+28h], rbp
0x14005122b  mov     [rdi+10h], rbx
0x14005122f  jmp     loc_140051091
0x140051234  cmp     al, 2
0x140051236  cmovnz  ecx, r15d; PoolType
0x14005123a  call    cs:__imp_ExAllocatePoolWithTag
0x140051241  nop     dword ptr [rax+rax+00h]
0x140051246  mov     r12, rax
0x140051249  test    rax, rax
0x14005124c  jz      loc_1400513AD
0x140051252  mov     r8, rbx; Size
0x140051255  xor     edx, edx; Val
0x140051257  mov     rcx, rax; void *
0x14005125a  call    memset
0x14005125f  cmp     rbp, rbx
0x140051262  mov     r8, rbx
0x140051265  mov     rdx, r13; Src
0x140051268  mov     rcx, r12; void *
0x14005126b  cmovb   r8, rbp; Size
0x14005126f  call    memmove
0x140051274  mov     edx, 7274534Dh; Tag
0x140051279  mov     rcx, r13; P
0x14005127c  call    cs:__imp_ExFreePoolWithTag
0x140051283  nop     dword ptr [rax+rax+00h]
0x140051288  jmp     loc_140051139
0x14005128d  cmp     al, 2
0x14005128f  cmovnz  ecx, r15d; PoolType
0x140051293  call    cs:__imp_ExAllocatePoolWithTag
0x14005129a  nop     dword ptr [rax+rax+00h]
0x14005129f  mov     rbp, rax
0x1400512a2  test    rax, rax
0x1400512a5  jz      loc_1400513AD
0x1400512ab  mov     r8, rbx; Size
0x1400512ae  xor     edx, edx; Val
0x1400512b0  mov     rcx, rax; void *
0x1400512b3  call    memset
0x1400512b8  cmp     r12, rbx
0x1400512bb  mov     r8, rbx
0x1400512be  mov     rdx, r13; Src
0x1400512c1  mov     rcx, rbp; void *
0x1400512c4  cmovb   r8, r12; Size
0x1400512c8  call    memmove
0x1400512cd  mov     edx, 7274534Dh; Tag
0x1400512d2  mov     rcx, r13; P
0x1400512d5  call    cs:__imp_ExFreePoolWithTag
0x1400512dc  nop     dword ptr [rax+rax+00h]
0x1400512e1  jmp     loc_1400511B0
0x1400512e6  mov     r13, [rdi+8]
0x1400512ea  call    cs:__imp_KeGetCurrentIrql
0x1400512f1  nop     dword ptr [rax+rax+00h]
0x1400512f6  cmp     al, 2
0x1400512f8  mov     rdx, rbx; NumberOfBytes
0x1400512fb  cmovnz  r14d, r15d
0x1400512ff  mov     r15d, 7274534Dh
0x140051305  mov     r8d, r15d; Tag
0x140051308  mov     ecx, r14d; PoolType
0x14005130b  call    cs:__imp_ExAllocatePoolWithTag
0x140051312  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
