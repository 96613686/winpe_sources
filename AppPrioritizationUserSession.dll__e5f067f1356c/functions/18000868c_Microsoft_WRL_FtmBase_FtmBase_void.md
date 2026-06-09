# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x18000868c`
- end: `0x18000874c`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `192`
- prototype: `__int64 __fastcall(Microsoft::WRL::FtmBase *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180007990`
- `0x180008594`

## callees

- `0x180002650`
- `0x18000868c`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800086cc`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800086cc`

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
  LPUNKNOWN ppunkMarshal; // [rsp+20h] [rbp-38h] BYREF

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
0x18000868c  push    rbx
0x18000868e  push    rbp
0x18000868f  push    rsi
0x180008690  push    rdi
0x180008691  sub     rsp, 38h
0x180008695  mov     rax, cs:__security_cookie
0x18000869c  xor     rax, rsp
0x18000869f  mov     [rsp+58h+var_30], rax
0x1800086a4  mov     rsi, rcx
0x1800086a7  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x1800086ae  mov     [rcx], rax
0x1800086b1  lea     rdi, [rcx+18h]
0x1800086b5  mov     qword ptr [rdi], 0
0x1800086bc  mov     [rsp+58h+ppunkMarshal], 0
0x1800086c5  lea     rdx, [rsp+58h+ppunkMarshal]; ppunkMarshal
0x1800086ca  xor     ecx, ecx; punkOuter
0x1800086cc  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1800086d2  test    eax, eax
0x1800086d4  js      short loc_180008713
0x1800086d6  mov     rbx, [rsp+58h+ppunkMarshal]
0x1800086db  mov     rax, [rbx]
0x1800086de  mov     rbp, [rax]
0x1800086e1  mov     rcx, [rdi]
0x1800086e4  test    rcx, rcx
0x1800086e7  jz      short loc_1800086FD
0x1800086e9  mov     qword ptr [rdi], 0
0x1800086f0  mov     rdx, [rcx]
0x1800086f3  mov     rax, [rdx+10h]
0x1800086f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086fc  nop
0x1800086fd  mov     r8, rdi
0x180008700  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x180008707  mov     rcx, rbx
0x18000870a  mov     rax, rbp
0x18000870d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008712  nop
0x180008713  mov     rcx, [rsp+58h+ppunkMarshal]
0x180008718  test    rcx, rcx
0x18000871b  jz      short loc_180008733
0x18000871d  mov     [rsp+58h+ppunkMarshal], 0
0x180008726  mov     rdx, [rcx]
0x180008729  mov     rax, [rdx+10h]
0x18000872d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008732  nop
0x180008733  mov     rax, rsi
0x180008736  mov     rcx, [rsp+58h+var_30]
0x18000873b  xor     rcx, rsp; StackCookie
0x18000873e  call    __security_check_cookie
0x180008743  add     rsp, 38h
0x180008747  pop     rdi
0x180008748  pop     rsi
0x180008749  pop     rbp
0x18000874a  pop     rbx
0x18000874b  retn
```
