# D3DXShader::CParse::Token(void)

- ea: `0x1400a5d18`
- end: `0x1400a6a24`
- name: `?Token@CParse@D3DXShader@@IEAAHXZ`
- size: `3340`
- prototype: `__int64 __fastcall(D3DXShader::CParse *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400a7d8c`

## callees

- `0x140003641`
- `0x140097ff4`
- `0x14009edd4`
- `0x1400a5d18`
- `0x1401131ca`

## import_xrefs

- `msvcrt!_stricmp` at `0x1400a6940`
- `msvcrt!_stricmp` at `0x1400a695f`
- `msvcrt!_stricmp` at `0x1400a697e`
- `msvcrt!_stricmp` at `0x1400a699d`
- `msvcrt!_stricmp` at `0x1400a6940`
- `msvcrt!_stricmp` at `0x1400a695f`
- `msvcrt!_stricmp` at `0x1400a697e`
- `msvcrt!_stricmp` at `0x1400a699d`

## string_xrefs

- `0x1400a60b2`: `compile`
- `0x1400a60cf`: `compile_fragment`
- `0x1400a5fb2`: `delete`
- `0x1400a64a6`: `template`

## pseudocode

```c
__int64 __fastcall D3DXShader::CParse::Token(D3DXShader::CParse *this)
{
  D3DXShader::CParse *v1; // rdi
  struct D3DXShader::D3DXTOKEN *v2; // r14
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  char v13; // al
  char v14; // al
  const char *v15; // rbx
  int v16; // esi
  int v17; // edx
  const char *v18; // rdx
  int v19; // edx
  int v20; // edx
  int v21; // eax

  v1 = D3DXShader::CParse::s_pParse;
  v2 = (D3DXShader::CParse *)((char *)D3DXShader::CParse::s_pParse + 64);
  while ( 1 )
  {
    while ( 1 )
    {
      if ( (int)D3DXShader::CPreProcessor::GetToken(*((D3DXShader::CPreProcessor **)v1 + 1), v2) < 0 )
      {
        *((_DWORD *)v1 + 28) = 1;
        return 0xFFFFFFFFLL;
      }
      v3 = *(_DWORD *)v2;
      if ( *(int *)v2 > 6 )
        break;
      if ( v3 == 6 )
        return 331;
      if ( !v3 )
        return 337;
      v4 = v3 - 1;
      if ( !v4 )
      {
        v13 = *((_BYTE *)v1 + 73);
        if ( !v13 )
          return (unsigned int)*((char *)v1 + 72);
        if ( !*((_BYTE *)v1 + 74) )
        {
          if ( v13 == 61 )
          {
            switch ( *((_BYTE *)v1 + 72) )
            {
              case '!':
                return 319;
              case '%':
                return 324;
              case '*':
                return 322;
              case '+':
                return 325;
              case '-':
                return 326;
              case '/':
                return 323;
              case '<':
                return 316;
              case '=':
                return 318;
              case '>':
                return 317;
            }
          }
          else if ( *((_BYTE *)v1 + 72) == v13 )
          {
            v14 = *((_BYTE *)v1 + 72);
            switch ( v14 )
            {
              case '&':
                return 320;
              case '+':
                return 314;
              case '-':
                return 315;
              case '|':
                return 321;
            }
          }
        }
        return 337;
      }
      v5 = v4 - 1;
      if ( !v5 )
        return 327;
      v6 = v5 - 1;
      if ( !v6 )
        return 328;
      v7 = v6 - 1;
      if ( !v7 )
        return 329;
      if ( v7 == 1 )
        return 330;
    }
    v9 = v3 - 7;
    if ( !v9 )
      return 332;
    v10 = v9 - 1;
    if ( !v10 )
      return 333;
    v11 = v10 - 1;
    if ( !v11 )
      break;
    v12 = v11 - 1;
    if ( !v12 )
      return 334;
    if ( v12 == 3 )
      return 0xFFFFFFFFLL;
  }
  v15 = (const char *)*((_QWORD *)v1 + 9);
  v16 = *v15;
  if ( v16 > 109 )
  {
    if ( v16 == 110 )
    {
      if ( !strcmp_0(*((const char **)v1 + 9), "namespace") )
        return 337;
      v18 = "new";
    }
    else if ( v16 == 111 )
    {
      if ( !strcmp_0(*((const char **)v1 + 9), "out") )
        return 280;
      v18 = "operator";
    }
    else
    {
      switch ( v16 )
      {
        case 'p':
          if ( !strcmp_0(*((const char **)v1 + 9), "pixelfragment") )
            return 282;
          if ( !strcmp_0(v15, "private") || !strcmp_0(v15, "protected") || !strcmp_0(v15, "public") )
            return 337;
          if ( *((_DWORD *)v1 + 30) && !strcmp_0(v15, "pixelshader") )
            return 283;
          goto LABEL_234;
        case 'r':
          if ( !strcmp_0(*((const char **)v1 + 9), "register") )
            return 284;
          if ( !strcmp_0(v15, "reinterpret_cast") )
            return 337;
          if ( !strcmp_0(v15, "row_major") )
            return 286;
          if ( !strcmp_0(v15, "return") )
            return 285;
          goto LABEL_234;
        case 's':
          if ( !strcmp_0(*((const char **)v1 + 9), "sampler1D") )
            return 288;
          if ( !strcmp_0(v15, "sampler2D") )
            return 289;
          if ( !strcmp_0(v15, "sampler3D") )
            return 290;
          if ( !strcmp_0(v15, "samplerCUBE") )
            return 291;
          if ( !strcmp_0(v15, "sampler_state") )
            return 292;
          if ( !strcmp_0(v15, "shared") )
            return 293;
          if ( !strcmp_0(v15, "short") || !strcmp_0(v15, "signed") || !strcmp_0(v15, "sizeof") )
            return 337;
          if ( !strcmp_0(v15, "stateblock_state") )
            return 295;
          if ( !strcmp_0(v15, "static") )
            return 296;
          if ( !strcmp_0(v15, "static_cast") )
            return 337;
          if ( !strcmp_0(v15, "string") )
            return 297;
          if ( !strcmp_0(v15, "struct") )
            return 298;
          if ( !strcmp_0(v15, "switch") )
            return 337;
          if ( *((_DWORD *)v1 + 30) )
          {
            if ( !strcmp_0(v15, "sampler") )
              return 287;
            if ( !strcmp_0(v15, "stateblock") )
              return 294;
          }
          goto LABEL_234;
        case 't':
          if ( !strcmp_0(*((const char **)v1 + 9), "template") )
            return 337;
          if ( !strcmp_0(v15, "texture1D") )
            return 301;
          if ( !strcmp_0(v15, "texture2D") )
            return 302;
          if ( !strcmp_0(v15, "texture3D") )
            return 303;
          if ( !strcmp_0(v15, "textureCUBE") )
            return 304;
          if ( !strcmp_0(v15, "this") || !strcmp_0(v15, "throw") )
            return 337;
          if ( !strcmp_0(v15, "true") )
            return 305;
          if ( !strcmp_0(v15, "try") )
            return 337;
          if ( !strcmp_0(v15, "typedef") )
            return 306;
          if ( !strcmp_0(v15, "typename") )
            return 337;
          if ( *((_DWORD *)v1 + 30) && !strcmp_0(v15, "texture") )
            return 300;
          goto LABEL_234;
      }
      if ( v16 != 117 )
      {
        if ( v16 == 118 )
        {
          if ( !strcmp_0(*((const char **)v1 + 9), "vector") )
            return 308;
          if ( !strcmp_0(v15, "vertexfragment") )
            return 309;
          if ( !strcmp_0(v15, "virtual") )
            return 337;
          if ( !strcmp_0(v15, "void") )
            return 311;
          if ( !strcmp_0(v15, "volatile") )
            return 312;
          if ( *((_DWORD *)v1 + 30) && !strcmp_0(v15, "vertexshader") )
            return 310;
        }
        else if ( v16 == 119 && !strcmp_0(*((const char **)v1 + 9), "while") )
        {
          return 313;
        }
        goto LABEL_234;
      }
      if ( !strcmp_0(*((const char **)v1 + 9), "uniform") )
        return 307;
      if ( !strcmp_0(v15, "union") || !strcmp_0(v15, "unsigned") )
        return 337;
      v18 = "using";
    }
    goto LABEL_233;
  }
  if ( v16 == 109 )
  {
    if ( !strcmp_0(*((const char **)v1 + 9), "matrix") )
      return 279;
    v18 = "mutable";
    goto LABEL_233;
  }
  if ( v16 > 102 )
  {
    switch ( v16 )
    {
      case 'g':
        v18 = "goto";
        break;
      case 'h':
        if ( !strcmp_0(*((const char **)v1 + 9), "half") )
          return 273;
        goto LABEL_234;
      case 'i':
        v19 = *(unsigned __int8 *)v15 - 105;
        if ( *v15 == 105 )
        {
          v19 = *((unsigned __int8 *)v15 + 1) - 102;
          if ( v15[1] == 102 )
            v19 = *((unsigned __int8 *)v15 + 2);
        }
        if ( !v19 )
          return 274;
        v20 = *(unsigned __int8 *)v15 - 105;
        if ( *v15 == 105 )
        {
          v20 = *((unsigned __int8 *)v15 + 1) - 110;
          if ( v15[1] == 110 )
            v20 = *((unsigned __int8 *)v15 + 2);
        }
        if ( !v20 )
          return 275;
        if ( !strcmp_0(*((const char **)v1 + 9), "inline") )
          return 276;
        if ( !strcmp_0(v15, "inout") )
          return 277;
        if ( !strcmp_0(v15, "int") )
          return 278;
        goto LABEL_234;
      case 'l':
        v18 = "long";
        break;
      default:
        goto LABEL_234;
    }
    goto LABEL_233;
  }
  switch ( v16 )
  {
    case 'f':
      if ( !strcmp_0(*((const char **)v1 + 9), "false") )
        return 270;
      if ( !strcmp_0(v15, "float") )
        return 271;
      if ( !strcmp_0(v15, "for") )
        return 272;
      v18 = "friend";
      goto LABEL_233;
    case 'a':
      if ( strcmp_0(*((const char **)v1 + 9), "auto") )
      {
        if ( !strcmp_0(v15, "asm_fragment") )
          return 258;
        break;
      }
      return 337;
    case 'b':
      if ( !strcmp_0(*((const char **)v1 + 9), "bool") )
        return 259;
      v18 = "break";
      goto LABEL_233;
    case 'c':
      if ( !strcmp_0(*((const char **)v1 + 9), "case")
        || !strcmp_0(v15, "catch")
        || !strcmp_0(v15, "char")
        || !strcmp_0(v15, "class") )
      {
        return 337;
      }
      if ( !strcmp_0(v15, "column_major") )
        return 260;
      if ( !strcmp_0(v15, "compile") )
        return 261;
      if ( !strcmp_0(v15, "compile_fragment") )
        return 262;
      if ( !strcmp_0(v15, "const") )
        return 263;
      if ( !strcmp_0(v15, "const_cast") )
        return 337;
      v18 = "continue";
LABEL_233:
      if ( strcmp_0(v15, v18) )
        break;
      return 337;
    case 'd':
      if ( !strcmp_0(*((const char **)v1 + 9), "default") || !strcmp_0(v15, "delete") )
        return 337;
      if ( !strcmp_0(v15, "discard") )
        return 265;
      v17 = *(unsigned __int8 *)v15 - 100;
      if ( *v15 == 100 )
      {
        v17 = *((unsigned __int8 *)v15 + 1) - 111;
        if ( v15[1] == 111 )
          v17 = *((unsigned __int8 *)v15 + 2);
      }
      if ( !v17 )
        return 267;
      if ( !strcmp_0(v15, "double") )
        return 266;
      v18 = "dynamic_cast";
      goto LABEL_233;
    case 'e':
      if ( !strcmp_0(*((const char **)v1 + 9), "else") )
        return 268;
      if ( !strcmp_0(v15, "enum") || !strcmp_0(v15, "explicit") )
        return 337;
      if ( !strcmp_0(v15, "extern") )
        return 269;
      break;
  }
LABEL_234:
  v21 = tolower_0(v16);
  switch ( v21 )
  {
    case 'a':
      if ( !_stricmp(*((const char **)v1 + 9), "asm") )
        return 257;
      break;
    case 'd':
      if ( !_stricmp(*((const char **)v1 + 9), "decl") )
        return 264;
      break;
    case 'p':
      if ( !_stricmp(*((const char **)v1 + 9), "pass") )
        return 281;
      break;
    default:
      if ( v21 == 116 && !_stricmp(*((const char **)v1 + 9), "technique") )
        return 299;
      break;
  }
  return (unsigned int)((unsigned int)D3DXShader::CParse::FindDecl(v1, 0, v2, 0, 0, *((_QWORD *)v1 + 4), 0, 0, 0) != 0)
       + 335;
}

```

## disassembly

```asm
0x1400a5d18  push    rbx
0x1400a5d1a  push    rsi
0x1400a5d1b  push    rdi
0x1400a5d1c  push    r14
0x1400a5d1e  push    r15
0x1400a5d20  sub     rsp, 50h
0x1400a5d24  mov     rdi, cs:?s_pParse@CParse@D3DXShader@@1PEAV12@EA; D3DXShader::CParse * D3DXShader::CParse::s_pParse
0x1400a5d2b  lea     r14, [rdi+40h]
0x1400a5d2f  mov     rcx, [rdi+8]; this
0x1400a5d33  mov     rdx, r14; struct D3DXShader::D3DXTOKEN *
0x1400a5d36  call    ?GetToken@CPreProcessor@D3DXShader@@QEAAJPEAUD3DXTOKEN@2@@Z; D3DXShader::CPreProcessor::GetToken(D3DXShader::D3DXTOKEN *)
0x1400a5d3b  test    eax, eax
0x1400a5d3d  js      loc_1400A6A0E
0x1400a5d43  mov     ecx, [r14]
0x1400a5d46  cmp     ecx, 6
0x1400a5d49  jg      short loc_1400A5D7C
0x1400a5d4b  jz      loc_1400A5EC1
0x1400a5d51  test    ecx, ecx
0x1400a5d53  jz      loc_1400A69F9
0x1400a5d59  sub     ecx, 1
0x1400a5d5c  jz      short loc_1400A5DC8
0x1400a5d5e  sub     ecx, 1
0x1400a5d61  jz      short loc_1400A5DBE
0x1400a5d63  sub     ecx, 1
0x1400a5d66  jz      short loc_1400A5DB4
0x1400a5d68  sub     ecx, 1
0x1400a5d6b  jz      short loc_1400A5DAA
0x1400a5d6d  cmp     ecx, 1
0x1400a5d70  jnz     short loc_1400A5D2F
0x1400a5d72  mov     eax, 14Ah
0x1400a5d77  jmp     loc_1400A6A18
0x1400a5d7c  sub     ecx, 7
0x1400a5d7f  jz      loc_1400A6A07
0x1400a5d85  sub     ecx, 1
0x1400a5d88  jz      loc_1400A6A00
0x1400a5d8e  sub     ecx, 1
0x1400a5d91  jz      loc_1400A5ED5
0x1400a5d97  sub     ecx, 1
0x1400a5d9a  jz      loc_1400A5ECB
0x1400a5da0  cmp     ecx, 3
0x1400a5da3  jnz     short loc_1400A5D2F
0x1400a5da5  jmp     loc_1400A6A15
0x1400a5daa  mov     eax, 149h
0x1400a5daf  jmp     loc_1400A6A18
0x1400a5db4  mov     eax, 148h
0x1400a5db9  jmp     loc_1400A6A18
0x1400a5dbe  mov     eax, 147h
0x1400a5dc3  jmp     loc_1400A6A18
0x1400a5dc8  mov     al, [rdi+49h]
0x1400a5dcb  test    al, al
0x1400a5dcd  jnz     short loc_1400A5DD8
0x1400a5dcf  movsx   eax, byte ptr [rdi+48h]
0x1400a5dd3  jmp     loc_1400A6A18
0x1400a5dd8  cmp     byte ptr [rdi+4Ah], 0
0x1400a5ddc  jnz     loc_1400A69F9
0x1400a5de2  cmp     al, 3Dh ; '='
0x1400a5de4  jnz     loc_1400A5E79
0x1400a5dea  movsx   ecx, byte ptr [rdi+48h]
0x1400a5dee  sub     ecx, 21h ; '!'
0x1400a5df1  jz      short loc_1400A5E6F
0x1400a5df3  sub     ecx, 4
0x1400a5df6  jz      short loc_1400A5E65
0x1400a5df8  sub     ecx, 5
0x1400a5dfb  jz      short loc_1400A5E5B
0x1400a5dfd  sub     ecx, 1
0x1400a5e00  jz      short loc_1400A5E51
0x1400a5e02  sub     ecx, 2
0x1400a5e05  jz      short loc_1400A5E47
0x1400a5e07  sub     ecx, 2
0x1400a5e0a  jz      short loc_1400A5E3D
0x1400a5e0c  sub     ecx, 0Dh
0x1400a5e0f  jz      short loc_1400A5E33
0x1400a5e11  sub     ecx, 1
0x1400a5e14  jz      short loc_1400A5E29
0x1400a5e16  cmp     ecx, 1
0x1400a5e19  jnz     loc_1400A69F9
0x1400a5e1f  mov     eax, 13Dh
0x1400a5e24  jmp     loc_1400A6A18
0x1400a5e29  mov     eax, 13Eh
0x1400a5e2e  jmp     loc_1400A6A18
0x1400a5e33  mov     eax, 13Ch
0x1400a5e38  jmp     loc_1400A6A18
0x1400a5e3d  mov     eax, 143h
0x1400a5e42  jmp     loc_1400A6A18
0x1400a5e47  mov     eax, 146h
0x1400a5e4c  jmp     loc_1400A6A18
0x1400a5e51  mov     eax, 145h
0x1400a5e56  jmp     loc_1400A6A18
0x1400a5e5b  mov     eax, 142h
0x1400a5e60  jmp     loc_1400A6A18
0x1400a5e65  mov     eax, 144h
0x1400a5e6a  jmp     loc_1400A6A18
0x1400a5e6f  mov     eax, 13Fh
0x1400a5e74  jmp     loc_1400A6A18
0x1400a5e79  cmp     [rdi+48h], al
0x1400a5e7c  jnz     loc_1400A69F9
0x1400a5e82  mov     al, [rdi+48h]
0x1400a5e85  cmp     al, 26h ; '&'
0x1400a5e87  jz      short loc_1400A5EB7
0x1400a5e89  cmp     al, 2Bh ; '+'
0x1400a5e8b  jz      short loc_1400A5EAD
0x1400a5e8d  cmp     al, 2Dh ; '-'
0x1400a5e8f  jz      short loc_1400A5EA3
0x1400a5e91  cmp     al, 7Ch ; '|'
0x1400a5e93  jnz     loc_1400A69F9
0x1400a5e99  mov     eax, 141h
0x1400a5e9e  jmp     loc_1400A6A18
0x1400a5ea3  mov     eax, 13Bh
0x1400a5ea8  jmp     loc_1400A6A18
0x1400a5ead  mov     eax, 13Ah
0x1400a5eb2  jmp     loc_1400A6A18
0x1400a5eb7  mov     eax, 140h
0x1400a5ebc  jmp     loc_1400A6A18
0x1400a5ec1  mov     eax, 14Bh
0x1400a5ec6  jmp     loc_1400A6A18
0x1400a5ecb  mov     eax, 14Eh
0x1400a5ed0  jmp     loc_1400A6A18
0x1400a5ed5  mov     rbx, [rdi+48h]
0x1400a5ed9  mov     r15d, 64h ; 'd'
0x1400a5edf  movsx   esi, byte ptr [rbx]
0x1400a5ee2  cmp     esi, 6Dh ; 'm'
0x1400a5ee5  jg      loc_1400A6329
0x1400a5eeb  jz      loc_1400A6300
0x1400a5ef1  lea     r8d, [r15+2]
0x1400a5ef5  cmp     esi, r8d
0x1400a5ef8  jg      loc_1400A61F0
0x1400a5efe  jz      loc_1400A618D
0x1400a5f04  mov     ecx, esi
0x1400a5f06  sub     ecx, 61h ; 'a'
0x1400a5f09  jz      loc_1400A6155
0x1400a5f0f  sub     ecx, 1
0x1400a5f12  jz      loc_1400A612C
0x1400a5f18  sub     ecx, 1
0x1400a5f1b  jz      loc_1400A6039
0x1400a5f21  sub     ecx, 1
0x1400a5f24  jz      short loc_1400A5F9B
0x1400a5f26  cmp     ecx, 1
0x1400a5f29  jnz     loc_1400A691A
0x1400a5f2f  lea     rdx, aElse; "else"
0x1400a5f36  mov     rcx, rbx; Str1
0x1400a5f39  call    strcmp_0
0x1400a5f3e  test    eax, eax
0x1400a5f40  jnz     short loc_1400A5F4C
0x1400a5f42  mov     eax, 10Ch
0x1400a5f47  jmp     loc_1400A6A18
0x1400a5f4c  lea     rdx, aEnum; "enum"
0x1400a5f53  mov     rcx, rbx; Str1
0x1400a5f56  call    strcmp_0
0x1400a5f5b  test    eax, eax
0x1400a5f5d  jz      loc_1400A69F9
0x1400a5f63  lea     rdx, aExplicit; "explicit"
0x1400a5f6a  mov     rcx, rbx; Str1
0x1400a5f6d  call    strcmp_0
0x1400a5f72  test    eax, eax
0x1400a5f74  jz      loc_1400A69F9
0x1400a5f7a  lea     rdx, aExtern; "extern"
0x1400a5f81  mov     rcx, rbx; Str1
0x1400a5f84  call    strcmp_0
0x1400a5f89  test    eax, eax
0x1400a5f8b  jnz     loc_1400A691A
0x1400a5f91  mov     eax, 10Dh
0x1400a5f96  jmp     loc_1400A6A18
0x1400a5f9b  lea     rdx, aDefault; "default"
0x1400a5fa2  mov     rcx, rbx; Str1
0x1400a5fa5  call    strcmp_0
0x1400a5faa  test    eax, eax
0x1400a5fac  jz      loc_1400A69F9
0x1400a5fb2  lea     rdx, aDelete; "delete"
0x1400a5fb9  mov     rcx, rbx; Str1
0x1400a5fbc  call    strcmp_0
0x1400a5fc1  test    eax, eax
0x1400a5fc3  jz      loc_1400A69F9
0x1400a5fc9  lea     rdx, aDiscard; "discard"
0x1400a5fd0  mov     rcx, rbx; Str1
0x1400a5fd3  call    strcmp_0
0x1400a5fd8  test    eax, eax
0x1400a5fda  jnz     short loc_1400A5FE6
0x1400a5fdc  mov     eax, 109h
0x1400a5fe1  jmp     loc_1400A6A18
0x1400a5fe6  movzx   edx, byte ptr [rbx]
0x1400a5fe9  sub     edx, r15d
0x1400a5fec  jnz     short loc_1400A6002
0x1400a5fee  movzx   edx, byte ptr [rbx+1]
0x1400a5ff2  sub     edx, 6Fh ; 'o'
0x1400a5ff5  jnz     short loc_1400A6002
0x1400a5ff7  movzx   edx, byte ptr [rbx+2]
0x1400a5ffb  xor     eax, eax
0x1400a5ffd  movzx   ecx, al
0x1400a6000  sub     edx, ecx
0x1400a6002  test    edx, edx
0x1400a6004  jnz     short loc_1400A6010
0x1400a6006  mov     eax, 10Bh
0x1400a600b  jmp     loc_1400A6A18
0x1400a6010  lea     rdx, aDouble; "double"
0x1400a6017  mov     rcx, rbx; Str1
0x1400a601a  call    strcmp_0
0x1400a601f  test    eax, eax
0x1400a6021  jnz     short loc_1400A602D
0x1400a6023  mov     eax, 10Ah
0x1400a6028  jmp     loc_1400A6A18
0x1400a602d  lea     rdx, aDynamicCast; "dynamic_cast"
0x1400a6034  jmp     loc_1400A690A
0x1400a6039  lea     rdx, aCase; "case"
0x1400a6040  mov     rcx, rbx; Str1
0x1400a6043  call    strcmp_0
0x1400a6048  test    eax, eax
0x1400a604a  jz      loc_1400A69F9
0x1400a6050  lea     rdx, aCatch; "catch"
0x1400a6057  mov     rcx, rbx; Str1
0x1400a605a  call    strcmp_0
0x1400a605f  test    eax, eax
0x1400a6061  jz      loc_1400A69F9
0x1400a6067  lea     rdx, aChar; "char"
0x1400a606e  mov     rcx, rbx; Str1
0x1400a6071  call    strcmp_0
0x1400a6076  test    eax, eax
0x1400a6078  jz      loc_1400A69F9
0x1400a607e  lea     rdx, aClass; "class"
0x1400a6085  mov     rcx, rbx; Str1
0x1400a6088  call    strcmp_0
0x1400a608d  test    eax, eax
0x1400a608f  jz      loc_1400A69F9
0x1400a6095  lea     rdx, aColumnMajor; "column_major"
0x1400a609c  mov     rcx, rbx; Str1
0x1400a609f  call    strcmp_0
0x1400a60a4  test    eax, eax
0x1400a60a6  jnz     short loc_1400A60B2
0x1400a60a8  mov     eax, 104h
0x1400a60ad  jmp     loc_1400A6A18
0x1400a60b2  lea     rdx, aCompile; "compile"
0x1400a60b9  mov     rcx, rbx; Str1
0x1400a60bc  call    strcmp_0
0x1400a60c1  test    eax, eax
0x1400a60c3  jnz     short loc_1400A60CF
0x1400a60c5  mov     eax, 105h
0x1400a60ca  jmp     loc_1400A6A18
0x1400a60cf  lea     rdx, aCompileFragmen; "compile_fragment"
0x1400a60d6  mov     rcx, rbx; Str1
0x1400a60d9  call    strcmp_0
0x1400a60de  test    eax, eax
0x1400a60e0  jnz     short loc_1400A60EC
0x1400a60e2  mov     eax, 106h
0x1400a60e7  jmp     loc_1400A6A18
0x1400a60ec  lea     rdx, aConst_0; "const"
0x1400a60f3  mov     rcx, rbx; Str1
0x1400a60f6  call    strcmp_0
0x1400a60fb  test    eax, eax
0x1400a60fd  jnz     short loc_1400A6109
0x1400a60ff  mov     eax, 107h
0x1400a6104  jmp     loc_1400A6A18
0x1400a6109  lea     rdx, aConstCast; "const_cast"
0x1400a6110  mov     rcx, rbx; Str1
0x1400a6113  call    strcmp_0
0x1400a6118  test    eax, eax
0x1400a611a  jz      loc_1400A69F9
0x1400a6120  lea     rdx, aContinue; "continue"
0x1400a6127  jmp     loc_1400A690A
0x1400a612c  lea     rdx, aBool; "bool"
0x1400a6133  mov     rcx, rbx; Str1
0x1400a6136  call    strcmp_0
0x1400a613b  test    eax, eax
0x1400a613d  jnz     short loc_1400A6149
0x1400a613f  mov     eax, 103h
0x1400a6144  jmp     loc_1400A6A18
0x1400a6149  lea     rdx, aBreak; "break"
0x1400a6150  jmp     loc_1400A690A
0x1400a6155  lea     rdx, aAuto; "auto"
0x1400a615c  mov     rcx, rbx; Str1
0x1400a615f  call    strcmp_0
0x1400a6164  test    eax, eax
0x1400a6166  jz      loc_1400A69F9
0x1400a616c  lea     rdx, aAsmFragment; "asm_fragment"
0x1400a6173  mov     rcx, rbx; Str1
0x1400a6176  call    strcmp_0
0x1400a617b  test    eax, eax
0x1400a617d  jnz     loc_1400A691A
0x1400a6183  mov     eax, 102h
0x1400a6188  jmp     loc_1400A6A18
0x1400a618d  lea     rdx, aFalse; "false"
0x1400a6194  mov     rcx, rbx; Str1
0x1400a6197  call    strcmp_0
0x1400a619c  test    eax, eax
0x1400a619e  jnz     short loc_1400A61AA
0x1400a61a0  mov     eax, 10Eh
0x1400a61a5  jmp     loc_1400A6A18
0x1400a61aa  lea     rdx, aFloat; "float"
0x1400a61b1  mov     rcx, rbx; Str1
0x1400a61b4  call    strcmp_0
0x1400a61b9  test    eax, eax
0x1400a61bb  jnz     short loc_1400A61C7
0x1400a61bd  mov     eax, 10Fh
0x1400a61c2  jmp     loc_1400A6A18
0x1400a61c7  lea     rdx, aFor; "for"
0x1400a61ce  mov     rcx, rbx; Str1
0x1400a61d1  call    strcmp_0
0x1400a61d6  test    eax, eax
0x1400a61d8  jnz     short loc_1400A61E4
0x1400a61da  mov     eax, 110h
0x1400a61df  jmp     loc_1400A6A18
0x1400a61e4  lea     rdx, aFriend; "friend"
  ... truncated ...
```
