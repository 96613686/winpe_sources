# std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>,0>>::_Rehash_for_1(void)

- ea: `0x180021eac`
- end: `0x1800220d1`
- name: `?_Rehash_for_1@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@IEAAXXZ`
- size: `549`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023260`

## callees

- `0x180002e74`
- `0x18001282c`
- `0x180021870`
- `0x180021eac`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180021f6c`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180021f6c`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>,0>>::_Rehash_for_1(
        __int64 a1)
{
  __int64 v1; // rdx
  bool v3; // sf
  unsigned __int64 v4; // rdx
  unsigned __int64 v5; // rbx
  float v6; // xmm0_4
  float v7; // xmm0_4
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rcx
  _QWORD *v12; // rsi
  unsigned __int64 v13; // rcx
  __int64 v14; // rbx
  _QWORD *v15; // rax
  _QWORD *v16; // rcx
  __int64 v17; // r8
  unsigned __int64 i; // r9
  __int64 v19; // rdx
  __int64 v20; // r11
  __int64 v21; // r10
  _QWORD *v22; // rdx
  __int64 v23; // r8
  _QWORD *v24; // rbx
  _QWORD *v25; // r9
  _QWORD *v26; // r8
  _QWORD *v27; // rdx
  _QWORD *v28; // rbx
  _QWORD *v29; // r10
  _QWORD *v30; // r9
  _QWORD *v31; // r8
  _QWORD *v32; // rdx
  _QWORD *v33; // r9
  _QWORD *v34; // r8
  _QWORD *v35; // rdx
  __int64 v37; // [rsp+50h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 16);
  v3 = v1 + 1 < 0;
  v4 = v1 + 1;
  v5 = *(_QWORD *)(a1 + 56);
  if ( v3 )
    v6 = (float)(int)(v4 & 1 | (v4 >> 1)) + (float)(int)(v4 & 1 | (v4 >> 1));
  else
    v6 = (float)(int)v4;
  v7 = o_ceilf_0(v6 / *(float *)a1);
  v8 = 0;
  if ( v7 >= 9.223372e18 )
  {
    v7 = v7 - 9.223372e18;
    if ( v7 < 9.223372e18 )
      v8 = 0x8000000000000000uLL;
  }
  v9 = v8 + (unsigned int)(int)v7;
  v10 = 8;
  if ( v9 > 8 )
    v10 = v9;
  if ( v5 < v10 )
  {
    if ( v5 >= 0x200 || (v5 *= 8LL, v5 < v10) )
      v5 = v10;
  }
  LODWORD(v37) = 0;
  _BitScanReverse64(&v11, 0xFFFFFFFFFFFFFFFuLL);
  if ( v5 > 1LL << v11 )
    std::_Xlength_error("invalid hash bucket count");
  v12 = *(_QWORD **)(a1 + 8);
  LODWORD(v37) = 0;
  _BitScanReverse64(&v13, (v5 - 1) | 1);
  v14 = 1LL << ((unsigned __int8)v13 + 1);
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>>,std::_Iterator_base0>>>::_Assign_grow(
    a1 + 24,
    2 * v14,
    v12);
  *(_QWORD *)(a1 + 56) = v14;
  *(_QWORD *)(a1 + 48) = v14 - 1;
  v15 = **(_QWORD ***)(a1 + 8);
  v16 = v15;
  while ( v15 != v12 )
  {
    v16 = (_QWORD *)*v16;
    v17 = 0xCBF29CE484222325uLL;
    for ( i = 0; i < 8; ++i )
    {
      v19 = *((unsigned __int8 *)v15 + i + 16);
      v17 = 0x100000001B3LL * (v19 ^ v17);
    }
    v20 = *(_QWORD *)(a1 + 24);
    v21 = 2 * (v17 & *(_QWORD *)(a1 + 48));
    if ( *(_QWORD **)(v20 + 16 * (v17 & *(_QWORD *)(a1 + 48))) == v12 )
    {
      *(_QWORD *)(v20 + 16 * (v17 & *(_QWORD *)(a1 + 48))) = v15;
LABEL_21:
      *(_QWORD *)(v20 + 8 * v21 + 8) = v15;
      goto LABEL_29;
    }
    v22 = *(_QWORD **)(v20 + 16 * (v17 & *(_QWORD *)(a1 + 48)) + 8);
    v23 = v15[2];
    if ( v23 == v22[2] )
    {
      v24 = (_QWORD *)*v22;
      if ( (_QWORD *)*v22 != v15 )
      {
        v25 = (_QWORD *)v15[1];
        *v25 = v16;
        v26 = (_QWORD *)v16[1];
        *v26 = v24;
        v27 = (_QWORD *)v24[1];
        *v27 = v15;
        v24[1] = v26;
        v16[1] = v25;
        v15[1] = v27;
      }
      goto LABEL_21;
    }
    while ( 1 )
    {
      v28 = v22 + 1;
      if ( *(_QWORD **)(v20 + 8 * v21) == v22 )
        break;
      v22 = (_QWORD *)*v28;
      if ( v23 == *(_QWORD *)(*v28 + 16LL) )
      {
        v29 = (_QWORD *)*v22;
        v30 = (_QWORD *)v15[1];
        *v30 = v16;
        v31 = (_QWORD *)v16[1];
        *v31 = v29;
        v32 = (_QWORD *)v29[1];
        *v32 = v15;
        v29[1] = v31;
        v16[1] = v30;
        v15[1] = v32;
        goto LABEL_29;
      }
    }
    v33 = (_QWORD *)v15[1];
    *v33 = v16;
    v34 = (_QWORD *)v16[1];
    *v34 = v22;
    v35 = (_QWORD *)*v28;
    *v35 = v15;
    *v28 = v34;
    v16[1] = v33;
    v15[1] = v35;
    *(_QWORD *)(v20 + 8 * v21) = v15;
LABEL_29:
    v15 = v16;
  }
  v37 = 0;
  return std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>,0>>::_Clear_guard::~_Clear_guard(&v37);
}

```

## disassembly

```asm
0x180021eac  push    rbx
0x180021eae  push    rsi
0x180021eaf  push    rdi
0x180021eb0  push    r14
0x180021eb2  sub     rsp, 28h
0x180021eb6  mov     rdx, [rcx+10h]
0x180021eba  mov     rdi, rcx
0x180021ebd  add     rdx, 1
0x180021ec1  mov     rbx, [rcx+38h]
0x180021ec5  xorps   xmm0, xmm0
0x180021ec8  js      short loc_180021ED1
0x180021eca  cvtsi2ss xmm0, rdx
0x180021ecf  jmp     short loc_180021EE6
0x180021ed1  mov     rax, rdx
0x180021ed4  and     edx, 1
0x180021ed7  shr     rax, 1
0x180021eda  or      rax, rdx
0x180021edd  cvtsi2ss xmm0, rax
0x180021ee2  addss   xmm0, xmm0
0x180021ee6  divss   xmm0, dword ptr [rcx]; X
0x180021eea  call    _o_ceilf_0
0x180021eef  movss   xmm1, cs:__real@5f000000
0x180021ef7  xor     ecx, ecx
0x180021ef9  comiss  xmm0, xmm1
0x180021efc  jb      short loc_180021F14
0x180021efe  subss   xmm0, xmm1
0x180021f02  comiss  xmm0, xmm1
0x180021f05  jnb     short loc_180021F14
0x180021f07  mov     rax, 8000000000000000h
0x180021f11  mov     rcx, rax
0x180021f14  cvttss2si rax, xmm0
0x180021f19  add     rax, rcx
0x180021f1c  mov     ecx, 8
0x180021f21  cmp     rax, rcx
0x180021f24  cmova   rcx, rax
0x180021f28  cmp     rbx, rcx
0x180021f2b  jnb     short loc_180021F42
0x180021f2d  cmp     rbx, 200h
0x180021f34  jnb     short loc_180021F3F
0x180021f36  shl     rbx, 3
0x180021f3a  cmp     rbx, rcx
0x180021f3d  jnb     short loc_180021F42
0x180021f3f  mov     rbx, rcx
0x180021f42  mov     rax, 0FFFFFFFFFFFFFFFh
0x180021f4c  mov     dword ptr [rsp+48h+arg_0], 0
0x180021f54  bsr     rcx, rax
0x180021f58  mov     eax, 1
0x180021f5d  shl     rax, cl
0x180021f60  cmp     rbx, rax
0x180021f63  jbe     short loc_180021F73
0x180021f65  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x180021f6c  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180021f73  mov     rsi, [rdi+8]
0x180021f77  lea     rax, [rbx-1]
0x180021f7b  or      rax, 1
0x180021f7f  mov     dword ptr [rsp+48h+arg_0], 0
0x180021f87  bsr     rcx, rax
0x180021f8b  mov     ebx, 1
0x180021f90  mov     r8, rsi
0x180021f93  inc     ecx
0x180021f95  shl     rbx, cl
0x180021f98  lea     rcx, [rdi+18h]
0x180021f9c  lea     rdx, [rbx+rbx]
0x180021fa0  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>>,std::_Iterator_base0>)
0x180021fa5  lea     rax, [rbx-1]
0x180021fa9  mov     [rdi+38h], rbx
0x180021fad  mov     [rdi+30h], rax
0x180021fb1  mov     rax, [rdi+8]
0x180021fb5  mov     rax, [rax]
0x180021fb8  mov     rcx, rax
0x180021fbb  cmp     rax, rsi
0x180021fbe  jz      loc_1800220B4
0x180021fc4  mov     rcx, [rcx]
0x180021fc7  mov     r8, 0CBF29CE484222325h
0x180021fd1  xor     r9d, r9d
0x180021fd4  movzx   edx, byte ptr [r9+rax+10h]
0x180021fda  mov     r10, 100000001B3h
0x180021fe4  xor     r8, rdx
0x180021fe7  inc     r9
0x180021fea  imul    r8, r10
0x180021fee  cmp     r9, 8
0x180021ff2  jb      short loc_180021FD4
0x180021ff4  mov     r10, [rdi+30h]
0x180021ff8  mov     r11, [rdi+18h]
0x180021ffc  and     r10, r8
0x180021fff  add     r10, r10
0x180022002  cmp     [r11+r10*8], rsi
0x180022006  jnz     short loc_180022016
0x180022008  mov     [r11+r10*8], rax
0x18002200c  mov     [r11+r10*8+8], rax
0x180022011  jmp     loc_1800220AC
0x180022016  mov     rdx, [r11+r10*8+8]
0x18002201b  mov     r8, [rax+10h]
0x18002201f  cmp     r8, [rdx+10h]
0x180022023  jnz     short loc_180022050
0x180022025  mov     rbx, [rdx]
0x180022028  cmp     rbx, rax
0x18002202b  jz      short loc_18002200C
0x18002202d  mov     r9, [rax+8]
0x180022031  mov     [r9], rcx
0x180022034  mov     r8, [rcx+8]
0x180022038  mov     [r8], rbx
0x18002203b  mov     rdx, [rbx+8]
0x18002203f  mov     [rdx], rax
0x180022042  mov     [rbx+8], r8
0x180022046  mov     [rcx+8], r9
0x18002204a  mov     [rax+8], rdx
0x18002204e  jmp     short loc_18002200C
0x180022050  lea     rbx, [rdx+8]
0x180022054  cmp     [r11+r10*8], rdx
0x180022058  jz      short loc_180022089
0x18002205a  mov     rdx, [rbx]
0x18002205d  cmp     r8, [rdx+10h]
0x180022061  jnz     short loc_180022050
0x180022063  mov     r10, [rdx]
0x180022066  mov     r9, [rax+8]
0x18002206a  mov     [r9], rcx
0x18002206d  mov     r8, [rcx+8]
0x180022071  mov     [r8], r10
0x180022074  mov     rdx, [r10+8]
0x180022078  mov     [rdx], rax
0x18002207b  mov     [r10+8], r8
0x18002207f  mov     [rcx+8], r9
0x180022083  mov     [rax+8], rdx
0x180022087  jmp     short loc_1800220AC
0x180022089  mov     r9, [rax+8]
0x18002208d  mov     [r9], rcx
0x180022090  mov     r8, [rcx+8]
0x180022094  mov     [r8], rdx
0x180022097  mov     rdx, [rbx]
0x18002209a  mov     [rdx], rax
0x18002209d  mov     [rbx], r8
0x1800220a0  mov     [rcx+8], r9
0x1800220a4  mov     [rax+8], rdx
0x1800220a8  mov     [r11+r10*8], rax
0x1800220ac  mov     rax, rcx
0x1800220af  jmp     loc_180021FBB
0x1800220b4  lea     rcx, [rsp+48h+arg_0]
0x1800220b9  mov     [rsp+48h+arg_0], 0
0x1800220c2  call    ??1_Clear_guard@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>,0>>::_Clear_guard::~_Clear_guard(void)
0x1800220c7  add     rsp, 28h
0x1800220cb  pop     r14
0x1800220cd  pop     rdi
0x1800220ce  pop     rsi
0x1800220cf  pop     rbx
0x1800220d0  retn
```
