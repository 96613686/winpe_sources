# ContainerManagerApi::RemoveNamedPipeInternal(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180022484`
- end: `0x18002259a`
- name: `?RemoveNamedPipeInternal@ContainerManagerApi@@AEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180080300`

## callees

- `0x180007344`
- `0x180018868`
- `0x180022484`
- `0x1800225a0`
- `0x1800225e4`
- `0x180022840`
- `0x180022870`
- `0x180031540`
- `0x18005d9d0`
- `0x18007f708`
- `0x18007f734`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x1800224e9`
- `msvcp_win!_Mtx_unlock` at `0x1800224e9`
- `api-ms-win-containers-cmclient-l1-2-0!CmsStartActivityAsync` at `0x180022540`
- `api-ms-win-containers-cmclient-l1-2-0!CmsStartActivityAsync` at `0x180022540`

## string_xrefs

- `0x180022551`: `onecore\windows\accessibletech\common\containermanagerapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall ContainerManagerApi::RemoveNamedPipeInternal(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rbx
  int started; // eax
  _QWORD v9[2]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v10; // [rsp+30h] [rbp-18h] BYREF
  std::_Ref_count_base *v11; // [rsp+38h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+30h]
  __int64 v13; // [rsp+80h] [rbp+38h] BYREF

  std::weak_ptr<INamedPipeChannel>::lock(a1 + 24, &v10);
  v4 = v10;
  if ( v10 )
  {
    v13 = v10 + 24;
    std::_Mutex_base::lock((std::_Mutex_base *)(v10 + 24));
    v5 = *(_QWORD *)(v4 + 8);
    if ( v5 == *(_QWORD *)(v4 + 16) )
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(v4, v5, a2);
    else
      std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring const &>(v4, a2);
    _Mtx_unlock((_Mtx_t)(v4 + 24));
    if ( !*(_BYTE *)(v4 + 104) )
    {
      ContainerManagerApi::GetContainerActivity(a1, v9, v6, 0x2712u);
      if ( !_InterlockedCompareExchange8((volatile signed __int8 *)(v4 + 104), 1, 0) )
      {
        v7 = v9[1];
        std::make_unique<ContainerManagerApi::UnmapPipeContainerActivityContext,std::weak_ptr<ContainerManagerApi::UnmapPipeDataManager> &,ContainerManagerApi::ContainerActivityGuard,0>(
          &v13,
          a1 + 24,
          v9);
        started = CmsStartActivityAsync(v7, ContainerManagerApi::UnmapNamedPipesActivityNotificationCallback, v13);
        if ( started < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xE5,
            (unsigned int)"onecore\\windows\\accessibletech\\common\\containermanagerapi.cpp",
            (const char *)(unsigned int)started,
            v9[0]);
        v13 = 0;
        std::unique_ptr<ContainerManagerApi::UnmapPipeContainerActivityContext>::~unique_ptr<ContainerManagerApi::UnmapPipeContainerActivityContext>(&v13);
      }
      ContainerManagerApi::ContainerActivityGuard::~ContainerActivityGuard((ContainerManagerApi::ContainerActivityGuard *)v9);
    }
  }
  if ( v11 )
    std::_Ref_count_base::_Decref(v11);
}

```

## disassembly

```asm
0x180022484  push    rbp
0x180022486  push    rbx
0x180022487  push    rsi
0x180022488  push    rdi
0x180022489  push    r14
0x18002248b  push    r15
0x18002248d  mov     rbp, rsp
0x180022490  sub     rsp, 48h
0x180022494  mov     rsi, rdx
0x180022497  mov     r14, rcx
0x18002249a  lea     rdx, [rbp+var_18]
0x18002249e  add     rcx, 18h
0x1800224a2  call    ?lock@?$weak_ptr@UINamedPipeChannel@@@std@@QEBA?AV?$shared_ptr@UINamedPipeChannel@@@2@XZ; std::weak_ptr<INamedPipeChannel>::lock(void)
0x1800224a7  nop
0x1800224a8  mov     rbx, [rbp+var_18]
0x1800224ac  test    rbx, rbx
0x1800224af  jz      loc_18002257F
0x1800224b5  lea     rdi, [rbx+18h]
0x1800224b9  mov     [rbp+arg_0], rdi
0x1800224bd  mov     rcx, rdi; this
0x1800224c0  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800224c5  nop
0x1800224c6  mov     rdx, [rbx+8]
0x1800224ca  mov     rcx, rbx
0x1800224cd  cmp     rdx, [rbx+10h]
0x1800224d1  jz      short loc_1800224DD
0x1800224d3  mov     rdx, rsi
0x1800224d6  call    ??$_Emplace_back_with_unused_capacity@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring const &>(std::wstring const &)
0x1800224db  jmp     short loc_1800224E6
0x1800224dd  mov     r8, rsi
0x1800224e0  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x1800224e5  nop
0x1800224e6  mov     rcx, rdi; _Mtx_t
0x1800224e9  call    cs:__imp__Mtx_unlock
0x1800224ef  mov     al, [rbx+68h]
0x1800224f2  nop
0x1800224f3  test    al, al
0x1800224f5  jnz     loc_18002257F
0x1800224fb  mov     r9d, 2712h
0x180022501  lea     rdx, [rbp+var_28]
0x180022505  mov     rcx, r14
0x180022508  call    ?GetContainerActivity@ContainerManagerApi@@QEAA?AVContainerActivityGuard@1@W4_CMS_CLIENT_ID@@W4_CMS_ACTIVITY_ID@@@Z; ContainerManagerApi::GetContainerActivity(_CMS_CLIENT_ID,_CMS_ACTIVITY_ID)
0x18002250d  nop
0x18002250e  mov     ecx, 1
0x180022513  xor     eax, eax
0x180022515  lock cmpxchg [rbx+68h], cl
0x18002251a  jnz     short loc_180022575
0x18002251c  mov     rbx, [rbp+var_20]
0x180022520  lea     r8, [rbp+var_28]
0x180022524  lea     rdx, [r14+18h]
0x180022528  lea     rcx, [rbp+arg_0]
0x18002252c  call    ??$make_unique@UUnmapPipeContainerActivityContext@ContainerManagerApi@@AEAV?$weak_ptr@VUnmapPipeDataManager@ContainerManagerApi@@@std@@VContainerActivityGuard@2@$0A@@std@@YA?AV?$unique_ptr@UUnmapPipeContainerActivityContext@ContainerManagerApi@@U?$default_delete@UUnmapPipeContainerActivityContext@ContainerManagerApi@@@std@@@0@AEAV?$weak_ptr@VUnmapPipeDataManager@ContainerManagerApi@@@0@$$QEAVContainerActivityGuard@ContainerManagerApi@@@Z; std::make_unique<ContainerManagerApi::UnmapPipeContainerActivityContext,std::weak_ptr<ContainerManagerApi::UnmapPipeDataManager> &,ContainerManagerApi::ContainerActivityGuard,0>(std::weak_ptr<ContainerManagerApi::UnmapPipeDataManager> &,ContainerManagerApi::ContainerActivityGuard &&)
0x180022531  nop
0x180022532  mov     r8, [rbp+arg_0]
0x180022536  lea     rdx, ?UnmapNamedPipesActivityNotificationCallback@ContainerManagerApi@@CAXPEAU_CMS_ACTIVITY_NOTIFICATION@@PEAX@Z; ContainerManagerApi::UnmapNamedPipesActivityNotificationCallback(_CMS_ACTIVITY_NOTIFICATION *,void *)
0x18002253d  mov     rcx, rbx
0x180022540  call    cs:__imp_CmsStartActivityAsync
0x180022546  mov     rcx, [rbp+30h]; this
0x18002254a  test    eax, eax
0x18002254c  jns     short loc_180022563
0x18002254e  mov     r9d, eax; char *
0x180022551  lea     r8, aOnecoreWindows_19; "onecore\\windows\\accessibletech\\commo"...
0x180022558  mov     edx, 0E5h; void *
0x18002255d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180022563  mov     [rbp+arg_0], 0
0x18002256b  lea     rcx, [rbp+arg_0]
0x18002256f  call    ??1?$unique_ptr@UUnmapPipeContainerActivityContext@ContainerManagerApi@@U?$default_delete@UUnmapPipeContainerActivityContext@ContainerManagerApi@@@std@@@std@@QEAA@XZ; std::unique_ptr<ContainerManagerApi::UnmapPipeContainerActivityContext>::~unique_ptr<ContainerManagerApi::UnmapPipeContainerActivityContext>(void)
0x180022574  nop
0x180022575  lea     rcx, [rbp+var_28]; this
0x180022579  call    ??1ContainerActivityGuard@ContainerManagerApi@@QEAA@XZ; ContainerManagerApi::ContainerActivityGuard::~ContainerActivityGuard(void)
0x18002257e  nop
0x18002257f  mov     rcx, [rbp+var_10]; this
0x180022583  test    rcx, rcx
0x180022586  jz      short loc_18002258D
0x180022588  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002258d  add     rsp, 48h
0x180022591  pop     r15
0x180022593  pop     r14
0x180022595  pop     rdi
0x180022596  pop     rsi
0x180022597  pop     rbx
0x180022598  pop     rbp
0x180022599  retn
```
