# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)

- ea: `0x140040b4c`
- end: `0x140040c21`
- name: `??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `213`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400402a4`
- `0x140040574`

## callees

- `0x140040b4c`
- `0x140045dc0`
- `0x14004cd00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x140040b95`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x140040b95`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(
        _QWORD *a1)
{
  __int64 *v2; // rdi
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbp
  __int64 v5; // rcx
  LPUNKNOWN v6; // rcx
  LPUNKNOWN v8; // [rsp+20h] [rbp-18h] BYREF

  *a1 = &Microsoft::WRL::FtmBase::`vftable';
  v2 = a1 + 3;
  a1[3] = 0;
  v8 = 0;
  if ( CoCreateFreeThreadedMarshaler(0, &v8) >= 0 )
  {
    v3 = v8;
    QueryInterface = v8->lpVtbl->QueryInterface;
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
  v6 = v8;
  if ( v8 )
  {
    v8 = 0;
    ((void (__fastcall *)(LPUNKNOWN))v6->lpVtbl->Release)(v6);
  }
  return a1;
}

```

## disassembly

```asm
0x140040b4c  mov     r11, rsp
0x140040b4f  mov     [r11+10h], rbx
0x140040b53  mov     [r11+18h], rbp
0x140040b57  mov     [r11+20h], rsi
0x140040b5b  push    rdi
0x140040b5c  sub     rsp, 30h
0x140040b60  mov     rax, cs:__security_cookie
0x140040b67  xor     rax, rsp
0x140040b6a  mov     [rsp+38h+var_10], rax
0x140040b6f  mov     rsi, rcx
0x140040b72  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x140040b79  mov     [rcx], rax
0x140040b7c  lea     rdi, [rcx+18h]
0x140040b80  mov     qword ptr [rdi], 0
0x140040b87  mov     qword ptr [r11-18h], 0
0x140040b8f  lea     rdx, [r11-18h]; ppunkMarshal
0x140040b93  xor     ecx, ecx; punkOuter
0x140040b95  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x140040b9b  test    eax, eax
0x140040b9d  js      short loc_140040BDC
0x140040b9f  mov     rbx, [rsp+38h+var_18]
0x140040ba4  mov     rax, [rbx]
0x140040ba7  mov     rbp, [rax]
0x140040baa  mov     rcx, [rdi]
0x140040bad  test    rcx, rcx
0x140040bb0  jz      short loc_140040BC6
0x140040bb2  mov     qword ptr [rdi], 0
0x140040bb9  mov     rdx, [rcx]
0x140040bbc  mov     rax, [rdx+10h]
0x140040bc0  call    _guard_dispatch_icall
0x140040bc5  nop
0x140040bc6  mov     r8, rdi
0x140040bc9  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x140040bd0  mov     rcx, rbx
0x140040bd3  mov     rax, rbp
0x140040bd6  call    _guard_dispatch_icall
0x140040bdb  nop
0x140040bdc  mov     rcx, [rsp+38h+var_18]
0x140040be1  test    rcx, rcx
0x140040be4  jz      short loc_140040BFC
0x140040be6  mov     [rsp+38h+var_18], 0
0x140040bef  mov     rdx, [rcx]
0x140040bf2  mov     rax, [rdx+10h]
0x140040bf6  call    _guard_dispatch_icall
0x140040bfb  nop
0x140040bfc  mov     rax, rsi
0x140040bff  mov     rcx, [rsp+38h+var_10]
0x140040c04  xor     rcx, rsp; StackCookie
0x140040c07  call    __security_check_cookie
0x140040c0c  mov     rbx, [rsp+38h+arg_8]
0x140040c11  mov     rbp, [rsp+38h+arg_10]
0x140040c16  mov     rsi, [rsp+38h+arg_18]
0x140040c1b  add     rsp, 30h
0x140040c1f  pop     rdi
0x140040c20  retn
```
