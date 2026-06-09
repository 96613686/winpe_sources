# std::_Tree<std::_Tmap_traits<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<ulong>,std::allocator<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>::_Insert(bool,std::_Tree_nod<std::_Tmap_traits<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<ulong>,std::allocator<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>::_Node *,std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>> const &)

- ea: `0x18000f0c0`
- end: `0x18000f3b3`
- name: `?_Insert@?$_Tree@V?$_Tmap_traits@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEAA?AViterator@12@_NPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@$0A@@std@@@2@AEBU?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@2@@Z`
- size: `755`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000e278`

## callees

- `0x1800022e4`
- `0x18000f0c0`
- `0x18000fe00`
- `0x180013178`
- `0x180026e30`
- `0x180026f66`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall std::_Tree<std::_Tmap_traits<unsigned long,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>::_Insert(
        __int64 a1,
        __int64 *a2,
        char a3,
        __int64 *a4,
        __int64 a5)
{
  __int64 v9; // r9
  __int64 *v10; // rax
  __int64 v11; // rax
  __int64 *v12; // rax
  __int64 v13; // rdx
  __int64 i; // r8
  __int64 *v15; // rax
  __int64 *v16; // r10
  __int64 v17; // rcx
  __int64 *v18; // rcx
  __int64 v19; // rax
  _QWORD *v20; // rax
  _QWORD *v21; // rcx
  _QWORD *v22; // r8
  __int64 v23; // rax
  __int64 v24; // rax
  _QWORD *v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rax
  _QWORD *v29; // rax
  __int64 v30; // rax
  _QWORD *v31; // rax
  _BYTE v33[40]; // [rsp+38h] [rbp-90h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+60h] [rbp-68h] BYREF

  if ( *(_QWORD *)(a1 + 16) >= 0x7FFFFFFFFFFFFFEuLL )
  {
    std::string::string(v33, "map/set<T> too long");
    std::length_error::length_error(pExceptionObject, v33);
    throw (std::length_error *)pExceptionObject;
  }
  v9 = std::_Tree<std::_Tmap_traits<unsigned long,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>::_Buynode(
         -2,
         *(_QWORD *)(a1 + 8),
         (_DWORD)a4,
         *(_QWORD *)(a1 + 8),
         a5);
  ++*(_QWORD *)(a1 + 16);
  v10 = *(__int64 **)(a1 + 8);
  if ( a4 == v10 )
  {
    v10[1] = v9;
    **(_QWORD **)(a1 + 8) = v9;
    v11 = *(_QWORD *)(a1 + 8);
LABEL_9:
    *(_QWORD *)(v11 + 16) = v9;
    goto LABEL_10;
  }
  if ( !a3 )
  {
    a4[2] = v9;
    v11 = *(_QWORD *)(a1 + 8);
    if ( a4 != *(__int64 **)(v11 + 16) )
      goto LABEL_10;
    goto LABEL_9;
  }
  *a4 = v9;
  v12 = *(__int64 **)(a1 + 8);
  if ( a4 == (__int64 *)*v12 )
    *v12 = v9;
LABEL_10:
  v13 = v9;
  for ( i = v9 + 8; !*(_BYTE *)(*(_QWORD *)(v13 + 8) + 56LL); i = v13 + 8 )
  {
    v15 = *(__int64 **)i;
    v16 = *(__int64 **)(*(_QWORD *)i + 8LL);
    v17 = *v16;
    if ( *(_QWORD *)i == *v16 )
    {
      v17 = v16[2];
      if ( *(_BYTE *)(v17 + 56) )
      {
        if ( v13 == v15[2] )
        {
          v13 = *(_QWORD *)i;
          v18 = (__int64 *)v15[2];
          v15[2] = *v18;
          if ( !*(_BYTE *)(*v18 + 57) )
            *(_QWORD *)(*v18 + 8) = v15;
          i = (__int64)(v15 + 1);
          v18[1] = v15[1];
          v19 = *(_QWORD *)(a1 + 8);
          if ( v13 == *(_QWORD *)(v19 + 8) )
          {
            *(_QWORD *)(v19 + 8) = v18;
          }
          else
          {
            v20 = *(_QWORD **)i;
            if ( v13 == **(_QWORD **)i )
              *v20 = v18;
            else
              v20[2] = v18;
          }
          *v18 = v13;
          *(_QWORD *)i = v18;
        }
        *(_BYTE *)(*(_QWORD *)i + 56LL) = 1;
        *(_BYTE *)(*(_QWORD *)(*(_QWORD *)i + 8LL) + 56LL) = 0;
        v21 = *(_QWORD **)(*(_QWORD *)i + 8LL);
        v22 = (_QWORD *)*v21;
        *v21 = *(_QWORD *)(*v21 + 16LL);
        v23 = v22[2];
        if ( !*(_BYTE *)(v23 + 57) )
          *(_QWORD *)(v23 + 8) = v21;
        v22[1] = v21[1];
        v24 = *(_QWORD *)(a1 + 8);
        if ( v21 == *(_QWORD **)(v24 + 8) )
        {
          *(_QWORD *)(v24 + 8) = v22;
        }
        else
        {
          v25 = (_QWORD *)v21[1];
          if ( v21 == (_QWORD *)v25[2] )
            v25[2] = v22;
          else
            *v25 = v22;
        }
        v22[2] = v21;
LABEL_49:
        v21[1] = v22;
        continue;
      }
    }
    else if ( *(_BYTE *)(v17 + 56) )
    {
      if ( v13 == *v15 )
      {
        v13 = *(_QWORD *)i;
        v26 = *v15;
        *v15 = *(_QWORD *)(*v15 + 16);
        v27 = *(_QWORD *)(v26 + 16);
        if ( !*(_BYTE *)(v27 + 57) )
          *(_QWORD *)(v27 + 8) = v13;
        i = v13 + 8;
        *(_QWORD *)(v26 + 8) = *(_QWORD *)(v13 + 8);
        v28 = *(_QWORD *)(a1 + 8);
        if ( v13 == *(_QWORD *)(v28 + 8) )
        {
          *(_QWORD *)(v28 + 8) = v26;
        }
        else
        {
          v29 = *(_QWORD **)i;
          if ( v13 == *(_QWORD *)(*(_QWORD *)i + 16LL) )
            v29[2] = v26;
          else
            *v29 = v26;
        }
        *(_QWORD *)(v26 + 16) = v13;
        *(_QWORD *)i = v26;
      }
      *(_BYTE *)(*(_QWORD *)i + 56LL) = 1;
      *(_BYTE *)(*(_QWORD *)(*(_QWORD *)i + 8LL) + 56LL) = 0;
      v21 = *(_QWORD **)(*(_QWORD *)i + 8LL);
      v22 = (_QWORD *)v21[2];
      v21[2] = *v22;
      if ( !*(_BYTE *)(*v22 + 57LL) )
        *(_QWORD *)(*v22 + 8LL) = v21;
      v22[1] = v21[1];
      v30 = *(_QWORD *)(a1 + 8);
      if ( v21 == *(_QWORD **)(v30 + 8) )
      {
        *(_QWORD *)(v30 + 8) = v22;
      }
      else
      {
        v31 = (_QWORD *)v21[1];
        if ( v21 == (_QWORD *)*v31 )
          *v31 = v22;
        else
          v31[2] = v22;
      }
      *v22 = v21;
      goto LABEL_49;
    }
    *((_BYTE *)v15 + 56) = 1;
    *(_BYTE *)(v17 + 56) = 1;
    *(_BYTE *)(*(_QWORD *)(*(_QWORD *)i + 8LL) + 56LL) = 0;
    v13 = *(_QWORD *)(*(_QWORD *)i + 8LL);
  }
  *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 56LL) = 1;
  *a2 = v9;
  return a2;
}

```

## disassembly

```asm
0x18000f0c0  mov     rax, rsp
0x18000f0c3  push    rsi
0x18000f0c4  push    rdi
0x18000f0c5  push    r14
0x18000f0c7  sub     rsp, 0B0h
0x18000f0ce  mov     [rsp+0C8h+var_98], 0FFFFFFFFFFFFFFFEh
0x18000f0d7  mov     [rax+18h], rbx
0x18000f0db  mov     rax, cs:__security_cookie
0x18000f0e2  xor     rax, rsp
0x18000f0e5  mov     [rsp+0C8h+var_28], rax
0x18000f0ed  mov     rdi, r9
0x18000f0f0  mov     sil, r8b
0x18000f0f3  mov     r14, rdx
0x18000f0f6  mov     rbx, rcx
0x18000f0f9  mov     rax, [rsp+0C8h+arg_20]
0x18000f101  mov     rcx, 7FFFFFFFFFFFFFEh
0x18000f10b  cmp     [rbx+10h], rcx
0x18000f10f  jb      short loc_18000F144
0x18000f111  lea     rdx, aMapSetTTooLong; "map/set<T> too long"
0x18000f118  lea     rcx, [rsp+0C8h+var_90]
0x18000f11d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAA@PEBD@Z; std::string::string(char const *)
0x18000f122  nop
0x18000f123  lea     rdx, [rsp+0C8h+var_90]
0x18000f128  lea     rcx, [rsp+0C8h+pExceptionObject]
0x18000f12d  call    ??0length_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@1@@Z; std::length_error::length_error(std::string const &)
0x18000f132  lea     rdx, _TI3?AVlength_error@std@@; pThrowInfo
0x18000f139  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x18000f13e  call    _CxxThrowException_0
0x18000f144  mov     rdx, [rbx+8]
0x18000f148  mov     [rsp+0C8h+var_A8], rax
0x18000f14d  mov     r9, rdx
0x18000f150  mov     r8, rdi
0x18000f153  call    ?_Buynode@?$_Tree@V?$_Tmap_traits@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEAAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@$0A@@std@@@2@PEAU342@00AEBU?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@2@D@Z; std::_Tree<std::_Tmap_traits<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<ulong>,std::allocator<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>::_Buynode(std::_Tree_nod<std::_Tmap_traits<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<ulong>,std::allocator<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>::_Node *,std::_Tree_nod<std::_Tmap_traits<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<ulong>,std::allocator<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>::_Node *,std::_Tree_nod<std::_Tmap_traits<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<ulong>,std::allocator<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>::_Node *,std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>> const &,char)
0x18000f158  mov     r9, rax
0x18000f15b  inc     qword ptr [rbx+10h]
0x18000f15f  mov     rax, [rbx+8]
0x18000f163  xor     r11d, r11d
0x18000f166  cmp     rdi, rax
0x18000f169  jnz     short loc_18000F17C
0x18000f16b  mov     [rax+8], r9
0x18000f16f  mov     rax, [rbx+8]
0x18000f173  mov     [rax], r9
0x18000f176  mov     rax, [rbx+8]
0x18000f17a  jmp     short loc_18000F1A0
0x18000f17c  test    sil, sil
0x18000f17f  jz      short loc_18000F192
0x18000f181  mov     [rdi], r9
0x18000f184  mov     rax, [rbx+8]
0x18000f188  cmp     rdi, [rax]
0x18000f18b  jnz     short loc_18000F1A4
0x18000f18d  mov     [rax], r9
0x18000f190  jmp     short loc_18000F1A4
0x18000f192  mov     [rdi+10h], r9
0x18000f196  mov     rax, [rbx+8]
0x18000f19a  cmp     rdi, [rax+10h]
0x18000f19e  jnz     short loc_18000F1A4
0x18000f1a0  mov     [rax+10h], r9
0x18000f1a4  mov     rdx, r9
0x18000f1a7  lea     r8, [r9+8]
0x18000f1ab  mov     rax, [r8]
0x18000f1ae  cmp     [rax+38h], r11b
0x18000f1b2  jnz     loc_18000F37D
0x18000f1b8  mov     rax, [r8]
0x18000f1bb  mov     r10, [rax+8]
0x18000f1bf  mov     rcx, [r10]
0x18000f1c2  cmp     rax, rcx
0x18000f1c5  jnz     loc_18000F291
0x18000f1cb  mov     rcx, [r10+10h]
0x18000f1cf  cmp     [rcx+38h], r11b
0x18000f1d3  jz      loc_18000F297
0x18000f1d9  cmp     rdx, [rax+10h]
0x18000f1dd  jnz     short loc_18000F22C
0x18000f1df  mov     rdx, rax
0x18000f1e2  mov     rcx, [rax+10h]
0x18000f1e6  mov     rax, [rcx]
0x18000f1e9  mov     [rdx+10h], rax
0x18000f1ed  mov     rax, [rcx]
0x18000f1f0  cmp     [rax+39h], r11b
0x18000f1f4  jnz     short loc_18000F1FA
0x18000f1f6  mov     [rax+8], rdx
0x18000f1fa  lea     r8, [rdx+8]
0x18000f1fe  mov     rax, [r8]
0x18000f201  mov     [rcx+8], rax
0x18000f205  mov     rax, [rbx+8]
0x18000f209  cmp     rdx, [rax+8]
0x18000f20d  jnz     short loc_18000F215
0x18000f20f  mov     [rax+8], rcx
0x18000f213  jmp     short loc_18000F226
0x18000f215  mov     rax, [r8]
0x18000f218  cmp     rdx, [rax]
0x18000f21b  jnz     short loc_18000F222
0x18000f21d  mov     [rax], rcx
0x18000f220  jmp     short loc_18000F226
0x18000f222  mov     [rax+10h], rcx
0x18000f226  mov     [rcx], rdx
0x18000f229  mov     [r8], rcx
0x18000f22c  mov     rax, [r8]
0x18000f22f  mov     byte ptr [rax+38h], 1
0x18000f233  mov     rax, [r8]
0x18000f236  mov     rcx, [rax+8]
0x18000f23a  mov     [rcx+38h], r11b
0x18000f23e  mov     rax, [r8]
0x18000f241  mov     rcx, [rax+8]
0x18000f245  mov     r8, [rcx]
0x18000f248  mov     rax, [r8+10h]
0x18000f24c  mov     [rcx], rax
0x18000f24f  mov     rax, [r8+10h]
0x18000f253  cmp     [rax+39h], r11b
0x18000f257  jnz     short loc_18000F25D
0x18000f259  mov     [rax+8], rcx
0x18000f25d  mov     rax, [rcx+8]
0x18000f261  mov     [r8+8], rax
0x18000f265  mov     rax, [rbx+8]
0x18000f269  cmp     rcx, [rax+8]
0x18000f26d  jnz     short loc_18000F275
0x18000f26f  mov     [rax+8], r8
0x18000f273  jmp     short loc_18000F288
0x18000f275  mov     rax, [rcx+8]
0x18000f279  cmp     rcx, [rax+10h]
0x18000f27d  jnz     short loc_18000F285
0x18000f27f  mov     [rax+10h], r8
0x18000f283  jmp     short loc_18000F288
0x18000f285  mov     [rax], r8
0x18000f288  mov     [r8+10h], rcx
0x18000f28c  jmp     loc_18000F368
0x18000f291  cmp     [rcx+38h], r11b
0x18000f295  jnz     short loc_18000F2B6
0x18000f297  mov     byte ptr [rax+38h], 1
0x18000f29b  mov     byte ptr [rcx+38h], 1
0x18000f29f  mov     rax, [r8]
0x18000f2a2  mov     rcx, [rax+8]
0x18000f2a6  mov     [rcx+38h], r11b
0x18000f2aa  mov     rax, [r8]
0x18000f2ad  mov     rdx, [rax+8]
0x18000f2b1  jmp     loc_18000F36C
0x18000f2b6  cmp     rdx, [rax]
0x18000f2b9  jnz     short loc_18000F30A
0x18000f2bb  mov     rdx, rax
0x18000f2be  mov     rcx, [rax]
0x18000f2c1  mov     rax, [rcx+10h]
0x18000f2c5  mov     [rdx], rax
0x18000f2c8  mov     rax, [rcx+10h]
0x18000f2cc  cmp     [rax+39h], r11b
0x18000f2d0  jnz     short loc_18000F2D6
0x18000f2d2  mov     [rax+8], rdx
0x18000f2d6  lea     r8, [rdx+8]
0x18000f2da  mov     rax, [r8]
0x18000f2dd  mov     [rcx+8], rax
0x18000f2e1  mov     rax, [rbx+8]
0x18000f2e5  cmp     rdx, [rax+8]
0x18000f2e9  jnz     short loc_18000F2F1
0x18000f2eb  mov     [rax+8], rcx
0x18000f2ef  jmp     short loc_18000F303
0x18000f2f1  mov     rax, [r8]
0x18000f2f4  cmp     rdx, [rax+10h]
0x18000f2f8  jnz     short loc_18000F300
0x18000f2fa  mov     [rax+10h], rcx
0x18000f2fe  jmp     short loc_18000F303
0x18000f300  mov     [rax], rcx
0x18000f303  mov     [rcx+10h], rdx
0x18000f307  mov     [r8], rcx
0x18000f30a  mov     rax, [r8]
0x18000f30d  mov     byte ptr [rax+38h], 1
0x18000f311  mov     rax, [r8]
0x18000f314  mov     rcx, [rax+8]
0x18000f318  mov     [rcx+38h], r11b
0x18000f31c  mov     rax, [r8]
0x18000f31f  mov     rcx, [rax+8]
0x18000f323  mov     r8, [rcx+10h]
0x18000f327  mov     rax, [r8]
0x18000f32a  mov     [rcx+10h], rax
0x18000f32e  mov     rax, [r8]
0x18000f331  cmp     [rax+39h], r11b
0x18000f335  jnz     short loc_18000F33B
0x18000f337  mov     [rax+8], rcx
0x18000f33b  mov     rax, [rcx+8]
0x18000f33f  mov     [r8+8], rax
0x18000f343  mov     rax, [rbx+8]
0x18000f347  cmp     rcx, [rax+8]
0x18000f34b  jnz     short loc_18000F353
0x18000f34d  mov     [rax+8], r8
0x18000f351  jmp     short loc_18000F365
0x18000f353  mov     rax, [rcx+8]
0x18000f357  cmp     rcx, [rax]
0x18000f35a  jnz     short loc_18000F361
0x18000f35c  mov     [rax], r8
0x18000f35f  jmp     short loc_18000F365
0x18000f361  mov     [rax+10h], r8
0x18000f365  mov     [r8], rcx
0x18000f368  mov     [rcx+8], r8
0x18000f36c  lea     r8, [rdx+8]
0x18000f370  mov     rcx, [r8]
0x18000f373  cmp     [rcx+38h], r11b
0x18000f377  jz      loc_18000F1B8
0x18000f37d  mov     rcx, [rbx+8]
0x18000f381  mov     rdx, [rcx+8]
0x18000f385  mov     byte ptr [rdx+38h], 1
0x18000f389  mov     [r14], r9
0x18000f38c  mov     rax, r14
0x18000f38f  mov     rcx, [rsp+0C8h+var_28]
0x18000f397  xor     rcx, rsp; StackCookie
0x18000f39a  call    __security_check_cookie
0x18000f39f  mov     rbx, [rsp+0C8h+arg_10]
0x18000f3a7  add     rsp, 0B0h
0x18000f3ae  pop     r14
0x18000f3b0  pop     rdi
0x18000f3b1  pop     rsi
0x18000f3b2  retn
```
