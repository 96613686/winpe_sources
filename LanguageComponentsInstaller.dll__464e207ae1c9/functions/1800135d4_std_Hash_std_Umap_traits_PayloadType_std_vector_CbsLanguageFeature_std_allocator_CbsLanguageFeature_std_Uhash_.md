# std::_Hash<std::_Umap_traits<PayloadType,std::vector<CbsLanguageFeature,std::allocator<CbsLanguageFeature>>,std::_Uhash_compare<PayloadType,std::hash<PayloadType>,std::equal_to<PayloadType>>,std::allocator<std::pair<PayloadType const,std::vector<CbsLanguageFeature,std::allocator<CbsLanguageFeature>>>>,0>>::_Clear_guard::~_Clear_guard(void)

- ea: `0x1800135d4`
- end: `0x1800136a0`
- name: `??1_Clear_guard@?$_Hash@V?$_Umap_traits@W4PayloadType@@V?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@V?$_Uhash_compare@W4PayloadType@@U?$hash@W4PayloadType@@@std@@U?$equal_to@W4PayloadType@@@3@@3@V?$allocator@U?$pair@$$CBW4PayloadType@@V?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ`
- size: `204`
- prototype: `void __fastcall(unsigned __int64 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800211f0`

## callees

- `0x180003a34`
- `0x1800135d4`
- `0x180021590`
- `0x1800217e8`

## pseudocode

```c
void __fastcall std::_Hash<std::_Umap_traits<enum PayloadType,std::vector<CbsLanguageFeature>,std::_Uhash_compare<enum PayloadType,std::hash<enum PayloadType>,std::equal_to<enum PayloadType>>,std::allocator<std::pair<enum PayloadType const,std::vector<CbsLanguageFeature>>>,0>>::_Clear_guard::~_Clear_guard(
        unsigned __int64 **a1)
{
  unsigned __int64 *v1; // rbx
  unsigned __int64 v2; // rcx
  _QWORD *v3; // rsi
  _QWORD *v4; // rdi
  void *v5; // rdi
  unsigned __int64 v6; // rcx

  v1 = *a1;
  if ( *a1 && v1[2] )
  {
    v2 = v1[1];
    if ( v1[7] >> 3 <= v1[2] )
    {
      **(_QWORD **)(v2 + 8) = 0;
      v3 = *(_QWORD **)v2;
      if ( *(_QWORD *)v2 )
      {
        do
        {
          v4 = (_QWORD *)*v3;
          std::vector<CbsLanguageFeature>::_Tidy(v3 + 3);
          operator delete(v3);
          v3 = v4;
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
    else
    {
      std::_Hash<std::_Umap_traits<enum PayloadType,std::vector<CbsLanguageFeature>,std::_Uhash_compare<enum PayloadType,std::hash<enum PayloadType>,std::equal_to<enum PayloadType>>,std::allocator<std::pair<enum PayloadType const,std::vector<CbsLanguageFeature>>>,0>>::_Unchecked_erase(
        v1,
        *(_QWORD *)v2,
        v1[1]);
    }
  }
}

```

## disassembly

```asm
0x1800135d4  mov     [rsp+arg_8], rbx
0x1800135d9  mov     [rsp+arg_10], rsi
0x1800135de  push    rdi
0x1800135df  sub     rsp, 20h
0x1800135e3  mov     rbx, [rcx]
0x1800135e6  test    rbx, rbx
0x1800135e9  jz      loc_180013690
0x1800135ef  cmp     qword ptr [rbx+10h], 0
0x1800135f4  jz      loc_180013690
0x1800135fa  mov     rax, [rbx+38h]
0x1800135fe  mov     rcx, [rbx+8]
0x180013602  shr     rax, 3
0x180013606  cmp     rax, [rbx+10h]
0x18001360a  jbe     short loc_18001361C
0x18001360c  mov     rdx, [rcx]
0x18001360f  mov     r8, rcx
0x180013612  mov     rcx, rbx
0x180013615  call    ?_Unchecked_erase@?$_Hash@V?$_Umap_traits@W4PayloadType@@V?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@V?$_Uhash_compare@W4PayloadType@@U?$hash@W4PayloadType@@@std@@U?$equal_to@W4PayloadType@@@3@@3@V?$allocator@U?$pair@$$CBW4PayloadType@@V?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@std@@@3@$0A@@std@@@std@@AEAAPEAU?$_List_node@U?$pair@$$CBW4PayloadType@@V?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@std@@PEAX@2@PEAU32@QEAU32@@Z; std::_Hash<std::_Umap_traits<PayloadType,std::vector<CbsLanguageFeature>,std::_Uhash_compare<PayloadType,std::hash<PayloadType>,std::equal_to<PayloadType>>,std::allocator<std::pair<PayloadType const,std::vector<CbsLanguageFeature>>>,0>>::_Unchecked_erase(std::_List_node<std::pair<PayloadType const,std::vector<CbsLanguageFeature>>,void *> *,std::_List_node<std::pair<PayloadType const,std::vector<CbsLanguageFeature>>,void *> * const)
0x18001361a  jmp     short loc_180013690
0x18001361c  mov     rax, [rcx+8]
0x180013620  mov     qword ptr [rax], 0
0x180013627  mov     rsi, [rcx]
0x18001362a  test    rsi, rsi
0x18001362d  jz      short loc_180013650
0x18001362f  mov     rdi, [rsi]
0x180013632  lea     rcx, [rsi+18h]
0x180013636  call    ?_Tidy@?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@AEAAXXZ; std::vector<CbsLanguageFeature>::_Tidy(void)
0x18001363b  mov     edx, 30h ; '0'
0x180013640  mov     rcx, rsi; Block
0x180013643  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180013648  mov     rsi, rdi
0x18001364b  test    rdi, rdi
0x18001364e  jnz     short loc_18001362F
0x180013650  mov     rax, [rbx+8]
0x180013654  xor     edx, edx
0x180013656  mov     [rax], rax
0x180013659  mov     rax, [rbx+8]
0x18001365d  mov     [rax+8], rax
0x180013661  mov     qword ptr [rbx+10h], 0
0x180013669  mov     rdi, [rbx+18h]
0x18001366d  mov     rcx, [rbx+20h]
0x180013671  sub     rcx, rdi
0x180013674  add     rcx, 7
0x180013678  shr     rcx, 3
0x18001367c  cmp     rdi, [rbx+20h]
0x180013680  cmova   rcx, rdx
0x180013684  test    rcx, rcx
0x180013687  jz      short loc_180013690
0x180013689  mov     rax, [rbx+8]
0x18001368d  rep stosq
0x180013690  mov     rbx, [rsp+28h+arg_8]
0x180013695  mov     rsi, [rsp+28h+arg_10]
0x18001369a  add     rsp, 20h
0x18001369e  pop     rdi
0x18001369f  retn
```
