# Windows::Internal::PopupWindowExtendedStringContentImpl::PopupWindowExtendedStringContentImpl(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x180084c10`
- end: `0x180084da9`
- name: `??0PopupWindowExtendedStringContentImpl@Internal@Windows@@QEAA@PEBG0000@Z`
- size: `409`
- prototype: `__int64 __fastcall(Windows::Internal::PopupWindowExtendedStringContentImpl *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180047720`

## callees

- `0x18000af94`
- `0x180084b40`
- `0x180084c10`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084cab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084cbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084ccc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084cdc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084cec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084d05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084d20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084d39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084d5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084d7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084cab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084cbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084ccc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084cdc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084cec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084d05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084d20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084d39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084d5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084d7f`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
Windows::Internal::PopupWindowExtendedStringContentImpl *__fastcall Windows::Internal::PopupWindowExtendedStringContentImpl::PopupWindowExtendedStringContentImpl(
        LPVOID *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6)
{
  LPVOID *v9; // rdi
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx

  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::IPopupWindowImplDUIContent>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::IPopupWindowImplDUIContent>(this);
  *this = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Internal::IPopupWindowExtendedStringContent>::`vftable'{for `Windows::Internal::IPopupWindowExtendedStringContent'};
  this[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Internal::IPopupWindowExtendedStringContent>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *, _QWORD))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                                 + 8LL))(
      Microsoft::WRL::Details::ModuleBase::module_,
      0);
  *this = &Windows::Internal::PopupWindowExtendedStringContentImpl::`vftable'{for `Windows::Internal::IPopupWindowExtendedStringContent'};
  this[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Internal::IPopupWindowExtendedStringContent>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource>'};
  this[4] = 0;
  this[5] = 0;
  v9 = this + 6;
  this[6] = 0;
  this[7] = 0;
  *((_BYTE *)this + 64) = 0;
  this[9] = 0;
  CoTaskMemFree(0);
  this[4] = 0;
  CoTaskMemFree(this[5]);
  this[5] = 0;
  CoTaskMemFree(this[6]);
  this[6] = 0;
  CoTaskMemFree(this[7]);
  this[7] = 0;
  CoTaskMemFree(this[9]);
  this[9] = 0;
  if ( a2 )
  {
    CoTaskMemFree(this[4]);
    _AllocString<CTCoAllocPolicy>(v11, v10, a2, this + 4);
  }
  if ( a3 )
  {
    CoTaskMemFree(this[5]);
    _AllocString<CTCoAllocPolicy>(v13, v12, a3, this + 5);
  }
  if ( a4 )
  {
    CoTaskMemFree(*v9);
    _AllocString<CTCoAllocPolicy>(v15, v14, a4, v9);
  }
  if ( a5 )
  {
    CoTaskMemFree(this[7]);
    _AllocString<CTCoAllocPolicy>(v17, v16, a5, this + 7);
  }
  if ( a6 )
  {
    *((_BYTE *)this + 64) = 1;
    CoTaskMemFree(this[9]);
    _AllocString<CTCoAllocPolicy>(v19, v18, a6, this + 9);
  }
  return (Windows::Internal::PopupWindowExtendedStringContentImpl *)this;
}

```

## disassembly

```asm
0x180084c10  mov     [rsp+arg_10], rbx
0x180084c15  mov     [rsp+arg_8], rdx
0x180084c1a  mov     [rsp+arg_0], rcx
0x180084c1f  push    rbp
0x180084c20  push    rsi
0x180084c21  push    rdi
0x180084c22  push    r12
0x180084c24  push    r13
0x180084c26  push    r14
0x180084c28  push    r15
0x180084c2a  sub     rsp, 20h
0x180084c2e  mov     r12, r9
0x180084c31  mov     r13, r8
0x180084c34  mov     rbx, rcx
0x180084c37  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIPopupWindowImplDUIContent@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::IPopupWindowImplDUIContent>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::IPopupWindowImplDUIContent>(void)
0x180084c3c  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIPopupWindowExtendedStringContent@Internal@Windows@@@WRL@Microsoft@@6BIPopupWindowExtendedStringContent@Internal@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Internal::IPopupWindowExtendedStringContent>::`vftable'{for `Windows::Internal::IPopupWindowExtendedStringContent'}
0x180084c43  mov     [rbx], rcx
0x180084c46  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIPopupWindowExtendedStringContent@Internal@Windows@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Internal::IPopupWindowExtendedStringContent>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource>'}
0x180084c4d  mov     [rbx+8], rax
0x180084c51  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180084c58  xor     edx, edx
0x180084c5a  test    rcx, rcx
0x180084c5d  jz      short loc_180084C6D
0x180084c5f  mov     rax, [rcx]
0x180084c62  mov     rax, [rax+8]
0x180084c66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084c6b  xor     edx, edx
0x180084c6d  lea     rax, ??_7PopupWindowExtendedStringContentImpl@Internal@Windows@@6BIPopupWindowExtendedStringContent@12@@; const Windows::Internal::PopupWindowExtendedStringContentImpl::`vftable'{for `Windows::Internal::IPopupWindowExtendedStringContent'}
0x180084c74  mov     [rbx], rax
0x180084c77  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIPopupWindowExtendedStringContent@Internal@Windows@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Internal::IPopupWindowExtendedStringContent>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource>'}
0x180084c7e  mov     [rbx+8], rax
0x180084c82  lea     rbp, [rbx+20h]
0x180084c86  mov     [rbp+0], rdx
0x180084c8a  lea     r15, [rbx+28h]
0x180084c8e  mov     [r15], rdx
0x180084c91  lea     rdi, [rbx+30h]
0x180084c95  mov     [rdi], rdx
0x180084c98  lea     r14, [rbx+38h]
0x180084c9c  mov     [r14], rdx
0x180084c9f  mov     [rbx+40h], dl
0x180084ca2  lea     rsi, [rbx+48h]
0x180084ca6  mov     [rsi], rdx
0x180084ca9  xor     ecx, ecx; pv
0x180084cab  call    cs:__imp_CoTaskMemFree
0x180084cb1  mov     qword ptr [rbp+0], 0
0x180084cb9  mov     rcx, [r15]; pv
0x180084cbc  call    cs:__imp_CoTaskMemFree
0x180084cc2  mov     qword ptr [r15], 0
0x180084cc9  mov     rcx, [rdi]; pv
0x180084ccc  call    cs:__imp_CoTaskMemFree
0x180084cd2  mov     qword ptr [rdi], 0
0x180084cd9  mov     rcx, [r14]; pv
0x180084cdc  call    cs:__imp_CoTaskMemFree
0x180084ce2  mov     qword ptr [r14], 0
0x180084ce9  mov     rcx, [rsi]; pv
0x180084cec  call    cs:__imp_CoTaskMemFree
0x180084cf2  mov     qword ptr [rsi], 0
0x180084cf9  cmp     [rsp+58h+arg_8], 0
0x180084cff  jz      short loc_180084D18
0x180084d01  mov     rcx, [rbp+0]; pv
0x180084d05  call    cs:__imp_CoTaskMemFree
0x180084d0b  mov     r9, rbp
0x180084d0e  mov     r8, [rsp+58h+arg_8]
0x180084d13  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180084d18  test    r13, r13
0x180084d1b  jz      short loc_180084D31
0x180084d1d  mov     rcx, [r15]; pv
0x180084d20  call    cs:__imp_CoTaskMemFree
0x180084d26  mov     r9, r15
0x180084d29  mov     r8, r13
0x180084d2c  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180084d31  test    r12, r12
0x180084d34  jz      short loc_180084D4A
0x180084d36  mov     rcx, [rdi]; pv
0x180084d39  call    cs:__imp_CoTaskMemFree
0x180084d3f  mov     r9, rdi
0x180084d42  mov     r8, r12
0x180084d45  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180084d4a  mov     rdi, [rsp+58h+arg_20]
0x180084d52  test    rdi, rdi
0x180084d55  jz      short loc_180084D6B
0x180084d57  mov     rcx, [r14]; pv
0x180084d5a  call    cs:__imp_CoTaskMemFree
0x180084d60  mov     r9, r14
0x180084d63  mov     r8, rdi
0x180084d66  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180084d6b  mov     rdi, [rsp+58h+arg_28]
0x180084d73  test    rdi, rdi
0x180084d76  jz      short loc_180084D91
0x180084d78  mov     byte ptr [rbx+40h], 1
0x180084d7c  mov     rcx, [rsi]; pv
0x180084d7f  call    cs:__imp_CoTaskMemFree
0x180084d85  mov     r9, rsi
0x180084d88  mov     r8, rdi
0x180084d8b  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180084d90  nop
0x180084d91  mov     rax, rbx
0x180084d94  mov     rbx, [rsp+58h+arg_10]
0x180084d99  add     rsp, 20h
0x180084d9d  pop     r15
0x180084d9f  pop     r14
0x180084da1  pop     r13
0x180084da3  pop     r12
0x180084da5  pop     rdi
0x180084da6  pop     rsi
0x180084da7  pop     rbp
0x180084da8  retn
```
