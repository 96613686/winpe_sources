# jsonTranslateBlobToText

- ea: `0x1800696ac`
- end: `0x180069bd5`
- name: `jsonTranslateBlobToText`
- size: `1321`
- prototype: ``
- caller_count: `6`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180064ffc`
- `0x180066b00`
- `0x180068f04`
- `0x1800691a8`
- `0x180069500`
- `0x1800696ac`

## callees

- `0x180064d60`
- `0x180064dc4`
- `0x180064f30`
- `0x180064f80`
- `0x180065168`
- `0x1800688cc`
- `0x180069380`
- `0x1800694ec`
- `0x1800696ac`
- `0x18006ac38`

## pseudocode

```c
__int64 __fastcall jsonTranslateBlobToText(__int64 *a1, __int64 a2, __int64 a3)
{
  __int64 v4; // r15
  int v6; // eax
  __int64 v7; // rdx
  int v8; // r13d
  __int64 v10; // r8
  unsigned int v11; // esi
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  unsigned __int64 v17; // rbx
  _BYTE *v18; // r14
  int v19; // ebp
  unsigned int v20; // r12d
  int v21; // eax
  __int64 v22; // rdx
  const char *v23; // r8
  __int64 v24; // r8
  const char *v25; // rdx
  unsigned int v26; // ebp
  _BYTE *v27; // r14
  __int64 v28; // rax
  unsigned int v29; // ecx
  unsigned int v30; // ecx
  unsigned int v31; // ecx
  unsigned int v32; // ecx
  unsigned int v33; // ecx
  char v34; // r12
  __int16 *v35; // rdx
  unsigned int v36; // ebx
  unsigned int v37; // ebp
  bool v38; // cc
  char v39; // al
  __int64 v40; // rdx
  unsigned int v41; // ebx
  unsigned int v42; // ebp
  unsigned int v43; // eax
  __int64 v44; // rdx
  const char *v45; // r14
  unsigned int v46; // ebx
  __int64 v47; // rbp
  __int64 v48; // rcx
  __int64 v49; // r8
  const char *v50; // rdx
  unsigned int v51; // [rsp+88h] [rbp+20h] BYREF

  v4 = (unsigned int)a2;
  v51 = 0;
  v6 = jsonbPayloadSize(a1, a2, &v51);
  v8 = v6;
  if ( !v6 )
  {
    *(_BYTE *)(a3 + 33) |= 2u;
    return (unsigned int)(*((_DWORD *)a1 + 2) + 1);
  }
  v10 = *a1;
  v11 = v51;
  v12 = *(_BYTE *)(v4 + *a1) & 0xF;
  if ( v12 > 6 )
  {
    v29 = v12 - 7;
    if ( !v29 || (v30 = v29 - 1) == 0 )
    {
      LOBYTE(v7) = 34;
      jsonAppendChar(a3, v7);
      jsonAppendRaw(a3, *a1 + (unsigned int)(v4 + v8), v11);
LABEL_117:
      LOBYTE(v35) = 34;
      goto LABEL_118;
    }
    v31 = v30 - 1;
    if ( v31 )
    {
      v32 = v31 - 1;
      if ( !v32 )
      {
        jsonAppendString(a3, v10 + (unsigned int)(v4 + v6), v51);
        return (unsigned int)v4 + v11 + v8;
      }
      v33 = v32 - 1;
      if ( !v33 )
      {
        LOBYTE(v7) = 91;
        jsonAppendChar(a3, v7);
        v41 = v4 + v8;
        v42 = v4 + v8 + v11;
        while ( v41 < v42 )
        {
          if ( *(_BYTE *)(a3 + 33) )
            goto LABEL_69;
          v43 = jsonTranslateBlobToText(a1, v41, a3);
          LOBYTE(v44) = 44;
          v41 = v43;
          jsonAppendChar(a3, v44);
        }
        if ( v41 > v42 )
          *(_BYTE *)(a3 + 33) |= 2u;
LABEL_69:
        if ( v11 )
          jsonStringTrimOneChar(a3);
        LOBYTE(v35) = 93;
        goto LABEL_118;
      }
      if ( v33 != 1 )
        goto LABEL_52;
      LOBYTE(v7) = 123;
      v34 = 0;
      jsonAppendChar(a3, v7);
      v36 = v4 + v8;
      v37 = v4 + v8 + v11;
      v38 = (int)v4 + v8 <= v37;
      if ( (int)v4 + v8 < v37 )
      {
        do
        {
          if ( *(_BYTE *)(a3 + 33) )
            break;
          v36 = jsonTranslateBlobToText(a1, v36, a3);
          v39 = v34++;
          LOBYTE(v40) = (v39 & 1) != 0 ? 44 : 58;
          jsonAppendChar(a3, v40);
        }
        while ( v36 < v37 );
        if ( (v34 & 1) != 0 )
          goto LABEL_59;
        v38 = v36 <= v37;
      }
      if ( v38 )
      {
LABEL_60:
        if ( v11 )
          jsonStringTrimOneChar(a3);
        LOBYTE(v35) = 125;
LABEL_118:
        jsonAppendChar(a3, v35);
        return (unsigned int)v4 + v11 + v8;
      }
LABEL_59:
      *(_BYTE *)(a3 + 33) |= 2u;
      goto LABEL_60;
    }
    LOBYTE(v7) = 34;
    v45 = (const char *)(v10 + (unsigned int)(v4 + v6));
    v46 = v51;
    jsonAppendChar(a3, v7);
    while ( 1 )
    {
      while ( 1 )
      {
        v35 = &_ImageBase;
        if ( !v46 )
          goto LABEL_117;
        v47 = 0;
        do
        {
          v48 = (unsigned __int8)v45[v47];
          if ( !*((_BYTE *)qword_1800BA610 + v48) && (_BYTE)v48 != 39 )
            break;
          v47 = (unsigned int)(v47 + 1);
        }
        while ( (unsigned int)v47 < v46 );
        if ( (_DWORD)v47 )
        {
          jsonAppendRawNZ(a3, v45, (unsigned int)v47);
          if ( (unsigned int)v47 >= v46 )
            goto LABEL_117;
          v45 += (unsigned int)v47;
          v46 -= v47;
        }
        if ( *v45 == 34 )
        {
          jsonAppendRawNZ(a3, "\\\"", 2);
          goto LABEL_84;
        }
        if ( *v45 > 31 )
          break;
        if ( (unsigned __int64)(*(_QWORD *)(a3 + 24) + 7LL) > *(_QWORD *)(a3 + 16)
          && (unsigned int)jsonStringGrow(a3, 7) )
        {
          goto LABEL_117;
        }
        LOBYTE(v35) = *v45;
        jsonAppendControlChar(a3, v35);
LABEL_84:
        ++v45;
        --v46;
      }
      if ( v46 < 2 )
      {
        *(_BYTE *)(a3 + 33) |= 2u;
        goto LABEL_117;
      }
      if ( v45[1] != 10 )
      {
        if ( v45[1] == 13 )
        {
          if ( v46 > 2 && v45[2] == 10 )
          {
            ++v45;
            --v46;
          }
        }
        else
        {
          if ( v45[1] != 39 )
          {
            switch ( v45[1] )
            {
              case '0':
                v50 = "\\u0000";
                break;
              case 'v':
                v50 = "\\u0009";
                break;
              case 'x':
                if ( v46 >= 4 )
                {
                  jsonAppendRawNZ(a3, "\\u00", 4);
                  v45 += 2;
                  jsonAppendRawNZ(a3, v45, 2);
                  goto LABEL_102;
                }
                goto LABEL_103;
              default:
                if ( *((unsigned __int8 *)v45 + 1) == 226 )
                {
                  if ( v46 >= 4 && v45[2] == (const char)0x80 && (v45[3] == 0xA8 || v45[3] == -87) )
                  {
                    v45 += 2;
LABEL_102:
                    v46 -= 2;
                    goto LABEL_114;
                  }
LABEL_103:
                  *(_BYTE *)(a3 + 33) |= 2u;
                  v46 = 2;
                  goto LABEL_114;
                }
                v49 = 2;
                v50 = v45;
                goto LABEL_109;
            }
            v49 = 6;
LABEL_109:
            jsonAppendRawNZ(a3, v50, v49);
            goto LABEL_114;
          }
          LOBYTE(v35) = 39;
          jsonAppendChar(a3, v35);
        }
      }
LABEL_114:
      v45 += 2;
      v46 -= 2;
    }
  }
  if ( v12 == 6 )
  {
    if ( v51 )
    {
      v26 = 0;
      v27 = (_BYTE *)(v10 + (unsigned int)(v4 + v6));
      if ( *v27 == 45 )
      {
        LOBYTE(v7) = 45;
        jsonAppendChar(a3, v7);
        v26 = 1;
      }
      if ( v27[v26] == 46 )
      {
        LOBYTE(v7) = 48;
        jsonAppendChar(a3, v7);
      }
      for ( ; v26 < v11; ++v26 )
      {
        LOBYTE(v7) = v27[v26];
        jsonAppendChar(a3, v7);
        if ( v27[v26] == 46 )
        {
          v28 = v26 + 1;
          if ( (_DWORD)v28 == v11 || (*((_BYTE *)&qword_1800ADE90 + (unsigned __int8)v27[v28]) & 4) == 0 )
          {
            LOBYTE(v7) = 48;
            jsonAppendChar(a3, v7);
          }
        }
      }
      return (unsigned int)v4 + v11 + v8;
    }
    goto LABEL_52;
  }
  if ( (*(_BYTE *)(v4 + *a1) & 0xF) == 0 )
  {
    v25 = "null";
    goto LABEL_32;
  }
  v13 = v12 - 1;
  if ( !v13 )
  {
    v25 = "true";
LABEL_32:
    v24 = 4;
    goto LABEL_33;
  }
  v14 = v13 - 1;
  if ( !v14 )
  {
    v24 = 5;
    v25 = "false";
LABEL_33:
    jsonAppendRawNZ(a3, v25, v24);
    return (unsigned int)(v4 + 1);
  }
  v15 = v14 - 1;
  if ( v15 )
  {
    v16 = v15 - 1;
    if ( !v16 )
    {
      if ( v51 )
      {
        v17 = 0;
        v18 = (_BYTE *)(v10 + (unsigned int)(v4 + v6));
        v19 = 0;
        if ( *v18 == 45 )
        {
          LOBYTE(v7) = 45;
          jsonAppendChar(a3, v7);
          v20 = 3;
        }
        else
        {
          v21 = 2;
          if ( *v18 == 43 )
            v21 = 3;
          v20 = v21;
        }
        while ( v20 < v11 )
        {
          v22 = (unsigned __int8)v18[v20];
          if ( (*((_BYTE *)&qword_1800ADE90 + v22) & 8) == 0 )
          {
            *(_BYTE *)(a3 + 33) |= 2u;
            break;
          }
          if ( v17 < 0x1000000000000000LL )
            v17 = (((_BYTE)v22 - 7 * (((char)v22 >> 6) & 1)) & 0xF) + 16 * v17;
          else
            v19 = 1;
          ++v20;
        }
        v23 = "9.0e999";
        if ( !v19 )
          v23 = "%llu";
        jsonPrintf(100, a3, v23, v17);
        return (unsigned int)v4 + v11 + v8;
      }
      goto LABEL_52;
    }
    if ( v16 != 1 )
      goto LABEL_52;
  }
  if ( !v51 )
  {
LABEL_52:
    *(_BYTE *)(a3 + 33) |= 2u;
    return (unsigned int)v4 + v11 + v8;
  }
  jsonAppendRaw(a3, v10 + (unsigned int)(v4 + v6), v51);
  return (unsigned int)v4 + v11 + v8;
}

```

## disassembly

```asm
0x1800696ac  mov     rax, rsp
0x1800696af  push    rbx
0x1800696b0  push    rbp
0x1800696b1  push    rsi
0x1800696b2  push    rdi
0x1800696b3  push    r12
0x1800696b5  push    r13
0x1800696b7  push    r14
0x1800696b9  push    r15
0x1800696bb  sub     rsp, 28h
0x1800696bf  mov     rdi, r8
0x1800696c2  mov     r15d, edx
0x1800696c5  lea     r8, [rax+20h]
0x1800696c9  mov     dword ptr [rax+20h], 0
0x1800696d0  mov     r14, rcx
0x1800696d3  call    jsonbPayloadSize
0x1800696d8  mov     r13d, eax
0x1800696db  test    eax, eax
0x1800696dd  jnz     short loc_1800696EE
0x1800696df  or      byte ptr [rdi+21h], 2
0x1800696e3  mov     eax, [r14+8]
0x1800696e7  inc     eax
0x1800696e9  jmp     loc_180069BC4
0x1800696ee  mov     r8, [r14]
0x1800696f1  mov     esi, [rsp+68h+arg_18]
0x1800696f8  movzx   ecx, byte ptr [r15+r8]
0x1800696fd  and     ecx, 0Fh
0x180069700  cmp     ecx, 6
0x180069703  ja      loc_1800698DD
0x180069709  jz      loc_180069854
0x18006970f  test    ecx, ecx
0x180069711  jz      loc_180069836
0x180069717  sub     ecx, 1
0x18006971a  jz      loc_18006982D
0x180069720  sub     ecx, 1
0x180069723  jz      loc_18006981E
0x180069729  sub     ecx, 1
0x18006972c  jz      short loc_18006973C
0x18006972e  sub     ecx, 1
0x180069731  jz      short loc_18006975B
0x180069733  cmp     ecx, 1
0x180069736  jnz     loc_18006990B
0x18006973c  test    esi, esi
0x18006973e  jz      loc_18006990B
0x180069744  lea     edx, [r15+rax]
0x180069748  mov     rcx, rdi
0x18006974b  add     rdx, r8
0x18006974e  mov     r8d, esi
0x180069751  call    jsonAppendRaw
0x180069756  jmp     loc_180069BBD
0x18006975b  test    esi, esi
0x18006975d  jz      loc_18006990B
0x180069763  lea     r14d, [r15+rax]
0x180069767  xor     ebx, ebx
0x180069769  add     r14, r8
0x18006976c  xor     ebp, ebp
0x18006976e  cmp     byte ptr [r14], 2Dh ; '-'
0x180069772  jnz     short loc_180069784
0x180069774  mov     dl, 2Dh ; '-'
0x180069776  mov     rcx, rdi
0x180069779  call    jsonAppendChar
0x18006977e  lea     r12d, [rbx+3]
0x180069782  jmp     short loc_180069798
0x180069784  cmp     byte ptr [r14], 2Bh ; '+'
0x180069788  mov     eax, 2
0x18006978d  lea     r12d, [rax+1]
0x180069791  cmovz   eax, r12d
0x180069795  mov     r12d, eax
0x180069798  lea     rcx, __ImageBase
0x18006979f  cmp     r12d, esi
0x1800697a2  jnb     short loc_1800697F5
0x1800697a4  mov     eax, r12d
0x1800697a7  movzx   edx, byte ptr [rax+r14]
0x1800697ac  test    byte ptr [rdx+rcx+0ADE90h], 8
0x1800697b4  jz      short loc_1800697F1
0x1800697b6  mov     rax, 1000000000000000h
0x1800697c0  cmp     rbx, rax
0x1800697c3  jb      short loc_1800697CC
0x1800697c5  mov     ebp, 1
0x1800697ca  jmp     short loc_1800697EC
0x1800697cc  mov     al, dl
0x1800697ce  shl     rbx, 4
0x1800697d2  sar     al, 6
0x1800697d5  and     al, 1
0x1800697d7  movzx   eax, al
0x1800697da  imul    ecx, eax, 7
0x1800697dd  sub     dl, cl
0x1800697df  lea     rcx, __ImageBase
0x1800697e6  and     edx, 0Fh
0x1800697e9  add     rbx, rdx
0x1800697ec  inc     r12d
0x1800697ef  jmp     short loc_18006979F
0x1800697f1  or      byte ptr [rdi+21h], 2
0x1800697f5  test    ebp, ebp
0x1800697f7  lea     rax, aLlu_0; "%llu"
0x1800697fe  lea     r8, a90e999; "9.0e999"
0x180069805  mov     r9, rbx
0x180069808  cmovz   r8, rax
0x18006980c  mov     rdx, rdi
0x18006980f  mov     ecx, 64h ; 'd'
0x180069814  call    jsonPrintf
0x180069819  jmp     loc_180069BBD
0x18006981e  mov     r8d, 5
0x180069824  lea     rdx, aFalse; "false"
0x18006982b  jmp     short loc_180069843
0x18006982d  lea     rdx, aTrue; "true"
0x180069834  jmp     short loc_18006983D
0x180069836  lea     rdx, aNull_3; "null"
0x18006983d  mov     r8d, 4
0x180069843  mov     rcx, rdi
0x180069846  call    jsonAppendRawNZ
0x18006984b  lea     eax, [r15+1]
0x18006984f  jmp     loc_180069BC4
0x180069854  test    esi, esi
0x180069856  jz      loc_18006990B
0x18006985c  lea     r14d, [r15+rax]
0x180069860  xor     ebp, ebp
0x180069862  add     r14, r8
0x180069865  cmp     byte ptr [r14], 2Dh ; '-'
0x180069869  jnz     short loc_18006987A
0x18006986b  mov     dl, 2Dh ; '-'
0x18006986d  mov     rcx, rdi
0x180069870  call    jsonAppendChar
0x180069875  mov     ebp, 1
0x18006987a  mov     eax, ebp
0x18006987c  cmp     byte ptr [rax+r14], 2Eh ; '.'
0x180069881  jnz     short loc_18006988D
0x180069883  mov     dl, 30h ; '0'
0x180069885  mov     rcx, rdi
0x180069888  call    jsonAppendChar
0x18006988d  cmp     ebp, esi
0x18006988f  jnb     loc_180069BBD
0x180069895  lea     r12, __ImageBase
0x18006989c  mov     ebx, ebp
0x18006989e  mov     rcx, rdi
0x1800698a1  mov     dl, [rbx+r14]
0x1800698a5  call    jsonAppendChar
0x1800698aa  cmp     byte ptr [rbx+r14], 2Eh ; '.'
0x1800698af  jnz     short loc_1800698D2
0x1800698b1  lea     eax, [rbp+1]
0x1800698b4  cmp     eax, esi
0x1800698b6  jz      short loc_1800698C8
0x1800698b8  movzx   ecx, byte ptr [rax+r14]
0x1800698bd  test    byte ptr [rcx+r12+0ADE90h], 4
0x1800698c6  jnz     short loc_1800698D2
0x1800698c8  mov     dl, 30h ; '0'
0x1800698ca  mov     rcx, rdi
0x1800698cd  call    jsonAppendChar
0x1800698d2  inc     ebp
0x1800698d4  cmp     ebp, esi
0x1800698d6  jb      short loc_18006989C
0x1800698d8  jmp     loc_180069BBD
0x1800698dd  sub     ecx, 7
0x1800698e0  jz      loc_180069B97
0x1800698e6  sub     ecx, 1
0x1800698e9  jz      loc_180069B97
0x1800698ef  sub     ecx, 1
0x1800698f2  jz      loc_1800699E7
0x1800698f8  sub     ecx, 1
0x1800698fb  jz      loc_1800699D0
0x180069901  sub     ecx, 1
0x180069904  jz      short loc_180069981
0x180069906  cmp     ecx, 1
0x180069909  jz      short loc_180069914
0x18006990b  or      byte ptr [rdi+21h], 2
0x18006990f  jmp     loc_180069BBD
0x180069914  mov     dl, 7Bh ; '{'
0x180069916  mov     rcx, rdi
0x180069919  xor     r12d, r12d
0x18006991c  call    jsonAppendChar
0x180069921  lea     ebx, [r15+r13]
0x180069925  lea     ebp, [rbx+rsi]
0x180069928  cmp     ebx, ebp
0x18006992a  jnb     short loc_180069968
0x18006992c  cmp     byte ptr [rdi+21h], 0
0x180069930  jnz     short loc_180069960
0x180069932  mov     r8, rdi
0x180069935  mov     edx, ebx
0x180069937  mov     rcx, r14
0x18006993a  call    jsonTranslateBlobToText
0x18006993f  mov     ebx, eax
0x180069941  mov     rcx, rdi
0x180069944  mov     eax, r12d
0x180069947  inc     r12d
0x18006994a  and     eax, 1
0x18006994d  neg     eax
0x18006994f  sbb     dl, dl
0x180069951  and     dl, 0F2h
0x180069954  add     dl, 3Ah ; ':'
0x180069957  call    jsonAppendChar
0x18006995c  cmp     ebx, ebp
0x18006995e  jb      short loc_18006992C
0x180069960  test    r12b, 1
0x180069964  jnz     short loc_18006996A
0x180069966  cmp     ebx, ebp
0x180069968  jbe     short loc_18006996E
0x18006996a  or      byte ptr [rdi+21h], 2
0x18006996e  test    esi, esi
0x180069970  jz      short loc_18006997A
0x180069972  mov     rcx, rdi
0x180069975  call    jsonStringTrimOneChar
0x18006997a  mov     dl, 7Dh ; '}'
0x18006997c  jmp     loc_180069BB5
0x180069981  mov     dl, 5Bh ; '['
0x180069983  mov     rcx, rdi
0x180069986  call    jsonAppendChar
0x18006998b  lea     ebx, [r15+r13]
0x18006998f  lea     ebp, [rbx+rsi]
0x180069992  jmp     short loc_1800699B3
0x180069994  cmp     byte ptr [rdi+21h], 0
0x180069998  jnz     short loc_1800699BD
0x18006999a  mov     r8, rdi
0x18006999d  mov     edx, ebx
0x18006999f  mov     rcx, r14
0x1800699a2  call    jsonTranslateBlobToText
0x1800699a7  mov     dl, 2Ch ; ','
0x1800699a9  mov     rcx, rdi
0x1800699ac  mov     ebx, eax
0x1800699ae  call    jsonAppendChar
0x1800699b3  cmp     ebx, ebp
0x1800699b5  jb      short loc_180069994
0x1800699b7  jbe     short loc_1800699BD
0x1800699b9  or      byte ptr [rdi+21h], 2
0x1800699bd  test    esi, esi
0x1800699bf  jz      short loc_1800699C9
0x1800699c1  mov     rcx, rdi
0x1800699c4  call    jsonStringTrimOneChar
0x1800699c9  mov     dl, 5Dh ; ']'
0x1800699cb  jmp     loc_180069BB5
0x1800699d0  lea     edx, [r15+rax]
0x1800699d4  mov     rcx, rdi
0x1800699d7  add     rdx, r8
0x1800699da  mov     r8d, esi
0x1800699dd  call    jsonAppendString
0x1800699e2  jmp     loc_180069BBD
0x1800699e7  lea     r14d, [r15+rax]
0x1800699eb  mov     dl, 22h ; '"'
0x1800699ed  add     r14, r8
0x1800699f0  mov     rcx, rdi
0x1800699f3  mov     ebx, esi
0x1800699f5  call    jsonAppendChar
0x1800699fa  mov     r12d, 3
0x180069a00  lea     rdx, __ImageBase
0x180069a07  test    ebx, ebx
0x180069a09  jz      loc_180069BB3
0x180069a0f  xor     ebp, ebp
0x180069a11  movzx   ecx, byte ptr [rbp+r14+0]
0x180069a17  cmp     byte ptr [rcx+rdx+0BA610h], 0
0x180069a1f  jnz     short loc_180069A26
0x180069a21  cmp     cl, 27h ; '''
0x180069a24  jnz     short loc_180069A2C
0x180069a26  inc     ebp
0x180069a28  cmp     ebp, ebx
0x180069a2a  jb      short loc_180069A11
0x180069a2c  test    ebp, ebp
0x180069a2e  jz      short loc_180069A4D
0x180069a30  mov     r8d, ebp
0x180069a33  mov     rdx, r14
0x180069a36  mov     rcx, rdi
0x180069a39  call    jsonAppendRawNZ
0x180069a3e  cmp     ebp, ebx
0x180069a40  jnb     loc_180069BB3
0x180069a46  mov     eax, ebp
0x180069a48  add     r14, rax
0x180069a4b  sub     ebx, ebp
0x180069a4d  cmp     byte ptr [r14], 22h ; '"'
0x180069a51  jnz     short loc_180069A6F
0x180069a53  mov     r8d, 2
0x180069a59  lea     rdx, asc_1800B5E44; "\\\""
0x180069a60  mov     rcx, rdi
0x180069a63  call    jsonAppendRawNZ
0x180069a68  inc     r14
0x180069a6b  dec     ebx
0x180069a6d  jmp     short loc_180069A00
0x180069a6f  cmp     byte ptr [r14], 1Fh
0x180069a73  jg      short loc_180069AA5
0x180069a75  mov     rax, [rdi+18h]
0x180069a79  add     rax, 7
0x180069a7d  cmp     rax, [rdi+10h]
0x180069a81  jbe     short loc_180069A98
0x180069a83  mov     edx, 7
0x180069a88  mov     rcx, rdi
0x180069a8b  call    jsonStringGrow
0x180069a90  test    eax, eax
0x180069a92  jnz     loc_180069BB3
0x180069a98  mov     dl, [r14]
0x180069a9b  mov     rcx, rdi
0x180069a9e  call    jsonAppendControlChar
0x180069aa3  jmp     short loc_180069A68
0x180069aa5  cmp     ebx, 2
0x180069aa8  jb      loc_180069B91
0x180069aae  movzx   ecx, byte ptr [r14+1]
0x180069ab3  sub     ecx, 0Ah
0x180069ab6  jz      loc_180069B85
0x180069abc  sub     ecx, r12d
0x180069abf  jz      loc_180069B74
0x180069ac5  sub     ecx, 1Ah
0x180069ac8  jz      loc_180069B68
0x180069ace  sub     ecx, 9
0x180069ad1  jz      short loc_180069B51
  ... truncated ...
```
