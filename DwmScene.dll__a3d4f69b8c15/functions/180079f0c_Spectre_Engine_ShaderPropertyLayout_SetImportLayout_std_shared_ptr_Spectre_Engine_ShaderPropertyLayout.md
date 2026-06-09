# Spectre::Engine::ShaderPropertyLayout::SetImportLayout(std::shared_ptr<Spectre::Engine::ShaderPropertyLayout>)

- ea: `0x180079f0c`
- end: `0x18007a17c`
- name: `?SetImportLayout@ShaderPropertyLayout@Engine@Spectre@@QEAAXV?$shared_ptr@VShaderPropertyLayout@Engine@Spectre@@@std@@@Z`
- size: `624`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180079908`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x18001128c`
- `0x180011f64`
- `0x180013664`
- `0x18001c630`
- `0x18001c720`
- `0x180038ddc`
- `0x180078820`
- `0x180079e1c`
- `0x180079f0c`

## string_xrefs

- `0x180079f61`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shaderpropertylayout.cpp`
- `0x18007a0b1`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shaderpropertylayout.cpp`
- `0x18007a111`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shaderpropertylayout.cpp`
- `0x180079f4f`: `ShaderPropertyLayout::SetMasterLayout() -- layout declaration must be complete before another layout can be connected as a master.`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall Spectre::Engine::ShaderPropertyLayout::SetImportLayout(__int64 a1, _QWORD *a2)
{
  _QWORD *v2; // rsi
  int v4; // eax
  int v5; // r8d
  __int64 v6; // r15
  __int64 v7; // rax
  __int64 v8; // r14
  __int64 v9; // rax
  __int64 v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // r12
  __int64 v14; // r13
  __int64 v15; // rcx
  int TypeSizeInElements; // eax
  int v17; // edi
  int v18; // esi
  __int64 v19; // rax
  int v20; // ebx
  int v21; // eax
  int v22; // r8d
  __int64 v23; // rax
  int v24; // ebx
  int v25; // eax
  int v26; // r8d
  std::_Ref_count_base *v27; // rcx
  __int64 v29; // [rsp+40h] [rbp-C0h]
  _DWORD v30[2]; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD v31[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v32; // [rsp+58h] [rbp-A8h]
  _BYTE v33[32]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v34[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v36[56]; // [rsp+D8h] [rbp-28h] BYREF

  v2 = a2;
  v32 = a2;
  if ( *(_DWORD *)(a1 + 1168) != 1 )
  {
    std::string::string(
      v33,
      "ShaderPropertyLayout::SetMasterLayout() -- layout declaration must be complete before another layout can be connec"
      "ted as a master.");
    v4 = std::string::string(
           v34,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\shaderp"
           "ropertylayout.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v4,
      v5,
      (unsigned int)v33,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  std::shared_ptr<Spectre::Engine::Light>::operator=(a1 + 1176, a2);
  v6 = a1 + 1192;
  v7 = *(_QWORD *)(a1 + 1192);
  if ( v7 != *(_QWORD *)(a1 + 1200) )
    *(_QWORD *)(a1 + 1200) = v7;
  v8 = a1 + 1216;
  v9 = *(_QWORD *)(a1 + 1216);
  if ( v9 != *(_QWORD *)(a1 + 1224) )
    *(_QWORD *)(a1 + 1224) = v9;
  v10 = *(_QWORD *)(a1 + 56);
  v11 = *(_QWORD *)(a1 + 64);
  v29 = v11;
  while ( v10 != v11 )
  {
    if ( *(_DWORD *)(v10 + 48) )
    {
      v12 = *(unsigned __int16 *)(*v2 + 2LL * *(unsigned __int16 *)(v10 + 32) + 128);
      if ( (_WORD)v12 == 0xFFFF )
      {
        v23 = std::operator+<char>(
                pExceptionObject,
                "ShaderPropertyLayout::SetMasterLayout() -- master layout does not have the property '",
                v10);
        v24 = std::operator+<char>(v34, v23, "' required for import by this layout");
        v25 = std::string::string(
                v33,
                "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\sh"
                "aderpropertylayout.cpp");
        Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException((unsigned int)v36, v25, v26, v24, 0);
        throw (Spectre::Engine::EngineInvalidArgException *)v36;
      }
      v13 = 56 * v12;
      v14 = *(_QWORD *)(*v2 + 56LL);
      v15 = *(unsigned int *)(v10 + 36);
      if ( (_DWORD)v15 != *(_DWORD *)(v13 + v14 + 36) )
      {
        v19 = std::operator+<char>(
                v34,
                "ShaderPropertyLayout::SetMasterLayout() -- master layout has different type for property '",
                v10);
        v20 = std::operator+<char>(pExceptionObject, v19, "' imported by this layout");
        v21 = std::string::string(
                v33,
                "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\sh"
                "aderpropertylayout.cpp");
        Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException((unsigned int)v36, v21, v22, v20, 0);
        throw (Spectre::Engine::EngineInvalidArgException *)v36;
      }
      if ( (_DWORD)v15 == 8 )
      {
        v30[0] = *(_DWORD *)(v13 + v14 + 40);
        v30[1] = *(_DWORD *)(v10 + 40);
        std::vector<std::pair<unsigned int,unsigned int>>::emplace_back<std::pair<unsigned int,unsigned int>>(v8, v30);
      }
      else
      {
        TypeSizeInElements = Spectre::Engine::ShaderPropertyLayout::GetTypeSizeInElements(v15);
        v17 = 0;
        if ( TypeSizeInElements > 0 )
        {
          v18 = TypeSizeInElements;
          do
          {
            v31[0] = v17 + *(_DWORD *)(v13 + v14 + 40);
            v31[1] = v17 + *(_DWORD *)(v10 + 40);
            std::vector<std::pair<unsigned int,unsigned int>>::emplace_back<std::pair<unsigned int,unsigned int>>(
              v6,
              v31);
            ++v17;
          }
          while ( v17 < v18 );
          v2 = a2;
        }
      }
      v11 = v29;
    }
    v10 += 56;
  }
  v27 = (std::_Ref_count_base *)v2[1];
  if ( v27 )
    std::_Ref_count_base::_Decref(v27);
}

```

## disassembly

```asm
0x180079f0c  mov     [rsp-8+arg_10], rbx
0x180079f11  push    rbp
0x180079f12  push    rsi
0x180079f13  push    rdi
0x180079f14  push    r12
0x180079f16  push    r13
0x180079f18  push    r14
0x180079f1a  push    r15
0x180079f1c  lea     rbp, [rsp-20h]
0x180079f21  sub     rsp, 120h
0x180079f28  mov     rax, cs:__security_cookie
0x180079f2f  xor     rax, rsp
0x180079f32  mov     [rbp+50h+var_40], rax
0x180079f36  mov     rsi, rdx
0x180079f39  mov     [rsp+150h+var_120], rdx
0x180079f3e  mov     rdi, rcx
0x180079f41  mov     [rsp+150h+var_F8], rdx
0x180079f46  cmp     dword ptr [rcx+490h], 1
0x180079f4d  jz      short loc_180079F98
0x180079f4f  lea     rdx, aShaderproperty_23; "ShaderPropertyLayout::SetMasterLayout()"...
0x180079f56  lea     rcx, [rsp+150h+var_F0]
0x180079f5b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180079f60  nop
0x180079f61  lea     rdx, aOnecoreuapWind_1; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180079f68  lea     rcx, [rbp+50h+var_D0]
0x180079f6c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180079f71  mov     [rsp+150h+var_130], 0
0x180079f76  lea     r9, [rsp+150h+var_F0]
0x180079f7b  mov     rdx, rax
0x180079f7e  lea     rcx, [rbp+50h+pExceptionObject]
0x180079f82  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x180079f87  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x180079f8e  lea     rcx, [rbp+50h+pExceptionObject]; pExceptionObject
0x180079f92  call    _CxxThrowException_0
0x180079f98  add     rcx, 498h
0x180079f9f  call    ??4?$shared_ptr@VLight@Engine@Spectre@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Spectre::Engine::Light>::operator=(std::shared_ptr<Spectre::Engine::Light> const &)
0x180079fa4  lea     r15, [rdi+4A8h]
0x180079fab  mov     rax, [r15]
0x180079fae  cmp     rax, [r15+8]
0x180079fb2  jz      short loc_180079FB8
0x180079fb4  mov     [r15+8], rax
0x180079fb8  lea     r14, [rdi+4C0h]
0x180079fbf  mov     rax, [r14]
0x180079fc2  cmp     rax, [r14+8]
0x180079fc6  jz      short loc_180079FCC
0x180079fc8  mov     [r14+8], rax
0x180079fcc  mov     rbx, [rdi+38h]
0x180079fd0  mov     rax, [rdi+40h]
0x180079fd4  mov     [rsp+150h+var_110], rax
0x180079fd9  cmp     rbx, rax
0x180079fdc  jz      loc_18007A147
0x180079fe2  cmp     dword ptr [rbx+30h], 0
0x180079fe6  jz      loc_18007A07E
0x180079fec  mov     r13, [rsi]
0x180079fef  movzx   eax, word ptr [rbx+20h]
0x180079ff3  movzx   ecx, word ptr [r13+rax*2+80h]
0x180079ffc  mov     eax, 0FFFFh
0x18007a001  cmp     cx, ax
0x18007a004  jz      loc_18007A0E7
0x18007a00a  imul    r12, rcx, 38h ; '8'
0x18007a00e  mov     r13, [r13+38h]
0x18007a012  mov     ecx, [rbx+24h]
0x18007a015  cmp     ecx, [r12+r13+24h]
0x18007a01a  jnz     short loc_18007A087
0x18007a01c  cmp     ecx, 8
0x18007a01f  jnz     short loc_18007A040
0x18007a021  mov     eax, [r12+r13+28h]
0x18007a026  mov     [rsp+150h+var_108], eax
0x18007a02a  mov     eax, [rbx+28h]
0x18007a02d  mov     [rsp+150h+var_104], eax
0x18007a031  lea     rdx, [rsp+150h+var_108]
0x18007a036  mov     rcx, r14
0x18007a039  call    ??$emplace_back@U?$pair@II@std@@@?$vector@U?$pair@II@std@@V?$allocator@U?$pair@II@std@@@2@@std@@QEAAAEAU?$pair@II@1@$$QEAU21@@Z; std::vector<std::pair<uint,uint>>::emplace_back<std::pair<uint,uint>>(std::pair<uint,uint> &&)
0x18007a03e  jmp     short loc_18007A079
0x18007a040  call    ?GetTypeSizeInElements@ShaderPropertyLayout@Engine@Spectre@@SAIW4ShaderPropertyType@23@@Z; Spectre::Engine::ShaderPropertyLayout::GetTypeSizeInElements(Spectre::Engine::ShaderPropertyType)
0x18007a045  xor     edi, edi
0x18007a047  test    eax, eax
0x18007a049  jle     short loc_18007A079
0x18007a04b  mov     esi, eax
0x18007a04d  mov     edx, [r12+r13+28h]
0x18007a052  add     edx, edi
0x18007a054  mov     [rsp+150h+var_100], edx
0x18007a058  mov     edx, [rbx+28h]
0x18007a05b  add     edx, edi
0x18007a05d  mov     [rsp+150h+var_FC], edx
0x18007a061  lea     rdx, [rsp+150h+var_100]
0x18007a066  mov     rcx, r15
0x18007a069  call    ??$emplace_back@U?$pair@II@std@@@?$vector@U?$pair@II@std@@V?$allocator@U?$pair@II@std@@@2@@std@@QEAAAEAU?$pair@II@1@$$QEAU21@@Z; std::vector<std::pair<uint,uint>>::emplace_back<std::pair<uint,uint>>(std::pair<uint,uint> &&)
0x18007a06e  inc     edi
0x18007a070  cmp     edi, esi
0x18007a072  jl      short loc_18007A04D
0x18007a074  mov     rsi, [rsp+150h+var_120]
0x18007a079  mov     rax, [rsp+150h+var_110]
0x18007a07e  add     rbx, 38h ; '8'
0x18007a082  jmp     loc_180079FD9
0x18007a087  mov     r8, rbx
0x18007a08a  lea     rdx, aShaderproperty_26; "ShaderPropertyLayout::SetMasterLayout()"...
0x18007a091  lea     rcx, [rbp+50h+var_D0]
0x18007a095  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBDAEBV10@@Z; std::operator+<char>(char const * const,std::string const &)
0x18007a09a  nop
0x18007a09b  lea     r8, aImportedByThis; "' imported by this layout"
0x18007a0a2  mov     rdx, rax
0x18007a0a5  lea     rcx, [rbp+50h+pExceptionObject]
0x18007a0a9  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x18007a0ae  mov     rbx, rax
0x18007a0b1  lea     rdx, aOnecoreuapWind_1; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18007a0b8  lea     rcx, [rsp+150h+var_F0]
0x18007a0bd  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18007a0c2  mov     [rsp+150h+var_130], 0
0x18007a0c7  mov     r9, rbx
0x18007a0ca  mov     rdx, rax
0x18007a0cd  lea     rcx, [rbp+50h+var_78]
0x18007a0d1  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18007a0d6  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18007a0dd  lea     rcx, [rbp+50h+var_78]; pExceptionObject
0x18007a0e1  call    _CxxThrowException_0
0x18007a0e7  mov     r8, rbx
0x18007a0ea  lea     rdx, aShaderproperty_15; "ShaderPropertyLayout::SetMasterLayout()"...
0x18007a0f1  lea     rcx, [rbp+50h+pExceptionObject]
0x18007a0f5  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBDAEBV10@@Z; std::operator+<char>(char const * const,std::string const &)
0x18007a0fa  nop
0x18007a0fb  lea     r8, aRequiredForImp; "' required for import by this layout"
0x18007a102  mov     rdx, rax
0x18007a105  lea     rcx, [rbp+50h+var_D0]
0x18007a109  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x18007a10e  mov     rbx, rax
0x18007a111  lea     rdx, aOnecoreuapWind_1; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18007a118  lea     rcx, [rsp+150h+var_F0]
0x18007a11d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18007a122  mov     [rsp+150h+var_130], 0
0x18007a127  mov     r9, rbx
0x18007a12a  mov     rdx, rax
0x18007a12d  lea     rcx, [rbp+50h+var_78]
0x18007a131  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18007a136  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18007a13d  lea     rcx, [rbp+50h+var_78]; pExceptionObject
0x18007a141  call    _CxxThrowException_0
0x18007a147  mov     rcx, [rsi+8]; this
0x18007a14b  test    rcx, rcx
0x18007a14e  jz      short loc_18007A155
0x18007a150  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007a155  mov     rcx, [rbp+50h+var_40]
0x18007a159  xor     rcx, rsp; StackCookie
0x18007a15c  call    __security_check_cookie
0x18007a161  mov     rbx, [rsp+150h+arg_10]
0x18007a169  add     rsp, 120h
0x18007a170  pop     r15
0x18007a172  pop     r14
0x18007a174  pop     r13
0x18007a176  pop     r12
0x18007a178  pop     rdi
0x18007a179  pop     rsi
0x18007a17a  pop     rbp
0x18007a17b  retn
```
