# CProviderRegistrationCache::AllocateAndInitializeIssuerList(ulong,ulong,_SecPkgContext_IssuerListInfoEx * *,uchar * *)

- ea: `0x18000c068`
- end: `0x18000c0fa`
- name: `?AllocateAndInitializeIssuerList@CProviderRegistrationCache@@SAKKKPEAPEAU_SecPkgContext_IssuerListInfoEx@@PEAPEAE@Z`
- size: `146`
- prototype: `__int64 __fastcall(DWORD, int, struct _SecPkgContext_IssuerListInfoEx **, unsigned __int8 **)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180004da0`
- `0x180014c2c`

## callees

- `0x18000c068`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000c0b7`
- `ntdll!RtlAllocateHeap` at `0x18000c0b7`

## pseudocode

```c
__int64 __fastcall CProviderRegistrationCache::AllocateAndInitializeIssuerList(
        DWORD a1,
        int a2,
        struct _SecPkgContext_IssuerListInfoEx **a3,
        unsigned __int8 **a4)
{
  unsigned __int64 v4; // rbx
  unsigned int v8; // eax
  struct _SecPkgContext_IssuerListInfoEx *Heap; // rax
  unsigned int v10; // edx

  v4 = 16LL * a1;
  *a3 = 0;
  *a4 = 0;
  if ( v4 > 0xFFFFFFFF )
    return 111;
  v8 = v4 + 16;
  if ( (int)v4 + 16 < (unsigned int)v4 || v8 + a2 < v8 )
  {
    return 111;
  }
  else
  {
    Heap = (struct _SecPkgContext_IssuerListInfoEx *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v8 + a2);
    if ( Heap )
    {
      *a3 = Heap;
      Heap->aIssuers = (PCERT_NAME_BLOB)&Heap[1];
      v10 = 0;
      (*a3)->cIssuers = a1;
      *a4 = (unsigned __int8 *)&Heap[1] + (unsigned int)v4;
    }
    else
    {
      return 14;
    }
  }
  return v10;
}

```

## disassembly

```asm
0x18000c068  push    rbx
0x18000c06a  push    rbp
0x18000c06b  push    rsi
0x18000c06c  push    rdi
0x18000c06d  sub     rsp, 28h
0x18000c071  mov     ebx, ecx
0x18000c073  mov     eax, 0FFFFFFFFh
0x18000c078  shl     rbx, 4
0x18000c07c  mov     rsi, r9
0x18000c07f  mov     qword ptr [r8], 0
0x18000c086  mov     rdi, r8
0x18000c089  mov     ebp, ecx
0x18000c08b  mov     qword ptr [r9], 0
0x18000c092  cmp     rbx, rax
0x18000c095  ja      short loc_18000C0EA
0x18000c097  lea     eax, [rbx+10h]
0x18000c09a  cmp     eax, ebx
0x18000c09c  jb      short loc_18000C0EA
0x18000c09e  lea     ecx, [rax+rdx]
0x18000c0a1  cmp     ecx, eax
0x18000c0a3  jb      short loc_18000C0EA
0x18000c0a5  mov     r8d, ecx; Size
0x18000c0a8  xor     edx, edx; Flags
0x18000c0aa  mov     rcx, gs:60h
0x18000c0b3  mov     rcx, [rcx+30h]; HeapHandle
0x18000c0b7  call    cs:__imp_RtlAllocateHeap
0x18000c0bd  mov     rcx, rax
0x18000c0c0  test    rax, rax
0x18000c0c3  jnz     short loc_18000C0CA
0x18000c0c5  lea     edx, [rax+0Eh]
0x18000c0c8  jmp     short loc_18000C0EF
0x18000c0ca  add     rax, 10h
0x18000c0ce  mov     [rdi], rcx
0x18000c0d1  mov     [rcx], rax
0x18000c0d4  xor     edx, edx
0x18000c0d6  mov     rax, [rdi]
0x18000c0d9  mov     [rax+8], ebp
0x18000c0dc  mov     eax, ebx
0x18000c0de  add     rax, 10h
0x18000c0e2  add     rcx, rax
0x18000c0e5  mov     [rsi], rcx
0x18000c0e8  jmp     short loc_18000C0EF
0x18000c0ea  mov     edx, 6Fh ; 'o'
0x18000c0ef  mov     eax, edx
0x18000c0f1  add     rsp, 28h
0x18000c0f5  pop     rdi
0x18000c0f6  pop     rsi
0x18000c0f7  pop     rbp
0x18000c0f8  pop     rbx
0x18000c0f9  retn
```
