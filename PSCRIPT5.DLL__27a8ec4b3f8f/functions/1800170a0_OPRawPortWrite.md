# OPRawPortWrite

- ea: `0x1800170a0`
- end: `0x180017138`
- name: `OPRawPortWrite`
- size: `152`
- prototype: `__int64(__int64, const char *, unsigned int, ...)`
- caller_count: `73`
- callee_count: `4`
- tags: ``

## callers

- `0x180005c18`
- `0x180005d44`
- `0x180007db0`
- `0x18000982c`
- `0x1800099ec`
- `0x180009eb4`
- `0x18000a420`
- `0x18000a81c`
- `0x18000ac50`
- `0x18000af70`
- `0x18000c180`
- `0x18000d0d0`
- `0x18000d200`
- `0x18000e4d0`
- `0x18000e910`
- `0x18000ec74`
- `0x18000f2e4`
- `0x18000fe54`
- `0x180011b5c`
- `0x180012100`
- `0x180012470`
- `0x1800128a0`
- `0x180012aa0`
- `0x180012b2c`
- `0x180012ba4`
- `0x180012c30`
- `0x180013114`
- `0x1800135b0`
- `0x180013780`
- `0x180013b68`
- `0x180014058`
- `0x180014154`
- `0x18001426c`
- `0x1800143c0`
- `0x180014434`
- `0x1800147b0`
- `0x1800148c4`
- `0x180014a84`
- `0x180014ccc`
- `0x180014d7c`
- `0x18001502c`
- `0x180015180`
- `0x1800153f0`
- `0x18001597c`
- `0x18001600c`
- `0x1800160b0`
- `0x1800161f8`
- `0x180016444`
- `0x1800166c0`
- `0x1800169ec`

## callees

- `0x180016828`
- `0x180016df0`
- `0x1800170a0`
- `0x18005e0c4`

## pseudocode

```c
__int64 OPRawPortWrite(__int64 a1, const char *a2, unsigned int a3, ...)
{
  __int64 result; // rax
  int i; // ecx
  _DWORD *v8; // rcx
  unsigned int v9; // eax
  unsigned int v10; // edx
  void *v11; // rcx
  __int64 v12; // rbx

  if ( *(_QWORD *)(a1 + 2896) || (result = BAllocateSpoolBuf(a1), (_DWORD)result) )
  {
    for ( i = *(_DWORD *)(a1 + 3440); !i; i = *(_DWORD *)(a1 + 3440) )
    {
      if ( !a3 )
        break;
      v8 = *(_DWORD **)(a1 + 2896);
      v9 = a3;
      v10 = v8[2] - *v8;
      v11 = *(void **)v8;
      if ( v10 <= a3 )
        v9 = v10;
      v12 = v9;
      memcpy_0(v11, a2, v9);
      a2 += v12;
      a3 -= v12;
      **(_QWORD **)(a1 + 2896) += v12;
      if ( *(_QWORD *)(*(_QWORD *)(a1 + 2896) + 8LL) <= **(_QWORD **)(a1 + 2896) )
        OPFlushToSpool(a1);
    }
    return i == 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800170a0  push    rbx
0x1800170a2  push    rbp
0x1800170a3  push    rsi
0x1800170a4  push    rdi
0x1800170a5  sub     rsp, 28h
0x1800170a9  cmp     qword ptr [rcx+0B50h], 0
0x1800170b1  mov     esi, r8d
0x1800170b4  mov     rbp, rdx
0x1800170b7  mov     rdi, rcx
0x1800170ba  jnz     short loc_1800170C5
0x1800170bc  call    BAllocateSpoolBuf
0x1800170c1  test    eax, eax
0x1800170c3  jz      short loc_18001712E
0x1800170c5  mov     ecx, [rdi+0D70h]
0x1800170cb  test    ecx, ecx
0x1800170cd  jnz     short loc_180017127
0x1800170cf  test    esi, esi
0x1800170d1  jz      short loc_180017127
0x1800170d3  mov     rcx, [rdi+0B50h]
0x1800170da  mov     eax, esi
0x1800170dc  mov     edx, [rcx+8]
0x1800170df  sub     edx, [rcx]
0x1800170e1  mov     rcx, [rcx]; void *
0x1800170e4  cmp     edx, esi
0x1800170e6  cmovbe  eax, edx
0x1800170e9  mov     rdx, rbp; Src
0x1800170ec  mov     r8d, eax; Size
0x1800170ef  mov     ebx, eax
0x1800170f1  call    memcpy_0
0x1800170f6  mov     rax, [rdi+0B50h]
0x1800170fd  add     rbp, rbx
0x180017100  sub     esi, ebx
0x180017102  add     [rax], rbx
0x180017105  mov     rcx, [rdi+0B50h]
0x18001710c  mov     rax, [rcx]
0x18001710f  cmp     [rcx+8], rax
0x180017113  ja      short loc_18001711D
0x180017115  mov     rcx, rdi
0x180017118  call    OPFlushToSpool
0x18001711d  mov     ecx, [rdi+0D70h]
0x180017123  test    ecx, ecx
0x180017125  jz      short loc_1800170CF
0x180017127  xor     eax, eax
0x180017129  test    ecx, ecx
0x18001712b  setz    al
0x18001712e  add     rsp, 28h
0x180017132  pop     rdi
0x180017133  pop     rsi
0x180017134  pop     rbp
0x180017135  pop     rbx
0x180017136  retn
```
