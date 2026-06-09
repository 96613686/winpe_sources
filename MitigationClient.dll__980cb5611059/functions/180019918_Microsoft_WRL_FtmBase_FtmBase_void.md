# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x180019918`
- end: `0x18001999e`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `134`
- prototype: `Microsoft::WRL::FtmBase *__fastcall(Microsoft::WRL::FtmBase *this)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180017e64`
- `0x180036e44`
- `0x180037914`
- `0x1800379b0`
- `0x180037a84`

## callees

- `0x18001055c`
- `0x180019918`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180019954`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180019954`

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
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&ppunkMarshal);
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v3 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v2);
    ((void (__fastcall *)(LPUNKNOWN, GUID *, char *))QueryInterface)(v3, &GUID_00000003_0000_0000_c000_000000000046, v2);
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&ppunkMarshal);
  return this;
}

```

## disassembly

```asm
0x180019918  push    rbx
0x18001991a  push    rsi
0x18001991b  push    rdi
0x18001991c  push    r14
0x18001991e  sub     rsp, 28h
0x180019922  mov     rsi, rcx
0x180019925  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x18001992c  mov     [rcx], rax
0x18001992f  lea     r14, [rcx+18h]
0x180019933  mov     qword ptr [r14], 0
0x18001993a  mov     [rsp+48h+ppunkMarshal], 0
0x180019943  lea     rcx, [rsp+48h+ppunkMarshal]
0x180019948  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001994d  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x180019952  xor     ecx, ecx; punkOuter
0x180019954  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18001995a  test    eax, eax
0x18001995c  js      short loc_180019987
0x18001995e  mov     rbx, [rsp+48h+ppunkMarshal]
0x180019963  mov     rax, [rbx]
0x180019966  mov     rdi, [rax]
0x180019969  mov     rcx, r14
0x18001996c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180019971  mov     r8, r14
0x180019974  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18001997b  mov     rcx, rbx
0x18001997e  mov     rax, rdi
0x180019981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019986  nop
0x180019987  lea     rcx, [rsp+48h+ppunkMarshal]
0x18001998c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180019991  mov     rax, rsi
0x180019994  add     rsp, 28h
0x180019998  pop     r14
0x18001999a  pop     rdi
0x18001999b  pop     rsi
0x18001999c  pop     rbx
0x18001999d  retn
```
