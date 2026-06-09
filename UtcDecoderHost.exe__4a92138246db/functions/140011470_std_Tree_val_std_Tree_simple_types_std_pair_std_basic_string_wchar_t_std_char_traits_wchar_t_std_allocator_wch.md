# std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo,std::default_delete<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo,std::default_delete<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>>,void *> *>,std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo,std::default_delete<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>>,void *> * const)

- ea: `0x140011470`
- end: `0x140011699`
- name: `?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@U?$default_delete@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@@std@@@2@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@U?$default_delete@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@@std@@@2@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@U?$default_delete@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@@std@@@2@@std@@PEAX@std@@@2@QEAU32@@Z`
- size: `553`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140002110`
- `0x140007f20`
- `0x14000f2d4`

## callees

- `0x140011470`

## pseudocode

```c
__int64 __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>>>::_Insert_node(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v4; // r10
  _QWORD *v5; // rax
  __int64 v6; // rax
  _QWORD *i; // rdx
  __int64 v8; // rcx
  __int64 *v9; // r9
  __int64 v10; // rax
  _QWORD *v11; // r9
  _QWORD *v12; // rax
  _QWORD *v13; // rcx
  _QWORD *v14; // r9
  __int64 v15; // rax
  _QWORD *v16; // rax
  _QWORD *v17; // r9
  __int64 v18; // rax
  _QWORD *v19; // rax
  _QWORD *v20; // rax

  ++a1[1];
  v4 = (_QWORD *)*a1;
  v5 = *(_QWORD **)a2;
  *(_QWORD *)(a3 + 8) = *(_QWORD *)a2;
  if ( v5 != v4 )
  {
    if ( *(_DWORD *)(a2 + 8) )
    {
      *v5 = a3;
      if ( v5 == (_QWORD *)*v4 )
        *v4 = a3;
    }
    else
    {
      v5[2] = a3;
      if ( v5 == (_QWORD *)v4[2] )
        v4[2] = a3;
    }
    v6 = *(_QWORD *)(a3 + 8);
    for ( i = (_QWORD *)a3; ; v6 = i[1] )
    {
      if ( *(_BYTE *)(v6 + 24) )
      {
        *(_BYTE *)(v4[1] + 24LL) = 1;
        return a3;
      }
      v8 = i[1];
      v9 = *(__int64 **)(v8 + 8);
      v10 = *v9;
      if ( v8 == *v9 )
      {
        v10 = v9[2];
        if ( !*(_BYTE *)(v10 + 24) )
          goto LABEL_29;
        v11 = *(_QWORD **)(v8 + 16);
        if ( i == v11 )
        {
          i = (_QWORD *)i[1];
          *(_QWORD *)(v8 + 16) = *v11;
          if ( !*(_BYTE *)(*v11 + 25LL) )
            *(_QWORD *)(*v11 + 8LL) = v8;
          v11[1] = *(_QWORD *)(v8 + 8);
          if ( v8 == *(_QWORD *)(*a1 + 8LL) )
          {
            *(_QWORD *)(*a1 + 8LL) = v11;
          }
          else
          {
            v12 = *(_QWORD **)(v8 + 8);
            if ( v8 == *v12 )
              *v12 = v11;
            else
              v12[2] = v11;
          }
          *v11 = v8;
          *(_QWORD *)(v8 + 8) = v11;
        }
        *(_BYTE *)(i[1] + 24LL) = 1;
        *(_BYTE *)(*(_QWORD *)(i[1] + 8LL) + 24LL) = 0;
        v13 = *(_QWORD **)(i[1] + 8LL);
        v14 = (_QWORD *)*v13;
        *v13 = *(_QWORD *)(*v13 + 16LL);
        v15 = v14[2];
        if ( !*(_BYTE *)(v15 + 25) )
          *(_QWORD *)(v15 + 8) = v13;
        v14[1] = v13[1];
        if ( v13 == *(_QWORD **)(*a1 + 8LL) )
        {
          *(_QWORD *)(*a1 + 8LL) = v14;
        }
        else
        {
          v16 = (_QWORD *)v13[1];
          if ( v13 == (_QWORD *)v16[2] )
            v16[2] = v14;
          else
            *v16 = v14;
        }
        v14[2] = v13;
      }
      else
      {
        if ( !*(_BYTE *)(v10 + 24) )
        {
LABEL_29:
          *(_BYTE *)(v8 + 24) = 1;
          *(_BYTE *)(v10 + 24) = 1;
          *(_BYTE *)(*(_QWORD *)(i[1] + 8LL) + 24LL) = 0;
          i = *(_QWORD **)(i[1] + 8LL);
          continue;
        }
        v17 = *(_QWORD **)v8;
        if ( i == *(_QWORD **)v8 )
        {
          i = (_QWORD *)i[1];
          *(_QWORD *)v8 = v17[2];
          v18 = v17[2];
          if ( !*(_BYTE *)(v18 + 25) )
            *(_QWORD *)(v18 + 8) = v8;
          v17[1] = *(_QWORD *)(v8 + 8);
          if ( v8 == *(_QWORD *)(*a1 + 8LL) )
          {
            *(_QWORD *)(*a1 + 8LL) = v17;
          }
          else
          {
            v19 = *(_QWORD **)(v8 + 8);
            if ( v8 == v19[2] )
              v19[2] = v17;
            else
              *v19 = v17;
          }
          v17[2] = v8;
          *(_QWORD *)(v8 + 8) = v17;
        }
        *(_BYTE *)(i[1] + 24LL) = 1;
        *(_BYTE *)(*(_QWORD *)(i[1] + 8LL) + 24LL) = 0;
        v13 = *(_QWORD **)(i[1] + 8LL);
        v14 = (_QWORD *)v13[2];
        v13[2] = *v14;
        if ( !*(_BYTE *)(*v14 + 25LL) )
          *(_QWORD *)(*v14 + 8LL) = v13;
        v14[1] = v13[1];
        if ( v13 == *(_QWORD **)(*a1 + 8LL) )
        {
          *(_QWORD *)(*a1 + 8LL) = v14;
        }
        else
        {
          v20 = (_QWORD *)v13[1];
          if ( v13 == (_QWORD *)*v20 )
            *v20 = v14;
          else
            v20[2] = v14;
        }
        *v14 = v13;
      }
      v13[1] = v14;
    }
  }
  *v4 = a3;
  v4[1] = a3;
  v4[2] = a3;
  *(_BYTE *)(a3 + 24) = 1;
  return a3;
}

```

## disassembly

```asm
0x140011470  mov     [rsp+arg_0], rbx
0x140011475  inc     qword ptr [rcx+8]
0x140011479  mov     r11, rcx
0x14001147c  mov     r10, [rcx]
0x14001147f  mov     rax, [rdx]
0x140011482  mov     [r8+8], rax
0x140011486  cmp     rax, r10
0x140011489  jnz     short loc_1400114A0
0x14001148b  mov     [r10], r8
0x14001148e  mov     [r10+8], r8
0x140011492  mov     [r10+10h], r8
0x140011496  mov     byte ptr [r8+18h], 1
0x14001149b  jmp     loc_140011690
0x1400114a0  xor     ebx, ebx
0x1400114a2  cmp     [rdx+8], ebx
0x1400114a5  jnz     short loc_1400114B7
0x1400114a7  mov     [rax+10h], r8
0x1400114ab  cmp     rax, [r10+10h]
0x1400114af  jnz     short loc_1400114C2
0x1400114b1  mov     [r10+10h], r8
0x1400114b5  jmp     short loc_1400114C2
0x1400114b7  mov     [rax], r8
0x1400114ba  cmp     rax, [r10]
0x1400114bd  jnz     short loc_1400114C2
0x1400114bf  mov     [r10], r8
0x1400114c2  mov     rax, [r8+8]
0x1400114c6  mov     rdx, r8
0x1400114c9  jmp     loc_14001167F
0x1400114ce  mov     rcx, [rdx+8]
0x1400114d2  mov     r9, [rcx+8]
0x1400114d6  mov     rax, [r9]
0x1400114d9  cmp     rcx, rax
0x1400114dc  jnz     loc_1400115A3
0x1400114e2  mov     rax, [r9+10h]
0x1400114e6  cmp     [rax+18h], bl
0x1400114e9  jz      loc_1400115A8
0x1400114ef  mov     r9, [rcx+10h]
0x1400114f3  cmp     rdx, r9
0x1400114f6  jnz     short loc_14001153E
0x1400114f8  mov     rax, [r9]
0x1400114fb  mov     rdx, rcx
0x1400114fe  mov     [rcx+10h], rax
0x140011502  mov     rax, [r9]
0x140011505  cmp     [rax+19h], bl
0x140011508  jnz     short loc_14001150E
0x14001150a  mov     [rax+8], rcx
0x14001150e  mov     rax, [rcx+8]
0x140011512  mov     [r9+8], rax
0x140011516  mov     rax, [r11]
0x140011519  cmp     rcx, [rax+8]
0x14001151d  jnz     short loc_140011525
0x14001151f  mov     [rax+8], r9
0x140011523  jmp     short loc_140011537
0x140011525  mov     rax, [rcx+8]
0x140011529  cmp     rcx, [rax]
0x14001152c  jnz     short loc_140011533
0x14001152e  mov     [rax], r9
0x140011531  jmp     short loc_140011537
0x140011533  mov     [rax+10h], r9
0x140011537  mov     [r9], rcx
0x14001153a  mov     [rcx+8], r9
0x14001153e  mov     rax, [rdx+8]
0x140011542  mov     byte ptr [rax+18h], 1
0x140011546  mov     rax, [rdx+8]
0x14001154a  mov     rcx, [rax+8]
0x14001154e  mov     [rcx+18h], bl
0x140011551  mov     rax, [rdx+8]
0x140011555  mov     rcx, [rax+8]
0x140011559  mov     r9, [rcx]
0x14001155c  mov     rax, [r9+10h]
0x140011560  mov     [rcx], rax
0x140011563  mov     rax, [r9+10h]
0x140011567  cmp     [rax+19h], bl
0x14001156a  jnz     short loc_140011570
0x14001156c  mov     [rax+8], rcx
0x140011570  mov     rax, [rcx+8]
0x140011574  mov     [r9+8], rax
0x140011578  mov     rax, [r11]
0x14001157b  cmp     rcx, [rax+8]
0x14001157f  jnz     short loc_140011587
0x140011581  mov     [rax+8], r9
0x140011585  jmp     short loc_14001159A
0x140011587  mov     rax, [rcx+8]
0x14001158b  cmp     rcx, [rax+10h]
0x14001158f  jnz     short loc_140011597
0x140011591  mov     [rax+10h], r9
0x140011595  jmp     short loc_14001159A
0x140011597  mov     [rax], r9
0x14001159a  mov     [r9+10h], rcx
0x14001159e  jmp     loc_140011677
0x1400115a3  cmp     [rax+18h], bl
0x1400115a6  jnz     short loc_1400115C8
0x1400115a8  mov     byte ptr [rcx+18h], 1
0x1400115ac  mov     byte ptr [rax+18h], 1
0x1400115b0  mov     rax, [rdx+8]
0x1400115b4  mov     rcx, [rax+8]
0x1400115b8  mov     [rcx+18h], bl
0x1400115bb  mov     rax, [rdx+8]
0x1400115bf  mov     rdx, [rax+8]
0x1400115c3  jmp     loc_14001167B
0x1400115c8  mov     r9, [rcx]
0x1400115cb  cmp     rdx, r9
0x1400115ce  jnz     short loc_140011619
0x1400115d0  mov     rax, [r9+10h]
0x1400115d4  mov     rdx, rcx
0x1400115d7  mov     [rcx], rax
0x1400115da  mov     rax, [r9+10h]
0x1400115de  cmp     [rax+19h], bl
0x1400115e1  jnz     short loc_1400115E7
0x1400115e3  mov     [rax+8], rcx
0x1400115e7  mov     rax, [rcx+8]
0x1400115eb  mov     [r9+8], rax
0x1400115ef  mov     rax, [r11]
0x1400115f2  cmp     rcx, [rax+8]
0x1400115f6  jnz     short loc_1400115FE
0x1400115f8  mov     [rax+8], r9
0x1400115fc  jmp     short loc_140011611
0x1400115fe  mov     rax, [rcx+8]
0x140011602  cmp     rcx, [rax+10h]
0x140011606  jnz     short loc_14001160E
0x140011608  mov     [rax+10h], r9
0x14001160c  jmp     short loc_140011611
0x14001160e  mov     [rax], r9
0x140011611  mov     [r9+10h], rcx
0x140011615  mov     [rcx+8], r9
0x140011619  mov     rax, [rdx+8]
0x14001161d  mov     byte ptr [rax+18h], 1
0x140011621  mov     rax, [rdx+8]
0x140011625  mov     rcx, [rax+8]
0x140011629  mov     [rcx+18h], bl
0x14001162c  mov     rax, [rdx+8]
0x140011630  mov     rcx, [rax+8]
0x140011634  mov     r9, [rcx+10h]
0x140011638  mov     rax, [r9]
0x14001163b  mov     [rcx+10h], rax
0x14001163f  mov     rax, [r9]
0x140011642  cmp     [rax+19h], bl
0x140011645  jnz     short loc_14001164B
0x140011647  mov     [rax+8], rcx
0x14001164b  mov     rax, [rcx+8]
0x14001164f  mov     [r9+8], rax
0x140011653  mov     rax, [r11]
0x140011656  cmp     rcx, [rax+8]
0x14001165a  jnz     short loc_140011662
0x14001165c  mov     [rax+8], r9
0x140011660  jmp     short loc_140011674
0x140011662  mov     rax, [rcx+8]
0x140011666  cmp     rcx, [rax]
0x140011669  jnz     short loc_140011670
0x14001166b  mov     [rax], r9
0x14001166e  jmp     short loc_140011674
0x140011670  mov     [rax+10h], r9
0x140011674  mov     [r9], rcx
0x140011677  mov     [rcx+8], r9
0x14001167b  mov     rax, [rdx+8]
0x14001167f  cmp     [rax+18h], bl
0x140011682  jz      loc_1400114CE
0x140011688  mov     rax, [r10+8]
0x14001168c  mov     byte ptr [rax+18h], 1
0x140011690  mov     rbx, [rsp+arg_0]
0x140011695  mov     rax, r8
0x140011698  retn
```
