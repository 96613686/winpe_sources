# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x180095a74`
- end: `0x180095b15`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `161`
- prototype: `__int64 __fastcall(Microsoft::WRL::FtmBase *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180095904`
- `0x1800982c4`
- `0x1800984b8`
- `0x1800a4e48`

## callees

- `0x180095a74`
- `0x1800967ac`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180095ab9`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180095ab9`

## pseudocode

```c
Microsoft::WRL::FtmBase *__fastcall Microsoft::WRL::FtmBase::FtmBase(Microsoft::WRL::FtmBase *this)
{
  char *v1; // r14
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  LPUNKNOWN ppunkMarshal; // [rsp+30h] [rbp+8h] BYREF

  v1 = (char *)this + 24;
  ppunkMarshal = 0;
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
0x180095a74  mov     r11, rsp
0x180095a77  mov     [r11+10h], rbx
0x180095a7b  mov     [r11+18h], rsi
0x180095a7f  mov     [r11+20h], rdi
0x180095a83  push    r14
0x180095a85  sub     rsp, 20h
0x180095a89  lea     r14, [rcx+18h]
0x180095a8d  mov     qword ptr [r11+8], 0
0x180095a95  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x180095a9c  mov     rsi, rcx
0x180095a9f  mov     [rcx], rax
0x180095aa2  lea     rcx, [r11+8]
0x180095aa6  mov     qword ptr [r14], 0
0x180095aad  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180095ab2  lea     rdx, [rsp+28h+ppunkMarshal]; ppunkMarshal
0x180095ab7  xor     ecx, ecx; punkOuter
0x180095ab9  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180095ac0  nop     dword ptr [rax+rax+00h]
0x180095ac5  test    eax, eax
0x180095ac7  js      short loc_180095AF1
0x180095ac9  mov     rbx, [rsp+28h+ppunkMarshal]
0x180095ace  mov     rcx, r14
0x180095ad1  mov     rax, [rbx]
0x180095ad4  mov     rdi, [rax]
0x180095ad7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180095adc  mov     r8, r14
0x180095adf  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x180095ae6  mov     rcx, rbx
0x180095ae9  mov     rax, rdi
0x180095aec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095af1  lea     rcx, [rsp+28h+ppunkMarshal]
0x180095af6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180095afb  mov     rbx, [rsp+28h+arg_8]
0x180095b00  mov     rax, rsi
0x180095b03  mov     rsi, [rsp+28h+arg_10]
0x180095b08  mov     rdi, [rsp+28h+arg_18]
0x180095b0d  add     rsp, 20h
0x180095b11  pop     r14
0x180095b13  retn
```
