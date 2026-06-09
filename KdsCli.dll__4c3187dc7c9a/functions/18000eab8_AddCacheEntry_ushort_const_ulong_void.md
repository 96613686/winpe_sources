# AddCacheEntry(ushort const *,ulong,void *)

- ea: `0x18000eab8`
- end: `0x18000ebe6`
- name: `?AddCacheEntry@@YAJPEBGKPEAX@Z`
- size: `302`
- prototype: `__int64 __fastcall(const unsigned __int16 *Src, unsigned int, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000edb8`

## callees

- `0x18000eab8`
- `0x18000ebec`
- `0x18000ec54`
- `0x1800100d0`
- `0x180010920`
- `0x180010950`
- `0x18001a450`
- `0x18001a6ac`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x18000eae9`
- `RPCRT4!RpcBindingFree` at `0x18000eae9`

## string_xrefs

- `0x18000eb56`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyrpccommon.cxx`

## pseudocode

```c
__int64 __fastcall AddCacheEntry(const unsigned __int16 *Src, unsigned int a2, void *a3)
{
  unsigned __int64 v4; // rbp
  unsigned int v6; // esi
  struct _RPC_HANDLE_CACHE *CachedRPCHandle; // rdi
  unsigned __int64 CurrentTimeInULL; // rbx
  struct _RPC_HANDLE_CACHE **v9; // rbx
  unsigned int v10; // r9d
  size_t v11; // r15
  void *v12; // rax
  void *v13; // rbp
  __int64 v14; // rax

  v4 = a2;
  v6 = 0;
  CachedRPCHandle = FindCachedRPCHandle(Src);
  if ( CachedRPCHandle )
  {
    CurrentTimeInULL = GetCurrentTimeInULL();
    RpcBindingFree((RPC_BINDING_HANDLE *)CachedRPCHandle);
    *(_QWORD *)CachedRPCHandle = a3;
    *((_QWORD *)CachedRPCHandle + 2) = CurrentTimeInULL;
    return v6;
  }
  v9 = (struct _RPC_HANDLE_CACHE **)SIDKeyProvAlloc(0x18u);
  if ( !v9 )
  {
    v10 = 944;
LABEL_9:
    v6 = -2147024882;
    SidKeyDebugTraceError(
      0x8007000E,
      "hr",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyrpccommon.cxx",
      v10);
    if ( CachedRPCHandle )
      FreeCacheEntry(CachedRPCHandle);
    if ( v9 )
      SIDKeyProvFree(v9);
    return v6;
  }
  CachedRPCHandle = (struct _RPC_HANDLE_CACHE *)SIDKeyProvAlloc(0x18u);
  if ( !CachedRPCHandle )
  {
    v10 = 951;
    goto LABEL_9;
  }
  v11 = v4;
  v12 = SIDKeyProvAlloc(v4);
  v13 = v12;
  if ( !v12 )
  {
    v10 = 958;
    goto LABEL_9;
  }
  memcpy_0(v12, Src, v11);
  *(_QWORD *)CachedRPCHandle = a3;
  *((_QWORD *)CachedRPCHandle + 1) = v13;
  *((_QWORD *)CachedRPCHandle + 2) = GetCurrentTimeInULL();
  *v9 = CachedRPCHandle;
  v14 = qword_1800234C8;
  if ( *(__int64 **)(qword_1800234C8 + 8) != &qword_1800234C8 )
    __fastfail(3u);
  v9[1] = (struct _RPC_HANDLE_CACHE *)qword_1800234C8;
  v9[2] = (struct _RPC_HANDLE_CACHE *)&qword_1800234C8;
  *(_QWORD *)(v14 + 8) = v9 + 1;
  qword_1800234C8 = (__int64)(v9 + 1);
  return v6;
}

```

## disassembly

```asm
0x18000eab8  push    rbx
0x18000eaba  push    rbp
0x18000eabb  push    rsi
0x18000eabc  push    rdi
0x18000eabd  push    r12
0x18000eabf  push    r14
0x18000eac1  push    r15
0x18000eac3  sub     rsp, 20h
0x18000eac7  mov     r14, r8
0x18000eaca  mov     ebp, edx
0x18000eacc  mov     r12, rcx
0x18000eacf  xor     esi, esi
0x18000ead1  call    ?FindCachedRPCHandle@@YAPEAU_RPC_HANDLE_CACHE@@PEBG@Z; FindCachedRPCHandle(ushort const *)
0x18000ead6  mov     rdi, rax
0x18000ead9  test    rax, rax
0x18000eadc  jz      short loc_18000EAFB
0x18000eade  call    ?GetCurrentTimeInULL@@YA_KXZ; GetCurrentTimeInULL(void)
0x18000eae3  mov     rcx, rdi; Binding
0x18000eae6  mov     rbx, rax
0x18000eae9  call    cs:__imp_RpcBindingFree
0x18000eaef  mov     [rdi], r14
0x18000eaf2  mov     [rdi+10h], rbx
0x18000eaf6  jmp     loc_18000EBD5
0x18000eafb  mov     r15d, 18h
0x18000eb01  mov     ecx, r15d; unsigned __int64
0x18000eb04  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18000eb09  mov     rbx, rax
0x18000eb0c  test    rax, rax
0x18000eb0f  jnz     short loc_18000EB19
0x18000eb11  mov     r9d, 3B0h
0x18000eb17  jmp     short loc_18000EB4A
0x18000eb19  mov     rcx, r15; unsigned __int64
0x18000eb1c  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18000eb21  mov     rdi, rax
0x18000eb24  test    rax, rax
0x18000eb27  jnz     short loc_18000EB31
0x18000eb29  mov     r9d, 3B7h
0x18000eb2f  jmp     short loc_18000EB4A
0x18000eb31  mov     rcx, rbp; unsigned __int64
0x18000eb34  mov     r15, rbp
0x18000eb37  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18000eb3c  mov     rbp, rax
0x18000eb3f  test    rax, rax
0x18000eb42  jnz     short loc_18000EB83
0x18000eb44  mov     r9d, 3BEh; unsigned int
0x18000eb4a  mov     ecx, 8007000Eh; unsigned int
0x18000eb4f  lea     rdx, aHr; "hr"
0x18000eb56  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000eb5d  mov     esi, 8007000Eh
0x18000eb62  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000eb67  test    rdi, rdi
0x18000eb6a  jz      short loc_18000EB74
0x18000eb6c  mov     rcx, rdi; lpMem
0x18000eb6f  call    FreeCacheEntry
0x18000eb74  test    rbx, rbx
0x18000eb77  jz      short loc_18000EBD5
0x18000eb79  mov     rcx, rbx; lpMem
0x18000eb7c  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x18000eb81  jmp     short loc_18000EBD5
0x18000eb83  mov     r8, r15; Size
0x18000eb86  mov     rdx, r12; Src
0x18000eb89  mov     rcx, rbp; void *
0x18000eb8c  call    memcpy_0
0x18000eb91  mov     [rdi], r14
0x18000eb94  mov     [rdi+8], rbp
0x18000eb98  call    ?GetCurrentTimeInULL@@YA_KXZ; GetCurrentTimeInULL(void)
0x18000eb9d  mov     [rdi+10h], rax
0x18000eba1  lea     rdx, qword_1800234C8
0x18000eba8  mov     [rbx], rdi
0x18000ebab  mov     rax, cs:qword_1800234C8
0x18000ebb2  cmp     [rax+8], rdx
0x18000ebb6  jz      short loc_18000EBBF
0x18000ebb8  mov     ecx, 3
0x18000ebbd  int     29h; Win8: RtlFailFast(ecx)
0x18000ebbf  lea     rcx, [rbx+8]
0x18000ebc3  mov     [rcx], rax
0x18000ebc6  mov     [rcx+8], rdx
0x18000ebca  mov     [rax+8], rcx
0x18000ebce  mov     cs:qword_1800234C8, rcx
0x18000ebd5  mov     eax, esi
0x18000ebd7  add     rsp, 20h
0x18000ebdb  pop     r15
0x18000ebdd  pop     r14
0x18000ebdf  pop     r12
0x18000ebe1  pop     rdi
0x18000ebe2  pop     rsi
0x18000ebe3  pop     rbp
0x18000ebe4  pop     rbx
0x18000ebe5  retn
```
