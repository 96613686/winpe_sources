# Spectre::Engine::Mesh::ComputeRequiredData(uint)

- ea: `0x18004521c`
- end: `0x180045361`
- name: `?ComputeRequiredData@Mesh@Engine@Spectre@@QEAAXI@Z`
- size: `325`
- prototype: `void __fastcall(Spectre::Engine::Mesh *__hidden this, unsigned int)`
- caller_count: `5`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014af0`
- `0x1800752a0`
- `0x180082ab4`
- `0x180082d3c`
- `0x18008fa30`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x180011f64`
- `0x18001daf4`
- `0x1800286b4`
- `0x180044e64`
- `0x180045024`
- `0x18004521c`
- `0x180045368`
- `0x1800681a8`

## string_xrefs

- `0x180045261`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\mesh.cpp`
- `0x18004524f`: `Mesh::ComputeRequiredData() -- Modification of a mesh that while it is mapped is not supported.`
- `0x1800452f6`: `Attempting to compute tangents for mesh without UV coordinates. Tangents will not be calculated.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Spectre::Engine::Mesh::ComputeRequiredData(Spectre::Engine::Mesh *this, __int64 a2, __int64 a3)
{
  int v4; // eax
  int v5; // r8d
  struct Spectre::Engine::Engine *v6; // rdx
  _QWORD *v7; // rcx
  char v8; // r8
  unsigned int v9; // r9d
  char v10; // di
  char v11; // si
  bool v12; // cl
  _BYTE v13[32]; // [rsp+38h] [rbp-90h] BYREF
  _BYTE v14[32]; // [rsp+58h] [rbp-70h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+78h] [rbp-50h] BYREF

  if ( *((_BYTE *)this + 310) )
  {
    std::string::string(
      v14,
      "Mesh::ComputeRequiredData() -- Modification of a mesh that while it is mapped is not supported.");
    v4 = std::string::string(
           v13,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\mesh.cpp");
    Spectre::Engine::EngineException::EngineException((unsigned int)pExceptionObject, v4, v5, (unsigned int)v14, 0);
    throw (Spectre::Engine::EngineException *)pExceptionObject;
  }
  LOBYTE(a3) = 1;
  Spectre::Engine::RendererResource::SetOption(this, 4, a3);
  if ( v7[18] )
  {
    v10 = v8 & (v9 >> 2);
    v11 = 0;
    if ( !v7[20] )
      v11 = v8 & v9;
    v12 = (v9 & 2) != 0 && v7[24] == 0;
    if ( v12 && !*((_QWORD *)this + 30) )
    {
      Trace::LevelSettingsWrapper::Output(
        &gTraceLevelsMesh,
        3,
        "Attempting to compute tangents for mesh without UV coordinates. Tangents will not be calculated.");
      v12 = 0;
    }
    if ( v11 )
    {
      if ( v12 )
        Spectre::Engine::Mesh::ComputeNormalsAndTangents(this, v6, v10);
      else
        Spectre::Engine::Mesh::ComputeNormals(this, v6);
    }
    else if ( v12 )
    {
      Spectre::Engine::Mesh::ComputeTangents(this, v6, v10);
    }
  }
}

```

## disassembly

```asm
0x18004521c  mov     [rsp+arg_8], rbx
0x180045221  mov     [rsp+arg_10], rsi
0x180045226  push    rdi
0x180045227  sub     rsp, 0C0h
0x18004522e  mov     rax, cs:__security_cookie
0x180045235  xor     rax, rsp
0x180045238  mov     [rsp+0C8h+var_18], rax
0x180045240  mov     r9d, edx
0x180045243  mov     rbx, rcx
0x180045246  cmp     byte ptr [rcx+136h], 0
0x18004524d  jz      short loc_18004529B
0x18004524f  lea     rdx, aMeshComputereq; "Mesh::ComputeRequiredData() -- Modifica"...
0x180045256  lea     rcx, [rsp+0C8h+var_70]
0x18004525b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180045260  nop
0x180045261  lea     rdx, aOnecoreuapWind_13; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180045268  lea     rcx, [rsp+0C8h+var_90]
0x18004526d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180045272  mov     [rsp+0C8h+var_A8], 0
0x180045277  lea     r9, [rsp+0C8h+var_70]
0x18004527c  mov     rdx, rax
0x18004527f  lea     rcx, [rsp+0C8h+pExceptionObject]
0x180045284  call    ??0EngineException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineException::EngineException(std::string,int,std::string const &,bool)
0x180045289  lea     rdx, _TI4?AUEngineException@Engine@Spectre@@; pThrowInfo
0x180045290  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x180045295  call    _CxxThrowException_0
0x18004529b  mov     r8b, 1
0x18004529e  mov     edx, 4
0x1800452a3  call    ?SetOption@RendererResource@Engine@Spectre@@QEAAXW4EResourceOption@123@_N@Z; Spectre::Engine::RendererResource::SetOption(Spectre::Engine::RendererResource::EResourceOption,bool)
0x1800452a8  cmp     qword ptr [rcx+90h], 0
0x1800452b0  jz      loc_18004533C
0x1800452b6  mov     edi, r9d
0x1800452b9  shr     edi, 2
0x1800452bc  and     dil, r8b
0x1800452bf  mov     eax, r9d
0x1800452c2  and     al, r8b
0x1800452c5  xor     esi, esi
0x1800452c7  movzx   eax, al
0x1800452ca  cmp     [rcx+0A0h], rsi
0x1800452d1  cmovz   esi, eax
0x1800452d4  and     r9b, 2
0x1800452d8  cmp     qword ptr [rcx+0C0h], 0
0x1800452e0  setz    al
0x1800452e3  neg     r9b
0x1800452e6  sbb     cl, cl
0x1800452e8  and     cl, al
0x1800452ea  jz      short loc_180045310
0x1800452ec  cmp     qword ptr [rbx+0F0h], 0
0x1800452f4  jnz     short loc_180045310
0x1800452f6  lea     r8, aAttemptingToCo; "Attempting to compute tangents for mesh"...
0x1800452fd  mov     edx, 3
0x180045302  lea     rcx, ?gTraceLevelsMesh@@3ULevelSettingsWrapper@Trace@@A; Trace::LevelSettingsWrapper gTraceLevelsMesh
0x180045309  call    ?Output@LevelSettingsWrapper@Trace@@QEAAXW4Level@2@PEBDZZ; Trace::LevelSettingsWrapper::Output(Trace::Level,char const *,...)
0x18004530e  xor     cl, cl
0x180045310  test    sil, sil
0x180045313  jz      short loc_18004532D
0x180045315  test    cl, cl
0x180045317  mov     rcx, rbx; this
0x18004531a  jz      short loc_180045326
0x18004531c  mov     r8b, dil; bool
0x18004531f  call    ?ComputeNormalsAndTangents@Mesh@Engine@Spectre@@IEAAXPEAV223@_N@Z; Spectre::Engine::Mesh::ComputeNormalsAndTangents(Spectre::Engine::Engine *,bool)
0x180045324  jmp     short loc_18004533C
0x180045326  call    ?ComputeNormals@Mesh@Engine@Spectre@@IEAAXPEAV223@@Z; Spectre::Engine::Mesh::ComputeNormals(Spectre::Engine::Engine *)
0x18004532b  jmp     short loc_18004533C
0x18004532d  test    cl, cl
0x18004532f  jz      short loc_18004533C
0x180045331  mov     r8b, dil; bool
0x180045334  mov     rcx, rbx; this
0x180045337  call    ?ComputeTangents@Mesh@Engine@Spectre@@IEAAXPEAV223@_N@Z; Spectre::Engine::Mesh::ComputeTangents(Spectre::Engine::Engine *,bool)
0x18004533c  mov     rcx, [rsp+0C8h+var_18]
0x180045344  xor     rcx, rsp; StackCookie
0x180045347  call    __security_check_cookie
0x18004534c  lea     r11, [rsp+0C8h+var_8]
0x180045354  mov     rbx, [r11+18h]
0x180045358  mov     rsi, [r11+20h]
0x18004535c  mov     rsp, r11
0x18004535f  pop     rdi
0x180045360  retn
```
