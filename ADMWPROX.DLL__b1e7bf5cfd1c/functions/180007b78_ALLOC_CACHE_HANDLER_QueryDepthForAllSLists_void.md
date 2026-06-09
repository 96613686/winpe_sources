# ALLOC_CACHE_HANDLER::QueryDepthForAllSLists(void)

- ea: `0x180007b78`
- end: `0x180007bcb`
- name: `?QueryDepthForAllSLists@ALLOC_CACHE_HANDLER@@AEAAKXZ`
- size: `83`
- prototype: `unsigned int __fastcall(ALLOC_CACHE_HANDLER *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180007604`

## callees

- `0x180007b78`

## import_xrefs

- `KERNEL32!QueryDepthSList` at `0x180007ba4`
- `KERNEL32!QueryDepthSList` at `0x180007ba4`

## pseudocode

```c
__int64 __fastcall ALLOC_CACHE_HANDLER::QueryDepthForAllSLists(ALLOC_CACHE_HANDLER *this)
{
  _QWORD *v1; // rbx
  unsigned int v2; // edi
  unsigned int i; // esi
  USHORT DepthSList; // ax

  v1 = (_QWORD *)*((_QWORD *)this + 3);
  v2 = 0;
  if ( v1 )
  {
    for ( i = 0; (unsigned __int64)i < v1[2]; v2 += DepthSList )
      DepthSList = QueryDepthSList((PSLIST_HEADER)(*v1 + v1[1] * i++));
  }
  return v2;
}

```

## disassembly

```asm
0x180007b78  mov     [rsp+arg_8], rbx
0x180007b7d  mov     [rsp+arg_10], rsi
0x180007b82  push    rdi
0x180007b83  sub     rsp, 20h
0x180007b87  mov     rbx, [rcx+18h]
0x180007b8b  xor     edi, edi
0x180007b8d  test    rbx, rbx
0x180007b90  jz      short loc_180007BB9
0x180007b92  xor     esi, esi
0x180007b94  cmp     [rbx+10h], rsi
0x180007b98  jbe     short loc_180007BB9
0x180007b9a  mov     ecx, esi
0x180007b9c  imul    rcx, [rbx+8]
0x180007ba1  add     rcx, [rbx]; ListHead
0x180007ba4  call    cs:__imp_QueryDepthSList
0x180007baa  movzx   ecx, ax
0x180007bad  inc     esi
0x180007baf  add     edi, ecx
0x180007bb1  mov     ecx, esi
0x180007bb3  cmp     rcx, [rbx+10h]
0x180007bb7  jb      short loc_180007B9A
0x180007bb9  mov     rbx, [rsp+28h+arg_8]
0x180007bbe  mov     eax, edi
0x180007bc0  mov     rsi, [rsp+28h+arg_10]
0x180007bc5  add     rsp, 20h
0x180007bc9  pop     rdi
0x180007bca  retn
```
