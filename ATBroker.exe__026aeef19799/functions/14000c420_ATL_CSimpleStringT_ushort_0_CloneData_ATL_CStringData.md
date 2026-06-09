# ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)

- ea: `0x14000c420`
- end: `0x14000c4a5`
- name: `?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z`
- size: `133`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x14000ce48`
- `0x14000cfd0`
- `0x14000f5dc`
- `0x14000f810`
- `0x140010244`

## callees

- `0x140009e84`
- `0x14000c420`
- `0x140017010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000c48b`
- `msvcrt!memcpy_s` at `0x14000c48b`

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
0x14000c420  mov     [rsp+arg_0], rbx
0x14000c425  push    rdi
0x14000c426  sub     rsp, 20h
0x14000c42a  mov     rbx, rcx
0x14000c42d  mov     rcx, [rcx]
0x14000c430  mov     rax, [rcx]
0x14000c433  mov     rax, [rax+20h]
0x14000c437  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c43c  cmp     dword ptr [rbx+10h], 0
0x14000c440  mov     rcx, rax
0x14000c443  jl      short loc_14000C453
0x14000c445  cmp     rax, [rbx]
0x14000c448  jnz     short loc_14000C453
0x14000c44a  mov     rdi, rbx
0x14000c44d  lock inc dword ptr [rbx+10h]
0x14000c451  jmp     short loc_14000C491
0x14000c453  mov     rax, [rax]
0x14000c456  mov     r8d, 2
0x14000c45c  mov     edx, [rbx+8]
0x14000c45f  mov     rax, [rax]
0x14000c462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c467  mov     rdi, rax
0x14000c46a  test    rax, rax
0x14000c46d  jz      short loc_14000C49F
0x14000c46f  mov     eax, [rbx+8]
0x14000c472  lea     r8, [rbx+18h]; Source
0x14000c476  mov     [rdi+8], eax
0x14000c479  lea     rcx, [rdi+18h]; Destination
0x14000c47d  mov     eax, [rbx+8]
0x14000c480  inc     eax
0x14000c482  movsxd  rdx, eax
0x14000c485  add     rdx, rdx; DestinationSize
0x14000c488  mov     r9, rdx; SourceSize
0x14000c48b  call    cs:__imp_memcpy_s
0x14000c491  mov     rbx, [rsp+28h+arg_0]
0x14000c496  mov     rax, rdi
0x14000c499  add     rsp, 20h
0x14000c49d  pop     rdi
0x14000c49e  retn
0x14000c49f  call    ?ThrowMemoryException@?$CSimpleStringT@G$0A@@ATL@@KAXXZ; ATL::CSimpleStringT<ushort,0>::ThrowMemoryException(void)
```
