# ContainerManagerApi::UnmapAllNamedPipesFromContainer(std::unique_ptr<ContainerManagerApi::UnmapPipeContainerActivityContext,std::default_delete<ContainerManagerApi::UnmapPipeContainerActivityContext>>)

- ea: `0x180022680`
- end: `0x1800227e4`
- name: `?UnmapAllNamedPipesFromContainer@ContainerManagerApi@@CAXV?$unique_ptr@UUnmapPipeContainerActivityContext@ContainerManagerApi@@U?$default_delete@UUnmapPipeContainerActivityContext@ContainerManagerApi@@@std@@@std@@@Z`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800800f0`

## callees

- `0x180007344`
- `0x180018868`
- `0x180022680`
- `0x1800227ec`
- `0x180022840`
- `0x180031540`
- `0x18005d9d0`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x1800226fa`
- `msvcp_win!_Mtx_unlock` at `0x1800226fa`
- `api-ms-win-containers-cmclient-l1-1-0!CmsUnmapNamedPipeFromContainer` at `0x180022760`
- `api-ms-win-containers-cmclient-l1-1-0!CmsUnmapNamedPipeFromContainer` at `0x180022760`

## string_xrefs

- `0x180022775`: `onecore\windows\accessibletech\common\containermanagerapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall ContainerManagerApi::UnmapAllNamedPipesFromContainer(_QWORD *a1)
{
  __int64 v2; // r14
  __int64 v3; // rbx
  _QWORD *v4; // r12
  _QWORD *v5; // rsi
  _QWORD *v6; // rdx
  int v7; // eax
  __int64 v9; // [rsp+20h] [rbp-68h] BYREF
  std::_Ref_count_base *v10; // [rsp+28h] [rbp-60h]
  __int128 v11; // [rsp+30h] [rbp-58h] BYREF
  __int64 v12; // [rsp+40h] [rbp-48h]
  __int128 v13; // [rsp+48h] [rbp-40h] BYREF
  __int64 v14; // [rsp+58h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v11 = 0;
  v12 = 0;
  std::weak_ptr<INamedPipeChannel>::lock(*a1, &v9);
  v2 = v9;
  if ( v9 )
  {
    std::_Mutex_base::lock((std::_Mutex_base *)(v9 + 24));
    v3 = *(_QWORD *)(v2 + 16);
    *(_QWORD *)(v2 + 16) = 0;
    v4 = *(_QWORD **)(v2 + 8);
    *(_QWORD *)(v2 + 8) = 0;
    v5 = *(_QWORD **)v2;
    *(_QWORD *)v2 = 0;
    *(_BYTE *)(v2 + 104) = 0;
    _Mtx_unlock((_Mtx_t)(v2 + 24));
    std::vector<std::wstring>::_Tidy(&v11);
    *(_QWORD *)&v11 = v5;
    *((_QWORD *)&v11 + 1) = v4;
    v12 = v3;
    v13 = 0;
    v14 = 0;
    std::vector<std::wstring>::_Tidy(&v13);
    if ( v10 )
      std::_Ref_count_base::_Decref(v10);
    while ( v5 != v4 )
    {
      if ( v5[3] <= 7u )
        v6 = v5;
      else
        v6 = (_QWORD *)*v5;
      v7 = CmsUnmapNamedPipeFromContainer(*(_QWORD *)(*a1 + 24LL), v6);
      if ( v7 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x98,
          (unsigned int)"onecore\\windows\\accessibletech\\common\\containermanagerapi.cpp",
          (const char *)(unsigned int)v7,
          v9);
      v5 += 4;
    }
  }
  else if ( v10 )
  {
    std::_Ref_count_base::_Decref(v10);
  }
  std::vector<std::wstring>::_Tidy(&v11);
  return std::unique_ptr<ContainerManagerApi::UnmapPipeContainerActivityContext>::~unique_ptr<ContainerManagerApi::UnmapPipeContainerActivityContext>(a1);
}

```

## disassembly

```asm
0x180022680  mov     rax, rsp
0x180022683  mov     [rax+18h], rbx
0x180022687  mov     [rax+8], rcx
0x18002268b  push    rsi
0x18002268c  push    rdi
0x18002268d  push    r12
0x18002268f  push    r14
0x180022691  push    r15
0x180022693  sub     rsp, 60h
0x180022697  mov     rdi, rcx
0x18002269a  xorps   xmm0, xmm0
0x18002269d  movdqu  xmmword ptr [rax-58h], xmm0
0x1800226a2  mov     qword ptr [rax-48h], 0
0x1800226aa  lea     rdx, [rax-68h]
0x1800226ae  mov     rcx, [rcx]
0x1800226b1  call    ?lock@?$weak_ptr@UINamedPipeChannel@@@std@@QEBA?AV?$shared_ptr@UINamedPipeChannel@@@2@XZ; std::weak_ptr<INamedPipeChannel>::lock(void)
0x1800226b6  nop
0x1800226b7  mov     r14, [rsp+88h+var_68]
0x1800226bc  test    r14, r14
0x1800226bf  jz      loc_180022799
0x1800226c5  lea     rcx, [r14+18h]; this
0x1800226c9  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800226ce  mov     rbx, [r14+10h]
0x1800226d2  mov     qword ptr [r14+10h], 0
0x1800226da  mov     r12, [r14+8]
0x1800226de  mov     qword ptr [r14+8], 0
0x1800226e6  mov     rsi, [r14]
0x1800226e9  mov     qword ptr [r14], 0
0x1800226f0  xor     eax, eax
0x1800226f2  xchg    al, [r14+68h]
0x1800226f6  lea     rcx, [r14+18h]; _Mtx_t
0x1800226fa  call    cs:__imp__Mtx_unlock
0x180022700  lea     rcx, [rsp+88h+var_58]
0x180022705  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18002270a  mov     [rsp+88h+var_58], rsi
0x18002270f  mov     [rsp+88h+var_50], r12
0x180022714  mov     [rsp+88h+var_48], rbx
0x180022719  xorps   xmm0, xmm0
0x18002271c  movdqu  [rsp+88h+var_40], xmm0
0x180022722  mov     [rsp+88h+var_30], 0
0x18002272b  lea     rcx, [rsp+88h+var_40]
0x180022730  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180022735  nop
0x180022736  mov     rcx, [rsp+88h+var_60]; this
0x18002273b  test    rcx, rcx
0x18002273e  jz      short loc_180022745
0x180022740  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180022745  cmp     rsi, r12
0x180022748  jz      short loc_18002278C
0x18002274a  cmp     qword ptr [rsi+18h], 7
0x18002274f  jbe     short loc_180022756
0x180022751  mov     rdx, [rsi]
0x180022754  jmp     short loc_180022759
0x180022756  mov     rdx, rsi
0x180022759  mov     rcx, [rdi]
0x18002275c  mov     rcx, [rcx+18h]
0x180022760  call    cs:__imp_CmsUnmapNamedPipeFromContainer
0x180022766  mov     rcx, [rsp+88h]; this
0x18002276e  test    eax, eax
0x180022770  jns     short loc_180022786
0x180022772  mov     r9d, eax; char *
0x180022775  lea     r8, aOnecoreWindows_19; "onecore\\windows\\accessibletech\\commo"...
0x18002277c  mov     edx, 98h; void *
0x180022781  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180022786  add     rsi, 20h ; ' '
0x18002278a  jmp     short loc_180022745
0x18002278c  lea     rcx, [rsp+88h+var_58]
0x180022791  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180022796  nop
0x180022797  jmp     short loc_1800227C6
0x180022799  mov     rcx, [rsp+88h+var_60]; this
0x18002279e  test    rcx, rcx
0x1800227a1  jz      short loc_1800227A9
0x1800227a3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800227a8  nop
0x1800227a9  lea     rcx, [rsp+88h+var_58]
0x1800227ae  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800227b3  nop
0x1800227b4  mov     rcx, rdi
0x1800227b7  call    ??1?$unique_ptr@UUnmapPipeContainerActivityContext@ContainerManagerApi@@U?$default_delete@UUnmapPipeContainerActivityContext@ContainerManagerApi@@@std@@@std@@QEAA@XZ; std::unique_ptr<ContainerManagerApi::UnmapPipeContainerActivityContext>::~unique_ptr<ContainerManagerApi::UnmapPipeContainerActivityContext>(void)
0x1800227bc  jmp     short loc_1800227CF
0x1800227be  mov     rdi, [rsp+88h+arg_0]
0x1800227c6  mov     rcx, rdi
0x1800227c9  call    ??1?$unique_ptr@UUnmapPipeContainerActivityContext@ContainerManagerApi@@U?$default_delete@UUnmapPipeContainerActivityContext@ContainerManagerApi@@@std@@@std@@QEAA@XZ; std::unique_ptr<ContainerManagerApi::UnmapPipeContainerActivityContext>::~unique_ptr<ContainerManagerApi::UnmapPipeContainerActivityContext>(void)
0x1800227ce  nop
0x1800227cf  mov     rbx, [rsp+88h+arg_10]
0x1800227d7  add     rsp, 60h
0x1800227db  pop     r15
0x1800227dd  pop     r14
0x1800227df  pop     r12
0x1800227e1  pop     rdi
0x1800227e2  pop     rsi
0x1800227e3  retn
```
