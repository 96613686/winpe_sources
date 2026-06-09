# Spectre::Engine::ColorTransform::AttachDevice(std::shared_ptr<Spectre::Engine::RenderDevice>)

- ea: `0x180085110`
- end: `0x1800851e3`
- name: `?AttachDevice@ColorTransform@Engine@Spectre@@UEAAXV?$shared_ptr@VRenderDevice@Engine@Spectre@@@std@@@Z`
- size: `211`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x18001128c`
- `0x180011f64`
- `0x180047a48`
- `0x180085110`
- `0x1800e7010`

## string_xrefs

- `0x180085167`: `ColorTransform::CreateResources() -- volume texture must be power of two below feature level 10.0`
- `0x180085179`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\colortransform.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Spectre::Engine::ColorTransform::AttachDevice(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rcx
  __int64 v5; // rax
  __int64 v6; // r8
  std::_Ref_count_base *v7; // rcx
  _BYTE v8[32]; // [rsp+40h] [rbp-88h] BYREF
  _BYTE v9[32]; // [rsp+60h] [rbp-68h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+80h] [rbp-48h] BYREF

  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a2 + 96LL))(*a2, 1) )
  {
    v4 = *(_QWORD *)(a1 + 144);
    if ( !v4 || ((v4 - 1) & v4) != 0 )
    {
      std::string::string(
        v9,
        "ColorTransform::CreateResources() -- volume texture must be power of two below feature level 10.0");
      v5 = std::string::string(
             v8,
             "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\colortransform.cpp");
      Spectre::Engine::EngineNotImplException::EngineNotImplException(pExceptionObject, v5, v6, v9);
      throw (Spectre::Engine::EngineNotImplException *)pExceptionObject;
    }
  }
  v7 = (std::_Ref_count_base *)a2[1];
  if ( v7 )
    std::_Ref_count_base::_Decref(v7);
}

```

## disassembly

```asm
0x180085110  mov     [rsp+arg_0], rbx
0x180085115  push    rdi
0x180085116  sub     rsp, 0C0h
0x18008511d  mov     rax, cs:__security_cookie
0x180085124  xor     rax, rsp
0x180085127  mov     [rsp+0C8h+var_10], rax
0x18008512f  mov     rbx, rdx
0x180085132  mov     rdi, rcx
0x180085135  mov     [rsp+0C8h+var_98], rdx
0x18008513a  mov     rcx, [rdx]
0x18008513d  mov     rax, [rcx]
0x180085140  mov     edx, 1
0x180085145  mov     rax, [rax+60h]
0x180085149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008514e  test    al, al
0x180085150  jnz     short loc_1800851B4
0x180085152  mov     rcx, [rdi+90h]
0x180085159  test    rcx, rcx
0x18008515c  jz      short loc_180085167
0x18008515e  lea     rax, [rcx-1]
0x180085162  test    rcx, rax
0x180085165  jz      short loc_1800851B4
0x180085167  lea     rdx, aColortransform_2; "ColorTransform::CreateResources() -- vo"...
0x18008516e  lea     rcx, [rsp+0C8h+var_68]
0x180085173  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180085178  nop
0x180085179  lea     rdx, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180085180  lea     rcx, [rsp+0C8h+var_88]
0x180085185  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18008518a  lea     r9, [rsp+0C8h+var_68]
0x18008518f  mov     rdx, rax
0x180085192  lea     rcx, [rsp+0C8h+pExceptionObject]
0x18008519a  call    ??0EngineNotImplException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineNotImplException::EngineNotImplException(std::string,int,std::string const &,bool)
0x18008519f  lea     rdx, _TI5?AUEngineNotImplException@Engine@Spectre@@; pThrowInfo
0x1800851a6  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x1800851ae  call    _CxxThrowException_0
0x1800851b4  mov     rcx, [rbx+8]; this
0x1800851b8  test    rcx, rcx
0x1800851bb  jz      short loc_1800851C2
0x1800851bd  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800851c2  mov     rcx, [rsp+0C8h+var_10]
0x1800851ca  xor     rcx, rsp; StackCookie
0x1800851cd  call    __security_check_cookie
0x1800851d2  mov     rbx, [rsp+0C8h+arg_0]
0x1800851da  add     rsp, 0C0h
0x1800851e1  pop     rdi
0x1800851e2  retn
```
