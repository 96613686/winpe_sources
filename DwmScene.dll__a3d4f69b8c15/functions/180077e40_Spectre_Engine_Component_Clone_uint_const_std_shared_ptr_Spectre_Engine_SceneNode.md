# Spectre::Engine::Component::Clone(uint const &,std::shared_ptr<Spectre::Engine::SceneNode>)

- ea: `0x180077e40`
- end: `0x180077f5f`
- name: `?Clone@Component@Engine@Spectre@@UEBA?AV?$shared_ptr@VComponent@Engine@Spectre@@@std@@AEBIV?$shared_ptr@VSceneNode@Engine@Spectre@@@5@@Z`
- size: `287`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x18000ca90`
- `0x18000d4ae`
- `0x18000dfa2`
- `0x18001128c`
- `0x180011f64`
- `0x18001c630`
- `0x18001c720`
- `0x180047a48`
- `0x180077e40`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x180077eb3`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x180077eb3`

## string_xrefs

- `0x180077ed1`: `Component::Clone() -- component '`
- `0x180077f2c`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\component.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall Spectre::Engine::Component::Clone(__int64 a1, _QWORD *a2, _DWORD *a3, __int64 a4)
{
  std::_Ref_count_base *v6; // rcx
  __int64 v8; // rax
  __int64 v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rbx
  __int64 v14; // rax
  __int64 v15; // r8
  _BYTE v16[32]; // [rsp+48h] [rbp-F0h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+68h] [rbp-D0h] BYREF
  _BYTE v18[32]; // [rsp+A0h] [rbp-98h] BYREF
  _BYTE v19[32]; // [rsp+C0h] [rbp-78h] BYREF
  _BYTE v20[32]; // [rsp+E0h] [rbp-58h] BYREF
  _BYTE v21[32]; // [rsp+100h] [rbp-38h] BYREF

  if ( (*a3 & 0x10000) == 0 )
  {
    v8 = __RTtypeid(a1);
    v9 = _std_type_info_name(v8 + 8, &__type_info_root_node);
    v10 = std::operator+<char>(v18, "Component::Clone() -- component '", a1 + 24);
    v11 = std::operator+<char>(v19, v10, "' of type ");
    v12 = std::operator+<char>(v20, v11, v9);
    v13 = std::operator+<char>(v21, v12, " does not support cloning.");
    v14 = std::string::string(
            v16,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\component.cpp");
    Spectre::Engine::EngineNotImplException::EngineNotImplException(pExceptionObject, v14, v15, v13);
    throw (Spectre::Engine::EngineNotImplException *)pExceptionObject;
  }
  *a2 = 0;
  a2[1] = 0;
  v6 = *(std::_Ref_count_base **)(a4 + 8);
  if ( v6 )
    std::_Ref_count_base::_Decref(v6);
  return a2;
}

```

## disassembly

```asm
0x180077e40  mov     [rsp+arg_10], rbx
0x180077e45  push    rdi
0x180077e46  sub     rsp, 130h
0x180077e4d  mov     rax, cs:__security_cookie
0x180077e54  xor     rax, rsp
0x180077e57  mov     [rsp+138h+var_18], rax
0x180077e5f  mov     rbx, rdx
0x180077e62  mov     rdi, rcx
0x180077e65  mov     [rsp+138h+var_100], rdx
0x180077e6a  mov     [rsp+138h+var_100], r9
0x180077e6f  xor     eax, eax
0x180077e71  test    dword ptr [r8], 10000h
0x180077e78  jz      short loc_180077EB3
0x180077e7a  mov     [rdx], rax
0x180077e7d  mov     [rdx+8], rax
0x180077e81  mov     rcx, [r9+8]; this
0x180077e85  test    rcx, rcx
0x180077e88  jz      short loc_180077E8F
0x180077e8a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180077e8f  mov     rax, rbx
0x180077e92  mov     rcx, [rsp+138h+var_18]
0x180077e9a  xor     rcx, rsp; StackCookie
0x180077e9d  call    __security_check_cookie
0x180077ea2  mov     rbx, [rsp+138h+arg_10]
0x180077eaa  add     rsp, 130h
0x180077eb1  pop     rdi
0x180077eb2  retn
0x180077eb3  call    cs:__imp___RTtypeid
0x180077eb9  nop
0x180077eba  lea     rcx, [rax+8]
0x180077ebe  lea     rdx, ?__type_info_root_node@@3U__type_info_node@@A; __type_info_node __type_info_root_node
0x180077ec5  call    __std_type_info_name
0x180077eca  mov     rbx, rax
0x180077ecd  lea     r8, [rdi+18h]
0x180077ed1  lea     rdx, aComponentClone; "Component::Clone() -- component '"
0x180077ed8  lea     rcx, [rsp+138h+var_98]
0x180077ee0  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBDAEBV10@@Z; std::operator+<char>(char const * const,std::string const &)
0x180077ee5  nop
0x180077ee6  lea     r8, aOfType; "' of type "
0x180077eed  mov     rdx, rax
0x180077ef0  lea     rcx, [rsp+138h+var_78]
0x180077ef8  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x180077efd  nop
0x180077efe  mov     r8, rbx
0x180077f01  mov     rdx, rax
0x180077f04  lea     rcx, [rsp+138h+var_58]
0x180077f0c  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x180077f11  nop
0x180077f12  lea     r8, aDoesNotSupport; " does not support cloning."
0x180077f19  mov     rdx, rax
0x180077f1c  lea     rcx, [rsp+138h+var_38]
0x180077f24  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x180077f29  mov     rbx, rax
0x180077f2c  lea     rdx, aOnecoreuapWind_14; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180077f33  lea     rcx, [rsp+138h+var_F0]
0x180077f38  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180077f3d  mov     r9, rbx
0x180077f40  mov     rdx, rax
0x180077f43  lea     rcx, [rsp+138h+pExceptionObject]
0x180077f48  call    ??0EngineNotImplException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineNotImplException::EngineNotImplException(std::string,int,std::string const &,bool)
0x180077f4d  lea     rdx, _TI5?AUEngineNotImplException@Engine@Spectre@@; pThrowInfo
0x180077f54  lea     rcx, [rsp+138h+pExceptionObject]; pExceptionObject
0x180077f59  call    _CxxThrowException_0
```
