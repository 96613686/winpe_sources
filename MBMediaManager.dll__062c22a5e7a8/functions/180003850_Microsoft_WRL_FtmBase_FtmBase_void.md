# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x180003850`
- end: `0x1800038ec`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `156`
- prototype: `Microsoft::WRL::FtmBase *__fastcall(Microsoft::WRL::FtmBase *this)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003730`
- `0x18001fc14`
- `0x180025f78`
- `0x1800315b0`
- `0x18003a890`
- `0x18003a99c`

## callees

- `0x180002150`
- `0x180003850`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000388c`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000388c`

## pseudocode

```c
Microsoft::WRL::FtmBase *__fastcall Microsoft::WRL::FtmBase::FtmBase(Microsoft::WRL::FtmBase *this)
{
  char *v2; // r14
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  LPUNKNOWN v5; // rcx
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
  v5 = ppunkMarshal;
  if ( ppunkMarshal )
  {
    ppunkMarshal = 0;
    ((void (__fastcall *)(LPUNKNOWN))v5->lpVtbl->Release)(v5);
  }
  return this;
}

```

## disassembly

```asm
0x180003850  push    rbx
0x180003852  push    rsi
0x180003853  push    rdi
0x180003854  push    r14
0x180003856  sub     rsp, 28h
0x18000385a  mov     rsi, rcx
0x18000385d  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x180003864  mov     [rcx], rax
0x180003867  lea     r14, [rcx+18h]
0x18000386b  mov     qword ptr [r14], 0
0x180003872  mov     [rsp+48h+ppunkMarshal], 0
0x18000387b  lea     rcx, [rsp+48h+ppunkMarshal]
0x180003880  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180003885  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x18000388a  xor     ecx, ecx; punkOuter
0x18000388c  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180003892  test    eax, eax
0x180003894  js      short loc_1800038BF
0x180003896  mov     rbx, [rsp+48h+ppunkMarshal]
0x18000389b  mov     rax, [rbx]
0x18000389e  mov     rdi, [rax]
0x1800038a1  mov     rcx, r14
0x1800038a4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800038a9  mov     r8, r14
0x1800038ac  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x1800038b3  mov     rcx, rbx
0x1800038b6  mov     rax, rdi
0x1800038b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038be  nop
0x1800038bf  mov     rcx, [rsp+48h+ppunkMarshal]
0x1800038c4  test    rcx, rcx
0x1800038c7  jz      short loc_1800038DF
0x1800038c9  mov     [rsp+48h+ppunkMarshal], 0
0x1800038d2  mov     rax, [rcx]
0x1800038d5  mov     rax, [rax+10h]
0x1800038d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038de  nop
0x1800038df  mov     rax, rsi
0x1800038e2  add     rsp, 28h
0x1800038e6  pop     r14
0x1800038e8  pop     rdi
0x1800038e9  pop     rsi
0x1800038ea  pop     rbx
0x1800038eb  retn
```
