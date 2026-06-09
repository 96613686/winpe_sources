# CFDNotification::QueryInterface(_GUID const &,void * *)

- ea: `0x1800060c0`
- end: `0x18000613c`
- name: `?QueryInterface@CFDNotification@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `124`
- prototype: `__int64 __fastcall(LPUNKNOWN punkOuter, IID *riid, void **ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800060c0`
- `0x18000b010`

## import_xrefs

- `ole32!CoCreateFreeThreadedMarshaler` at `0x180006115`
- `ole32!CoCreateFreeThreadedMarshaler` at `0x180006115`
- `SHLWAPI!__imp_QISearch` at `0x1800060df`
- `SHLWAPI!__imp_QISearch` at `0x1800060df`

## pseudocode

```c
HRESULT __fastcall CFDNotification::QueryInterface(LPUNKNOWN punkOuter, IID *riid, void **ppv)
{
  HRESULT result; // eax

  result = QISearch(punkOuter, &`CFDNotification::QueryInterface'::`2'::qit, riid, ppv);
  if ( result == -2147467262
    && *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IMarshal.Data1
    && *(_QWORD *)riid->Data4 == *(_QWORD *)IID_IMarshal.Data4 )
  {
    if ( punkOuter[4].lpVtbl )
      return (*(__int64 (__fastcall **)(struct IUnknownVtbl *, IID *, void **))punkOuter[4].lpVtbl->QueryInterface)(
               punkOuter[4].lpVtbl,
               riid,
               ppv);
    result = CoCreateFreeThreadedMarshaler(punkOuter, (LPUNKNOWN *)&punkOuter[4]);
    if ( result >= 0 )
      return (*(__int64 (__fastcall **)(struct IUnknownVtbl *, IID *, void **))punkOuter[4].lpVtbl->QueryInterface)(
               punkOuter[4].lpVtbl,
               riid,
               ppv);
  }
  return result;
}

```

## disassembly

```asm
0x1800060c0  push    rbx
0x1800060c2  push    rbp
0x1800060c3  push    rsi
0x1800060c4  push    rdi
0x1800060c5  sub     rsp, 28h
0x1800060c9  mov     rbp, r8
0x1800060cc  mov     r9, r8; ppv
0x1800060cf  mov     r8, rdx; riid
0x1800060d2  mov     rdi, rdx
0x1800060d5  lea     rdx, ?qit@?1??QueryInterface@CFDNotification@@UEAAJAEBU_GUID@@PEAPEAX@Z@4QBUQITAB@@B; pqit
0x1800060dc  mov     rsi, rcx
0x1800060df  call    cs:__imp_QISearch
0x1800060e5  cmp     eax, 80004002h
0x1800060ea  jnz     short loc_180006133
0x1800060ec  mov     r9, [rdi]
0x1800060ef  cmp     r9, qword ptr cs:IID_IMarshal.Data1
0x1800060f6  jnz     short loc_180006133
0x1800060f8  mov     rcx, [rdi+8]
0x1800060fc  cmp     rcx, qword ptr cs:IID_IMarshal.Data4
0x180006103  jnz     short loc_180006133
0x180006105  lea     rbx, [rsi+20h]
0x180006109  cmp     qword ptr [rbx], 0
0x18000610d  jnz     short loc_18000611F
0x18000610f  mov     rdx, rbx; ppunkMarshal
0x180006112  mov     rcx, rsi; punkOuter
0x180006115  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18000611b  test    eax, eax
0x18000611d  js      short loc_180006133
0x18000611f  mov     rcx, [rbx]
0x180006122  mov     r8, rbp
0x180006125  mov     rdx, rdi
0x180006128  mov     rax, [rcx]
0x18000612b  mov     rax, [rax]
0x18000612e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006133  add     rsp, 28h
0x180006137  pop     rdi
0x180006138  pop     rsi
0x180006139  pop     rbp
0x18000613a  pop     rbx
0x18000613b  retn
```
