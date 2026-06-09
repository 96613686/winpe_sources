# Spectre::Engine::ShaderManager::AddShaderProgram(std::basic_string<char,std::char_traits<char>,std::allocator<char>>,Spectre::Engine::EShaderType,Spectre::Engine::ShaderProgram)

- ea: `0x18004c104`
- end: `0x18004c2e0`
- name: `?AddShaderProgram@ShaderManager@Engine@Spectre@@QEAAXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4EShaderType@23@VShaderProgram@23@@Z`
- size: `476`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1800333b8`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x180011f64`
- `0x180012ba8`
- `0x18001c630`
- `0x18001c720`
- `0x18001e46c`
- `0x180038ddc`
- `0x18004a50c`
- `0x18004b1fc`
- `0x18004b848`
- `0x18004c104`
- `0x18004d600`
- `0x18004d620`

## string_xrefs

- `0x18004c151`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shadermanager.cpp`
- `0x18004c1d3`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shadermanager.cpp`
- `0x18004c227`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shadermanager.cpp`
- `0x18004c1bd`: `' is already added`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Spectre::Engine::ShaderManager::AddShaderProgram(
        __int64 a1,
        __int64 a2,
        int a3,
        Spectre::Engine::ShaderProgram *a4)
{
  int v7; // eax
  int v8; // r8d
  __int64 v9; // rsi
  __int64 v10; // rax
  int v11; // ebx
  int v12; // eax
  int v13; // r8d
  int v14; // eax
  int v15; // r8d
  _QWORD *v16; // rax
  _BYTE v18[16]; // [rsp+30h] [rbp-D0h] BYREF
  Spectre::Engine::ShaderProgram *v19; // [rsp+40h] [rbp-C0h]
  __int64 v20; // [rsp+48h] [rbp-B8h]
  _BYTE v21[32]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v22[32]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD pExceptionObject[2]; // [rsp+90h] [rbp-70h] BYREF
  int v24; // [rsp+A0h] [rbp-60h]
  __int128 v25; // [rsp+A8h] [rbp-58h]
  _BYTE v26[56]; // [rsp+C8h] [rbp-38h] BYREF

  v20 = a2;
  v19 = a4;
  if ( !*(_QWORD *)(a2 + 16) )
  {
    std::string::string(
      v22,
      "ShaderManager::AddShaderProgram() -- shader program cannot be registered with an empty name");
    v7 = std::string::string(
           v21,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\shadermanager.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v7,
      v8,
      (unsigned int)v22,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  v9 = a1 + 18576;
  if ( *(_QWORD *)std::_Tree<std::_Tmap_traits<std::string,Spectre::Engine::ShaderManager::ShaderInfo,std::less<std::string>,std::allocator<std::pair<std::string const,Spectre::Engine::ShaderManager::ShaderInfo>>,0>>::find(
                    a1 + 18576,
                    v18,
                    a2) != *(_QWORD *)(a1 + 18576) )
  {
    v10 = std::operator+<char>(v21, "ShaderManager::AddShaderProgram() -- shader program for name '", a2);
    v11 = std::operator+<char>(pExceptionObject, v10, "' is already added");
    v12 = std::string::string(
            v22,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\shadermanager.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException((unsigned int)v26, v12, v13, v11, 0);
    throw (Spectre::Engine::EngineInvalidArgException *)v26;
  }
  if ( Spectre::Engine::ShaderProgram::empty(a4) )
  {
    std::string::string(
      v21,
      "ShaderManager::AddShaderProgram() -- shader program cannot be registered with zero-length program buffer");
    v14 = std::string::string(
            v22,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\shadermanager.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)v26,
      v14,
      v15,
      (unsigned int)v21,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)v26;
  }
  v16 = (_QWORD *)std::make_shared<Spectre::Engine::ShaderProgram,Spectre::Engine::ShaderProgram>(v18, a4);
  pExceptionObject[0] = *v16;
  pExceptionObject[1] = v16[1];
  *v16 = 0;
  v16[1] = 0;
  v24 = a3;
  v25 = 0;
  std::_Tree<std::_Tmap_traits<std::string,Spectre::Engine::ShaderManager::ShaderInfo,std::less<std::string>,std::allocator<std::pair<std::string const,Spectre::Engine::ShaderManager::ShaderInfo>>,0>>::_Emplace<std::string,Spectre::Engine::ShaderManager::ShaderInfo>(
    v9,
    v21,
    a2,
    pExceptionObject);
  Spectre::Engine::ShaderManager::ShaderInfo::~ShaderInfo((Spectre::Engine::ShaderManager::ShaderInfo *)pExceptionObject);
  std::string::_Tidy_deallocate(a2);
  return std::vector<unsigned char>::_Tidy(a4);
}

```

## disassembly

```asm
0x18004c104  push    rbp
0x18004c106  push    rbx
0x18004c107  push    rsi
0x18004c108  push    rdi
0x18004c109  push    r14
0x18004c10b  lea     rbp, [rsp-10h]
0x18004c110  sub     rsp, 110h
0x18004c117  mov     rax, cs:__security_cookie
0x18004c11e  xor     rax, rsp
0x18004c121  mov     [rbp+30h+var_30], rax
0x18004c125  mov     rdi, r9
0x18004c128  mov     r14d, r8d
0x18004c12b  mov     rbx, rdx
0x18004c12e  mov     [rsp+130h+var_E8], rdx
0x18004c133  mov     [rsp+130h+var_F0], r9
0x18004c138  cmp     qword ptr [rdx+10h], 0
0x18004c13d  jnz     short loc_18004C189
0x18004c13f  lea     rdx, aShadermanagerA_4; "ShaderManager::AddShaderProgram() -- sh"...
0x18004c146  lea     rcx, [rsp+130h+var_C0]
0x18004c14b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18004c150  nop
0x18004c151  lea     rdx, aOnecoreuapWind_15; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18004c158  lea     rcx, [rsp+130h+var_E0]
0x18004c15d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18004c162  mov     [rsp+130h+var_110], 0
0x18004c167  lea     r9, [rsp+130h+var_C0]
0x18004c16c  mov     rdx, rax
0x18004c16f  lea     rcx, [rbp+30h+pExceptionObject]
0x18004c173  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18004c178  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18004c17f  lea     rcx, [rbp+30h+pExceptionObject]; pExceptionObject
0x18004c183  call    _CxxThrowException_0
0x18004c189  lea     rsi, [rcx+4890h]
0x18004c190  mov     r8, rbx
0x18004c193  lea     rdx, [rsp+130h+var_100]
0x18004c198  mov     rcx, rsi
0x18004c19b  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UShaderInfo@ShaderManager@Engine@Spectre@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UShaderInfo@ShaderManager@Engine@Spectre@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UShaderInfo@ShaderManager@Engine@Spectre@@@std@@@std@@@std@@@2@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::string,Spectre::Engine::ShaderManager::ShaderInfo,std::less<std::string>,std::allocator<std::pair<std::string const,Spectre::Engine::ShaderManager::ShaderInfo>>,0>>::find(std::string const &)
0x18004c1a0  mov     rcx, [rsi]
0x18004c1a3  cmp     [rax], rcx
0x18004c1a6  jz      short loc_18004C209
0x18004c1a8  mov     r8, rbx
0x18004c1ab  lea     rdx, aShadermanagerA_1; "ShaderManager::AddShaderProgram() -- sh"...
0x18004c1b2  lea     rcx, [rsp+130h+var_E0]
0x18004c1b7  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBDAEBV10@@Z; std::operator+<char>(char const * const,std::string const &)
0x18004c1bc  nop
0x18004c1bd  lea     r8, aIsAlreadyAdded; "' is already added"
0x18004c1c4  mov     rdx, rax
0x18004c1c7  lea     rcx, [rbp+30h+pExceptionObject]
0x18004c1cb  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x18004c1d0  mov     rbx, rax
0x18004c1d3  lea     rdx, aOnecoreuapWind_15; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18004c1da  lea     rcx, [rsp+130h+var_C0]
0x18004c1df  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18004c1e4  mov     [rsp+130h+var_110], 0
0x18004c1e9  mov     r9, rbx
0x18004c1ec  mov     rdx, rax
0x18004c1ef  lea     rcx, [rbp+30h+var_68]
0x18004c1f3  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18004c1f8  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18004c1ff  lea     rcx, [rbp+30h+var_68]; pExceptionObject
0x18004c203  call    _CxxThrowException_0
0x18004c209  mov     rcx, rdi; this
0x18004c20c  call    ?empty@ShaderProgram@Engine@Spectre@@QEBA_NXZ; Spectre::Engine::ShaderProgram::empty(void)
0x18004c211  test    al, al
0x18004c213  jz      short loc_18004C25F
0x18004c215  lea     rdx, aShadermanagerA_6; "ShaderManager::AddShaderProgram() -- sh"...
0x18004c21c  lea     rcx, [rsp+130h+var_E0]
0x18004c221  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18004c226  nop
0x18004c227  lea     rdx, aOnecoreuapWind_15; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18004c22e  lea     rcx, [rsp+130h+var_C0]
0x18004c233  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18004c238  mov     [rsp+130h+var_110], 0
0x18004c23d  lea     r9, [rsp+130h+var_E0]
0x18004c242  mov     rdx, rax
0x18004c245  lea     rcx, [rbp+30h+var_68]
0x18004c249  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18004c24e  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18004c255  lea     rcx, [rbp+30h+var_68]; pExceptionObject
0x18004c259  call    _CxxThrowException_0
0x18004c25f  mov     rdx, rdi
0x18004c262  lea     rcx, [rsp+130h+var_100]
0x18004c267  call    ??$make_shared@VShaderProgram@Engine@Spectre@@V123@@std@@YA?AV?$shared_ptr@VShaderProgram@Engine@Spectre@@@0@$$QEAVShaderProgram@Engine@Spectre@@@Z; std::make_shared<Spectre::Engine::ShaderProgram,Spectre::Engine::ShaderProgram>(Spectre::Engine::ShaderProgram &&)
0x18004c26c  mov     rcx, [rax]
0x18004c26f  mov     [rbp+30h+pExceptionObject], rcx
0x18004c273  mov     rdx, [rax+8]
0x18004c277  mov     [rbp+30h+var_98], rdx
0x18004c27b  mov     qword ptr [rax], 0
0x18004c282  mov     qword ptr [rax+8], 0
0x18004c28a  mov     [rbp+30h+var_90], r14d
0x18004c28e  xorps   xmm1, xmm1
0x18004c291  movdqu  [rbp+30h+var_88], xmm1
0x18004c296  lea     r9, [rbp+30h+pExceptionObject]
0x18004c29a  mov     r8, rbx
0x18004c29d  lea     rdx, [rsp+130h+var_E0]
0x18004c2a2  mov     rcx, rsi
0x18004c2a5  call    ??$_Emplace@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UShaderInfo@ShaderManager@Engine@Spectre@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UShaderInfo@ShaderManager@Engine@Spectre@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UShaderInfo@ShaderManager@Engine@Spectre@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UShaderInfo@ShaderManager@Engine@Spectre@@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@$$QEAUShaderInfo@ShaderManager@Engine@Spectre@@@Z; std::_Tree<std::_Tmap_traits<std::string,Spectre::Engine::ShaderManager::ShaderInfo,std::less<std::string>,std::allocator<std::pair<std::string const,Spectre::Engine::ShaderManager::ShaderInfo>>,0>>::_Emplace<std::string,Spectre::Engine::ShaderManager::ShaderInfo>(std::string &&,Spectre::Engine::ShaderManager::ShaderInfo &&)
0x18004c2aa  nop
0x18004c2ab  lea     rcx, [rbp+30h+pExceptionObject]; this
0x18004c2af  call    ??1ShaderInfo@ShaderManager@Engine@Spectre@@QEAA@XZ; Spectre::Engine::ShaderManager::ShaderInfo::~ShaderInfo(void)
0x18004c2b4  nop
0x18004c2b5  mov     rcx, rbx
0x18004c2b8  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18004c2bd  nop
0x18004c2be  mov     rcx, rdi
0x18004c2c1  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18004c2c6  mov     rcx, [rbp+30h+var_30]
0x18004c2ca  xor     rcx, rsp; StackCookie
0x18004c2cd  call    __security_check_cookie
0x18004c2d2  add     rsp, 110h
0x18004c2d9  pop     r14
0x18004c2db  pop     rdi
0x18004c2dc  pop     rsi
0x18004c2dd  pop     rbx
0x18004c2de  pop     rbp
0x18004c2df  retn
```
