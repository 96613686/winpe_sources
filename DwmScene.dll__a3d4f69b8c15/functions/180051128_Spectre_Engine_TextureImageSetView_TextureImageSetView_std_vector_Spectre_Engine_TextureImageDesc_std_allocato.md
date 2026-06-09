# Spectre::Engine::TextureImageSetView::TextureImageSetView(std::vector<Spectre::Engine::TextureImageDesc,std::allocator<Spectre::Engine::TextureImageDesc>>,void const *,unsigned __int64)

- ea: `0x180051128`
- end: `0x1800512c2`
- name: `??0TextureImageSetView@Engine@Spectre@@QEAA@V?$vector@UTextureImageDesc@Engine@Spectre@@V?$allocator@UTextureImageDesc@Engine@Spectre@@@std@@@std@@PEBX_K@Z`
- size: `410`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800510a8`
- `0x180051e54`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x180011f64`
- `0x18004e6bc`
- `0x180050f00`
- `0x180051128`
- `0x1800681a8`

## string_xrefs

- `0x1800511ca`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\texture.cpp`
- `0x180051211`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\texture.cpp`
- `0x18005128c`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\texture.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Spectre::Engine::TextureImageSetView::TextureImageSetView(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v5; // r11
  int v6; // eax
  int v7; // edx
  __int64 *v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  int v11; // eax
  int v12; // r8d
  int v13; // eax
  int v14; // r8d
  int v16; // eax
  int v17; // r8d
  _BYTE v18[32]; // [rsp+48h] [rbp-31h] BYREF
  _BYTE v19[32]; // [rsp+68h] [rbp-11h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+88h] [rbp+Fh] BYREF

  *(_QWORD *)a1 = &Spectre::Engine::TextureImageSetView::`vftable';
  *(_QWORD *)(a1 + 8) = a3;
  *(_QWORD *)(a1 + 16) = a4;
  std::vector<Spectre::Engine::TextureImageDesc>::vector<Spectre::Engine::TextureImageDesc>(a1 + 24);
  *(_DWORD *)(a1 + 48) = -1;
  v6 = 0;
  v7 = 0;
  v9 = *v8;
  v10 = v8[1];
  while ( v9 != v10 )
  {
    if ( *(_DWORD *)(v9 + 28) == v6 )
    {
      ++v6;
    }
    else
    {
      if ( *(_DWORD *)(v9 + 28) )
      {
        std::string::string(v18, "TextureImageSetView: texture image mip levels are not consecutive ascending integers");
        v13 = std::string::string(
                v19,
                "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\texture.cpp");
        Spectre::Engine::EngineException::EngineException(
          (unsigned int)pExceptionObject,
          v13,
          v14,
          (unsigned int)v18,
          0);
        throw (Spectre::Engine::EngineException *)pExceptionObject;
      }
      if ( v7 )
      {
        if ( v6 != *(_DWORD *)(a1 + 48) )
        {
          std::string::string(
            v19,
            "TextureImageSetView: texture array elements must all have the same number of mip levels defined");
          v11 = std::string::string(
                  v18,
                  "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\texture.cpp");
          Spectre::Engine::EngineException::EngineException(
            (unsigned int)pExceptionObject,
            v11,
            v12,
            (unsigned int)v19,
            0);
          throw (Spectre::Engine::EngineException *)pExceptionObject;
        }
      }
      else
      {
        *(_DWORD *)(a1 + 48) = v6;
      }
      ++v7;
      v6 = 1;
    }
    v9 += 32;
  }
  if ( v7 )
  {
    if ( v6 != *(_DWORD *)(a1 + 48) )
    {
      std::string::string(
        v18,
        "TextureImageSetView: texture array elements must all have the same number of mip levels defined");
      v16 = std::string::string(
              v19,
              "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\texture.cpp");
      Spectre::Engine::EngineException::EngineException((unsigned int)pExceptionObject, v16, v17, (unsigned int)v18, 0);
      throw (Spectre::Engine::EngineException *)pExceptionObject;
    }
  }
  else
  {
    *(_DWORD *)(a1 + 48) = v6;
  }
  std::vector<Spectre::Engine::TextureImageDesc>::_Tidy(v5);
  return a1;
}

```

## disassembly

```asm
0x180051128  mov     [rsp-8+arg_10], rbx
0x18005112d  push    rbp
0x18005112e  lea     rbp, [rsp-57h]
0x180051133  sub     rsp, 0D0h
0x18005113a  mov     rax, cs:__security_cookie
0x180051141  xor     rax, rsp
0x180051144  mov     [rbp+57h+var_10], rax
0x180051148  mov     r11, rdx
0x18005114b  mov     rbx, rcx
0x18005114e  mov     [rbp+57h+var_98], rcx
0x180051152  mov     [rbp+57h+var_90], rdx
0x180051156  lea     rax, ??_7TextureImageSetView@Engine@Spectre@@6B@; const Spectre::Engine::TextureImageSetView::`vftable'
0x18005115d  mov     [rcx], rax
0x180051160  mov     [rcx+8], r8
0x180051164  mov     [rcx+10h], r9
0x180051168  add     rcx, 18h
0x18005116c  call    ??0?$vector@UTextureImageDesc@Engine@Spectre@@V?$allocator@UTextureImageDesc@Engine@Spectre@@@std@@@std@@QEAA@$$QEAV01@@Z; std::vector<Spectre::Engine::TextureImageDesc>::vector<Spectre::Engine::TextureImageDesc>(std::vector<Spectre::Engine::TextureImageDesc> &&)
0x180051171  nop
0x180051172  mov     dword ptr [rbx+30h], 0FFFFFFFFh
0x180051179  xor     eax, eax
0x18005117b  xor     edx, edx
0x18005117d  mov     r8, [rcx]
0x180051180  mov     r9, [rcx+8]
0x180051184  cmp     r8, r9
0x180051187  jz      loc_180051247
0x18005118d  cmp     [r8+1Ch], eax
0x180051191  jnz     short loc_180051197
0x180051193  inc     eax
0x180051195  jmp     short loc_1800511B3
0x180051197  cmp     dword ptr [r8+1Ch], 0
0x18005119c  jnz     short loc_180051200
0x18005119e  test    edx, edx
0x1800511a0  jnz     short loc_1800511A7
0x1800511a2  mov     [rbx+30h], eax
0x1800511a5  jmp     short loc_1800511AC
0x1800511a7  cmp     eax, [rbx+30h]
0x1800511aa  jnz     short loc_1800511B9
0x1800511ac  inc     edx
0x1800511ae  mov     eax, 1
0x1800511b3  add     r8, 20h ; ' '
0x1800511b7  jmp     short loc_180051184
0x1800511b9  lea     rdx, aTextureimagese_0; "TextureImageSetView: texture array elem"...
0x1800511c0  lea     rcx, [rbp+57h+var_68]
0x1800511c4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800511c9  nop
0x1800511ca  lea     rdx, aOnecoreuapWind; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x1800511d1  lea     rcx, [rbp+57h+var_88]
0x1800511d5  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800511da  mov     [rsp+0D0h+var_B0], 0
0x1800511df  lea     r9, [rbp+57h+var_68]
0x1800511e3  mov     rdx, rax
0x1800511e6  lea     rcx, [rbp+57h+pExceptionObject]
0x1800511ea  call    ??0EngineException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineException::EngineException(std::string,int,std::string const &,bool)
0x1800511ef  lea     rdx, _TI4?AUEngineException@Engine@Spectre@@; pThrowInfo
0x1800511f6  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800511fa  call    _CxxThrowException_0
0x180051200  lea     rdx, aTextureimagese; "TextureImageSetView: texture image mip "...
0x180051207  lea     rcx, [rbp+57h+var_88]
0x18005120b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180051210  nop
0x180051211  lea     rdx, aOnecoreuapWind; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180051218  lea     rcx, [rbp+57h+var_68]
0x18005121c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180051221  mov     [rsp+0D0h+var_B0], 0
0x180051226  lea     r9, [rbp+57h+var_88]
0x18005122a  mov     rdx, rax
0x18005122d  lea     rcx, [rbp+57h+pExceptionObject]
0x180051231  call    ??0EngineException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineException::EngineException(std::string,int,std::string const &,bool)
0x180051236  lea     rdx, _TI4?AUEngineException@Engine@Spectre@@; pThrowInfo
0x18005123d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180051241  call    _CxxThrowException_0
0x180051247  test    edx, edx
0x180051249  jnz     short loc_180051276
0x18005124b  mov     [rbx+30h], eax
0x18005124e  mov     rcx, r11
0x180051251  call    ?_Tidy@?$vector@UTextureImageDesc@Engine@Spectre@@V?$allocator@UTextureImageDesc@Engine@Spectre@@@std@@@std@@AEAAXXZ; std::vector<Spectre::Engine::TextureImageDesc>::_Tidy(void)
0x180051256  mov     rax, rbx
0x180051259  mov     rcx, [rbp+57h+var_10]
0x18005125d  xor     rcx, rsp; StackCookie
0x180051260  call    __security_check_cookie
0x180051265  mov     rbx, [rsp+0D0h+arg_10]
0x18005126d  add     rsp, 0D0h
0x180051274  pop     rbp
0x180051275  retn
0x180051276  cmp     eax, [rbx+30h]
0x180051279  jz      short loc_18005124E
0x18005127b  lea     rdx, aTextureimagese_0; "TextureImageSetView: texture array elem"...
0x180051282  lea     rcx, [rbp+57h+var_88]
0x180051286  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18005128b  nop
0x18005128c  lea     rdx, aOnecoreuapWind; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180051293  lea     rcx, [rbp+57h+var_68]
0x180051297  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18005129c  mov     [rsp+0D0h+var_B0], 0
0x1800512a1  lea     r9, [rbp+57h+var_88]
0x1800512a5  mov     rdx, rax
0x1800512a8  lea     rcx, [rbp+57h+pExceptionObject]
0x1800512ac  call    ??0EngineException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineException::EngineException(std::string,int,std::string const &,bool)
0x1800512b1  lea     rdx, _TI4?AUEngineException@Engine@Spectre@@; pThrowInfo
0x1800512b8  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800512bc  call    _CxxThrowException_0
```
