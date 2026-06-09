# ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)

- ea: `0x18000acf0`
- end: `0x18000ad75`
- name: `?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z`
- size: `133`
- prototype: `volatile signed __int32 *__fastcall(volatile signed __int32 *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a324`
- `0x18000aa30`
- `0x18000aab8`
- `0x18000bacc`

## callees

- `0x18000acf0`
- `0x18000bf30`
- `0x18000e010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000ad5b`
- `msvcrt!memcpy_s` at `0x18000ad5b`

## pseudocode

```c
volatile signed __int32 *__fastcall ATL::CSimpleStringT<unsigned short,0>::CloneData(volatile signed __int32 *a1)
{
  __int64 (__fastcall ***v2)(_QWORD, _QWORD, __int64); // rax
  volatile signed __int32 *v3; // rdi
  __int64 v4; // rax
  rsize_t v5; // r9

  v2 = (__int64 (__fastcall ***)(_QWORD, _QWORD, __int64))(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)a1 + 32LL))(*(_QWORD *)a1);
  if ( *((int *)a1 + 4) >= 0 && v2 == *(__int64 (__fastcall ****)(_QWORD, _QWORD, __int64))a1 )
  {
    v3 = a1;
    _InterlockedIncrement(a1 + 4);
  }
  else
  {
    v4 = (**v2)(v2, *((unsigned int *)a1 + 2), 2);
    v3 = (volatile signed __int32 *)v4;
    if ( !v4 )
      ATL::CSimpleStringT<unsigned short,0>::ThrowMemoryException();
    *(_DWORD *)(v4 + 8) = *((_DWORD *)a1 + 2);
    v5 = 2LL * (*((_DWORD *)a1 + 2) + 1);
    memcpy_s((void *const)(v4 + 24), v5, (const void *const)(a1 + 6), v5);
  }
  return v3;
}

```

## disassembly

```asm
0x18000acf0  mov     [rsp+arg_0], rbx
0x18000acf5  push    rdi
0x18000acf6  sub     rsp, 20h
0x18000acfa  mov     rbx, rcx
0x18000acfd  mov     rcx, [rcx]
0x18000ad00  mov     rax, [rcx]
0x18000ad03  mov     rax, [rax+20h]
0x18000ad07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad0c  cmp     dword ptr [rbx+10h], 0
0x18000ad10  mov     rcx, rax
0x18000ad13  jl      short loc_18000AD23
0x18000ad15  cmp     rax, [rbx]
0x18000ad18  jnz     short loc_18000AD23
0x18000ad1a  mov     rdi, rbx
0x18000ad1d  lock inc dword ptr [rbx+10h]
0x18000ad21  jmp     short loc_18000AD61
0x18000ad23  mov     rax, [rax]
0x18000ad26  mov     r8d, 2
0x18000ad2c  mov     edx, [rbx+8]
0x18000ad2f  mov     rax, [rax]
0x18000ad32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad37  mov     rdi, rax
0x18000ad3a  test    rax, rax
0x18000ad3d  jz      short loc_18000AD6F
0x18000ad3f  mov     eax, [rbx+8]
0x18000ad42  lea     r8, [rbx+18h]; Source
0x18000ad46  mov     [rdi+8], eax
0x18000ad49  lea     rcx, [rdi+18h]; Destination
0x18000ad4d  mov     eax, [rbx+8]
0x18000ad50  inc     eax
0x18000ad52  movsxd  rdx, eax
0x18000ad55  add     rdx, rdx; DestinationSize
0x18000ad58  mov     r9, rdx; SourceSize
0x18000ad5b  call    cs:__imp_memcpy_s
0x18000ad61  mov     rbx, [rsp+28h+arg_0]
0x18000ad66  mov     rax, rdi
0x18000ad69  add     rsp, 20h
0x18000ad6d  pop     rdi
0x18000ad6e  retn
0x18000ad6f  call    ?ThrowMemoryException@?$CSimpleStringT@G$0A@@ATL@@KAXXZ; ATL::CSimpleStringT<ushort,0>::ThrowMemoryException(void)
```
