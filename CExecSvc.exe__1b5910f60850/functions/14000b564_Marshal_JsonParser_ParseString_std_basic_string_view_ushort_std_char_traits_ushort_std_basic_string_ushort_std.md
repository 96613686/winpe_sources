# Marshal::JsonParser::ParseString(std::basic_string_view<ushort,std::char_traits<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,bool)

- ea: `0x14000b564`
- end: `0x14000b8c0`
- name: `?ParseString@JsonParser@Marshal@@SA_KV?$basic_string_view@GU?$char_traits@G@std@@@std@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@_N@Z`
- size: `860`
- prototype: `unsigned __int64 __fastcall(__int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000b4ac`

## callees

- `0x140002ed8`
- `0x1400073c4`
- `0x14000b564`

## pseudocode

```c
unsigned __int64 __fastcall Marshal::JsonParser::ParseString(__int64 a1, unsigned __int64 a2)
{
  unsigned __int64 v2; // rbx
  unsigned __int64 i; // rdi
  _WORD *v5; // r8
  int v6; // r9d
  int v7; // r9d
  int v8; // ecx
  int v9; // r9d
  int v10; // ecx
  int v11; // r10d
  int v12; // ecx
  int v13; // edx
  int v14; // ecx
  int v15; // eax
  __int16 v16; // r9
  __int16 v17; // r9
  bool v18; // cc
  _WORD *v19; // rcx
  __int64 v20; // rax
  unsigned __int64 v21; // rcx
  unsigned __int64 v22; // rcx
  _DWORD pExceptionObject[10]; // [rsp+20h] [rbp-28h] BYREF

  v2 = a2;
  if ( !*(_QWORD *)(a1 + 8) || **(_WORD **)a1 != 34 )
  {
    pExceptionObject[0] = 4;
    throw (Marshal::JsonParser::ParseException *)pExceptionObject;
  }
  for ( i = 1; ; i += v20 )
  {
    if ( i >= *(_QWORD *)(a1 + 8) )
    {
      pExceptionObject[0] = 1;
      throw (Marshal::JsonParser::ParseException *)pExceptionObject;
    }
    v5 = *(_WORD **)a1;
    v6 = *(unsigned __int16 *)(*(_QWORD *)a1 + 2 * i);
    if ( v6 == 34 )
      break;
    if ( v6 != 92 )
    {
      v22 = *(_QWORD *)(v2 + 16);
      if ( v22 >= *(_QWORD *)(v2 + 24) )
      {
        std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(
          (void **)v2,
          a2,
          (__int64)v5,
          v6);
      }
      else
      {
        v18 = *(_QWORD *)(v2 + 24) <= 7u;
        *(_QWORD *)(v2 + 16) = v22 + 1;
        if ( v18 )
          a2 = v2;
        else
          a2 = *(_QWORD *)v2;
        *(_WORD *)(a2 + 2 * v22) = v6;
        *(_WORD *)(a2 + 2 * v22 + 2) = 0;
      }
      v20 = 1;
      continue;
    }
    if ( i + 1 >= *(_QWORD *)(a1 + 8) )
      goto LABEL_82;
    v7 = (unsigned __int16)v5[i + 1];
    if ( v7 == 117 )
    {
      if ( i + 2 >= *(_QWORD *)(a1 + 8) )
        goto LABEL_15;
      v8 = (unsigned __int16)v5[i + 2];
      v9 = v8 - 48;
      if ( (unsigned int)(v8 - 48) <= 9 )
        goto LABEL_16;
      if ( (unsigned int)(v8 - 65) <= 5 )
      {
        v9 = v8 - 55;
        goto LABEL_16;
      }
      if ( (unsigned int)(v8 - 97) > 5 )
LABEL_15:
        v9 = -1;
      else
        v9 = v8 - 87;
LABEL_16:
      if ( i + 3 >= *(_QWORD *)(a1 + 8) )
        goto LABEL_22;
      v10 = (unsigned __int16)v5[i + 3];
      v11 = v10 - 48;
      if ( (unsigned int)(v10 - 48) <= 9 )
        goto LABEL_23;
      if ( (unsigned int)(v10 - 65) <= 5 )
      {
        v11 = v10 - 55;
        goto LABEL_23;
      }
      if ( (unsigned int)(v10 - 97) > 5 )
LABEL_22:
        v11 = -1;
      else
        v11 = v10 - 87;
LABEL_23:
      if ( i + 4 >= *(_QWORD *)(a1 + 8) )
        goto LABEL_29;
      v12 = (unsigned __int16)v5[i + 4];
      v13 = v12 - 48;
      if ( (unsigned int)(v12 - 48) <= 9 )
        goto LABEL_30;
      if ( (unsigned int)(v12 - 65) <= 5 )
      {
        v13 = v12 - 55;
        goto LABEL_30;
      }
      if ( (unsigned int)(v12 - 97) > 5 )
LABEL_29:
        v13 = -1;
      else
        v13 = v12 - 87;
LABEL_30:
      if ( i + 5 >= *(_QWORD *)(a1 + 8) )
        goto LABEL_36;
      v14 = (unsigned __int16)v5[i + 5];
      v15 = v14 - 48;
      if ( (unsigned int)(v14 - 48) <= 9 )
        goto LABEL_37;
      if ( (unsigned int)(v14 - 65) <= 5 )
      {
        v15 = v14 - 55;
        goto LABEL_37;
      }
      if ( (unsigned int)(v14 - 97) > 5 )
LABEL_36:
        v15 = -1;
      else
        v15 = v14 - 87;
LABEL_37:
      if ( v9 < 0 || v11 < 0 || v13 < 0 || v15 < 0 )
      {
        pExceptionObject[0] = 13;
        throw (Marshal::JsonParser::ParseException *)pExceptionObject;
      }
      v16 = v13 | (16 * (v11 | (16 * v9)));
      a2 = *(_QWORD *)(v2 + 16);
      v17 = v15 | (16 * v16);
      if ( a2 >= *(_QWORD *)(v2 + 24) )
      {
        std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(
          (void **)v2,
          a2,
          (__int64)v5,
          v17);
      }
      else
      {
        v18 = *(_QWORD *)(v2 + 24) <= 7u;
        *(_QWORD *)(v2 + 16) = a2 + 1;
        if ( v18 )
          v19 = (_WORD *)v2;
        else
          v19 = *(_WORD **)v2;
        v19[a2] = v17;
        v19[a2 + 1] = 0;
      }
      v20 = 6;
      continue;
    }
    if ( v7 != 34 )
    {
      if ( v7 == 39 )
      {
        pExceptionObject[0] = 13;
        throw (Marshal::JsonParser::ParseException *)pExceptionObject;
      }
      if ( v7 != 47 && v7 != 92 )
      {
        switch ( v7 )
        {
          case 'b':
            LOWORD(v7) = 8;
            break;
          case 'f':
            LOWORD(v7) = 12;
            break;
          case 'n':
            LOWORD(v7) = 10;
            break;
          case 'r':
            LOWORD(v7) = 13;
            break;
          case 't':
            LOWORD(v7) = 9;
            break;
          default:
LABEL_82:
            pExceptionObject[0] = 13;
            throw (Marshal::JsonParser::ParseException *)pExceptionObject;
        }
      }
    }
    v21 = *(_QWORD *)(v2 + 16);
    if ( v21 >= *(_QWORD *)(v2 + 24) )
    {
      std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(
        (void **)v2,
        a2,
        (__int64)v5,
        v7);
    }
    else
    {
      v18 = *(_QWORD *)(v2 + 24) <= 7u;
      *(_QWORD *)(v2 + 16) = v21 + 1;
      if ( v18 )
        a2 = v2;
      else
        a2 = *(_QWORD *)v2;
      *(_WORD *)(a2 + 2 * v21) = v7;
      *(_WORD *)(a2 + 2 * v21 + 2) = 0;
    }
    v20 = 2;
  }
  return i + 1;
}

```

## disassembly

```asm
0x14000b564  mov     [rsp+arg_0], rbx
0x14000b569  mov     [rsp+arg_10], rsi
0x14000b56e  push    rdi
0x14000b56f  push    r13
0x14000b571  push    r15
0x14000b573  sub     rsp, 30h
0x14000b577  cmp     qword ptr [rcx+8], 0
0x14000b57c  mov     rbx, rdx
0x14000b57f  mov     rsi, rcx
0x14000b582  jbe     loc_14000B858
0x14000b588  mov     rax, [rcx]
0x14000b58b  mov     r13d, 22h ; '"'
0x14000b591  cmp     [rax], r13w
0x14000b595  jnz     loc_14000B858
0x14000b59b  lea     r15d, [r13-21h]
0x14000b59f  mov     edi, r15d
0x14000b5a2  cmp     rdi, [rsi+8]
0x14000b5a6  jnb     loc_14000B841
0x14000b5ac  mov     r8, [rsi]
0x14000b5af  movzx   r9d, word ptr [r8+rdi*2]
0x14000b5b4  cmp     r9d, r13d
0x14000b5b7  jz      loc_14000B829
0x14000b5bd  cmp     r9d, 27h ; '''
0x14000b5c1  jz      loc_14000B7E7
0x14000b5c7  cmp     r9d, 5Ch ; '\'
0x14000b5cb  jnz     loc_14000B7E7
0x14000b5d1  lea     rax, [rdi+1]
0x14000b5d5  cmp     rax, [rsi+8]
0x14000b5d9  jnb     loc_14000B8A6
0x14000b5df  movzx   r9d, word ptr [r8+rax*2]
0x14000b5e4  cmp     r9d, 75h ; 'u'
0x14000b5e8  jnz     loc_14000B746
0x14000b5ee  lea     rax, [rdi+2]
0x14000b5f2  cmp     rax, [rsi+8]
0x14000b5f6  jnb     short loc_14000B623
0x14000b5f8  movzx   ecx, word ptr [r8+rax*2]
0x14000b5fd  lea     r9d, [rcx-30h]
0x14000b601  cmp     r9d, 9
0x14000b605  jbe     short loc_14000B627
0x14000b607  lea     eax, [rcx-41h]
0x14000b60a  cmp     eax, 5
0x14000b60d  ja      short loc_14000B615
0x14000b60f  lea     r9d, [rcx-37h]
0x14000b613  jmp     short loc_14000B627
0x14000b615  lea     eax, [rcx-61h]
0x14000b618  cmp     eax, 5
0x14000b61b  ja      short loc_14000B623
0x14000b61d  lea     r9d, [rcx-57h]
0x14000b621  jmp     short loc_14000B627
0x14000b623  or      r9d, 0FFFFFFFFh
0x14000b627  lea     rax, [rdi+3]
0x14000b62b  cmp     rax, [rsi+8]
0x14000b62f  jnb     short loc_14000B65C
0x14000b631  movzx   ecx, word ptr [r8+rax*2]
0x14000b636  lea     r10d, [rcx-30h]
0x14000b63a  cmp     r10d, 9
0x14000b63e  jbe     short loc_14000B660
0x14000b640  lea     eax, [rcx-41h]
0x14000b643  cmp     eax, 5
0x14000b646  ja      short loc_14000B64E
0x14000b648  lea     r10d, [rcx-37h]
0x14000b64c  jmp     short loc_14000B660
0x14000b64e  lea     eax, [rcx-61h]
0x14000b651  cmp     eax, 5
0x14000b654  ja      short loc_14000B65C
0x14000b656  lea     r10d, [rcx-57h]
0x14000b65a  jmp     short loc_14000B660
0x14000b65c  or      r10d, 0FFFFFFFFh
0x14000b660  lea     rax, [rdi+4]
0x14000b664  cmp     rax, [rsi+8]
0x14000b668  jnb     short loc_14000B691
0x14000b66a  movzx   ecx, word ptr [r8+rax*2]
0x14000b66f  lea     edx, [rcx-30h]
0x14000b672  cmp     edx, 9
0x14000b675  jbe     short loc_14000B694
0x14000b677  lea     eax, [rcx-41h]
0x14000b67a  cmp     eax, 5
0x14000b67d  ja      short loc_14000B684
0x14000b67f  lea     edx, [rcx-37h]
0x14000b682  jmp     short loc_14000B694
0x14000b684  lea     eax, [rcx-61h]
0x14000b687  cmp     eax, 5
0x14000b68a  ja      short loc_14000B691
0x14000b68c  lea     edx, [rcx-57h]
0x14000b68f  jmp     short loc_14000B694
0x14000b691  or      edx, 0FFFFFFFFh
0x14000b694  lea     rax, [rdi+5]
0x14000b698  cmp     rax, [rsi+8]
0x14000b69c  jnb     short loc_14000B6C5
0x14000b69e  movzx   ecx, word ptr [r8+rax*2]
0x14000b6a3  lea     eax, [rcx-30h]
0x14000b6a6  cmp     eax, 9
0x14000b6a9  jbe     short loc_14000B6C8
0x14000b6ab  lea     eax, [rcx-41h]
0x14000b6ae  cmp     eax, 5
0x14000b6b1  ja      short loc_14000B6B8
0x14000b6b3  lea     eax, [rcx-37h]
0x14000b6b6  jmp     short loc_14000B6C8
0x14000b6b8  lea     eax, [rcx-61h]
0x14000b6bb  cmp     eax, 5
0x14000b6be  ja      short loc_14000B6C5
0x14000b6c0  lea     eax, [rcx-57h]
0x14000b6c3  jmp     short loc_14000B6C8
0x14000b6c5  or      eax, 0FFFFFFFFh
0x14000b6c8  test    r9d, r9d
0x14000b6cb  js      loc_14000B872
0x14000b6d1  test    r10d, r10d
0x14000b6d4  js      loc_14000B872
0x14000b6da  test    edx, edx
0x14000b6dc  js      loc_14000B872
0x14000b6e2  test    eax, eax
0x14000b6e4  js      loc_14000B872
0x14000b6ea  shl     r9w, 4
0x14000b6ef  or      r9w, r10w
0x14000b6f3  shl     r9w, 4
0x14000b6f8  or      r9w, dx
0x14000b6fc  mov     rdx, [rbx+10h]
0x14000b700  shl     r9w, 4
0x14000b705  or      r9w, ax
0x14000b709  cmp     rdx, [rbx+18h]
0x14000b70d  jnb     short loc_14000B734
0x14000b70f  cmp     qword ptr [rbx+18h], 7
0x14000b714  lea     rax, [rdx+1]
0x14000b718  mov     [rbx+10h], rax
0x14000b71c  jbe     short loc_14000B723
0x14000b71e  mov     rcx, [rbx]
0x14000b721  jmp     short loc_14000B726
0x14000b723  mov     rcx, rbx
0x14000b726  xor     eax, eax
0x14000b728  mov     [rcx+rdx*2], r9w
0x14000b72d  mov     [rcx+rdx*2+2], ax
0x14000b732  jmp     short loc_14000B73C
0x14000b734  mov     rcx, rbx; Src
0x14000b737  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x14000b73c  mov     eax, 6
0x14000b741  jmp     loc_14000B821
0x14000b746  cmp     r9d, r13d
0x14000b749  jz      short loc_14000B7A9
0x14000b74b  cmp     r9d, 27h ; '''
0x14000b74f  jz      loc_14000B88C
0x14000b755  cmp     r9d, 2Fh ; '/'
0x14000b759  jz      short loc_14000B7A9
0x14000b75b  cmp     r9d, 5Ch ; '\'
0x14000b75f  jz      short loc_14000B7A9
0x14000b761  cmp     r9d, 62h ; 'b'
0x14000b765  jz      short loc_14000B7A3
0x14000b767  cmp     r9d, 66h ; 'f'
0x14000b76b  jz      short loc_14000B79B
0x14000b76d  cmp     r9d, 6Eh ; 'n'
0x14000b771  jz      short loc_14000B793
0x14000b773  cmp     r9d, 72h ; 'r'
0x14000b777  jz      short loc_14000B78B
0x14000b779  cmp     r9d, 74h ; 't'
0x14000b77d  jnz     loc_14000B8A6
0x14000b783  mov     r9d, 9
0x14000b789  jmp     short loc_14000B7A9
0x14000b78b  mov     r9d, 0Dh
0x14000b791  jmp     short loc_14000B7A9
0x14000b793  mov     r9d, 0Ah
0x14000b799  jmp     short loc_14000B7A9
0x14000b79b  mov     r9d, 0Ch
0x14000b7a1  jmp     short loc_14000B7A9
0x14000b7a3  mov     r9d, 8
0x14000b7a9  mov     rcx, [rbx+10h]
0x14000b7ad  cmp     rcx, [rbx+18h]
0x14000b7b1  jnb     short loc_14000B7D8
0x14000b7b3  cmp     qword ptr [rbx+18h], 7
0x14000b7b8  lea     rax, [rcx+1]
0x14000b7bc  mov     [rbx+10h], rax
0x14000b7c0  jbe     short loc_14000B7C7
0x14000b7c2  mov     rdx, [rbx]
0x14000b7c5  jmp     short loc_14000B7CA
0x14000b7c7  mov     rdx, rbx
0x14000b7ca  xor     eax, eax
0x14000b7cc  mov     [rdx+rcx*2], r9w
0x14000b7d1  mov     [rdx+rcx*2+2], ax
0x14000b7d6  jmp     short loc_14000B7E0
0x14000b7d8  mov     rcx, rbx; Src
0x14000b7db  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x14000b7e0  mov     eax, 2
0x14000b7e5  jmp     short loc_14000B821
0x14000b7e7  mov     rcx, [rbx+10h]
0x14000b7eb  cmp     rcx, [rbx+18h]
0x14000b7ef  jnb     short loc_14000B816
0x14000b7f1  cmp     qword ptr [rbx+18h], 7
0x14000b7f6  lea     rax, [rcx+1]
0x14000b7fa  mov     [rbx+10h], rax
0x14000b7fe  jbe     short loc_14000B805
0x14000b800  mov     rdx, [rbx]
0x14000b803  jmp     short loc_14000B808
0x14000b805  mov     rdx, rbx
0x14000b808  xor     eax, eax
0x14000b80a  mov     [rdx+rcx*2], r9w
0x14000b80f  mov     [rdx+rcx*2+2], ax
0x14000b814  jmp     short loc_14000B81E
0x14000b816  mov     rcx, rbx; Src
0x14000b819  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x14000b81e  mov     rax, r15
0x14000b821  add     rdi, rax
0x14000b824  jmp     loc_14000B5A2
0x14000b829  mov     rbx, [rsp+48h+arg_0]
0x14000b82e  lea     rax, [rdi+1]
0x14000b832  mov     rsi, [rsp+48h+arg_10]
0x14000b837  add     rsp, 30h
0x14000b83b  pop     r15
0x14000b83d  pop     r13
0x14000b83f  pop     rdi
0x14000b840  retn
0x14000b841  lea     rdx, _TI1?AUParseException@JsonParser@Marshal@@; pThrowInfo
0x14000b848  mov     [rsp+48h+pExceptionObject], r15d
0x14000b84d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x14000b852  call    _CxxThrowException_0
0x14000b858  lea     rdx, _TI1?AUParseException@JsonParser@Marshal@@; pThrowInfo
0x14000b85f  mov     [rsp+48h+pExceptionObject], 4
0x14000b867  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x14000b86c  call    _CxxThrowException_0
0x14000b872  lea     rdx, _TI1?AUParseException@JsonParser@Marshal@@; pThrowInfo
0x14000b879  mov     [rsp+48h+pExceptionObject], 0Dh
0x14000b881  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x14000b886  call    _CxxThrowException_0
0x14000b88c  lea     rdx, _TI1?AUParseException@JsonParser@Marshal@@; pThrowInfo
0x14000b893  mov     [rsp+48h+pExceptionObject], 0Dh
0x14000b89b  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x14000b8a0  call    _CxxThrowException_0
0x14000b8a6  lea     rdx, _TI1?AUParseException@JsonParser@Marshal@@; pThrowInfo
0x14000b8ad  mov     [rsp+48h+pExceptionObject], 0Dh
0x14000b8b5  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x14000b8ba  call    _CxxThrowException_0
```
