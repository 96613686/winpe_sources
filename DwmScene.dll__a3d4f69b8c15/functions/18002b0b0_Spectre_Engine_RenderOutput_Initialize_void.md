# Spectre::Engine::RenderOutput::Initialize(void)

- ea: `0x18002b0b0`
- end: `0x18002b190`
- name: `?Initialize@RenderOutput@Engine@Spectre@@UEAAXXZ`
- size: `224`
- prototype: `void __fastcall(Spectre::Engine::RenderOutput *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x18001128c`
- `0x1800112c4`
- `0x180011f64`
- `0x180012c58`
- `0x18002b0b0`
- `0x1800681a8`
- `0x18006b588`
- `0x1800e7010`

## string_xrefs

- `0x18002b13e`: `RenderDevice was removed`
- `0x18002b150`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\renderoutput.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Spectre::Engine::RenderOutput::Initialize(Spectre::Engine::ImageProcessingManager **this)
{
  __int64 v2; // rax
  int v3; // eax
  int v4; // r8d
  _BYTE v5[8]; // [rsp+30h] [rbp-A8h] BYREF
  std::_Ref_count_base *v6; // [rsp+38h] [rbp-A0h]
  struct Spectre::Engine::RenderDevice *v7; // [rsp+40h] [rbp-98h] BYREF
  std::_Ref_count_base *v8; // [rsp+48h] [rbp-90h]
  _BYTE v9[32]; // [rsp+50h] [rbp-88h] BYREF
  _BYTE v10[32]; // [rsp+70h] [rbp-68h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+90h] [rbp-48h] BYREF

  v2 = (*((__int64 (__fastcall **)(Spectre::Engine::ImageProcessingManager **, _BYTE *))*this + 47))(this, v5);
  std::weak_ptr<Spectre::Engine::RenderDevice>::lock(v2, &v7);
  if ( v6 )
    std::_Ref_count_base::_Decwref(v6);
  if ( !v7 )
  {
    std::string::string(v10, "RenderDevice was removed");
    v3 = std::string::string(
           v9,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\renderoutput.cpp");
    Spectre::Engine::EngineException::EngineException((unsigned int)pExceptionObject, v3, v4, (unsigned int)v10, 0);
    throw (Spectre::Engine::EngineException *)pExceptionObject;
  }
  Spectre::Engine::ImageProcessingManager::Create(this[26], v7);
  if ( v8 )
    std::_Ref_count_base::_Decref(v8);
}

```

## disassembly

```asm
0x18002b0b0  push    rbx
0x18002b0b2  sub     rsp, 0D0h
0x18002b0b9  mov     rax, cs:__security_cookie
0x18002b0c0  xor     rax, rsp
0x18002b0c3  mov     [rsp+0D8h+var_10], rax
0x18002b0cb  mov     rbx, rcx
0x18002b0ce  mov     rax, [rcx]
0x18002b0d1  lea     rdx, [rsp+0D8h+var_A8]
0x18002b0d6  mov     rax, [rax+178h]
0x18002b0dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b0e2  lea     rdx, [rsp+0D8h+var_98]
0x18002b0e7  mov     rcx, rax
0x18002b0ea  call    ?lock@?$weak_ptr@VRenderDevice@Engine@Spectre@@@std@@QEBA?AV?$shared_ptr@VRenderDevice@Engine@Spectre@@@2@XZ; std::weak_ptr<Spectre::Engine::RenderDevice>::lock(void)
0x18002b0ef  nop
0x18002b0f0  mov     rcx, [rsp+0D8h+var_A0]; this
0x18002b0f5  test    rcx, rcx
0x18002b0f8  jz      short loc_18002B0FF
0x18002b0fa  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18002b0ff  mov     rdx, [rsp+0D8h+var_98]; struct Spectre::Engine::RenderDevice *
0x18002b104  test    rdx, rdx
0x18002b107  jz      short loc_18002B13E
0x18002b109  mov     rcx, [rbx+0D0h]; this
0x18002b110  call    ?Create@ImageProcessingManager@Engine@Spectre@@QEAAXPEAVRenderDevice@23@@Z; Spectre::Engine::ImageProcessingManager::Create(Spectre::Engine::RenderDevice *)
0x18002b115  nop
0x18002b116  mov     rcx, [rsp+0D8h+var_90]; this
0x18002b11b  test    rcx, rcx
0x18002b11e  jz      short loc_18002B125
0x18002b120  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002b125  mov     rcx, [rsp+0D8h+var_10]
0x18002b12d  xor     rcx, rsp; StackCookie
0x18002b130  call    __security_check_cookie
0x18002b135  add     rsp, 0D0h
0x18002b13c  pop     rbx
0x18002b13d  retn
0x18002b13e  lea     rdx, aRenderdeviceWa; "RenderDevice was removed"
0x18002b145  lea     rcx, [rsp+0D8h+var_68]
0x18002b14a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002b14f  nop
0x18002b150  lea     rdx, aOnecoreuapWind_12; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18002b157  lea     rcx, [rsp+0D8h+var_88]
0x18002b15c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002b161  mov     [rsp+0D8h+var_B8], 0
0x18002b166  lea     r9, [rsp+0D8h+var_68]
0x18002b16b  mov     rdx, rax
0x18002b16e  lea     rcx, [rsp+0D8h+pExceptionObject]
0x18002b176  call    ??0EngineException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineException::EngineException(std::string,int,std::string const &,bool)
0x18002b17b  lea     rdx, _TI4?AUEngineException@Engine@Spectre@@; pThrowInfo
0x18002b182  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x18002b18a  call    _CxxThrowException_0
```
