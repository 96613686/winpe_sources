# Spectre::Engine::Texture::AttachDeviceTexture(std::shared_ptr<Spectre::Engine::DeviceTexture>)

- ea: `0x1800515cc`
- end: `0x1800517e7`
- name: `?AttachDeviceTexture@Texture@Engine@Spectre@@QEAAXV?$shared_ptr@VDeviceTexture@Engine@Spectre@@@std@@@Z`
- size: `539`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180027150`
- `0x180027584`
- `0x1800518e4`
- `0x1800686bc`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x18001128c`
- `0x180011f64`
- `0x180050b54`
- `0x180050ebc`
- `0x180051300`
- `0x1800515cc`
- `0x1800517f0`
- `0x1800681a8`

## string_xrefs

- `0x18005162d`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\texture.cpp`
- `0x180051706`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\texture.cpp`
- `0x1800516f5`: `Attaching a texture buffer to an incompatible texture`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Spectre::Engine::Texture::AttachDeviceTexture(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rdx
  _DWORD **v5; // rbx
  _DWORD *v6; // rbx
  int v7; // eax
  int v8; // r8d
  char v9; // r15
  __int64 v10; // r12
  _DWORD *v11; // rcx
  int v12; // eax
  int v13; // r8d
  __int64 v14; // r13
  __int64 v15; // rax
  int v16; // xmm0_4
  std::_Ref_count_base *v17; // rcx
  __int64 v18; // [rsp+30h] [rbp-69h]
  _QWORD *v19; // [rsp+38h] [rbp-61h] BYREF
  _QWORD v20[4]; // [rsp+40h] [rbp-59h] BYREF
  _BYTE v21[32]; // [rsp+60h] [rbp-39h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+80h] [rbp-19h] BYREF

  v19 = a2;
  v4 = *a2;
  v5 = *(_DWORD ***)(v4 + 112);
  if ( v5 )
    v6 = *v5;
  else
    v6 = 0;
  if ( !v6 )
  {
    std::string::string(v21, "Attaching an uninitialized device texture.");
    v7 = std::string::string(
           v20,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\texture.cpp");
    Spectre::Engine::EngineException::EngineException((unsigned int)pExceptionObject, v7, v8, (unsigned int)v21, 0);
    throw (Spectre::Engine::EngineException *)pExceptionObject;
  }
  v9 = 1;
  if ( !*(_QWORD *)(a1 + 120)
    || *(_DWORD *)(a1 + 120) == 1 && *(_DWORD *)(**(_QWORD **)(a1 + 112) + 32LL) == *(_DWORD *)(v4 + 88) )
  {
    v10 = a1 + 128;
  }
  else
  {
    v10 = a1 + 128;
    v11 = *(_DWORD **)(a1 + 128);
    if ( v11 != v6
      && (*v11 != *v6
       || v11[1] != v6[1]
       || v11[2] != v6[2]
       || v11[3] != v6[3]
       || v11[4] != v6[4]
       || v11[5] != v6[5]
       || v11[6] != v6[6])
      || (_mm_movemask_ps(_mm_cmpeq_ps((__m128)*(unsigned __int64 *)(v4 + 152), (__m128)*(unsigned __int64 *)(a1 + 144)))
        & 3) != 3 )
    {
      std::string::string(v20, "Attaching a texture buffer to an incompatible texture");
      v12 = std::string::string(
              v21,
              "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\texture.cpp");
      Spectre::Engine::EngineException::EngineException((unsigned int)pExceptionObject, v12, v13, (unsigned int)v20, 0);
      throw (Spectre::Engine::EngineException *)pExceptionObject;
    }
    v9 = 0;
  }
  v18 = a1;
  v14 = v4;
  v20[0] = v4;
  v20[1] = a2[1];
  *a2 = 0;
  a2[1] = 0;
  Spectre::Engine::Texture::AttachDeviceTextureInternal(a1, v20);
  if ( v9 )
  {
    v15 = std::make_unique<Spectre::Engine::TextureDesc,Spectre::Engine::TextureDesc const &,0>(&v19, v6);
    std::unique_ptr<Spectre::Engine::TextureDesc>::operator=<std::default_delete<Spectre::Engine::TextureDesc>,0>(
      v10,
      v15);
    std::unique_ptr<Spectre::Engine::TextureDesc>::~unique_ptr<Spectre::Engine::TextureDesc>(&v19);
    v16 = *(_DWORD *)(v14 + 156);
    *(_DWORD *)(v18 + 144) = *(_DWORD *)(v14 + 152);
    *(_DWORD *)(v18 + 148) = v16;
  }
  v17 = (std::_Ref_count_base *)a2[1];
  if ( v17 )
    std::_Ref_count_base::_Decref(v17);
}

```

## disassembly

```asm
0x1800515cc  mov     [rsp-8+arg_10], rbx
0x1800515d1  push    rbp
0x1800515d2  push    rsi
0x1800515d3  push    rdi
0x1800515d4  push    r12
0x1800515d6  push    r13
0x1800515d8  push    r14
0x1800515da  push    r15
0x1800515dc  lea     rbp, [rsp-27h]
0x1800515e1  sub     rsp, 0C0h
0x1800515e8  mov     rax, cs:__security_cookie
0x1800515ef  xor     rax, rsp
0x1800515f2  mov     [rbp+57h+var_38], rax
0x1800515f6  mov     rdi, rdx
0x1800515f9  mov     r8, rcx
0x1800515fc  mov     [rbp+57h+var_B8], rdx
0x180051600  mov     rdx, [rdx]
0x180051603  mov     rbx, [rdx+70h]
0x180051607  xor     r9d, r9d
0x18005160a  test    rbx, rbx
0x18005160d  jz      short loc_180051614
0x18005160f  mov     rbx, [rbx]
0x180051612  jmp     short loc_180051617
0x180051614  mov     rbx, r9
0x180051617  test    rbx, rbx
0x18005161a  jnz     short loc_180051662
0x18005161c  lea     rdx, aAttachingAnUni; "Attaching an uninitialized device textu"...
0x180051623  lea     rcx, [rbp+57h+var_90]
0x180051627  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18005162c  nop
0x18005162d  lea     rdx, aOnecoreuapWind; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180051634  lea     rcx, [rbp+57h+var_B0]
0x180051638  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18005163d  mov     [rsp+0F0h+var_D0], bl
0x180051641  lea     r9, [rbp+57h+var_90]
0x180051645  mov     rdx, rax
0x180051648  lea     rcx, [rbp+57h+pExceptionObject]
0x18005164c  call    ??0EngineException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineException::EngineException(std::string,int,std::string const &,bool)
0x180051651  lea     rdx, _TI4?AUEngineException@Engine@Spectre@@; pThrowInfo
0x180051658  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18005165c  call    _CxxThrowException_0
0x180051662  mov     r15d, 1
0x180051668  cmp     [rcx+78h], r9
0x18005166c  jz      loc_18005173C
0x180051672  cmp     [rcx+78h], r15d
0x180051676  jnz     short loc_18005168B
0x180051678  mov     rax, [rcx+70h]
0x18005167c  mov     rcx, [rax]
0x18005167f  mov     eax, [rdx+58h]
0x180051682  cmp     [rcx+20h], eax
0x180051685  jz      loc_18005173C
0x18005168b  lea     r12, [r8+80h]
0x180051692  mov     rcx, [r12]
0x180051696  cmp     rcx, rbx
0x180051699  jz      short loc_1800516D1
0x18005169b  mov     eax, [rbx]
0x18005169d  cmp     [rcx], eax
0x18005169f  jnz     short loc_1800516F5
0x1800516a1  mov     eax, [rbx+4]
0x1800516a4  cmp     [rcx+4], eax
0x1800516a7  jnz     short loc_1800516F5
0x1800516a9  mov     eax, [rbx+8]
0x1800516ac  cmp     [rcx+8], eax
0x1800516af  jnz     short loc_1800516F5
0x1800516b1  mov     eax, [rbx+0Ch]
0x1800516b4  cmp     [rcx+0Ch], eax
0x1800516b7  jnz     short loc_1800516F5
0x1800516b9  mov     eax, [rbx+10h]
0x1800516bc  cmp     [rcx+10h], eax
0x1800516bf  jnz     short loc_1800516F5
0x1800516c1  mov     eax, [rbx+14h]
0x1800516c4  cmp     [rcx+14h], eax
0x1800516c7  jnz     short loc_1800516F5
0x1800516c9  mov     eax, [rbx+18h]
0x1800516cc  cmp     [rcx+18h], eax
0x1800516cf  jnz     short loc_1800516F5
0x1800516d1  movsd   xmm1, qword ptr [r8+90h]
0x1800516da  movsd   xmm0, qword ptr [rdx+98h]
0x1800516e2  cmpeqps xmm0, xmm1
0x1800516e6  movmskps eax, xmm0
0x1800516e9  and     eax, 3
0x1800516ec  cmp     al, 3
0x1800516ee  jnz     short loc_1800516F5
0x1800516f0  mov     r15b, r9b
0x1800516f3  jmp     short loc_180051743
0x1800516f5  lea     rdx, aAttachingAText; "Attaching a texture buffer to an incomp"...
0x1800516fc  lea     rcx, [rbp+57h+var_B0]
0x180051700  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180051705  nop
0x180051706  lea     rdx, aOnecoreuapWind; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18005170d  lea     rcx, [rbp+57h+var_90]
0x180051711  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180051716  mov     [rsp+0F0h+var_D0], 0
0x18005171b  lea     r9, [rbp+57h+var_B0]
0x18005171f  mov     rdx, rax
0x180051722  lea     rcx, [rbp+57h+pExceptionObject]
0x180051726  call    ??0EngineException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineException::EngineException(std::string,int,std::string const &,bool)
0x18005172b  lea     rdx, _TI4?AUEngineException@Engine@Spectre@@; pThrowInfo
0x180051732  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180051736  call    _CxxThrowException_0
0x18005173c  lea     r12, [r8+80h]
0x180051743  mov     r14d, 90h
0x180051749  mov     [rbp+57h+var_C0], r8
0x18005174d  lea     esi, [r14+8]
0x180051751  mov     r13, rdx
0x180051754  mov     [rbp+57h+var_B0], rdx
0x180051758  mov     rax, [rdi+8]
0x18005175c  mov     [rbp+57h+var_A8], rax
0x180051760  mov     [rdi], r9
0x180051763  mov     [rdi+8], r9
0x180051767  lea     rdx, [rbp+57h+var_B0]
0x18005176b  mov     rcx, r8
0x18005176e  call    ?AttachDeviceTextureInternal@Texture@Engine@Spectre@@AEAAXV?$shared_ptr@VDeviceTexture@Engine@Spectre@@@std@@@Z; Spectre::Engine::Texture::AttachDeviceTextureInternal(std::shared_ptr<Spectre::Engine::DeviceTexture>)
0x180051773  test    r15b, r15b
0x180051776  jz      short loc_1800517B2
0x180051778  mov     rdx, rbx
0x18005177b  lea     rcx, [rbp+57h+var_B8]
0x18005177f  call    ??$make_unique@UTextureDesc@Engine@Spectre@@AEBU123@$0A@@std@@YA?AV?$unique_ptr@UTextureDesc@Engine@Spectre@@U?$default_delete@UTextureDesc@Engine@Spectre@@@std@@@0@AEBUTextureDesc@Engine@Spectre@@@Z; std::make_unique<Spectre::Engine::TextureDesc,Spectre::Engine::TextureDesc const &,0>(Spectre::Engine::TextureDesc const &)
0x180051784  mov     rdx, rax
0x180051787  mov     rcx, r12
0x18005178a  call    ??$?4U?$default_delete@UTextureDesc@Engine@Spectre@@@std@@$0A@@?$unique_ptr@UTextureDesc@Engine@Spectre@@U?$default_delete@UTextureDesc@Engine@Spectre@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Spectre::Engine::TextureDesc>::operator=<std::default_delete<Spectre::Engine::TextureDesc>,0>(std::unique_ptr<Spectre::Engine::TextureDesc> &&)
0x18005178f  lea     rcx, [rbp+57h+var_B8]
0x180051793  call    ??1?$unique_ptr@UTextureDesc@Engine@Spectre@@U?$default_delete@UTextureDesc@Engine@Spectre@@@std@@@std@@QEAA@XZ; std::unique_ptr<Spectre::Engine::TextureDesc>::~unique_ptr<Spectre::Engine::TextureDesc>(void)
0x180051798  movss   xmm0, dword ptr [rsi+r13+4]
0x18005179f  mov     eax, [rsi+r13]
0x1800517a3  mov     rcx, [rbp+57h+var_C0]
0x1800517a7  mov     [r14+rcx], eax
0x1800517ab  movss   dword ptr [r14+rcx+4], xmm0
0x1800517b2  mov     rcx, [rdi+8]; this
0x1800517b6  test    rcx, rcx
0x1800517b9  jz      short loc_1800517C0
0x1800517bb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800517c0  mov     rcx, [rbp+57h+var_38]
0x1800517c4  xor     rcx, rsp; StackCookie
0x1800517c7  call    __security_check_cookie
0x1800517cc  mov     rbx, [rsp+0F0h+arg_10]
0x1800517d4  add     rsp, 0C0h
0x1800517db  pop     r15
0x1800517dd  pop     r14
0x1800517df  pop     r13
0x1800517e1  pop     r12
0x1800517e3  pop     rdi
0x1800517e4  pop     rsi
0x1800517e5  pop     rbp
0x1800517e6  retn
```
