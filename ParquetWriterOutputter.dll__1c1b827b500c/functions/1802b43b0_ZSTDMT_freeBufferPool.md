# ZSTDMT_freeBufferPool

- ea: `0x1802b43b0`
- end: `0x1802b4437`
- name: `ZSTDMT_freeBufferPool`
- size: `135`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1802b3f70`
- `0x1802b4440`
- `0x1802b4620`

## callees

- `0x1802af0e0`
- `0x1802b43b0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1802b4405`
- `KERNEL32!DeleteCriticalSection` at `0x1802b4405`

## pseudocode

```c
__int64 __fastcall ZSTDMT_freeBufferPool(LPCRITICAL_SECTION lpCriticalSection)
{
  unsigned int i; // edi
  ULONG_PTR SpinCount; // xmm1_8
  ULONG_PTR v4; // xmm1_8
  __int64 result; // rax
  __int128 v6; // [rsp+20h] [rbp-28h] BYREF
  ULONG_PTR v7; // [rsp+30h] [rbp-18h]

  if ( lpCriticalSection )
  {
    for ( i = 0; i < lpCriticalSection[1].LockCount; ++i )
    {
      SpinCount = lpCriticalSection[1].SpinCount;
      v6 = *(_OWORD *)&lpCriticalSection[1].OwningThread;
      v7 = SpinCount;
      ZSTD_free(*((_QWORD *)&lpCriticalSection[2].DebugInfo + 2 * i), &v6);
    }
    DeleteCriticalSection(lpCriticalSection);
    v4 = lpCriticalSection[1].SpinCount;
    v6 = *(_OWORD *)&lpCriticalSection[1].OwningThread;
    v7 = v4;
    return ZSTD_free(lpCriticalSection, &v6);
  }
  return result;
}

```

## disassembly

```asm
0x1802b43b0  test    rcx, rcx
0x1802b43b3  jz      locret_1802B4436
0x1802b43b9  push    rbx
0x1802b43ba  sub     rsp, 40h
0x1802b43be  mov     [rsp+48h+arg_0], rdi
0x1802b43c3  mov     rbx, rcx
0x1802b43c6  xor     edi, edi
0x1802b43c8  cmp     [rcx+30h], edi
0x1802b43cb  jbe     short loc_1802B4402
0x1802b43cd  nop     dword ptr [rax]
0x1802b43d0  movups  xmm0, xmmword ptr [rbx+38h]
0x1802b43d4  lea     rdx, [rsp+48h+var_28]
0x1802b43d9  mov     ecx, edi
0x1802b43db  movsd   xmm1, qword ptr [rbx+48h]
0x1802b43e0  add     rcx, 5
0x1802b43e4  add     rcx, rcx
0x1802b43e7  movaps  [rsp+48h+var_28], xmm0
0x1802b43ec  movsd   [rsp+48h+var_18], xmm1
0x1802b43f2  mov     rcx, [rbx+rcx*8]
0x1802b43f6  call    ZSTD_free
0x1802b43fb  inc     edi
0x1802b43fd  cmp     edi, [rbx+30h]
0x1802b4400  jb      short loc_1802B43D0
0x1802b4402  mov     rcx, rbx; lpCriticalSection
0x1802b4405  call    cs:__imp_DeleteCriticalSection
0x1802b440b  movups  xmm0, xmmword ptr [rbx+38h]
0x1802b440f  lea     rdx, [rsp+48h+var_28]
0x1802b4414  mov     rcx, rbx
0x1802b4417  movsd   xmm1, qword ptr [rbx+48h]
0x1802b441c  movaps  [rsp+48h+var_28], xmm0
0x1802b4421  movsd   [rsp+48h+var_18], xmm1
0x1802b4427  call    ZSTD_free
0x1802b442c  mov     rdi, [rsp+48h+arg_0]
0x1802b4431  add     rsp, 40h
0x1802b4435  pop     rbx
0x1802b4436  retn
```
