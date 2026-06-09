# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x180011744`
- end: `0x1800117e8`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `164`
- prototype: `__int64 __fastcall(Microsoft::WRL::FtmBase *__hidden this)`
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f2cc`
- `0x18000f468`
- `0x1800105e0`
- `0x180010788`
- `0x180010868`
- `0x180010948`
- `0x180010a34`
- `0x180010b20`
- `0x180010c78`

## callees

- `0x180011744`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180011775`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180011775`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
Microsoft::WRL::FtmBase *__fastcall Microsoft::WRL::FtmBase::FtmBase(Microsoft::WRL::FtmBase *this)
{
  __int64 *v2; // rdi
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbp
  __int64 v5; // rcx
  LPUNKNOWN v6; // rcx
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  *(_QWORD *)this = &Microsoft::WRL::FtmBase::`vftable';
  v2 = (__int64 *)((char *)this + 24);
  *((_QWORD *)this + 3) = 0;
  ppunkMarshal = 0;
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v3 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    v5 = *v2;
    if ( *v2 )
    {
      *v2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    ((void (__fastcall *)(LPUNKNOWN, GUID *, __int64 *))QueryInterface)(
      v3,
      &GUID_00000003_0000_0000_c000_000000000046,
      v2);
  }
  v6 = ppunkMarshal;
  if ( ppunkMarshal )
  {
    ppunkMarshal = 0;
    ((void (__fastcall *)(LPUNKNOWN))v6->lpVtbl->Release)(v6);
  }
  return this;
}

```

## disassembly

```asm
0x180011744  push    rbx
0x180011746  push    rbp
0x180011747  push    rsi
0x180011748  push    rdi
0x180011749  sub     rsp, 28h
0x18001174d  mov     rsi, rcx
0x180011750  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x180011757  mov     [rcx], rax
0x18001175a  lea     rdi, [rcx+18h]
0x18001175e  mov     qword ptr [rdi], 0
0x180011765  mov     [rsp+48h+ppunkMarshal], 0
0x18001176e  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x180011773  xor     ecx, ecx; punkOuter
0x180011775  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18001177b  test    eax, eax
0x18001177d  js      short loc_1800117BC
0x18001177f  mov     rbx, [rsp+48h+ppunkMarshal]
0x180011784  mov     rax, [rbx]
0x180011787  mov     rbp, [rax]
0x18001178a  mov     rcx, [rdi]
0x18001178d  test    rcx, rcx
0x180011790  jz      short loc_1800117A6
0x180011792  mov     qword ptr [rdi], 0
0x180011799  mov     rdx, [rcx]
0x18001179c  mov     rax, [rdx+10h]
0x1800117a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800117a5  nop
0x1800117a6  mov     r8, rdi
0x1800117a9  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x1800117b0  mov     rcx, rbx
0x1800117b3  mov     rax, rbp
0x1800117b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800117bb  nop
0x1800117bc  mov     rcx, [rsp+48h+ppunkMarshal]
0x1800117c1  test    rcx, rcx
0x1800117c4  jz      short loc_1800117DC
0x1800117c6  mov     [rsp+48h+ppunkMarshal], 0
0x1800117cf  mov     rax, [rcx]
0x1800117d2  mov     rax, [rax+10h]
0x1800117d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800117db  nop
0x1800117dc  mov     rax, rsi
0x1800117df  add     rsp, 28h
0x1800117e3  pop     rdi
0x1800117e4  pop     rsi
0x1800117e5  pop     rbp
0x1800117e6  pop     rbx
0x1800117e7  retn
```
