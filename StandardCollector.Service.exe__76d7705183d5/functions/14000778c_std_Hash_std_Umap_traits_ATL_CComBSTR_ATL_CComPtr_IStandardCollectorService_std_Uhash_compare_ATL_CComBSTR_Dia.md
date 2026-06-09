# std::_Hash<std::_Umap_traits<ATL::CComBSTR,ATL::CComPtr<IStandardCollectorService>,std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComPtr<IStandardCollectorService>>>,0>>::_Clear_guard::~_Clear_guard(void)

- ea: `0x14000778c`
- end: `0x140007853`
- name: `??1_Clear_guard@?$_Hash@V?$_Umap_traits@VCComBSTR@ATL@@V?$CComPtr@UIStandardCollectorService@@@2@V?$_Uhash_compare@VCComBSTR@ATL@@UBSTRHash@DiagHubCommon@@U?$BSTREqualToBase@$00@4@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@V?$CComPtr@UIStandardCollectorService@@@2@@std@@@5@$0A@@std@@@std@@QEAA@XZ`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x140007144`

## callees

- `0x14000778c`
- `0x14001382c`
- `0x140014c70`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1400077e9`
- `OLEAUT32!__imp_SysFreeString` at `0x1400077e9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::_Hash<std::_Umap_traits<ATL::CComBSTR,ATL::CComPtr<IStandardCollectorService>,std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComPtr<IStandardCollectorService>>>,0>>::_Clear_guard::~_Clear_guard(
        unsigned __int64 **a1)
{
  unsigned __int64 *v1; // rbx
  unsigned __int64 v2; // rcx
  void *v3; // rdi
  void *v4; // rsi
  __int64 v5; // rcx
  void *v6; // rdi
  unsigned __int64 v7; // rcx

  v1 = *a1;
  if ( *a1 && v1[2] )
  {
    v2 = v1[1];
    **(_QWORD **)(v2 + 8) = 0;
    v3 = *(void **)v2;
    if ( *(_QWORD *)v2 )
    {
      do
      {
        v4 = *(void **)v3;
        v5 = *((_QWORD *)v3 + 3);
        if ( v5 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
        SysFreeString(*((BSTR *)v3 + 2));
        operator delete(v3);
        v3 = v4;
      }
      while ( v4 );
    }
    *(_QWORD *)v1[1] = v1[1];
    *(_QWORD *)(v1[1] + 8) = v1[1];
    v1[2] = 0;
    v6 = (void *)v1[3];
    v7 = (v1[4] - (unsigned __int64)v6 + 7) >> 3;
    if ( (unsigned __int64)v6 > v1[4] )
      v7 = 0;
    if ( v7 )
      memset64(v6, v1[1], v7);
  }
}

```

## disassembly

```asm
0x14000778c  mov     [rsp+arg_8], rbx
0x140007791  mov     [rsp+arg_10], rbp
0x140007796  mov     [rsp+arg_18], rsi
0x14000779b  push    rdi
0x14000779c  sub     rsp, 20h
0x1400077a0  mov     rbx, [rcx]
0x1400077a3  xor     ebp, ebp
0x1400077a5  test    rbx, rbx
0x1400077a8  jz      loc_14000783E
0x1400077ae  cmp     [rbx+10h], rbp
0x1400077b2  jz      loc_14000783E
0x1400077b8  mov     rcx, [rbx+8]
0x1400077bc  mov     rax, [rcx+8]
0x1400077c0  mov     [rax], rbp
0x1400077c3  mov     rdi, [rcx]
0x1400077c6  test    rdi, rdi
0x1400077c9  jz      short loc_140007804
0x1400077cb  mov     rsi, [rdi]
0x1400077ce  mov     rcx, [rdi+18h]
0x1400077d2  test    rcx, rcx
0x1400077d5  jz      short loc_1400077E5
0x1400077d7  mov     rax, [rcx]
0x1400077da  mov     rax, [rax+10h]
0x1400077de  call    cs:__guard_dispatch_icall_fptr
0x1400077e4  nop
0x1400077e5  mov     rcx, [rdi+10h]; bstrString
0x1400077e9  call    cs:__imp_SysFreeString
0x1400077ef  mov     edx, 20h ; ' '
0x1400077f4  mov     rcx, rdi; Block
0x1400077f7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400077fc  mov     rdi, rsi
0x1400077ff  test    rsi, rsi
0x140007802  jnz     short loc_1400077CB
0x140007804  mov     rax, [rbx+8]
0x140007808  mov     [rax], rax
0x14000780b  mov     rax, [rbx+8]
0x14000780f  mov     [rax+8], rax
0x140007813  mov     [rbx+10h], rbp
0x140007817  mov     rdi, [rbx+18h]
0x14000781b  mov     rcx, [rbx+20h]
0x14000781f  sub     rcx, rdi
0x140007822  add     rcx, 7
0x140007826  shr     rcx, 3
0x14000782a  cmp     rdi, [rbx+20h]
0x14000782e  cmova   rcx, rbp
0x140007832  test    rcx, rcx
0x140007835  jz      short loc_14000783E
0x140007837  mov     rax, [rbx+8]
0x14000783b  rep stosq
0x14000783e  mov     rbx, [rsp+28h+arg_8]
0x140007843  mov     rbp, [rsp+28h+arg_10]
0x140007848  mov     rsi, [rsp+28h+arg_18]
0x14000784d  add     rsp, 20h
0x140007851  pop     rdi
0x140007852  retn
```
