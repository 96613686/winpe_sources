# ??$ToJsonValue@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$$V$$Z$$V@Marshal@@YA_NAEAVJsonWriter@0@AEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEBVMarshalContext@0@U?$ModifierList@$$V@0@3@Z

- ea: `0x1400062f0`
- end: `0x1400064ab`
- name: `??$ToJsonValue@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$$V$$Z$$V@Marshal@@YA_NAEAVJsonWriter@0@AEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEBVMarshalContext@0@U?$ModifierList@$$V@0@3@Z`
- size: `443`
- prototype: `bool __fastcall(_BYTE *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1400065f0`

## callees

- `0x1400062f0`
- `0x1400073c4`
- `0x14000db94`

## pseudocode

```c
bool __fastcall ___ToJsonValue_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12_U__less_X_2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12__std___2___V__Z__V_Marshal__YA_NAEAVJsonWriter_0_AEBV__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12_U__less_X_2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12__std___2__std__AEBVMarshalContext_0_U__ModifierList___V_0_3_Z(
        _BYTE *a1,
        __int64 a2)
{
  void **v4; // rcx
  unsigned __int64 v5; // r8
  bool v6; // cc
  __int64 *v7; // rbx
  void **v8; // rcx
  unsigned __int64 v9; // rdx
  __int64 *v10; // rax
  __int64 v11; // r8
  void **v12; // rcx
  unsigned __int64 v13; // rdx
  _QWORD *v14; // rax
  __int64 **v15; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  void **v18; // rcx
  unsigned __int64 v19; // rdx
  _QWORD v21[2]; // [rsp+20h] [rbp-58h] BYREF
  _QWORD v22[9]; // [rsp+30h] [rbp-48h] BYREF

  v4 = *(void ***)a1;
  v5 = (unsigned __int64)v4[2];
  if ( v5 >= (unsigned __int64)v4[3] )
  {
    std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(v4, a2, v5, 123);
  }
  else
  {
    v6 = (unsigned __int64)v4[3] <= 7;
    v4[2] = (void *)(v5 + 1);
    if ( !v6 )
      v4 = (void **)*v4;
    *(_DWORD *)((char *)v4 + 2 * v5) = 123;
  }
  a1[8] = 1;
  v7 = **(__int64 ***)a2;
  while ( !*((_BYTE *)v7 + 25) )
  {
    if ( !a1[8] )
    {
      v8 = *(void ***)a1;
      v9 = *(_QWORD *)(*(_QWORD *)a1 + 16LL);
      if ( v9 >= *(_QWORD *)(*(_QWORD *)a1 + 24LL) )
      {
        std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(v8, v9, v5, 44);
      }
      else
      {
        v6 = (unsigned __int64)v8[3] <= 7;
        v8[2] = (void *)(v9 + 1);
        if ( !v6 )
          v8 = (void **)*v8;
        *(_DWORD *)((char *)v8 + 2 * v9) = 44;
      }
    }
    a1[8] = 0;
    if ( (unsigned __int64)v7[7] <= 7 )
      v10 = v7 + 4;
    else
      v10 = (__int64 *)v7[4];
    v21[0] = v10;
    v21[1] = v7[6];
    Marshal::JsonWriter::WriteValue(a1, v21);
    v12 = *(void ***)a1;
    v13 = *(_QWORD *)(*(_QWORD *)a1 + 16LL);
    if ( v13 >= *(_QWORD *)(*(_QWORD *)a1 + 24LL) )
    {
      std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(v12, v13, v11, 58);
    }
    else
    {
      v6 = (unsigned __int64)v12[3] <= 7;
      v12[2] = (void *)(v13 + 1);
      if ( !v6 )
        v12 = (void **)*v12;
      *(_DWORD *)((char *)v12 + 2 * v13) = 58;
    }
    v14 = v7 + 8;
    if ( (unsigned __int64)v7[11] > 7 )
      v14 = (_QWORD *)*v14;
    v22[0] = v14;
    v22[1] = v7[10];
    Marshal::JsonWriter::WriteValue(a1, v22);
    v15 = (__int64 **)v7[2];
    if ( *((_BYTE *)v15 + 25) )
    {
      for ( i = (__int64 *)v7[1]; !*((_BYTE *)i + 25) && v7 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v7 = i;
      v7 = i;
    }
    else
    {
      v7 = (__int64 *)v7[2];
      for ( j = *v15; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v7 = j;
    }
  }
  v18 = *(void ***)a1;
  v19 = *(_QWORD *)(*(_QWORD *)a1 + 16LL);
  if ( v19 >= *(_QWORD *)(*(_QWORD *)a1 + 24LL) )
  {
    std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(v18, v19, v5, 125);
  }
  else
  {
    v6 = (unsigned __int64)v18[3] <= 7;
    v18[2] = (void *)(v19 + 1);
    if ( !v6 )
      v18 = (void **)*v18;
    *(_DWORD *)((char *)v18 + 2 * v19) = 125;
  }
  a1[8] = 0;
  return *(_QWORD *)(a2 + 8) != 0;
}

```

## disassembly

```asm
0x1400062f0  push    rbx
0x1400062f2  push    rsi
0x1400062f3  push    rdi
0x1400062f4  push    r12
0x1400062f6  push    r14
0x1400062f8  push    r15
0x1400062fa  sub     rsp, 48h
0x1400062fe  mov     rsi, rcx
0x140006301  mov     r14, rdx
0x140006304  mov     rcx, [rcx]; Src
0x140006307  mov     r8, [rcx+10h]
0x14000630b  cmp     r8, [rcx+18h]
0x14000630f  jnb     short loc_14000632D
0x140006311  cmp     qword ptr [rcx+18h], 7
0x140006316  lea     rax, [r8+1]
0x14000631a  mov     [rcx+10h], rax
0x14000631e  jbe     short loc_140006323
0x140006320  mov     rcx, [rcx]
0x140006323  mov     dword ptr [rcx+r8*2], 7Bh ; '{'
0x14000632b  jmp     short loc_140006338
0x14000632d  mov     r9d, 7Bh ; '{'
0x140006333  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x140006338  mov     byte ptr [rsi+8], 1
0x14000633c  mov     r15d, 2Ch ; ','
0x140006342  mov     rbx, [r14]
0x140006345  lea     r12d, [r15+0Eh]
0x140006349  mov     rbx, [rbx]
0x14000634c  cmp     byte ptr [rbx+19h], 0
0x140006350  jnz     loc_14000645E
0x140006356  cmp     byte ptr [rsi+8], 0
0x14000635a  jnz     short loc_140006389
0x14000635c  mov     rcx, [rsi]; Src
0x14000635f  mov     rdx, [rcx+10h]
0x140006363  cmp     rdx, [rcx+18h]
0x140006367  jnb     short loc_140006381
0x140006369  cmp     qword ptr [rcx+18h], 7
0x14000636e  lea     rax, [rdx+1]
0x140006372  mov     [rcx+10h], rax
0x140006376  jbe     short loc_14000637B
0x140006378  mov     rcx, [rcx]
0x14000637b  mov     [rcx+rdx*2], r15d
0x14000637f  jmp     short loc_140006389
0x140006381  mov     r9d, r15d
0x140006384  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x140006389  mov     byte ptr [rsi+8], 0
0x14000638d  cmp     qword ptr [rbx+38h], 7
0x140006392  jbe     short loc_14000639A
0x140006394  mov     rax, [rbx+20h]
0x140006398  jmp     short loc_14000639E
0x14000639a  lea     rax, [rbx+20h]
0x14000639e  mov     [rsp+78h+var_58], rax
0x1400063a3  lea     rdx, [rsp+78h+var_58]
0x1400063a8  mov     rax, [rbx+30h]
0x1400063ac  mov     rcx, rsi
0x1400063af  mov     [rsp+78h+var_50], rax
0x1400063b4  call    ?WriteValue@JsonWriter@Marshal@@QEAAXV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; Marshal::JsonWriter::WriteValue(std::basic_string_view<ushort>)
0x1400063b9  mov     rcx, [rsi]; Src
0x1400063bc  mov     rdx, [rcx+10h]
0x1400063c0  cmp     rdx, [rcx+18h]
0x1400063c4  jnb     short loc_1400063DE
0x1400063c6  cmp     qword ptr [rcx+18h], 7
0x1400063cb  lea     rax, [rdx+1]
0x1400063cf  mov     [rcx+10h], rax
0x1400063d3  jbe     short loc_1400063D8
0x1400063d5  mov     rcx, [rcx]
0x1400063d8  mov     [rcx+rdx*2], r12d
0x1400063dc  jmp     short loc_1400063E6
0x1400063de  mov     r9d, r12d
0x1400063e1  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x1400063e6  cmp     qword ptr [rbx+58h], 7
0x1400063eb  lea     rax, [rbx+40h]
0x1400063ef  jbe     short loc_1400063F4
0x1400063f1  mov     rax, [rax]
0x1400063f4  mov     [rsp+78h+var_48], rax
0x1400063f9  lea     rdx, [rsp+78h+var_48]
0x1400063fe  mov     rax, [rbx+50h]
0x140006402  mov     rcx, rsi
0x140006405  mov     [rsp+78h+var_40], rax
0x14000640a  call    ?WriteValue@JsonWriter@Marshal@@QEAAXV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; Marshal::JsonWriter::WriteValue(std::basic_string_view<ushort>)
0x14000640f  mov     rcx, [rbx+10h]
0x140006413  cmp     byte ptr [rcx+19h], 0
0x140006417  jz      short loc_14000643A
0x140006419  mov     rax, [rbx+8]
0x14000641d  jmp     short loc_14000642C
0x14000641f  cmp     rbx, [rax+10h]
0x140006423  jnz     short loc_140006432
0x140006425  mov     rbx, rax
0x140006428  mov     rax, [rax+8]
0x14000642c  cmp     byte ptr [rax+19h], 0
0x140006430  jz      short loc_14000641F
0x140006432  mov     rbx, rax
0x140006435  jmp     loc_14000634C
0x14000643a  mov     rbx, rcx
0x14000643d  mov     rcx, [rcx]
0x140006440  cmp     byte ptr [rcx+19h], 0
0x140006444  jnz     loc_14000634C
0x14000644a  mov     rax, [rcx]
0x14000644d  mov     rbx, rcx
0x140006450  mov     rcx, rax
0x140006453  cmp     byte ptr [rax+19h], 0
0x140006457  jz      short loc_14000644A
0x140006459  jmp     loc_14000634C
0x14000645e  mov     rcx, [rsi]; Src
0x140006461  mov     rdx, [rcx+10h]
0x140006465  cmp     rdx, [rcx+18h]
0x140006469  jnb     short loc_140006486
0x14000646b  cmp     qword ptr [rcx+18h], 7
0x140006470  lea     rax, [rdx+1]
0x140006474  mov     [rcx+10h], rax
0x140006478  jbe     short loc_14000647D
0x14000647a  mov     rcx, [rcx]
0x14000647d  mov     dword ptr [rcx+rdx*2], 7Dh ; '}'
0x140006484  jmp     short loc_140006491
0x140006486  mov     r9d, 7Dh ; '}'
0x14000648c  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x140006491  mov     byte ptr [rsi+8], 0
0x140006495  cmp     qword ptr [r14+8], 0
0x14000649a  setnz   al
0x14000649d  add     rsp, 48h
0x1400064a1  pop     r15
0x1400064a3  pop     r14
0x1400064a5  pop     r12
0x1400064a7  pop     rdi
0x1400064a8  pop     rsi
0x1400064a9  pop     rbx
0x1400064aa  retn
```
