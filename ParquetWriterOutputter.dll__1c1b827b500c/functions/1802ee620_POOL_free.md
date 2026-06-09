# POOL_free

- ea: `0x1802ee620`
- end: `0x1802ee6a4`
- name: `POOL_free`
- size: `132`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1802b4440`
- `0x1802ee4b0`

## callees

- `0x1802af0e0`
- `0x1802ee620`
- `0x1802ee6b0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1802ee636`
- `KERNEL32!DeleteCriticalSection` at `0x1802ee636`

## pseudocode

```c
__int64 __fastcall POOL_free(__int128 *a1)
{
  __int64 v2; // rcx
  __int64 v3; // xmm1_8
  __int64 v4; // rcx
  __int64 v5; // xmm1_8
  __int64 v6; // xmm1_8
  __int64 result; // rax
  __int128 v8; // [rsp+20h] [rbp-28h] BYREF
  __int64 v9; // [rsp+30h] [rbp-18h]

  if ( a1 )
  {
    POOL_join();
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 6));
    v2 = *((_QWORD *)a1 + 6);
    v3 = *((_QWORD *)a1 + 2);
    v8 = *a1;
    v9 = v3;
    ZSTD_free(v2, &v8);
    v4 = *((_QWORD *)a1 + 3);
    v5 = *((_QWORD *)a1 + 2);
    v8 = *a1;
    v9 = v5;
    ZSTD_free(v4, &v8);
    v6 = *((_QWORD *)a1 + 2);
    v8 = *a1;
    v9 = v6;
    return ZSTD_free(a1, &v8);
  }
  return result;
}

```

## disassembly

```asm
0x1802ee620  test    rcx, rcx
0x1802ee623  jz      short locret_1802EE6A3
0x1802ee625  push    rbx
0x1802ee626  sub     rsp, 40h
0x1802ee62a  mov     rbx, rcx
0x1802ee62d  call    POOL_join
0x1802ee632  lea     rcx, [rbx+60h]; lpCriticalSection
0x1802ee636  call    cs:__imp_DeleteCriticalSection
0x1802ee63c  movups  xmm0, xmmword ptr [rbx]
0x1802ee63f  lea     rdx, [rsp+48h+var_28]
0x1802ee644  mov     rcx, [rbx+30h]
0x1802ee648  movsd   xmm1, qword ptr [rbx+10h]
0x1802ee64d  movaps  [rsp+48h+var_28], xmm0
0x1802ee652  movsd   [rsp+48h+var_18], xmm1
0x1802ee658  call    ZSTD_free
0x1802ee65d  movups  xmm0, xmmword ptr [rbx]
0x1802ee660  lea     rdx, [rsp+48h+var_28]
0x1802ee665  mov     rcx, [rbx+18h]
0x1802ee669  movsd   xmm1, qword ptr [rbx+10h]
0x1802ee66e  movaps  [rsp+48h+var_28], xmm0
0x1802ee673  movsd   [rsp+48h+var_18], xmm1
0x1802ee679  call    ZSTD_free
0x1802ee67e  movups  xmm0, xmmword ptr [rbx]
0x1802ee681  lea     rdx, [rsp+48h+var_28]
0x1802ee686  mov     rcx, rbx
0x1802ee689  movsd   xmm1, qword ptr [rbx+10h]
0x1802ee68e  movaps  [rsp+48h+var_28], xmm0
0x1802ee693  movsd   [rsp+48h+var_18], xmm1
0x1802ee699  call    ZSTD_free
0x1802ee69e  add     rsp, 40h
0x1802ee6a2  pop     rbx
0x1802ee6a3  retn
```
