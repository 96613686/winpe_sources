# MapControl::ConfigurationManager::serializeOverrides(void)

- ea: `0x180021e14`
- end: `0x18002210c`
- name: `?serializeOverrides@ConfigurationManager@MapControl@@AEAA?AV?$shared_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@XZ`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config`

## callers

- `0x180022ae0`

## callees

- `0x1800094a0`
- `0x180009988`
- `0x18000ba50`
- `0x18000c354`
- `0x180011ddc`
- `0x180012158`
- `0x18001d540`
- `0x18001f940`
- `0x180021e14`
- `0x18002521c`
- `0x18003417c`
- `0x1800342dc`
- `0x180034324`
- `0x180034538`
- `0x180034630`
- `0x1800346dc`
- `0x180034714`
- `0x1800348b8`
- `0x18003a770`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180022105`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180022105`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_QWORD *__fastcall MapControl::ConfigurationManager::serializeOverrides(__int64 a1, _QWORD *a2)
{
  int v4; // r15d
  __int64 v5; // rdi
  __int64 v6; // r13
  void **v7; // r10
  int v8; // r11d
  _BYTE *v9; // rax
  _BYTE *v10; // rsi
  __int64 v11; // rbx
  __int64 v12; // rax
  Json::Value *v13; // rbx
  __int64 v14; // rax
  Json::Value *v15; // rbx
  __int64 v16; // rax
  __int64 v17; // rbx
  __int64 v18; // rax
  __int64 v19; // rdx
  void *v20; // rcx
  __int64 v21; // rax
  void **v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rax
  void **v27; // [rsp+20h] [rbp-E0h] BYREF
  int v28; // [rsp+28h] [rbp-D8h]
  _BYTE *v29; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v30[40]; // [rsp+38h] [rbp-C8h] BYREF
  void *v31[6]; // [rsp+60h] [rbp-A0h] BYREF
  void *v32[5]; // [rsp+90h] [rbp-70h] BYREF
  void *v33; // [rsp+B8h] [rbp-48h] BYREF
  int v34; // [rsp+C0h] [rbp-40h]
  __int128 v35; // [rsp+C8h] [rbp-38h]
  __int64 v36; // [rsp+D8h] [rbp-28h]
  void **v37; // [rsp+E0h] [rbp-20h] BYREF
  char v38[32]; // [rsp+E8h] [rbp-18h] BYREF
  __int16 v39; // [rsp+108h] [rbp+8h]
  char v40; // [rsp+10Ah] [rbp+Ah]

  v31[5] = a2;
  v28 = 0;
  Json::Value::Value((__int64)v31, 0);
  Json::Value::Value((__int64)v32, 6);
  v4 = 0;
  v5 = *(_QWORD *)(a1 + 120);
  v6 = *(_QWORD *)(a1 + 128);
  while ( v5 != v6 )
  {
    if ( *(_QWORD *)(v5 + 8) > 3u )
    {
      Json::Value::Value((__int64)&v33, 0);
      v7 = **(void ****)v5;
      v27 = v7;
      while ( !*((_BYTE *)v7 + 25) )
      {
        v8 = *((_DWORD *)v7 + 8);
        v9 = *(_BYTE **)MapControl::StringKeyToEnumKeyMap::kStringKeyToEnumKeyMap;
        v29 = *(_BYTE **)MapControl::StringKeyToEnumKeyMap::kStringKeyToEnumKeyMap;
        while ( !v9[25] )
        {
          v10 = v9 + 32;
          if ( *((_DWORD *)v9 + 16) == v8 )
          {
            v29 = v30;
            v11 = Json::Value::Value((__int64)v30, (__int64)(v7 + 5));
            v12 = Json::Value::operator[](&v33, v10);
            Json::Value::operator=(v12, v11);
            break;
          }
          std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,enum MapControl::ConfigurationKeys>>>,std::_Iterator_base0>::operator++(&v29);
          v9 = v29;
        }
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<enum MapControl::ConfigurationKeys const,std::wstring>>>,std::_Iterator_base0>::operator++(&v27);
        v7 = v27;
      }
      v27 = (void **)v30;
      v13 = Json::Value::Value((Json::Value *)v30, (const struct Json::Value *)&v33);
      v14 = Json::Value::operator[]((__int64 **)v32, v4++);
      Json::Value::operator=(v14, v13);
      Json::Value::~Value(&v33);
    }
    v5 += 16;
  }
  v27 = (void **)v30;
  v15 = Json::Value::Value((Json::Value *)v30, (const struct Json::Value *)v32);
  v16 = Json::Value::operator[](v31, L"overrides");
  Json::Value::operator=(v16, v15);
  v27 = (void **)v30;
  v17 = Json::Value::Value((__int64)v30, a1 + 336);
  v18 = Json::Value::operator[](v31, L"most_recent_region");
  Json::Value::operator=(v18, v17);
  v27 = &v33;
  v20 = (void *)*(unsigned int *)(a1 + 448);
  if ( (unsigned int)((_DWORD)v20 - 1) > 0x63 )
  {
    _o_terminate(v20, v19);
    JUMPOUT(0x18002210BLL);
  }
  LOBYTE(v34) = 2;
  v34 &= ~0x100u;
  v35 = 0;
  v36 = 0;
  v33 = v20;
  v21 = Json::Value::operator[](v31, L"bucket");
  Json::Value::operator=(v21, &v33);
  v22 = (void **)operator new(0x30u);
  v27 = v22;
  *(_OWORD *)v22 = 0;
  *((_DWORD *)v22 + 2) = 1;
  *((_DWORD *)v22 + 3) = 1;
  *v22 = &std::_Ref_count_obj2<std::wstring>::`vftable';
  std::_Construct_in_place<std::wstring,>(v22 + 2);
  *a2 = v23;
  a2[1] = v24;
  v28 = 3;
  v37 = &Json::FastWriter::`vftable';
  std::wstring::wstring((__int64)v38);
  v39 = 0;
  v40 = 0;
  v25 = Json::FastWriter::write((Json::FastWriter *)&v37);
  std::wstring::operator=(*a2, v25);
  std::wstring::_Tidy_deallocate(&v33);
  Json::FastWriter::~FastWriter((Json::FastWriter *)&v37);
  Json::Value::~Value(v32);
  Json::Value::~Value(v31);
  return a2;
}

```

## disassembly

```asm
0x180021e14  mov     [rsp-8+arg_10], rbx
0x180021e19  push    rbp
0x180021e1a  push    rsi
0x180021e1b  push    rdi
0x180021e1c  push    r12
0x180021e1e  push    r13
0x180021e20  push    r14
0x180021e22  push    r15
0x180021e24  lea     rbp, [rsp-20h]
0x180021e29  sub     rsp, 120h
0x180021e30  mov     rax, cs:__security_cookie
0x180021e37  xor     rax, rsp
0x180021e3a  mov     [rbp+50h+var_40], rax
0x180021e3e  mov     r12, rdx
0x180021e41  mov     r14, rcx
0x180021e44  mov     [rbp+50h+var_C8], rdx
0x180021e48  xor     esi, esi
0x180021e4a  mov     [rsp+150h+var_128], esi
0x180021e4e  xor     edx, edx
0x180021e50  lea     rcx, [rsp+150h+var_F0]
0x180021e55  call    ??0Value@Json@@QEAA@W4ValueType@1@@Z; Json::Value::Value(Json::ValueType)
0x180021e5a  nop
0x180021e5b  lea     edx, [rsi+6]
0x180021e5e  lea     rcx, [rbp+50h+var_C0]
0x180021e62  call    ??0Value@Json@@QEAA@W4ValueType@1@@Z; Json::Value::Value(Json::ValueType)
0x180021e67  nop
0x180021e68  mov     r15d, esi
0x180021e6b  mov     rdi, [r14+78h]
0x180021e6f  mov     r13, [r14+80h]
0x180021e76  jmp     loc_180021F64
0x180021e7b  cmp     qword ptr [rdi+8], 3
0x180021e80  jbe     loc_180021F60
0x180021e86  xor     edx, edx
0x180021e88  lea     rcx, [rbp+50h+var_98]
0x180021e8c  call    ??0Value@Json@@QEAA@W4ValueType@1@@Z; Json::Value::Value(Json::ValueType)
0x180021e91  nop
0x180021e92  mov     r10, [rdi]
0x180021e95  mov     r10, [r10]
0x180021e98  mov     [rsp+150h+var_130], r10
0x180021e9d  cmp     [r10+19h], sil
0x180021ea1  jnz     short loc_180021F21
0x180021ea3  mov     r11d, [r10+20h]
0x180021ea7  mov     rax, qword ptr cs:?kStringKeyToEnumKeyMap@StringKeyToEnumKeyMap@MapControl@@0V?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4ConfigurationKeys@MapControl@@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4ConfigurationKeys@MapControl@@@std@@@2@@std@@B; std::map<std::wstring const,MapControl::ConfigurationKeys> const MapControl::StringKeyToEnumKeyMap::kStringKeyToEnumKeyMap
0x180021eae  mov     rax, [rax]
0x180021eb1  mov     [rsp+150h+var_120], rax
0x180021eb6  cmp     [rax+19h], sil
0x180021eba  jnz     short loc_180021F0D
0x180021ebc  lea     rsi, [rax+20h]
0x180021ec0  cmp     [rsi+20h], r11d
0x180021ec4  jz      short loc_180021ED9
0x180021ec6  lea     rcx, [rsp+150h+var_120]
0x180021ecb  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4ConfigurationKeys@MapControl@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,MapControl::ConfigurationKeys>>>,std::_Iterator_base0>::operator++(void)
0x180021ed0  mov     rax, [rsp+150h+var_120]
0x180021ed5  xor     esi, esi
0x180021ed7  jmp     short loc_180021EB6
0x180021ed9  lea     rax, [rsp+150h+var_118]
0x180021ede  mov     [rsp+150h+var_120], rax
0x180021ee3  lea     rdx, [r10+28h]
0x180021ee7  lea     rcx, [rsp+150h+var_118]
0x180021eec  call    ??0Value@Json@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Json::Value::Value(std::wstring const &)
0x180021ef1  mov     rbx, rax
0x180021ef4  mov     rdx, rsi
0x180021ef7  lea     rcx, [rbp+50h+var_98]
0x180021efb  call    ??AValue@Json@@QEAAAEAV01@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Json::Value::operator[](std::wstring const &)
0x180021f00  mov     rcx, rax
0x180021f03  mov     rdx, rbx
0x180021f06  call    ??4Value@Json@@QEAAAEAV01@V01@@Z; Json::Value::operator=(Json::Value)
0x180021f0b  xor     esi, esi
0x180021f0d  lea     rcx, [rsp+150h+var_130]
0x180021f12  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<MapControl::ConfigurationKeys const,std::wstring>>>,std::_Iterator_base0>::operator++(void)
0x180021f17  mov     r10, [rsp+150h+var_130]
0x180021f1c  jmp     loc_180021E9D
0x180021f21  lea     rax, [rsp+150h+var_118]
0x180021f26  mov     [rsp+150h+var_130], rax
0x180021f2b  lea     rdx, [rbp+50h+var_98]; struct Json::Value *
0x180021f2f  lea     rcx, [rsp+150h+var_118]; this
0x180021f34  call    ??0Value@Json@@QEAA@AEBV01@@Z; Json::Value::Value(Json::Value const &)
0x180021f39  mov     rbx, rax
0x180021f3c  mov     edx, r15d
0x180021f3f  lea     rcx, [rbp+50h+var_C0]
0x180021f43  call    ??AValue@Json@@QEAAAEAV01@H@Z; Json::Value::operator[](int)
0x180021f48  inc     r15d
0x180021f4b  mov     rdx, rbx
0x180021f4e  mov     rcx, rax
0x180021f51  call    ??4Value@Json@@QEAAAEAV01@V01@@Z; Json::Value::operator=(Json::Value)
0x180021f56  nop
0x180021f57  lea     rcx, [rbp+50h+var_98]; this
0x180021f5b  call    ??1Value@Json@@QEAA@XZ; Json::Value::~Value(void)
0x180021f60  add     rdi, 10h
0x180021f64  cmp     rdi, r13
0x180021f67  jnz     loc_180021E7B
0x180021f6d  lea     rax, [rsp+150h+var_118]
0x180021f72  mov     [rsp+150h+var_130], rax
0x180021f77  lea     rdx, [rbp+50h+var_C0]; struct Json::Value *
0x180021f7b  lea     rcx, [rsp+150h+var_118]; this
0x180021f80  call    ??0Value@Json@@QEAA@AEBV01@@Z; Json::Value::Value(Json::Value const &)
0x180021f85  mov     rbx, rax
0x180021f88  lea     rdx, aOverrides; "overrides"
0x180021f8f  lea     rcx, [rsp+150h+var_F0]
0x180021f94  call    ??AValue@Json@@QEAAAEAV01@PEBG@Z; Json::Value::operator[](ushort const *)
0x180021f99  mov     rcx, rax
0x180021f9c  mov     rdx, rbx
0x180021f9f  call    ??4Value@Json@@QEAAAEAV01@V01@@Z; Json::Value::operator=(Json::Value)
0x180021fa4  lea     rax, [rsp+150h+var_118]
0x180021fa9  mov     [rsp+150h+var_130], rax
0x180021fae  lea     rdx, [r14+150h]
0x180021fb5  lea     rcx, [rsp+150h+var_118]
0x180021fba  call    ??0Value@Json@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Json::Value::Value(std::wstring const &)
0x180021fbf  mov     rbx, rax
0x180021fc2  lea     rdx, aMostRecentRegi; "most_recent_region"
0x180021fc9  lea     rcx, [rsp+150h+var_F0]
0x180021fce  call    ??AValue@Json@@QEAAAEAV01@PEBG@Z; Json::Value::operator[](ushort const *)
0x180021fd3  mov     rcx, rax
0x180021fd6  mov     rdx, rbx
0x180021fd9  call    ??4Value@Json@@QEAAAEAV01@V01@@Z; Json::Value::operator=(Json::Value)
0x180021fde  lea     rax, [rbp+50h+var_98]
0x180021fe2  mov     [rsp+150h+var_130], rax
0x180021fe7  mov     ecx, [r14+1C0h]
0x180021fee  lea     eax, [rcx-1]
0x180021ff1  cmp     eax, 63h ; 'c'
0x180021ff4  ja      loc_180022105
0x180021ffa  mov     byte ptr [rbp+50h+var_90], 2
0x180021ffe  btr     [rbp+50h+var_90], 8
0x180022003  xorps   xmm0, xmm0
0x180022006  movdqu  [rbp+50h+var_88], xmm0
0x18002200b  mov     [rbp+50h+var_78], rsi
0x18002200f  mov     [rbp+50h+var_98], rcx
0x180022013  lea     rdx, aBucket; "bucket"
0x18002201a  lea     rcx, [rsp+150h+var_F0]
0x18002201f  call    ??AValue@Json@@QEAAAEAV01@PEBG@Z; Json::Value::operator[](ushort const *)
0x180022024  mov     rcx, rax
0x180022027  lea     rdx, [rbp+50h+var_98]
0x18002202b  call    ??4Value@Json@@QEAAAEAV01@V01@@Z; Json::Value::operator=(Json::Value)
0x180022030  mov     ecx, 30h ; '0'; Size
0x180022035  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002203a  mov     rdx, rax
0x18002203d  mov     [rsp+150h+var_130], rax
0x180022042  xorps   xmm0, xmm0
0x180022045  movups  xmmword ptr [rax], xmm0
0x180022048  mov     eax, 1
0x18002204d  mov     [rdx+8], eax
0x180022050  mov     [rdx+0Ch], eax
0x180022053  lea     rax, ??_7?$_Ref_count_obj2@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@6B@; const std::_Ref_count_obj2<std::wstring>::`vftable'
0x18002205a  mov     [rdx], rax
0x18002205d  lea     rcx, [rdx+10h]
0x180022061  call    ??$_Construct_in_place@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@std@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::_Construct_in_place<std::wstring,>(std::wstring &)
0x180022066  mov     [r12], rcx
0x18002206a  mov     [r12+8], rdx
0x18002206f  mov     [rsp+150h+var_128], 3
0x180022077  lea     rax, ??_7FastWriter@Json@@6B@; const Json::FastWriter::`vftable'
0x18002207e  mov     [rbp+50h+var_70], rax
0x180022082  lea     rcx, [rbp+50h+var_68]
0x180022086  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002208b  mov     [rbp+50h+var_48], 0
0x180022091  mov     [rbp+50h+var_46], sil
0x180022095  lea     r8, [rsp+150h+var_F0]
0x18002209a  lea     rdx, [rbp+50h+var_98]
0x18002209e  lea     rcx, [rbp+50h+var_70]; this
0x1800220a2  call    ?write@FastWriter@Json@@UEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVValue@2@@Z; Json::FastWriter::write(Json::Value const &)
0x1800220a7  mov     rdx, rax
0x1800220aa  mov     rcx, [r12]
0x1800220ae  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800220b3  lea     rcx, [rbp+50h+var_98]
0x1800220b7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800220bc  nop
0x1800220bd  lea     rcx, [rbp+50h+var_70]; this
0x1800220c1  call    ??1FastWriter@Json@@UEAA@XZ; Json::FastWriter::~FastWriter(void)
0x1800220c6  nop
0x1800220c7  lea     rcx, [rbp+50h+var_C0]; this
0x1800220cb  call    ??1Value@Json@@QEAA@XZ; Json::Value::~Value(void)
0x1800220d0  nop
0x1800220d1  lea     rcx, [rsp+150h+var_F0]; this
0x1800220d6  call    ??1Value@Json@@QEAA@XZ; Json::Value::~Value(void)
0x1800220db  mov     rax, r12
0x1800220de  mov     rcx, [rbp+50h+var_40]
0x1800220e2  xor     rcx, rsp; StackCookie
0x1800220e5  call    __security_check_cookie
0x1800220ea  mov     rbx, [rsp+150h+arg_10]
0x1800220f2  add     rsp, 120h
0x1800220f9  pop     r15
0x1800220fb  pop     r14
0x1800220fd  pop     r13
0x1800220ff  pop     r12
0x180022101  pop     rdi
0x180022102  pop     rsi
0x180022103  pop     rbp
0x180022104  retn
0x180022105  call    cs:__imp__o_terminate
```
