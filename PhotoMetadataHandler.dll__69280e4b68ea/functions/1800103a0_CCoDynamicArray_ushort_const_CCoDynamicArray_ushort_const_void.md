# CCoDynamicArray<ushort const *>::~CCoDynamicArray<ushort const *>(void)

- ea: `0x1800103a0`
- end: `0x1800103f6`
- name: `??1?$CCoDynamicArray@PEBG@@UEAA@XZ`
- size: `86`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014640`
- `0x180021630`
- `0x180027f85`

## callees

- `0x1800103a0`
- `0x1800103fc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800103cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800103cc`

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
0x1800103a0  push    rbx
0x1800103a2  push    rbp
0x1800103a3  push    rsi
0x1800103a4  push    rdi
0x1800103a5  sub     rsp, 28h
0x1800103a9  mov     rbp, [rcx+10h]
0x1800103ad  lea     rax, ??_7?$CCoDynamicArray@PEBG@@6B@; const CCoDynamicArray<ushort const *>::`vftable'
0x1800103b4  xor     esi, esi
0x1800103b6  mov     [rcx], rax
0x1800103b9  mov     rdi, rcx
0x1800103bc  test    rbp, rbp
0x1800103bf  jz      short loc_1800103F0
0x1800103c1  lea     rbx, [rdi+8]
0x1800103c5  mov     rcx, [rbx]
0x1800103c8  mov     rcx, [rcx+rsi*8]; pv
0x1800103cc  call    cs:__imp_CoTaskMemFree
0x1800103d3  nop     dword ptr [rax+rax+00h]
0x1800103d8  inc     rsi
0x1800103db  cmp     rsi, rbp
0x1800103de  jb      short loc_1800103C1
0x1800103e0  mov     rcx, rbx
0x1800103e3  add     rsp, 28h
0x1800103e7  pop     rdi
0x1800103e8  pop     rsi
0x1800103e9  pop     rbp
0x1800103ea  pop     rbx
0x1800103eb  jmp     ??1?$CAtlArray@PEBGV?$CElementTraits@PEBG@ATL@@@ATL@@QEAA@XZ; ATL::CAtlArray<ushort const *,ATL::CElementTraits<ushort const *>>::~CAtlArray<ushort const *,ATL::CElementTraits<ushort const *>>(void)
0x1800103f0  lea     rbx, [rcx+8]
0x1800103f4  jmp     short loc_1800103E0
```
