# Spectre::Engine::DeviceTexture::SetActiveSize(Spectre::Utils::Math::Vector2)

- ea: `0x180052480`
- end: `0x18005251f`
- name: `?SetActiveSize@DeviceTexture@Engine@Spectre@@QEAAXUVector2@Math@Utils@3@@Z`
- size: `159`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002799c`
- `0x180052528`
- `0x1800bd080`
- `0x1800befe8`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x180011f64`
- `0x180052480`
- `0x1800681a8`

## string_xrefs

- `0x1800524d3`: `Attempted to set an active size with a negative component`
- `0x1800524e5`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\texture.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Spectre::Engine::DeviceTexture::SetActiveSize(__int64 a1, __int64 a2)
{
  int v2; // eax
  int v3; // r8d
  _BYTE v4[32]; // [rsp+38h] [rbp-90h] BYREF
  _BYTE v5[32]; // [rsp+58h] [rbp-70h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+78h] [rbp-50h] BYREF

  if ( *(float *)&a2 < 0.0 || *((float *)&a2 + 1) < 0.0 )
  {
    std::string::string(v5, "Attempted to set an active size with a negative component");
    v2 = std::string::string(
           v4,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\texture.cpp");
    Spectre::Engine::EngineException::EngineException((unsigned int)pExceptionObject, v2, v3, (unsigned int)v5, 0);
    throw (Spectre::Engine::EngineException *)pExceptionObject;
  }
  *(_QWORD *)(a1 + 152) = a2;
}

```

## disassembly

```asm
0x180052480  sub     rsp, 0C8h
0x180052487  mov     rax, cs:__security_cookie
0x18005248e  xor     rax, rsp
0x180052491  mov     [rsp+0C8h+var_18], rax
0x180052499  movq    xmm0, rdx
0x18005249e  movsd   [rsp+0C8h+var_98], xmm0
0x1800524a4  xorps   xmm1, xmm1
0x1800524a7  comiss  xmm1, xmm0
0x1800524aa  ja      short loc_1800524D3
0x1800524ac  comiss  xmm1, dword ptr [rsp+0C8h+var_98+4]
0x1800524b1  ja      short loc_1800524D3
0x1800524b3  movsd   qword ptr [rcx+98h], xmm0
0x1800524bb  mov     rcx, [rsp+0C8h+var_18]
0x1800524c3  xor     rcx, rsp; StackCookie
0x1800524c6  call    __security_check_cookie
0x1800524cb  add     rsp, 0C8h
0x1800524d2  retn
0x1800524d3  lea     rdx, aAttemptedToSet; "Attempted to set an active size with a "...
0x1800524da  lea     rcx, [rsp+0C8h+var_70]
0x1800524df  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800524e4  nop
0x1800524e5  lea     rdx, aOnecoreuapWind; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x1800524ec  lea     rcx, [rsp+0C8h+var_90]
0x1800524f1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800524f6  mov     [rsp+0C8h+var_A8], 0
0x1800524fb  lea     r9, [rsp+0C8h+var_70]
0x180052500  mov     rdx, rax
0x180052503  lea     rcx, [rsp+0C8h+pExceptionObject]
0x180052508  call    ??0EngineException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineException::EngineException(std::string,int,std::string const &,bool)
0x18005250d  lea     rdx, _TI4?AUEngineException@Engine@Spectre@@; pThrowInfo
0x180052514  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x180052519  call    _CxxThrowException_0
```
