# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x180028380`
- end: `0x18002841b`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `155`
- prototype: `__int64 __fastcall(Microsoft::WRL::FtmBase *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180027a18`
- `0x1800282e8`

## callees

- `0x180028380`
- `0x180033de0`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800283bf`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800283bf`

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
0x180028380  mov     r11, rsp
0x180028383  mov     [r11+10h], rbx
0x180028387  mov     [r11+18h], rsi
0x18002838b  mov     [r11+20h], rdi
0x18002838f  push    r14
0x180028391  sub     rsp, 20h
0x180028395  and     qword ptr [r11+8], 0
0x18002839a  lea     r14, [rcx+18h]
0x18002839e  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x1800283a5  mov     rsi, rcx
0x1800283a8  mov     [rcx], rax
0x1800283ab  lea     rcx, [r11+8]
0x1800283af  and     qword ptr [r14], 0
0x1800283b3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800283b8  lea     rdx, [rsp+28h+ppunkMarshal]; ppunkMarshal
0x1800283bd  xor     ecx, ecx; punkOuter
0x1800283bf  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1800283c6  nop     dword ptr [rax+rax+00h]
0x1800283cb  test    eax, eax
0x1800283cd  js      short loc_1800283F7
0x1800283cf  mov     rbx, [rsp+28h+ppunkMarshal]
0x1800283d4  mov     rcx, r14
0x1800283d7  mov     rax, [rbx]
0x1800283da  mov     rdi, [rax]
0x1800283dd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800283e2  mov     r8, r14
0x1800283e5  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x1800283ec  mov     rcx, rbx
0x1800283ef  mov     rax, rdi
0x1800283f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800283f7  lea     rcx, [rsp+28h+ppunkMarshal]
0x1800283fc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180028401  mov     rbx, [rsp+28h+arg_8]
0x180028406  mov     rax, rsi
0x180028409  mov     rsi, [rsp+28h+arg_10]
0x18002840e  mov     rdi, [rsp+28h+arg_18]
0x180028413  add     rsp, 20h
0x180028417  pop     r14
0x180028419  retn
```
