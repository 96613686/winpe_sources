# std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Buynode(std::_Tree_nod<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Node *,std::_Tree_nod<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Node *,std::_Tree_nod<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Node *,_EVENT_DESCRIPTOR const &,char)

- ea: `0x18000fd3c`
- end: `0x18000fdb0`
- name: `?_Buynode@?$_Tree@V?$_Tset_traits@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@$0A@@std@@@std@@IEAAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@$0A@@std@@@2@PEAU342@00AEBU_EVENT_DESCRIPTOR@@D@Z`
- size: `116`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ebf4`
- `0x180010428`

## callees

- `0x18000fd3c`
- `0x18002687c`

## pseudocode

```c
char *std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Buynode(
        _DWORD a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _OWORD *a5,
        char a6,
        ...)
{
  char *result; // rax
  _OWORD *v10; // rcx

  result = (char *)operator new(0x30u);
  try
  {
    if ( result )
    {
      *(_QWORD *)result = a2;
      *((_QWORD *)result + 1) = a3;
      *((_QWORD *)result + 2) = a4;
      v10 = a5;
      *(_OWORD *)(result + 24) = *a5;
      result[40] = a6;
      result[41] = 0;
    }
  }
  catch ( ... )
  {
    std::allocator<unsigned int>::deallocate(v10, result);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x18000fd3c  mov     rax, rsp
0x18000fd3f  mov     [rax+8], rcx
0x18000fd43  push    rdi
0x18000fd44  sub     rsp, 30h
0x18000fd48  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFEh
0x18000fd50  mov     [rax+10h], rbx
0x18000fd54  mov     [rax+18h], rsi
0x18000fd58  mov     rbx, r9
0x18000fd5b  mov     rdi, r8
0x18000fd5e  mov     rsi, rdx
0x18000fd61  mov     ecx, 30h ; '0'; Size
0x18000fd66  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000fd6b  mov     r10, rax
0x18000fd6e  mov     [rsp+38h+arg_0], rax
0x18000fd73  test    rax, rax
0x18000fd76  jz      short loc_18000FD9D
0x18000fd78  mov     [rax], rsi
0x18000fd7b  mov     [rax+8], rdi
0x18000fd7f  mov     [rax+10h], rbx
0x18000fd83  mov     rcx, [rsp+38h+arg_20]
0x18000fd88  movups  xmm0, xmmword ptr [rcx]
0x18000fd8b  movdqu  xmmword ptr [rax+18h], xmm0
0x18000fd90  mov     al, [rsp+38h+arg_28]
0x18000fd94  mov     [r10+28h], al
0x18000fd98  mov     byte ptr [r10+29h], 0
0x18000fd9d  mov     rax, r10
0x18000fda0  mov     rbx, [rsp+38h+arg_8]
0x18000fda5  mov     rsi, [rsp+38h+arg_10]
0x18000fdaa  add     rsp, 30h
0x18000fdae  pop     rdi
0x18000fdaf  retn
```
