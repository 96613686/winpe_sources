# BiTranslateFilePath

- ea: `0x140024b30`
- end: `0x140024c77`
- name: `BiTranslateFilePath`
- size: `327`
- prototype: `__int64 __fastcall(__int64, unsigned int, _QWORD *)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1400228bc`
- `0x140022e8c`
- `0x140023f80`

## callees

- `0x1400133e4`
- `0x140020678`
- `0x14002166c`
- `0x140021888`
- `0x140024b30`
- `0x140027010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x140024bde`
- `ntdll!RtlAllocateHeap` at `0x140024bde`
- `ntdll!RtlFreeHeap` at `0x140024c5c`
- `ntdll!RtlFreeHeap` at `0x140024c5c`

## string_xrefs

- `0x140024b63`: `ZwTranslateFilePath`
- `0x140024c31`: `BiTranslateFilePath failed. File type: %lu. Status: %x`

## pseudocode

```c
__int64 __fastcall BiTranslateFilePath(__int64 a1, unsigned int a2, _QWORD *a3)
{
  void *v6; // rdi
  NTSTATUS v7; // ebx
  int v8; // eax
  PVOID Heap; // rax
  __int64 (__fastcall *v11)(__int64, _QWORD, PVOID, SIZE_T *); // [rsp+30h] [rbp-28h] BYREF
  _QWORD v12[4]; // [rsp+38h] [rbp-20h] BYREF
  SIZE_T Size; // [rsp+78h] [rbp+20h] BYREF

  LODWORD(Size) = 0;
  v11 = 0;
  v12[0] = 0;
  v6 = 0;
  if ( (int)BiLookupNtdllProcedureAddress("ZwTranslateFilePath", (PVOID *)&v11) < 0 )
  {
    v7 = -1073741637;
LABEL_14:
    BiLogMessage(
      4,
      L"BiTranslateFilePath failed. File type: %lu. Status: %x",
      *(unsigned int *)(a1 + 8),
      (unsigned int)v7);
    goto LABEL_15;
  }
  v7 = BiAcquirePrivilege(0x16u, (__int64)v12);
  if ( v7 >= 0 )
  {
    LODWORD(Size) = 0;
    v8 = v11(a1, a2, 0, &Size);
    v7 = v8;
    if ( v8 == -1073741789 )
    {
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)Size);
      v6 = Heap;
      v7 = Heap ? v11(a1, a2, Heap, &Size) : -1073741670;
    }
    else if ( v8 >= 0 )
    {
      v7 = -1073741811;
    }
    BiReleasePrivilege((__int64)v12);
    if ( v7 >= 0 )
    {
      *a3 = v6;
      return (unsigned int)v7;
    }
  }
  if ( v7 != -1073741811 || *(_DWORD *)(a1 + 8) != 4 )
    goto LABEL_14;
LABEL_15:
  if ( v6 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140024b30  mov     rax, rsp
0x140024b33  mov     [rax+8], rbx
0x140024b37  mov     [rax+10h], rbp
0x140024b3b  push    rsi
0x140024b3c  push    rdi
0x140024b3d  push    r14
0x140024b3f  sub     rsp, 40h
0x140024b43  mov     ebp, edx
0x140024b45  mov     dword ptr [rax+20h], 0
0x140024b4c  mov     rsi, rcx
0x140024b4f  mov     qword ptr [rax-28h], 0
0x140024b57  lea     rdx, [rax-28h]
0x140024b5b  mov     qword ptr [rax-20h], 0
0x140024b63  lea     rcx, aZwtranslatefil; "ZwTranslateFilePath"
0x140024b6a  mov     r14, r8
0x140024b6d  xor     edi, edi
0x140024b6f  call    BiLookupNtdllProcedureAddress
0x140024b74  test    eax, eax
0x140024b76  jns     short loc_140024B82
0x140024b78  mov     ebx, 0C00000BBh
0x140024b7d  jmp     loc_140024C2D
0x140024b82  lea     rdx, [rsp+58h+var_20]
0x140024b87  mov     ecx, 16h
0x140024b8c  call    BiAcquirePrivilege
0x140024b91  mov     ebx, eax
0x140024b93  test    eax, eax
0x140024b95  js      loc_140024C1F
0x140024b9b  mov     rax, [rsp+58h+var_28]
0x140024ba0  lea     r9, [rsp+58h+Size]
0x140024ba5  xor     r8d, r8d
0x140024ba8  mov     dword ptr [rsp+58h+Size], edi
0x140024bac  mov     edx, ebp
0x140024bae  mov     rcx, rsi
0x140024bb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024bb6  mov     ebx, eax
0x140024bb8  cmp     eax, 0C0000023h
0x140024bbd  jz      short loc_140024BCA
0x140024bbf  test    eax, eax
0x140024bc1  js      short loc_140024C0C
0x140024bc3  mov     ebx, 0C000000Dh
0x140024bc8  jmp     short loc_140024C0C
0x140024bca  mov     rcx, gs:60h
0x140024bd3  xor     edx, edx; Flags
0x140024bd5  mov     r8d, dword ptr [rsp+58h+Size]; Size
0x140024bda  mov     rcx, [rcx+30h]; HeapHandle
0x140024bde  call    cs:__imp_RtlAllocateHeap
0x140024be4  mov     rdi, rax
0x140024be7  test    rax, rax
0x140024bea  jnz     short loc_140024BF3
0x140024bec  mov     ebx, 0C000009Ah
0x140024bf1  jmp     short loc_140024C0C
0x140024bf3  mov     r8, rax
0x140024bf6  lea     r9, [rsp+58h+Size]
0x140024bfb  mov     rax, [rsp+58h+var_28]
0x140024c00  mov     edx, ebp
0x140024c02  mov     rcx, rsi
0x140024c05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024c0a  mov     ebx, eax
0x140024c0c  lea     rcx, [rsp+58h+var_20]
0x140024c11  call    BiReleasePrivilege
0x140024c16  test    ebx, ebx
0x140024c18  js      short loc_140024C1F
0x140024c1a  mov     [r14], rdi
0x140024c1d  jmp     short loc_140024C62
0x140024c1f  cmp     ebx, 0C000000Dh
0x140024c25  jnz     short loc_140024C2D
0x140024c27  cmp     dword ptr [rsi+8], 4
0x140024c2b  jz      short loc_140024C45
0x140024c2d  mov     r8d, [rsi+8]
0x140024c31  lea     rdx, aBitranslatefil; "BiTranslateFilePath failed. File type: "...
0x140024c38  mov     r9d, ebx
0x140024c3b  mov     ecx, 4
0x140024c40  call    BiLogMessage
0x140024c45  test    rdi, rdi
0x140024c48  jz      short loc_140024C62
0x140024c4a  mov     rcx, gs:60h
0x140024c53  mov     r8, rdi; P
0x140024c56  xor     edx, edx; Flags
0x140024c58  mov     rcx, [rcx+30h]; HeapHandle
0x140024c5c  call    cs:__imp_RtlFreeHeap
0x140024c62  mov     rbp, [rsp+58h+arg_8]
0x140024c67  mov     eax, ebx
0x140024c69  mov     rbx, [rsp+58h+arg_0]
0x140024c6e  add     rsp, 40h
0x140024c72  pop     r14
0x140024c74  pop     rdi
0x140024c75  pop     rsi
0x140024c76  retn
```
