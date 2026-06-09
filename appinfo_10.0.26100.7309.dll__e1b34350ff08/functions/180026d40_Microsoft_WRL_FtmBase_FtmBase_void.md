# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x180026d40`
- end: `0x180026ddb`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `155`
- prototype: `__int64 __fastcall(Microsoft::WRL::FtmBase *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800263d8`
- `0x180026ca8`

## callees

- `0x180026d40`
- `0x180033e90`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180026d7f`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180026d7f`

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
0x180026d40  mov     r11, rsp
0x180026d43  mov     [r11+10h], rbx
0x180026d47  mov     [r11+18h], rsi
0x180026d4b  mov     [r11+20h], rdi
0x180026d4f  push    r14
0x180026d51  sub     rsp, 20h
0x180026d55  and     qword ptr [r11+8], 0
0x180026d5a  lea     r14, [rcx+18h]
0x180026d5e  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x180026d65  mov     rsi, rcx
0x180026d68  mov     [rcx], rax
0x180026d6b  lea     rcx, [r11+8]
0x180026d6f  and     qword ptr [r14], 0
0x180026d73  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026d78  lea     rdx, [rsp+28h+ppunkMarshal]; ppunkMarshal
0x180026d7d  xor     ecx, ecx; punkOuter
0x180026d7f  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180026d86  nop     dword ptr [rax+rax+00h]
0x180026d8b  test    eax, eax
0x180026d8d  js      short loc_180026DB7
0x180026d8f  mov     rbx, [rsp+28h+ppunkMarshal]
0x180026d94  mov     rcx, r14
0x180026d97  mov     rax, [rbx]
0x180026d9a  mov     rdi, [rax]
0x180026d9d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026da2  mov     r8, r14
0x180026da5  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x180026dac  mov     rcx, rbx
0x180026daf  mov     rax, rdi
0x180026db2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026db7  lea     rcx, [rsp+28h+ppunkMarshal]
0x180026dbc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026dc1  mov     rbx, [rsp+28h+arg_8]
0x180026dc6  mov     rax, rsi
0x180026dc9  mov     rsi, [rsp+28h+arg_10]
0x180026dce  mov     rdi, [rsp+28h+arg_18]
0x180026dd3  add     rsp, 20h
0x180026dd7  pop     r14
0x180026dd9  retn
```
