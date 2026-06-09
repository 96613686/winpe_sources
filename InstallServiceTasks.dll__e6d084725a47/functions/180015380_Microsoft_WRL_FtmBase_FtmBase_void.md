# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x180015380`
- end: `0x180015406`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `134`
- prototype: `Microsoft::WRL::FtmBase *__fastcall(Microsoft::WRL::FtmBase *this)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180014574`
- `0x180015074`
- `0x18003b4dc`

## callees

- `0x18000760c`
- `0x180015380`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800153bc`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800153bc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180015380  push    rbx
0x180015382  push    rsi
0x180015383  push    rdi
0x180015384  push    r14
0x180015386  sub     rsp, 28h
0x18001538a  mov     rsi, rcx
0x18001538d  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x180015394  mov     [rcx], rax
0x180015397  lea     r14, [rcx+18h]
0x18001539b  mov     qword ptr [r14], 0
0x1800153a2  mov     [rsp+48h+ppunkMarshal], 0
0x1800153ab  lea     rcx, [rsp+48h+ppunkMarshal]
0x1800153b0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800153b5  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x1800153ba  xor     ecx, ecx; punkOuter
0x1800153bc  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1800153c2  test    eax, eax
0x1800153c4  js      short loc_1800153EF
0x1800153c6  mov     rbx, [rsp+48h+ppunkMarshal]
0x1800153cb  mov     rax, [rbx]
0x1800153ce  mov     rdi, [rax]
0x1800153d1  mov     rcx, r14
0x1800153d4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800153d9  mov     r8, r14
0x1800153dc  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x1800153e3  mov     rcx, rbx
0x1800153e6  mov     rax, rdi
0x1800153e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153ee  nop
0x1800153ef  lea     rcx, [rsp+48h+ppunkMarshal]
0x1800153f4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800153f9  mov     rax, rsi
0x1800153fc  add     rsp, 28h
0x180015400  pop     r14
0x180015402  pop     rdi
0x180015403  pop     rsi
0x180015404  pop     rbx
0x180015405  retn
```
