# Spectre::Engine::ShaderManager::CreateShaderFamily(std::basic_string<char,std::char_traits<char>,std::allocator<char>>,std::shared_ptr<Spectre::Engine::IShaderExtension>)

- ea: `0x18004c330`
- end: `0x18004c4ca`
- name: `?CreateShaderFamily@ShaderManager@Engine@Spectre@@QEAA?AV?$shared_ptr@VShaderFamily@Engine@Spectre@@@std@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@V?$shared_ptr@VIShaderExtension@Engine@Spectre@@@5@@Z`
- size: `410`
- prototype: ``
- caller_count: `5`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180075690`
- `0x180076150`
- `0x1800764d0`
- `0x180077560`
- `0x18008f130`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x18001128c`
- `0x180011f64`
- `0x180012ba8`
- `0x180013664`
- `0x180018318`
- `0x18001c630`
- `0x18001c720`
- `0x180038ddc`
- `0x180040a6c`
- `0x18004a914`
- `0x18004b10c`
- `0x18004c330`
- `0x18004cfa0`

## string_xrefs

- `0x18004c38d`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shadermanager.cpp`
- `0x18004c405`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shadermanager.cpp`
- `0x18004c3ef`: `' already exists`
- `0x18004c380`: `ShaderManager::CreateShaderFamily() -- shader family must have a non-empty name`
- `0x18004c3de`: `ShaderManager::CreateShaderFamily() -- shader family with name '`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Spectre::Engine::ShaderManager::CreateShaderFamily(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v8; // eax
  int v9; // r8d
  __int64 v10; // rax
  __int64 v11; // rax
  int v12; // ebx
  int v13; // eax
  int v14; // r8d
  __int64 v15; // rax
  _QWORD *v16; // rax
  std::_Ref_count_base *v17; // rcx
  _BYTE v19[8]; // [rsp+38h] [rbp-C8h] BYREF
  std::_Ref_count_base *v20; // [rsp+40h] [rbp-C0h]
  __int64 v21; // [rsp+48h] [rbp-B8h]
  __int64 v22; // [rsp+50h] [rbp-B0h]
  __int64 v23; // [rsp+58h] [rbp-A8h]
  _BYTE v24[32]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v25[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v27[56]; // [rsp+D8h] [rbp-28h] BYREF

  v21 = a2;
  v23 = a3;
  v22 = a4;
  if ( !*(_QWORD *)(a3 + 16) )
  {
    std::string::string(v24, "ShaderManager::CreateShaderFamily() -- shader family must have a non-empty name");
    v8 = std::string::string(
           v25,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\shadermanager.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v8,
      v9,
      (unsigned int)v24,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  v10 = std::string::string(v24, a3);
  if ( (unsigned __int8)Spectre::Engine::ShaderManager::HasShaderFamily(a1, v10) )
  {
    v11 = std::operator+<char>(v25, "ShaderManager::CreateShaderFamily() -- shader family with name '", a3);
    v12 = std::operator+<char>(pExceptionObject, v11, "' already exists");
    v13 = std::string::string(
            v24,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\shadermanager.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException((unsigned int)v27, v13, v14, v12, 0);
    throw (Spectre::Engine::EngineInvalidArgException *)v27;
  }
  v15 = std::enable_shared_from_this<Spectre::Engine::Component>::shared_from_this(a1, v19);
  std::make_shared<Spectre::Engine::ShaderFamily,std::string &,std::shared_ptr<Spectre::Engine::ShaderManager>,std::shared_ptr<Spectre::Engine::IShaderExtension> &>(
    a2,
    a3,
    v15,
    a4);
  if ( v20 )
    std::_Ref_count_base::_Decref(v20);
  v16 = (_QWORD *)std::map<std::string,std::shared_ptr<Spectre::Engine::ShaderFamily>>::_Try_emplace<std::string const &,>(
                    a1 + 18560,
                    v19,
                    a3);
  std::shared_ptr<Spectre::Engine::Light>::operator=(*v16 + 64LL, a2);
  std::string::_Tidy_deallocate(a3);
  v17 = *(std::_Ref_count_base **)(a4 + 8);
  if ( v17 )
    std::_Ref_count_base::_Decref(v17);
  return a2;
}

```

## disassembly

```asm
0x18004c330  push    rbp
0x18004c332  push    rbx
0x18004c333  push    rsi
0x18004c334  push    rdi
0x18004c335  push    r14
0x18004c337  lea     rbp, [rsp-20h]
0x18004c33c  sub     rsp, 120h
0x18004c343  mov     rax, cs:__security_cookie
0x18004c34a  xor     rax, rsp
0x18004c34d  mov     [rbp+40h+var_30], rax
0x18004c351  mov     rsi, r9
0x18004c354  mov     rbx, r8
0x18004c357  mov     rdi, rdx
0x18004c35a  mov     r14, rcx
0x18004c35d  mov     [rsp+140h+var_F8], rdx
0x18004c362  mov     [rsp+140h+var_E8], rbx
0x18004c367  mov     [rsp+140h+var_F0], r9
0x18004c36c  mov     [rsp+140h+var_110], 0
0x18004c374  lea     rcx, [rsp+140h+var_E0]
0x18004c379  cmp     qword ptr [r8+10h], 0
0x18004c37e  jnz     short loc_18004C3C4
0x18004c380  lea     rdx, aShadermanagerC_0; "ShaderManager::CreateShaderFamily() -- "...
0x18004c387  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18004c38c  nop
0x18004c38d  lea     rdx, aOnecoreuapWind_15; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18004c394  lea     rcx, [rbp+40h+var_C0]
0x18004c398  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18004c39d  mov     [rsp+140h+var_120], 0
0x18004c3a2  lea     r9, [rsp+140h+var_E0]
0x18004c3a7  mov     rdx, rax
0x18004c3aa  lea     rcx, [rbp+40h+pExceptionObject]
0x18004c3ae  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18004c3b3  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18004c3ba  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x18004c3be  call    _CxxThrowException_0
0x18004c3c4  mov     rdx, rbx
0x18004c3c7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x18004c3cc  mov     rdx, rax
0x18004c3cf  mov     rcx, r14
0x18004c3d2  call    ?HasShaderFamily@ShaderManager@Engine@Spectre@@QEAA_NV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Spectre::Engine::ShaderManager::HasShaderFamily(std::string)
0x18004c3d7  test    al, al
0x18004c3d9  jz      short loc_18004C43B
0x18004c3db  mov     r8, rbx
0x18004c3de  lea     rdx, aShadermanagerC; "ShaderManager::CreateShaderFamily() -- "...
0x18004c3e5  lea     rcx, [rbp+40h+var_C0]
0x18004c3e9  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBDAEBV10@@Z; std::operator+<char>(char const * const,std::string const &)
0x18004c3ee  nop
0x18004c3ef  lea     r8, aAlreadyExists_0; "' already exists"
0x18004c3f6  mov     rdx, rax
0x18004c3f9  lea     rcx, [rbp+40h+pExceptionObject]
0x18004c3fd  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x18004c402  mov     rbx, rax
0x18004c405  lea     rdx, aOnecoreuapWind_15; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18004c40c  lea     rcx, [rsp+140h+var_E0]
0x18004c411  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18004c416  mov     [rsp+140h+var_120], 0
0x18004c41b  mov     r9, rbx
0x18004c41e  mov     rdx, rax
0x18004c421  lea     rcx, [rbp+40h+var_68]
0x18004c425  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18004c42a  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18004c431  lea     rcx, [rbp+40h+var_68]; pExceptionObject
0x18004c435  call    _CxxThrowException_0
0x18004c43b  lea     rdx, [rsp+140h+var_108]
0x18004c440  mov     rcx, r14
0x18004c443  call    ?shared_from_this@?$enable_shared_from_this@VComponent@Engine@Spectre@@@std@@QEAA?AV?$shared_ptr@VComponent@Engine@Spectre@@@2@XZ; std::enable_shared_from_this<Spectre::Engine::Component>::shared_from_this(void)
0x18004c448  nop
0x18004c449  mov     r9, rsi
0x18004c44c  mov     r8, rax
0x18004c44f  mov     rdx, rbx
0x18004c452  mov     rcx, rdi
0x18004c455  call    ??$make_shared@VShaderFamily@Engine@Spectre@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@VShaderManager@Engine@Spectre@@@5@AEAV?$shared_ptr@VIShaderExtension@Engine@Spectre@@@5@@std@@YA?AV?$shared_ptr@VShaderFamily@Engine@Spectre@@@0@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV?$shared_ptr@VShaderManager@Engine@Spectre@@@0@AEAV?$shared_ptr@VIShaderExtension@Engine@Spectre@@@0@@Z; std::make_shared<Spectre::Engine::ShaderFamily,std::string &,std::shared_ptr<Spectre::Engine::ShaderManager>,std::shared_ptr<Spectre::Engine::IShaderExtension> &>(std::string &,std::shared_ptr<Spectre::Engine::ShaderManager> &&,std::shared_ptr<Spectre::Engine::IShaderExtension> &)
0x18004c45a  mov     [rsp+140h+var_110], 1
0x18004c462  mov     rcx, [rsp+140h+var_100]; this
0x18004c467  test    rcx, rcx
0x18004c46a  jz      short loc_18004C471
0x18004c46c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004c471  lea     rcx, [r14+4880h]
0x18004c478  mov     r8, rbx
0x18004c47b  lea     rdx, [rsp+140h+var_108]
0x18004c480  call    ??$_Try_emplace@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$$V@?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@VShaderFamily@Engine@Spectre@@@2@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@VShaderFamily@Engine@Spectre@@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@VShaderFamily@Engine@Spectre@@@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string,std::shared_ptr<Spectre::Engine::ShaderFamily>>::_Try_emplace<std::string const &,>(std::string const &)
0x18004c485  mov     rcx, [rax]
0x18004c488  add     rcx, 40h ; '@'
0x18004c48c  mov     rdx, rdi
0x18004c48f  call    ??4?$shared_ptr@VLight@Engine@Spectre@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Spectre::Engine::Light>::operator=(std::shared_ptr<Spectre::Engine::Light> const &)
0x18004c494  nop
0x18004c495  mov     rcx, rbx
0x18004c498  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18004c49d  nop
0x18004c49e  mov     rcx, [rsi+8]; this
0x18004c4a2  test    rcx, rcx
0x18004c4a5  jz      short loc_18004C4AC
0x18004c4a7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004c4ac  mov     rax, rdi
0x18004c4af  mov     rcx, [rbp+40h+var_30]
0x18004c4b3  xor     rcx, rsp; StackCookie
0x18004c4b6  call    __security_check_cookie
0x18004c4bb  add     rsp, 120h
0x18004c4c2  pop     r14
0x18004c4c4  pop     rdi
0x18004c4c5  pop     rsi
0x18004c4c6  pop     rbx
0x18004c4c7  pop     rbp
0x18004c4c8  retn
```
