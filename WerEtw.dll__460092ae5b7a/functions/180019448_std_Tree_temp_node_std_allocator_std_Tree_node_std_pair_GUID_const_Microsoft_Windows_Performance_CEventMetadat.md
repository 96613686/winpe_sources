# std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>,void *>>>(std::allocator<std::_Tree_node<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>,void *>> &,std::_Tree_node<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>,void *> *,std::piecewise_construct_t const &,std::tuple<_GUID const &> &&,std::tuple<> &&)

- ea: `0x180019448`
- end: `0x18001954f`
- name: `??$?0AEBUpiecewise_construct_t@std@@V?$tuple@AEBU_GUID@@@1@V?$tuple@$$V@1@@?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@UCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@UCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@UCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@std@@PEAX@1@AEBUpiecewise_construct_t@1@$$QEAV?$tuple@AEBU_GUID@@@1@$$QEAV?$tuple@$$V@1@@Z`
- size: `263`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, __int64, __int64, _OWORD **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001bb1c`

## callees

- `0x1800018a0`
- `0x180019448`

## pseudocode

```c
_QWORD *__fastcall std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>,void *>>>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _OWORD **a5)
{
  _OWORD *v7; // rax
  char *v8; // rdi
  _QWORD *v9; // rax
  _QWORD *v10; // rax
  __int64 i; // rcx

  *a1 = a2;
  a1[1] = 0;
  v7 = operator new(0x78u);
  a1[1] = v7;
  v7[2] = **a5;
  v8 = (char *)(v7 + 3);
  *((_QWORD *)v7 + 6) = 0;
  *((_QWORD *)v7 + 7) = 0;
  v9 = operator new(0x30u);
  *v9 = v9;
  v9[1] = v9;
  v9[2] = v9;
  *((_WORD *)v9 + 12) = 257;
  *(_QWORD *)v8 = v9;
  *((_QWORD *)v8 + 2) = 0;
  *((_QWORD *)v8 + 3) = 0;
  v10 = operator new(0x40u);
  *v10 = v10;
  v10[1] = v10;
  v10[2] = v10;
  *((_WORD *)v10 + 12) = 257;
  *((_QWORD *)v8 + 2) = v10;
  *((_OWORD *)v8 + 2) = 0;
  *((_QWORD *)v8 + 6) = 0;
  *((_QWORD *)v8 + 7) = 7;
  *((_WORD *)v8 + 16) = 0;
  v8[64] = 0;
  *(_QWORD *)a1[1] = a3;
  *(_QWORD *)(a1[1] + 8LL) = a3;
  *(_QWORD *)(a1[1] + 16LL) = a3;
  for ( i = 0; i != 2; ++i )
    *(_BYTE *)(i + a1[1] + 24) = 0;
  return a1;
}

```

## disassembly

```asm
0x180019448  mov     [rsp+arg_8], rbx
0x18001944d  mov     [rsp+arg_18], r9
0x180019452  mov     [rsp+arg_0], rcx
0x180019457  push    rsi
0x180019458  push    rdi
0x180019459  push    r14
0x18001945b  sub     rsp, 20h
0x18001945f  mov     rsi, r8
0x180019462  mov     r14, rcx
0x180019465  mov     [rcx], rdx
0x180019468  mov     qword ptr [rcx+8], 0
0x180019470  mov     ecx, 78h ; 'x'; Size
0x180019475  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001947a  mov     [r14+8], rax
0x18001947e  mov     rcx, [rsp+38h+arg_20]
0x180019483  mov     rcx, [rcx]
0x180019486  movups  xmm0, xmmword ptr [rcx]
0x180019489  movdqu  xmmword ptr [rax+20h], xmm0
0x18001948e  lea     rdi, [rax+30h]
0x180019492  mov     [rsp+38h+arg_18], rdi
0x180019497  mov     qword ptr [rdi], 0
0x18001949e  mov     qword ptr [rdi+8], 0
0x1800194a6  mov     ecx, 30h ; '0'; Size
0x1800194ab  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800194b0  mov     [rax], rax
0x1800194b3  mov     [rax+8], rax
0x1800194b7  mov     [rax+10h], rax
0x1800194bb  mov     word ptr [rax+18h], 101h
0x1800194c1  mov     [rdi], rax
0x1800194c4  mov     qword ptr [rdi+10h], 0
0x1800194cc  mov     qword ptr [rdi+18h], 0
0x1800194d4  mov     ecx, 40h ; '@'; Size
0x1800194d9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800194de  mov     [rax], rax
0x1800194e1  mov     [rax+8], rax
0x1800194e5  mov     [rax+10h], rax
0x1800194e9  mov     word ptr [rax+18h], 101h
0x1800194ef  mov     [rdi+10h], rax
0x1800194f3  xorps   xmm0, xmm0
0x1800194f6  movups  xmmword ptr [rdi+20h], xmm0
0x1800194fa  mov     qword ptr [rdi+30h], 0
0x180019502  mov     qword ptr [rdi+38h], 7
0x18001950a  xor     eax, eax
0x18001950c  mov     [rdi+20h], ax
0x180019510  mov     [rdi+40h], al
0x180019513  mov     rax, [r14+8]
0x180019517  mov     [rax], rsi
0x18001951a  mov     rax, [r14+8]
0x18001951e  mov     [rax+8], rsi
0x180019522  mov     rax, [r14+8]
0x180019526  mov     [rax+10h], rsi
0x18001952a  xor     ecx, ecx
0x18001952c  mov     rax, [r14+8]
0x180019530  mov     byte ptr [rcx+rax+18h], 0
0x180019535  inc     rcx
0x180019538  cmp     rcx, 2
0x18001953c  jnz     short loc_18001952C
0x18001953e  mov     rax, r14
0x180019541  mov     rbx, [rsp+38h+arg_8]
0x180019546  add     rsp, 20h
0x18001954a  pop     r14
0x18001954c  pop     rdi
0x18001954d  pop     rsi
0x18001954e  retn
```
