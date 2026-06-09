# CreateObjectServerTaskBase::CreateObjectServerTaskBase(void)

- ea: `0x14000722c`
- end: `0x1400072e3`
- name: `??0CreateObjectServerTaskBase@@QEAA@XZ`
- size: `183`
- prototype: `CreateObjectServerTaskBase *__fastcall(CreateObjectServerTaskBase *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x140006788`

## callees

- `0x140004340`
- `0x14000722c`
- `0x14000a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x140007269`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x140007269`

## pseudocode

```c
CreateObjectServerTaskBase *__fastcall CreateObjectServerTaskBase::CreateObjectServerTaskBase(
        CreateObjectServerTaskBase *this)
{
  char *v2; // r14
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  *((_QWORD *)this + 2) = &CreateObjectServerTaskBase::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  v2 = (char *)this + 40;
  *((_QWORD *)this + 5) = 0;
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
  *(_QWORD *)this = &CreateObjectServerTaskBase::`vftable';
  *((_QWORD *)this + 1) = &CreateObjectServerTaskBase::`vftable'{for `IClassFactory'};
  *((_QWORD *)this + 2) = &CreateObjectServerTaskBase::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  return this;
}

```

## disassembly

```asm
0x14000722c  push    rbx
0x14000722e  push    rsi
0x14000722f  push    rdi
0x140007230  push    r14
0x140007232  sub     rsp, 28h
0x140007236  mov     rsi, rcx
0x140007239  lea     rax, ??_7CreateObjectServerTaskBase@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const CreateObjectServerTaskBase::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x140007240  mov     [rcx+10h], rax
0x140007244  lea     r14, [rcx+28h]
0x140007248  mov     qword ptr [r14], 0
0x14000724f  mov     [rsp+48h+ppunkMarshal], 0
0x140007258  lea     rcx, [rsp+48h+ppunkMarshal]
0x14000725d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140007262  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x140007267  xor     ecx, ecx; punkOuter
0x140007269  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x14000726f  test    eax, eax
0x140007271  js      short loc_14000729C
0x140007273  mov     rbx, [rsp+48h+ppunkMarshal]
0x140007278  mov     rax, [rbx]
0x14000727b  mov     rdi, [rax]
0x14000727e  mov     rcx, r14
0x140007281  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140007286  mov     r8, r14
0x140007289  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x140007290  mov     rcx, rbx
0x140007293  mov     rax, rdi
0x140007296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000729b  nop
0x14000729c  lea     rcx, [rsp+48h+ppunkMarshal]
0x1400072a1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400072a6  lea     rax, ??_7CreateObjectServerTaskBase@@6B@; const CreateObjectServerTaskBase::`vftable'
0x1400072ad  mov     [rsi], rax
0x1400072b0  lea     rax, ??_7CreateObjectServerTaskBase@@6BIClassFactory@@@; const CreateObjectServerTaskBase::`vftable'{for `IClassFactory'}
0x1400072b7  mov     [rsi+8], rax
0x1400072bb  lea     rax, ??_7CreateObjectServerTaskBase@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const CreateObjectServerTaskBase::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1400072c2  mov     [rsi+10h], rax
0x1400072c6  mov     qword ptr [rsi+50h], 0
0x1400072ce  mov     qword ptr [rsi+58h], 0
0x1400072d6  mov     rax, rsi
0x1400072d9  add     rsp, 28h
0x1400072dd  pop     r14
0x1400072df  pop     rdi
0x1400072e0  pop     rsi
0x1400072e1  pop     rbx
0x1400072e2  retn
```
