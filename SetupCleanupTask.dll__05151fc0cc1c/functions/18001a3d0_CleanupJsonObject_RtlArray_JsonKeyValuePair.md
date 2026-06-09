# CleanupJsonObject(RtlArray<JsonKeyValuePair *> * *)

- ea: `0x18001a3d0`
- end: `0x18001a46e`
- name: `?CleanupJsonObject@@YAXPEAPEAV?$RtlArray@PEAUJsonKeyValuePair@@@@@Z`
- size: `158`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x18001a474`
- `0x18001ec50`
- `0x18001faec`
- `0x18001ff90`

## callees

- `0x18001a354`
- `0x18001a3d0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001a451`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001a451`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a43a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a43a`

## pseudocode

```c
void __fastcall CleanupJsonObject(__int64 *a1)
{
  __int64 v1; // rbx
  unsigned __int64 v3; // rdi
  void ***v4; // rax
  void *v5; // r8

  v1 = *a1;
  if ( *a1 )
  {
    if ( !*(_QWORD *)(v1 + 16) )
      goto LABEL_10;
    v3 = 0;
    do
    {
      v4 = 0;
      if ( v3 < *(_QWORD *)(v1 + 16) )
      {
        if ( !is_mul_ok(*(_QWORD *)(v1 + 8), v3)
          || (v4 = (void ***)(*(_QWORD *)(v1 + 40) + *(_QWORD *)(v1 + 8) * v3),
              (unsigned __int64)v4 < *(_QWORD *)(v1 + 40)) )
        {
          v4 = 0;
        }
      }
      CleanupJsonKeyValuePair(v4);
      v1 = *a1;
      ++v3;
    }
    while ( v3 < *(_QWORD *)(*a1 + 16) );
    if ( v1 )
    {
LABEL_10:
      v5 = *(void **)(v1 + 40);
      if ( v5 )
        HeapFree(*(HANDLE *)v1, 0, v5);
      *(_OWORD *)v1 = 0;
      *(_OWORD *)(v1 + 16) = 0;
      *(_OWORD *)(v1 + 32) = 0;
      operator delete((void *)v1);
      *a1 = 0;
    }
  }
}

```

## disassembly

```asm
0x18001a3d0  mov     [rsp+arg_8], rbx
0x18001a3d5  mov     [rsp+arg_10], rsi
0x18001a3da  push    rdi
0x18001a3db  sub     rsp, 20h
0x18001a3df  mov     rbx, [rcx]
0x18001a3e2  mov     rsi, rcx
0x18001a3e5  test    rbx, rbx
0x18001a3e8  jz      short loc_18001A45E
0x18001a3ea  cmp     qword ptr [rbx+10h], 0
0x18001a3ef  jbe     short loc_18001A42C
0x18001a3f1  xor     edi, edi
0x18001a3f3  xor     eax, eax
0x18001a3f5  cmp     rdi, [rbx+10h]
0x18001a3f9  jnb     short loc_18001A413
0x18001a3fb  mov     rax, rdi
0x18001a3fe  mul     qword ptr [rbx+8]
0x18001a402  test    rdx, rdx
0x18001a405  jnz     short loc_18001A411
0x18001a407  add     rax, [rbx+28h]
0x18001a40b  cmp     rax, [rbx+28h]
0x18001a40f  jnb     short loc_18001A413
0x18001a411  xor     eax, eax
0x18001a413  mov     rcx, rax; struct JsonKeyValuePair **
0x18001a416  call    ?CleanupJsonKeyValuePair@@YAXPEAPEAUJsonKeyValuePair@@@Z; CleanupJsonKeyValuePair(JsonKeyValuePair * *)
0x18001a41b  mov     rbx, [rsi]
0x18001a41e  inc     rdi
0x18001a421  cmp     rdi, [rbx+10h]
0x18001a425  jb      short loc_18001A3F3
0x18001a427  test    rbx, rbx
0x18001a42a  jz      short loc_18001A45E
0x18001a42c  mov     r8, [rbx+28h]; lpMem
0x18001a430  test    r8, r8
0x18001a433  jz      short loc_18001A440
0x18001a435  mov     rcx, [rbx]; hHeap
0x18001a438  xor     edx, edx; dwFlags
0x18001a43a  call    cs:__imp_HeapFree
0x18001a440  xorps   xmm0, xmm0
0x18001a443  mov     rcx, rbx
0x18001a446  movups  xmmword ptr [rbx], xmm0
0x18001a449  movups  xmmword ptr [rbx+10h], xmm0
0x18001a44d  movups  xmmword ptr [rbx+20h], xmm0
0x18001a451  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001a457  mov     qword ptr [rsi], 0
0x18001a45e  mov     rbx, [rsp+28h+arg_8]
0x18001a463  mov     rsi, [rsp+28h+arg_10]
0x18001a468  add     rsp, 20h
0x18001a46c  pop     rdi
0x18001a46d  retn
```
