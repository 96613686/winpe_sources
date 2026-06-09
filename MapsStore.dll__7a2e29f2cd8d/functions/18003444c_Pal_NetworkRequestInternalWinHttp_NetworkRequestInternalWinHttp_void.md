# Pal::NetworkRequestInternalWinHttp::~NetworkRequestInternalWinHttp(void)

- ea: `0x18003444c`
- end: `0x180034564`
- name: `??1NetworkRequestInternalWinHttp@Pal@@UEAA@XZ`
- size: `280`
- prototype: `void __fastcall(Pal::NetworkRequestInternalWinHttp *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180034910`

## callees

- `0x180012720`
- `0x180016cbc`
- `0x18001b9e0`
- `0x18001ba18`
- `0x1800256d0`
- `0x180025bbc`
- `0x18003444c`
- `0x180036100`
- `0x180036cc8`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800344e8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800344e8`
- `WINHTTP!WinHttpCloseHandle` at `0x1800344b5`
- `WINHTTP!WinHttpCloseHandle` at `0x1800344b5`

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
  std::_Func_class<void,Pal::AsyncOperation<std::shared_ptr<std::vector<unsigned char> const>> &>::_Tidy((char *)this + 400);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 352));
  std::wstring::_Tidy_deallocate((char *)this + 312);
  v3 = (std::_Ref_count_base *)*((_QWORD *)this + 38);
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  std::wstring::_Tidy_deallocate((char *)this + 256);
  std::wstring::_Tidy_deallocate((char *)this + 224);
  Pal::Lockable<std::shared_ptr<MapControl::LocalIndex>>::~Lockable<std::shared_ptr<MapControl::LocalIndex>>((char *)this + 168);
  Pal::Lockable<std::shared_ptr<MapControl::LocalIndex>>::~Lockable<std::shared_ptr<MapControl::LocalIndex>>((char *)this + 96);
  Pal::Lockable<std::shared_ptr<MapControl::LocalIndex>>::~Lockable<std::shared_ptr<MapControl::LocalIndex>>((char *)this + 40);
  std::unique_ptr<std::vector<unsigned char>>::~unique_ptr<std::vector<unsigned char>>((char *)this + 24);
  v4 = (std::_Ref_count_base *)*((_QWORD *)this + 2);
  if ( v4 )
    std::_Ref_count_base::_Decwref(v4);
}

```

## disassembly

```asm
0x18003444c  mov     [rsp+arg_0], rbx
0x180034451  push    rdi
0x180034452  sub     rsp, 40h
0x180034456  mov     rbx, rcx
0x180034459  lea     rax, ??_7NetworkRequestInternalWinHttp@Pal@@6B@; const Pal::NetworkRequestInternalWinHttp::`vftable'
0x180034460  mov     [rcx], rax
0x180034463  call    ?closeHttpHandles@NetworkRequestInternalWinHttp@Pal@@AEAAXXZ; Pal::NetworkRequestInternalWinHttp::closeHttpHandles(void)
0x180034468  xorps   xmm0, xmm0
0x18003446b  movdqu  xmmword ptr [rsp+48h+var_28], xmm0
0x180034471  lea     r8, [rsp+48h+var_28]
0x180034476  lea     rdx, [rsp+48h+var_18]
0x18003447b  lea     rcx, [rbx+28h]; lpCriticalSection
0x18003447f  call    ?replace@?$Lockable@V?$shared_ptr@VUntypedAsyncOperation@Pal@@@std@@@Pal@@QEAA?AV?$shared_ptr@VUntypedAsyncOperation@Pal@@@std@@$$QEAV34@@Z; Pal::Lockable<std::shared_ptr<Pal::UntypedAsyncOperation>>::replace(std::shared_ptr<Pal::UntypedAsyncOperation> &&)
0x180034484  mov     rcx, [rsp+48h+var_28+8]; this
0x180034489  test    rcx, rcx
0x18003448c  jz      short loc_180034493
0x18003448e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180034493  mov     rcx, [rsp+48h+var_18]
0x180034498  test    rcx, rcx
0x18003449b  jz      short loc_1800344A9
0x18003449d  mov     rax, [rcx]
0x1800344a0  mov     rax, [rax+8]
0x1800344a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800344a9  mov     rcx, [rbx+98h]; hInternet
0x1800344b0  test    rcx, rcx
0x1800344b3  jz      short loc_1800344C6
0x1800344b5  call    cs:__imp_WinHttpCloseHandle
0x1800344bb  mov     qword ptr [rbx+98h], 0
0x1800344c6  mov     rcx, [rsp+48h+var_10]; this
0x1800344cb  test    rcx, rcx
0x1800344ce  jz      short loc_1800344D5
0x1800344d0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800344d5  lea     rcx, [rbx+190h]
0x1800344dc  call    ?_Tidy@?$_Func_class@XAEAV?$AsyncOperation@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@@Pal@@@std@@IEAAXXZ; std::_Func_class<void,Pal::AsyncOperation<std::shared_ptr<std::vector<uchar> const>> &>::_Tidy(void)
0x1800344e1  lea     rcx, [rbx+160h]; lpCriticalSection
0x1800344e8  call    cs:__imp_DeleteCriticalSection
0x1800344ee  lea     rcx, [rbx+138h]
0x1800344f5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800344fa  mov     rcx, [rbx+130h]; this
0x180034501  test    rcx, rcx
0x180034504  jz      short loc_18003450B
0x180034506  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003450b  lea     rcx, [rbx+100h]
0x180034512  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034517  lea     rcx, [rbx+0E0h]
0x18003451e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034523  lea     rcx, [rbx+0A8h]
0x18003452a  call    ??1?$Lockable@V?$shared_ptr@VLocalIndex@MapControl@@@std@@@Pal@@QEAA@XZ; Pal::Lockable<std::shared_ptr<MapControl::LocalIndex>>::~Lockable<std::shared_ptr<MapControl::LocalIndex>>(void)
0x18003452f  lea     rcx, [rbx+60h]
0x180034533  call    ??1?$Lockable@V?$shared_ptr@VLocalIndex@MapControl@@@std@@@Pal@@QEAA@XZ; Pal::Lockable<std::shared_ptr<MapControl::LocalIndex>>::~Lockable<std::shared_ptr<MapControl::LocalIndex>>(void)
0x180034538  lea     rcx, [rbx+28h]
0x18003453c  call    ??1?$Lockable@V?$shared_ptr@VLocalIndex@MapControl@@@std@@@Pal@@QEAA@XZ; Pal::Lockable<std::shared_ptr<MapControl::LocalIndex>>::~Lockable<std::shared_ptr<MapControl::LocalIndex>>(void)
0x180034541  lea     rcx, [rbx+18h]
0x180034545  call    ??1?$unique_ptr@V?$vector@EV?$allocator@E@std@@@std@@U?$default_delete@V?$vector@EV?$allocator@E@std@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::vector<uchar>>::~unique_ptr<std::vector<uchar>>(void)
0x18003454a  mov     rcx, [rbx+10h]; this
0x18003454e  test    rcx, rcx
0x180034551  jz      short loc_180034559
0x180034553  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180034558  nop
0x180034559  mov     rbx, [rsp+48h+arg_0]
0x18003455e  add     rsp, 40h
0x180034562  pop     rdi
0x180034563  retn
```
