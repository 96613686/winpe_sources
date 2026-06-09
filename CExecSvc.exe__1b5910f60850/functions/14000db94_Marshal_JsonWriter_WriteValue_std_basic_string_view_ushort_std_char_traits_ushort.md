# Marshal::JsonWriter::WriteValue(std::basic_string_view<ushort,std::char_traits<ushort>>)

- ea: `0x14000db94`
- end: `0x14000ddec`
- name: `?WriteValue@JsonWriter@Marshal@@QEAAXV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z`
- size: `600`
- prototype: `void **__fastcall(void ***, __int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1400062f0`
- `0x1400065b0`

## callees

- `0x1400073c4`
- `0x14000894c`
- `0x14000db94`

## pseudocode

```c
void **__fastcall Marshal::JsonWriter::WriteValue(void ***a1, __int64 *a2)
{
  void **v4; // rcx
  unsigned __int64 v5; // r8
  bool v6; // cc
  unsigned __int64 v7; // r14
  __int64 v8; // rdi
  unsigned __int64 i; // rbp
  unsigned __int64 v10; // rdx
  void **v11; // rcx
  __int16 v12; // r9
  void **v13; // rcx
  unsigned __int16 v14; // ax
  unsigned __int64 v15; // rdx
  __int16 v16; // r9
  void **v17; // rcx
  unsigned __int64 v18; // rdx
  wchar_t *v19; // rdx
  void **v20; // rcx
  unsigned __int64 v21; // rdx
  void **result; // rax

  v4 = *a1;
  v5 = (unsigned __int64)v4[2];
  if ( v5 >= (unsigned __int64)v4[3] )
  {
    std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(v4, (__int64)a2, v5, 34);
  }
  else
  {
    v6 = (unsigned __int64)v4[3] <= 7;
    v4[2] = (void *)(v5 + 1);
    if ( !v6 )
      v4 = (void **)*v4;
    *(_DWORD *)((char *)v4 + 2 * v5) = 34;
  }
  v7 = a2[1];
  if ( v7 )
  {
    v8 = *a2;
    for ( i = 0; i < v7; ++i )
    {
      v10 = *(unsigned __int16 *)(v8 + 2 * i);
      if ( (unsigned int)v10 < 0x20 || (_WORD)v10 == 92 || (_WORD)v10 == 34 )
      {
        switch ( (_DWORD)v10 )
        {
          case 8:
            v19 = L"\\b";
            goto LABEL_45;
          case 9:
            v19 = L"\\t";
            goto LABEL_45;
          case 0xA:
            v19 = L"\\n";
            goto LABEL_45;
          case 0xC:
            v19 = L"\\f";
            goto LABEL_45;
          case 0xD:
            v19 = L"\\r";
LABEL_45:
            std::wstring::operator+=(*a1, v19);
            continue;
          case 0x22:
          case 0x5C:
            v17 = *a1;
            v18 = (unsigned __int64)(*a1)[2];
            if ( v18 >= (unsigned __int64)(*a1)[3] )
            {
              std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(
                v17,
                v18,
                v5,
                92);
            }
            else
            {
              v6 = (unsigned __int64)v17[3] <= 7;
              v17[2] = (void *)(v18 + 1);
              if ( !v6 )
                v17 = (void **)*v17;
              *(_DWORD *)((char *)v17 + 2 * v18) = 92;
            }
            v12 = *(_WORD *)(v8 + 2 * i);
            break;
          default:
            std::wstring::operator+=(*a1, L"\\u00");
            v13 = *a1;
            v14 = (unsigned __int8)*(_WORD *)(v8 + 2 * i) >> 4;
            v15 = (unsigned __int64)(*a1)[2];
            v16 = v14 + (v14 < 0xAu ? 48 : 87);
            if ( v15 >= (unsigned __int64)(*a1)[3] )
            {
              std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(
                v13,
                v15,
                v5,
                v16);
            }
            else
            {
              v6 = (unsigned __int64)v13[3] <= 7;
              v13[2] = (void *)(v15 + 1);
              if ( !v6 )
                v13 = (void **)*v13;
              *((_WORD *)v13 + v15) = v16;
              *((_WORD *)v13 + v15 + 1) = 0;
            }
            v12 = (*(_WORD *)(v8 + 2 * i) & 0xF) + ((*(_WORD *)(v8 + 2 * i) & 0xFu) < 0xA ? 48 : 87);
            break;
        }
        v11 = *a1;
        v10 = (unsigned __int64)(*a1)[2];
        if ( v10 < (unsigned __int64)(*a1)[3] )
        {
          v11[2] = (void *)(v10 + 1);
          if ( (unsigned __int64)v11[3] > 7 )
            v11 = (void **)*v11;
          *((_WORD *)v11 + v10) = v12;
          *((_WORD *)v11 + v10 + 1) = 0;
          continue;
        }
      }
      else
      {
        v11 = *a1;
        v5 = (unsigned __int64)(*a1)[2];
        if ( v5 < (unsigned __int64)(*a1)[3] )
        {
          v6 = (unsigned __int64)v11[3] <= 7;
          v11[2] = (void *)(v5 + 1);
          if ( !v6 )
            v11 = (void **)*v11;
          *((_WORD *)v11 + v5) = v10;
          *((_WORD *)v11 + v5 + 1) = 0;
          continue;
        }
        v12 = *(_WORD *)(v8 + 2 * i);
      }
      std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(v11, v10, v5, v12);
    }
  }
  v20 = *a1;
  v21 = (unsigned __int64)(*a1)[2];
  if ( v21 >= (unsigned __int64)(*a1)[3] )
    return std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(v20, v21, v5, 34);
  v6 = (unsigned __int64)v20[3] <= 7;
  result = (void **)(v21 + 1);
  v20[2] = (void *)(v21 + 1);
  if ( !v6 )
    v20 = (void **)*v20;
  *(_DWORD *)((char *)v20 + 2 * v21) = 34;
  return result;
}

```

## disassembly

```asm
0x14000db94  push    rbx
0x14000db96  push    rbp
0x14000db97  push    rsi
0x14000db98  push    rdi
0x14000db99  push    r14
0x14000db9b  push    r15
0x14000db9d  sub     rsp, 28h
0x14000dba1  mov     rbx, rcx
0x14000dba4  mov     rdi, rdx
0x14000dba7  mov     rcx, [rcx]; Src
0x14000dbaa  mov     r8, [rcx+10h]
0x14000dbae  cmp     r8, [rcx+18h]
0x14000dbb2  jnb     short loc_14000DBD1
0x14000dbb4  cmp     qword ptr [rcx+18h], 7
0x14000dbb9  lea     rax, [r8+1]
0x14000dbbd  mov     [rcx+10h], rax
0x14000dbc1  jbe     short loc_14000DBC6
0x14000dbc3  mov     rcx, [rcx]
0x14000dbc6  mov     esi, 22h ; '"'
0x14000dbcb  mov     [rcx+r8*2], esi
0x14000dbcf  jmp     short loc_14000DBDE
0x14000dbd1  mov     esi, 22h ; '"'
0x14000dbd6  mov     r9d, esi
0x14000dbd9  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x14000dbde  mov     r14, [rdi+8]
0x14000dbe2  test    r14, r14
0x14000dbe5  jz      loc_14000DDAF
0x14000dbeb  mov     rdi, [rdi]
0x14000dbee  xor     ebp, ebp
0x14000dbf0  lea     r15d, [rbp+5Ch]
0x14000dbf4  movzx   edx, word ptr [rdi+rbp*2]
0x14000dbf8  cmp     edx, 20h ; ' '
0x14000dbfb  jb      short loc_14000DC47
0x14000dbfd  cmp     dx, r15w
0x14000dc01  jz      short loc_14000DC47
0x14000dc03  cmp     dx, si
0x14000dc06  jz      short loc_14000DC47
0x14000dc08  mov     rcx, [rbx]; Src
0x14000dc0b  mov     r8, [rcx+10h]
0x14000dc0f  cmp     r8, [rcx+18h]
0x14000dc13  jnb     short loc_14000DC39
0x14000dc15  cmp     qword ptr [rcx+18h], 7
0x14000dc1a  lea     rax, [r8+1]
0x14000dc1e  mov     [rcx+10h], rax
0x14000dc22  jbe     short loc_14000DC27
0x14000dc24  mov     rcx, [rcx]
0x14000dc27  xor     eax, eax
0x14000dc29  mov     [rcx+r8*2], dx
0x14000dc2e  mov     [rcx+r8*2+2], ax
0x14000dc34  jmp     loc_14000DDA3
0x14000dc39  movzx   r9d, dx
0x14000dc3d  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x14000dc42  jmp     loc_14000DDA3
0x14000dc47  mov     ecx, edx
0x14000dc49  sub     ecx, 8
0x14000dc4c  jz      loc_14000DD94
0x14000dc52  sub     ecx, 1
0x14000dc55  jz      loc_14000DD8B
0x14000dc5b  sub     ecx, 1
0x14000dc5e  jz      loc_14000DD82
0x14000dc64  sub     ecx, 2
0x14000dc67  jz      loc_14000DD79
0x14000dc6d  sub     ecx, 1
0x14000dc70  jz      loc_14000DD70
0x14000dc76  sub     ecx, 15h
0x14000dc79  jz      loc_14000DD3C
0x14000dc7f  cmp     ecx, 3Ah ; ':'
0x14000dc82  jz      loc_14000DD3C
0x14000dc88  mov     rcx, [rbx]; Src
0x14000dc8b  lea     rdx, aU00; "\\u00"
0x14000dc92  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x14000dc97  mov     rcx, [rbx]; Src
0x14000dc9a  movzx   eax, word ptr [rdi+rbp*2]
0x14000dc9e  shr     ax, 4
0x14000dca2  and     ax, 0Fh
0x14000dca6  mov     rdx, [rcx+10h]
0x14000dcaa  cmp     ax, 0Ah
0x14000dcae  sbb     r9w, r9w
0x14000dcb2  and     r9w, 0FFD9h
0x14000dcb8  add     r9w, 57h ; 'W'
0x14000dcbd  add     r9w, ax
0x14000dcc1  cmp     rdx, [rcx+18h]
0x14000dcc5  jnb     short loc_14000DCE7
0x14000dcc7  cmp     qword ptr [rcx+18h], 7
0x14000dccc  lea     rax, [rdx+1]
0x14000dcd0  mov     [rcx+10h], rax
0x14000dcd4  jbe     short loc_14000DCD9
0x14000dcd6  mov     rcx, [rcx]
0x14000dcd9  xor     eax, eax
0x14000dcdb  mov     [rcx+rdx*2], r9w
0x14000dce0  mov     [rcx+rdx*2+2], ax
0x14000dce5  jmp     short loc_14000DCEC
0x14000dce7  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x14000dcec  movzx   eax, word ptr [rdi+rbp*2]
0x14000dcf0  and     ax, 0Fh
0x14000dcf4  cmp     ax, 0Ah
0x14000dcf8  sbb     r9w, r9w
0x14000dcfc  and     r9w, 0FFD9h
0x14000dd02  add     r9w, 57h ; 'W'
0x14000dd07  add     r9w, ax
0x14000dd0b  mov     rcx, [rbx]
0x14000dd0e  mov     rdx, [rcx+10h]
0x14000dd12  cmp     rdx, [rcx+18h]
0x14000dd16  jnb     loc_14000DC3D
0x14000dd1c  lea     rax, [rdx+1]
0x14000dd20  mov     [rcx+10h], rax
0x14000dd24  cmp     qword ptr [rcx+18h], 7
0x14000dd29  jbe     short loc_14000DD2E
0x14000dd2b  mov     rcx, [rcx]
0x14000dd2e  xor     eax, eax
0x14000dd30  mov     [rcx+rdx*2], r9w
0x14000dd35  mov     [rcx+rdx*2+2], ax
0x14000dd3a  jmp     short loc_14000DDA3
0x14000dd3c  mov     rcx, [rbx]; Src
0x14000dd3f  mov     rdx, [rcx+10h]
0x14000dd43  cmp     rdx, [rcx+18h]
0x14000dd47  jnb     short loc_14000DD61
0x14000dd49  cmp     qword ptr [rcx+18h], 7
0x14000dd4e  lea     rax, [rdx+1]
0x14000dd52  mov     [rcx+10h], rax
0x14000dd56  jbe     short loc_14000DD5B
0x14000dd58  mov     rcx, [rcx]
0x14000dd5b  mov     [rcx+rdx*2], r15d
0x14000dd5f  jmp     short loc_14000DD69
0x14000dd61  mov     r9d, r15d
0x14000dd64  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x14000dd69  movzx   r9d, word ptr [rdi+rbp*2]
0x14000dd6e  jmp     short loc_14000DD0B
0x14000dd70  lea     rdx, aR; "\\r"
0x14000dd77  jmp     short loc_14000DD9B
0x14000dd79  lea     rdx, asc_140027828; "\\f"
0x14000dd80  jmp     short loc_14000DD9B
0x14000dd82  lea     rdx, aN; "\\n"
0x14000dd89  jmp     short loc_14000DD9B
0x14000dd8b  lea     rdx, aT; "\\t"
0x14000dd92  jmp     short loc_14000DD9B
0x14000dd94  lea     rdx, aB; "\\b"
0x14000dd9b  mov     rcx, [rbx]; Src
0x14000dd9e  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x14000dda3  inc     rbp
0x14000dda6  cmp     rbp, r14
0x14000dda9  jb      loc_14000DBF4
0x14000ddaf  mov     rcx, [rbx]; Src
0x14000ddb2  mov     rdx, [rcx+10h]
0x14000ddb6  cmp     rdx, [rcx+18h]
0x14000ddba  jnb     short loc_14000DDD7
0x14000ddbc  cmp     qword ptr [rcx+18h], 7
0x14000ddc1  lea     rax, [rdx+1]
0x14000ddc5  mov     [rcx+10h], rax
0x14000ddc9  jbe     short loc_14000DDCE
0x14000ddcb  mov     rcx, [rcx]
0x14000ddce  mov     dword ptr [rcx+rdx*2], 22h ; '"'
0x14000ddd5  jmp     short loc_14000DDDF
0x14000ddd7  mov     r9d, esi
0x14000ddda  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x14000dddf  add     rsp, 28h
0x14000dde3  pop     r15
0x14000dde5  pop     r14
0x14000dde7  pop     rdi
0x14000dde8  pop     rsi
0x14000dde9  pop     rbp
0x14000ddea  pop     rbx
0x14000ddeb  retn
```
