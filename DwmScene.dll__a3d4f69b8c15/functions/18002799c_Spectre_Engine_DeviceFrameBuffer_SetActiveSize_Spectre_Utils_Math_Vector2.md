# Spectre::Engine::DeviceFrameBuffer::SetActiveSize(Spectre::Utils::Math::Vector2)

- ea: `0x18002799c`
- end: `0x180027a6d`
- name: `?SetActiveSize@DeviceFrameBuffer@Engine@Spectre@@QEAAXUVector2@Math@Utils@3@@Z`
- size: `209`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800bbb2c`
- `0x1800bbd50`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x180011f64`
- `0x18002799c`
- `0x180052480`
- `0x1800681a8`

## string_xrefs

- `0x180027a21`: `Attempted to set an active size with a negative component`
- `0x180027a33`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\rendertarget.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Spectre::Engine::DeviceFrameBuffer::SetActiveSize(__int64 a1, __int64 a2)
{
  __int64 v4; // rcx
  __int64 v5; // rcx
  int v6; // eax
  int v7; // r8d
  _BYTE v8[32]; // [rsp+38h] [rbp-A0h] BYREF
  _BYTE v9[32]; // [rsp+58h] [rbp-80h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+78h] [rbp-60h] BYREF

  if ( *(float *)&a2 < 0.0 || *((float *)&a2 + 1) < 0.0 )
  {
    std::string::string(v9, "Attempted to set an active size with a negative component");
    v6 = std::string::string(
           v8,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\rendertarget.cpp");
    Spectre::Engine::EngineException::EngineException((unsigned int)pExceptionObject, v6, v7, (unsigned int)v9, 0);
    throw (Spectre::Engine::EngineException *)pExceptionObject;
  }
  v4 = *(_QWORD *)(a1 + 96);
  if ( v4 )
    Spectre::Engine::DeviceTexture::SetActiveSize(v4, a2);
  v5 = *(_QWORD *)(a1 + 112);
  if ( v5 )
    Spectre::Engine::DeviceTexture::SetActiveSize(v5, a2);
}

```

## disassembly

```asm
0x18002799c  mov     rax, rsp
0x18002799f  push    rbx
0x1800279a0  sub     rsp, 0D0h
0x1800279a7  movaps  xmmword ptr [rax-18h], xmm6
0x1800279ab  mov     rax, cs:__security_cookie
0x1800279b2  xor     rax, rsp
0x1800279b5  mov     [rsp+0D8h+var_28], rax
0x1800279bd  mov     rbx, rcx
0x1800279c0  movq    xmm6, rdx
0x1800279c5  movsd   [rsp+0D8h+var_A8], xmm6
0x1800279cb  xorps   xmm0, xmm0
0x1800279ce  comiss  xmm0, xmm6
0x1800279d1  ja      short loc_180027A21
0x1800279d3  comiss  xmm0, dword ptr [rsp+0D8h+var_A8+4]
0x1800279d8  ja      short loc_180027A21
0x1800279da  mov     rcx, [rcx+60h]
0x1800279de  test    rcx, rcx
0x1800279e1  jz      short loc_1800279ED
0x1800279e3  movq    rdx, xmm6
0x1800279e8  call    ?SetActiveSize@DeviceTexture@Engine@Spectre@@QEAAXUVector2@Math@Utils@3@@Z; Spectre::Engine::DeviceTexture::SetActiveSize(Spectre::Utils::Math::Vector2)
0x1800279ed  mov     rcx, [rbx+70h]
0x1800279f1  test    rcx, rcx
0x1800279f4  jz      short loc_180027A00
0x1800279f6  movq    rdx, xmm6
0x1800279fb  call    ?SetActiveSize@DeviceTexture@Engine@Spectre@@QEAAXUVector2@Math@Utils@3@@Z; Spectre::Engine::DeviceTexture::SetActiveSize(Spectre::Utils::Math::Vector2)
0x180027a00  mov     rcx, [rsp+0D8h+var_28]
0x180027a08  xor     rcx, rsp; StackCookie
0x180027a0b  call    __security_check_cookie
0x180027a10  movaps  xmm6, [rsp+0D8h+var_18]
0x180027a18  add     rsp, 0D0h
0x180027a1f  pop     rbx
0x180027a20  retn
0x180027a21  lea     rdx, aAttemptedToSet; "Attempted to set an active size with a "...
0x180027a28  lea     rcx, [rsp+0D8h+var_80]
0x180027a2d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180027a32  nop
0x180027a33  lea     rdx, aOnecoreuapWind_57; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180027a3a  lea     rcx, [rsp+0D8h+var_A0]
0x180027a3f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180027a44  mov     [rsp+0D8h+var_B8], 0
0x180027a49  lea     r9, [rsp+0D8h+var_80]
0x180027a4e  mov     rdx, rax
0x180027a51  lea     rcx, [rsp+0D8h+pExceptionObject]
0x180027a56  call    ??0EngineException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineException::EngineException(std::string,int,std::string const &,bool)
0x180027a5b  lea     rdx, _TI4?AUEngineException@Engine@Spectre@@; pThrowInfo
0x180027a62  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x180027a67  call    _CxxThrowException_0
```
