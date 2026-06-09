# HampConnectionDeserializeActivities

- ea: `0x1800046e4`
- end: `0x180004863`
- name: `HampConnectionDeserializeActivities`
- size: `383`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180003430`

## callees

- `0x180001f10`
- `0x1800046e4`
- `0x180010fb0`
- `0x18001ae8e`

## pseudocode

```c
__int64 __fastcall HampConnectionDeserializeActivities(__int64 a1, __int64 a2)
{
  unsigned __int64 v2; // rbx
  __int64 result; // rax
  void *v6; // rax
  void *v7; // rax
  __int64 v8; // r10
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // rdx
  size_t size; // [rsp+58h] [rbp+10h] BYREF

  v2 = *(unsigned int *)(a2 + 16);
  size = 0;
  if ( !(_DWORD)v2 )
    return 0;
  result = RtlULongLongMult((unsigned int)v2, 0xA0u, &size);
  if ( (int)result < 0 )
    return result;
  v6 = MIDL_user_allocate(size);
  *(_QWORD *)(a1 + 136) = v6;
  if ( !v6 )
    return 3221225495LL;
  memset_0(v6, 0, size);
  result = RtlULongLongMult(v2, 8u, &size);
  if ( (int)result >= 0 )
  {
    v7 = MIDL_user_allocate(size);
    *(_QWORD *)(a1 + 144) = v7;
    if ( !v7 )
      return 3221225495LL;
    memset_0(v7, 0, size);
    v8 = 0;
    *(_DWORD *)(a1 + 152) = v2;
    do
    {
      v9 = *(_QWORD *)(a2 + 8);
      v10 = *(_QWORD *)(a1 + 136);
      v11 = 160 * v8;
      v12 = 152LL * (unsigned int)v8;
      *(_OWORD *)(v11 + v10) = *(_OWORD *)(v12 + v9);
      *(_OWORD *)(v11 + v10 + 16) = *(_OWORD *)(v12 + v9 + 16);
      *(_OWORD *)(v11 + v10 + 32) = *(_OWORD *)(v12 + v9 + 32);
      *(_OWORD *)(v11 + v10 + 48) = *(_OWORD *)(v12 + v9 + 48);
      *(_OWORD *)(v11 + v10 + 64) = *(_OWORD *)(v12 + v9 + 64);
      *(_OWORD *)(v11 + v10 + 80) = *(_OWORD *)(v12 + v9 + 80);
      *(_OWORD *)(v11 + v10 + 96) = *(_OWORD *)(v12 + v9 + 96);
      *(_OWORD *)(v11 + v10 + 112) = *(_OWORD *)(v12 + v9 + 112);
      *(_OWORD *)(v11 + v10 + 128) = *(_OWORD *)(v12 + v9 + 128);
      *(_QWORD *)(v11 + v10 + 144) = *(_QWORD *)(v12 + v9 + 144);
      *(_QWORD *)(*(_QWORD *)(a1 + 144) + 8 * v8) = 160 * v8 + *(_QWORD *)(a1 + 136);
      v8 = (unsigned int)(v8 + 1);
    }
    while ( (unsigned int)v8 < *(_DWORD *)(a1 + 152) );
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800046e4  push    rbx
0x1800046e6  push    rbp
0x1800046e7  push    rsi
0x1800046e8  push    rdi
0x1800046e9  sub     rsp, 28h
0x1800046ed  mov     ebx, [rdx+10h]
0x1800046f0  mov     rbp, rdx
0x1800046f3  mov     [rsp+48h+size], 0
0x1800046fc  mov     rdi, rcx
0x1800046ff  test    ebx, ebx
0x180004701  jz      loc_180004858
0x180004707  lea     r8, [rsp+48h+size]; unsigned __int64 *
0x18000470c  mov     edx, 0A0h; unsigned __int64
0x180004711  mov     ecx, ebx; unsigned __int64
0x180004713  call    ?RtlULongLongMult@@YAJ_K0PEA_K@Z; RtlULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180004718  test    eax, eax
0x18000471a  js      loc_18000485A
0x180004720  mov     rcx, [rsp+48h+size]; size
0x180004725  call    MIDL_user_allocate
0x18000472a  mov     [rdi+88h], rax
0x180004731  test    rax, rax
0x180004734  jnz     short loc_180004740
0x180004736  mov     eax, 0C0000017h
0x18000473b  jmp     loc_18000485A
0x180004740  mov     r8, [rsp+48h+size]; Size
0x180004745  xor     edx, edx; Val
0x180004747  mov     rcx, rax; void *
0x18000474a  call    memset_0
0x18000474f  lea     r8, [rsp+48h+size]; unsigned __int64 *
0x180004754  mov     edx, 8; unsigned __int64
0x180004759  mov     rcx, rbx; unsigned __int64
0x18000475c  call    ?RtlULongLongMult@@YAJ_K0PEA_K@Z; RtlULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180004761  test    eax, eax
0x180004763  js      loc_18000485A
0x180004769  mov     rcx, [rsp+48h+size]; size
0x18000476e  call    MIDL_user_allocate
0x180004773  mov     [rdi+90h], rax
0x18000477a  test    rax, rax
0x18000477d  jz      short loc_180004736
0x18000477f  mov     r8, [rsp+48h+size]; Size
0x180004784  xor     edx, edx; Val
0x180004786  mov     rcx, rax; void *
0x180004789  call    memset_0
0x18000478e  xor     r10d, r10d
0x180004791  mov     [rdi+98h], ebx
0x180004797  test    ebx, ebx
0x180004799  jz      loc_180004858
0x18000479f  mov     rax, [rbp+8]
0x1800047a3  lea     r8, [r10+r10*4]
0x1800047a7  mov     rcx, [rdi+88h]
0x1800047ae  shl     r8, 5
0x1800047b2  mov     r9d, r10d
0x1800047b5  imul    rdx, r9, 98h
0x1800047bc  movups  xmm0, xmmword ptr [rdx+rax]
0x1800047c0  movups  xmmword ptr [r8+rcx], xmm0
0x1800047c5  movups  xmm1, xmmword ptr [rdx+rax+10h]
0x1800047ca  movups  xmmword ptr [r8+rcx+10h], xmm1
0x1800047d0  movups  xmm0, xmmword ptr [rdx+rax+20h]
0x1800047d5  movups  xmmword ptr [r8+rcx+20h], xmm0
0x1800047db  movups  xmm1, xmmword ptr [rdx+rax+30h]
0x1800047e0  movups  xmmword ptr [r8+rcx+30h], xmm1
0x1800047e6  movups  xmm0, xmmword ptr [rdx+rax+40h]
0x1800047eb  movups  xmmword ptr [r8+rcx+40h], xmm0
0x1800047f1  movups  xmm1, xmmword ptr [rdx+rax+50h]
0x1800047f6  movups  xmmword ptr [r8+rcx+50h], xmm1
0x1800047fc  movups  xmm0, xmmword ptr [rdx+rax+60h]
0x180004801  movups  xmmword ptr [r8+rcx+60h], xmm0
0x180004807  movups  xmm1, xmmword ptr [rdx+rax+70h]
0x18000480c  movups  xmmword ptr [r8+rcx+70h], xmm1
0x180004812  movups  xmm0, xmmword ptr [rdx+rax+80h]
0x18000481a  movups  xmmword ptr [r8+rcx+80h], xmm0
0x180004823  mov     rax, [rdx+rax+90h]
0x18000482b  mov     [r8+rcx+90h], rax
0x180004833  mov     rcx, [rdi+88h]
0x18000483a  mov     rax, [rdi+90h]
0x180004841  add     rcx, r8
0x180004844  mov     [rax+r10*8], rcx
0x180004848  inc     r10d
0x18000484b  cmp     r10d, [rdi+98h]
0x180004852  jb      loc_18000479F
0x180004858  xor     eax, eax
0x18000485a  add     rsp, 28h
0x18000485e  pop     rdi
0x18000485f  pop     rsi
0x180004860  pop     rbp
0x180004861  pop     rbx
0x180004862  retn
```
