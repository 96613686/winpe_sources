# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x18000ed8c`
- end: `0x18000ee2d`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `161`
- prototype: `Microsoft::WRL::FtmBase *__fastcall(Microsoft::WRL::FtmBase *this)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000dd2c`
- `0x18000de6c`
- `0x18000e0b4`
- `0x18000e2fc`
- `0x18000e544`
- `0x18000e78c`
- `0x18000ea14`

## callees

- `0x18000ed8c`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000edbd`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000edbd`

## pseudocode

```c
Microsoft::WRL::FtmBase *__fastcall Microsoft::WRL::FtmBase::FtmBase(Microsoft::WRL::FtmBase *this)
{
  __int64 *v1; // rdi
  LPUNKNOWN v3; // rbx
  __int64 v4; // rcx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbp
  LPUNKNOWN v6; // rcx
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  v1 = (__int64 *)((char *)this + 24);
  ppunkMarshal = 0;
  *(_QWORD *)this = &Microsoft::WRL::FtmBase::`vftable';
  *((_QWORD *)this + 3) = 0;
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v3 = ppunkMarshal;
    v4 = *v1;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    if ( *v1 )
    {
      *v1 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    }
    ((void (__fastcall *)(LPUNKNOWN, GUID *, __int64 *))QueryInterface)(
      v3,
      &GUID_00000003_0000_0000_c000_000000000046,
      v1);
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
0x18000ed8c  push    rbx
0x18000ed8e  push    rbp
0x18000ed8f  push    rsi
0x18000ed90  push    rdi
0x18000ed91  sub     rsp, 28h
0x18000ed95  lea     rdi, [rcx+18h]
0x18000ed99  mov     [rsp+48h+ppunkMarshal], 0
0x18000eda2  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x18000eda9  mov     rsi, rcx
0x18000edac  mov     [rcx], rax
0x18000edaf  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x18000edb4  xor     ecx, ecx; punkOuter
0x18000edb6  mov     qword ptr [rdi], 0
0x18000edbd  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18000edc3  test    eax, eax
0x18000edc5  js      short loc_18000EE02
0x18000edc7  mov     rbx, [rsp+48h+ppunkMarshal]
0x18000edcc  mov     rcx, [rdi]
0x18000edcf  mov     rax, [rbx]
0x18000edd2  mov     rbp, [rax]
0x18000edd5  test    rcx, rcx
0x18000edd8  jz      short loc_18000EDED
0x18000edda  mov     qword ptr [rdi], 0
0x18000ede1  mov     rdx, [rcx]
0x18000ede4  mov     rax, [rdx+10h]
0x18000ede8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eded  mov     r8, rdi
0x18000edf0  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18000edf7  mov     rcx, rbx
0x18000edfa  mov     rax, rbp
0x18000edfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee02  mov     rcx, [rsp+48h+ppunkMarshal]
0x18000ee07  test    rcx, rcx
0x18000ee0a  jz      short loc_18000EE21
0x18000ee0c  mov     [rsp+48h+ppunkMarshal], 0
0x18000ee15  mov     rax, [rcx]
0x18000ee18  mov     rax, [rax+10h]
0x18000ee1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee21  mov     rax, rsi
0x18000ee24  add     rsp, 28h
0x18000ee28  pop     rdi
0x18000ee29  pop     rsi
0x18000ee2a  pop     rbp
0x18000ee2b  pop     rbx
0x18000ee2c  retn
```
