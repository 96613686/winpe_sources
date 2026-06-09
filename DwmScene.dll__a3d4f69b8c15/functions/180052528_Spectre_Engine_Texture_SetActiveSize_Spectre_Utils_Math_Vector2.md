# Spectre::Engine::Texture::SetActiveSize(Spectre::Utils::Math::Vector2)

- ea: `0x180052528`
- end: `0x180052608`
- name: `?SetActiveSize@Texture@Engine@Spectre@@QEAAXUVector2@Math@Utils@3@@Z`
- size: `224`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180027a74`
- `0x180051990`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x180011f64`
- `0x18001d578`
- `0x180052480`
- `0x180052528`
- `0x1800681a8`

## string_xrefs

- `0x18005259b`: `Attempted to set an active size with a negative component`
- `0x1800525ad`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\texture.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_UNKNOWN **__fastcall Spectre::Engine::Texture::SetActiveSize(__int64 a1, __int64 a2)
{
  _UNKNOWN **result; // rax
  __int64 *v4; // rbx
  __int64 *v5; // rcx
  int v6; // eax
  int v7; // r8d
  __int64 v8; // [rsp+30h] [rbp-A8h] BYREF
  char v9[32]; // [rsp+38h] [rbp-A0h] BYREF
  _BYTE v10[32]; // [rsp+58h] [rbp-80h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+78h] [rbp-60h] BYREF
  _UNKNOWN *retaddr; // [rsp+D8h] [rbp+0h] BYREF

  result = &retaddr;
  v8 = a2;
  if ( *(float *)&a2 < 0.0 || *((float *)&v8 + 1) < 0.0 )
  {
    std::string::string(v10, "Attempted to set an active size with a negative component");
    v6 = std::string::string(
           v9,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\texture.cpp");
    Spectre::Engine::EngineException::EngineException((unsigned int)pExceptionObject, v6, v7, (unsigned int)v10, 0);
    throw (Spectre::Engine::EngineException *)pExceptionObject;
  }
  *(_QWORD *)(a1 + 144) = a2;
  v4 = *(__int64 **)(a1 + 112);
  v5 = (__int64 *)*v4;
  v8 = *v4;
  while ( v5 != v4 )
  {
    Spectre::Engine::DeviceTexture::SetActiveSize(v5[5], a2);
    result = (_UNKNOWN **)std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<enum Spectre::Engine::RenderDeviceID const,std::shared_ptr<Spectre::Engine::DeviceConstantBuffer>>>>,std::_Iterator_base0>::operator++(&v8);
    v5 = (__int64 *)v8;
  }
  return result;
}

```

## disassembly

```asm
0x180052528  mov     rax, rsp
0x18005252b  push    rbx
0x18005252c  sub     rsp, 0D0h
0x180052533  movaps  xmmword ptr [rax-18h], xmm6
0x180052537  mov     rax, cs:__security_cookie
0x18005253e  xor     rax, rsp
0x180052541  mov     [rsp+0D8h+var_28], rax
0x180052549  movq    xmm6, rdx
0x18005254e  movsd   [rsp+0D8h+var_A8], xmm6
0x180052554  xorps   xmm0, xmm0
0x180052557  comiss  xmm0, xmm6
0x18005255a  ja      short loc_18005259B
0x18005255c  comiss  xmm0, dword ptr [rsp+0D8h+var_A8+4]
0x180052561  ja      short loc_18005259B
0x180052563  movsd   qword ptr [rcx+90h], xmm6
0x18005256b  mov     rbx, [rcx+70h]
0x18005256f  mov     rcx, [rbx]
0x180052572  mov     [rsp+0D8h+var_A8], rcx
0x180052577  cmp     rcx, rbx
0x18005257a  jz      short loc_1800525E7
0x18005257c  movq    rdx, xmm6
0x180052581  mov     rcx, [rcx+28h]
0x180052585  call    ?SetActiveSize@DeviceTexture@Engine@Spectre@@QEAAXUVector2@Math@Utils@3@@Z; Spectre::Engine::DeviceTexture::SetActiveSize(Spectre::Utils::Math::Vector2)
0x18005258a  lea     rcx, [rsp+0D8h+var_A8]
0x18005258f  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4RenderDeviceID@Engine@Spectre@@V?$shared_ptr@VDeviceConstantBuffer@Engine@Spectre@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<Spectre::Engine::RenderDeviceID const,std::shared_ptr<Spectre::Engine::DeviceConstantBuffer>>>>,std::_Iterator_base0>::operator++(void)
0x180052594  mov     rcx, [rsp+0D8h+var_A8]
0x180052599  jmp     short loc_180052577
0x18005259b  lea     rdx, aAttemptedToSet; "Attempted to set an active size with a "...
0x1800525a2  lea     rcx, [rsp+0D8h+var_80]
0x1800525a7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800525ac  nop
0x1800525ad  lea     rdx, aOnecoreuapWind; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x1800525b4  lea     rcx, [rsp+0D8h+var_A0]
0x1800525b9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800525be  mov     [rsp+0D8h+var_B8], 0
0x1800525c3  lea     r9, [rsp+0D8h+var_80]
0x1800525c8  mov     rdx, rax
0x1800525cb  lea     rcx, [rsp+0D8h+pExceptionObject]
0x1800525d0  call    ??0EngineException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineException::EngineException(std::string,int,std::string const &,bool)
0x1800525d5  lea     rdx, _TI4?AUEngineException@Engine@Spectre@@; pThrowInfo
0x1800525dc  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x1800525e1  call    _CxxThrowException_0
0x1800525e7  mov     rcx, [rsp+0D8h+var_28]
0x1800525ef  xor     rcx, rsp; StackCookie
0x1800525f2  call    __security_check_cookie
0x1800525f7  movaps  xmm6, [rsp+0D8h+var_18]
0x1800525ff  add     rsp, 0D0h
0x180052606  pop     rbx
0x180052607  retn
```
