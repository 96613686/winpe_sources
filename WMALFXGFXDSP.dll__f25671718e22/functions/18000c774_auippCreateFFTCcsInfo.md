# auippCreateFFTCcsInfo

- ea: `0x18000c774`
- end: `0x18000c872`
- name: `auippCreateFFTCcsInfo`
- size: `254`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000c720`

## callees

- `0x18000c774`
- `0x18000c8f4`
- `0x18000c9a0`
- `0x180016c00`
- `0x180016ea0`
- `0x180085020`

## pseudocode

```c
__int64 __fastcall auippCreateFFTCcsInfo(void **a1)
{
  int FFTInfo; // ebx
  unsigned int *v4; // rax
  unsigned int v5; // ecx
  unsigned int v6; // eax
  int v7; // eax
  unsigned int v8; // esi
  int i; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r14
  int v13; // [rsp+68h] [rbp+20h] BYREF

  v13 = 0;
  FFTInfo = prvCreateFFTInfo();
  if ( FFTInfo < 0 )
    goto LABEL_2;
  v4 = (unsigned int *)*a1;
  if ( !*((_QWORD *)*a1 + 1) || (v5 = *v4, v6 = v4[1], v6 < v5) || (v7 = v6 - v5, v8 = v7 + 1, v7 + 1 <= v7) )
  {
LABEL_14:
    FFTInfo = -2147467259;
LABEL_2:
    auippDeleteFFTInfo(*a1);
    *a1 = 0;
    return (unsigned int)FFTInfo;
  }
  for ( i = 0; ; ++i )
  {
    v10 = *a1;
    if ( i >= (int)v8 )
      break;
    v11 = (unsigned int)(*(_DWORD *)v10 + i);
    if ( (unsigned int)v11 < *(_DWORD *)v10 )
      goto LABEL_14;
    v12 = 32LL * i;
    if ( (int)ippsFFTInitAlloc_R_32f(v12 + v10[1], v11, 2) < 0 )
      goto LABEL_14;
    *(_DWORD *)(*((_QWORD *)*a1 + 1) + v12 + 8) = 1 << (i + *(_DWORD *)*a1);
    if ( (int)ippsFFTGetBufSize_R_32f(*(_QWORD *)(*((_QWORD *)*a1 + 1) + 32LL * i), &v13) < 0 )
      goto LABEL_14;
    *(_DWORD *)(*((_QWORD *)*a1 + 1) + v12 + 24) = v13;
  }
  *((_DWORD *)v10 + 4) = 2;
  FFTInfo = prvAllocateWorkBuf(*((_QWORD *)*a1 + 1), v8, *((unsigned int *)*a1 + 4));
  if ( FFTInfo < 0 )
    goto LABEL_2;
  return (unsigned int)FFTInfo;
}

```

## disassembly

```asm
0x18000c774  mov     [rsp+arg_18], r9d
0x18000c779  push    rbx
0x18000c77a  push    rsi
0x18000c77b  push    rdi
0x18000c77c  push    r14
0x18000c77e  sub     rsp, 28h
0x18000c782  mov     rdi, rcx
0x18000c785  mov     [rsp+48h+arg_18], 0
0x18000c78d  call    prvCreateFFTInfo
0x18000c792  mov     ebx, eax
0x18000c794  test    eax, eax
0x18000c796  jns     short loc_18000C7D4
0x18000c798  mov     rcx, [rdi]; Block
0x18000c79b  call    auippDeleteFFTInfo
0x18000c7a0  mov     qword ptr [rdi], 0
0x18000c7a7  jmp     short loc_18000C7C8
0x18000c7a9  mov     dword ptr [rcx+10h], 2
0x18000c7b0  mov     edx, esi
0x18000c7b2  mov     rcx, [rdi]
0x18000c7b5  mov     r8d, [rcx+10h]
0x18000c7b9  mov     rcx, [rcx+8]
0x18000c7bd  call    prvAllocateWorkBuf
0x18000c7c2  mov     ebx, eax
0x18000c7c4  test    eax, eax
0x18000c7c6  js      short loc_18000C798
0x18000c7c8  mov     eax, ebx
0x18000c7ca  add     rsp, 28h
0x18000c7ce  pop     r14
0x18000c7d0  pop     rdi
0x18000c7d1  pop     rsi
0x18000c7d2  pop     rbx
0x18000c7d3  retn
0x18000c7d4  mov     rax, [rdi]
0x18000c7d7  cmp     qword ptr [rax+8], 0
0x18000c7dc  jz      loc_18000C868
0x18000c7e2  mov     ecx, [rax]
0x18000c7e4  mov     eax, [rax+4]
0x18000c7e7  cmp     eax, ecx
0x18000c7e9  jb      short loc_18000C868
0x18000c7eb  sub     eax, ecx
0x18000c7ed  lea     esi, [rax+1]
0x18000c7f0  cmp     esi, eax
0x18000c7f2  jl      short loc_18000C868
0x18000c7f4  xor     ebx, ebx
0x18000c7f6  mov     rcx, [rdi]
0x18000c7f9  cmp     ebx, esi
0x18000c7fb  jge     short loc_18000C7A9
0x18000c7fd  mov     eax, [rcx]
0x18000c7ff  lea     edx, [rax+rbx]
0x18000c802  cmp     edx, eax
0x18000c804  jb      short loc_18000C868
0x18000c806  mov     rcx, [rcx+8]
0x18000c80a  xor     r9d, r9d
0x18000c80d  movsxd  r14, ebx
0x18000c810  shl     r14, 5
0x18000c814  add     rcx, r14
0x18000c817  lea     r8d, [r9+2]
0x18000c81b  call    ippsFFTInitAlloc_R_32f
0x18000c820  test    eax, eax
0x18000c822  js      short loc_18000C868
0x18000c824  mov     rax, [rdi]
0x18000c827  mov     edx, 1
0x18000c82c  mov     ecx, [rax]
0x18000c82e  mov     rax, [rax+8]
0x18000c832  add     ecx, ebx
0x18000c834  shl     edx, cl
0x18000c836  mov     [rax+r14+8], edx
0x18000c83b  lea     rdx, [rsp+48h+arg_18]
0x18000c840  mov     rax, [rdi]
0x18000c843  mov     rcx, [rax+8]
0x18000c847  mov     rcx, [rcx+r14]
0x18000c84b  call    ippsFFTGetBufSize_R_32f
0x18000c850  test    eax, eax
0x18000c852  js      short loc_18000C868
0x18000c854  mov     rax, [rdi]
0x18000c857  inc     ebx
0x18000c859  mov     rcx, [rax+8]
0x18000c85d  mov     eax, [rsp+48h+arg_18]
0x18000c861  mov     [rcx+r14+18h], eax
0x18000c866  jmp     short loc_18000C7F6
0x18000c868  mov     ebx, 80004005h
0x18000c86d  jmp     loc_18000C798
```
