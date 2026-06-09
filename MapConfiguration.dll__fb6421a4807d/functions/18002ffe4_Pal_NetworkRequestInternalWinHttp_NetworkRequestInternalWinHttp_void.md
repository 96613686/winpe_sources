# Pal::NetworkRequestInternalWinHttp::~NetworkRequestInternalWinHttp(void)

- ea: `0x18002ffe4`
- end: `0x1800300fc`
- name: `??1NetworkRequestInternalWinHttp@Pal@@UEAA@XZ`
- size: `280`
- prototype: `void __fastcall(Pal::NetworkRequestInternalWinHttp *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180030490`

## callees

- `0x18000c354`
- `0x180010e68`
- `0x180011500`
- `0x180013da8`
- `0x180013de0`
- `0x180014cd8`
- `0x18002ffe4`
- `0x180031c68`
- `0x180032728`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180030080`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180030080`
- `WINHTTP!WinHttpCloseHandle` at `0x18003004d`
- `WINHTTP!WinHttpCloseHandle` at `0x18003004d`

## pseudocode

```c
void __fastcall Pal::NetworkRequestInternalWinHttp::~NetworkRequestInternalWinHttp(
        Pal::NetworkRequestInternalWinHttp *this)
{
  void *v2; // rcx
  std::_Ref_count_base *v3; // rcx
  std::_Ref_count_base *v4; // rcx
  __int64 v5; // [rsp+30h] [rbp-18h]
  std::_Ref_count_base *v6; // [rsp+38h] [rbp-10h]

  *(_QWORD *)this = &Pal::NetworkRequestInternalWinHttp::`vftable';
  Pal::NetworkRequestInternalWinHttp::closeHttpHandles(this);
  Pal::Lockable<std::shared_ptr<Pal::UntypedAsyncOperation>>::replace((LPCRITICAL_SECTION)this + 1);
  if ( v5 )
    (*(void (__fastcall **)())(*(_QWORD *)v5 + 8LL))();
  v2 = (void *)*((_QWORD *)this + 19);
  if ( v2 )
  {
    WinHttpCloseHandle(v2);
    *((_QWORD *)this + 19) = 0;
  }
  if ( v6 )
    std::_Ref_count_base::_Decref(v6);
  std::_Func_class<void,>::_Tidy((char *)this + 400);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 352));
  std::wstring::_Tidy_deallocate((char *)this + 312);
  v3 = (std::_Ref_count_base *)*((_QWORD *)this + 38);
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  std::wstring::_Tidy_deallocate((char *)this + 256);
  std::wstring::_Tidy_deallocate((char *)this + 224);
  Pal::Lockable<std::shared_ptr<Pal::NetworkRequestInternalWinHttp>>::~Lockable<std::shared_ptr<Pal::NetworkRequestInternalWinHttp>>((char *)this + 168);
  Pal::Lockable<std::shared_ptr<Pal::NetworkRequestInternalWinHttp>>::~Lockable<std::shared_ptr<Pal::NetworkRequestInternalWinHttp>>((char *)this + 96);
  Pal::Lockable<std::shared_ptr<Pal::NetworkRequestInternalWinHttp>>::~Lockable<std::shared_ptr<Pal::NetworkRequestInternalWinHttp>>((char *)this + 40);
  std::unique_ptr<std::vector<unsigned char>>::~unique_ptr<std::vector<unsigned char>>((char *)this + 24);
  v4 = (std::_Ref_count_base *)*((_QWORD *)this + 2);
  if ( v4 )
    std::_Ref_count_base::_Decwref(v4);
}

```

## disassembly

```asm
0x18002ffe4  mov     [rsp+arg_0], rbx
0x18002ffe9  push    rdi
0x18002ffea  sub     rsp, 40h
0x18002ffee  mov     rbx, rcx
0x18002fff1  lea     rax, ??_7NetworkRequestInternalWinHttp@Pal@@6B@; const Pal::NetworkRequestInternalWinHttp::`vftable'
0x18002fff8  mov     [rcx], rax
0x18002fffb  call    ?closeHttpHandles@NetworkRequestInternalWinHttp@Pal@@AEAAXXZ; Pal::NetworkRequestInternalWinHttp::closeHttpHandles(void)
0x180030000  xorps   xmm0, xmm0
0x180030003  movdqu  xmmword ptr [rsp+48h+var_28], xmm0
0x180030009  lea     r8, [rsp+48h+var_28]
0x18003000e  lea     rdx, [rsp+48h+var_18]
0x180030013  lea     rcx, [rbx+28h]; lpCriticalSection
0x180030017  call    ?replace@?$Lockable@V?$shared_ptr@VUntypedAsyncOperation@Pal@@@std@@@Pal@@QEAA?AV?$shared_ptr@VUntypedAsyncOperation@Pal@@@std@@$$QEAV34@@Z; Pal::Lockable<std::shared_ptr<Pal::UntypedAsyncOperation>>::replace(std::shared_ptr<Pal::UntypedAsyncOperation> &&)
0x18003001c  mov     rcx, [rsp+48h+var_28+8]; this
0x180030021  test    rcx, rcx
0x180030024  jz      short loc_18003002B
0x180030026  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003002b  mov     rcx, [rsp+48h+var_18]
0x180030030  test    rcx, rcx
0x180030033  jz      short loc_180030041
0x180030035  mov     rax, [rcx]
0x180030038  mov     rax, [rax+8]
0x18003003c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030041  mov     rcx, [rbx+98h]; hInternet
0x180030048  test    rcx, rcx
0x18003004b  jz      short loc_18003005E
0x18003004d  call    cs:__imp_WinHttpCloseHandle
0x180030053  mov     qword ptr [rbx+98h], 0
0x18003005e  mov     rcx, [rsp+48h+var_10]; this
0x180030063  test    rcx, rcx
0x180030066  jz      short loc_18003006D
0x180030068  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003006d  lea     rcx, [rbx+190h]
0x180030074  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x180030079  lea     rcx, [rbx+160h]; lpCriticalSection
0x180030080  call    cs:__imp_DeleteCriticalSection
0x180030086  lea     rcx, [rbx+138h]
0x18003008d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180030092  mov     rcx, [rbx+130h]; this
0x180030099  test    rcx, rcx
0x18003009c  jz      short loc_1800300A3
0x18003009e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800300a3  lea     rcx, [rbx+100h]
0x1800300aa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800300af  lea     rcx, [rbx+0E0h]
0x1800300b6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800300bb  lea     rcx, [rbx+0A8h]
0x1800300c2  call    ??1?$Lockable@V?$shared_ptr@VNetworkRequestInternalWinHttp@Pal@@@std@@@Pal@@QEAA@XZ; Pal::Lockable<std::shared_ptr<Pal::NetworkRequestInternalWinHttp>>::~Lockable<std::shared_ptr<Pal::NetworkRequestInternalWinHttp>>(void)
0x1800300c7  lea     rcx, [rbx+60h]
0x1800300cb  call    ??1?$Lockable@V?$shared_ptr@VNetworkRequestInternalWinHttp@Pal@@@std@@@Pal@@QEAA@XZ; Pal::Lockable<std::shared_ptr<Pal::NetworkRequestInternalWinHttp>>::~Lockable<std::shared_ptr<Pal::NetworkRequestInternalWinHttp>>(void)
0x1800300d0  lea     rcx, [rbx+28h]
0x1800300d4  call    ??1?$Lockable@V?$shared_ptr@VNetworkRequestInternalWinHttp@Pal@@@std@@@Pal@@QEAA@XZ; Pal::Lockable<std::shared_ptr<Pal::NetworkRequestInternalWinHttp>>::~Lockable<std::shared_ptr<Pal::NetworkRequestInternalWinHttp>>(void)
0x1800300d9  lea     rcx, [rbx+18h]
0x1800300dd  call    ??1?$unique_ptr@V?$vector@EV?$allocator@E@std@@@std@@U?$default_delete@V?$vector@EV?$allocator@E@std@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::vector<uchar>>::~unique_ptr<std::vector<uchar>>(void)
0x1800300e2  mov     rcx, [rbx+10h]; this
0x1800300e6  test    rcx, rcx
0x1800300e9  jz      short loc_1800300F1
0x1800300eb  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x1800300f0  nop
0x1800300f1  mov     rbx, [rsp+48h+arg_0]
0x1800300f6  add     rsp, 40h
0x1800300fa  pop     rdi
0x1800300fb  retn
```
