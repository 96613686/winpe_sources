# Spectre::Engine::ShaderManager::AddProperty(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x18004bfc0`
- end: `0x18004c0fc`
- name: `?AddProperty@ShaderManager@Engine@Spectre@@QEAA?AW4ShaderProperty@23@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `316`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180078dfc`
- `0x180079298`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x180011f64`
- `0x180014554`
- `0x180038ddc`
- `0x18004ab3c`
- `0x18004bfc0`
- `0x18004c5e4`

## string_xrefs

- `0x18004c000`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shadermanager.cpp`
- `0x18004c0c6`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shadermanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Spectre::Engine::ShaderManager::AddProperty(__int64 a1, __int64 a2)
{
  int v4; // eax
  int v5; // r8d
  __int64 v6; // rbx
  int v8; // eax
  int v9; // r8d
  _BYTE v10[16]; // [rsp+30h] [rbp-49h] BYREF
  _BYTE v11[32]; // [rsp+40h] [rbp-39h] BYREF
  _BYTE v12[32]; // [rsp+60h] [rbp-19h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+80h] [rbp+7h] BYREF

  if ( !*(_QWORD *)(a2 + 16) )
  {
    std::string::string(v12, "ShaderManager::RegisterShaderProperty() -- shader property name cannot be empty");
    v4 = std::string::string(
           v11,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\shadermanager.cpp");
    Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
      (unsigned int)pExceptionObject,
      v4,
      v5,
      (unsigned int)v12,
      0);
    throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
  }
  LOWORD(v6) = Spectre::Engine::ShaderManager::FindProperty();
  if ( (_WORD)v6 == 511 )
  {
    v6 = *(int *)(a1 + 18488);
    if ( (int)v6 >= 512 )
    {
      std::string::string(
        v11,
        "ShaderManager::RegisterProperty() -- property could not be registered because the maximum number of properties has been reached");
      v8 = std::string::string(
             v12,
             "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\shadermanager.cpp");
      Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(
        (unsigned int)pExceptionObject,
        v8,
        v9,
        (unsigned int)v11,
        0);
      throw (Spectre::Engine::EngineInvalidArgException *)pExceptionObject;
    }
    *(_DWORD *)(a1 + 18488) = v6 + 1;
    *(_WORD *)(*(_QWORD *)std::map<std::string,enum Spectre::Engine::ShaderProperty>::_Try_emplace<std::string const &,>(
                            a1 + 2088,
                            v10,
                            a2)
             + 64LL) = v6;
    std::string::operator=(a1 + 32 * v6 + 2104, a2);
  }
  return (unsigned __int16)v6;
}

```

## disassembly

```asm
0x18004bfc0  mov     [rsp-8+arg_10], rbx
0x18004bfc5  push    rbp
0x18004bfc6  push    rsi
0x18004bfc7  push    rdi
0x18004bfc8  lea     rbp, [rsp-47h]
0x18004bfcd  sub     rsp, 0C0h
0x18004bfd4  mov     rax, cs:__security_cookie
0x18004bfdb  xor     rax, rsp
0x18004bfde  mov     [rbp+57h+var_18], rax
0x18004bfe2  mov     rsi, rdx
0x18004bfe5  mov     rdi, rcx
0x18004bfe8  cmp     qword ptr [rdx+10h], 0
0x18004bfed  jnz     short loc_18004C036
0x18004bfef  lea     rdx, aShadermanagerR; "ShaderManager::RegisterShaderProperty()"...
0x18004bff6  lea     rcx, [rbp+57h+var_70]
0x18004bffa  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18004bfff  nop
0x18004c000  lea     rdx, aOnecoreuapWind_15; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18004c007  lea     rcx, [rbp+57h+var_90]
0x18004c00b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18004c010  mov     [rsp+0D0h+var_B0], 0
0x18004c015  lea     r9, [rbp+57h+var_70]
0x18004c019  mov     rdx, rax
0x18004c01c  lea     rcx, [rbp+57h+pExceptionObject]
0x18004c020  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18004c025  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18004c02c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18004c030  call    _CxxThrowException_0
0x18004c036  call    ?FindProperty@ShaderManager@Engine@Spectre@@QEBA?AW4ShaderProperty@23@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Spectre::Engine::ShaderManager::FindProperty(std::string const &)
0x18004c03b  movzx   ebx, ax
0x18004c03e  mov     eax, 1FFh
0x18004c043  cmp     bx, ax
0x18004c046  jnz     short loc_18004C093
0x18004c048  movsxd  rbx, dword ptr [rdi+4838h]
0x18004c04f  cmp     ebx, 200h
0x18004c055  jge     short loc_18004C0B5
0x18004c057  lea     eax, [rbx+1]
0x18004c05a  mov     [rdi+4838h], eax
0x18004c060  lea     rcx, [rdi+828h]
0x18004c067  mov     r8, rsi
0x18004c06a  lea     rdx, [rbp+57h+var_A0]
0x18004c06e  call    ??$_Try_emplace@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$$V@?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ShaderProperty@Engine@Spectre@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ShaderProperty@Engine@Spectre@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ShaderProperty@Engine@Spectre@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string,Spectre::Engine::ShaderProperty>::_Try_emplace<std::string const &,>(std::string const &)
0x18004c073  mov     rcx, [rax]
0x18004c076  mov     [rcx+40h], bx
0x18004c07a  mov     rcx, rbx
0x18004c07d  shl     rcx, 5
0x18004c081  add     rcx, 838h
0x18004c088  add     rcx, rdi
0x18004c08b  mov     rdx, rsi
0x18004c08e  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@AEBV01@@Z; std::string::operator=(std::string const &)
0x18004c093  movzx   eax, bx
0x18004c096  mov     rcx, [rbp+57h+var_18]
0x18004c09a  xor     rcx, rsp; StackCookie
0x18004c09d  call    __security_check_cookie
0x18004c0a2  mov     rbx, [rsp+0D0h+arg_10]
0x18004c0aa  add     rsp, 0C0h
0x18004c0b1  pop     rdi
0x18004c0b2  pop     rsi
0x18004c0b3  pop     rbp
0x18004c0b4  retn
0x18004c0b5  lea     rdx, aShadermanagerR_0; "ShaderManager::RegisterProperty() -- pr"...
0x18004c0bc  lea     rcx, [rbp+57h+var_90]
0x18004c0c0  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18004c0c5  nop
0x18004c0c6  lea     rdx, aOnecoreuapWind_15; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18004c0cd  lea     rcx, [rbp+57h+var_70]
0x18004c0d1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18004c0d6  mov     [rsp+0D0h+var_B0], 0
0x18004c0db  lea     r9, [rbp+57h+var_90]
0x18004c0df  mov     rdx, rax
0x18004c0e2  lea     rcx, [rbp+57h+pExceptionObject]
0x18004c0e6  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18004c0eb  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18004c0f2  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18004c0f6  call    _CxxThrowException_0
```
