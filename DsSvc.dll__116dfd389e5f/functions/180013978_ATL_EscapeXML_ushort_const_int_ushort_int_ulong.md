# ATL::EscapeXML(ushort const *,int,ushort *,int,ulong)

- ea: `0x180013978`
- end: `0x180013be9`
- name: `?EscapeXML@ATL@@YAHPEBGHPEAGHK@Z`
- size: `625`
- prototype: `int(const unsigned __int16 *, int, unsigned __int16 *, int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180014050`

## callees

- `0x180013948`
- `0x180013978`
- `0x1800143c4`
- `0x18001445c`
- `0x18001b340`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180013ad7`
- `msvcrt!swprintf_s` at `0x180013ad7`

## pseudocode

```c
__int64 __fastcall ATL::EscapeXML(const unsigned __int16 *a1, int a2, ATL::Checked *a3, int a4)
{
  int v6; // r15d
  const unsigned __int16 *v7; // r14
  unsigned int v8; // esi
  unsigned __int16 v9; // bp
  int v10; // edx
  unsigned __int16 v11; // ax
  int v12; // ecx
  unsigned __int16 v13; // cx
  unsigned __int64 Buffer[3]; // [rsp+20h] [rbp-58h] BYREF

  v6 = a2;
  v7 = a1;
  if ( !a1 )
    ATL::AtlThrowImpl(-2147467259);
  v8 = 0;
  v9 = 0;
  if ( a2 )
  {
    while ( 1 )
    {
      v10 = *v7;
      --v6;
      if ( v10 == 34 )
        goto LABEL_18;
      if ( *v7 == 38 )
      {
        if ( a3 && a4 > 4 )
        {
          ATL::Checked::memcpy_s(a3, (void *)(2LL * a4), (unsigned __int64)L"&amp;", (const void *)0xA, Buffer[0]);
          a3 = (ATL::Checked *)((char *)a3 + 10);
        }
        v12 = 5;
        goto LABEL_45;
      }
      if ( *v7 == 39 || *v7 != 60 && *v7 != 62 )
      {
LABEL_18:
        if ( (unsigned __int16)(v10 + 10240) > 0x3FFu )
        {
          if ( !v9 )
            goto LABEL_36;
          if ( (unsigned __int16)(v10 + 9216) > 0x3FFu )
          {
            if ( a3 && a4 > 7 )
            {
              ATL::_AtlCopyNCR(v9, (unsigned __int16 *)a3);
              a3 = (ATL::Checked *)((char *)a3 + 16);
            }
            v8 += 8;
            v9 = 0;
            a4 -= 8;
LABEL_36:
            v13 = *v7;
            if ( (unsigned __int16)(*v7 - 32) > 0x5Eu )
            {
              if ( a3 && a4 > 7 )
              {
                ATL::_AtlCopyNCR(v13, (unsigned __int16 *)a3);
                a3 = (ATL::Checked *)((char *)a3 + 16);
              }
              v12 = 8;
            }
            else
            {
              if ( a3 && a4 > 0 )
              {
                *(_WORD *)a3 = v13;
                a3 = (ATL::Checked *)((char *)a3 + 2);
              }
              v12 = 1;
            }
            goto LABEL_45;
          }
          if ( a3 && a4 > 9 )
          {
            swprintf_s((wchar_t *const)Buffer, 0xBu, L"&#x%06X;", v10 - 56613888 + (v9 << 10));
            ATL::Checked::memcpy_s(a3, (void *)0x16, (unsigned __int64)Buffer, (const void *)0x14, Buffer[0]);
            a3 = (ATL::Checked *)((char *)a3 + 20);
          }
          v12 = 10;
          v9 = 0;
        }
        else
        {
          if ( v9 )
          {
            if ( a3 && a4 > 7 )
            {
              ATL::_AtlCopyNCR(v9, (unsigned __int16 *)a3);
              LOWORD(v10) = *v7;
              a3 = (ATL::Checked *)((char *)a3 + 16);
            }
            v12 = 8;
          }
          else
          {
            v12 = 0;
          }
          v9 = v10;
        }
      }
      else
      {
        if ( a3 && a4 > 3 )
        {
          *(_WORD *)a3 = 38;
          v11 = 108;
          if ( *v7 != 60 )
            v11 = 103;
          *((_WORD *)a3 + 1) = v11;
          *((_DWORD *)a3 + 1) = 3866740;
          a3 = (ATL::Checked *)((char *)a3 + 8);
        }
        v12 = 4;
      }
LABEL_45:
      a4 -= v12;
      v8 += v12;
      ++v7;
      if ( !v6 )
      {
        if ( v9 )
        {
          if ( (unsigned __int16)(v9 - 32) > 0x5Eu )
          {
            if ( a3 && a4 > 7 )
              ATL::_AtlCopyNCR(v9, (unsigned __int16 *)a3);
            a4 -= 8;
            v8 += 8;
          }
          else
          {
            if ( a3 && a4 > 0 )
              *(_WORD *)a3 = v9;
            --a4;
            ++v8;
          }
        }
        break;
      }
    }
  }
  if ( a3 && a4 < 0 )
    return 0;
  return v8;
}

```

## disassembly

```asm
0x180013978  push    rbx
0x18001397a  push    rbp
0x18001397b  push    rsi
0x18001397c  push    rdi
0x18001397d  push    r12
0x18001397f  push    r14
0x180013981  push    r15
0x180013983  sub     rsp, 40h
0x180013987  mov     rax, cs:__security_cookie
0x18001398e  xor     rax, rsp
0x180013991  mov     [rsp+78h+var_40], rax
0x180013996  xor     r12d, r12d
0x180013999  mov     edi, r9d
0x18001399c  mov     rbx, r8
0x18001399f  mov     r15d, edx
0x1800139a2  mov     r14, rcx
0x1800139a5  test    rcx, rcx
0x1800139a8  jz      loc_180013BDE
0x1800139ae  mov     esi, r12d
0x1800139b1  mov     ebp, r12d
0x1800139b4  test    edx, edx
0x1800139b6  jz      loc_180013BB5
0x1800139bc  mov     r8d, 3FFh
0x1800139c2  movzx   edx, word ptr [r14]
0x1800139c6  dec     r15d
0x1800139c9  mov     ecx, edx
0x1800139cb  sub     ecx, 22h ; '"'
0x1800139ce  jz      loc_180013A54
0x1800139d4  sub     ecx, 4
0x1800139d7  jz      short loc_180013A21
0x1800139d9  sub     ecx, 1
0x1800139dc  jz      short loc_180013A54
0x1800139de  sub     ecx, 15h
0x1800139e1  jz      short loc_1800139E8
0x1800139e3  cmp     ecx, 2
0x1800139e6  jnz     short loc_180013A54
0x1800139e8  test    rbx, rbx
0x1800139eb  jz      short loc_180013A17
0x1800139ed  cmp     edi, 3
0x1800139f0  jle     short loc_180013A17
0x1800139f2  mov     word ptr [rbx], 26h ; '&'
0x1800139f7  mov     eax, 6Ch ; 'l'
0x1800139fc  cmp     word ptr [r14], 3Ch ; '<'
0x180013a01  lea     ecx, [rax-5]
0x180013a04  cmovnz  ax, cx
0x180013a08  mov     [rbx+2], ax
0x180013a0c  mov     dword ptr [rbx+4], 3B0074h
0x180013a13  add     rbx, 8
0x180013a17  mov     ecx, 4
0x180013a1c  jmp     loc_180013B63
0x180013a21  test    rbx, rbx
0x180013a24  jz      short loc_180013A4A
0x180013a26  cmp     edi, 4
0x180013a29  jle     short loc_180013A4A
0x180013a2b  movsxd  rdx, edi
0x180013a2e  lea     r8, aAmp; "&amp;"
0x180013a35  add     rdx, rdx; void *
0x180013a38  mov     r9d, 0Ah; void *
0x180013a3e  mov     rcx, rbx; this
0x180013a41  call    ?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)
0x180013a46  add     rbx, 0Ah
0x180013a4a  mov     ecx, 5
0x180013a4f  jmp     loc_180013B63
0x180013a54  mov     eax, 2800h
0x180013a59  add     eax, edx
0x180013a5b  cmp     ax, r8w
0x180013a5f  ja      short loc_180013A95
0x180013a61  test    bp, bp
0x180013a64  jz      short loc_180013A8A
0x180013a66  test    rbx, rbx
0x180013a69  jz      short loc_180013A83
0x180013a6b  cmp     edi, 7
0x180013a6e  jle     short loc_180013A83
0x180013a70  mov     rdx, rbx; unsigned __int16 *
0x180013a73  movzx   ecx, bp; unsigned __int16
0x180013a76  call    ?_AtlCopyNCR@ATL@@YAHGPEAG@Z; ATL::_AtlCopyNCR(ushort,ushort *)
0x180013a7b  movzx   edx, word ptr [r14]
0x180013a7f  add     rbx, 10h
0x180013a83  mov     ecx, 8
0x180013a88  jmp     short loc_180013A8D
0x180013a8a  mov     ecx, r12d
0x180013a8d  movzx   ebp, dx
0x180013a90  jmp     loc_180013B63
0x180013a95  test    bp, bp
0x180013a98  jz      loc_180013B24
0x180013a9e  mov     eax, 2400h
0x180013aa3  add     eax, edx
0x180013aa5  cmp     ax, r8w
0x180013aa9  ja      short loc_180013B02
0x180013aab  test    rbx, rbx
0x180013aae  jz      short loc_180013AF8
0x180013ab0  cmp     edi, 9
0x180013ab3  jle     short loc_180013AF8
0x180013ab5  add     edx, 0FCA02400h
0x180013abb  movzx   r9d, bp
0x180013abf  shl     r9d, 0Ah
0x180013ac3  lea     r8, aX06x; "&#x%06X;"
0x180013aca  add     r9d, edx
0x180013acd  lea     rcx, [rsp+78h+Buffer]; Buffer
0x180013ad2  mov     edx, 0Bh; BufferCount
0x180013ad7  call    cs:__imp_swprintf_s
0x180013add  mov     r9d, 14h; void *
0x180013ae3  lea     r8, [rsp+78h+Buffer]; unsigned __int64
0x180013ae8  mov     rcx, rbx; this
0x180013aeb  lea     edx, [r9+2]; void *
0x180013aef  call    ?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)
0x180013af4  add     rbx, 14h
0x180013af8  mov     ecx, 0Ah
0x180013afd  mov     ebp, r12d
0x180013b00  jmp     short loc_180013B63
0x180013b02  test    rbx, rbx
0x180013b05  jz      short loc_180013B1B
0x180013b07  cmp     edi, 7
0x180013b0a  jle     short loc_180013B1B
0x180013b0c  mov     rdx, rbx; unsigned __int16 *
0x180013b0f  movzx   ecx, bp; unsigned __int16
0x180013b12  call    ?_AtlCopyNCR@ATL@@YAHGPEAG@Z; ATL::_AtlCopyNCR(ushort,ushort *)
0x180013b17  add     rbx, 10h
0x180013b1b  add     esi, 8
0x180013b1e  mov     ebp, r12d
0x180013b21  sub     edi, 8
0x180013b24  movzx   ecx, word ptr [r14]; unsigned __int16
0x180013b28  lea     eax, [rcx-20h]
0x180013b2b  cmp     ax, 5Eh ; '^'
0x180013b2f  ja      short loc_180013B48
0x180013b31  test    rbx, rbx
0x180013b34  jz      short loc_180013B41
0x180013b36  test    edi, edi
0x180013b38  jle     short loc_180013B41
0x180013b3a  mov     [rbx], cx
0x180013b3d  add     rbx, 2
0x180013b41  mov     ecx, 1
0x180013b46  jmp     short loc_180013B63
0x180013b48  test    rbx, rbx
0x180013b4b  jz      short loc_180013B5E
0x180013b4d  cmp     edi, 7
0x180013b50  jle     short loc_180013B5E
0x180013b52  mov     rdx, rbx; unsigned __int16 *
0x180013b55  call    ?_AtlCopyNCR@ATL@@YAHGPEAG@Z; ATL::_AtlCopyNCR(ushort,ushort *)
0x180013b5a  add     rbx, 10h
0x180013b5e  mov     ecx, 8
0x180013b63  sub     edi, ecx
0x180013b65  add     esi, ecx
0x180013b67  add     r14, 2
0x180013b6b  mov     r8d, 3FFh
0x180013b71  test    r15d, r15d
0x180013b74  jnz     loc_1800139C2
0x180013b7a  test    bp, bp
0x180013b7d  jz      short loc_180013BB5
0x180013b7f  lea     eax, [rbp-20h]
0x180013b82  cmp     ax, 5Eh ; '^'
0x180013b86  ja      short loc_180013B9A
0x180013b88  test    rbx, rbx
0x180013b8b  jz      short loc_180013B94
0x180013b8d  test    edi, edi
0x180013b8f  jle     short loc_180013B94
0x180013b91  mov     [rbx], bp
0x180013b94  dec     edi
0x180013b96  inc     esi
0x180013b98  jmp     short loc_180013BB5
0x180013b9a  test    rbx, rbx
0x180013b9d  jz      short loc_180013BAF
0x180013b9f  cmp     edi, 7
0x180013ba2  jle     short loc_180013BAF
0x180013ba4  mov     rdx, rbx; unsigned __int16 *
0x180013ba7  movzx   ecx, bp; unsigned __int16
0x180013baa  call    ?_AtlCopyNCR@ATL@@YAHGPEAG@Z; ATL::_AtlCopyNCR(ushort,ushort *)
0x180013baf  sub     edi, 8
0x180013bb2  add     esi, 8
0x180013bb5  test    rbx, rbx
0x180013bb8  jz      short loc_180013BC0
0x180013bba  test    edi, edi
0x180013bbc  cmovs   esi, r12d
0x180013bc0  mov     eax, esi
0x180013bc2  mov     rcx, [rsp+78h+var_40]
0x180013bc7  xor     rcx, rsp; StackCookie
0x180013bca  call    __security_check_cookie
0x180013bcf  add     rsp, 40h
0x180013bd3  pop     r15
0x180013bd5  pop     r14
0x180013bd7  pop     r12
0x180013bd9  pop     rdi
0x180013bda  pop     rsi
0x180013bdb  pop     rbp
0x180013bdc  pop     rbx
0x180013bdd  retn
0x180013bde  mov     ecx, 80004005h; int
0x180013be3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
