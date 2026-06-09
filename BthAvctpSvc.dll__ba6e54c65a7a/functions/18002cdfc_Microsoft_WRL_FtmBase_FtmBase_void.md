# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x18002cdfc`
- end: `0x18002ce82`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `134`
- prototype: `Microsoft::WRL::FtmBase *__fastcall(Microsoft::WRL::FtmBase *this)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002ce88`
- `0x180034c38`
- `0x18003ee1c`

## callees

- `0x18000d0c0`
- `0x18002cdfc`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18002ce38`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18002ce38`

## pseudocode

```c
Microsoft::WRL::FtmBase *__fastcall Microsoft::WRL::FtmBase::FtmBase(Microsoft::WRL::FtmBase *this)
{
  char *v2; // r14
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  *(_QWORD *)this = &Microsoft::WRL::FtmBase::`vftable';
  v2 = (char *)this + 24;
  *((_QWORD *)this + 3) = 0;
  ppunkMarshal = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppunkMarshal);
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v3 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v2);
    ((void (__fastcall *)(LPUNKNOWN, GUID *, char *))QueryInterface)(v3, &GUID_00000003_0000_0000_c000_000000000046, v2);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppunkMarshal);
  return this;
}

```

## disassembly

```asm
0x18002cdfc  push    rbx
0x18002cdfe  push    rsi
0x18002cdff  push    rdi
0x18002ce00  push    r14
0x18002ce02  sub     rsp, 28h
0x18002ce06  mov     rsi, rcx
0x18002ce09  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x18002ce10  mov     [rcx], rax
0x18002ce13  lea     r14, [rcx+18h]
0x18002ce17  mov     qword ptr [r14], 0
0x18002ce1e  mov     [rsp+48h+ppunkMarshal], 0
0x18002ce27  lea     rcx, [rsp+48h+ppunkMarshal]
0x18002ce2c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002ce31  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x18002ce36  xor     ecx, ecx; punkOuter
0x18002ce38  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18002ce3e  test    eax, eax
0x18002ce40  js      short loc_18002CE6B
0x18002ce42  mov     rbx, [rsp+48h+ppunkMarshal]
0x18002ce47  mov     rax, [rbx]
0x18002ce4a  mov     rdi, [rax]
0x18002ce4d  mov     rcx, r14
0x18002ce50  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002ce55  mov     r8, r14
0x18002ce58  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18002ce5f  mov     rcx, rbx
0x18002ce62  mov     rax, rdi
0x18002ce65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce6a  nop
0x18002ce6b  lea     rcx, [rsp+48h+ppunkMarshal]
0x18002ce70  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002ce75  mov     rax, rsi
0x18002ce78  add     rsp, 28h
0x18002ce7c  pop     r14
0x18002ce7e  pop     rdi
0x18002ce7f  pop     rsi
0x18002ce80  pop     rbx
0x18002ce81  retn
```
