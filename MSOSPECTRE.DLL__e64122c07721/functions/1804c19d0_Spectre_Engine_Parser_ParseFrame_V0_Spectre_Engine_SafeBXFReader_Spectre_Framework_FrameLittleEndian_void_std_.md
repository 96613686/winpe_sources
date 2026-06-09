# Spectre::Engine::Parser::ParseFrame_V0(Spectre::Engine::SafeBXFReader<Spectre::Framework::FrameLittleEndian>,void *,std::function<void (Spectre::Framework::EFrameType,Spectre::Framework::EFrameQuality)>)

- ea: `0x1804c19d0`
- end: `0x1804c247c`
- name: `?ParseFrame_V0@Parser@Engine@Spectre@@IEAAIV?$SafeBXFReader@UFrameLittleEndian@Framework@Spectre@@@23@PEAXV?$function@$$A6AXW4EFrameType@Framework@Spectre@@W4EFrameQuality@23@@Z@std@@@Z`
- size: `2732`
- prototype: `__int64 __fastcall(Spectre::Engine::Parser *this, __int64 *, void *, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1804c1790`

## callees

- `0x180015770`
- `0x1801cd2a0`
- `0x1801cd320`
- `0x1801d4fe0`
- `0x18039f8e0`
- `0x1804c19d0`
- `0x1804c2480`
- `0x1804c2660`
- `0x1804c2cc0`
- `0x1804c3860`
- `0x1804f99e0`

## string_xrefs

- `0x1804c1c96`: `Incorrect COOL format. Please update your COOL files`
- `0x1804c1e0e`: `Incorrect COOL format. Please update your COOL files`
- `0x1804c1f27`: `Parser: Compression not supported for frame data`
- `0x1804c2095`: `SafeBXFReader - NULL buffer`
- `0x1804c21c9`: `SafeBXFReader - NULL buffer`
- `0x1804c2395`: `SafeBXFReader - NULL buffer`
- `0x1804c1fff`: `SafeBXFReader - Sizeof Type exceeds buffer size`
- `0x1804c212d`: `SafeBXFReader - Sizeof Type exceeds buffer size`
- `0x1804c22f9`: `SafeBXFReader - Sizeof Type exceeds buffer size`
- `0x1804c20c7`: `Frame::GetItemByIndex - Object outside bounds of frame. Bad data.`
- `0x1804c21fd`: `Frame::GetItemByIndex - Object outside bounds of frame. Bad data.`
- `0x1804c23c9`: `Frame::GetItemByIndex - Object outside bounds of frame. Bad data.`
- `0x1804c242d`: `Frame::GetItemByIndex - Object outside bounds of frame. Bad data.`
- `0x1804c2031`: `SafeBXFReader - child buffer is outside parent buffer`
- `0x1804c2063`: `SafeBXFReader - child buffer is outside parent buffer`
- `0x1804c2161`: `SafeBXFReader - child buffer is outside parent buffer`
- `0x1804c2195`: `SafeBXFReader - child buffer is outside parent buffer`
- `0x1804c232d`: `SafeBXFReader - child buffer is outside parent buffer`
- `0x1804c2361`: `SafeBXFReader - child buffer is outside parent buffer`

## pseudocode

```c
__int64 __fastcall Spectre::Engine::Parser::ParseFrame_V0(
        Spectre::Engine::Parser *this,
        __int64 *a2,
        void *a3,
        _QWORD *a4)
{
  _QWORD *v4; // r15
  unsigned int v8; // esi
  __int64 v9; // rbx
  __int64 v10; // rdi
  __int64 v11; // rdx
  unsigned int v12; // r8d
  unsigned int *v13; // rcx
  unsigned __int8 v14; // r10
  char v15; // r8
  unsigned int v16; // edi
  __int64 v17; // rdx
  unsigned __int64 v18; // rcx
  unsigned __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // rdx
  unsigned int v22; // eax
  unsigned int v23; // edi
  __int64 v24; // rdx
  unsigned __int64 v25; // rcx
  unsigned __int64 v26; // r8
  __int64 v27; // rdx
  __int64 v28; // rdx
  unsigned int v29; // eax
  unsigned int v30; // eax
  __int64 v31; // rdx
  unsigned __int64 v32; // rdi
  unsigned __int64 v33; // rcx
  __int64 v34; // r15
  unsigned int v35; // eax
  __int64 v36; // rcx
  _QWORD *v37; // r9
  unsigned int v39; // edi
  __int64 v40; // rdx
  __int64 v41; // rcx
  unsigned int v42; // eax
  int v43; // [rsp+30h] [rbp-D0h]
  unsigned __int64 v44; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v45; // [rsp+48h] [rbp-B8h]
  unsigned __int64 v46; // [rsp+50h] [rbp-B0h]
  _BYTE v47[64]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v48[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v50[32]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v51[64]; // [rsp+120h] [rbp+20h] BYREF
  void *v52; // [rsp+160h] [rbp+60h]
  __int64 v53; // [rsp+168h] [rbp+68h]
  _BYTE v54[64]; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int64 v55; // [rsp+1B0h] [rbp+B0h] BYREF
  _QWORD *v56; // [rsp+1B8h] [rbp+B8h] BYREF
  void *v57; // [rsp+1C0h] [rbp+C0h] BYREF
  char v58[8]; // [rsp+1C8h] [rbp+C8h] BYREF
  char v59[8]; // [rsp+1D0h] [rbp+D0h] BYREF
  _DWORD v60[18]; // [rsp+1D8h] [rbp+D8h] BYREF

  v4 = a4;
  v56 = a4;
  v52 = a4;
  v8 = 0;
  v53 = 0;
  v9 = *a2;
  v10 = *(unsigned int *)(*a2 + 36);
  v43 = *(_DWORD *)(*a2 + 36);
  if ( *(_BYTE *)(*a2 + 12) )
  {
    std::string::string(&v44, "Parser: Compression not supported for frame data");
    Spectre::Utils::SpectreInvalidArgException::SpectreInvalidArgException(v47, &v44, 0);
    throw (Spectre::Utils::SpectreInvalidArgException *)v47;
  }
  v11 = *(unsigned __int16 *)(v9 + 42);
  if ( 4 * v11 >= (unsigned __int64)(v10 - 48) )
  {
    std::string::string(&v44, "Parser: Invalid Item Offset array size in Frame");
    Spectre::Utils::SpectreInvalidArgException::SpectreInvalidArgException(v47, &v44, 0);
    throw (Spectre::Utils::SpectreInvalidArgException *)v47;
  }
  v12 = 0;
  if ( (_DWORD)v11 )
  {
    v13 = (unsigned int *)(v9 + 44);
    do
    {
      if ( *v13 < (unsigned __int64)(4 * v11 + 44) )
      {
        std::string::string(&v44, "Parser: Item Offset underflow in Frame");
        Spectre::Utils::SpectreInvalidArgException::SpectreInvalidArgException(v47, &v44, 0);
        throw (Spectre::Utils::SpectreInvalidArgException *)v47;
      }
      ++v12;
      ++v13;
    }
    while ( v12 < (unsigned int)v11 );
  }
  v59[0] = *(_BYTE *)(v9 + 14);
  v14 = v59[0];
  if ( v59[0] && (unsigned int)(unsigned __int8)v59[0] - 1 > 1 )
  {
    std::string::string(&v44, "Parser: Invalid Quality Type for frame");
    Spectre::Utils::SpectreInvalidArgException::SpectreInvalidArgException(v47, &v44, 0);
    throw (Spectre::Utils::SpectreInvalidArgException *)v47;
  }
  v58[0] = *(_BYTE *)(v9 + 13);
  v15 = v58[0];
  switch ( v58[0] )
  {
    case 1:
      v16 = 0;
      if ( (_DWORD)v11 )
      {
        do
        {
          if ( v16 >= (unsigned __int16)v11 )
          {
            std::string::string(v47, "Frame::GetItemByIndex - Invalid index specified.");
            Spectre::Utils::SpectreException::SpectreException(pExceptionObject, v47, 0);
            throw (Spectre::Utils::SpectreException *)pExceptionObject;
          }
          v17 = *(unsigned int *)(v9 + 4LL * v16 + 44);
          if ( v17 + 16 > (unsigned __int64)*(unsigned int *)(v9 + 36) )
          {
            std::string::string(v50, "Frame::GetItemByIndex - Object outside bounds of frame. Bad data.");
            Spectre::Utils::SpectreException::SpectreException(v54, v50, 0);
            throw (Spectre::Utils::SpectreException *)v54;
          }
          v18 = v17 + v9;
          if ( !(v17 + v9) )
          {
            std::string::string(v48, "SafeBXFReader - NULL buffer");
            Spectre::Utils::SpectreInvalidArgException::SpectreInvalidArgException(v51, v48, 0);
            throw (Spectre::Utils::SpectreInvalidArgException *)v51;
          }
          v19 = a2[1];
          if ( v18 < v19 )
          {
            std::string::string(v48, "SafeBXFReader - child buffer is outside parent buffer");
            Spectre::Utils::SpectreInvalidArgException::SpectreInvalidArgException(v51, v48, 0);
            throw (Spectre::Utils::SpectreInvalidArgException *)v51;
          }
          v20 = a2[2];
          if ( v18 >= v20 + v19 )
          {
            std::string::string(v48, "SafeBXFReader - child buffer is outside parent buffer");
            Spectre::Utils::SpectreInvalidArgException::SpectreInvalidArgException(v51, v48, 0);
            throw (Spectre::Utils::SpectreInvalidArgException *)v51;
          }
          v21 = v20 - v18;
          if ( v21 + v19 < 0x10 )
          {
            std::string::string(v48, "SafeBXFReader - Sizeof Type exceeds buffer size");
            Spectre::Utils::SpectreInvalidArgException::SpectreInvalidArgException(v51, v48, 0);
            throw (Spectre::Utils::SpectreInvalidArgException *)v51;
          }
          v44 = v18;
          v45 = v18;
          v46 = v21 + v19;
          Spectre::Engine::Parser::ParseFrame_V0_MeshSegment(this, &v44, (__int64)a3);
          ++v16;
          v22 = *(unsigned __int16 *)(v9 + 42);
          v11 = (unsigned __int16)v22;
        }
        while ( v16 < v22 );
        v15 = v58[0];
        v14 = v59[0];
      }
      goto LABEL_19;
    case 2:
      v23 = 0;
      if ( !(_WORD)v11 )
        goto LABEL_19;
      do
      {
        if ( v23 >= (unsigned __int16)v11 )
        {
          std::string::string(v48, "Frame::GetItemByIndex - Invalid index specified.");
          Spectre::Utils::SpectreException::SpectreException(v51, v48, 0);
          throw (Spectre::Utils::SpectreException *)v51;
        }
        v24 = *(unsigned int *)(v9 + 4LL * v23 + 44);
        if ( v24 + 12 > (unsigned __int64)*(unsigned int *)(v9 + 36) )
        {
          std::string::string(v50, "Frame::GetItemByIndex - Object outside bounds of frame. Bad data.");
          Spectre::Utils::SpectreException::SpectreException(v54, v50, 0);
          throw (Spectre::Utils::SpectreException *)v54;
        }
        v25 = v24 + v9;
        if ( !(v24 + v9) )
        {
          std::string::string(v47, "SafeBXFReader - NULL buffer");
          Spectre::Utils::SpectreInvalidArgException::SpectreInvalidArgException(pExceptionObject, v47, 0);
          throw (Spectre::Utils::SpectreInvalidArgException *)pExceptionObject;
        }
        v26 = a2[1];
        if ( v25 < v26 )
        {
          std::string::string(v47, "SafeBXFReader - child buffer is outside parent buffer");
          Spectre::Utils::SpectreInvalidArgException::SpectreInvalidArgException(pExceptionObject, v47, 0);
          throw (Spectre::Utils::SpectreInvalidArgException *)pExceptionObject;
        }
        v27 = a2[2];
        if ( v25 >= v27 + v26 )
        {
          std::string::string(v47, "SafeBXFReader - child buffer is outside parent buffer");
          Spectre::Utils::SpectreInvalidArgException::SpectreInvalidArgException(pExceptionObject, v47, 0);
          throw (Spectre::Utils::SpectreInvalidArgException *)pExceptionObject;
        }
        v28 = v27 - v25;
        if ( v28 + v26 < 0xC )
        {
          std::string::string(v47, "SafeBXFReader - Sizeof Type exceeds buffer size");
          Spectre::Utils::SpectreInvalidArgException::SpectreInvalidArgException(pExceptionObject, v47, 0);
          throw (Spectre::Utils::SpectreInvalidArgException *)pExceptionObject;
        }
        v44 = v25;
        v45 = v25;
        v46 = v28 + v26;
        Spectre::Engine::Parser::ParseFrame_V0_AnimationSegment(this, &v44, a3);
        ++v23;
        v29 = *(unsigned __int16 *)(v9 + 42);
        v11 = (unsigned __int16)v29;
      }
      while ( v23 < v29 );
      v15 = v58[0];
      v14 = v59[0];
      LODWORD(v10) = v43;
      break;
    case 3:
      if ( (_WORD)v11 )
      {
        LOWORD(v30) = *(_WORD *)(v9 + 42);
        do
        {
          if ( v8 >= (unsigned __int16)v30 )
          {
            std::string::string(v48, "Frame::GetItemByIndex - Invalid index specified.");
            Spectre::Utils::SpectreException::SpectreException(v51, v48, 0);
            throw (Spectre::Utils::SpectreException *)v51;
          }
          v31 = *(unsigned int *)(v9 + 4LL * v8 + 44);
          if ( v31 + 36 > (unsigned __int64)*(unsigned int *)(v9 + 36) )
          {
            std::string::string(v50, "Frame::GetItemByIndex - Object outside bounds of frame. Bad data.");
            Spectre::Utils::SpectreException::SpectreException(v54, v50, 0);
            throw (Spectre::Utils::SpectreException *)v54;
          }
          v32 = v31 + v9;
          if ( !(v31 + v9) )
          {
            std::string::string(v47, "SafeBXFReader - NULL buffer");
            Spectre::Utils::SpectreInvalidArgException::SpectreInvalidArgException(pExceptionObject, v47, 0);
            throw (Spectre::Utils::SpectreInvalidArgException *)pExceptionObject;
          }
          v33 = a2[1];
          if ( v32 < v33 )
          {
            std::string::string(v47, "SafeBXFReader - child buffer is outside parent buffer");
            Spectre::Utils::SpectreInvalidArgException::SpectreInvalidArgException(pExceptionObject, v47, 0);
            throw (Spectre::Utils::SpectreInvalidArgException *)pExceptionObject;
          }
          v34 = a2[2];
          if ( v32 >= v34 + v33 )
          {
            std::string::string(v47, "SafeBXFReader - child buffer is outside parent buffer");
            Spectre::Utils::SpectreInvalidArgException::SpectreInvalidArgException(pExceptionObject, v47, 0);
            throw (Spectre::Utils::SpectreInvalidArgException *)pExceptionObject;
          }
          if ( v33 + v34 - v32 < 0x24 )
          {
            std::string::string(v47, "SafeBXFReader - Sizeof Type exceeds buffer size");
            Spectre::Utils::SpectreInvalidArgException::SpectreInvalidArgException(pExceptionObject, v47, 0);
            throw (Spectre::Utils::SpectreInvalidArgException *)pExceptionObject;
          }
          v44 = v31 + v9;
          v45 = v31 + v9;
          v46 = v33 + v34 - v32;
          if ( *(_DWORD *)v32 == 268443648 )
          {
            if ( *(_BYTE *)(v32 + 16) >= 7u )
            {
              std::string::string(v48, "Parser: Texture with invalid format");
              Spectre::Utils::SpectreInvalidArgException::SpectreInvalidArgException(v51, v48, 0);
              throw (Spectre::Utils::SpectreInvalidArgException *)v51;
            }
            if ( (*(_BYTE *)(v32 + 4) & 0xFC) != 0 )
            {
              std::string::string(v50, "Parser: Texture with invalid flags");
              Spectre::Utils::SpectreInvalidArgException::SpectreInvalidArgException(v54, v50, 0);
              throw (Spectre::Utils::SpectreInvalidArgException *)v54;
            }
            v35 = *(_DWORD *)(v32 + 32);
            if ( v35 < 0x24 )
            {
              std::string::string(v47, "Parser: TextureData offset underflow");
              Spectre::Utils::SpectreInvalidArgException::SpectreInvalidArgException(pExceptionObject, v47, 0);
              throw (Spectre::Utils::SpectreInvalidArgException *)pExceptionObject;
            }
            Spectre::Engine::SafeBXFReader<Spectre::Framework::MeshSegmentLittleEndian>::ValidateOffset(
              (__int64)&v44,
              v35);
            Spectre::Engine::SafeBXFReader<Spectre::Framework::MeshSegmentLittleEndian>::ValidateOffset(
              (__int64)&v44,
              (unsigned int)(*(_DWORD *)(v32 + 32) + *(_DWORD *)(v32 + 12)) - 36LL);
            v36 = *((_QWORD *)this + 15);
            if ( v36 )
            {
              v57 = a3;
              v60[0] = v34;
              v55 = v32;
              (*(void (__fastcall **)(__int64, unsigned __int64 *, _DWORD *, void **))(*(_QWORD *)v36 + 16LL))(
                v36,
                &v55,
                v60,
                &v57);
            }
          }
          else
          {
            Trace::LevelSettingsWrapper::Output(
              &gTraceLevelsParser,
              3,
              "Incorrect COOL format. Please update your COOL files");
          }
          ++v8;
          v30 = *(unsigned __int16 *)(v9 + 42);
        }
        while ( v8 < v30 );
        v4 = v56;
        v15 = v58[0];
        v14 = v59[0];
        LODWORD(v10) = v43;
      }
      break;
    case 4:
      v39 = 0;
      if ( (_WORD)v11 )
      {
        do
        {
          if ( v39 >= (unsigned __int16)v11 )
          {
            std::string::string(v47, "Frame::GetItemByIndex - Invalid index specified.");
            Spectre::Utils::SpectreException::SpectreException(pExceptionObject, v47, 0);
            throw (Spectre::Utils::SpectreException *)pExceptionObject;
          }
          v40 = *(unsigned int *)(v9 + 4LL * v39 + 44);
          if ( v40 + 92 > (unsigned __int64)*(unsigned int *)(v9 + 36) )
          {
            std::string::string(v47, "Frame::GetItemByIndex - Object outside bounds of frame. Bad data.");
            Spectre::Utils::SpectreException::SpectreException(pExceptionObject, v47, 0);
            throw (Spectre::Utils::SpectreException *)pExceptionObject;
          }
          if ( *(_DWORD *)(v9 + v40) == 268447744 )
          {
            v41 = *((_QWORD *)this + 23);
            if ( v41 )
            {
              v56 = a3;
              v60[0] = *((_DWORD *)a2 + 4);
              v55 = v9 + v40;
              (*(void (__fastcall **)(__int64, unsigned __int64 *, _DWORD *, _QWORD **))(*(_QWORD *)v41 + 16LL))(
                v41,
                &v55,
                v60,
                &v56);
            }
          }
          else
          {
            Trace::LevelSettingsWrapper::Output(
              &gTraceLevelsParser,
              3,
              "Incorrect COOL format. Please update your COOL files");
          }
          ++v39;
          v42 = *(unsigned __int16 *)(v9 + 42);
          v11 = (unsigned __int16)v42;
        }
        while ( v39 < v42 );
        v15 = v58[0];
        v14 = v59[0];
        LODWORD(v10) = v43;
      }
      else
      {
LABEL_19:
        LODWORD(v10) = v43;
      }
      break;
    case 5:
      break;
    case 6:
      Spectre::Engine::Parser::ParseFrame_V0_SceneSegment(
        this,
        (const struct Spectre::Framework::FrameLittleEndian *)v9,
        *((_DWORD *)a2 + 4),
        a3);
      v15 = v58[0];
      v14 = v59[0];
      break;
    default:
      std::string::string(v47, "Parser: Invalid Frame Type");
      Spectre::Utils::SpectreInvalidArgException::SpectreInvalidArgException(pExceptionObject, v47, 0);
      throw (Spectre::Utils::SpectreInvalidArgException *)pExceptionObject;
  }
  v37 = (_QWORD *)v4[7];
  if ( v37 )
  {
    v59[0] = v14;
    v58[0] = v15;
    (*(void (__fastcall **)(_QWORD *, char *, char *))(*v37 + 16LL))(v37, v58, v59);
    v37 = (_QWORD *)v4[7];
  }
  if ( v37 )
  {
    LOBYTE(v11) = v37 != v4;
    (*(void (__fastcall **)(_QWORD *, __int64))(*v37 + 32LL))(v37, v11);
    v4[7] = 0;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1804c19d0  push    rbp
0x1804c19d2  push    rbx
0x1804c19d3  push    rsi
0x1804c19d4  push    rdi
0x1804c19d5  push    r12
0x1804c19d7  push    r13
0x1804c19d9  push    r14
0x1804c19db  push    r15
0x1804c19dd  lea     rbp, [rsp-0E8h]
0x1804c19e5  sub     rsp, 1E8h
0x1804c19ec  mov     r15, r9
0x1804c19ef  mov     [rbp+120h+var_68], r9
0x1804c19f6  mov     r12, r8
0x1804c19f9  mov     r14, rdx
0x1804c19fc  mov     r13, rcx
0x1804c19ff  mov     [rbp+120h+var_C0], r9
0x1804c1a03  xor     esi, esi
0x1804c1a05  mov     [rbp+120h+var_B8], rsi
0x1804c1a09  mov     rbx, [rdx]
0x1804c1a0c  mov     edi, [rbx+24h]
0x1804c1a0f  mov     [rsp+220h+var_1F0], edi
0x1804c1a13  cmp     [rbx+0Ch], sil
0x1804c1a17  jnz     loc_1804C1F27
0x1804c1a1d  movzx   edx, word ptr [rbx+2Ah]
0x1804c1a21  mov     ecx, edx
0x1804c1a23  shl     rcx, 2
0x1804c1a27  lea     rax, [rdi-30h]
0x1804c1a2b  cmp     rcx, rax
0x1804c1a2e  jnb     loc_1804C1F5D
0x1804c1a34  mov     r8d, esi
0x1804c1a37  test    edx, edx
0x1804c1a39  jz      short loc_1804C1A5A
0x1804c1a3b  lea     r10, [rcx+2Ch]
0x1804c1a3f  lea     rcx, [rbx+2Ch]
0x1804c1a43  mov     eax, [rcx]
0x1804c1a45  cmp     rax, r10
0x1804c1a48  jb      loc_1804C1FC9
0x1804c1a4e  inc     r8d
0x1804c1a51  add     rcx, 4
0x1804c1a55  cmp     r8d, edx
0x1804c1a58  jb      short loc_1804C1A43
0x1804c1a5a  movzx   r10d, byte ptr [rbx+0Eh]
0x1804c1a5f  mov     [rbp+120h+var_50], r10b
0x1804c1a66  mov     ecx, r10d
0x1804c1a69  test    r10b, r10b
0x1804c1a6c  jz      short loc_1804C1A7C
0x1804c1a6e  sub     ecx, 1
0x1804c1a71  jz      short loc_1804C1A7C
0x1804c1a73  cmp     ecx, 1
0x1804c1a76  jnz     loc_1804C1F93
0x1804c1a7c  movzx   r8d, byte ptr [rbx+0Dh]
0x1804c1a81  mov     [rbp+120h+var_58], r8b
0x1804c1a88  lea     eax, [r8-1]; switch 6 cases
0x1804c1a8c  cmp     eax, 5
0x1804c1a8f  ja      def_1804C1AA9; jumptable 00000001804C1AA9 default case
0x1804c1a95  cdqe
0x1804c1a97  lea     r11, __ImageBase
0x1804c1a9e  mov     ecx, ds:(jpt_1804C1AA9 - 180000000h)[r11+rax*4]
0x1804c1aa6  add     rcx, r11
0x1804c1aa9  jmp     rcx; switch jump
0x1804c1aab  mov     edi, esi; jumptable 00000001804C1AA9 case 1
0x1804c1aad  test    edx, edx
0x1804c1aaf  jz      loc_1804C1B52
0x1804c1ab5  movzx   eax, dx
0x1804c1ab8  cmp     edi, eax
0x1804c1aba  jnb     loc_1804C20F9
0x1804c1ac0  mov     eax, edi
0x1804c1ac2  mov     edx, [rbx+rax*4+2Ch]
0x1804c1ac6  mov     ecx, [rbx+24h]
0x1804c1ac9  lea     rax, [rdx+10h]
0x1804c1acd  cmp     rax, rcx
0x1804c1ad0  ja      loc_1804C20C7
0x1804c1ad6  lea     rcx, [rdx+rbx]
0x1804c1ada  test    rcx, rcx
0x1804c1add  jz      loc_1804C2095
0x1804c1ae3  mov     r8, [r14+8]
0x1804c1ae7  cmp     rcx, r8
0x1804c1aea  jb      loc_1804C2063
0x1804c1af0  mov     rdx, [r14+10h]
0x1804c1af4  lea     rax, [rdx+r8]
0x1804c1af8  cmp     rcx, rax
0x1804c1afb  jnb     loc_1804C2031
0x1804c1b01  sub     rdx, rcx
0x1804c1b04  lea     rax, [rdx+r8]
0x1804c1b08  cmp     rax, 10h
0x1804c1b0c  jb      loc_1804C1FFF
0x1804c1b12  mov     [rsp+220h+var_1E0], rcx
0x1804c1b17  mov     [rsp+220h+var_1D8], rcx
0x1804c1b1c  mov     [rsp+220h+var_1D0], rax
0x1804c1b21  mov     r8, r12
0x1804c1b24  lea     rdx, [rsp+220h+var_1E0]
0x1804c1b29  mov     rcx, r13
0x1804c1b2c  call    ?ParseFrame_V0_MeshSegment@Parser@Engine@Spectre@@IEAAXV?$SafeBXFReader@UMeshBaseSegment@Framework@Spectre@@@23@PEAX@Z; Spectre::Engine::Parser::ParseFrame_V0_MeshSegment(Spectre::Engine::SafeBXFReader<Spectre::Framework::MeshBaseSegment>,void *)
0x1804c1b31  inc     edi
0x1804c1b33  movzx   eax, word ptr [rbx+2Ah]
0x1804c1b37  movzx   edx, ax
0x1804c1b3a  cmp     edi, eax
0x1804c1b3c  jb      loc_1804C1AB5
0x1804c1b42  movzx   r8d, [rbp+120h+var_58]
0x1804c1b4a  movzx   r10d, [rbp+120h+var_50]
0x1804c1b52  mov     edi, [rsp+220h+var_1F0]
0x1804c1b56  jmp     loc_1804C1D5E; jumptable 00000001804C1AA9 case 5
0x1804c1b5b  mov     edi, esi; jumptable 00000001804C1AA9 case 2
0x1804c1b5d  cmp     si, dx
0x1804c1b60  jnb     short loc_1804C1B52
0x1804c1b62  movzx   eax, dx
0x1804c1b65  cmp     edi, eax
0x1804c1b67  jnb     loc_1804C222F
0x1804c1b6d  mov     eax, edi
0x1804c1b6f  mov     edx, [rbx+rax*4+2Ch]
0x1804c1b73  mov     ecx, [rbx+24h]
0x1804c1b76  lea     rax, [rdx+0Ch]
0x1804c1b7a  cmp     rax, rcx
0x1804c1b7d  ja      loc_1804C21FD
0x1804c1b83  lea     rcx, [rdx+rbx]
0x1804c1b87  test    rcx, rcx
0x1804c1b8a  jz      loc_1804C21C9
0x1804c1b90  mov     r8, [r14+8]
0x1804c1b94  cmp     rcx, r8
0x1804c1b97  jb      loc_1804C2195
0x1804c1b9d  mov     rdx, [r14+10h]
0x1804c1ba1  lea     rax, [rdx+r8]
0x1804c1ba5  cmp     rcx, rax
0x1804c1ba8  jnb     loc_1804C2161
0x1804c1bae  sub     rdx, rcx
0x1804c1bb1  lea     rax, [rdx+r8]
0x1804c1bb5  cmp     rax, 0Ch
0x1804c1bb9  jb      loc_1804C212D
0x1804c1bbf  mov     [rsp+220h+var_1E0], rcx
0x1804c1bc4  mov     [rsp+220h+var_1D8], rcx
0x1804c1bc9  mov     [rsp+220h+var_1D0], rax
0x1804c1bce  mov     r8, r12
0x1804c1bd1  lea     rdx, [rsp+220h+var_1E0]
0x1804c1bd6  mov     rcx, r13
0x1804c1bd9  call    ?ParseFrame_V0_AnimationSegment@Parser@Engine@Spectre@@IEAAXV?$SafeBXFReader@UAnimationHeader@Framework@Spectre@@@23@PEAX@Z; Spectre::Engine::Parser::ParseFrame_V0_AnimationSegment(Spectre::Engine::SafeBXFReader<Spectre::Framework::AnimationHeader>,void *)
0x1804c1bde  inc     edi
0x1804c1be0  movzx   eax, word ptr [rbx+2Ah]
0x1804c1be4  movzx   edx, ax
0x1804c1be7  cmp     edi, eax
0x1804c1be9  jb      loc_1804C1B62
0x1804c1bef  movzx   r8d, [rbp+120h+var_58]
0x1804c1bf7  movzx   r10d, [rbp+120h+var_50]
0x1804c1bff  mov     edi, [rsp+220h+var_1F0]
0x1804c1c03  jmp     loc_1804C1D5E; jumptable 00000001804C1AA9 case 5
0x1804c1c08  xor     eax, eax; jumptable 00000001804C1AA9 case 3
0x1804c1c0a  cmp     ax, dx
0x1804c1c0d  jnb     loc_1804C1D5C
0x1804c1c13  movzx   eax, word ptr [rbx+2Ah]
0x1804c1c17  nop     word ptr [rax+rax+00000000h]
0x1804c1c20  movzx   eax, ax
0x1804c1c23  cmp     esi, eax
0x1804c1c25  jnb     loc_1804C23FB
0x1804c1c2b  mov     eax, esi
0x1804c1c2d  mov     edx, [rbx+rax*4+2Ch]
0x1804c1c31  mov     ecx, [rbx+24h]
0x1804c1c34  lea     rax, [rdx+24h]
0x1804c1c38  cmp     rax, rcx
0x1804c1c3b  ja      loc_1804C23C9
0x1804c1c41  lea     rdi, [rdx+rbx]
0x1804c1c45  test    rdi, rdi
0x1804c1c48  jz      loc_1804C2395
0x1804c1c4e  mov     rcx, [r14+8]
0x1804c1c52  cmp     rdi, rcx
0x1804c1c55  jb      loc_1804C2361
0x1804c1c5b  mov     r15, [r14+10h]
0x1804c1c5f  lea     rax, [r15+rcx]
0x1804c1c63  cmp     rdi, rax
0x1804c1c66  jnb     loc_1804C232D
0x1804c1c6c  mov     rdx, r15
0x1804c1c6f  sub     rdx, rdi
0x1804c1c72  add     rdx, rcx
0x1804c1c75  cmp     rdx, 24h ; '$'
0x1804c1c79  jb      loc_1804C22F9
0x1804c1c7f  mov     [rsp+220h+var_1E0], rdi
0x1804c1c84  mov     [rsp+220h+var_1D8], rdi
0x1804c1c89  mov     [rsp+220h+var_1D0], rdx
0x1804c1c8e  cmp     dword ptr [rdi], 10002000h
0x1804c1c94  jz      short loc_1804C1CB3
0x1804c1c96  lea     r8, aIncorrectCoolF; "Incorrect COOL format. Please update yo"...
0x1804c1c9d  mov     edx, 3
0x1804c1ca2  lea     rcx, ?gTraceLevelsParser@@3ULevelSettingsWrapper@Trace@@A; Trace::LevelSettingsWrapper gTraceLevelsParser
0x1804c1ca9  call    ?Output@LevelSettingsWrapper@Trace@@QEAAXW4Level@2@PEBDZZ; Trace::LevelSettingsWrapper::Output(Trace::Level,char const *,...)
0x1804c1cae  jmp     loc_1804C1D33
0x1804c1cb3  cmp     byte ptr [rdi+10h], 7
0x1804c1cb7  jnb     loc_1804C22C7
0x1804c1cbd  test    byte ptr [rdi+4], 0FCh
0x1804c1cc1  jnz     loc_1804C2295
0x1804c1cc7  mov     eax, [rdi+20h]
0x1804c1cca  cmp     eax, 24h ; '$'
0x1804c1ccd  jb      loc_1804C2261
0x1804c1cd3  mov     edx, eax
0x1804c1cd5  lea     rcx, [rsp+220h+var_1E0]
0x1804c1cda  call    ?ValidateOffset@?$SafeBXFReader@UMeshSegmentLittleEndian@Framework@Spectre@@@Engine@Spectre@@QEBAX_K@Z; Spectre::Engine::SafeBXFReader<Spectre::Framework::MeshSegmentLittleEndian>::ValidateOffset(unsigned __int64)
0x1804c1cdf  mov     edx, [rdi+0Ch]
0x1804c1ce2  add     edx, [rdi+20h]
0x1804c1ce5  sub     rdx, 24h ; '$'
0x1804c1ce9  lea     rcx, [rsp+220h+var_1E0]
0x1804c1cee  call    ?ValidateOffset@?$SafeBXFReader@UMeshSegmentLittleEndian@Framework@Spectre@@@Engine@Spectre@@QEBAX_K@Z; Spectre::Engine::SafeBXFReader<Spectre::Framework::MeshSegmentLittleEndian>::ValidateOffset(unsigned __int64)
0x1804c1cf3  mov     rcx, [r13+78h]
0x1804c1cf7  test    rcx, rcx
0x1804c1cfa  jz      short loc_1804C1D33
0x1804c1cfc  mov     [rbp+120h+var_60], r12
0x1804c1d03  mov     [rbp+120h+var_48], r15d
0x1804c1d0a  mov     [rbp+120h+var_70], rdi
0x1804c1d11  mov     rax, [rcx]
0x1804c1d14  lea     r9, [rbp+120h+var_60]
0x1804c1d1b  lea     r8, [rbp+120h+var_48]
0x1804c1d22  lea     rdx, [rbp+120h+var_70]
0x1804c1d29  mov     rax, [rax+10h]
0x1804c1d2d  call    cs:__guard_dispatch_icall_fptr
0x1804c1d33  inc     esi
0x1804c1d35  movzx   eax, word ptr [rbx+2Ah]
0x1804c1d39  cmp     esi, eax
0x1804c1d3b  jb      loc_1804C1C20
0x1804c1d41  mov     r15, [rbp+120h+var_68]
0x1804c1d48  movzx   r8d, [rbp+120h+var_58]
0x1804c1d50  movzx   r10d, [rbp+120h+var_50]
0x1804c1d58  mov     edi, [rsp+220h+var_1F0]
0x1804c1d5c  xor     esi, esi
0x1804c1d5e  mov     r9, [r15+38h]; jumptable 00000001804C1AA9 case 5
0x1804c1d62  test    r9, r9
0x1804c1d65  jz      short loc_1804C1D97
0x1804c1d67  mov     [rbp+120h+var_50], r10b
0x1804c1d6e  mov     [rbp+120h+var_58], r8b
0x1804c1d75  mov     rax, [r9]
0x1804c1d78  lea     r8, [rbp+120h+var_50]
0x1804c1d7f  lea     rdx, [rbp+120h+var_58]
0x1804c1d86  mov     rcx, r9
0x1804c1d89  mov     rax, [rax+10h]
0x1804c1d8d  call    cs:__guard_dispatch_icall_fptr
0x1804c1d93  mov     r9, [r15+38h]
0x1804c1d97  test    r9, r9
0x1804c1d9a  jz      short loc_1804C1DB6
0x1804c1d9c  mov     rcx, [r9]
0x1804c1d9f  cmp     r9, r15
0x1804c1da2  setnz   dl
0x1804c1da5  mov     rax, [rcx+20h]
0x1804c1da9  mov     rcx, r9
0x1804c1dac  call    cs:__guard_dispatch_icall_fptr
0x1804c1db2  mov     [r15+38h], rsi
0x1804c1db6  mov     eax, edi
0x1804c1db8  add     rsp, 1E8h
0x1804c1dbf  pop     r15
0x1804c1dc1  pop     r14
0x1804c1dc3  pop     r13
0x1804c1dc5  pop     r12
0x1804c1dc7  pop     rdi
0x1804c1dc8  pop     rsi
0x1804c1dc9  pop     rbx
0x1804c1dca  pop     rbp
0x1804c1dcb  retn
0x1804c1dcc  mov     edi, esi; jumptable 00000001804C1AA9 case 4
0x1804c1dce  cmp     si, dx
0x1804c1dd1  jnb     loc_1804C1B52
0x1804c1dd7  nop     word ptr [rax+rax+00000000h]
0x1804c1de0  movzx   eax, dx
0x1804c1de3  cmp     edi, eax
0x1804c1de5  jnb     loc_1804C1EBF
0x1804c1deb  mov     eax, edi
0x1804c1ded  mov     edx, [rbx+rax*4+2Ch]
0x1804c1df1  mov     ecx, [rbx+24h]
0x1804c1df4  lea     rax, [rdx+5Ch]
0x1804c1df8  cmp     rax, rcx
0x1804c1dfb  ja      loc_1804C242D
0x1804c1e01  lea     r8, [rbx+rdx]
0x1804c1e05  cmp     dword ptr [r8], 10003000h
0x1804c1e0c  jz      short loc_1804C1E28
0x1804c1e0e  lea     r8, aIncorrectCoolF; "Incorrect COOL format. Please update yo"...
0x1804c1e15  mov     edx, 3
0x1804c1e1a  lea     rcx, ?gTraceLevelsParser@@3ULevelSettingsWrapper@Trace@@A; Trace::LevelSettingsWrapper gTraceLevelsParser
0x1804c1e21  call    ?Output@LevelSettingsWrapper@Trace@@QEAAXW4Level@2@PEBDZZ; Trace::LevelSettingsWrapper::Output(Trace::Level,char const *,...)
0x1804c1e26  jmp     short loc_1804C1E6E
0x1804c1e28  mov     rcx, [r13+0B8h]
0x1804c1e2f  test    rcx, rcx
0x1804c1e32  jz      short loc_1804C1E6E
0x1804c1e34  mov     [rbp+120h+var_68], r12
0x1804c1e3b  mov     eax, [r14+10h]
0x1804c1e3f  mov     [rbp+120h+var_48], eax
0x1804c1e45  mov     [rbp+120h+var_70], r8
0x1804c1e4c  mov     rax, [rcx]
0x1804c1e4f  lea     r9, [rbp+120h+var_68]
0x1804c1e56  lea     r8, [rbp+120h+var_48]
0x1804c1e5d  lea     rdx, [rbp+120h+var_70]
0x1804c1e64  mov     rax, [rax+10h]
0x1804c1e68  call    cs:__guard_dispatch_icall_fptr
0x1804c1e6e  inc     edi
0x1804c1e70  movzx   eax, word ptr [rbx+2Ah]
0x1804c1e74  movzx   edx, ax
0x1804c1e77  cmp     edi, eax
0x1804c1e79  jb      loc_1804C1DE0
0x1804c1e7f  movzx   r8d, [rbp+120h+var_58]
0x1804c1e87  movzx   r10d, [rbp+120h+var_50]
0x1804c1e8f  mov     edi, [rsp+220h+var_1F0]
0x1804c1e93  jmp     loc_1804C1D5E; jumptable 00000001804C1AA9 case 5
0x1804c1e98  mov     r9, r12; jumptable 00000001804C1AA9 case 6
0x1804c1e9b  mov     r8d, [r14+10h]; unsigned int
0x1804c1e9f  mov     rdx, rbx; struct Spectre::Framework::FrameLittleEndian *
0x1804c1ea2  mov     rcx, r13; this
0x1804c1ea5  call    ?ParseFrame_V0_SceneSegment@Parser@Engine@Spectre@@IEAAXPEBUFrameLittleEndian@Framework@3@IPEAX@Z; Spectre::Engine::Parser::ParseFrame_V0_SceneSegment(Spectre::Framework::FrameLittleEndian const *,uint,void *)
0x1804c1eaa  movzx   r8d, [rbp+120h+var_58]
  ... truncated ...
```
