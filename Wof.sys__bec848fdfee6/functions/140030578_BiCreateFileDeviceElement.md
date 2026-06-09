# BiCreateFileDeviceElement

- ea: `0x140030578`
- end: `0x140030745`
- name: `BiCreateFileDeviceElement`
- size: `461`
- prototype: `__int64 __fastcall(const wchar_t *Src, _QWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14003074c`

## callees

- `0x14000da0d`
- `0x1400116c0`
- `0x1400119c0`
- `0x140030578`

## import_xrefs

- `ntoskrnl!wcscpy_s` at `0x1400306bc`
- `ntoskrnl!wcscpy_s` at `0x1400306e8`
- `ntoskrnl!wcscpy_s` at `0x1400306bc`
- `ntoskrnl!wcscpy_s` at `0x1400306e8`
- `ntoskrnl!ExAllocatePool2` at `0x1400305f6`
- `ntoskrnl!ExAllocatePool2` at `0x14003066b`
- `ntoskrnl!ExAllocatePool2` at `0x1400305f6`
- `ntoskrnl!ExAllocatePool2` at `0x14003066b`
- `ntoskrnl!wcschr` at `0x1400305c4`
- `ntoskrnl!wcschr` at `0x1400305c4`
- `ntoskrnl!_wcsnicmp` at `0x1400305a6`
- `ntoskrnl!_wcsnicmp` at `0x1400305a6`

## pseudocode

```c
__int64 __fastcall BiCreateFileDeviceElement(const wchar_t *Src, _QWORD *a2, unsigned int *a3)
{
  wchar_t *v4; // rax
  const wchar_t *v5; // r14
  __int64 v6; // rbx
  char *Pool2; // rsi
  int v8; // ebx
  size_t v9; // rbx
  __int64 v10; // rbp
  __int64 v11; // rdx
  __int64 v12; // rax
  int v13; // r15d
  unsigned int v14; // r13d
  char *v15; // rax
  char *v16; // rdi
  __int64 v17; // rdx

  if ( _wcsnicmp(Src, L"\\Device\\HarddiskVolume", 0x16u) )
    return (unsigned int)-1073741811;
  v4 = wcschr(Src + 22, 0x5Cu);
  if ( (v5 = v4) == 0 )
  {
    return (unsigned int)-1073741811;
  }
  else
  {
    v6 = v4 - Src;
    Pool2 = (char *)ExAllocatePool2(258, 2LL * (unsigned int)(v6 + 1), 1262764866);
    if ( Pool2 )
    {
      v9 = 2LL * (unsigned int)v6;
      memmove(Pool2, Src, v9);
      v10 = -1;
      *(_WORD *)&Pool2[v9] = 0;
      v11 = -1;
      do
        ++v11;
      while ( *(_WORD *)&Pool2[2 * v11] );
      v12 = -1;
      do
        ++v12;
      while ( v5[v12] );
      v13 = 2 * v12 + 46;
      v14 = v13 + 2 * (v11 + 11);
      v15 = (char *)ExAllocatePool2(258, v14, 1262764866);
      v16 = v15;
      if ( v15 )
      {
        v8 = 0;
        memset(v15, 0, v14);
        v17 = -1;
        *((_DWORD *)v16 + 5) = v13;
        *(_DWORD *)v16 = 3;
        do
          ++v17;
        while ( v5[v17] );
        wcscpy_s((wchar_t *)v16 + 12, v17 + 1, v5);
        *(_DWORD *)&v16[v13] = 2;
        do
          ++v10;
        while ( *(_WORD *)&Pool2[2 * v10] );
        wcscpy_s((wchar_t *)&v16[v13 + 20], v10 + 1, (const wchar_t *)Pool2);
        *a2 = v16;
        *a3 = v14;
      }
      else
      {
        v8 = -1073741670;
      }
      ExFreePoolWithTag_0(Pool2, 0x4B444342u);
      if ( v8 < 0 && v16 )
        ExFreePoolWithTag_0(v16, 0x4B444342u);
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140030578  mov     [rsp+arg_0], rbx
0x14003057d  mov     [rsp+arg_10], r8
0x140030582  mov     [rsp+arg_8], rdx
0x140030587  push    rbp
0x140030588  push    rsi
0x140030589  push    rdi
0x14003058a  push    r12
0x14003058c  push    r13
0x14003058e  push    r14
0x140030590  push    r15
0x140030592  sub     rsp, 20h
0x140030596  mov     r8d, 16h; MaxCount
0x14003059c  lea     rdx, aDeviceHarddisk_0; "\\Device\\HarddiskVolume"
0x1400305a3  mov     rdi, rcx
0x1400305a6  call    cs:__imp__wcsnicmp
0x1400305ad  nop     dword ptr [rax+rax+00h]
0x1400305b2  xor     r15d, r15d
0x1400305b5  test    eax, eax
0x1400305b7  jnz     loc_140030728
0x1400305bd  lea     edx, [rax+5Ch]; Ch
0x1400305c0  lea     rcx, [rdi+2Ch]; Str
0x1400305c4  call    cs:__imp_wcschr
0x1400305cb  nop     dword ptr [rax+rax+00h]
0x1400305d0  mov     r14, rax
0x1400305d3  test    rax, rax
0x1400305d6  jz      loc_140030728
0x1400305dc  mov     rbx, rax
0x1400305df  mov     ecx, 102h
0x1400305e4  sub     rbx, rdi
0x1400305e7  mov     r8d, 4B444342h
0x1400305ed  sar     rbx, 1
0x1400305f0  lea     edx, [rbx+1]
0x1400305f3  add     rdx, rdx
0x1400305f6  call    cs:__imp_ExAllocatePool2
0x1400305fd  nop     dword ptr [rax+rax+00h]
0x140030602  mov     rsi, rax
0x140030605  test    rax, rax
0x140030608  jnz     short loc_140030614
0x14003060a  mov     ebx, 0C000009Ah
0x14003060f  jmp     loc_14003072D
0x140030614  mov     eax, ebx
0x140030616  mov     rdx, rdi; Src
0x140030619  mov     rcx, rsi; void *
0x14003061c  lea     rbx, [rax+rax]
0x140030620  mov     r8, rbx; Size
0x140030623  call    memmove
0x140030628  or      rbp, 0FFFFFFFFFFFFFFFFh
0x14003062c  mov     [rbx+rsi], r15w
0x140030631  mov     rdx, rbp
0x140030634  inc     rdx
0x140030637  cmp     [rsi+rdx*2], r15w
0x14003063c  jnz     short loc_140030634
0x14003063e  mov     rax, rbp
0x140030641  inc     rax
0x140030644  cmp     [r14+rax*2], r15w
0x140030649  jnz     short loc_140030641
0x14003064b  lea     edx, [rdx+0Bh]
0x14003064e  mov     r8d, 4B444342h
0x140030654  lea     r15d, ds:2Eh[rax*2]
0x14003065c  mov     ecx, 102h
0x140030661  lea     r13d, [r15+rdx*2]
0x140030665  mov     edx, r13d
0x140030668  mov     r12d, r13d
0x14003066b  call    cs:__imp_ExAllocatePool2
0x140030672  nop     dword ptr [rax+rax+00h]
0x140030677  mov     rdi, rax
0x14003067a  test    rax, rax
0x14003067d  jnz     short loc_140030686
0x14003067f  mov     ebx, 0C000009Ah
0x140030684  jmp     short loc_140030704
0x140030686  mov     r8, r12; Size
0x140030689  xor     edx, edx; Val
0x14003068b  mov     rcx, rdi; void *
0x14003068e  xor     ebx, ebx
0x140030690  call    memset
0x140030695  mov     r12d, r15d
0x140030698  mov     rdx, rbp
0x14003069b  mov     [rdi+14h], r15d
0x14003069f  xor     r15d, r15d
0x1400306a2  mov     dword ptr [rdi], 3
0x1400306a8  inc     rdx
0x1400306ab  cmp     [r14+rdx*2], r15w
0x1400306b0  jnz     short loc_1400306A8
0x1400306b2  inc     rdx; SizeInWords
0x1400306b5  lea     rcx, [rdi+18h]; Dst
0x1400306b9  mov     r8, r14; Src
0x1400306bc  call    cs:__imp_wcscpy_s
0x1400306c3  nop     dword ptr [rax+rax+00h]
0x1400306c8  mov     dword ptr [r12+rdi], 2
0x1400306d0  inc     rbp
0x1400306d3  cmp     [rsi+rbp*2], r15w
0x1400306d8  jnz     short loc_1400306D0
0x1400306da  lea     rcx, [rdi+14h]
0x1400306de  mov     r8, rsi; Src
0x1400306e1  add     rcx, r12; Dst
0x1400306e4  lea     rdx, [rbp+1]; SizeInWords
0x1400306e8  call    cs:__imp_wcscpy_s
0x1400306ef  nop     dword ptr [rax+rax+00h]
0x1400306f4  mov     rax, [rsp+58h+arg_8]
0x1400306f9  mov     [rax], rdi
0x1400306fc  mov     rax, [rsp+58h+arg_10]
0x140030701  mov     [rax], r13d
0x140030704  mov     ebp, 4B444342h
0x140030709  mov     rcx, rsi; P
0x14003070c  mov     edx, ebp; Tag
0x14003070e  call    ExFreePoolWithTag_0
0x140030713  test    ebx, ebx
0x140030715  jns     short loc_14003072D
0x140030717  test    rdi, rdi
0x14003071a  jz      short loc_14003072D
0x14003071c  mov     edx, ebp; Tag
0x14003071e  mov     rcx, rdi; P
0x140030721  call    ExFreePoolWithTag_0
0x140030726  jmp     short loc_14003072D
0x140030728  mov     ebx, 0C000000Dh
0x14003072d  mov     eax, ebx
0x14003072f  mov     rbx, [rsp+58h+arg_0]
0x140030734  add     rsp, 20h
0x140030738  pop     r15
0x14003073a  pop     r14
0x14003073c  pop     r13
0x14003073e  pop     r12
0x140030740  pop     rdi
0x140030741  pop     rsi
0x140030742  pop     rbp
0x140030743  retn
```
