# CacNx::TileEncoderX11on10::initRgb2YCbCr(void)

- ea: `0x180073258`
- end: `0x18007361b`
- name: `?initRgb2YCbCr@TileEncoderX11on10@CacNx@@AEAAJXZ`
- size: `963`
- prototype: `__int64 __fastcall(CacNx::TileEncoderX11on10 *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180071600`

## callees

- `0x180006580`
- `0x180006ff4`
- `0x18006a898`
- `0x180073258`
- `0x180089010`

## string_xrefs

- `0x1800732f7`: `"CreateVertexShader failed"`
- `0x18007339f`: `"CreateInputLayout failed"`
- `0x180073403`: `"CreateGeometryShader failed"`
- `0x1800734f2`: `"CreateTexture2D failed"`
- `0x1800735b7`: `"CreateRenderTargetView failed"`
- `0x1800735de`: `"CreateShaderResourceView failed"`
- `0x180073467`: `"CreatePixelShader"`

## pseudocode

```c
__int64 __fastcall CacNx::TileEncoderX11on10::initRgb2YCbCr(CacNx::TileEncoderX11on10 *this)
{
  int v2; // eax
  unsigned int v3; // ebx
  _QWORD *v4; // rcx
  int v5; // edx
  const wchar_t *v6; // r9
  __int64 v7; // rcx
  __int64 *v8; // r14
  __int64 v9; // rcx
  unsigned int v10; // esi
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rdx
  int v16; // [rsp+40h] [rbp-99h] BYREF
  __int64 v17; // [rsp+44h] [rbp-95h]
  unsigned int v18; // [rsp+4Ch] [rbp-8Dh]
  int v19; // [rsp+50h] [rbp-89h]
  int v20; // [rsp+58h] [rbp-81h] BYREF
  __int64 v21; // [rsp+5Ch] [rbp-7Dh]
  int v22; // [rsp+64h] [rbp-75h]
  unsigned int v23; // [rsp+68h] [rbp-71h]
  int v24; // [rsp+6Ch] [rbp-6Dh]
  const char *v25; // [rsp+70h] [rbp-69h] BYREF
  int v26; // [rsp+78h] [rbp-61h]
  __int64 v27; // [rsp+7Ch] [rbp-5Dh]
  __int64 v28; // [rsp+84h] [rbp-55h]
  int v29; // [rsp+8Ch] [rbp-4Dh]
  const char *v30; // [rsp+90h] [rbp-49h]
  int v31; // [rsp+98h] [rbp-41h]
  __int64 v32; // [rsp+9Ch] [rbp-3Dh]
  __int64 v33; // [rsp+A4h] [rbp-35h]
  int v34; // [rsp+ACh] [rbp-2Dh]
  _DWORD v35[5]; // [rsp+B0h] [rbp-29h] BYREF
  __int64 v36; // [rsp+C4h] [rbp-15h]
  int v37; // [rsp+CCh] [rbp-Dh]
  __int64 v38; // [rsp+D0h] [rbp-9h]
  int v39; // [rsp+D8h] [rbp-1h]

  memcpy_s((char *)this + 76, 0x30u, qword_1800C1C60, 0x30u);
  v2 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64, _QWORD, char *))(**((_QWORD **)this + 1) + 96LL))(
         *((_QWORD *)this + 1),
         qword_1800A2290,
         512,
         0,
         (char *)this + 304);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v7 = *((_QWORD *)this + 1);
    v25 = "TEXCOORD";
    v30 = "TEXCOORD";
    v26 = 0;
    v27 = 18;
    v28 = 0;
    v29 = 0;
    v31 = 1;
    v32 = 18;
    v33 = 8;
    v34 = 0;
    v2 = (*(__int64 (__fastcall **)(__int64, const char **, __int64, __int64 *, __int64, char *))(*(_QWORD *)v7 + 88LL))(
           v7,
           &v25,
           2,
           qword_1800A2290,
           512,
           (char *)this + 312);
    v3 = v2;
    if ( v2 >= 0 )
    {
      v2 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64, _QWORD, char *))(**((_QWORD **)this + 1) + 104LL))(
             *((_QWORD *)this + 1),
             qword_1800A1BB0,
             1760,
             0,
             (char *)this + 344);
      v3 = v2;
      if ( v2 >= 0 )
      {
        v2 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64, _QWORD, char *))(**((_QWORD **)this + 1) + 120LL))(
               *((_QWORD *)this + 1),
               qword_18009FFF0,
               1084,
               0,
               (char *)this + 352);
        v3 = v2;
        if ( v2 >= 0 )
        {
          v8 = (__int64 *)((char *)this + 360);
          v9 = *((_QWORD *)this + 1);
          v35[0] = *((_DWORD *)this + 6);
          v35[1] = *((_DWORD *)this + 7);
          v35[2] = 1;
          v35[3] = 3;
          v35[4] = 41;
          v36 = 1;
          v37 = 0;
          v38 = 40;
          v39 = 0;
          v2 = (*(__int64 (__fastcall **)(__int64, _DWORD *, _QWORD, char *))(*(_QWORD *)v9 + 40LL))(
                 v9,
                 v35,
                 0,
                 (char *)this + 360);
          v3 = v2;
          if ( v2 >= 0 )
          {
            v10 = 0;
            while ( 1 )
            {
              v11 = *((_QWORD *)this + 1);
              v12 = *v8;
              v20 = 41;
              v21 = 5;
              v22 = 1;
              v23 = v10;
              v24 = 1;
              v2 = (*(__int64 (__fastcall **)(__int64, __int64, int *, char *))(*(_QWORD *)v11 + 56LL))(
                     v11,
                     v12,
                     &v20,
                     (char *)this + 8 * v10 + 368);
              v3 = v2;
              if ( v2 < 0 )
                break;
              v13 = *((_QWORD *)this + 1);
              v14 = *v8;
              v16 = 41;
              v17 = 5;
              v18 = v10;
              v19 = 1;
              v2 = (*(__int64 (__fastcall **)(__int64, __int64, int *, char *))(*(_QWORD *)v13 + 72LL))(
                     v13,
                     v14,
                     &v16,
                     (char *)this + 8 * v10 + 392);
              v3 = v2;
              if ( v2 < 0 )
              {
                v4 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                {
                  v5 = 29;
                  v6 = L"\"CreateRenderTargetView failed\"";
                  goto LABEL_32;
                }
                return v3;
              }
              if ( ++v10 >= 3 )
                return v3;
            }
            v4 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              v5 = 28;
              v6 = L"\"CreateShaderResourceView failed\"";
              goto LABEL_32;
            }
          }
          else
          {
            v4 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              v5 = 27;
              v6 = L"\"CreateTexture2D failed\"";
              goto LABEL_32;
            }
          }
        }
        else
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v5 = 26;
            v6 = L"\"CreatePixelShader\"";
            goto LABEL_32;
          }
        }
      }
      else
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v5 = 25;
          v6 = L"\"CreateGeometryShader failed\"";
          goto LABEL_32;
        }
      }
    }
    else
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v5 = 24;
        v6 = L"\"CreateInputLayout failed\"";
        goto LABEL_32;
      }
    }
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v5 = 23;
      v6 = L"\"CreateVertexShader failed\"";
LABEL_32:
      WPP_SF_Sd(v4[2], v5, (unsigned int)WPP_f7ccfaaf8ea83090a4b72d85c6394124_Traceguids, (_DWORD)v6, v2);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180073258  push    rbp
0x18007325a  push    rbx
0x18007325b  push    rsi
0x18007325c  push    rdi
0x18007325d  push    r12
0x18007325f  push    r13
0x180073261  push    r14
0x180073263  push    r15
0x180073265  lea     rbp, [rsp-1Fh]
0x18007326a  sub     rsp, 0F8h
0x180073271  mov     rax, cs:__security_cookie
0x180073278  xor     rax, rsp
0x18007327b  mov     [rbp+57h+var_50], rax
0x18007327f  mov     edx, 30h ; '0'; DestinationSize
0x180073284  lea     r8, qword_1800C1C60; Source
0x18007328b  mov     rdi, rcx
0x18007328e  mov     r9d, edx; SourceSize
0x180073291  add     rcx, 4Ch ; 'L'; Destination
0x180073295  call    memcpy_s
0x18007329a  mov     rcx, [rdi+8]
0x18007329e  lea     rdx, [rdi+130h]
0x1800732a5  mov     [rsp+130h+var_110], rdx
0x1800732aa  mov     esi, 200h
0x1800732af  xor     r9d, r9d
0x1800732b2  lea     rdx, qword_1800A2290
0x1800732b9  mov     r8d, esi
0x1800732bc  mov     rax, [rcx]
0x1800732bf  mov     rax, [rax+60h]
0x1800732c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800732c8  xor     r12d, r12d
0x1800732cb  mov     ebx, eax
0x1800732cd  test    eax, eax
0x1800732cf  jns     short loc_180073303
0x1800732d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800732d8  lea     rdx, WPP_GLOBAL_Control
0x1800732df  cmp     rcx, rdx
0x1800732e2  jz      loc_1800735F9
0x1800732e8  test    byte ptr [rcx+1Ch], 4
0x1800732ec  jz      loc_1800735F9
0x1800732f2  lea     edx, [r12+17h]
0x1800732f7  lea     r9, aCreatevertexsh; "\"CreateVertexShader failed\""
0x1800732fe  jmp     loc_1800735E5
0x180073303  mov     rcx, [rdi+8]
0x180073307  lea     rax, aTexcoord; "TEXCOORD"
0x18007330e  mov     [rbp+57h+var_C0], rax
0x180073312  lea     rdx, [rdi+138h]
0x180073319  mov     [rbp+57h+var_A0], rax
0x18007331d  lea     r9, qword_1800A2290
0x180073324  mov     [rsp+130h+var_108], rdx
0x180073329  mov     r13d, 1
0x18007332f  mov     [rbp+57h+var_B8], r12d
0x180073333  lea     rdx, [rbp+57h+var_C0]
0x180073337  mov     [rbp+57h+var_B4], 12h
0x18007333f  mov     [rbp+57h+var_AC], r12
0x180073343  mov     [rbp+57h+var_A4], r12d
0x180073347  lea     r8d, [r13+1]
0x18007334b  mov     [rbp+57h+var_98], r13d
0x18007334f  mov     [rbp+57h+var_94], 12h
0x180073357  mov     [rbp+57h+var_8C], 8
0x18007335f  mov     [rbp+57h+var_84], r12d
0x180073363  mov     rax, [rcx]
0x180073366  mov     [rsp+130h+var_110], rsi
0x18007336b  mov     rax, [rax+58h]
0x18007336f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073374  mov     ebx, eax
0x180073376  test    eax, eax
0x180073378  jns     short loc_1800733AB
0x18007337a  mov     rcx, cs:WPP_GLOBAL_Control
0x180073381  lea     rdx, WPP_GLOBAL_Control
0x180073388  cmp     rcx, rdx
0x18007338b  jz      loc_1800735F9
0x180073391  test    byte ptr [rcx+1Ch], 4
0x180073395  jz      loc_1800735F9
0x18007339b  lea     edx, [r13+17h]
0x18007339f  lea     r9, aCreateinputlay; "\"CreateInputLayout failed\""
0x1800733a6  jmp     loc_1800735E5
0x1800733ab  mov     rcx, [rdi+8]
0x1800733af  lea     rdx, [rdi+158h]
0x1800733b6  mov     [rsp+130h+var_110], rdx
0x1800733bb  xor     r9d, r9d
0x1800733be  mov     r8d, 6E0h
0x1800733c4  lea     rdx, qword_1800A1BB0
0x1800733cb  mov     rax, [rcx]
0x1800733ce  mov     rax, [rax+68h]
0x1800733d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800733d7  mov     ebx, eax
0x1800733d9  test    eax, eax
0x1800733db  jns     short loc_18007340F
0x1800733dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800733e4  lea     rdx, WPP_GLOBAL_Control
0x1800733eb  cmp     rcx, rdx
0x1800733ee  jz      loc_1800735F9
0x1800733f4  test    byte ptr [rcx+1Ch], 4
0x1800733f8  jz      loc_1800735F9
0x1800733fe  mov     edx, 19h
0x180073403  lea     r9, aCreategeometry; "\"CreateGeometryShader failed\""
0x18007340a  jmp     loc_1800735E5
0x18007340f  mov     rcx, [rdi+8]
0x180073413  lea     rdx, [rdi+160h]
0x18007341a  mov     [rsp+130h+var_110], rdx
0x18007341f  xor     r9d, r9d
0x180073422  mov     r8d, 43Ch
0x180073428  lea     rdx, qword_18009FFF0
0x18007342f  mov     rax, [rcx]
0x180073432  mov     rax, [rax+78h]
0x180073436  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007343b  mov     ebx, eax
0x18007343d  test    eax, eax
0x18007343f  jns     short loc_180073473
0x180073441  mov     rcx, cs:WPP_GLOBAL_Control
0x180073448  lea     rdx, WPP_GLOBAL_Control
0x18007344f  cmp     rcx, rdx
0x180073452  jz      loc_1800735F9
0x180073458  test    byte ptr [rcx+1Ch], 4
0x18007345c  jz      loc_1800735F9
0x180073462  mov     edx, 1Ah
0x180073467  lea     r9, aCreatepixelsha_1; "\"CreatePixelShader\""
0x18007346e  jmp     loc_1800735E5
0x180073473  mov     eax, [rdi+18h]
0x180073476  lea     r14, [rdi+168h]
0x18007347d  mov     rcx, [rdi+8]
0x180073481  lea     rdx, [rbp+57h+var_80]
0x180073485  mov     [rbp+57h+var_80], eax
0x180073488  mov     r9, r14
0x18007348b  mov     eax, [rdi+1Ch]
0x18007348e  xor     r8d, r8d
0x180073491  mov     [rbp+57h+var_7C], eax
0x180073494  mov     [rbp+57h+var_78], r13d
0x180073498  mov     [rbp+57h+var_74], 3
0x18007349f  mov     [rbp+57h+var_70], 29h ; ')'
0x1800734a6  mov     [rbp+57h+var_6C], r13
0x1800734aa  mov     [rbp+57h+var_64], r12d
0x1800734ae  mov     [rbp+57h+var_60], 28h ; '('
0x1800734b6  mov     [rbp+57h+var_58], r12d
0x1800734ba  mov     rax, [rcx]
0x1800734bd  mov     rax, [rax+28h]
0x1800734c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800734c6  mov     ebx, eax
0x1800734c8  test    eax, eax
0x1800734ca  jns     short loc_1800734FE
0x1800734cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800734d3  lea     rdx, WPP_GLOBAL_Control
0x1800734da  cmp     rcx, rdx
0x1800734dd  jz      loc_1800735F9
0x1800734e3  test    byte ptr [rcx+1Ch], 4
0x1800734e7  jz      loc_1800735F9
0x1800734ed  mov     edx, 1Bh
0x1800734f2  lea     r9, aCreatetexture2; "\"CreateTexture2D failed\""
0x1800734f9  jmp     loc_1800735E5
0x1800734fe  mov     esi, r12d
0x180073501  mov     rcx, [rdi+8]
0x180073505  lea     r9, [rdi+170h]
0x18007350c  mov     rdx, [r14]
0x18007350f  lea     r8, [rsp+130h+var_D8]
0x180073514  mov     [rsp+130h+var_D8], 29h ; ')'
0x18007351c  mov     [rbp+57h+var_D4], 5
0x180073524  mov     [rbp+57h+var_CC], r13d
0x180073528  mov     [rbp+57h+var_C8], esi
0x18007352b  mov     [rbp+57h+var_C4], r13d
0x18007352f  mov     rax, [rcx]
0x180073532  mov     r15d, esi
0x180073535  mov     rax, [rax+38h]
0x180073539  lea     r9, [r9+r15*8]
0x18007353d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073542  mov     ebx, eax
0x180073544  test    eax, eax
0x180073546  js      short loc_1800735C0
0x180073548  mov     rcx, [rdi+8]
0x18007354c  lea     r9, [rdi+188h]
0x180073553  mov     rdx, [r14]
0x180073556  lea     r9, [r9+r15*8]
0x18007355a  mov     [rsp+130h+var_F0], 29h ; ')'
0x180073562  lea     r8, [rsp+130h+var_F0]
0x180073567  mov     [rsp+130h+var_EC], 5
0x180073570  mov     [rsp+130h+var_E4], esi
0x180073574  mov     [rsp+130h+var_E0], r13d
0x180073579  mov     rax, [rcx]
0x18007357c  mov     rax, [rax+48h]
0x180073580  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073585  mov     ebx, eax
0x180073587  test    eax, eax
0x180073589  js      short loc_180073599
0x18007358b  add     esi, r13d
0x18007358e  cmp     esi, 3
0x180073591  jb      loc_180073501
0x180073597  jmp     short loc_1800735F9
0x180073599  mov     rcx, cs:WPP_GLOBAL_Control
0x1800735a0  lea     rdx, WPP_GLOBAL_Control
0x1800735a7  cmp     rcx, rdx
0x1800735aa  jz      short loc_1800735F9
0x1800735ac  test    byte ptr [rcx+1Ch], 4
0x1800735b0  jz      short loc_1800735F9
0x1800735b2  mov     edx, 1Dh
0x1800735b7  lea     r9, aCreaterenderta; "\"CreateRenderTargetView failed\""
0x1800735be  jmp     short loc_1800735E5
0x1800735c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800735c7  lea     rdx, WPP_GLOBAL_Control
0x1800735ce  cmp     rcx, rdx
0x1800735d1  jz      short loc_1800735F9
0x1800735d3  test    byte ptr [rcx+1Ch], 4
0x1800735d7  jz      short loc_1800735F9
0x1800735d9  mov     edx, 1Ch
0x1800735de  lea     r9, aCreateshaderre; "\"CreateShaderResourceView failed\""
0x1800735e5  mov     rcx, [rcx+10h]
0x1800735e9  lea     r8, WPP_f7ccfaaf8ea83090a4b72d85c6394124_Traceguids
0x1800735f0  mov     dword ptr [rsp+130h+var_110], eax
0x1800735f4  call    WPP_SF_Sd
0x1800735f9  mov     eax, ebx
0x1800735fb  mov     rcx, [rbp+57h+var_50]
0x1800735ff  xor     rcx, rsp; StackCookie
0x180073602  call    __security_check_cookie
0x180073607  add     rsp, 0F8h
0x18007360e  pop     r15
0x180073610  pop     r14
0x180073612  pop     r13
0x180073614  pop     r12
0x180073616  pop     rdi
0x180073617  pop     rsi
0x180073618  pop     rbx
0x180073619  pop     rbp
0x18007361a  retn
```
