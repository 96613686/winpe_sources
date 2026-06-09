# boost::_anonymous_namespace_::run_thread_exit_callbacks

- ea: `0x1800059e0`
- end: `0x180005b59`
- name: `boost::_anonymous_namespace_::run_thread_exit_callbacks`
- size: `377`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005890`

## callees

- `0x180004d20`
- `0x180005220`
- `0x1800059e0`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005a6f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005a83`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005b35`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005a6f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005a83`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005b35`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005a7d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005a91`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005b43`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005a7d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005a91`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005b43`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800059fe`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800059fe`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180005b0a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180005b0a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall boost::_anonymous_namespace_::run_thread_exit_callbacks(__int64 a1, __int64 a2, void *a3)
{
  volatile signed __int32 *Value; // rsi
  _QWORD *v4; // rbx
  void *v5; // rdi
  HANDLE ProcessHeap; // rax
  HANDLE v7; // rax
  __int64 v8; // rbx
  HANDLE v9; // rax

  if ( dwTlsIndex == -1 )
    Value = 0;
  else
    Value = (volatile signed __int32 *)TlsGetValue(dwTlsIndex);
  if ( !Value )
    goto LABEL_20;
LABEL_5:
  if ( *((_QWORD *)Value + 6) )
  {
    v4 = (_QWORD *)*((_QWORD *)Value + 3);
    if ( !v4 )
      goto LABEL_12;
    goto LABEL_9;
  }
  while ( *((_QWORD *)Value + 3) )
  {
    v4 = (_QWORD *)*((_QWORD *)Value + 3);
    do
    {
LABEL_9:
      *((_QWORD *)Value + 3) = v4[1];
      if ( *v4 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 8LL))(*v4);
        v5 = (void *)*v4;
        (**(void (__fastcall ***)(_QWORD, _QWORD))*v4)(*v4, 0);
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v5);
      }
      v7 = GetProcessHeap();
      HeapFree(v7, 0, v4);
      v4 = (_QWORD *)*((_QWORD *)Value + 3);
    }
    while ( v4 );
LABEL_12:
    if ( *((_QWORD *)Value + 6) )
    {
      do
      {
        v8 = **((_QWORD **)Value + 5);
        if ( *(_QWORD *)(v8 + 48) )
        {
          if ( *(_QWORD *)(v8 + 56) )
            (*(void (**)(void))(v8 + 40))();
        }
        std::_Tree<std::_Tmap_traits<void const *,boost::detail::tss_data_node,std::less<void const *>,std::allocator<std::pair<void const * const,boost::detail::tss_data_node>>,0>>::_Erase_unchecked(
          Value + 10,
          v8);
      }
      while ( *((_QWORD *)Value + 6) );
      goto LABEL_5;
    }
  }
  boost::call_once(
    (struct boost::once_flag *)&qword_180032B28,
    boost::_anonymous_namespace_::create_current_thread_tls_key,
    a3);
  if ( dwTlsIndex != -1 )
    TlsSetValue(dwTlsIndex, 0);
LABEL_20:
  if ( Value && _InterlockedExchangeAdd(Value + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *, _QWORD))Value)(Value, 0);
    v9 = GetProcessHeap();
    HeapFree(v9, 0, (LPVOID)Value);
  }
}

```

## disassembly

```asm
0x1800059e0  mov     [rsp+arg_8], rbx
0x1800059e5  mov     [rsp+arg_10], rsi
0x1800059ea  push    rdi
0x1800059eb  sub     rsp, 20h
0x1800059ef  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x1800059f5  cmp     ecx, 0FFFFFFFFh
0x1800059f8  jnz     short loc_1800059FE
0x1800059fa  xor     esi, esi
0x1800059fc  jmp     short loc_180005A07
0x1800059fe  call    cs:__imp_TlsGetValue
0x180005a04  mov     rsi, rax
0x180005a07  mov     [rsp+28h+arg_0], rsi
0x180005a0c  test    rsi, rsi
0x180005a0f  jz      loc_180005B11
0x180005a15  cmp     qword ptr [rsi+30h], 0
0x180005a1a  jnz     short loc_180005A2D
0x180005a1c  cmp     qword ptr [rsi+18h], 0
0x180005a21  jz      loc_180005AEA
0x180005a27  mov     rbx, [rsi+18h]
0x180005a2b  jmp     short loc_180005A40
0x180005a2d  mov     rbx, [rsi+18h]
0x180005a31  test    rbx, rbx
0x180005a34  jz      short loc_180005AA0
0x180005a36  nop     word ptr [rax+rax+00000000h]
0x180005a40  mov     rax, [rbx+8]
0x180005a44  mov     [rsi+18h], rax
0x180005a48  mov     rcx, [rbx]
0x180005a4b  test    rcx, rcx
0x180005a4e  jz      short loc_180005A83
0x180005a50  mov     rax, [rcx]
0x180005a53  mov     rax, [rax+8]
0x180005a57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a5c  mov     rdi, [rbx]
0x180005a5f  mov     rax, [rdi]
0x180005a62  xor     edx, edx
0x180005a64  mov     rcx, rdi
0x180005a67  mov     rax, [rax]
0x180005a6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a6f  call    cs:__imp_GetProcessHeap
0x180005a75  mov     rcx, rax; hHeap
0x180005a78  mov     r8, rdi; lpMem
0x180005a7b  xor     edx, edx; dwFlags
0x180005a7d  call    cs:__imp_HeapFree
0x180005a83  call    cs:__imp_GetProcessHeap
0x180005a89  mov     rcx, rax; hHeap
0x180005a8c  mov     r8, rbx; lpMem
0x180005a8f  xor     edx, edx; dwFlags
0x180005a91  call    cs:__imp_HeapFree
0x180005a97  mov     rbx, [rsi+18h]
0x180005a9b  test    rbx, rbx
0x180005a9e  jnz     short loc_180005A40
0x180005aa0  cmp     qword ptr [rsi+30h], 0
0x180005aa5  jz      loc_180005A1C
0x180005aab  nop     dword ptr [rax+rax+00h]
0x180005ab0  mov     rbx, [rsi+28h]
0x180005ab4  mov     rbx, [rbx]
0x180005ab7  mov     rcx, [rbx+30h]
0x180005abb  test    rcx, rcx
0x180005abe  jz      short loc_180005AD2
0x180005ac0  mov     rdx, [rbx+38h]
0x180005ac4  test    rdx, rdx
0x180005ac7  jz      short loc_180005AD2
0x180005ac9  mov     rax, [rbx+28h]
0x180005acd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ad2  mov     rdx, rbx
0x180005ad5  lea     rcx, [rsi+28h]
0x180005ad9  call    ?_Erase_unchecked@?$_Tree@V?$_Tmap_traits@PEBXUtss_data_node@detail@boost@@U?$less@PEBX@std@@V?$allocator@U?$pair@QEBXUtss_data_node@detail@boost@@@std@@@5@$0A@@std@@@std@@AEAAPEAU?$_Tree_node@U?$pair@QEBXUtss_data_node@detail@boost@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBXUtss_data_node@detail@boost@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree<std::_Tmap_traits<void const *,boost::detail::tss_data_node,std::less<void const *>,std::allocator<std::pair<void const * const,boost::detail::tss_data_node>>,0>>::_Erase_unchecked(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<void const * const,boost::detail::tss_data_node>>>,std::_Iterator_base0>)
0x180005ade  cmp     qword ptr [rsi+30h], 0
0x180005ae3  jnz     short loc_180005AB0
0x180005ae5  jmp     loc_180005A15
0x180005aea  lea     rdx, boost___anonymous_namespace___create_current_thread_tls_key; void (*)(void)
0x180005af1  lea     rcx, qword_180032B28; struct boost::once_flag *
0x180005af8  call    ?call_once@boost@@YAXAEAUonce_flag@1@P6AXXZ@Z; boost::call_once(boost::once_flag &,void (*)(void))
0x180005afd  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x180005b03  cmp     ecx, 0FFFFFFFFh
0x180005b06  jz      short loc_180005B11
0x180005b08  xor     edx, edx; lpTlsValue
0x180005b0a  call    cs:__imp_TlsSetValue
0x180005b10  nop
0x180005b11  test    rsi, rsi
0x180005b14  jz      short loc_180005B49
0x180005b16  mov     eax, 0FFFFFFFFh
0x180005b1b  lock xadd [rsi+8], eax
0x180005b20  cmp     eax, 1
0x180005b23  jnz     short loc_180005B49
0x180005b25  mov     rax, [rsi]
0x180005b28  xor     edx, edx
0x180005b2a  mov     rcx, rsi
0x180005b2d  mov     rax, [rax]
0x180005b30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b35  call    cs:__imp_GetProcessHeap
0x180005b3b  mov     rcx, rax; hHeap
0x180005b3e  mov     r8, rsi; lpMem
0x180005b41  xor     edx, edx; dwFlags
0x180005b43  call    cs:__imp_HeapFree
0x180005b49  mov     rbx, [rsp+28h+arg_8]
0x180005b4e  mov     rsi, [rsp+28h+arg_10]
0x180005b53  add     rsp, 20h
0x180005b57  pop     rdi
0x180005b58  retn
```
