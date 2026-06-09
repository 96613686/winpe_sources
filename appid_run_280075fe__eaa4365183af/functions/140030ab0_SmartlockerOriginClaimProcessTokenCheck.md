# SmartlockerOriginClaimProcessTokenCheck

- ea: `0x140030ab0`
- end: `0x140030c74`
- name: `SmartlockerOriginClaimProcessTokenCheck`
- size: `452`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001bbc`
- `0x1400236ac`
- `0x140023a40`
- `0x14002f560`

## callees

- `0x140023110`
- `0x140030ab0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140030c00`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030c63`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030c00`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030c63`
- `ntoskrnl!ExAllocatePool2` at `0x140030afd`
- `ntoskrnl!ExAllocatePool2` at `0x140030afd`
- `ntoskrnl!ZwQuerySecurityAttributesToken` at `0x140030b39`
- `ntoskrnl!ZwQuerySecurityAttributesToken` at `0x140030b39`
- `ksecdd!BCryptGenRandom` at `0x140030bdd`
- `ksecdd!BCryptGenRandom` at `0x140030bdd`

## pseudocode

```c
__int64 __fastcall SmartlockerOriginClaimProcessTokenCheck(
        __int64 a1,
        char a2,
        _BYTE *a3,
        int *a4,
        _QWORD *a5,
        __int64 *a6)
{
  __int64 v6; // r14
  int v10; // r15d
  unsigned int v11; // edi
  __int64 Pool2; // rbx
  int v13; // eax
  __int64 v14; // rax
  _DWORD *v15; // rcx
  unsigned int v16; // ebp
  unsigned int v17; // eax
  unsigned int v18; // edi
  __int64 v19; // rcx
  int v20; // ecx
  __int64 result; // rax
  unsigned int v23; // [rsp+88h] [rbp+20h] BYREF

  v6 = 0;
  v23 = 0;
  v10 = 326;
  v11 = 436;
  while ( 1 )
  {
    Pool2 = ExAllocatePool2(258, v11, 1098149235, a4);
    if ( !Pool2 )
      goto LABEL_20;
    v13 = ZwQuerySecurityAttributesToken(a1, L"24", 1, Pool2, v11, &v23);
    if ( v13 != -1073741789 )
      break;
    if ( v11 >= v23 )
      goto LABEL_19;
    v11 = v23;
    ExFreePoolWithTag((PVOID)Pool2, 0x41746D73u);
  }
  if ( v13 < 0 )
  {
LABEL_19:
    ExFreePoolWithTag((PVOID)Pool2, 0x41746D73u);
    Pool2 = 0;
LABEL_20:
    v18 = -1073741823;
    goto LABEL_21;
  }
  if ( !*(_DWORD *)(Pool2 + 4) )
    goto LABEL_20;
  v14 = *(_QWORD *)(Pool2 + 8);
  if ( *(_WORD *)(v14 + 16) != 16 )
    goto LABEL_20;
  v15 = *(_DWORD **)(v14 + 32);
  v16 = v15[2];
  if ( v16 < 0x40 )
    goto LABEL_20;
  v6 = *(_QWORD *)v15;
  v10 = v15[2];
  v17 = *(_DWORD *)(*(_QWORD *)v15 + 8LL);
  if ( v17 <= 1 || (v18 = -1073741823, v17 == 4) )
    v18 = 0;
  if ( a2 && !*(_DWORD *)(v6 + 4) )
  {
    v19 = *(_QWORD *)(v6 + 32) - *(_QWORD *)(v6 + 16);
    if ( !v19 )
      v19 = *(_QWORD *)(v6 + 40) - *(_QWORD *)(v6 + 24);
    if ( !v19 )
    {
      if ( a3 )
        *a3 = 1;
      BCryptGenRandom(0, (PUCHAR)(v6 + 32), 0x10u, 2u);
      SmartlockerTagProcessToken(a1, v16, v6);
    }
  }
LABEL_21:
  v20 = 0;
  result = v18;
  if ( v6 )
    v20 = v10;
  *a4 = v20;
  *a5 = v6;
  *a6 = Pool2;
  return result;
}

```

## disassembly

```asm
0x140030ab0  mov     [rsp+arg_8], dl
0x140030ab4  push    rbx
0x140030ab5  push    rsi
0x140030ab6  push    rdi
0x140030ab7  push    r12
0x140030ab9  push    r13
0x140030abb  push    r14
0x140030abd  push    r15
0x140030abf  sub     rsp, 30h
0x140030ac3  xor     r14d, r14d
0x140030ac6  mov     [rsp+68h+arg_0], rbp
0x140030acb  mov     [rsp+68h+arg_18], r14d
0x140030ad3  mov     r12, r9
0x140030ad6  mov     r13, r8
0x140030ad9  mov     rsi, rcx
0x140030adc  mov     r15d, 146h
0x140030ae2  mov     edi, 1B4h
0x140030ae7  nop     word ptr [rax+rax+00000000h]
0x140030af0  mov     edx, edi
0x140030af2  mov     ecx, 102h
0x140030af7  mov     r8d, 41746D73h
0x140030afd  call    cs:__imp_ExAllocatePool2
0x140030b04  nop     dword ptr [rax+rax+00h]
0x140030b09  mov     rbx, rax
0x140030b0c  test    rax, rax
0x140030b0f  jz      loc_140030C0E
0x140030b15  lea     rax, [rsp+68h+arg_18]
0x140030b1d  mov     r9, rbx
0x140030b20  mov     [rsp+68h+var_40], rax
0x140030b25  lea     rdx, a24; "24"
0x140030b2c  mov     r8d, 1
0x140030b32  mov     [rsp+68h+var_48], edi
0x140030b36  mov     rcx, rsi
0x140030b39  call    cs:__imp_ZwQuerySecurityAttributesToken
0x140030b40  nop     dword ptr [rax+rax+00h]
0x140030b45  cmp     eax, 0C0000023h
0x140030b4a  jz      loc_140030C4E
0x140030b50  test    eax, eax
0x140030b52  js      loc_140030BF8
0x140030b58  cmp     [rbx+4], r14d
0x140030b5c  jbe     loc_140030C0E
0x140030b62  mov     rax, [rbx+8]
0x140030b66  cmp     word ptr [rax+10h], 10h
0x140030b6b  jnz     loc_140030C0E
0x140030b71  mov     rcx, [rax+20h]
0x140030b75  mov     ebp, [rcx+8]
0x140030b78  cmp     ebp, 40h ; '@'
0x140030b7b  jb      loc_140030C0E
0x140030b81  mov     r14, [rcx]
0x140030b84  mov     r15d, ebp
0x140030b87  mov     eax, [r14+8]
0x140030b8b  cmp     eax, 1
0x140030b8e  jbe     short loc_140030B9A
0x140030b90  mov     edi, 0C0000001h
0x140030b95  cmp     eax, 4
0x140030b98  jnz     short loc_140030B9C
0x140030b9a  xor     edi, edi
0x140030b9c  cmp     [rsp+68h+arg_8], 0
0x140030ba1  jz      short loc_140030C13
0x140030ba3  cmp     dword ptr [r14+4], 0
0x140030ba8  jnz     short loc_140030C13
0x140030baa  mov     rcx, [r14+20h]
0x140030bae  lea     rdx, [r14+20h]; pbBuffer
0x140030bb2  sub     rcx, [r14+10h]
0x140030bb6  jnz     short loc_140030BC0
0x140030bb8  mov     rcx, [rdx+8]
0x140030bbc  sub     rcx, [r14+18h]
0x140030bc0  test    rcx, rcx
0x140030bc3  jnz     short loc_140030C13
0x140030bc5  test    r13, r13
0x140030bc8  jz      short loc_140030BCF
0x140030bca  mov     byte ptr [r13+0], 1
0x140030bcf  xor     ecx, ecx; hAlgorithm
0x140030bd1  mov     r9d, 2; dwFlags
0x140030bd7  mov     r8d, 10h; cbBuffer
0x140030bdd  call    cs:__imp_BCryptGenRandom
0x140030be4  nop     dword ptr [rax+rax+00h]
0x140030be9  mov     r8, r14
0x140030bec  mov     edx, ebp
0x140030bee  mov     rcx, rsi
0x140030bf1  call    SmartlockerTagProcessToken
0x140030bf6  jmp     short loc_140030C13
0x140030bf8  mov     edx, 41746D73h; Tag
0x140030bfd  mov     rcx, rbx; P
0x140030c00  call    cs:__imp_ExFreePoolWithTag
0x140030c07  nop     dword ptr [rax+rax+00h]
0x140030c0c  xor     ebx, ebx
0x140030c0e  mov     edi, 0C0000001h
0x140030c13  mov     rbp, [rsp+68h+arg_0]
0x140030c18  xor     ecx, ecx
0x140030c1a  test    r14, r14
0x140030c1d  mov     eax, edi
0x140030c1f  cmovnz  ecx, r15d
0x140030c23  mov     [r12], ecx
0x140030c27  mov     rcx, [rsp+68h+arg_20]
0x140030c2f  mov     [rcx], r14
0x140030c32  mov     rcx, [rsp+68h+arg_28]
0x140030c3a  mov     [rcx], rbx
0x140030c3d  add     rsp, 30h
0x140030c41  pop     r15
0x140030c43  pop     r14
0x140030c45  pop     r13
0x140030c47  pop     r12
0x140030c49  pop     rdi
0x140030c4a  pop     rsi
0x140030c4b  pop     rbx
0x140030c4c  retn
0x140030c4e  mov     eax, [rsp+68h+arg_18]
0x140030c55  cmp     edi, eax
0x140030c57  jnb     short loc_140030BF8
0x140030c59  mov     edx, 41746D73h; Tag
0x140030c5e  mov     rcx, rbx; P
0x140030c61  mov     edi, eax
0x140030c63  call    cs:__imp_ExFreePoolWithTag
0x140030c6a  nop     dword ptr [rax+rax+00h]
0x140030c6f  jmp     loc_140030AF0
```
