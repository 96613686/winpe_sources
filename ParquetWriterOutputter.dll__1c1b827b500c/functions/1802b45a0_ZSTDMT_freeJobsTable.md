# ZSTDMT_freeJobsTable

- ea: `0x1802b45a0`
- end: `0x1802b461c`
- name: `ZSTDMT_freeJobsTable`
- size: `124`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1802b4080`
- `0x1802b4440`

## callees

- `0x1802af0e0`
- `0x1802b45a0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1802b45d3`
- `KERNEL32!DeleteCriticalSection` at `0x1802b45d3`

## pseudocode

```c
__int64 __fastcall ZSTDMT_freeJobsTable(__int64 a1, unsigned int a2, __int128 *a3)
{
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  __int64 v6; // rdi
  __int64 v7; // xmm1_8
  __int64 result; // rax
  __int128 v9; // [rsp+20h] [rbp-28h] BYREF
  __int64 v10; // [rsp+30h] [rbp-18h]

  if ( a1 )
  {
    if ( a2 )
    {
      v5 = (struct _RTL_CRITICAL_SECTION *)(a1 + 16);
      v6 = a2;
      do
      {
        DeleteCriticalSection(v5);
        v5 = (struct _RTL_CRITICAL_SECTION *)((char *)v5 + 336);
        --v6;
      }
      while ( v6 );
    }
    v7 = *((_QWORD *)a3 + 2);
    v9 = *a3;
    v10 = v7;
    return ZSTD_free(a1, &v9);
  }
  return result;
}

```

## disassembly

```asm
0x1802b45a0  test    rcx, rcx
0x1802b45a3  jz      short locret_1802B461B
0x1802b45a5  mov     [rsp+arg_10], rbp
0x1802b45aa  push    rsi
0x1802b45ab  sub     rsp, 40h
0x1802b45af  mov     rbp, r8
0x1802b45b2  mov     rsi, rcx
0x1802b45b5  test    edx, edx
0x1802b45b7  jz      short loc_1802B45F0
0x1802b45b9  mov     [rsp+48h+arg_0], rbx
0x1802b45be  lea     rbx, [rcx+10h]
0x1802b45c2  mov     [rsp+48h+arg_8], rdi
0x1802b45c7  mov     edi, edx
0x1802b45c9  nop     dword ptr [rax+00000000h]
0x1802b45d0  mov     rcx, rbx; lpCriticalSection
0x1802b45d3  call    cs:__imp_DeleteCriticalSection
0x1802b45d9  add     rbx, 150h
0x1802b45e0  sub     rdi, 1
0x1802b45e4  jnz     short loc_1802B45D0
0x1802b45e6  mov     rdi, [rsp+48h+arg_8]
0x1802b45eb  mov     rbx, [rsp+48h+arg_0]
0x1802b45f0  movups  xmm0, xmmword ptr [rbp+0]
0x1802b45f4  lea     rdx, [rsp+48h+var_28]
0x1802b45f9  mov     rcx, rsi
0x1802b45fc  movsd   xmm1, qword ptr [rbp+10h]
0x1802b4601  movaps  [rsp+48h+var_28], xmm0
0x1802b4606  movsd   [rsp+48h+var_18], xmm1
0x1802b460c  call    ZSTD_free
0x1802b4611  mov     rbp, [rsp+48h+arg_10]
0x1802b4616  add     rsp, 40h
0x1802b461a  pop     rsi
0x1802b461b  retn
```
