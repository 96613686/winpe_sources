# CTitleBar::_UpdateCurrentRestoreGlyph(void)

- ea: `0x180014610`
- end: `0x180014800`
- name: `?_UpdateCurrentRestoreGlyph@CTitleBar@@AEAAXXZ`
- size: `496`
- prototype: `void __fastcall(CTitleBar *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180009e40`
- `0x18002c164`
- `0x18003d510`

## callees

- `0x1800145f0`
- `0x180014610`
- `0x180046b0c`
- `0x180072010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x180014704`
- `SHCORE!SHTaskPoolQueueTask` at `0x180014704`
- `ext-ms-win-ntuser-window-l1-1-3!IsZoomed` at `0x180014625`
- `ext-ms-win-ntuser-window-l1-1-3!IsZoomed` at `0x180014625`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CTitleBar::_UpdateCurrentRestoreGlyph(CTitleBar *this)
{
  signed __int32 i; // eax
  CTitleBar *v3; // rdi
  signed __int32 j; // eax
  unsigned int v5; // ebp
  _BYTE *v6; // rax
  _BYTE *v7; // rbx
  volatile signed __int32 *v8; // rdi
  signed __int32 k; // edx
  volatile signed __int32 *v10; // rsi
  signed __int32 m; // edx
  char v12; // [rsp+30h] [rbp-38h] BYREF

  *((_DWORD *)this + 361) = IsZoomed(*((HWND *)this + 63)) + 4;
  for ( i = *((_DWORD *)this + 25); i != 0x7FFFFFFF; i = *((_DWORD *)this + 25) )
  {
    if ( i == _InterlockedCompareExchange((volatile signed __int32 *)this + 25, i + 1, i) )
      break;
  }
  v3 = this;
  for ( j = *((_DWORD *)this + 25); j != 0x7FFFFFFF; j = *((_DWORD *)this + 25) )
  {
    if ( j == _InterlockedCompareExchange((volatile signed __int32 *)this + 25, j + 1, j) )
      break;
  }
  v5 = *((_DWORD *)this + 374);
  v6 = operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
  v7 = v6;
  if ( v6 )
  {
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IExtensionStateManager>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IExtensionStateManager>(v6);
    *(_QWORD *)v7 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *((_QWORD *)v7 + 2) = 0;
    if ( v7 + 16 != &v12 )
    {
      *((_QWORD *)v7 + 2) = this;
      v3 = 0;
    }
    *(_QWORD *)v7 = &off_180073178;
  }
  else
  {
    v7 = 0;
  }
  SHTaskPoolQueueTask(0, 2, v5, 0);
  if ( v7 )
    (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v7 + 16LL))(v7);
  if ( v3 )
  {
    v8 = (volatile signed __int32 *)((char *)v3 + 16);
    for ( k = *((_DWORD *)v8 + 21); k != 0x7FFFFFFF; k = *((_DWORD *)v8 + 21) )
    {
      if ( k == _InterlockedCompareExchange(v8 + 21, k - 1, k) )
        break;
    }
    if ( k == 1 )
    {
      if ( v8 )
        (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v8 + 40LL))(v8, 1);
      if ( Microsoft::WRL::Details::ModuleBase::module_ )
        (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                             + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
    }
  }
  v10 = (volatile signed __int32 *)((char *)this + 16);
  for ( m = *((_DWORD *)v10 + 21); m != 0x7FFFFFFF; m = *((_DWORD *)v10 + 21) )
  {
    if ( m == _InterlockedCompareExchange(v10 + 21, m - 1, m) )
      break;
  }
  if ( m == 1 )
  {
    if ( v10 )
      (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v10 + 40LL))(v10, 1);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
  }
}

```

## disassembly

```asm
0x180014610  push    rbx
0x180014612  push    rbp
0x180014613  push    rsi
0x180014614  push    rdi
0x180014615  push    r14
0x180014617  sub     rsp, 40h
0x18001461b  mov     rsi, rcx
0x18001461e  mov     rcx, [rcx+1F8h]; hWnd
0x180014625  call    cs:__imp_IsZoomed
0x18001462b  xor     r14d, r14d
0x18001462e  mov     ecx, r14d
0x180014631  test    eax, eax
0x180014633  setnz   cl
0x180014636  add     ecx, 4
0x180014639  mov     [rsi+5A4h], ecx
0x18001463f  mov     eax, [rsi+64h]
0x180014642  cmp     eax, 7FFFFFFFh
0x180014647  jz      short loc_18001465D
0x180014649  lea     ecx, [rax+1]
0x18001464c  lock cmpxchg [rsi+64h], ecx
0x180014651  jz      short loc_18001465D
0x180014653  mov     eax, [rsi+64h]
0x180014656  cmp     eax, 7FFFFFFFh
0x18001465b  jnz     short loc_180014649
0x18001465d  mov     rdi, rsi
0x180014660  mov     eax, [rsi+64h]
0x180014663  cmp     eax, 7FFFFFFFh
0x180014668  jz      short loc_18001467E
0x18001466a  lea     ecx, [rax+1]
0x18001466d  lock cmpxchg [rsi+64h], ecx
0x180014672  jz      short loc_18001467E
0x180014674  mov     eax, [rsi+64h]
0x180014677  cmp     eax, 7FFFFFFFh
0x18001467c  jnz     short loc_18001466A
0x18001467e  mov     ebp, [rsi+5D8h]
0x180014684  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001468b  mov     ecx, 18h; unsigned __int64
0x180014690  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180014695  mov     rbx, rax
0x180014698  test    rax, rax
0x18001469b  jz      loc_1800147F8
0x1800146a1  mov     rcx, rax
0x1800146a4  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIExtensionStateManager@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IExtensionStateManager>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IExtensionStateManager>(void)
0x1800146a9  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIComPoolTask@Internal@Windows@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::`vftable'
0x1800146b0  mov     [rbx], rcx
0x1800146b3  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800146ba  test    rcx, rcx
0x1800146bd  jz      short loc_1800146CC
0x1800146bf  mov     rax, [rcx]
0x1800146c2  mov     rax, [rax+8]
0x1800146c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800146cb  nop
0x1800146cc  lea     rax, [rbx+10h]
0x1800146d0  mov     [rax], r14
0x1800146d3  lea     rcx, [rsp+68h+var_38]
0x1800146d8  cmp     rax, rcx
0x1800146db  jz      short loc_1800146E3
0x1800146dd  mov     [rax], rsi
0x1800146e0  mov     rdi, r14
0x1800146e3  lea     rax, off_180073178
0x1800146ea  mov     [rbx], rax
0x1800146ed  mov     [rsp+68h+var_40], r14
0x1800146f2  mov     [rsp+68h+var_48], rbx
0x1800146f7  xor     r9d, r9d
0x1800146fa  mov     r8d, ebp
0x1800146fd  mov     edx, 2
0x180014702  xor     ecx, ecx
0x180014704  call    cs:__imp_SHTaskPoolQueueTask
0x18001470a  nop
0x18001470b  test    rbx, rbx
0x18001470e  jz      short loc_180014720
0x180014710  mov     rax, [rbx]
0x180014713  mov     rcx, rbx
0x180014716  mov     rax, [rax+10h]
0x18001471a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001471f  nop
0x180014720  test    rdi, rdi
0x180014723  jz      short loc_180014747
0x180014725  add     rdi, 10h
0x180014729  mov     edx, [rdi+54h]
0x18001472c  cmp     edx, 7FFFFFFFh
0x180014732  jz      short loc_180014740
0x180014734  lea     ecx, [rdx-1]
0x180014737  mov     eax, edx
0x180014739  lock cmpxchg [rdi+54h], ecx
0x18001473e  jnz     short loc_180014774
0x180014740  lea     eax, [rdx-1]
0x180014743  test    eax, eax
0x180014745  jz      short loc_18001478E
0x180014747  add     rsi, 10h
0x18001474b  mov     edx, [rsi+54h]
0x18001474e  cmp     edx, 7FFFFFFFh
0x180014754  jz      short loc_180014762
0x180014756  lea     ecx, [rdx-1]
0x180014759  mov     eax, edx
0x18001475b  lock cmpxchg [rsi+54h], ecx
0x180014760  jnz     short loc_180014781
0x180014762  lea     eax, [rdx-1]
0x180014765  test    eax, eax
0x180014767  jz      short loc_1800147AD
0x180014769  add     rsp, 40h
0x18001476d  pop     r14
0x18001476f  pop     rdi
0x180014770  pop     rsi
0x180014771  pop     rbp
0x180014772  pop     rbx
0x180014773  retn
0x180014774  mov     edx, [rdi+54h]
0x180014777  cmp     edx, 7FFFFFFFh
0x18001477d  jnz     short loc_180014734
0x18001477f  jmp     short loc_180014740
0x180014781  mov     edx, [rsi+54h]
0x180014784  cmp     edx, 7FFFFFFFh
0x18001478a  jnz     short loc_180014756
0x18001478c  jmp     short loc_180014762
0x18001478e  test    rdi, rdi
0x180014791  jnz     short loc_1800147CC
0x180014793  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18001479a  test    rcx, rcx
0x18001479d  jz      short loc_180014747
0x18001479f  mov     rax, [rcx]
0x1800147a2  mov     rax, [rax+10h]
0x1800147a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147ab  jmp     short loc_180014747
0x1800147ad  test    rsi, rsi
0x1800147b0  jnz     short loc_1800147E2
0x1800147b2  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800147b9  test    rcx, rcx
0x1800147bc  jz      short loc_180014769
0x1800147be  mov     rax, [rcx]
0x1800147c1  mov     rax, [rax+10h]
0x1800147c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147ca  jmp     short loc_180014769
0x1800147cc  mov     rax, [rdi]
0x1800147cf  mov     edx, 1
0x1800147d4  mov     rcx, rdi
0x1800147d7  mov     rax, [rax+28h]
0x1800147db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147e0  jmp     short loc_180014793
0x1800147e2  mov     rax, [rsi]
0x1800147e5  mov     edx, 1
0x1800147ea  mov     rcx, rsi
0x1800147ed  mov     rax, [rax+28h]
0x1800147f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147f6  jmp     short loc_1800147B2
0x1800147f8  mov     rbx, r14
0x1800147fb  jmp     loc_1800146ED
```
