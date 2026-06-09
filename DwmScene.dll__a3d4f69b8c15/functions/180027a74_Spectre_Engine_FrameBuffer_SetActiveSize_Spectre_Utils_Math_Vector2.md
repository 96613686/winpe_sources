# Spectre::Engine::FrameBuffer::SetActiveSize(Spectre::Utils::Math::Vector2)

- ea: `0x180027a74`
- end: `0x180027b21`
- name: `?SetActiveSize@FrameBuffer@Engine@Spectre@@QEAAXUVector2@Math@Utils@3@@Z`
- size: `173`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180027280`
- `0x18002bb54`
- `0x1800b7a40`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x180011f64`
- `0x180027a74`
- `0x180052528`
- `0x1800681a8`

## string_xrefs

- `0x180027ad5`: `Attempted to set an active size with a negative component`
- `0x180027ae7`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\rendertarget.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Spectre::Engine::FrameBuffer::SetActiveSize(__int64 a1, __int64 a2)
{
  __int64 v2; // rcx
  int v3; // eax
  int v4; // r8d
  _BYTE v5[32]; // [rsp+38h] [rbp-90h] BYREF
  _BYTE v6[32]; // [rsp+58h] [rbp-70h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+78h] [rbp-50h] BYREF

  if ( *(float *)&a2 < 0.0 || *((float *)&a2 + 1) < 0.0 )
  {
    std::string::string(v6, "Attempted to set an active size with a negative component");
    v3 = std::string::string(
           v5,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\rendertarget.cpp");
    Spectre::Engine::EngineException::EngineException((unsigned int)pExceptionObject, v3, v4, (unsigned int)v6, 0);
    throw (Spectre::Engine::EngineException *)pExceptionObject;
  }
  v2 = *(_QWORD *)(a1 + 136);
  if ( v2 )
    Spectre::Engine::Texture::SetActiveSize(v2, a2);
}

```

## disassembly

```asm
0x180027a74  sub     rsp, 0C8h
0x180027a7b  mov     rax, cs:__security_cookie
0x180027a82  xor     rax, rsp
0x180027a85  mov     [rsp+0C8h+var_18], rax
0x180027a8d  movq    xmm0, rdx
0x180027a92  movsd   [rsp+0C8h+var_98], xmm0
0x180027a98  xorps   xmm1, xmm1
0x180027a9b  comiss  xmm1, xmm0
0x180027a9e  ja      short loc_180027AD5
0x180027aa0  comiss  xmm1, dword ptr [rsp+0C8h+var_98+4]
0x180027aa5  ja      short loc_180027AD5
0x180027aa7  mov     rcx, [rcx+88h]
0x180027aae  test    rcx, rcx
0x180027ab1  jz      short loc_180027ABD
0x180027ab3  movq    rdx, xmm0
0x180027ab8  call    ?SetActiveSize@Texture@Engine@Spectre@@QEAAXUVector2@Math@Utils@3@@Z; Spectre::Engine::Texture::SetActiveSize(Spectre::Utils::Math::Vector2)
0x180027abd  mov     rcx, [rsp+0C8h+var_18]
0x180027ac5  xor     rcx, rsp; StackCookie
0x180027ac8  call    __security_check_cookie
0x180027acd  add     rsp, 0C8h
0x180027ad4  retn
0x180027ad5  lea     rdx, aAttemptedToSet; "Attempted to set an active size with a "...
0x180027adc  lea     rcx, [rsp+0C8h+var_70]
0x180027ae1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180027ae6  nop
0x180027ae7  lea     rdx, aOnecoreuapWind_57; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180027aee  lea     rcx, [rsp+0C8h+var_90]
0x180027af3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180027af8  mov     [rsp+0C8h+var_A8], 0
0x180027afd  lea     r9, [rsp+0C8h+var_70]
0x180027b02  mov     rdx, rax
0x180027b05  lea     rcx, [rsp+0C8h+pExceptionObject]
0x180027b0a  call    ??0EngineException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineException::EngineException(std::string,int,std::string const &,bool)
0x180027b0f  lea     rdx, _TI4?AUEngineException@Engine@Spectre@@; pThrowInfo
0x180027b16  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x180027b1b  call    _CxxThrowException_0
```
