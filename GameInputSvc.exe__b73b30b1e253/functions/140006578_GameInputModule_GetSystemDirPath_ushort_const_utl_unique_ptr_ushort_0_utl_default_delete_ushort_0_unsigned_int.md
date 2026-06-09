# GameInputModule::GetSystemDirPath(ushort const *,utl::unique_ptr<ushort [0],utl::default_delete<ushort [0]>> &,unsigned __int64 *)

- ea: `0x140006578`
- end: `0x1400066c7`
- name: `?GetSystemDirPath@GameInputModule@@CAJPEBGAEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@utl@@@utl@@PEA_K@Z`
- size: `335`
- prototype: `signed int __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x140006750`

## callees

- `0x140006578`
- `0x140006b48`

## import_xrefs

- `ntdll!towlower` at `0x140006635`
- `ntdll!towlower` at `0x140006662`
- `ntdll!towlower` at `0x140006635`
- `ntdll!towlower` at `0x140006662`
- `ntdll!RtlAllocateHeap` at `0x1400065fb`
- `ntdll!RtlAllocateHeap` at `0x1400065fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000669d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000669d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1400065a4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140006618`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1400065a4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140006618`

## pseudocode

```c
signed int __fastcall GameInputModule::GetSystemDirPath(__int64 a1, void **a2)
{
  void *v3; // rcx
  UINT SystemDirectoryW; // eax
  __int64 v6; // rbp
  unsigned __int64 v7; // rsi
  unsigned __int64 v8; // rdi
  SIZE_T v9; // rax
  WCHAR *Heap; // rax
  WCHAR *v11; // rbx
  signed int result; // eax
  unsigned __int64 v13; // rdi
  unsigned __int64 i; // rbp
  unsigned __int64 v15; // rbp
  void *v16; // rcx

  v3 = *a2;
  *a2 = 0;
  if ( v3 )
    operator delete[](v3);
  SystemDirectoryW = GetSystemDirectoryW(0, 0);
  v6 = SystemDirectoryW;
  if ( SystemDirectoryW )
  {
    if ( a1 )
    {
      v7 = -1;
      do
        ++v7;
      while ( *(_WORD *)(a1 + 2 * v7) );
    }
    else
    {
      v7 = 0;
    }
    v8 = v7 + SystemDirectoryW + 1LL;
    if ( !a1 )
      v8 = SystemDirectoryW;
    v9 = 2 * v8;
    if ( !is_mul_ok(v8, 2u) )
      v9 = -1;
    Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
    v11 = Heap;
    if ( !Heap )
      return -2147024882;
    v13 = GetSystemDirectoryW(Heap, v8);
    if ( v13 == v6 - 1 )
    {
      for ( i = 0; i < v13; ++i )
        v11[i] = towlower(v11[i]);
      if ( a1 )
      {
        v11[v13] = 92;
        v15 = 0;
        ++v13;
        if ( v7 )
        {
          do
            v11[v13++] = towlower(*(_WORD *)(a1 + 2 * v15++));
          while ( v15 < v7 );
        }
      }
      v11[v13] = 0;
      v16 = *a2;
      *a2 = v11;
      if ( v16 )
        operator delete[](v16);
      return 0;
    }
    operator delete[](v11);
    if ( v13 )
      return -2147418113;
  }
  result = GetLastError();
  if ( !result )
    return -2147418113;
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140006578  push    rbx
0x14000657a  push    rbp
0x14000657b  push    rsi
0x14000657c  push    rdi
0x14000657d  push    r12
0x14000657f  push    r14
0x140006581  push    r15
0x140006583  sub     rsp, 20h
0x140006587  xor     r12d, r12d
0x14000658a  mov     r14, rcx
0x14000658d  mov     rcx, [rdx]; P
0x140006590  mov     r15, rdx
0x140006593  mov     [rdx], r12
0x140006596  test    rcx, rcx
0x140006599  jz      short loc_1400065A0
0x14000659b  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1400065a0  xor     edx, edx; uSize
0x1400065a2  xor     ecx, ecx; lpBuffer
0x1400065a4  call    cs:__imp_GetSystemDirectoryW
0x1400065aa  mov     ebp, eax
0x1400065ac  test    eax, eax
0x1400065ae  jz      loc_14000669D
0x1400065b4  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400065b8  test    r14, r14
0x1400065bb  jz      short loc_1400065CC
0x1400065bd  mov     rsi, rcx
0x1400065c0  inc     rsi
0x1400065c3  cmp     [r14+rsi*2], r12w
0x1400065c8  jnz     short loc_1400065C0
0x1400065ca  jmp     short loc_1400065CF
0x1400065cc  mov     rsi, r12
0x1400065cf  lea     rdi, [rbp+1]
0x1400065d3  mov     eax, 2
0x1400065d8  add     rdi, rsi
0x1400065db  test    r14, r14
0x1400065de  cmovz   rdi, rbp
0x1400065e2  mul     rdi
0x1400065e5  cmovb   rax, rcx
0x1400065e9  mov     rcx, gs:60h
0x1400065f2  mov     r8, rax; Size
0x1400065f5  xor     edx, edx; Flags
0x1400065f7  mov     rcx, [rcx+30h]; HeapHandle
0x1400065fb  call    cs:__imp_RtlAllocateHeap
0x140006601  mov     rbx, rax
0x140006604  test    rax, rax
0x140006607  jnz     short loc_140006613
0x140006609  mov     eax, 8007000Eh
0x14000660e  jmp     loc_1400066B8
0x140006613  mov     edx, edi; uSize
0x140006615  mov     rcx, rbx; lpBuffer
0x140006618  call    cs:__imp_GetSystemDirectoryW
0x14000661e  mov     edi, eax
0x140006620  lea     rax, [rbp-1]
0x140006624  cmp     rdi, rax
0x140006627  jnz     short loc_140006690
0x140006629  mov     rbp, r12
0x14000662c  test    rdi, rdi
0x14000662f  jz      short loc_140006647
0x140006631  movzx   ecx, word ptr [rbx+rbp*2]; C
0x140006635  call    cs:__imp_towlower
0x14000663b  mov     [rbx+rbp*2], ax
0x14000663f  inc     rbp
0x140006642  cmp     rbp, rdi
0x140006645  jb      short loc_140006631
0x140006647  test    r14, r14
0x14000664a  jz      short loc_140006677
0x14000664c  mov     word ptr [rbx+rdi*2], 5Ch ; '\'
0x140006652  mov     rbp, r12
0x140006655  inc     rdi
0x140006658  test    rsi, rsi
0x14000665b  jz      short loc_140006677
0x14000665d  movzx   ecx, word ptr [r14+rbp*2]; C
0x140006662  call    cs:__imp_towlower
0x140006668  mov     [rbx+rdi*2], ax
0x14000666c  inc     rbp
0x14000666f  inc     rdi
0x140006672  cmp     rbp, rsi
0x140006675  jb      short loc_14000665D
0x140006677  mov     [rbx+rdi*2], r12w
0x14000667c  mov     rcx, [r15]; P
0x14000667f  mov     [r15], rbx
0x140006682  test    rcx, rcx
0x140006685  jz      short loc_14000668C
0x140006687  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x14000668c  xor     eax, eax
0x14000668e  jmp     short loc_1400066B8
0x140006690  mov     rcx, rbx; P
0x140006693  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x140006698  test    rdi, rdi
0x14000669b  jnz     short loc_1400066A7
0x14000669d  call    cs:__imp_GetLastError
0x1400066a3  test    eax, eax
0x1400066a5  jnz     short loc_1400066AE
0x1400066a7  mov     eax, 8000FFFFh
0x1400066ac  jmp     short loc_1400066B8
0x1400066ae  jle     short loc_1400066B8
0x1400066b0  movzx   eax, ax
0x1400066b3  or      eax, 80070000h
0x1400066b8  add     rsp, 20h
0x1400066bc  pop     r15
0x1400066be  pop     r14
0x1400066c0  pop     r12
0x1400066c2  pop     rdi
0x1400066c3  pop     rsi
0x1400066c4  pop     rbp
0x1400066c5  pop     rbx
0x1400066c6  retn
```
