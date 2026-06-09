# CacNx::SurfaceDifferencerX11::init(void)

- ea: `0x18006db10`
- end: `0x18006e20c`
- name: `?init@SurfaceDifferencerX11@CacNx@@AEAAJXZ`
- size: `1788`
- prototype: `__int64 __fastcall(CacNx::SurfaceDifferencerX11 *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18006cfd8`

## callees

- `0x180006580`
- `0x1800065a4`
- `0x180006994`
- `0x180007018`
- `0x18006a898`
- `0x18006db10`
- `0x18006e214`
- `0x180070c34`
- `0x180089010`

## string_xrefs

- `0x18006dd67`: `"CreateVertexShader failed"`
- `0x18006dc91`: `"CreateBuffer failed"`
- `0x18006de06`: `"CreateInputLayout failed"`
- `0x18006dece`: `"CreatePixelShader failed: PsDifferFirst"`
- `0x18006de6a`: `"CreateGeometryShader failed"`
- `0x18006e123`: `"CreateTexture2D failed"`
- `0x18006df32`: `"CreatePixelShader failed: PsDifferNext"`
- `0x18006e0bf`: `"CreateRenderTargetView failed"`
- `0x18006e0f1`: `"CreateShaderResourceView failed"`

## pseudocode

```c
__int64 __fastcall CacNx::SurfaceDifferencerX11::init(CacNx::SurfaceDifferencerX11 *this)
{
  int v2; // r15d
  unsigned int v3; // ecx
  unsigned int v4; // r9d
  unsigned int v5; // r8d
  int v6; // eax
  unsigned int v7; // edi
  int v8; // edi
  __int64 v9; // rcx
  int v10; // eax
  _QWORD *v11; // rcx
  int v12; // edx
  const wchar_t *v13; // r9
  __int64 v14; // rcx
  __int64 v15; // rcx
  int v16; // r12d
  unsigned int v17; // ebx
  __int64 v18; // rcx
  int v19; // r14d
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rcx
  void *v25; // rax
  __int64 v27; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v28; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v29; // [rsp+50h] [rbp-B0h] BYREF
  void *Block; // [rsp+58h] [rbp-A8h]
  _QWORD v31[2]; // [rsp+60h] [rbp-A0h] BYREF
  const char *v32; // [rsp+70h] [rbp-90h] BYREF
  int v33; // [rsp+78h] [rbp-88h]
  __int64 v34; // [rsp+7Ch] [rbp-84h]
  __int64 v35; // [rsp+84h] [rbp-7Ch]
  int v36; // [rsp+8Ch] [rbp-74h]
  const char *v37; // [rsp+90h] [rbp-70h]
  int v38; // [rsp+98h] [rbp-68h]
  __int64 v39; // [rsp+9Ch] [rbp-64h]
  __int64 v40; // [rsp+A4h] [rbp-5Ch]
  int v41; // [rsp+ACh] [rbp-54h]
  int v42; // [rsp+B0h] [rbp-50h] BYREF
  int v43; // [rsp+B4h] [rbp-4Ch]
  int v44; // [rsp+B8h] [rbp-48h]
  int v45; // [rsp+BCh] [rbp-44h]
  int v46; // [rsp+C0h] [rbp-40h]
  __int64 v47; // [rsp+C4h] [rbp-3Ch]
  _BYTE v48[12]; // [rsp+CCh] [rbp-34h]
  int v49; // [rsp+D8h] [rbp-28h]
  _DWORD v50[4]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v51; // [rsp+F0h] [rbp-10h]
  _QWORD v52[3]; // [rsp+F8h] [rbp-8h] BYREF

  *((_DWORD *)this + 24) = 1065353216;
  v2 = 0;
  *(_QWORD *)((char *)this + 84) = 0;
  *((_DWORD *)this + 23) = 0;
  *(_QWORD *)((char *)this + 76) = 0;
  v3 = *((_DWORD *)this + 14);
  v4 = (v3 + *((_DWORD *)this + 12) - 1) / v3;
  *((_DWORD *)this + 15) = v4;
  *((_DWORD *)this + 16) = (v3 + *((_DWORD *)this + 13) - 1) / v3;
  v5 = *((_DWORD *)this + 14);
  *((_DWORD *)this + 18) = *((_DWORD *)this + 16) * v5;
  *((_DWORD *)this + 17) = v5 * v4;
  v6 = CacNx::TileMap::Init(
         (CacNx::SurfaceDifferencerX11 *)((char *)this + 248),
         (const struct tagPOINT *)((char *)this + 68),
         v5);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v8 = *((_DWORD *)this + 15) * *((_DWORD *)this + 16);
    Block = operator new(saturated_mul(v8, 0x10u));
    memset_0(Block, 0, 16LL * v8);
    v9 = *((_QWORD *)this + 4);
    v51 = 0;
    v50[1] = 2;
    v50[2] = 1;
    v50[3] = 0x10000;
    v31[0] = Block;
    v31[1] = 0;
    v50[0] = 16 * v8;
    v10 = (*(__int64 (__fastcall **)(__int64, _DWORD *, _QWORD *, char *))(*(_QWORD *)v9 + 24LL))(
            v9,
            v50,
            v31,
            (char *)this + 104);
    v7 = v10;
    if ( v10 >= 0 )
    {
      v14 = *((_QWORD *)this + 4);
      v52[2] = 0;
      v52[0] = 32;
      v52[1] = 4;
      v10 = (*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD, char *))(*(_QWORD *)v14 + 24LL))(
              v14,
              v52,
              0,
              (char *)this + 112);
      v7 = v10;
      if ( v10 >= 0 )
      {
        v10 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64, _QWORD, char *))(**((_QWORD **)this + 4) + 96LL))(
                *((_QWORD *)this + 4),
                qword_18009E6C0,
                512,
                0,
                (char *)this + 128);
        v7 = v10;
        if ( v10 >= 0 )
        {
          v15 = *((_QWORD *)this + 4);
          v32 = "TEXCOORD";
          v37 = "TEXCOORD";
          v33 = 0;
          v34 = 18;
          v35 = 0;
          v36 = 0;
          v38 = 1;
          v39 = 18;
          v40 = 8;
          v41 = 0;
          v10 = (*(__int64 (__fastcall **)(__int64, const char **, __int64, __int64 *, __int64, char *))(*(_QWORD *)v15 + 88LL))(
                  v15,
                  &v32,
                  2,
                  qword_18009E6C0,
                  512,
                  (char *)this + 120);
          v7 = v10;
          if ( v10 >= 0 )
          {
            v10 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64, _QWORD, char *))(**((_QWORD **)this + 4) + 104LL))(
                    *((_QWORD *)this + 4),
                    qword_18009E8D0,
                    1684,
                    0,
                    (char *)this + 136);
            v7 = v10;
            if ( v10 >= 0 )
            {
              v10 = (*(__int64 (__fastcall **)(_QWORD, void *, __int64, _QWORD, char *))(**((_QWORD **)this + 4) + 120LL))(
                      *((_QWORD *)this + 4),
                      &unk_18009EF70,
                      1880,
                      0,
                      (char *)this + 144);
              v7 = v10;
              if ( v10 >= 0 )
              {
                v10 = (*(__int64 (__fastcall **)(_QWORD, void *, __int64, _QWORD, char *))(**((_QWORD **)this + 4)
                                                                                         + 120LL))(
                        *((_QWORD *)this + 4),
                        &unk_18009F6D0,
                        1192,
                        0,
                        (char *)this + 152);
                v7 = v10;
                if ( v10 >= 0 )
                {
                  v44 = 1;
                  v16 = 0;
                  v45 = 1;
                  v47 = 1;
                  v17 = *((_DWORD *)this + 14);
                  v46 = 42;
                  *(_DWORD *)v48 = 0;
                  *(_QWORD *)&v48[4] = 40;
                  v49 = 0;
                  if ( v17 >= 2 )
                  {
                    while ( 1 )
                    {
                      v18 = *((_QWORD *)this + 4);
                      v17 >>= 1;
                      v27 = 0;
                      v19 = *((_DWORD *)this + 15) * v17;
                      v2 = *((_DWORD *)this + 16) * v17;
                      v42 = v19;
                      v43 = v2;
                      v10 = (*(__int64 (__fastcall **)(__int64, int *, _QWORD, __int64 *))(*(_QWORD *)v18 + 40LL))(
                              v18,
                              &v42,
                              0,
                              &v27);
                      v7 = v10;
                      if ( v10 < 0 )
                        break;
                      CacNx::TDynamicArrayBase<ID3D11Texture2D *,CacNx::TCntPtr<ID3D11Texture2D>>::push_back(
                        (char *)this + 160,
                        v27);
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
                      v20 = *((_QWORD *)this + 4);
                      v21 = *((_QWORD *)this + 21);
                      v28 = 0;
                      v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v20 + 56LL))(
                              v20,
                              *(_QWORD *)(v21 + 8LL * v16),
                              0,
                              &v28);
                      v7 = v10;
                      if ( v10 < 0 )
                      {
                        v11 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                        {
                          v12 = 23;
                          v13 = L"\"CreateShaderResourceView failed\"";
                          goto LABEL_10;
                        }
                        goto LABEL_57;
                      }
                      CacNx::TDynamicArrayBase<ID3D11Texture2D *,CacNx::TCntPtr<ID3D11Texture2D>>::push_back(
                        (char *)this + 184,
                        v28);
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
                      v22 = *((_QWORD *)this + 4);
                      v23 = *((_QWORD *)this + 21);
                      v29 = 0;
                      v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v22 + 72LL))(
                              v22,
                              *(_QWORD *)(v23 + 8LL * v16),
                              0,
                              &v29);
                      v7 = v10;
                      if ( v10 < 0 )
                      {
                        v11 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                        {
                          v12 = 24;
                          v13 = L"\"CreateRenderTargetView failed\"";
                          goto LABEL_10;
                        }
                        goto LABEL_57;
                      }
                      CacNx::TDynamicArrayBase<ID3D11Texture2D *,CacNx::TCntPtr<ID3D11Texture2D>>::push_back(
                        (char *)this + 208,
                        v29);
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
                      ++v16;
                      if ( v17 < 2 )
                        goto LABEL_52;
                    }
                    v11 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                    {
                      v12 = 22;
                      goto LABEL_50;
                    }
                    goto LABEL_57;
                  }
                  v19 = 0;
LABEL_52:
                  v24 = *((_QWORD *)this + 4);
                  *((_DWORD *)this + 60) = v16;
                  *(_QWORD *)v48 = 3;
                  *(_DWORD *)&v48[8] = 0x20000;
                  v42 = v19;
                  v43 = v2;
                  v10 = (*(__int64 (__fastcall **)(__int64, int *, _QWORD, char *))(*(_QWORD *)v24 + 40LL))(
                          v24,
                          &v42,
                          0,
                          (char *)this + 232);
                  v7 = v10;
                  if ( v10 >= 0 )
                  {
                    v25 = operator new(saturated_mul((unsigned int)(v19 * v2), 4u));
                    *((_QWORD *)this + 38) = v25;
                    memset_0(v25, 255, 4LL * (unsigned int)(v19 * v2));
                    *((_DWORD *)this + 74) = v19;
                    *((_DWORD *)this + 75) = v2;
                    goto LABEL_57;
                  }
                  v11 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
                    goto LABEL_57;
                  v12 = 25;
LABEL_50:
                  v13 = L"\"CreateTexture2D failed\"";
                }
                else
                {
                  v11 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
                    goto LABEL_57;
                  v12 = 21;
                  v13 = L"\"CreatePixelShader failed: PsDifferNext\"";
                }
              }
              else
              {
                v11 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
                  goto LABEL_57;
                v12 = 20;
                v13 = L"\"CreatePixelShader failed: PsDifferFirst\"";
              }
            }
            else
            {
              v11 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
                goto LABEL_57;
              v12 = 19;
              v13 = L"\"CreateGeometryShader failed\"";
            }
          }
          else
          {
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
              goto LABEL_57;
            v12 = 18;
            v13 = L"\"CreateInputLayout failed\"";
          }
        }
        else
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
            goto LABEL_57;
          v12 = 17;
          v13 = L"\"CreateVertexShader failed\"";
        }
LABEL_10:
        WPP_SF_Sd(v11[2], v12, (unsigned int)WPP_d7b9b1f3ce2935a14401eef6738845c5_Traceguids, (_DWORD)v13, v10);
LABEL_57:
        operator delete(Block);
        return v7;
      }
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_57;
      v12 = 16;
    }
    else
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_57;
      v12 = 15;
    }
    v13 = L"\"CreateBuffer failed\"";
    goto LABEL_10;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      (unsigned int)WPP_d7b9b1f3ce2935a14401eef6738845c5_Traceguids,
      (unsigned int)L"\"TileMap init failed\"",
      v6);
  return v7;
}

```

## disassembly

```asm
0x18006db10  push    rbp
0x18006db12  push    rbx
0x18006db13  push    rsi
0x18006db14  push    rdi
0x18006db15  push    r12
0x18006db17  push    r13
0x18006db19  push    r14
0x18006db1b  push    r15
0x18006db1d  lea     rbp, [rsp-28h]
0x18006db22  sub     rsp, 128h
0x18006db29  mov     rax, cs:__security_cookie
0x18006db30  xor     rax, rsp
0x18006db33  mov     [rbp+60h+var_50], rax
0x18006db37  mov     rsi, rcx
0x18006db3a  mov     dword ptr [rcx+60h], 3F800000h
0x18006db41  xor     edx, edx
0x18006db43  xor     r15d, r15d
0x18006db46  mov     [rcx+54h], r15
0x18006db4a  mov     [rcx+5Ch], r15d
0x18006db4e  mov     [rcx+4Ch], r15
0x18006db52  mov     ecx, [rcx+38h]
0x18006db55  mov     eax, [rsi+30h]
0x18006db58  dec     eax
0x18006db5a  add     eax, ecx
0x18006db5c  div     ecx
0x18006db5e  xor     edx, edx
0x18006db60  mov     r9d, eax
0x18006db63  mov     [rsi+3Ch], eax
0x18006db66  mov     eax, [rsi+34h]
0x18006db69  dec     eax
0x18006db6b  add     eax, ecx
0x18006db6d  div     ecx
0x18006db6f  lea     rdx, [rsi+44h]; struct tagPOINT *
0x18006db73  mov     [rsi+40h], eax
0x18006db76  lea     rcx, [rsi+0F8h]; this
0x18006db7d  mov     r8d, [rsi+38h]; unsigned int
0x18006db81  mov     eax, r8d
0x18006db84  imul    eax, [rsi+40h]
0x18006db88  imul    r9d, r8d
0x18006db8c  mov     [rsi+48h], eax
0x18006db8f  mov     [rdx], r9d
0x18006db92  call    ?Init@TileMap@CacNx@@QEAAJAEBUtagPOINT@@I@Z; CacNx::TileMap::Init(tagPOINT const &,uint)
0x18006db97  mov     edi, eax
0x18006db99  test    eax, eax
0x18006db9b  jns     short loc_18006DBE2
0x18006db9d  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dba4  lea     rdx, WPP_GLOBAL_Control
0x18006dbab  cmp     rcx, rdx
0x18006dbae  jz      loc_18006E1EA
0x18006dbb4  test    byte ptr [rcx+1Ch], 4
0x18006dbb8  jz      loc_18006E1EA
0x18006dbbe  mov     rcx, [rcx+10h]
0x18006dbc2  lea     edx, [r15+0Eh]
0x18006dbc6  lea     r9, aTilemapInitFai; "\"TileMap init failed\""
0x18006dbcd  mov     dword ptr [rsp+160h+var_140], eax
0x18006dbd1  lea     r8, WPP_d7b9b1f3ce2935a14401eef6738845c5_Traceguids
0x18006dbd8  call    WPP_SF_Sd
0x18006dbdd  jmp     loc_18006E1EA
0x18006dbe2  mov     edi, [rsi+40h]
0x18006dbe5  mov     r14d, 10h
0x18006dbeb  imul    edi, [rsi+3Ch]
0x18006dbef  mov     eax, r14d
0x18006dbf2  lea     rcx, [r14-11h]
0x18006dbf6  movsxd  rbx, edi
0x18006dbf9  mul     rbx
0x18006dbfc  cmovb   rax, rcx
0x18006dc00  mov     rcx, rax; Size
0x18006dc03  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006dc08  shl     rbx, 4
0x18006dc0c  xor     edx, edx; Val
0x18006dc0e  mov     r8, rbx; Size
0x18006dc11  mov     [rsp+160h+Block], rax
0x18006dc16  mov     rcx, rax; void *
0x18006dc19  mov     r13, rax
0x18006dc1c  call    memset_0
0x18006dc21  mov     rcx, [rsi+20h]
0x18006dc25  lea     ebx, [r14-0Fh]
0x18006dc29  mov     [rbp+60h+var_70], r15
0x18006dc2d  lea     r9, [rsi+68h]
0x18006dc31  mov     [rbp+60h+var_7C], 2
0x18006dc38  lea     r8, [rsp+160h+var_100]
0x18006dc3d  mov     [rbp+60h+var_78], ebx
0x18006dc40  lea     rdx, [rbp+60h+var_80]
0x18006dc44  mov     [rbp+60h+var_74], 10000h
0x18006dc4b  mov     [rsp+160h+var_100], r13
0x18006dc50  mov     [rsp+160h+var_F8], r15
0x18006dc55  shl     edi, 4
0x18006dc58  mov     [rbp+60h+var_80], edi
0x18006dc5b  mov     rax, [rcx]
0x18006dc5e  mov     rax, [rax+18h]
0x18006dc62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dc67  mov     edi, eax
0x18006dc69  test    eax, eax
0x18006dc6b  jns     short loc_18006DCB1
0x18006dc6d  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dc74  lea     rdx, WPP_GLOBAL_Control
0x18006dc7b  cmp     rcx, rdx
0x18006dc7e  jz      loc_18006E1E0
0x18006dc84  test    byte ptr [rcx+1Ch], 4
0x18006dc88  jz      loc_18006E1E0
0x18006dc8e  lea     edx, [rbx+0Eh]
0x18006dc91  lea     r9, aCreatebufferFa; "\"CreateBuffer failed\""
0x18006dc98  mov     rcx, [rcx+10h]
0x18006dc9c  lea     r8, WPP_d7b9b1f3ce2935a14401eef6738845c5_Traceguids
0x18006dca3  mov     dword ptr [rsp+160h+var_140], eax
0x18006dca7  call    WPP_SF_Sd
0x18006dcac  jmp     loc_18006E1E0
0x18006dcb1  mov     rcx, [rsi+20h]
0x18006dcb5  lea     r9, [rsi+70h]
0x18006dcb9  mov     [rbp+60h+var_58], r15
0x18006dcbd  lea     rdx, [rbp+60h+var_68]
0x18006dcc1  mov     [rbp+60h+var_68], 20h ; ' '
0x18006dcc9  xor     r8d, r8d
0x18006dccc  mov     [rbp+60h+var_60], 4
0x18006dcd4  mov     rax, [rcx]
0x18006dcd7  mov     rax, [rax+18h]
0x18006dcdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dce0  mov     edi, eax
0x18006dce2  test    eax, eax
0x18006dce4  jns     short loc_18006DD0C
0x18006dce6  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dced  lea     rdx, WPP_GLOBAL_Control
0x18006dcf4  cmp     rcx, rdx
0x18006dcf7  jz      loc_18006E1E0
0x18006dcfd  test    byte ptr [rcx+1Ch], 4
0x18006dd01  jz      loc_18006E1E0
0x18006dd07  mov     edx, r14d
0x18006dd0a  jmp     short loc_18006DC91
0x18006dd0c  mov     rcx, [rsi+20h]
0x18006dd10  lea     rdx, [rsi+80h]
0x18006dd17  mov     [rsp+160h+var_140], rdx
0x18006dd1c  mov     r12d, 200h
0x18006dd22  xor     r9d, r9d
0x18006dd25  lea     rdx, qword_18009E6C0
0x18006dd2c  mov     r8d, r12d
0x18006dd2f  mov     rax, [rcx]
0x18006dd32  mov     rax, [rax+60h]
0x18006dd36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dd3b  mov     edi, eax
0x18006dd3d  test    eax, eax
0x18006dd3f  jns     short loc_18006DD73
0x18006dd41  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dd48  lea     rdx, WPP_GLOBAL_Control
0x18006dd4f  cmp     rcx, rdx
0x18006dd52  jz      loc_18006E1E0
0x18006dd58  test    byte ptr [rcx+1Ch], 4
0x18006dd5c  jz      loc_18006E1E0
0x18006dd62  mov     edx, 11h
0x18006dd67  lea     r9, aCreatevertexsh; "\"CreateVertexShader failed\""
0x18006dd6e  jmp     loc_18006DC98
0x18006dd73  mov     rcx, [rsi+20h]
0x18006dd77  lea     rax, aTexcoord; "TEXCOORD"
0x18006dd7e  mov     r14d, 12h
0x18006dd84  mov     [rsp+160h+var_F0], rax
0x18006dd89  mov     [rbp+60h+var_D0], rax
0x18006dd8d  lea     rdx, [rsi+78h]
0x18006dd91  mov     [rsp+160h+var_138], rdx
0x18006dd96  lea     r9, qword_18009E6C0
0x18006dd9d  mov     [rsp+160h+var_E8], r15d
0x18006dda2  lea     rdx, [rsp+160h+var_F0]
0x18006dda7  mov     [rsp+160h+var_E4], r14
0x18006ddac  lea     r8d, [r14-10h]
0x18006ddb0  mov     [rbp+60h+var_DC], r15
0x18006ddb4  mov     [rbp+60h+var_D4], r15d
0x18006ddb8  mov     [rbp+60h+var_C8], ebx
0x18006ddbb  mov     [rbp+60h+var_C4], r14
0x18006ddbf  mov     [rbp+60h+var_BC], 8
0x18006ddc7  mov     [rbp+60h+var_B4], r15d
0x18006ddcb  mov     rax, [rcx]
0x18006ddce  mov     [rsp+160h+var_140], r12
0x18006ddd3  mov     rax, [rax+58h]
0x18006ddd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dddc  mov     edi, eax
0x18006ddde  test    eax, eax
0x18006dde0  jns     short loc_18006DE12
0x18006dde2  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dde9  lea     rdx, WPP_GLOBAL_Control
0x18006ddf0  cmp     rcx, rdx
0x18006ddf3  jz      loc_18006E1E0
0x18006ddf9  test    byte ptr [rcx+1Ch], 4
0x18006ddfd  jz      loc_18006E1E0
0x18006de03  mov     edx, r14d
0x18006de06  lea     r9, aCreateinputlay; "\"CreateInputLayout failed\""
0x18006de0d  jmp     loc_18006DC98
0x18006de12  mov     rcx, [rsi+20h]
0x18006de16  lea     rdx, [rsi+88h]
0x18006de1d  mov     [rsp+160h+var_140], rdx
0x18006de22  xor     r9d, r9d
0x18006de25  mov     r8d, 694h
0x18006de2b  lea     rdx, qword_18009E8D0
0x18006de32  mov     rax, [rcx]
0x18006de35  mov     rax, [rax+68h]
0x18006de39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006de3e  mov     edi, eax
0x18006de40  test    eax, eax
0x18006de42  jns     short loc_18006DE76
0x18006de44  mov     rcx, cs:WPP_GLOBAL_Control
0x18006de4b  lea     rdx, WPP_GLOBAL_Control
0x18006de52  cmp     rcx, rdx
0x18006de55  jz      loc_18006E1E0
0x18006de5b  test    byte ptr [rcx+1Ch], 4
0x18006de5f  jz      loc_18006E1E0
0x18006de65  mov     edx, 13h
0x18006de6a  lea     r9, aCreategeometry; "\"CreateGeometryShader failed\""
0x18006de71  jmp     loc_18006DC98
0x18006de76  mov     rcx, [rsi+20h]
0x18006de7a  lea     rdx, [rsi+90h]
0x18006de81  mov     [rsp+160h+var_140], rdx
0x18006de86  xor     r9d, r9d
0x18006de89  mov     r8d, 758h
0x18006de8f  lea     rdx, unk_18009EF70
0x18006de96  mov     rax, [rcx]
0x18006de99  mov     rax, [rax+78h]
0x18006de9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dea2  mov     edi, eax
0x18006dea4  test    eax, eax
0x18006dea6  jns     short loc_18006DEDA
0x18006dea8  mov     rcx, cs:WPP_GLOBAL_Control
0x18006deaf  lea     rdx, WPP_GLOBAL_Control
0x18006deb6  cmp     rcx, rdx
0x18006deb9  jz      loc_18006E1E0
0x18006debf  test    byte ptr [rcx+1Ch], 4
0x18006dec3  jz      loc_18006E1E0
0x18006dec9  mov     edx, 14h
0x18006dece  lea     r9, aCreatepixelsha; "\"CreatePixelShader failed: PsDifferFir"...
0x18006ded5  jmp     loc_18006DC98
0x18006deda  mov     rcx, [rsi+20h]
0x18006dede  lea     rdx, [rsi+98h]
0x18006dee5  mov     [rsp+160h+var_140], rdx
0x18006deea  xor     r9d, r9d
0x18006deed  mov     r8d, 4A8h
0x18006def3  lea     rdx, unk_18009F6D0
0x18006defa  mov     rax, [rcx]
0x18006defd  mov     rax, [rax+78h]
0x18006df01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006df06  mov     edi, eax
0x18006df08  test    eax, eax
0x18006df0a  jns     short loc_18006DF3E
0x18006df0c  mov     rcx, cs:WPP_GLOBAL_Control
0x18006df13  lea     rdx, WPP_GLOBAL_Control
0x18006df1a  cmp     rcx, rdx
0x18006df1d  jz      loc_18006E1E0
0x18006df23  test    byte ptr [rcx+1Ch], 4
0x18006df27  jz      loc_18006E1E0
0x18006df2d  mov     edx, 15h
0x18006df32  lea     r9, aCreatepixelsha_0; "\"CreatePixelShader failed: PsDifferNex"...
0x18006df39  jmp     loc_18006DC98
0x18006df3e  mov     [rbp+60h+var_A8], ebx
0x18006df41  mov     r12d, r15d
0x18006df44  mov     [rbp+60h+var_A4], ebx
0x18006df47  mov     [rbp+60h+var_9C], rbx
0x18006df4b  mov     ebx, [rsi+38h]
0x18006df4e  mov     [rbp+60h+var_A0], 2Ah ; '*'
0x18006df55  mov     dword ptr [rbp+60h+var_94], r15d
0x18006df59  mov     [rbp+60h+var_94+4], 28h ; '('
0x18006df61  mov     [rbp+60h+var_88], r15d
0x18006df65  cmp     ebx, 2
0x18006df68  jb      loc_18006E12F
0x18006df6e  mov     rcx, [rsi+20h]
0x18006df72  lea     r9, [rsp+160h+var_120]
0x18006df77  shr     ebx, 1
0x18006df79  lea     rdx, [rbp+60h+var_B0]
0x18006df7d  mov     [rsp+160h+var_120], 0
0x18006df86  mov     r14d, ebx
0x18006df89  imul    r14d, [rsi+3Ch]
0x18006df8e  mov     r15d, ebx
0x18006df91  imul    r15d, [rsi+40h]
0x18006df96  xor     r8d, r8d
0x18006df99  mov     [rbp+60h+var_B0], r14d
0x18006df9d  mov     [rbp+60h+var_AC], r15d
0x18006dfa1  mov     rax, [rcx]
0x18006dfa4  mov     rax, [rax+28h]
0x18006dfa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dfad  mov     edi, eax
0x18006dfaf  test    eax, eax
0x18006dfb1  js      loc_18006E0FD
0x18006dfb7  mov     rdx, [rsp+160h+var_120]
0x18006dfbc  lea     r13, [rsi+0A0h]
0x18006dfc3  mov     rcx, r13
0x18006dfc6  call    ?push_back@?$TDynamicArrayBase@PEAUID3D11Texture2D@@V?$TCntPtr@UID3D11Texture2D@@@CacNx@@@CacNx@@QEAAJPEAUID3D11Texture2D@@@Z; CacNx::TDynamicArrayBase<ID3D11Texture2D *,CacNx::TCntPtr<ID3D11Texture2D>>::push_back(ID3D11Texture2D *)
0x18006dfcb  mov     rcx, [rsp+160h+var_120]
0x18006dfd0  mov     rax, [rcx]
0x18006dfd3  mov     rax, [rax+10h]
0x18006dfd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dfdc  mov     rcx, [rsi+20h]
0x18006dfe0  lea     r9, [rsp+160h+var_118]
0x18006dfe5  mov     rdx, [r13+8]
0x18006dfe9  xor     r8d, r8d
0x18006dfec  mov     [rsp+160h+var_118], 0
0x18006dff5  movsxd  r10, r12d
0x18006dff8  mov     rax, [rcx]
0x18006dffb  mov     rdx, [rdx+r10*8]
0x18006dfff  mov     rax, [rax+38h]
0x18006e003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e008  mov     edi, eax
0x18006e00a  test    eax, eax
0x18006e00c  js      loc_18006E0CB
0x18006e012  mov     rdx, [rsp+160h+var_118]
0x18006e017  lea     rcx, [rsi+0B8h]
0x18006e01e  call    ?push_back@?$TDynamicArrayBase@PEAUID3D11Texture2D@@V?$TCntPtr@UID3D11Texture2D@@@CacNx@@@CacNx@@QEAAJPEAUID3D11Texture2D@@@Z; CacNx::TDynamicArrayBase<ID3D11Texture2D *,CacNx::TCntPtr<ID3D11Texture2D>>::push_back(ID3D11Texture2D *)
  ... truncated ...
```
