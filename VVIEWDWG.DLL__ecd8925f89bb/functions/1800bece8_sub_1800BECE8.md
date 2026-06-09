# sub_1800BECE8

- ea: `0x1800bece8`
- end: `0x1800bef57`
- name: `sub_1800BECE8`
- size: `623`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1800140f4`

## callees

- `0x1800029e0`
- `0x180003300`
- `0x180009498`
- `0x18001c2e8`
- `0x18001f6ac`
- `0x1800bece0`
- `0x1800bece8`
- `0x1804c6020`

## import_xrefs

- `mfc140u!??_U@YAPEAX_K@Z` at `0x1800bee75`
- `mfc140u!??_U@YAPEAX_K@Z` at `0x1800bee75`
- `mfc140u!__imp_??_V@YAXPEAX@Z` at `0x1800bef0e`
- `mfc140u!__imp_??_V@YAXPEAX@Z` at `0x1800bef0e`
- `KERNEL32!lstrcmpiW` at `0x1800beec9`
- `KERNEL32!lstrcmpiW` at `0x1800beedd`
- `KERNEL32!lstrcmpiW` at `0x1800beec9`
- `KERNEL32!lstrcmpiW` at `0x1800beedd`
- `USER32!CharNextW` at `0x1800bed6a`
- `USER32!CharNextW` at `0x1800bed6a`
- `SHLWAPI!PathFindFileNameW` at `0x1800bed30`
- `SHLWAPI!PathFindFileNameW` at `0x1800bed30`

## pseudocode

```c
bool __fastcall sub_1800BECE8(const WCHAR *a1, __int64 a2)
{
  bool v4; // bl
  wchar_t *FileNameW; // rax
  const wchar_t *v6; // rdi
  wchar_t *v7; // rax
  LPWSTR v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // r8
  int v12; // r9d
  int v13; // esi
  unsigned __int64 v14; // r10
  unsigned __int64 v15; // rax
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rbx
  unsigned __int64 v18; // rax
  void *v19; // r15
  int v20; // eax
  const wchar_t *v21; // rbp
  _WORD v23[264]; // [rsp+20h] [rbp-258h] BYREF

  if ( !a1 || !a2 )
    return 0;
  v4 = 0;
  FileNameW = PathFindFileNameW(a1);
  v6 = FileNameW;
  if ( FileNameW )
  {
    if ( !sub_18001C2E8(FileNameW) )
    {
      v7 = wcsrchr(v6, 0x2Eu);
      if ( v7 )
      {
        v8 = CharNextW(v7);
        v9 = -1;
        do
          ++v9;
        while ( v8[v9] );
        if ( v9 == 3 )
        {
          v10 = *v8;
          v11 = 65503;
          v12 = 1;
          if ( (((_WORD)v10 - 83) & 0xFFDF) == 0 && ((v8[1] - 72) & 0xFFDF) == 0 && ((v8[2] - 88) & 0xFFDF) == 0 )
            v4 = 1;
          if ( (((_WORD)v10 - 83) & 0xFFDF) == 0 && ((v8[1] - 72) & 0xFFDF) == 0 && ((v8[2] - 80) & 0xFFDF) == 0 )
            v4 = 1;
          LOWORD(v10) = v10 - 70;
          if ( (v10 & 0xFFDF) == 0 && ((v8[1] - 77) & 0xFFDF) == 0 && ((v8[2] - 80) & 0xFFDF) == 0 )
            v4 = 1;
          if ( v4 )
          {
            v4 = 0;
            v13 = 0;
            do
            {
              if ( v13 >= 3 )
                break;
              v13 += v12;
              if ( (unsigned __int8)sub_1800029E0(v8, v10, v11) )
              {
                v15 = v14;
                do
                  ++v15;
                while ( v23[v15] );
                v16 = v14;
                do
                  ++v16;
                while ( v6[v16] );
                v17 = v15 + v16 + 1;
                v18 = 2 * v17;
                if ( !is_mul_ok(v17, 2u) )
                  v18 = v14;
                v19 = operator new[](v18);
                sub_180009498(v19, v23, v17);
                sub_180003300(v19, v17, v6);
                v20 = sub_18001F6AC(a2, v19, 0x8000);
                v4 = v20 >= 0;
                if ( v20 < 0 )
                {
                  v21 = L"ic-txt.shx";
                  if ( !lstrcmpiW(v6, L"extfont2.shx") || !lstrcmpiW(v6, L"@extfont2.shx") )
                    v21 = L"bigfont.shx";
                  sub_180009498(v6, v21, 260 - (v6 - a1));
                }
                operator delete[](v19);
                v12 = 1;
              }
            }
            while ( !v4 );
          }
        }
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1800bece8  mov     [rsp+arg_10], rbx
0x1800beced  push    rbp
0x1800becee  push    rsi
0x1800becef  push    rdi
0x1800becf0  push    r12
0x1800becf2  push    r13
0x1800becf4  push    r14
0x1800becf6  push    r15
0x1800becf8  sub     rsp, 240h
0x1800becff  mov     rax, cs:__security_cookie
0x1800bed06  xor     rax, rsp
0x1800bed09  mov     [rsp+278h+var_48], rax
0x1800bed11  xor     r13d, r13d
0x1800bed14  mov     r12, rdx
0x1800bed17  mov     r14, rcx
0x1800bed1a  test    rcx, rcx
0x1800bed1d  jz      loc_1800BEF2A
0x1800bed23  test    rdx, rdx
0x1800bed26  jz      loc_1800BEF2A
0x1800bed2c  movzx   ebx, r13b
0x1800bed30  call    cs:PathFindFileNameW
0x1800bed36  mov     rdi, rax
0x1800bed39  test    rax, rax
0x1800bed3c  jz      loc_1800BEF26
0x1800bed42  mov     rcx, rax; FullPath
0x1800bed45  call    sub_18001C2E8
0x1800bed4a  test    al, al
0x1800bed4c  jnz     loc_1800BEF26
0x1800bed52  lea     edx, [r13+2Eh]; Ch
0x1800bed56  mov     rcx, rdi; Str
0x1800bed59  call    wcsrchr
0x1800bed5e  test    rax, rax
0x1800bed61  jz      loc_1800BEF26
0x1800bed67  mov     rcx, rax; lpsz
0x1800bed6a  call    cs:CharNextW
0x1800bed70  or      r10, 0FFFFFFFFFFFFFFFFh
0x1800bed74  mov     rcx, rax
0x1800bed77  mov     rax, r10
0x1800bed7a  inc     rax
0x1800bed7d  cmp     [rcx+rax*2], r13w
0x1800bed82  jnz     short loc_1800BED7A
0x1800bed84  cmp     rax, 3
0x1800bed88  jnz     loc_1800BEF26
0x1800bed8e  movzx   edx, word ptr [rcx]
0x1800bed91  mov     r8d, 0FFDFh
0x1800bed97  mov     r9d, 1
0x1800bed9d  lea     eax, [rdx-53h]
0x1800beda0  test    r8w, ax
0x1800beda4  jnz     short loc_1800BEDC4
0x1800beda6  movzx   eax, word ptr [rcx+2]
0x1800bedaa  sub     ax, 48h ; 'H'
0x1800bedae  test    r8w, ax
0x1800bedb2  jnz     short loc_1800BEDC4
0x1800bedb4  movzx   eax, word ptr [rcx+4]
0x1800bedb8  sub     ax, 58h ; 'X'
0x1800bedbc  test    r8w, ax
0x1800bedc0  cmovz   ebx, r9d
0x1800bedc4  lea     eax, [rdx-53h]
0x1800bedc7  test    r8w, ax
0x1800bedcb  jnz     short loc_1800BEDEE
0x1800bedcd  movzx   eax, word ptr [rcx+2]
0x1800bedd1  sub     ax, 48h ; 'H'
0x1800bedd5  test    r8w, ax
0x1800bedd9  jnz     short loc_1800BEDEE
0x1800beddb  movzx   eax, word ptr [rcx+4]
0x1800beddf  sub     ax, 50h ; 'P'
0x1800bede3  movzx   ebx, bl
0x1800bede6  test    r8w, ax
0x1800bedea  cmovz   ebx, r9d
0x1800bedee  sub     dx, 46h ; 'F'
0x1800bedf2  test    r8w, dx
0x1800bedf6  jnz     short loc_1800BEE19
0x1800bedf8  movzx   eax, word ptr [rcx+2]
0x1800bedfc  sub     ax, 4Dh ; 'M'
0x1800bee00  test    r8w, ax
0x1800bee04  jnz     short loc_1800BEE19
0x1800bee06  movzx   eax, word ptr [rcx+4]
0x1800bee0a  sub     ax, 50h ; 'P'
0x1800bee0e  movzx   ebx, bl
0x1800bee11  test    r8w, ax
0x1800bee15  cmovz   ebx, r9d
0x1800bee19  test    bl, bl
0x1800bee1b  jz      loc_1800BEF26
0x1800bee21  mov     bl, r13b
0x1800bee24  mov     esi, r13d
0x1800bee27  cmp     esi, 3
0x1800bee2a  jge     loc_1800BEF26
0x1800bee30  add     esi, r9d
0x1800bee33  call    sub_1800029E0
0x1800bee38  test    al, al
0x1800bee3a  jz      loc_1800BEF1E
0x1800bee40  lea     rcx, [rsp+278h+var_258]
0x1800bee45  mov     rax, r10
0x1800bee48  inc     rax
0x1800bee4b  cmp     [rcx+rax*2], r13w
0x1800bee50  jnz     short loc_1800BEE48
0x1800bee52  mov     rcx, r10
0x1800bee55  inc     rcx
0x1800bee58  cmp     [rdi+rcx*2], r13w
0x1800bee5d  jnz     short loc_1800BEE55
0x1800bee5f  lea     rbx, [rcx+1]
0x1800bee63  add     rbx, rax
0x1800bee66  mov     eax, 2
0x1800bee6b  mul     rbx
0x1800bee6e  cmovb   rax, r10
0x1800bee72  mov     rcx, rax
0x1800bee75  call    cs:??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800bee7b  mov     r8, rbx
0x1800bee7e  lea     rdx, [rsp+278h+var_258]
0x1800bee83  mov     rcx, rax
0x1800bee86  mov     r15, rax
0x1800bee89  call    sub_180009498
0x1800bee8e  mov     r8, rdi
0x1800bee91  mov     rdx, rbx
0x1800bee94  mov     rcx, r15
0x1800bee97  call    sub_180003300
0x1800bee9c  mov     r8d, 8000h
0x1800beea2  mov     rdx, r15
0x1800beea5  mov     rcx, r12
0x1800beea8  call    sub_18001F6AC
0x1800beead  not     eax
0x1800beeaf  shr     eax, 1Fh
0x1800beeb2  mov     bl, al
0x1800beeb4  test    al, al
0x1800beeb6  jnz     short loc_1800BEF0B
0x1800beeb8  lea     rdx, aExtfont2Shx; "extfont2.shx"
0x1800beebf  mov     rcx, rdi; lpString1
0x1800beec2  lea     rbp, aIcTxtShx_0; "ic-txt.shx"
0x1800beec9  call    cs:lstrcmpiW
0x1800beecf  test    eax, eax
0x1800beed1  jz      short loc_1800BEEE7
0x1800beed3  lea     rdx, aExtfont2Shx_0; "@extfont2.shx"
0x1800beeda  mov     rcx, rdi; lpString1
0x1800beedd  call    cs:lstrcmpiW
0x1800beee3  test    eax, eax
0x1800beee5  jnz     short loc_1800BEEEE
0x1800beee7  lea     rbp, aBigfontShx_0; "bigfont.shx"
0x1800beeee  mov     rax, rdi
0x1800beef1  mov     r8d, 104h
0x1800beef7  sub     rax, r14
0x1800beefa  mov     rdx, rbp
0x1800beefd  sar     rax, 1
0x1800bef00  mov     rcx, rdi
0x1800bef03  sub     r8, rax
0x1800bef06  call    sub_180009498
0x1800bef0b  mov     rcx, r15
0x1800bef0e  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800bef14  mov     r9d, 1
0x1800bef1a  or      r10, 0FFFFFFFFFFFFFFFFh
0x1800bef1e  test    bl, bl
0x1800bef20  jz      loc_1800BEE27
0x1800bef26  mov     al, bl
0x1800bef28  jmp     short loc_1800BEF2C
0x1800bef2a  xor     al, al
0x1800bef2c  mov     rcx, [rsp+278h+var_48]
0x1800bef34  xor     rcx, rsp; StackCookie
0x1800bef37  call    __security_check_cookie
0x1800bef3c  mov     rbx, [rsp+278h+arg_10]
0x1800bef44  add     rsp, 240h
0x1800bef4b  pop     r15
0x1800bef4d  pop     r14
0x1800bef4f  pop     r13
0x1800bef51  pop     r12
0x1800bef53  pop     rdi
0x1800bef54  pop     rsi
0x1800bef55  pop     rbp
0x1800bef56  retn
```
