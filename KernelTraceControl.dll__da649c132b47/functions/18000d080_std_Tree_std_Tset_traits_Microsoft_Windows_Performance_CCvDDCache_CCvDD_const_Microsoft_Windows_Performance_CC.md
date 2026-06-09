# std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,0>>::insert(Microsoft::Windows::Performance::CCvDDCache::CCvDD const * const &)

- ea: `0x18000d080`
- end: `0x18000d249`
- name: `?insert@?$_Tree@V?$_Tset_traits@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessCCvDDPtrByImageId@2345@V?$allocator@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@$0A@@std@@@std@@QEAA?AU?$pair@Viterator@?$_Tree@V?$_Tset_traits@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessCCvDDPtrByImageId@2345@V?$allocator@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@$0A@@std@@@std@@_N@2@AEBQEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@Z`
- size: `457`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800093c0`

## callees

- `0x18000d080`
- `0x18000dd64`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,0>>::insert(
        __int64 a1,
        __int64 a2,
        __int64 *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  int v6; // r15d
  _QWORD *v7; // r10
  bool v8; // r11
  __int64 *v9; // r9
  __int64 v10; // rdi
  __int64 v11; // rax
  unsigned int v12; // ecx
  _QWORD *v13; // rax
  unsigned int v14; // ecx
  unsigned int v15; // edx
  __int64 v16; // r8
  unsigned __int16 *v17; // rax
  int v18; // ecx
  int v19; // edx
  __int64 v20; // rcx
  __int64 i; // rcx
  __int64 v22; // rcx
  __int64 v23; // rdx
  unsigned int v24; // r9d
  unsigned int v25; // r9d
  __int64 v26; // r9
  unsigned __int16 *v27; // rcx
  __int64 v28; // r9
  int v29; // edx
  _QWORD *v30; // rax
  char v32; // [rsp+50h] [rbp+8h] BYREF

  v3 = *(_QWORD **)(a1 + 8);
  v4 = (__int64)a3;
  v6 = a1;
  v7 = v3;
  v8 = 1;
  v9 = (__int64 *)v3[1];
  if ( !*((_BYTE *)v9 + 33) )
  {
    v10 = *a3;
    while ( 1 )
    {
      v11 = v9[3];
      v7 = v9;
      v12 = *(_DWORD *)(v11 + 156);
      if ( *(_DWORD *)(v10 + 156) < v12 )
        break;
      if ( *(_DWORD *)(v10 + 156) > v12 )
        goto LABEL_6;
      v14 = *(_DWORD *)(v10 + 160);
      v15 = *(_DWORD *)(v11 + 160);
      if ( v14 < v15 )
        break;
      if ( v14 > v15 )
      {
LABEL_6:
        v8 = 0;
      }
      else
      {
        if ( *(_QWORD *)(v11 + 72) < 8u )
          v16 = v11 + 48;
        else
          v16 = *(_QWORD *)(v11 + 48);
        if ( *(_QWORD *)(v10 + 72) < 8u )
          v17 = (unsigned __int16 *)(v10 + 48);
        else
          v17 = *(unsigned __int16 **)(v10 + 48);
        a3 = (__int64 *)(v16 - (_QWORD)v17);
        do
        {
          v18 = *(unsigned __int16 *)((char *)a3 + (_QWORD)v17);
          v19 = *v17 - v18;
          if ( v19 )
            break;
          ++v17;
        }
        while ( v18 );
        v8 = v19 < 0;
        if ( v19 < 0 )
          goto LABEL_24;
      }
      v9 = (__int64 *)v9[2];
LABEL_8:
      if ( *((_BYTE *)v9 + 33) )
        goto LABEL_9;
    }
    v8 = 1;
LABEL_24:
    v9 = (__int64 *)*v9;
    goto LABEL_8;
  }
LABEL_9:
  v13 = v7;
  if ( v8 )
  {
    if ( v7 == (_QWORD *)*v3 )
    {
      LOBYTE(a3) = 1;
LABEL_52:
      v30 = (_QWORD *)std::_Tree<std::_Tset_traits<unsigned short const *,std::less<unsigned short const *>,std::allocator<unsigned short const *>,0>>::_Insert(
                        v6,
                        (unsigned int)&v32,
                        (_DWORD)a3,
                        (_DWORD)v7,
                        v4);
      *(_BYTE *)(a2 + 8) = 1;
      *(_QWORD *)a2 = *v30;
      return a2;
    }
    if ( *((_BYTE *)v7 + 33) )
    {
      v13 = (_QWORD *)v7[2];
    }
    else
    {
      v20 = *v7;
      if ( *(_BYTE *)(*v7 + 33LL) )
      {
        for ( i = v7[1]; !*(_BYTE *)(i + 33) && v13 == *(_QWORD **)i; i = *(_QWORD *)(i + 8) )
          v13 = (_QWORD *)i;
        if ( !*((_BYTE *)v13 + 33) )
          v13 = (_QWORD *)i;
      }
      else
      {
        do
        {
          v13 = (_QWORD *)v20;
          v20 = *(_QWORD *)(v20 + 16);
        }
        while ( !*(_BYTE *)(v20 + 33) );
      }
    }
  }
  v22 = *(_QWORD *)v4;
  v23 = v13[3];
  v24 = *(_DWORD *)(*(_QWORD *)v4 + 156LL);
  LODWORD(a3) = *(_DWORD *)(v23 + 156);
  if ( (unsigned int)a3 < v24 )
    goto LABEL_51;
  if ( (unsigned int)a3 <= v24 )
  {
    LODWORD(a3) = *(_DWORD *)(v23 + 160);
    v25 = *(_DWORD *)(v22 + 160);
    if ( (unsigned int)a3 < v25 )
      goto LABEL_51;
    if ( (unsigned int)a3 <= v25 )
    {
      v26 = *(_QWORD *)(v22 + 72) < 8u ? v22 + 48 : *(_QWORD *)(v22 + 48);
      v27 = *(_QWORD *)(v23 + 72) < 8u ? (unsigned __int16 *)(v23 + 48) : *(unsigned __int16 **)(v23 + 48);
      v28 = v26 - (_QWORD)v27;
      do
      {
        LODWORD(a3) = *(unsigned __int16 *)((char *)v27 + v28);
        v29 = *v27 - (_DWORD)a3;
        if ( v29 )
          break;
        ++v27;
      }
      while ( (_DWORD)a3 );
      if ( v29 < 0 )
      {
LABEL_51:
        LOBYTE(a3) = v8;
        goto LABEL_52;
      }
    }
  }
  *(_QWORD *)a2 = v13;
  *(_BYTE *)(a2 + 8) = 0;
  return a2;
}

```

## disassembly

```asm
0x18000d080  mov     [rsp+arg_8], rbx
0x18000d085  mov     [rsp+arg_10], rsi
0x18000d08a  push    rdi
0x18000d08b  push    r14
0x18000d08d  push    r15
0x18000d08f  sub     rsp, 30h
0x18000d093  mov     rsi, [rcx+8]
0x18000d097  mov     r14, r8
0x18000d09a  mov     rbx, rdx
0x18000d09d  mov     r15, rcx
0x18000d0a0  mov     r10, rsi
0x18000d0a3  mov     r11b, 1
0x18000d0a6  mov     r9, [rsi+8]
0x18000d0aa  cmp     byte ptr [r9+21h], 0
0x18000d0af  jnz     short loc_18000D0DE
0x18000d0b1  mov     rdi, [r8]
0x18000d0b4  mov     rax, [r9+18h]
0x18000d0b8  mov     r10, r9
0x18000d0bb  mov     ecx, [rax+9Ch]
0x18000d0c1  cmp     [rdi+9Ch], ecx
0x18000d0c7  jnb     short loc_18000D0CE
0x18000d0c9  mov     r11b, 1
0x18000d0cc  jmp     short loc_18000D14D
0x18000d0ce  jbe     short loc_18000D0F7
0x18000d0d0  xor     r11b, r11b
0x18000d0d3  mov     r9, [r9+10h]
0x18000d0d7  cmp     byte ptr [r9+21h], 0
0x18000d0dc  jz      short loc_18000D0B4
0x18000d0de  mov     rax, r10
0x18000d0e1  test    r11b, r11b
0x18000d0e4  jz      loc_18000D197
0x18000d0ea  cmp     r10, [rsi]
0x18000d0ed  jnz     short loc_18000D152
0x18000d0ef  mov     r8b, 1
0x18000d0f2  jmp     loc_18000D213
0x18000d0f7  mov     ecx, [rdi+0A0h]
0x18000d0fd  mov     edx, [rax+0A0h]
0x18000d103  cmp     ecx, edx
0x18000d105  jb      short loc_18000D0C9
0x18000d107  ja      short loc_18000D0D0
0x18000d109  cmp     qword ptr [rax+48h], 8
0x18000d10e  jb      short loc_18000D116
0x18000d110  mov     r8, [rax+30h]
0x18000d114  jmp     short loc_18000D11A
0x18000d116  lea     r8, [rax+30h]
0x18000d11a  cmp     qword ptr [rdi+48h], 8
0x18000d11f  jb      short loc_18000D127
0x18000d121  mov     rax, [rdi+30h]
0x18000d125  jmp     short loc_18000D12B
0x18000d127  lea     rax, [rdi+30h]
0x18000d12b  sub     r8, rax
0x18000d12e  movzx   edx, word ptr [rax]
0x18000d131  movzx   ecx, word ptr [rax+r8]
0x18000d136  sub     edx, ecx
0x18000d138  jnz     short loc_18000D142
0x18000d13a  add     rax, 2
0x18000d13e  test    ecx, ecx
0x18000d140  jnz     short loc_18000D12E
0x18000d142  test    edx, edx
0x18000d144  sets    r11b
0x18000d148  test    r11b, r11b
0x18000d14b  jz      short loc_18000D0D3
0x18000d14d  mov     r9, [r9]
0x18000d150  jmp     short loc_18000D0D7
0x18000d152  cmp     byte ptr [r10+21h], 0
0x18000d157  jz      short loc_18000D15F
0x18000d159  mov     rax, [r10+10h]
0x18000d15d  jmp     short loc_18000D197
0x18000d15f  mov     rcx, [r10]
0x18000d162  cmp     byte ptr [rcx+21h], 0
0x18000d166  jnz     short loc_18000D177
0x18000d168  mov     rax, rcx
0x18000d16b  mov     rcx, [rcx+10h]
0x18000d16f  cmp     byte ptr [rcx+21h], 0
0x18000d173  jz      short loc_18000D168
0x18000d175  jmp     short loc_18000D197
0x18000d177  mov     rcx, [r10+8]
0x18000d17b  jmp     short loc_18000D189
0x18000d17d  cmp     rax, [rcx]
0x18000d180  jnz     short loc_18000D18F
0x18000d182  mov     rax, rcx
0x18000d185  mov     rcx, [rcx+8]
0x18000d189  cmp     byte ptr [rcx+21h], 0
0x18000d18d  jz      short loc_18000D17D
0x18000d18f  cmp     byte ptr [rax+21h], 0
0x18000d193  cmovz   rax, rcx
0x18000d197  mov     rcx, [r14]
0x18000d19a  mov     rdx, [rax+18h]
0x18000d19e  mov     r9d, [rcx+9Ch]
0x18000d1a5  mov     r8d, [rdx+9Ch]
0x18000d1ac  cmp     r8d, r9d
0x18000d1af  jb      short loc_18000D210
0x18000d1b1  ja      short loc_18000D207
0x18000d1b3  mov     r8d, [rdx+0A0h]
0x18000d1ba  mov     r9d, [rcx+0A0h]
0x18000d1c1  cmp     r8d, r9d
0x18000d1c4  jb      short loc_18000D210
0x18000d1c6  ja      short loc_18000D207
0x18000d1c8  cmp     qword ptr [rcx+48h], 8
0x18000d1cd  jb      short loc_18000D1D5
0x18000d1cf  mov     r9, [rcx+30h]
0x18000d1d3  jmp     short loc_18000D1D9
0x18000d1d5  lea     r9, [rcx+30h]
0x18000d1d9  cmp     qword ptr [rdx+48h], 8
0x18000d1de  jb      short loc_18000D1E6
0x18000d1e0  mov     rcx, [rdx+30h]
0x18000d1e4  jmp     short loc_18000D1EA
0x18000d1e6  lea     rcx, [rdx+30h]
0x18000d1ea  sub     r9, rcx
0x18000d1ed  movzx   edx, word ptr [rcx]
0x18000d1f0  movzx   r8d, word ptr [rcx+r9]
0x18000d1f5  sub     edx, r8d
0x18000d1f8  jnz     short loc_18000D203
0x18000d1fa  add     rcx, 2
0x18000d1fe  test    r8d, r8d
0x18000d201  jnz     short loc_18000D1ED
0x18000d203  test    edx, edx
0x18000d205  js      short loc_18000D210
0x18000d207  mov     [rbx], rax
0x18000d20a  mov     byte ptr [rbx+8], 0
0x18000d20e  jmp     short loc_18000D232
0x18000d210  mov     r8b, r11b
0x18000d213  mov     r9, r10
0x18000d216  mov     [rsp+48h+var_28], r14
0x18000d21b  lea     rdx, [rsp+48h+arg_0]
0x18000d220  mov     rcx, r15
0x18000d223  call    ?_Insert@?$_Tree@V?$_Tset_traits@PEBGU?$less@PEBG@std@@V?$allocator@PEBG@2@$0A@@std@@@std@@IEAA?AViterator@12@_NPEAU_Node@?$_Tree_nod@V?$_Tset_traits@PEBGU?$less@PEBG@std@@V?$allocator@PEBG@2@$0A@@std@@@2@AEBQEBG@Z; std::_Tree<std::_Tset_traits<ushort const *,std::less<ushort const *>,std::allocator<ushort const *>,0>>::_Insert(bool,std::_Tree_nod<std::_Tset_traits<ushort const *,std::less<ushort const *>,std::allocator<ushort const *>,0>>::_Node *,ushort const * const &)
0x18000d228  mov     byte ptr [rbx+8], 1
0x18000d22c  mov     rcx, [rax]
0x18000d22f  mov     [rbx], rcx
0x18000d232  mov     rsi, [rsp+48h+arg_10]
0x18000d237  mov     rax, rbx
0x18000d23a  mov     rbx, [rsp+48h+arg_8]
0x18000d23f  add     rsp, 30h
0x18000d243  pop     r15
0x18000d245  pop     r14
0x18000d247  pop     rdi
0x18000d248  retn
```
