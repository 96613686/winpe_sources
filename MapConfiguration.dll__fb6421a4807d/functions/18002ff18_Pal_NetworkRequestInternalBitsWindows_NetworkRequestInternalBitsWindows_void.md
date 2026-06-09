# Pal::NetworkRequestInternalBitsWindows::~NetworkRequestInternalBitsWindows(void)

- ea: `0x18002ff18`
- end: `0x18002ffde`
- name: `??1NetworkRequestInternalBitsWindows@Pal@@UEAA@XZ`
- size: `198`
- prototype: `void __fastcall(Pal::NetworkRequestInternalBitsWindows *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180030450`

## callees

- `0x18000c354`
- `0x180010e68`
- `0x180013da8`
- `0x180013de0`
- `0x180014cd8`
- `0x180014de4`
- `0x18002ff18`
- `0x180032728`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002ff92`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002ff92`

## pseudocode

```c
void __fastcall Pal::NetworkRequestInternalBitsWindows::~NetworkRequestInternalBitsWindows(
        Pal::NetworkRequestInternalBitsWindows *this)
{
  std::_Ref_count_base *v2; // rcx
  std::_Ref_count_base *v3; // rcx
  __int64 v4; // [rsp+30h] [rbp-18h]
  std::_Ref_count_base *v5; // [rsp+38h] [rbp-10h]

  *(_QWORD *)this = &Pal::NetworkRequestInternalBitsWindows::`vftable';
  Pal::Lockable<std::shared_ptr<Pal::UntypedAsyncOperation>>::replace((LPCRITICAL_SECTION)((char *)this + 24));
  if ( v4 )
    (*(void (__fastcall **)())(*(_QWORD *)v4 + 8LL))();
  if ( v5 )
    std::_Ref_count_base::_Decref(v5);
  std::_Func_class<void,>::_Tidy((char *)this + 208);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 4);
  std::string::_Tidy_deallocate((char *)this + 128);
  std::wstring::_Tidy_deallocate((char *)this + 96);
  v2 = (std::_Ref_count_base *)*((_QWORD *)this + 11);
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  Pal::Lockable<std::shared_ptr<Pal::NetworkRequestInternalWinHttp>>::~Lockable<std::shared_ptr<Pal::NetworkRequestInternalWinHttp>>((char *)this + 24);
  v3 = (std::_Ref_count_base *)*((_QWORD *)this + 2);
  if ( v3 )
    std::_Ref_count_base::_Decwref(v3);
}

```

## disassembly

```asm
0x18002ff18  mov     [rsp+arg_0], rbx
0x18002ff1d  push    rdi
0x18002ff1e  sub     rsp, 40h
0x18002ff22  mov     rbx, rcx
0x18002ff25  lea     rax, ??_7NetworkRequestInternalBitsWindows@Pal@@6B@; const Pal::NetworkRequestInternalBitsWindows::`vftable'
0x18002ff2c  mov     [rcx], rax
0x18002ff2f  xorps   xmm0, xmm0
0x18002ff32  movdqu  xmmword ptr [rsp+48h+var_28], xmm0
0x18002ff38  lea     r8, [rsp+48h+var_28]
0x18002ff3d  lea     rdx, [rsp+48h+var_18]
0x18002ff42  add     rcx, 18h; lpCriticalSection
0x18002ff46  call    ?replace@?$Lockable@V?$shared_ptr@VUntypedAsyncOperation@Pal@@@std@@@Pal@@QEAA?AV?$shared_ptr@VUntypedAsyncOperation@Pal@@@std@@$$QEAV34@@Z; Pal::Lockable<std::shared_ptr<Pal::UntypedAsyncOperation>>::replace(std::shared_ptr<Pal::UntypedAsyncOperation> &&)
0x18002ff4b  mov     rcx, [rsp+48h+var_28+8]; this
0x18002ff50  test    rcx, rcx
0x18002ff53  jz      short loc_18002FF5A
0x18002ff55  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002ff5a  mov     rcx, [rsp+48h+var_18]
0x18002ff5f  test    rcx, rcx
0x18002ff62  jz      short loc_18002FF70
0x18002ff64  mov     rax, [rcx]
0x18002ff67  mov     rax, [rax+8]
0x18002ff6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ff70  mov     rcx, [rsp+48h+var_10]; this
0x18002ff75  test    rcx, rcx
0x18002ff78  jz      short loc_18002FF7F
0x18002ff7a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002ff7f  lea     rcx, [rbx+0D0h]
0x18002ff86  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x18002ff8b  lea     rcx, [rbx+0A0h]; lpCriticalSection
0x18002ff92  call    cs:__imp_DeleteCriticalSection
0x18002ff98  lea     rcx, [rbx+80h]
0x18002ff9f  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18002ffa4  lea     rcx, [rbx+60h]
0x18002ffa8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ffad  mov     rcx, [rbx+58h]; this
0x18002ffb1  test    rcx, rcx
0x18002ffb4  jz      short loc_18002FFBB
0x18002ffb6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002ffbb  lea     rcx, [rbx+18h]
0x18002ffbf  call    ??1?$Lockable@V?$shared_ptr@VNetworkRequestInternalWinHttp@Pal@@@std@@@Pal@@QEAA@XZ; Pal::Lockable<std::shared_ptr<Pal::NetworkRequestInternalWinHttp>>::~Lockable<std::shared_ptr<Pal::NetworkRequestInternalWinHttp>>(void)
0x18002ffc4  mov     rcx, [rbx+10h]; this
0x18002ffc8  test    rcx, rcx
0x18002ffcb  jz      short loc_18002FFD3
0x18002ffcd  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18002ffd2  nop
0x18002ffd3  mov     rbx, [rsp+48h+arg_0]
0x18002ffd8  add     rsp, 40h
0x18002ffdc  pop     rdi
0x18002ffdd  retn
```
