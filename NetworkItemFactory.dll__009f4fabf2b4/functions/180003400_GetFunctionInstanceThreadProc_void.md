# GetFunctionInstanceThreadProc(void *)

- ea: `0x180003400`
- end: `0x180003462`
- name: `?GetFunctionInstanceThreadProc@@YAKPEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003400`
- `0x180005d3c`
- `0x18000b010`

## import_xrefs

- `ole32!CoMarshalInterThreadInterfaceInStream` at `0x180003439`
- `ole32!CoMarshalInterThreadInterfaceInStream` at `0x180003439`

## pseudocode

```c
__int64 __fastcall GetFunctionInstanceThreadProc(PVOID Parameter)
{
  HRESULT FunctionInstanceByID; // edi
  LPUNKNOWN pUnk; // [rsp+30h] [rbp+8h] BYREF

  pUnk = 0;
  FunctionInstanceByID = GetFunctionInstanceByID(
                           *(const unsigned __int16 **)Parameter,
                           (struct IFunctionInstance **)&pUnk);
  if ( FunctionInstanceByID >= 0 )
  {
    FunctionInstanceByID = CoMarshalInterThreadInterfaceInStream(
                             &IID_IFunctionInstance,
                             pUnk,
                             (LPSTREAM *)Parameter + 2);
    ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
  }
  *((_DWORD *)Parameter + 2) = FunctionInstanceByID;
  return 0;
}

```

## disassembly

```asm
0x180003400  mov     [rsp+arg_8], rbx
0x180003405  push    rdi
0x180003406  sub     rsp, 20h
0x18000340a  mov     rbx, rcx
0x18000340d  mov     [rsp+28h+pUnk], 0
0x180003416  mov     rcx, [rcx]; unsigned __int16 *
0x180003419  lea     rdx, [rsp+28h+pUnk]; struct IFunctionInstance **
0x18000341e  call    ?GetFunctionInstanceByID@@YAJPEBGPEAPEAUIFunctionInstance@@@Z; GetFunctionInstanceByID(ushort const *,IFunctionInstance * *)
0x180003423  mov     edi, eax
0x180003425  test    eax, eax
0x180003427  js      short loc_180003452
0x180003429  mov     rdx, [rsp+28h+pUnk]; pUnk
0x18000342e  lea     r8, [rbx+10h]; ppStm
0x180003432  lea     rcx, IID_IFunctionInstance; riid
0x180003439  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x18000343f  mov     rcx, [rsp+28h+pUnk]
0x180003444  mov     edi, eax
0x180003446  mov     rax, [rcx]
0x180003449  mov     rax, [rax+10h]
0x18000344d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003452  mov     [rbx+8], edi
0x180003455  xor     eax, eax
0x180003457  mov     rbx, [rsp+28h+arg_8]
0x18000345c  add     rsp, 20h
0x180003460  pop     rdi
0x180003461  retn
```
