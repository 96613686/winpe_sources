# Microsoft::WRL::Details::Make<CLicensingUIPopupCommand,HINSTANCE__ * &,long (*)(IPopupWindow *,IPopupCommand *,void *),void *,uint &,uint &>(HINSTANCE__ * &,long (*&&)(IPopupWindow *,IPopupCommand *,void *),void * &&,uint &,uint &)

- ea: `0x18000a1fc`
- end: `0x18000a2c5`
- name: `??$Make@VCLicensingUIPopupCommand@@AEAPEAUHINSTANCE__@@P6AJPEAUIPopupWindow@@PEAUIPopupCommand@@PEAX@ZPEAXAEAIAEAI@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCLicensingUIPopupCommand@@@12@AEAPEAUHINSTANCE__@@$$QEAP6AJPEAUIPopupWindow@@PEAUIPopupCommand@@PEAX@Z$$QEAPEAXAEAI6@Z`
- size: `201`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 *, __int64 *, __int64 *, int *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a620`

## callees

- `0x180001ea8`
- `0x18000a1fc`
- `0x180023010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::Details::Make<CLicensingUIPopupCommand,HINSTANCE__ * &,long (*)(IPopupWindow *,IPopupCommand *,void *),void *,unsigned int &,unsigned int &>(
        _QWORD *a1,
        __int64 *a2,
        __int64 *a3,
        __int64 *a4,
        int *a5,
        int *a6)
{
  _DWORD *v10; // rax
  _DWORD *v11; // rbx
  __int64 v12; // r14
  __int64 v13; // r15
  __int64 v14; // r12
  struct Microsoft::WRL::Details::ModuleBase *v15; // rcx
  int v16; // esi
  int v17; // ebp

  *a1 = 0;
  v10 = operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v10;
  if ( v10 )
  {
    v12 = *a4;
    v13 = *a3;
    v14 = *a2;
    v15 = Microsoft::WRL::Details::ModuleBase::module_;
    v16 = *a6;
    v17 = *a5;
    v10[3] = 1;
    *(_QWORD *)v10 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IPopupCommand>::`vftable';
    if ( v15 )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v15 + 8LL))(v15);
    *((_QWORD *)v11 + 2) = v14;
    *(_QWORD *)v11 = &CLicensingUIPopupCommand::`vftable';
    *((_QWORD *)v11 + 3) = v13;
    *((_QWORD *)v11 + 4) = v12;
    v11[10] = v17;
    v11[11] = v16;
    if ( *a1 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
    *a1 = v11;
  }
  return a1;
}

```

## disassembly

```asm
0x18000a1fc  push    rbx
0x18000a1fe  push    rbp
0x18000a1ff  push    rsi
0x18000a200  push    rdi
0x18000a201  push    r12
0x18000a203  push    r14
0x18000a205  push    r15
0x18000a207  sub     rsp, 20h
0x18000a20b  mov     r12, rdx
0x18000a20e  mov     qword ptr [rcx], 0
0x18000a215  mov     rdi, rcx
0x18000a218  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a21f  mov     ecx, 30h ; '0'; unsigned __int64
0x18000a224  mov     r14, r9
0x18000a227  mov     r15, r8
0x18000a22a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a22f  mov     rbx, rax
0x18000a232  test    rax, rax
0x18000a235  jz      short loc_18000A2B3
0x18000a237  mov     r14, [r14]
0x18000a23a  mov     r15, [r15]
0x18000a23d  mov     r12, [r12]
0x18000a241  mov     r10, [rsp+58h+arg_28]
0x18000a249  mov     r8, [rsp+58h+arg_20]
0x18000a251  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000a258  mov     esi, [r10]
0x18000a25b  mov     ebp, [r8]
0x18000a25e  mov     dword ptr [rax+0Ch], 1
0x18000a265  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIPopupCommand@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IPopupCommand>::`vftable'
0x18000a26c  mov     [rbx], rax
0x18000a26f  test    rcx, rcx
0x18000a272  jz      short loc_18000A280
0x18000a274  mov     rax, [rcx]
0x18000a277  mov     rax, [rax+8]
0x18000a27b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a280  lea     rax, ??_7CLicensingUIPopupCommand@@6B@; const CLicensingUIPopupCommand::`vftable'
0x18000a287  mov     [rbx+10h], r12
0x18000a28b  mov     [rbx], rax
0x18000a28e  mov     [rbx+18h], r15
0x18000a292  mov     [rbx+20h], r14
0x18000a296  mov     [rbx+28h], ebp
0x18000a299  mov     [rbx+2Ch], esi
0x18000a29c  mov     rcx, [rdi]
0x18000a29f  test    rcx, rcx
0x18000a2a2  jz      short loc_18000A2B0
0x18000a2a4  mov     rax, [rcx]
0x18000a2a7  mov     rax, [rax+10h]
0x18000a2ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2b0  mov     [rdi], rbx
0x18000a2b3  mov     rax, rdi
0x18000a2b6  add     rsp, 20h
0x18000a2ba  pop     r15
0x18000a2bc  pop     r14
0x18000a2be  pop     r12
0x18000a2c0  pop     rdi
0x18000a2c1  pop     rsi
0x18000a2c2  pop     rbp
0x18000a2c3  pop     rbx
0x18000a2c4  retn
```
