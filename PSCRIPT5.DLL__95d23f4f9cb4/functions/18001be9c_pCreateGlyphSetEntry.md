# pCreateGlyphSetEntry

- ea: `0x18001be9c`
- end: `0x18001bfa5`
- name: `pCreateGlyphSetEntry`
- size: `265`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001b83c`
- `0x18001bc58`

## callees

- `0x18001be9c`
- `0x18001c180`
- `0x18005c434`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18001bf24`
- `KERNEL32!LocalFree` at `0x18001bf24`
- `KERNEL32!LocalAlloc` at `0x18001bee5`
- `KERNEL32!LocalAlloc` at `0x18001bee5`

## pseudocode

```c
char __fastcall pCreateGlyphSetEntry(__int64 a1, int a2, int *a3, const void **a4)
{
  int v8; // edi
  __int64 v9; // r14
  _DWORD *v10; // rax
  _DWORD *v11; // r15
  char result; // al
  int v13; // edx
  int v14; // ecx
  int v15; // r8d
  int i; // eax
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // rax

  v8 = 48 * *a3;
  if ( *(_DWORD *)(a1 + 36) )
    v9 = a1 + *(unsigned int *)(a1 + 36);
  else
    v9 = 0;
  v10 = LocalAlloc(0x40u, v8 + 48 * *(_DWORD *)(a1 + 32));
  v11 = v10;
  if ( v10 )
  {
    if ( v8 > 0 )
    {
      memcpy_0(v10, *a4, v8);
      if ( *a4 )
        LocalFree((HLOCAL)*a4);
    }
    v13 = *a3;
    v14 = *a3;
    v15 = *(_DWORD *)(a1 + 32);
    for ( i = v15 + *a3; v13 < i; i = *a3 + v15 )
    {
      v17 = 32LL * (v13 - v14);
      v18 = 6LL * v13;
      v11[2 * v18] = *(_DWORD *)(v17 + v9 + 4);
      v11[2 * v18 + 1] = *(_DWORD *)(v17 + v9 + 12);
      v11[2 * v18 + 4] = a2;
      if ( *(_DWORD *)(v17 + v9) )
        v19 = a1 + *(unsigned int *)(v17 + v9);
      else
        v19 = 0;
      *(_QWORD *)&v11[12 * v13++ + 2] = v19;
      v15 = *(_DWORD *)(a1 + 32);
      v14 = *a3;
    }
    result = 1;
    *a3 = v15 + v14;
    *a4 = v11;
  }
  else
  {
    vFreeDataEntry((HLOCAL)*a4);
    *a4 = 0;
    result = 0;
    *a3 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001be9c  push    rbx
0x18001be9e  push    rbp
0x18001be9f  push    rsi
0x18001bea0  push    rdi
0x18001bea1  push    r12
0x18001bea3  push    r14
0x18001bea5  push    r15
0x18001bea7  sub     rsp, 20h
0x18001beab  mov     eax, [r8]
0x18001beae  mov     rsi, r9
0x18001beb1  mov     rbx, r8
0x18001beb4  mov     r12d, edx
0x18001beb7  mov     rbp, rcx
0x18001beba  lea     edi, [rax+rax*2]
0x18001bebd  shl     edi, 4
0x18001bec0  cmp     dword ptr [rcx+24h], 0
0x18001bec4  jz      short loc_18001BECF
0x18001bec6  mov     r14d, [rcx+24h]
0x18001beca  add     r14, rcx
0x18001becd  jmp     short loc_18001BED2
0x18001becf  xor     r14d, r14d
0x18001bed2  mov     eax, [rcx+20h]
0x18001bed5  lea     ecx, [rax+rax*2]
0x18001bed8  shl     ecx, 4
0x18001bedb  add     ecx, edi
0x18001bedd  movsxd  rdx, ecx; uBytes
0x18001bee0  mov     ecx, 40h ; '@'; uFlags
0x18001bee5  call    cs:__imp_LocalAlloc
0x18001beeb  mov     r15, rax
0x18001beee  test    rax, rax
0x18001bef1  jnz     short loc_18001BF0A
0x18001bef3  mov     edx, [rbx]
0x18001bef5  mov     rcx, [rsi]; hMem
0x18001bef8  call    vFreeDataEntry
0x18001befd  mov     [rsi], r15
0x18001bf00  xor     al, al
0x18001bf02  mov     [rbx], r15d
0x18001bf05  jmp     loc_18001BF96
0x18001bf0a  test    edi, edi
0x18001bf0c  jle     short loc_18001BF2A
0x18001bf0e  mov     rdx, [rsi]; Src
0x18001bf11  mov     rcx, r15; void *
0x18001bf14  movsxd  r8, edi; Size
0x18001bf17  call    memcpy_0
0x18001bf1c  mov     rcx, [rsi]; hMem
0x18001bf1f  test    rcx, rcx
0x18001bf22  jz      short loc_18001BF2A
0x18001bf24  call    cs:__imp_LocalFree
0x18001bf2a  mov     edx, [rbx]
0x18001bf2c  mov     ecx, edx
0x18001bf2e  mov     r8d, [rbp+20h]
0x18001bf32  lea     eax, [r8+rdx]
0x18001bf36  cmp     edx, eax
0x18001bf38  jge     short loc_18001BF8C
0x18001bf3a  mov     eax, edx
0x18001bf3c  sub     eax, ecx
0x18001bf3e  movsxd  rcx, eax
0x18001bf41  shl     rcx, 5
0x18001bf45  movsxd  rax, edx
0x18001bf48  lea     r8, [rax+rax*2]
0x18001bf4c  mov     eax, [rcx+r14+4]
0x18001bf51  add     r8, r8
0x18001bf54  mov     [r15+r8*8], eax
0x18001bf58  mov     eax, [rcx+r14+0Ch]
0x18001bf5d  mov     [r15+r8*8+4], eax
0x18001bf62  mov     [r15+r8*8+10h], r12d
0x18001bf67  cmp     dword ptr [rcx+r14], 0
0x18001bf6c  jz      short loc_18001BF77
0x18001bf6e  mov     eax, [rcx+r14]
0x18001bf72  add     rax, rbp
0x18001bf75  jmp     short loc_18001BF79
0x18001bf77  xor     eax, eax
0x18001bf79  mov     [r15+r8*8+8], rax
0x18001bf7e  inc     edx
0x18001bf80  mov     r8d, [rbp+20h]
0x18001bf84  mov     ecx, [rbx]
0x18001bf86  lea     eax, [rcx+r8]
0x18001bf8a  jmp     short loc_18001BF36
0x18001bf8c  add     ecx, r8d
0x18001bf8f  mov     al, 1
0x18001bf91  mov     [rbx], ecx
0x18001bf93  mov     [rsi], r15
0x18001bf96  add     rsp, 20h
0x18001bf9a  pop     r15
0x18001bf9c  pop     r14
0x18001bf9e  pop     r12
0x18001bfa0  pop     rdi
0x18001bfa1  pop     rsi
0x18001bfa2  pop     rbp
0x18001bfa3  pop     rbx
0x18001bfa4  retn
```
