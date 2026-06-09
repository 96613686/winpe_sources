# Spectre::Engine::ValidateAnimation(Spectre::Engine::SafeBXFReader<Spectre::Framework::AnimationSkinnedLittleEndian>,std::map<uint,unsigned __int64,std::less<uint>,std::allocator<std::pair<uint const,unsigned __int64>>> const &,bool)

- ea: `0x1804c2e30`
- end: `0x1804c3378`
- name: `?ValidateAnimation@Engine@Spectre@@YAXV?$SafeBXFReader@UAnimationSkinnedLittleEndian@Framework@Spectre@@@12@AEBV?$map@I_KU?$less@I@std@@V?$allocator@U?$pair@$$CBI_K@std@@@2@@std@@_N@Z`
- size: `1352`
- prototype: `void __fastcall(__int64, __int64 **)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x1804c2480`

## callees

- `0x180015770`
- `0x180016430`
- `0x1801d4fe0`
- `0x1802ed820`
- `0x18039e5b0`
- `0x18039ebb0`
- `0x18039f8e0`
- `0x18039fa90`
- `0x1804c0d80`
- `0x1804c12b0`
- `0x1804c2e30`
- `0x1804c3860`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1804c30d0`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1804c314d`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1804c3192`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1804c30d0`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1804c314d`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1804c3192`

## string_xrefs

- `0x1804c3240`: `Parser: Found invalid animation - no linked skeleton`
- `0x1804c31d8`: `Parser: Found invalid animation - linked skeleton could not be found`
- `0x1804c32dc`: `SafeBXFReader - unknown ChunkType.`
- `0x1804c3274`: `SafeBXFReader - invalid alignment`

## pseudocode

```c
void __fastcall Spectre::Engine::ValidateAnimation(__int64 a1, __int64 **a2)
{
  __int64 v2; // rdi
  __int64 v3; // r13
  __int64 v4; // r11
  unsigned int v5; // r9d
  __int64 *v6; // rdx
  __int64 *v7; // rcx
  __int64 *v8; // r8
  char v9; // r10
  __int64 *v10; // rax
  unsigned __int64 v11; // rsi
  __int64 *v12; // r15
  __int64 v13; // r12
  unsigned __int16 v14; // r14
  __int64 *v15; // rbx
  __int64 v16; // rdi
  __int64 v17; // r8
  __int64 v18; // rax
  _QWORD *v19; // rdx
  void *v20; // rcx
  void *v21; // r8
  unsigned __int64 v22; // rbx
  __int64 v23; // rax
  __int64 v24; // rcx
  void *v25; // rcx
  void *Block[3]; // [rsp+20h] [rbp-A9h] BYREF
  unsigned __int64 v27; // [rsp+38h] [rbp-91h]
  __int64 v28; // [rsp+40h] [rbp-89h]
  __int64 v29; // [rsp+48h] [rbp-81h] BYREF
  unsigned __int64 v30; // [rsp+50h] [rbp-79h]
  __int128 v31; // [rsp+60h] [rbp-69h] BYREF
  __int64 v32; // [rsp+70h] [rbp-59h]
  _BYTE pExceptionObject[64]; // [rsp+80h] [rbp-49h] BYREF
  void *v34[2]; // [rsp+C0h] [rbp-9h] BYREF
  void *v35; // [rsp+D0h] [rbp+7h]
  void *v36[2]; // [rsp+D8h] [rbp+Fh] BYREF
  __int64 *v37; // [rsp+E8h] [rbp+1Fh]

  v2 = a1;
  v28 = a1;
  v3 = *(_QWORD *)a1;
  v4 = *(unsigned int *)(*(_QWORD *)a1 + 28LL);
  if ( !(_DWORD)v4 )
  {
    std::string::string(Block, "Parser: Found invalid animation - no chunks");
    Spectre::Utils::SpectreInvalidArgException::SpectreInvalidArgException(pExceptionObject, Block, 0);
    throw (Spectre::Utils::SpectreInvalidArgException *)pExceptionObject;
  }
  v5 = *(_DWORD *)(v3 + 12);
  if ( !v5 )
  {
    std::string::string(Block, "Parser: Found invalid animation - no linked skeleton");
    Spectre::Utils::SpectreInvalidArgException::SpectreInvalidArgException(pExceptionObject, Block, 0);
    throw (Spectre::Utils::SpectreInvalidArgException *)pExceptionObject;
  }
  v6 = *a2;
  v7 = (__int64 *)v6[1];
  v8 = v6;
  v9 = *((_BYTE *)v7 + 25);
  if ( !v9 )
  {
    v10 = (__int64 *)v6[1];
    do
    {
      if ( *((_DWORD *)v10 + 8) >= v5 )
      {
        v8 = v10;
        v10 = (__int64 *)*v10;
      }
      else
      {
        v10 = (__int64 *)v10[2];
      }
    }
    while ( !*((_BYTE *)v10 + 25) );
  }
  if ( *((_BYTE *)v8 + 25) || v5 < *((_DWORD *)v8 + 8) || v8 == v6 )
  {
    std::string::string(Block, "Parser: Found invalid animation - linked skeleton could not be found");
    Spectre::Utils::SpectreInvalidArgException::SpectreInvalidArgException(pExceptionObject, Block, 0);
    throw (Spectre::Utils::SpectreInvalidArgException *)pExceptionObject;
  }
  if ( !v9 )
  {
    do
    {
      if ( *((_DWORD *)v7 + 8) >= v5 )
      {
        v6 = v7;
        v7 = (__int64 *)*v7;
      }
      else
      {
        v7 = (__int64 *)v7[2];
      }
    }
    while ( !*((_BYTE *)v7 + 25) );
  }
  if ( *((_BYTE *)v6 + 25) || v5 < *((_DWORD *)v6 + 8) )
  {
    std::_Xout_of_range("invalid map<K, T> key");
    __debugbreak();
  }
  v30 = v6[5];
  Spectre::Engine::SafeBXFReader<Spectre::Framework::MeshSegmentLittleEndian>::ValidateOffset(v2, 8 * v4 + 32);
  *(_OWORD *)v34 = 0;
  v11 = 0;
  v35 = 0;
  *(_OWORD *)v36 = 0;
  v12 = 0;
  v37 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  if ( *(_DWORD *)(v3 + 28) )
  {
    do
    {
      v16 = v3 + 32 + 8LL * v14;
      v29 = v16;
      Spectre::Engine::SafeBXFReader<Spectre::Framework::MeshSegmentLittleEndian>::ValidateOffset(
        v28,
        *(unsigned int *)(v16 + 4));
      if ( *(_BYTE *)v16 != 1 )
      {
        std::string::string(Block, "SafeBXFReader - unknown ChunkType.");
        Spectre::Utils::SpectreInvalidArgException::SpectreInvalidArgException(pExceptionObject, Block, 0);
        throw (Spectre::Utils::SpectreInvalidArgException *)pExceptionObject;
      }
      v13 |= 2uLL;
      if ( v13 != 2 )
      {
        std::string::string(Block, "ValidateAnimation: Mixture of ChunkTypes.");
        Spectre::Utils::SpectreInvalidArgException::SpectreInvalidArgException(pExceptionObject, Block, 0);
        throw (Spectre::Utils::SpectreInvalidArgException *)pExceptionObject;
      }
      Spectre::Engine::SafeBXFReader<Spectre::Framework::MeshSegmentLittleEndian>::ValidateOffset(
        v28,
        *(unsigned int *)(v16 + 4) + 4LL);
      v17 = *(unsigned int *)(v16 + 4);
      if ( (v17 & 3) != 0 )
      {
        std::string::string(Block, "SafeBXFReader - invalid alignment");
        Spectre::Utils::SpectreInvalidArgException::SpectreInvalidArgException(pExceptionObject, Block, 0);
        throw (Spectre::Utils::SpectreInvalidArgException *)pExceptionObject;
      }
      v18 = v17 + 40LL * *(unsigned __int16 *)(v17 + v16 + 2);
      *(_QWORD *)&v31 = v17 + 8LL * v14 + 32;
      *((_QWORD *)&v31 + 1) = v18 + 8LL * v14 + 36;
      v19 = v34[1];
      if ( v34[1] == v35 )
      {
        std::vector<std::pair<unsigned __int64,unsigned __int64>>::_Emplace_reallocate<std::pair<unsigned __int64,unsigned __int64>>(
          v34,
          v34[1],
          &v31);
      }
      else
      {
        *(_QWORD *)v34[1] = v17 + 8LL * v14 + 32;
        v19[1] = v18 + 8LL * v14 + 36;
        v34[1] = (char *)v34[1] + 16;
      }
      if ( v15 == v12 )
      {
        std::vector<Spectre::Engine::SceneNode *>::_Emplace_reallocate<Spectre::Engine::SceneNode * const &>(
          v36,
          v15,
          &v29);
        v12 = v37;
        v15 = (__int64 *)v36[1];
      }
      else
      {
        *v15++ = v16;
        v36[1] = v15;
      }
      ++v14;
    }
    while ( (unsigned int)v14 < *(_DWORD *)(v3 + 28) );
    v2 = v28;
  }
  Block[0] = 0;
  Block[2] = 0;
  v27 = 15;
  std::string::assign(Block);
  v31 = *(_OWORD *)v2;
  v32 = *(_QWORD *)(v2 + 16);
  sub_1804C0D80((__int64)&v31, (__int64)v34);
  if ( v27 >= 0x10 )
  {
    v20 = Block[0];
    if ( v27 + 1 >= 0x1000 )
    {
      v20 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v20 - 8) > 0x1F )
        _invalid_parameter_noinfo_noreturn();
    }
    operator delete(v20);
  }
  v21 = v36[0];
  v22 = ((char *)v15 - (char *)v36[0]) >> 3;
  if ( v22 )
  {
    do
    {
      v23 = *((_QWORD *)v36[0] + v11);
      v24 = *(unsigned int *)(v23 + 4);
      if ( !*(_WORD *)(v24 + v23 + 2) )
      {
        std::string::string(Block, "ValidateAnimation: FixedTimeStepChunk has no frames.");
        Spectre::Utils::SpectreInvalidArgException::SpectreInvalidArgException(pExceptionObject, Block, 0);
        throw (Spectre::Utils::SpectreInvalidArgException *)pExceptionObject;
      }
      if ( *(unsigned __int16 *)(v24 + v23) >= v30 )
      {
        std::string::string(Block, "ValidateAnimation: FixedTimeStepChunk joint index overflows skeleton joint count.");
        Spectre::Utils::SpectreInvalidArgException::SpectreInvalidArgException(pExceptionObject, Block, 0);
        throw (Spectre::Utils::SpectreInvalidArgException *)pExceptionObject;
      }
      ++v11;
    }
    while ( v11 < v22 );
  }
  if ( v36[0] )
  {
    if ( (unsigned __int64)(8 * (((char *)v12 - (char *)v36[0]) >> 3)) >= 0x1000 )
    {
      v21 = (void *)*((_QWORD *)v36[0] - 1);
      if ( (unsigned __int64)((char *)v36[0] - (char *)v21 - 8) > 0x1F )
        _invalid_parameter_noinfo_noreturn();
    }
    operator delete(v21);
  }
  v25 = v34[0];
  if ( v34[0] )
  {
    if ( (((unsigned __int64)v35 - (unsigned __int64)v34[0]) & 0xFFFFFFFFFFFFFFF0uLL) >= 0x1000 )
    {
      v25 = (void *)*((_QWORD *)v34[0] - 1);
      if ( (unsigned __int64)((char *)v34[0] - (char *)v25 - 8) > 0x1F )
        _invalid_parameter_noinfo_noreturn();
    }
    operator delete(v25);
  }
}

```

## disassembly

```asm
0x1804c2e30  mov     [rsp-8+arg_8], rbx
0x1804c2e35  mov     [rsp-8+arg_10], rsi
0x1804c2e3a  mov     [rsp-8+arg_18], rdi
0x1804c2e3f  push    rbp
0x1804c2e40  push    r12
0x1804c2e42  push    r13
0x1804c2e44  push    r14
0x1804c2e46  push    r15
0x1804c2e48  lea     rbp, [rsp-37h]
0x1804c2e4d  sub     rsp, 100h
0x1804c2e54  mov     rax, cs:__security_cookie
0x1804c2e5b  xor     rax, rsp
0x1804c2e5e  mov     [rbp+57h+var_30], rax
0x1804c2e62  mov     rdi, rcx
0x1804c2e65  mov     [rsp+120h+var_E0], rcx
0x1804c2e6a  mov     r13, [rcx]
0x1804c2e6d  mov     r11d, [r13+1Ch]
0x1804c2e71  test    r11d, r11d
0x1804c2e74  jz      loc_1804C320C
0x1804c2e7a  mov     r9d, [r13+0Ch]
0x1804c2e7e  test    r9d, r9d
0x1804c2e81  jz      loc_1804C3240
0x1804c2e87  mov     rdx, [rdx]
0x1804c2e8a  mov     rcx, [rdx+8]
0x1804c2e8e  mov     r8, rdx
0x1804c2e91  movzx   r10d, byte ptr [rcx+19h]
0x1804c2e96  test    r10b, r10b
0x1804c2e99  jnz     short loc_1804C2EB8
0x1804c2e9b  mov     rax, rcx
0x1804c2e9e  xchg    ax, ax
0x1804c2ea0  cmp     [rax+20h], r9d
0x1804c2ea4  jnb     short loc_1804C2EAC
0x1804c2ea6  mov     rax, [rax+10h]
0x1804c2eaa  jmp     short loc_1804C2EB2
0x1804c2eac  mov     r8, rax
0x1804c2eaf  mov     rax, [rax]
0x1804c2eb2  cmp     byte ptr [rax+19h], 0
0x1804c2eb6  jz      short loc_1804C2EA0
0x1804c2eb8  cmp     byte ptr [r8+19h], 0
0x1804c2ebd  jnz     loc_1804C31D8
0x1804c2ec3  cmp     r9d, [r8+20h]
0x1804c2ec7  jb      loc_1804C31D8
0x1804c2ecd  cmp     r8, rdx
0x1804c2ed0  jz      loc_1804C31D8
0x1804c2ed6  test    r10b, r10b
0x1804c2ed9  jnz     short loc_1804C2EF8
0x1804c2edb  nop     dword ptr [rax+rax+00h]
0x1804c2ee0  cmp     [rcx+20h], r9d
0x1804c2ee4  jnb     short loc_1804C2EEC
0x1804c2ee6  mov     rcx, [rcx+10h]
0x1804c2eea  jmp     short loc_1804C2EF2
0x1804c2eec  mov     rdx, rcx
0x1804c2eef  mov     rcx, [rcx]
0x1804c2ef2  cmp     byte ptr [rcx+19h], 0
0x1804c2ef6  jz      short loc_1804C2EE0
0x1804c2ef8  cmp     byte ptr [rdx+19h], 0
0x1804c2efc  jnz     loc_1804C31CB
0x1804c2f02  cmp     r9d, [rdx+20h]
0x1804c2f06  jb      loc_1804C31CB
0x1804c2f0c  mov     rax, [rdx+28h]
0x1804c2f10  mov     [rbp+57h+var_D0], rax
0x1804c2f14  lea     rdx, ds:20h[r11*8]
0x1804c2f1c  mov     rcx, rdi
0x1804c2f1f  call    ?ValidateOffset@?$SafeBXFReader@UMeshSegmentLittleEndian@Framework@Spectre@@@Engine@Spectre@@QEBAX_K@Z; Spectre::Engine::SafeBXFReader<Spectre::Framework::MeshSegmentLittleEndian>::ValidateOffset(unsigned __int64)
0x1804c2f24  xorps   xmm1, xmm1
0x1804c2f27  movdqu  xmmword ptr [rbp+57h+var_60], xmm1
0x1804c2f2c  xor     esi, esi
0x1804c2f2e  mov     [rbp+57h+var_50], rsi
0x1804c2f32  movdqu  xmmword ptr [rbp+57h+var_48], xmm1
0x1804c2f37  mov     r15d, esi
0x1804c2f3a  mov     [rbp+57h+var_38], rsi
0x1804c2f3e  mov     r12d, esi
0x1804c2f41  movzx   r14d, si
0x1804c2f45  mov     rbx, [rbp+57h+var_48+8]
0x1804c2f49  cmp     [r13+1Ch], esi
0x1804c2f4d  jbe     loc_1804C3048
0x1804c2f53  movzx   eax, r14w
0x1804c2f57  lea     rdi, [r13+20h]
0x1804c2f5b  lea     rdi, [rdi+rax*8]
0x1804c2f5f  mov     [rsp+120h+var_D8], rdi
0x1804c2f64  mov     edx, [rdi+4]
0x1804c2f67  mov     rcx, [rsp+120h+var_E0]
0x1804c2f6c  call    ?ValidateOffset@?$SafeBXFReader@UMeshSegmentLittleEndian@Framework@Spectre@@@Engine@Spectre@@QEBAX_K@Z; Spectre::Engine::SafeBXFReader<Spectre::Framework::MeshSegmentLittleEndian>::ValidateOffset(unsigned __int64)
0x1804c2f71  movzx   eax, byte ptr [rdi]
0x1804c2f74  cmp     al, 1
0x1804c2f76  jnz     loc_1804C32DC
0x1804c2f7c  mov     ecx, eax
0x1804c2f7e  mov     eax, 1
0x1804c2f83  shl     rax, cl
0x1804c2f86  or      r12, rax
0x1804c2f89  cmp     r12, rax
0x1804c2f8c  jnz     loc_1804C32A8
0x1804c2f92  cmp     ecx, 1
0x1804c2f95  jnz     loc_1804C3031
0x1804c2f9b  mov     edx, [rdi+4]
0x1804c2f9e  add     rdx, 4
0x1804c2fa2  mov     rcx, [rsp+120h+var_E0]
0x1804c2fa7  call    ?ValidateOffset@?$SafeBXFReader@UMeshSegmentLittleEndian@Framework@Spectre@@@Engine@Spectre@@QEBAX_K@Z; Spectre::Engine::SafeBXFReader<Spectre::Framework::MeshSegmentLittleEndian>::ValidateOffset(unsigned __int64)
0x1804c2fac  mov     r8d, [rdi+4]
0x1804c2fb0  test    r8b, 3
0x1804c2fb4  jnz     loc_1804C3274
0x1804c2fba  mov     rdx, rdi
0x1804c2fbd  sub     rdx, r13
0x1804c2fc0  lea     r9, [r8+rdx]
0x1804c2fc4  movzx   eax, word ptr [r8+rdi+2]
0x1804c2fca  lea     rcx, [rax+rax*4]
0x1804c2fce  lea     rax, [r8+rcx*8]
0x1804c2fd2  lea     rcx, [rdx+4]
0x1804c2fd6  add     rcx, rax
0x1804c2fd9  mov     qword ptr [rbp+57h+var_C0], r9
0x1804c2fdd  mov     qword ptr [rbp+57h+var_C0+8], rcx
0x1804c2fe1  mov     rdx, [rbp+57h+var_60+8]
0x1804c2fe5  cmp     rdx, [rbp+57h+var_50]
0x1804c2fe9  jz      short loc_1804C2FF9
0x1804c2feb  mov     [rdx], r9
0x1804c2fee  mov     [rdx+8], rcx
0x1804c2ff2  add     [rbp+57h+var_60+8], 10h
0x1804c2ff7  jmp     short loc_1804C3006
0x1804c2ff9  lea     r8, [rbp+57h+var_C0]
0x1804c2ffd  lea     rcx, [rbp+57h+var_60]
0x1804c3001  call    ??$_Emplace_reallocate@U?$pair@_K_K@std@@@?$vector@U?$pair@_K_K@std@@V?$allocator@U?$pair@_K_K@std@@@2@@std@@QEAAPEAU?$pair@_K_K@1@QEAU21@$$QEAU21@@Z; std::vector<std::pair<unsigned __int64,unsigned __int64>>::_Emplace_reallocate<std::pair<unsigned __int64,unsigned __int64>>(std::pair<unsigned __int64,unsigned __int64> * const,std::pair<unsigned __int64,unsigned __int64> &&)
0x1804c3006  cmp     rbx, r15
0x1804c3009  jz      short loc_1804C3018
0x1804c300b  mov     [rbx], rdi
0x1804c300e  add     rbx, 8
0x1804c3012  mov     [rbp+57h+var_48+8], rbx
0x1804c3016  jmp     short loc_1804C3031
0x1804c3018  lea     r8, [rsp+120h+var_D8]
0x1804c301d  mov     rdx, rbx
0x1804c3020  lea     rcx, [rbp+57h+var_48]
0x1804c3024  call    ??$_Emplace_reallocate@AEBQEAVSceneNode@Engine@Spectre@@@?$vector@PEAVSceneNode@Engine@Spectre@@V?$allocator@PEAVSceneNode@Engine@Spectre@@@std@@@std@@QEAAPEAPEAVSceneNode@Engine@Spectre@@QEAPEAV234@AEBQEAV234@@Z; std::vector<Spectre::Engine::SceneNode *>::_Emplace_reallocate<Spectre::Engine::SceneNode * const &>(Spectre::Engine::SceneNode * * const,Spectre::Engine::SceneNode * const &)
0x1804c3029  mov     r15, [rbp+57h+var_38]
0x1804c302d  mov     rbx, [rbp+57h+var_48+8]
0x1804c3031  inc     r14w
0x1804c3035  movzx   eax, r14w
0x1804c3039  cmp     eax, [r13+1Ch]
0x1804c303d  jb      loc_1804C2F53
0x1804c3043  mov     rdi, [rsp+120h+var_E0]
0x1804c3048  mov     [rsp+120h+Block], rsi
0x1804c304d  mov     [rsp+120h+var_F0], rsi
0x1804c3052  mov     [rsp+120h+var_E8], 0Fh
0x1804c305b  mov     byte ptr [rsp+120h+Block], 0
0x1804c3060  mov     r8d, 39h ; '9'
0x1804c3066  lea     rdx, aValidateanimat; "ValidateAnimation: Overlapping data buf"...
0x1804c306d  lea     rcx, [rsp+120h+Block]; void *
0x1804c3072  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x1804c3077  nop
0x1804c3078  movups  xmm0, xmmword ptr [rdi]
0x1804c307b  movaps  [rbp+57h+var_C0], xmm0
0x1804c307f  movsd   xmm1, qword ptr [rdi+10h]
0x1804c3084  movsd   [rbp+57h+var_B0], xmm1
0x1804c3089  lea     r8, [rsp+120h+Block]
0x1804c308e  lea     rdx, [rbp+57h+var_60]
0x1804c3092  lea     rcx, [rbp+57h+var_C0]
0x1804c3096  call    sub_1804C0D80
0x1804c309b  nop
0x1804c309c  mov     rdx, [rsp+120h+var_E8]
0x1804c30a1  cmp     rdx, 10h
0x1804c30a5  jb      short loc_1804C30DC
0x1804c30a7  inc     rdx
0x1804c30aa  mov     rcx, [rsp+120h+Block]; Block
0x1804c30af  mov     rax, rcx
0x1804c30b2  cmp     rdx, 1000h
0x1804c30b9  jb      short loc_1804C30D7
0x1804c30bb  add     rdx, 27h ; '''
0x1804c30bf  mov     rcx, [rcx-8]
0x1804c30c3  sub     rax, rcx
0x1804c30c6  add     rax, 0FFFFFFFFFFFFFFF8h
0x1804c30ca  cmp     rax, 1Fh
0x1804c30ce  jbe     short loc_1804C30D7
0x1804c30d0  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1804c30d7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1804c30dc  mov     r8, [rbp+57h+var_48]
0x1804c30e0  sub     rbx, r8
0x1804c30e3  sar     rbx, 3
0x1804c30e7  test    rbx, rbx
0x1804c30ea  jz      short loc_1804C3118
0x1804c30ec  mov     rdx, [rbp+57h+var_D0]
0x1804c30f0  mov     rax, [r8+rsi*8]
0x1804c30f4  mov     ecx, [rax+4]
0x1804c30f7  cmp     word ptr [rcx+rax+2], 0
0x1804c30fd  jz      loc_1804C3344
0x1804c3103  movzx   eax, word ptr [rcx+rax]
0x1804c3107  cmp     rax, rdx
0x1804c310a  jnb     loc_1804C3310
0x1804c3110  inc     rsi
0x1804c3113  cmp     rsi, rbx
0x1804c3116  jb      short loc_1804C30F0
0x1804c3118  test    r8, r8
0x1804c311b  jz      short loc_1804C315D
0x1804c311d  sub     r15, r8
0x1804c3120  sar     r15, 3
0x1804c3124  lea     rdx, ds:0[r15*8]
0x1804c312c  mov     rax, r8
0x1804c312f  cmp     rdx, 1000h
0x1804c3136  jb      short loc_1804C3154
0x1804c3138  add     rdx, 27h ; '''
0x1804c313c  mov     r8, [r8-8]
0x1804c3140  sub     rax, r8
0x1804c3143  add     rax, 0FFFFFFFFFFFFFFF8h
0x1804c3147  cmp     rax, 1Fh
0x1804c314b  jbe     short loc_1804C3154
0x1804c314d  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1804c3154  mov     rcx, r8; Block
0x1804c3157  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1804c315c  nop
0x1804c315d  mov     rcx, [rbp+57h+var_60]; Block
0x1804c3161  test    rcx, rcx
0x1804c3164  jz      short loc_1804C319E
0x1804c3166  mov     rdx, [rbp+57h+var_50]
0x1804c316a  sub     rdx, rcx
0x1804c316d  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1804c3171  mov     rax, rcx
0x1804c3174  cmp     rdx, 1000h
0x1804c317b  jb      short loc_1804C3199
0x1804c317d  add     rdx, 27h ; '''
0x1804c3181  mov     rcx, [rcx-8]
0x1804c3185  sub     rax, rcx
0x1804c3188  add     rax, 0FFFFFFFFFFFFFFF8h
0x1804c318c  cmp     rax, 1Fh
0x1804c3190  jbe     short loc_1804C3199
0x1804c3192  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1804c3199  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1804c319e  mov     rcx, [rbp+57h+var_30]
0x1804c31a2  xor     rcx, rsp; StackCookie
0x1804c31a5  call    __security_check_cookie
0x1804c31aa  lea     r11, [rsp+120h+var_20]
0x1804c31b2  mov     rbx, [r11+38h]
0x1804c31b6  mov     rsi, [r11+40h]
0x1804c31ba  mov     rdi, [r11+48h]
0x1804c31be  mov     rsp, r11
0x1804c31c1  pop     r15
0x1804c31c3  pop     r14
0x1804c31c5  pop     r13
0x1804c31c7  pop     r12
0x1804c31c9  pop     rbp
0x1804c31ca  retn
0x1804c31cb  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x1804c31d2  call    ?_Xout_of_range@std@@YAXPEBD@Z_0; std::_Xout_of_range(char const *)
0x1804c31d7  int     3; Trap to Debugger
0x1804c31d8  lea     rdx, aParserFoundInv_5; "Parser: Found invalid animation - linke"...
0x1804c31df  lea     rcx, [rsp+120h+Block]
0x1804c31e4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1804c31e9  nop
0x1804c31ea  xor     r8d, r8d
0x1804c31ed  lea     rdx, [rsp+120h+Block]
0x1804c31f2  lea     rcx, [rbp+57h+pExceptionObject]
0x1804c31f6  call    ??0SpectreInvalidArgException@Utils@Spectre@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@Z; Spectre::Utils::SpectreInvalidArgException::SpectreInvalidArgException(std::string const &,bool)
0x1804c31fb  lea     rdx, _TI4?AUSpectreInvalidArgException@Utils@Spectre@@; pThrowInfo
0x1804c3202  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1804c3206  call    _CxxThrowException_0
0x1804c320c  lea     rdx, aParserFoundInv_3; "Parser: Found invalid animation - no ch"...
0x1804c3213  lea     rcx, [rsp+120h+Block]
0x1804c3218  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1804c321d  nop
0x1804c321e  xor     r8d, r8d
0x1804c3221  lea     rdx, [rsp+120h+Block]
0x1804c3226  lea     rcx, [rbp+57h+pExceptionObject]
0x1804c322a  call    ??0SpectreInvalidArgException@Utils@Spectre@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@Z; Spectre::Utils::SpectreInvalidArgException::SpectreInvalidArgException(std::string const &,bool)
0x1804c322f  lea     rdx, _TI4?AUSpectreInvalidArgException@Utils@Spectre@@; pThrowInfo
0x1804c3236  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1804c323a  call    _CxxThrowException_0
0x1804c3240  lea     rdx, aParserFoundInv_1; "Parser: Found invalid animation - no li"...
0x1804c3247  lea     rcx, [rsp+120h+Block]
0x1804c324c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1804c3251  nop
0x1804c3252  xor     r8d, r8d
0x1804c3255  lea     rdx, [rsp+120h+Block]
0x1804c325a  lea     rcx, [rbp+57h+pExceptionObject]
0x1804c325e  call    ??0SpectreInvalidArgException@Utils@Spectre@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@Z; Spectre::Utils::SpectreInvalidArgException::SpectreInvalidArgException(std::string const &,bool)
0x1804c3263  lea     rdx, _TI4?AUSpectreInvalidArgException@Utils@Spectre@@; pThrowInfo
0x1804c326a  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1804c326e  call    _CxxThrowException_0
0x1804c3274  lea     rdx, aSafebxfreaderI; "SafeBXFReader - invalid alignment"
0x1804c327b  lea     rcx, [rsp+120h+Block]
0x1804c3280  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1804c3285  nop
0x1804c3286  xor     r8d, r8d
0x1804c3289  lea     rdx, [rsp+120h+Block]
0x1804c328e  lea     rcx, [rbp+57h+pExceptionObject]
0x1804c3292  call    ??0SpectreInvalidArgException@Utils@Spectre@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@Z; Spectre::Utils::SpectreInvalidArgException::SpectreInvalidArgException(std::string const &,bool)
0x1804c3297  lea     rdx, _TI4?AUSpectreInvalidArgException@Utils@Spectre@@; pThrowInfo
0x1804c329e  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1804c32a2  call    _CxxThrowException_0
0x1804c32a8  lea     rdx, aValidateanimat_1; "ValidateAnimation: Mixture of ChunkType"...
0x1804c32af  lea     rcx, [rsp+120h+Block]
0x1804c32b4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1804c32b9  nop
0x1804c32ba  xor     r8d, r8d
0x1804c32bd  lea     rdx, [rsp+120h+Block]
0x1804c32c2  lea     rcx, [rbp+57h+pExceptionObject]
0x1804c32c6  call    ??0SpectreInvalidArgException@Utils@Spectre@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@Z; Spectre::Utils::SpectreInvalidArgException::SpectreInvalidArgException(std::string const &,bool)
0x1804c32cb  lea     rdx, _TI4?AUSpectreInvalidArgException@Utils@Spectre@@; pThrowInfo
0x1804c32d2  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1804c32d6  call    _CxxThrowException_0
0x1804c32dc  lea     rdx, aSafebxfreaderU; "SafeBXFReader - unknown ChunkType."
0x1804c32e3  lea     rcx, [rsp+120h+Block]
0x1804c32e8  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1804c32ed  nop
0x1804c32ee  xor     r8d, r8d
  ... truncated ...
```
