# Spectre::Engine::ShaderManager::AddOption(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x18004be90`
- end: `0x18004bfb8`
- name: `?AddOption@ShaderManager@Engine@Spectre@@QEAA?AW4ShaderOption@23@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `296`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18005ac1c`
- `0x18005f450`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x180011f64`
- `0x180014554`
- `0x180038ddc`
- `0x18004aa28`
- `0x18004be90`
- `0x18004c590`

## string_xrefs

- `0x18004bed0`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shadermanager.cpp`
- `0x18004bf82`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\shadermanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Spectre::Engine::ShaderManager::AddOption(__int64 a1, __int64 a2)
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
    std::string::string(v12, "ShaderManager::AddOption() -- shader option name cannot be empty");
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
  LODWORD(v6) = Spectre::Engine::ShaderManager::FindOption();
  if ( (_DWORD)v6 == -1 )
  {
    v6 = *(int *)(a1 + 2080);
    if ( (int)v6 >= 64 )
    {
      std::string::string(
        v11,
        "ShaderManager::AddOption() -- option could not be added because the maximum number of options has been reached");
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
    *(_DWORD *)(a1 + 2080) = v6 + 1;
    *(_DWORD *)(*(_QWORD *)std::map<std::string,enum Spectre::Engine::ShaderOption>::_Try_emplace<std::string const &,>(
                             a1 + 16,
                             v10,
                             a2)
              + 64LL) = v6;
    std::string::operator=(a1 + 32 * (v6 + 1), a2);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18004be90  mov     [rsp-8+arg_10], rbx
0x18004be95  push    rbp
0x18004be96  push    rsi
0x18004be97  push    rdi
0x18004be98  lea     rbp, [rsp-47h]
0x18004be9d  sub     rsp, 0C0h
0x18004bea4  mov     rax, cs:__security_cookie
0x18004beab  xor     rax, rsp
0x18004beae  mov     [rbp+57h+var_18], rax
0x18004beb2  mov     rsi, rdx
0x18004beb5  mov     rdi, rcx
0x18004beb8  cmp     qword ptr [rdx+10h], 0
0x18004bebd  jnz     short loc_18004BF06
0x18004bebf  lea     rdx, aShadermanagerA_3; "ShaderManager::AddOption() -- shader op"...
0x18004bec6  lea     rcx, [rbp+57h+var_70]
0x18004beca  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18004becf  nop
0x18004bed0  lea     rdx, aOnecoreuapWind_15; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18004bed7  lea     rcx, [rbp+57h+var_90]
0x18004bedb  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18004bee0  mov     [rsp+0D0h+var_B0], 0
0x18004bee5  lea     r9, [rbp+57h+var_70]
0x18004bee9  mov     rdx, rax
0x18004beec  lea     rcx, [rbp+57h+pExceptionObject]
0x18004bef0  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18004bef5  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18004befc  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18004bf00  call    _CxxThrowException_0
0x18004bf06  call    ?FindOption@ShaderManager@Engine@Spectre@@QEBA?AW4ShaderOption@23@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Spectre::Engine::ShaderManager::FindOption(std::string const &)
0x18004bf0b  mov     ebx, eax
0x18004bf0d  cmp     eax, 0FFFFFFFFh
0x18004bf10  jnz     short loc_18004BF50
0x18004bf12  movsxd  rbx, dword ptr [rdi+820h]
0x18004bf19  cmp     ebx, 40h ; '@'
0x18004bf1c  jge     short loc_18004BF71
0x18004bf1e  lea     eax, [rbx+1]
0x18004bf21  mov     [rdi+820h], eax
0x18004bf27  lea     rcx, [rdi+10h]
0x18004bf2b  mov     r8, rsi
0x18004bf2e  lea     rdx, [rbp+57h+var_A0]
0x18004bf32  call    ??$_Try_emplace@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$$V@?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ShaderOption@Engine@Spectre@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ShaderOption@Engine@Spectre@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ShaderOption@Engine@Spectre@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string,Spectre::Engine::ShaderOption>::_Try_emplace<std::string const &,>(std::string const &)
0x18004bf37  mov     rcx, [rax]
0x18004bf3a  mov     [rcx+40h], ebx
0x18004bf3d  lea     rcx, [rbx+1]
0x18004bf41  shl     rcx, 5
0x18004bf45  add     rcx, rdi
0x18004bf48  mov     rdx, rsi
0x18004bf4b  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@AEBV01@@Z; std::string::operator=(std::string const &)
0x18004bf50  mov     eax, ebx
0x18004bf52  mov     rcx, [rbp+57h+var_18]
0x18004bf56  xor     rcx, rsp; StackCookie
0x18004bf59  call    __security_check_cookie
0x18004bf5e  mov     rbx, [rsp+0D0h+arg_10]
0x18004bf66  add     rsp, 0C0h
0x18004bf6d  pop     rdi
0x18004bf6e  pop     rsi
0x18004bf6f  pop     rbp
0x18004bf70  retn
0x18004bf71  lea     rdx, aShadermanagerA_5; "ShaderManager::AddOption() -- option co"...
0x18004bf78  lea     rcx, [rbp+57h+var_90]
0x18004bf7c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18004bf81  nop
0x18004bf82  lea     rdx, aOnecoreuapWind_15; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18004bf89  lea     rcx, [rbp+57h+var_70]
0x18004bf8d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18004bf92  mov     [rsp+0D0h+var_B0], 0
0x18004bf97  lea     r9, [rbp+57h+var_90]
0x18004bf9b  mov     rdx, rax
0x18004bf9e  lea     rcx, [rbp+57h+pExceptionObject]
0x18004bfa2  call    ??0EngineInvalidArgException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineInvalidArgException::EngineInvalidArgException(std::string,int,std::string const &,bool)
0x18004bfa7  lea     rdx, _TI5?AUEngineInvalidArgException@Engine@Spectre@@; pThrowInfo
0x18004bfae  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18004bfb2  call    _CxxThrowException_0
```
