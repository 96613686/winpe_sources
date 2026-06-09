# std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::insert(std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::iterator,std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> const &)

- ea: `0x18000e058`
- end: `0x18000e278`
- name: `?insert@?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@QEAA?AViterator@12@V312@AEBU?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@2@@Z`
- size: `544`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000d560`

## callees

- `0x18000e058`
- `0x18000ebf4`
- `0x18000eee4`
- `0x180027444`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000e0af`
- `msvcrt!_wcsicmp` at `0x18000e0e0`
- `msvcrt!_wcsicmp` at `0x18000e102`
- `msvcrt!_wcsicmp` at `0x18000e167`
- `msvcrt!_wcsicmp` at `0x18000e1a0`
- `msvcrt!_wcsicmp` at `0x18000e211`
- `msvcrt!_wcsicmp` at `0x18000e0af`
- `msvcrt!_wcsicmp` at `0x18000e0e0`
- `msvcrt!_wcsicmp` at `0x18000e102`
- `msvcrt!_wcsicmp` at `0x18000e167`
- `msvcrt!_wcsicmp` at `0x18000e1a0`
- `msvcrt!_wcsicmp` at `0x18000e211`

## pseudocode

```c
__int64 *__fastcall std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::insert(
        __int64 a1,
        __int64 *a2,
        __int64 *a3,
        const wchar_t **a4)
{
  __int64 *v6; // r14
  __int64 v7; // rbp
  __int64 *v8; // r9
  char v9; // r8
  __int64 **v10; // rax
  __int64 *v11; // r9
  char v12; // r8
  __int64 *v13; // rax
  __int64 *v14; // rdi
  __int64 *j; // rax
  __int64 *i; // rcx
  __int64 *v17; // rdi
  __int64 *v18; // rax
  __int64 *v19; // rdi
  __int64 *k; // rax
  uintptr_t Reserved; // [rsp+20h] [rbp-38h]
  _BYTE v23[40]; // [rsp+30h] [rbp-28h] BYREF

  v6 = a2;
  v7 = a1;
  if ( !*(_QWORD *)(a1 + 16) )
  {
    Reserved = (uintptr_t)a4;
    v8 = *(__int64 **)(a1 + 8);
LABEL_3:
    v9 = 1;
LABEL_4:
    std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Insert(
      a1,
      a2,
      v9,
      v8,
      Reserved);
    return v6;
  }
  v10 = *(__int64 ***)(a1 + 8);
  if ( a3 != *v10 )
  {
    if ( a3 != (__int64 *)v10 )
    {
      if ( _wcsicmp(*a4, (const wchar_t *)a3[3]) >= 0 )
        goto LABEL_44;
      v13 = a3;
      if ( *((_BYTE *)a3 + 41) )
      {
        v14 = (__int64 *)a3[2];
      }
      else
      {
        v14 = (__int64 *)*a3;
        if ( *(_BYTE *)(*a3 + 41) )
        {
          for ( i = (__int64 *)a3[1]; !*((_BYTE *)i + 41) && v13 == (__int64 *)*i; i = (__int64 *)i[1] )
            v13 = i;
          v14 = v13;
          if ( !*((_BYTE *)v13 + 41) )
            v14 = i;
        }
        else
        {
          for ( j = (__int64 *)v14[2]; !*((_BYTE *)j + 41); j = (__int64 *)j[2] )
            v14 = j;
        }
      }
      if ( _wcsicmp((const wchar_t *)v14[3], *a4) >= 0 )
      {
LABEL_44:
        if ( _wcsicmp((const wchar_t *)a3[3], *a4) >= 0 )
          goto LABEL_48;
        v17 = a3;
        if ( *((_BYTE *)a3 + 41) )
          invalid_parameter(0, 0, 0, 0, 0);
        v18 = (__int64 *)a3[2];
        if ( *((_BYTE *)v18 + 41) )
        {
          for ( k = (__int64 *)a3[1]; !*((_BYTE *)k + 41) && v17 == (__int64 *)k[2]; k = (__int64 *)k[1] )
            v17 = k;
          v19 = k;
        }
        else
        {
          do
          {
            v19 = v18;
            v18 = (__int64 *)*v18;
          }
          while ( !*((_BYTE *)v18 + 41) );
        }
        if ( v19 != *(__int64 **)(v7 + 8) && _wcsicmp(*a4, (const wchar_t *)v19[3]) >= 0 )
          goto LABEL_48;
        a2 = v6;
        Reserved = (uintptr_t)a4;
        a1 = v7;
        if ( !*(_BYTE *)(a3[2] + 41) )
        {
          v8 = v19;
          goto LABEL_3;
        }
        v8 = a3;
      }
      else
      {
        a2 = v6;
        Reserved = (uintptr_t)a4;
        a1 = v7;
        if ( !*(_BYTE *)(v14[2] + 41) )
        {
          v8 = a3;
          goto LABEL_3;
        }
        v8 = v14;
      }
      v9 = 0;
      goto LABEL_4;
    }
    if ( _wcsicmp((const wchar_t *)v10[2][3], *a4) < 0 )
    {
      v12 = 0;
      v11 = *(__int64 **)(*(_QWORD *)(v7 + 8) + 16LL);
      goto LABEL_9;
    }
LABEL_48:
    *v6 = *(_QWORD *)std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::insert(
                       v7,
                       v23,
                       a4);
    return v6;
  }
  if ( _wcsicmp(*a4, (const wchar_t *)a3[3]) >= 0 )
    goto LABEL_48;
  v11 = a3;
  v12 = 1;
LABEL_9:
  std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Insert(
    v7,
    v6,
    v12,
    v11,
    (__int64)a4);
  return v6;
}

```

## disassembly

```asm
0x18000e058  mov     rax, rsp
0x18000e05b  mov     [rax+8], rbx
0x18000e05f  mov     [rax+10h], rbp
0x18000e063  mov     [rax+18h], rsi
0x18000e067  mov     [rax+20h], rdi
0x18000e06b  push    r12
0x18000e06d  push    r14
0x18000e06f  push    r15
0x18000e071  sub     rsp, 40h
0x18000e075  xor     r12d, r12d
0x18000e078  mov     r15, r9
0x18000e07b  mov     rbx, r8
0x18000e07e  mov     r14, rdx
0x18000e081  mov     rbp, rcx
0x18000e084  cmp     [rcx+10h], r12
0x18000e088  jnz     short loc_18000E09F
0x18000e08a  mov     [rax-38h], r9
0x18000e08e  mov     r9, [rcx+8]
0x18000e092  mov     r8b, 1
0x18000e095  call    ?_Insert@?$_Tree@V?$_Tset_traits@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@$0A@@std@@@std@@IEAA?AViterator@12@_NPEAU_Node@?$_Tree_nod@V?$_Tset_traits@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@$0A@@std@@@2@AEBU_EVENT_DESCRIPTOR@@@Z; std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Insert(bool,std::_Tree_nod<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Node *,_EVENT_DESCRIPTOR const &)
0x18000e09a  jmp     loc_18000E256
0x18000e09f  mov     rax, [rcx+8]
0x18000e0a3  cmp     rbx, [rax]
0x18000e0a6  jnz     short loc_18000E0D0
0x18000e0a8  mov     rdx, [r8+18h]; String2
0x18000e0ac  mov     rcx, [r9]; String1
0x18000e0af  call    cs:__imp__wcsicmp
0x18000e0b5  test    eax, eax
0x18000e0b7  jns     loc_18000E240
0x18000e0bd  mov     r9, rbx
0x18000e0c0  mov     r8b, 1
0x18000e0c3  mov     [rsp+58h+Reserved], r15
0x18000e0c8  mov     rdx, r14
0x18000e0cb  mov     rcx, rbp
0x18000e0ce  jmp     short loc_18000E095
0x18000e0d0  cmp     rbx, rax
0x18000e0d3  jnz     short loc_18000E0FB
0x18000e0d5  mov     rax, [rax+10h]
0x18000e0d9  mov     rdx, [r9]; String2
0x18000e0dc  mov     rcx, [rax+18h]; String1
0x18000e0e0  call    cs:__imp__wcsicmp
0x18000e0e6  test    eax, eax
0x18000e0e8  jns     loc_18000E240
0x18000e0ee  mov     r9, [rbp+8]
0x18000e0f2  xor     r8d, r8d
0x18000e0f5  mov     r9, [r9+10h]
0x18000e0f9  jmp     short loc_18000E0C3
0x18000e0fb  mov     rdx, [r8+18h]; String2
0x18000e0ff  mov     rcx, [r9]; String1
0x18000e102  call    cs:__imp__wcsicmp
0x18000e108  test    eax, eax
0x18000e10a  jns     loc_18000E199
0x18000e110  mov     rax, rbx
0x18000e113  cmp     [rbx+29h], r12b
0x18000e117  jz      short loc_18000E11F
0x18000e119  mov     rdi, [rbx+10h]
0x18000e11d  jmp     short loc_18000E160
0x18000e11f  mov     rdi, [rbx]
0x18000e122  cmp     [rdi+29h], r12b
0x18000e126  jnz     short loc_18000E13D
0x18000e128  mov     rax, [rdi+10h]
0x18000e12c  jmp     short loc_18000E135
0x18000e12e  mov     rdi, rax
0x18000e131  mov     rax, [rax+10h]
0x18000e135  cmp     [rax+29h], r12b
0x18000e139  jz      short loc_18000E12E
0x18000e13b  jmp     short loc_18000E160
0x18000e13d  mov     rcx, [rbx+8]
0x18000e141  jmp     short loc_18000E14F
0x18000e143  cmp     rax, [rcx]
0x18000e146  jnz     short loc_18000E155
0x18000e148  mov     rax, rcx
0x18000e14b  mov     rcx, [rcx+8]
0x18000e14f  cmp     [rcx+29h], r12b
0x18000e153  jz      short loc_18000E143
0x18000e155  cmp     [rax+29h], r12b
0x18000e159  mov     rdi, rax
0x18000e15c  cmovz   rdi, rcx
0x18000e160  mov     rdx, [r15]; String2
0x18000e163  mov     rcx, [rdi+18h]; String1
0x18000e167  call    cs:__imp__wcsicmp
0x18000e16d  test    eax, eax
0x18000e16f  jns     short loc_18000E199
0x18000e171  mov     rax, [rdi+10h]
0x18000e175  mov     rdx, r14
0x18000e178  mov     [rsp+58h+Reserved], r15
0x18000e17d  mov     rcx, rbp
0x18000e180  cmp     [rax+29h], r12b
0x18000e184  jz      short loc_18000E191
0x18000e186  mov     r9, rdi
0x18000e189  xor     r8d, r8d
0x18000e18c  jmp     loc_18000E095
0x18000e191  mov     r9, rbx
0x18000e194  jmp     loc_18000E092
0x18000e199  mov     rdx, [r15]; String2
0x18000e19c  mov     rcx, [rbx+18h]; String1
0x18000e1a0  call    cs:__imp__wcsicmp
0x18000e1a6  test    eax, eax
0x18000e1a8  jns     loc_18000E240
0x18000e1ae  mov     rdi, rbx
0x18000e1b1  mov     rsi, [rbp+8]
0x18000e1b5  cmp     [rbx+29h], r12b
0x18000e1b9  jz      short loc_18000E1D1
0x18000e1bb  xor     r9d, r9d; LineNo
0x18000e1be  mov     [rsp+58h+Reserved], r12; Reserved
0x18000e1c3  xor     r8d, r8d; FileName
0x18000e1c6  xor     edx, edx; FunctionName
0x18000e1c8  xor     ecx, ecx; Expression
0x18000e1ca  call    _invalid_parameter
0x18000e1cf  jmp     short loc_18000E205
0x18000e1d1  mov     rax, [rbx+10h]
0x18000e1d5  cmp     [rax+29h], r12b
0x18000e1d9  jnz     short loc_18000E1E9
0x18000e1db  mov     rdi, rax
0x18000e1de  mov     rax, [rax]
0x18000e1e1  cmp     [rax+29h], r12b
0x18000e1e5  jz      short loc_18000E1DB
0x18000e1e7  jmp     short loc_18000E205
0x18000e1e9  mov     rax, [rbx+8]
0x18000e1ed  jmp     short loc_18000E1FC
0x18000e1ef  cmp     rdi, [rax+10h]
0x18000e1f3  jnz     short loc_18000E202
0x18000e1f5  mov     rdi, rax
0x18000e1f8  mov     rax, [rax+8]
0x18000e1fc  cmp     [rax+29h], r12b
0x18000e200  jz      short loc_18000E1EF
0x18000e202  mov     rdi, rax
0x18000e205  cmp     rdi, rsi
0x18000e208  jz      short loc_18000E21B
0x18000e20a  mov     rdx, [rdi+18h]; String2
0x18000e20e  mov     rcx, [r15]; String1
0x18000e211  call    cs:__imp__wcsicmp
0x18000e217  test    eax, eax
0x18000e219  jns     short loc_18000E240
0x18000e21b  mov     rax, [rbx+10h]
0x18000e21f  mov     rdx, r14
0x18000e222  mov     [rsp+58h+Reserved], r15
0x18000e227  mov     rcx, rbp
0x18000e22a  cmp     [rax+29h], r12b
0x18000e22e  jz      short loc_18000E238
0x18000e230  mov     r9, rbx
0x18000e233  jmp     loc_18000E189
0x18000e238  mov     r9, rdi
0x18000e23b  jmp     loc_18000E092
0x18000e240  mov     r8, r15
0x18000e243  lea     rdx, [rsp+58h+var_28]
0x18000e248  mov     rcx, rbp
0x18000e24b  call    ?insert@?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@QEAA?AU?$pair@Viterator@?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@_N@2@AEBU?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@2@@Z; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::insert(std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> const &)
0x18000e250  mov     rcx, [rax]
0x18000e253  mov     [r14], rcx
0x18000e256  mov     rbx, [rsp+58h+arg_0]
0x18000e25b  mov     rax, r14
0x18000e25e  mov     rbp, [rsp+58h+arg_8]
0x18000e263  mov     rsi, [rsp+58h+arg_10]
0x18000e268  mov     rdi, [rsp+58h+arg_18]
0x18000e26d  add     rsp, 40h
0x18000e271  pop     r15
0x18000e273  pop     r14
0x18000e275  pop     r12
0x18000e277  retn
```
