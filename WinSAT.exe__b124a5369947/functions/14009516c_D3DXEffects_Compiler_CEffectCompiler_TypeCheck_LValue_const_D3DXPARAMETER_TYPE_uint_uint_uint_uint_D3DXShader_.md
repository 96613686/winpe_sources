# D3DXEffects::Compiler::CEffectCompiler::TypeCheck(LValue const *,_D3DXPARAMETER_TYPE,uint,uint,uint,uint,D3DXShader::D3DXTOKEN *)

- ea: `0x14009516c`
- end: `0x140095439`
- name: `?TypeCheck@CEffectCompiler@Compiler@D3DXEffects@@AEAAJPEBULValue@@W4_D3DXPARAMETER_TYPE@@IIIIPEAUD3DXTOKEN@D3DXShader@@@Z`
- size: `717`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140091ad0`

## callees

- `0x14009516c`
- `0x1400a96b4`

## string_xrefs

- `0x14009520d`: `ID3DXEffectCompiler: State '%s' was not assigned a stateblock type`
- `0x140095216`: `ID3DXEffectCompiler: State '%s' cannot be assigned an array or structure`
- `0x140095330`: `ID3DXEffectCompiler: State '%s' was not assigned a texture type`
- `0x1400952ed`: `ID3DXEffectCompiler: State '%s' was not assigned a sampler type`
- `0x140095268`: `ID3DXEffectCompiler: State '%s' must be assigned a numeric scalar or a 4-float vector`
- `0x1400952aa`: `ID3DXEffectCompiler: State '%s' was assigned an incompatible type`
- `0x1400953e0`: `ID3DXEffectCompiler: State '%s' must be assigned a 3-vector or a 4-vector or a uint scalar`
- `0x140095408`: `ID3DXEffectCompiler: State '%s' must be assigned a scalar`
- `0x1400951d5`: `ID3DXEffectCompiler: Unexpected value type of state '%s' (internal error)`
- `0x140095425`: `ID3DXEffectCompiler: State '%s' must be assigned a numeric value`

## pseudocode

```c
__int64 __fastcall D3DXEffects::Compiler::CEffectCompiler::TypeCheck(
        __int64 a1,
        _QWORD *a2,
        int a3,
        int a4,
        int a5,
        int a6,
        int a7,
        struct D3DXShader::D3DXTOKEN *a8)
{
  unsigned int v9; // eax
  unsigned int v10; // eax
  bool v11; // zf
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax

  switch ( *((_DWORD *)a2 + 2) )
  {
    case 1:
    case 2:
      goto LABEL_77;
    case 3:
      v9 = *((_DWORD *)a2 + 7);
      if ( v9 > 0xD000000 )
      {
        v12 = v9 - 218103809;
        v11 = v12 == 0;
      }
      else
      {
        if ( v9 == 218103808 )
          goto LABEL_77;
        v10 = v9 - 201326592;
        if ( !v10 )
          goto LABEL_77;
        v12 = v10 - 1;
        v11 = v12 == 0;
      }
      if ( v11 )
        goto LABEL_77;
      v13 = v12 - 1;
      if ( !v13 )
        goto LABEL_77;
      v14 = v13 - 1;
      if ( !v14 )
        goto LABEL_77;
      v15 = v14 - 1;
      if ( !v15 )
        goto LABEL_77;
      v16 = v15 - 65532;
      if ( !v16 || v16 == 0x10000 || *((_DWORD *)a2 + 4) != 1 )
        goto LABEL_77;
      if ( *((_DWORD *)a2 + 5) == 1 )
      {
        if ( a4 != 1 || a5 != 1 || a6 || a7 )
        {
          D3DXShader::CTErrors::Error(
            (D3DXShader::CTErrors *)(a1 + 56),
            a8,
            0,
            "ID3DXEffectCompiler: State '%s' must be assigned a scalar",
            *a2);
          return 2147500037LL;
        }
      }
      else
      {
        if ( (unsigned int)(*((_DWORD *)a2 + 5) - 3) > 1 )
          goto LABEL_77;
        if ( a5 != 1 || (unsigned int)(a4 - 3) > 1 || a6 || a7 )
        {
          if ( a3 != 2 || a4 != 1 || a5 != 1 )
          {
            D3DXShader::CTErrors::Error(
              (D3DXShader::CTErrors *)(a1 + 56),
              a8,
              0,
              "ID3DXEffectCompiler: State '%s' must be assigned a 3-vector or a 4-vector or a uint scalar",
              *a2);
            return 2147500037LL;
          }
LABEL_77:
          if ( a7 )
            return 0;
        }
      }
      if ( (unsigned int)(a3 - 1) > 2 )
      {
        D3DXShader::CTErrors::Error(
          (D3DXShader::CTErrors *)(a1 + 56),
          a8,
          0,
          "ID3DXEffectCompiler: State '%s' must be assigned a numeric value",
          *a2);
        return 2147500037LL;
      }
      return 0;
    case 5:
      if ( !a6 && !a7 )
      {
        if ( a4 != 1 || a5 != 1 || a3 != 2 && (unsigned int)(a3 - 5) > 4 )
        {
          D3DXShader::CTErrors::Error(
            (D3DXShader::CTErrors *)(a1 + 56),
            a8,
            0,
            "ID3DXEffectCompiler: State '%s' was not assigned a texture type",
            *a2);
          return 2147500037LL;
        }
        return 0;
      }
      goto LABEL_18;
    case 0xA:
      if ( !a6 && !a7 )
      {
        if ( a4 != 1 || a5 != 1 || a3 != 2 && (unsigned int)(a3 - 10) > 4 )
        {
          D3DXShader::CTErrors::Error(
            (D3DXShader::CTErrors *)(a1 + 56),
            a8,
            0,
            "ID3DXEffectCompiler: State '%s' was not assigned a sampler type",
            *a2);
          return 2147500037LL;
        }
        return 0;
      }
      goto LABEL_18;
    case 0xF:
    case 0x10:
      if ( !a6 && !a7 )
      {
        if ( (*((_DWORD *)a2 + 2) != a3 || a4 != 1 || a5 != 1) && (a3 != 2 || a4 != 1 || a5 != 1) )
        {
          D3DXShader::CTErrors::Error(
            (D3DXShader::CTErrors *)(a1 + 56),
            a8,
            0,
            "ID3DXEffectCompiler: State '%s' was assigned an incompatible type",
            *a2);
          return 2147500037LL;
        }
        return 0;
      }
LABEL_18:
      D3DXShader::CTErrors::Error(
        (D3DXShader::CTErrors *)(a1 + 56),
        a8,
        0,
        "ID3DXEffectCompiler: State '%s' cannot be assigned an array or structure",
        *a2);
      return 2147500037LL;
    case 0xF20000:
      if ( a3 == 3 )
      {
        if ( a4 == 4 )
        {
LABEL_25:
          if ( a5 == 1 )
            return 0;
LABEL_26:
          D3DXShader::CTErrors::Error(
            (D3DXShader::CTErrors *)(a1 + 56),
            a8,
            0,
            "ID3DXEffectCompiler: State '%s' must be assigned a numeric scalar or a 4-float vector",
            *a2);
          return 2147500037LL;
        }
      }
      else if ( (unsigned int)(a3 - 1) > 1 )
      {
        goto LABEL_26;
      }
      if ( a4 != 1 )
        goto LABEL_26;
      goto LABEL_25;
  }
  if ( *((_DWORD *)a2 + 2) != 15925248 )
  {
    D3DXShader::CTErrors::Error(
      (D3DXShader::CTErrors *)(a1 + 56),
      a8,
      0,
      "ID3DXEffectCompiler: Unexpected value type of state '%s' (internal error)",
      *a2);
    return 2147500037LL;
  }
  if ( a6 || a7 )
    goto LABEL_18;
  if ( a4 != 1 || a5 != 1 || a3 != 15925248 && a3 != 2 )
  {
    D3DXShader::CTErrors::Error(
      (D3DXShader::CTErrors *)(a1 + 56),
      a8,
      0,
      "ID3DXEffectCompiler: State '%s' was not assigned a stateblock type",
      *a2);
    return 2147500037LL;
  }
  return 0;
}

```

## disassembly

```asm
0x14009516c  push    rbx
0x14009516e  sub     rsp, 30h
0x140095172  mov     r10d, [rdx+8]
0x140095176  mov     r11, rcx
0x140095179  mov     ebx, [rsp+38h+arg_30]
0x14009517d  sub     r10d, 1
0x140095181  jz      loc_140095414
0x140095187  sub     r10d, 1
0x14009518b  jz      loc_140095414
0x140095191  sub     r10d, 1
0x140095195  jz      loc_14009533C
0x14009519b  sub     r10d, 2
0x14009519f  jz      loc_1400952F9
0x1400951a5  sub     r10d, 5
0x1400951a9  jz      loc_1400952B6
0x1400951af  sub     r10d, 5
0x1400951b3  jz      loc_140095271
0x1400951b9  sub     r10d, 1
0x1400951bd  jz      loc_140095271
0x1400951c3  sub     r10d, 0F1FFF0h
0x1400951ca  jz      short loc_140095240
0x1400951cc  cmp     r10d, 10000h
0x1400951d3  jz      short loc_1400951DE
0x1400951d5  lea     r9, aId3dxeffectcom_1; "ID3DXEffectCompiler: Unexpected value t"...
0x1400951dc  jmp     short loc_14009521D
0x1400951de  cmp     [rsp+38h+arg_28], 0
0x1400951e3  jnz     short loc_140095216
0x1400951e5  test    ebx, ebx
0x1400951e7  jnz     short loc_140095216
0x1400951e9  cmp     r9d, 1
0x1400951ed  jnz     short loc_14009520D
0x1400951ef  cmp     [rsp+38h+arg_20], r9d
0x1400951f4  jnz     short loc_14009520D
0x1400951f6  cmp     r8d, 0F30000h
0x1400951fd  jz      loc_140095431
0x140095203  cmp     r8d, 2
0x140095207  jz      loc_140095431
0x14009520d  lea     r9, aId3dxeffectcom_16; "ID3DXEffectCompiler: State '%s' was not"...
0x140095214  jmp     short loc_14009521D
0x140095216  lea     r9, aId3dxeffectcom_38; "ID3DXEffectCompiler: State '%s' cannot "...
0x14009521d  add     rcx, 38h ; '8'; this
0x140095221  mov     rax, [rdx]
0x140095224  xor     r8d, r8d; unsigned int
0x140095227  mov     rdx, [rsp+38h+arg_38]; struct D3DXShader::D3DXTOKEN *
0x14009522c  mov     [rsp+38h+var_18], rax
0x140095231  call    ?Error@CTErrors@D3DXShader@@QEAAJPEAUD3DXTOKEN@2@IPEBDZZ; D3DXShader::CTErrors::Error(D3DXShader::D3DXTOKEN *,uint,char const *,...)
0x140095236  mov     eax, 80004005h
0x14009523b  jmp     loc_140095433
0x140095240  cmp     r8d, 3
0x140095244  jnz     short loc_14009524E
0x140095246  cmp     r9d, 4
0x14009524a  jnz     short loc_140095257
0x14009524c  jmp     short loc_14009525D
0x14009524e  lea     eax, [r8-1]
0x140095252  cmp     eax, 1
0x140095255  ja      short loc_140095268
0x140095257  cmp     r9d, 1
0x14009525b  jnz     short loc_140095268
0x14009525d  cmp     [rsp+38h+arg_20], 1
0x140095262  jz      loc_140095431
0x140095268  lea     r9, aId3dxeffectcom_49; "ID3DXEffectCompiler: State '%s' must be"...
0x14009526f  jmp     short loc_14009521D
0x140095271  cmp     [rsp+38h+arg_28], 0
0x140095276  jnz     short loc_140095216
0x140095278  test    ebx, ebx
0x14009527a  jnz     short loc_140095216
0x14009527c  cmp     [rdx+8], r8d
0x140095280  jnz     short loc_140095293
0x140095282  cmp     r9d, 1
0x140095286  jnz     short loc_140095293
0x140095288  cmp     [rsp+38h+arg_20], r9d
0x14009528d  jz      loc_140095431
0x140095293  cmp     r8d, 2
0x140095297  jnz     short loc_1400952AA
0x140095299  cmp     r9d, 1
0x14009529d  jnz     short loc_1400952AA
0x14009529f  cmp     [rsp+38h+arg_20], r9d
0x1400952a4  jz      loc_140095431
0x1400952aa  lea     r9, aId3dxeffectcom_14; "ID3DXEffectCompiler: State '%s' was ass"...
0x1400952b1  jmp     loc_14009521D
0x1400952b6  cmp     [rsp+38h+arg_28], 0
0x1400952bb  jnz     loc_140095216
0x1400952c1  test    ebx, ebx
0x1400952c3  jnz     loc_140095216
0x1400952c9  cmp     r9d, 1
0x1400952cd  jnz     short loc_1400952ED
0x1400952cf  cmp     [rsp+38h+arg_20], r9d
0x1400952d4  jnz     short loc_1400952ED
0x1400952d6  cmp     r8d, 2
0x1400952da  jz      loc_140095431
0x1400952e0  lea     eax, [r8-0Ah]
0x1400952e4  cmp     eax, 4
0x1400952e7  jbe     loc_140095431
0x1400952ed  lea     r9, aId3dxeffectcom; "ID3DXEffectCompiler: State '%s' was not"...
0x1400952f4  jmp     loc_14009521D
0x1400952f9  cmp     [rsp+38h+arg_28], 0
0x1400952fe  jnz     loc_140095216
0x140095304  test    ebx, ebx
0x140095306  jnz     loc_140095216
0x14009530c  cmp     r9d, 1
0x140095310  jnz     short loc_140095330
0x140095312  cmp     [rsp+38h+arg_20], r9d
0x140095317  jnz     short loc_140095330
0x140095319  cmp     r8d, 2
0x14009531d  jz      loc_140095431
0x140095323  lea     eax, [r8-5]
0x140095327  cmp     eax, 4
0x14009532a  jbe     loc_140095431
0x140095330  lea     r9, aId3dxeffectcom_47; "ID3DXEffectCompiler: State '%s' was not"...
0x140095337  jmp     loc_14009521D
0x14009533c  mov     eax, [rdx+1Ch]
0x14009533f  mov     ecx, 0D000000h
0x140095344  cmp     eax, ecx
0x140095346  ja      short loc_14009535E
0x140095348  jz      loc_140095414
0x14009534e  sub     eax, 0C000000h
0x140095353  jz      loc_140095414
0x140095359  sub     eax, 1
0x14009535c  jmp     short loc_140095363
0x14009535e  sub     eax, 0D000001h
0x140095363  jz      loc_140095414
0x140095369  sub     eax, 1
0x14009536c  jz      loc_140095414
0x140095372  sub     eax, 1
0x140095375  jz      loc_140095414
0x14009537b  sub     eax, 1
0x14009537e  jz      loc_140095414
0x140095384  sub     eax, 0FFFCh
0x140095389  jz      loc_140095414
0x14009538f  cmp     eax, 10000h
0x140095394  jz      short loc_140095414
0x140095396  cmp     dword ptr [rdx+10h], 1
0x14009539a  jnz     short loc_140095414
0x14009539c  mov     ecx, [rdx+14h]
0x14009539f  sub     ecx, 1
0x1400953a2  jz      short loc_1400953EC
0x1400953a4  sub     ecx, 2
0x1400953a7  jz      short loc_1400953AE
0x1400953a9  cmp     ecx, 1
0x1400953ac  jnz     short loc_140095414
0x1400953ae  cmp     [rsp+38h+arg_20], 1
0x1400953b3  jnz     short loc_1400953C9
0x1400953b5  lea     eax, [r9-3]
0x1400953b9  cmp     eax, 1
0x1400953bc  ja      short loc_1400953C9
0x1400953be  cmp     [rsp+38h+arg_28], 0
0x1400953c3  jnz     short loc_1400953C9
0x1400953c5  test    ebx, ebx
0x1400953c7  jz      short loc_140095418
0x1400953c9  cmp     r8d, 2
0x1400953cd  jnz     short loc_1400953DC
0x1400953cf  cmp     r9d, 1
0x1400953d3  jnz     short loc_1400953DC
0x1400953d5  cmp     [rsp+38h+arg_20], r9d
0x1400953da  jz      short loc_140095414
0x1400953dc  lea     rcx, [r11+38h]
0x1400953e0  lea     r9, aId3dxeffectcom_23; "ID3DXEffectCompiler: State '%s' must be"...
0x1400953e7  jmp     loc_140095221
0x1400953ec  cmp     r9d, 1
0x1400953f0  jnz     short loc_140095404
0x1400953f2  cmp     [rsp+38h+arg_20], r9d
0x1400953f7  jnz     short loc_140095404
0x1400953f9  cmp     [rsp+38h+arg_28], 0
0x1400953fe  jnz     short loc_140095404
0x140095400  test    ebx, ebx
0x140095402  jz      short loc_140095418
0x140095404  lea     rcx, [r11+38h]
0x140095408  lea     r9, aId3dxeffectcom_6; "ID3DXEffectCompiler: State '%s' must be"...
0x14009540f  jmp     loc_140095221
0x140095414  test    ebx, ebx
0x140095416  jnz     short loc_140095431
0x140095418  lea     eax, [r8-1]
0x14009541c  cmp     eax, 2
0x14009541f  jbe     short loc_140095431
0x140095421  lea     rcx, [r11+38h]
0x140095425  lea     r9, aId3dxeffectcom_7; "ID3DXEffectCompiler: State '%s' must be"...
0x14009542c  jmp     loc_140095221
0x140095431  xor     eax, eax
0x140095433  add     rsp, 30h
0x140095437  pop     rbx
0x140095438  retn
```
