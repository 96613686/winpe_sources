# std::_Hash<std::_Uset_traits<ATL::CComBSTR,std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>,std::allocator<ATL::CComBSTR>,0>>::_Clear_guard::~_Clear_guard(void)

- ea: `0x140010800`
- end: `0x1400108a8`
- name: `??1_Clear_guard@?$_Hash@V?$_Uset_traits@VCComBSTR@ATL@@V?$_Uhash_compare@VCComBSTR@ATL@@UBSTRHash@DiagHubCommon@@U?$BSTREqualToBase@$00@4@@std@@V?$allocator@VCComBSTR@ATL@@@4@$0A@@std@@@std@@QEAA@XZ`
- size: `168`
- prototype: `void __fastcall(unsigned __int64 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140010570`

## callees

- `0x140010800`
- `0x14001382c`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14001083e`
- `OLEAUT32!__imp_SysFreeString` at `0x14001083e`

## pseudocode

```c
void __fastcall std::_Hash<std::_Uset_traits<ATL::CComBSTR,std::_Uhash_compare<ATL::CComBSTR,DiagHubCommon::BSTRHash,DiagHubCommon::BSTREqualToBase<1>>,std::allocator<ATL::CComBSTR>,0>>::_Clear_guard::~_Clear_guard(
        unsigned __int64 **a1)
{
  unsigned __int64 *v1; // rbx
  unsigned __int64 v2; // rcx
  BSTR *v3; // rsi
  BSTR v4; // rdi
  void *v5; // rdi
  unsigned __int64 v6; // rcx

  v1 = *a1;
  if ( *a1 && v1[2] )
  {
    v2 = v1[1];
    **(_QWORD **)(v2 + 8) = 0;
    v3 = *(BSTR **)v2;
    if ( *(_QWORD *)v2 )
    {
      do
      {
        v4 = *v3;
        SysFreeString(v3[2]);
        operator delete(v3);
        v3 = (BSTR *)v4;
      }
      while ( v4 );
    }
    *(_QWORD *)v1[1] = v1[1];
    *(_QWORD *)(v1[1] + 8) = v1[1];
    v1[2] = 0;
    v5 = (void *)v1[3];
    v6 = (v1[4] - (unsigned __int64)v5 + 7) >> 3;
    if ( (unsigned __int64)v5 > v1[4] )
      v6 = 0;
    if ( v6 )
      memset64(v5, v1[1], v6);
  }
}

```

## disassembly

```asm
0x140010800  mov     [rsp+arg_8], rbx
0x140010805  mov     [rsp+arg_10], rbp
0x14001080a  mov     [rsp+arg_18], rsi
0x14001080f  push    rdi
0x140010810  sub     rsp, 20h
0x140010814  mov     rbx, [rcx]
0x140010817  xor     ebp, ebp
0x140010819  test    rbx, rbx
0x14001081c  jz      short loc_140010893
0x14001081e  cmp     [rbx+10h], rbp
0x140010822  jz      short loc_140010893
0x140010824  mov     rcx, [rbx+8]
0x140010828  mov     rax, [rcx+8]
0x14001082c  mov     [rax], rbp
0x14001082f  mov     rsi, [rcx]
0x140010832  test    rsi, rsi
0x140010835  jz      short loc_140010859
0x140010837  mov     rcx, [rsi+10h]; bstrString
0x14001083b  mov     rdi, [rsi]
0x14001083e  call    cs:__imp_SysFreeString
0x140010844  mov     edx, 18h
0x140010849  mov     rcx, rsi; Block
0x14001084c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140010851  mov     rsi, rdi
0x140010854  test    rdi, rdi
0x140010857  jnz     short loc_140010837
0x140010859  mov     rax, [rbx+8]
0x14001085d  mov     [rax], rax
0x140010860  mov     rax, [rbx+8]
0x140010864  mov     [rax+8], rax
0x140010868  mov     [rbx+10h], rbp
0x14001086c  mov     rdi, [rbx+18h]
0x140010870  mov     rcx, [rbx+20h]
0x140010874  sub     rcx, rdi
0x140010877  add     rcx, 7
0x14001087b  shr     rcx, 3
0x14001087f  cmp     rdi, [rbx+20h]
0x140010883  cmova   rcx, rbp
0x140010887  test    rcx, rcx
0x14001088a  jz      short loc_140010893
0x14001088c  mov     rax, [rbx+8]
0x140010890  rep stosq
0x140010893  mov     rbx, [rsp+28h+arg_8]
0x140010898  mov     rbp, [rsp+28h+arg_10]
0x14001089d  mov     rsi, [rsp+28h+arg_18]
0x1400108a2  add     rsp, 20h
0x1400108a6  pop     rdi
0x1400108a7  retn
```
