# std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>,0>>::insert(SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback * const &)

- ea: `0x180023260`
- end: `0x18002344c`
- name: `?insert@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@@std@@@std@@@std@@_N@2@AEBQEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@@Z`
- size: `492`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800102cc`
- `0x18001d6d4`

## callees

- `0x180002890`
- `0x180021eac`
- `0x180023260`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002330b`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002330b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>,0>>::insert(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v6; // rbp
  unsigned __int64 v7; // rcx
  char v8; // r14
  __int64 v9; // rdx
  _QWORD *v10; // rbx
  _QWORD *v11; // rsi
  __int64 v12; // rcx
  float v13; // xmm0_4
  __int64 v14; // rcx
  float v15; // xmm1_4
  __int64 v16; // r8
  _QWORD *v17; // rcx
  _QWORD *v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rax
  _QWORD *v21; // r8
  __int64 result; // rax

  v6 = 0xCBF29CE484222325uLL;
  v7 = 0;
  v8 = 1;
  do
    v6 = 0x100000001B3LL * (*((unsigned __int8 *)a3 + v7++) ^ (unsigned __int64)v6);
  while ( v7 < 8 );
  v9 = *(_QWORD *)(a1 + 24);
  v10 = *(_QWORD **)(v9 + 16 * (*(_QWORD *)(a1 + 48) & v6) + 8);
  v11 = *(_QWORD **)(a1 + 8);
  if ( v10 == v11 )
  {
LABEL_8:
    if ( *(_QWORD *)(a1 + 16) == 0xAAAAAAAAAAAAAAALL )
      std::_Xlength_error("unordered_map/set too long");
    v10 = operator new(0x18u);
    v10[2] = *a3;
    v12 = *(_QWORD *)(a1 + 16) + 1LL;
    if ( v12 < 0 )
      v13 = (float)(v12 & 1 | (unsigned int)((unsigned __int64)v12 >> 1))
          + (float)(v12 & 1 | (unsigned int)((unsigned __int64)v12 >> 1));
    else
      v13 = (float)(int)v12;
    v14 = *(_QWORD *)(a1 + 56);
    if ( v14 < 0 )
      v15 = (float)(v14 & 1 | (unsigned int)((unsigned __int64)v14 >> 1))
          + (float)(v14 & 1 | (unsigned int)((unsigned __int64)v14 >> 1));
    else
      v15 = (float)(int)v14;
    if ( (float)(v13 / v15) > *(float *)a1 )
    {
      std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>,0>>::_Rehash_for_1(a1);
      v16 = *(_QWORD *)(a1 + 24);
      v17 = *(_QWORD **)(v16 + 16 * (*(_QWORD *)(a1 + 48) & v6) + 8);
      v11 = *(_QWORD **)(a1 + 8);
      if ( v17 != v11 )
      {
        while ( v10[2] != v17[2] )
        {
          if ( v17 == *(_QWORD **)(v16 + 16 * (*(_QWORD *)(a1 + 48) & v6)) )
          {
            v11 = v17;
            goto LABEL_23;
          }
          v17 = (_QWORD *)v17[1];
        }
        v11 = (_QWORD *)*v17;
      }
    }
LABEL_23:
    v18 = (_QWORD *)v11[1];
    ++*(_QWORD *)(a1 + 16);
    *v10 = v11;
    v10[1] = v18;
    *v18 = v10;
    v11[1] = v10;
    v19 = *(_QWORD *)(a1 + 24);
    v20 = 2 * (v6 & *(_QWORD *)(a1 + 48));
    v21 = *(_QWORD **)(v19 + 16 * (v6 & *(_QWORD *)(a1 + 48)));
    if ( v21 == *(_QWORD **)(a1 + 8) )
    {
      *(_QWORD *)(v19 + 16 * (v6 & *(_QWORD *)(a1 + 48))) = v10;
    }
    else
    {
      if ( v21 == v11 )
      {
        *(_QWORD *)(v19 + 16 * (v6 & *(_QWORD *)(a1 + 48))) = v10;
        goto LABEL_31;
      }
      if ( *(_QWORD **)(v19 + 16 * (v6 & *(_QWORD *)(a1 + 48)) + 8) != v18 )
        goto LABEL_31;
    }
    *(_QWORD *)(v19 + 8 * v20 + 8) = v10;
    goto LABEL_31;
  }
  while ( *a3 != v10[2] )
  {
    if ( v10 == *(_QWORD **)(v9 + 16 * (*(_QWORD *)(a1 + 48) & v6)) )
    {
      v11 = v10;
      goto LABEL_8;
    }
    v10 = (_QWORD *)v10[1];
  }
  v8 = 0;
LABEL_31:
  result = a2;
  *(_QWORD *)a2 = v10;
  *(_BYTE *)(a2 + 8) = v8;
  return result;
}

```

## disassembly

```asm
0x180023260  push    rbx
0x180023262  push    rbp
0x180023263  push    rsi
0x180023264  push    rdi
0x180023265  push    r12
0x180023267  push    r13
0x180023269  push    r14
0x18002326b  push    r15
0x18002326d  sub     rsp, 38h
0x180023271  mov     r12, r8
0x180023274  mov     r15, rdx
0x180023277  mov     rdi, rcx
0x18002327a  mov     rbp, 0CBF29CE484222325h
0x180023284  xor     ecx, ecx
0x180023286  lea     r14d, [rcx+1]
0x18002328a  lea     r13d, [rcx+8]
0x18002328e  movzx   eax, byte ptr [r8+rcx]
0x180023293  xor     rbp, rax
0x180023296  mov     rdx, 100000001B3h
0x1800232a0  imul    rbp, rdx
0x1800232a4  add     rcx, r14
0x1800232a7  cmp     rcx, r13
0x1800232aa  jb      short loc_18002328E
0x1800232ac  mov     rcx, rbp
0x1800232af  and     rcx, [rdi+30h]
0x1800232b3  mov     rdx, [rdi+18h]
0x1800232b7  mov     rax, rcx
0x1800232ba  add     rax, rax
0x1800232bd  mov     rbx, [rdx+rax*8+8]
0x1800232c2  lea     rax, [rdi+8]
0x1800232c6  mov     rsi, [rax]
0x1800232c9  cmp     rbx, rsi
0x1800232cc  jz      short loc_1800232F4
0x1800232ce  add     rcx, rcx
0x1800232d1  mov     rax, [rdx+rcx*8]
0x1800232d5  mov     rcx, [r8]
0x1800232d8  cmp     rcx, [rbx+10h]
0x1800232dc  jz      loc_18002342B
0x1800232e2  cmp     rbx, rax
0x1800232e5  jz      short loc_1800232ED
0x1800232e7  mov     rbx, [rbx+8]
0x1800232eb  jmp     short loc_1800232D8
0x1800232ed  mov     rsi, rbx
0x1800232f0  lea     rax, [rdi+8]
0x1800232f4  mov     rcx, 0AAAAAAAAAAAAAAAh
0x1800232fe  cmp     [rdi+10h], rcx
0x180023302  jnz     short loc_180023312
0x180023304  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x18002330b  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180023312  mov     [rsp+78h+var_58], rax
0x180023317  mov     [rsp+78h+var_50], 0
0x180023320  mov     ecx, 18h; Size
0x180023325  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002332a  mov     rbx, rax
0x18002332d  mov     [rsp+78h+var_50], rax
0x180023332  mov     rcx, [r12]
0x180023336  mov     [rax+10h], rcx
0x18002333a  mov     rcx, [rdi+10h]
0x18002333e  add     rcx, r14
0x180023341  xorps   xmm0, xmm0
0x180023344  js      short loc_18002334D
0x180023346  cvtsi2ss xmm0, rcx
0x18002334b  jmp     short loc_180023362
0x18002334d  mov     rax, rcx
0x180023350  shr     rax, 1
0x180023353  and     rcx, r14
0x180023356  or      rax, rcx
0x180023359  cvtsi2ss xmm0, rax
0x18002335e  addss   xmm0, xmm0
0x180023362  mov     rcx, [rdi+38h]
0x180023366  xorps   xmm1, xmm1
0x180023369  test    rcx, rcx
0x18002336c  js      short loc_180023375
0x18002336e  cvtsi2ss xmm1, rcx
0x180023373  jmp     short loc_18002338A
0x180023375  mov     rax, rcx
0x180023378  shr     rax, 1
0x18002337b  and     rcx, r14
0x18002337e  or      rax, rcx
0x180023381  cvtsi2ss xmm1, rax
0x180023386  addss   xmm1, xmm1
0x18002338a  divss   xmm0, xmm1
0x18002338e  comiss  xmm0, dword ptr [rdi]
0x180023391  jbe     short loc_1800233DE
0x180023393  mov     rcx, rdi
0x180023396  call    ?_Rehash_for_1@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@IEAAXXZ; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>,0>>::_Rehash_for_1(void)
0x18002339b  mov     rdx, rbp
0x18002339e  and     rdx, [rdi+30h]
0x1800233a2  mov     r8, [rdi+18h]
0x1800233a6  mov     rax, rdx
0x1800233a9  add     rax, rax
0x1800233ac  mov     rcx, [r8+rax*8+8]
0x1800233b1  mov     rsi, [rdi+8]
0x1800233b5  cmp     rcx, rsi
0x1800233b8  jz      short loc_1800233DE
0x1800233ba  add     rdx, rdx
0x1800233bd  mov     rax, [r8+rdx*8]
0x1800233c1  mov     rdx, [rbx+10h]
0x1800233c5  cmp     rdx, [rcx+10h]
0x1800233c9  jz      short loc_1800233DB
0x1800233cb  cmp     rcx, rax
0x1800233ce  jz      short loc_1800233D6
0x1800233d0  mov     rcx, [rcx+8]
0x1800233d4  jmp     short loc_1800233C5
0x1800233d6  mov     rsi, rcx
0x1800233d9  jmp     short loc_1800233DE
0x1800233db  mov     rsi, [rcx]
0x1800233de  mov     rdx, [rsi+8]
0x1800233e2  add     [rdi+10h], r14
0x1800233e6  mov     [rbx], rsi
0x1800233e9  mov     [rbx+8], rdx
0x1800233ed  mov     [rdx], rbx
0x1800233f0  mov     [rsi+8], rbx
0x1800233f4  mov     rcx, [rdi+18h]
0x1800233f8  mov     rax, [rdi+30h]
0x1800233fc  and     rax, rbp
0x1800233ff  add     rax, rax
0x180023402  mov     r8, [rcx+rax*8]
0x180023406  cmp     r8, [rdi+8]
0x18002340a  jnz     short loc_180023412
0x18002340c  mov     [rcx+rax*8], rbx
0x180023410  jmp     short loc_180023424
0x180023412  cmp     r8, rsi
0x180023415  jnz     short loc_18002341D
0x180023417  mov     [rcx+rax*8], rbx
0x18002341b  jmp     short loc_180023429
0x18002341d  cmp     [rcx+rax*8+8], rdx
0x180023422  jnz     short loc_180023429
0x180023424  mov     [rcx+rax*8+8], rbx
0x180023429  jmp     short loc_18002342E
0x18002342b  xor     r14b, r14b
0x18002342e  mov     rcx, r15
0x180023431  mov     rax, r15
0x180023434  mov     [rax], rbx
0x180023437  mov     [rcx+r13], r14b
0x18002343b  add     rsp, 38h
0x18002343f  pop     r15
0x180023441  pop     r14
0x180023443  pop     r13
0x180023445  pop     r12
0x180023447  pop     rdi
0x180023448  pop     rsi
0x180023449  pop     rbp
0x18002344a  pop     rbx
0x18002344b  retn
```
