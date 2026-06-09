# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x180026e10`
- end: `0x180026eab`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `155`
- prototype: `__int64 __fastcall(Microsoft::WRL::FtmBase *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800264a8`
- `0x180026d78`

## callees

- `0x180026e10`
- `0x180034150`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180026e4f`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180026e4f`

## pseudocode

```c
Microsoft::WRL::FtmBase *__fastcall Microsoft::WRL::FtmBase::FtmBase(Microsoft::WRL::FtmBase *this)
{
  char *v1; // r14
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  LPUNKNOWN ppunkMarshal; // [rsp+30h] [rbp+8h] BYREF

  ppunkMarshal = 0;
  v1 = (char *)this + 24;
  *(_QWORD *)this = &Microsoft::WRL::FtmBase::`vftable';
  *((_QWORD *)this + 3) = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppunkMarshal);
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v3 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v1);
    ((void (__fastcall *)(LPUNKNOWN, GUID *, char *))QueryInterface)(v3, &GUID_00000003_0000_0000_c000_000000000046, v1);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppunkMarshal);
  return this;
}

```

## disassembly

```asm
0x180026e10  mov     r11, rsp
0x180026e13  mov     [r11+10h], rbx
0x180026e17  mov     [r11+18h], rsi
0x180026e1b  mov     [r11+20h], rdi
0x180026e1f  push    r14
0x180026e21  sub     rsp, 20h
0x180026e25  and     qword ptr [r11+8], 0
0x180026e2a  lea     r14, [rcx+18h]
0x180026e2e  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x180026e35  mov     rsi, rcx
0x180026e38  mov     [rcx], rax
0x180026e3b  lea     rcx, [r11+8]
0x180026e3f  and     qword ptr [r14], 0
0x180026e43  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026e48  lea     rdx, [rsp+28h+ppunkMarshal]; ppunkMarshal
0x180026e4d  xor     ecx, ecx; punkOuter
0x180026e4f  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180026e56  nop     dword ptr [rax+rax+00h]
0x180026e5b  test    eax, eax
0x180026e5d  js      short loc_180026E87
0x180026e5f  mov     rbx, [rsp+28h+ppunkMarshal]
0x180026e64  mov     rcx, r14
0x180026e67  mov     rax, [rbx]
0x180026e6a  mov     rdi, [rax]
0x180026e6d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026e72  mov     r8, r14
0x180026e75  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x180026e7c  mov     rcx, rbx
0x180026e7f  mov     rax, rdi
0x180026e82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e87  lea     rcx, [rsp+28h+ppunkMarshal]
0x180026e8c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026e91  mov     rbx, [rsp+28h+arg_8]
0x180026e96  mov     rax, rsi
0x180026e99  mov     rsi, [rsp+28h+arg_10]
0x180026e9e  mov     rdi, [rsp+28h+arg_18]
0x180026ea3  add     rsp, 20h
0x180026ea7  pop     r14
0x180026ea9  retn
```
