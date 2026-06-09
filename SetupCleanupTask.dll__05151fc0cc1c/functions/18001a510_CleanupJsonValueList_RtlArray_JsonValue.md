# CleanupJsonValueList(RtlArray<JsonValue *> * *)

- ea: `0x18001a510`
- end: `0x18001a5ae`
- name: `?CleanupJsonValueList@@YAXPEAPEAV?$RtlArray@PEAUJsonValue@@@@@Z`
- size: `158`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x18001a474`
- `0x18001ff90`
- `0x18002043c`

## callees

- `0x18001a474`
- `0x18001a510`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001a591`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001a591`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a57a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a57a`

## pseudocode

```c
void __fastcall CleanupJsonValueList(__int64 *a1)
{
  __int64 v1; // rbx
  unsigned __int64 v3; // rdi
  struct JsonValue **v4; // rax
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
          || (v4 = (struct JsonValue **)(*(_QWORD *)(v1 + 40) + *(_QWORD *)(v1 + 8) * v3),
              (unsigned __int64)v4 < *(_QWORD *)(v1 + 40)) )
        {
          v4 = 0;
        }
      }
      CleanupJsonValue(v4);
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
0x18001a510  mov     [rsp+arg_8], rbx
0x18001a515  mov     [rsp+arg_10], rsi
0x18001a51a  push    rdi
0x18001a51b  sub     rsp, 20h
0x18001a51f  mov     rbx, [rcx]
0x18001a522  mov     rsi, rcx
0x18001a525  test    rbx, rbx
0x18001a528  jz      short loc_18001A59E
0x18001a52a  cmp     qword ptr [rbx+10h], 0
0x18001a52f  jbe     short loc_18001A56C
0x18001a531  xor     edi, edi
0x18001a533  xor     eax, eax
0x18001a535  cmp     rdi, [rbx+10h]
0x18001a539  jnb     short loc_18001A553
0x18001a53b  mov     rax, rdi
0x18001a53e  mul     qword ptr [rbx+8]
0x18001a542  test    rdx, rdx
0x18001a545  jnz     short loc_18001A551
0x18001a547  add     rax, [rbx+28h]
0x18001a54b  cmp     rax, [rbx+28h]
0x18001a54f  jnb     short loc_18001A553
0x18001a551  xor     eax, eax
0x18001a553  mov     rcx, rax; struct JsonValue **
0x18001a556  call    ?CleanupJsonValue@@YAXPEAPEAUJsonValue@@@Z; CleanupJsonValue(JsonValue * *)
0x18001a55b  mov     rbx, [rsi]
0x18001a55e  inc     rdi
0x18001a561  cmp     rdi, [rbx+10h]
0x18001a565  jb      short loc_18001A533
0x18001a567  test    rbx, rbx
0x18001a56a  jz      short loc_18001A59E
0x18001a56c  mov     r8, [rbx+28h]; lpMem
0x18001a570  test    r8, r8
0x18001a573  jz      short loc_18001A580
0x18001a575  mov     rcx, [rbx]; hHeap
0x18001a578  xor     edx, edx; dwFlags
0x18001a57a  call    cs:__imp_HeapFree
0x18001a580  xorps   xmm0, xmm0
0x18001a583  mov     rcx, rbx
0x18001a586  movups  xmmword ptr [rbx], xmm0
0x18001a589  movups  xmmword ptr [rbx+10h], xmm0
0x18001a58d  movups  xmmword ptr [rbx+20h], xmm0
0x18001a591  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001a597  mov     qword ptr [rsi], 0
0x18001a59e  mov     rbx, [rsp+28h+arg_8]
0x18001a5a3  mov     rsi, [rsp+28h+arg_10]
0x18001a5a8  add     rsp, 20h
0x18001a5ac  pop     rdi
0x18001a5ad  retn
```
