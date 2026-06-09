# CCoDynamicArray<ushort const *>::~CCoDynamicArray<ushort const *>(void)

- ea: `0x18000fc0c`
- end: `0x18000fc5c`
- name: `??1?$CCoDynamicArray@PEBG@@UEAA@XZ`
- size: `80`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180013c88`
- `0x1800205e0`
- `0x180026cd4`

## callees

- `0x18000fc0c`
- `0x18000fc64`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fc38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fc38`

## pseudocode

```c
__int64 __fastcall CCoDynamicArray<unsigned short const *>::~CCoDynamicArray<unsigned short const *>(_QWORD *a1)
{
  unsigned __int64 v1; // rbp
  unsigned __int64 v2; // rsi

  v1 = a1[2];
  v2 = 0;
  *a1 = &CCoDynamicArray<unsigned short const *>::`vftable';
  if ( !v1 )
    return ATL::CAtlArray<unsigned short const *,ATL::CElementTraits<unsigned short const *>>::~CAtlArray<unsigned short const *,ATL::CElementTraits<unsigned short const *>>(a1 + 1);
  do
    CoTaskMemFree(*(LPVOID *)(a1[1] + 8 * v2++));
  while ( v2 < v1 );
  return ATL::CAtlArray<unsigned short const *,ATL::CElementTraits<unsigned short const *>>::~CAtlArray<unsigned short const *,ATL::CElementTraits<unsigned short const *>>(a1 + 1);
}

```

## disassembly

```asm
0x18000fc0c  push    rbx
0x18000fc0e  push    rbp
0x18000fc0f  push    rsi
0x18000fc10  push    rdi
0x18000fc11  sub     rsp, 28h
0x18000fc15  mov     rbp, [rcx+10h]
0x18000fc19  lea     rax, ??_7?$CCoDynamicArray@PEBG@@6B@; const CCoDynamicArray<ushort const *>::`vftable'
0x18000fc20  xor     esi, esi
0x18000fc22  mov     [rcx], rax
0x18000fc25  mov     rdi, rcx
0x18000fc28  test    rbp, rbp
0x18000fc2b  jz      short loc_18000FC56
0x18000fc2d  lea     rbx, [rdi+8]
0x18000fc31  mov     rcx, [rbx]
0x18000fc34  mov     rcx, [rcx+rsi*8]; pv
0x18000fc38  call    cs:__imp_CoTaskMemFree
0x18000fc3e  inc     rsi
0x18000fc41  cmp     rsi, rbp
0x18000fc44  jb      short loc_18000FC2D
0x18000fc46  mov     rcx, rbx
0x18000fc49  add     rsp, 28h
0x18000fc4d  pop     rdi
0x18000fc4e  pop     rsi
0x18000fc4f  pop     rbp
0x18000fc50  pop     rbx
0x18000fc51  jmp     ??1?$CAtlArray@PEBGV?$CElementTraits@PEBG@ATL@@@ATL@@QEAA@XZ; ATL::CAtlArray<ushort const *,ATL::CElementTraits<ushort const *>>::~CAtlArray<ushort const *,ATL::CElementTraits<ushort const *>>(void)
0x18000fc56  lea     rbx, [rcx+8]
0x18000fc5a  jmp     short loc_18000FC46
```
