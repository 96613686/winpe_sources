# mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::find_switch_word(ushort const *,unsigned __int64 &,unsigned __int64 &)

- ea: `0x18001c63c`
- end: `0x18001c84d`
- name: `?find_switch_word@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEBA_NPEBGAEA_K1@Z`
- size: `529`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001c900`

## callees

- `0x180003640`
- `0x18000a0b0`
- `0x18001c324`
- `0x18001c63c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001c77b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001c77b`

## pseudocode

```c
char __fastcall mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::find_switch_word(
        __int64 a1,
        const WCHAR *a2,
        _QWORD *a3,
        _QWORD *a4)
{
  const WCHAR *lpString2; // rdi
  char result; // al
  WCHAR v8; // ax
  unsigned __int64 cchCount2; // rbp
  const WCHAR *v10; // r15
  const WCHAR *v11; // rbx
  const WCHAR *v12; // rsi
  const WCHAR *v13; // r14
  unsigned __int16 *v14; // rdi

  lpString2 = a2;
  if ( **(_QWORD **)a1 && a2 && *a2 )
  {
    mlib::m_traits<unsigned short>::CStrlen(a2, 0x10000);
    while ( (unsigned __int8)mlib::m_traits<unsigned short>::isSpace(*lpString2) )
    {
      if ( !++lpString2 )
        return 0;
    }
    v8 = *lpString2;
    cchCount2 = 0;
    while ( v8 && !(unsigned __int8)mlib::m_traits<unsigned short>::isSpace(v8) )
      v8 = lpString2[++cchCount2];
    v10 = *(const WCHAR **)(*(_QWORD *)a1 + 24LL);
    v11 = v10;
    v12 = &v10[**(_QWORD **)a1];
    while ( 1 )
    {
LABEL_13:
      while ( 1 )
      {
        v13 = lpString2;
        if ( *v11 != 34 )
          break;
        v11 = (const WCHAR *)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::delimit_quoted_string(
                               a1,
                               v11,
                               34);
        if ( v11 == v12 )
          return 0;
      }
      if ( (unsigned __int8)mlib::m_traits<unsigned short>::isSpace(*v11) )
        break;
      if ( *v11 != 45 && *v11 != 47 && *v11 != 8211 && *v11 != 8260 )
      {
        while ( 1 )
        {
          if ( ++v11 == v12 )
            return 0;
          if ( (unsigned __int8)mlib::m_traits<unsigned short>::isSpace(*v11) )
            goto LABEL_13;
        }
      }
      if ( ++v11 == v12 || v12 - v11 < cchCount2 )
        return 0;
      if ( CompareStringW(0x400u, 0x1001u, v11, cchCount2, lpString2, cchCount2) == 2 )
      {
        v14 = (unsigned __int16 *)&v11[cchCount2];
        if ( v14 == v12 || (unsigned __int8)mlib::m_traits<unsigned short>::isSpace(*v14) )
        {
          result = 1;
          *a3 = v11 - v10 - 1;
          *a4 = cchCount2 + 1;
          return result;
        }
        v11 += cchCount2;
        lpString2 = v13;
        if ( !(unsigned __int8)mlib::m_traits<unsigned short>::isSpace(*v11) )
        {
          while ( !(unsigned __int8)mlib::m_traits<unsigned short>::isSpace(*v11) )
          {
            if ( ++v11 == v12 )
              return 0;
          }
        }
      }
    }
    while ( ++v11 != v12 )
    {
      if ( !(unsigned __int8)mlib::m_traits<unsigned short>::isSpace(*v11) )
        goto LABEL_13;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001c63c  mov     rax, rsp
0x18001c63f  mov     [rax+8], rbx
0x18001c643  mov     [rax+10h], rbp
0x18001c647  mov     [rax+20h], rsi
0x18001c64b  mov     [rax+18h], r8
0x18001c64f  push    rdi
0x18001c650  push    r12
0x18001c652  push    r13
0x18001c654  push    r14
0x18001c656  push    r15
0x18001c658  sub     rsp, 30h
0x18001c65c  mov     rax, [rcx]
0x18001c65f  xor     ebx, ebx
0x18001c661  mov     r13, r9
0x18001c664  mov     rdi, rdx
0x18001c667  mov     r12, rcx
0x18001c66a  cmp     [rax], rbx
0x18001c66d  jz      short loc_18001C698
0x18001c66f  test    rdx, rdx
0x18001c672  jz      short loc_18001C698
0x18001c674  cmp     [rdx], bx
0x18001c677  jz      short loc_18001C698
0x18001c679  mov     edx, 10000h
0x18001c67e  mov     rcx, rdi
0x18001c681  call    ?CStrlen@?$m_traits@G@mlib@@SA_KPEBG_K@Z; mlib::m_traits<ushort>::CStrlen(ushort const *,unsigned __int64)
0x18001c686  movzx   ecx, word ptr [rdi]
0x18001c689  call    ?isSpace@?$m_traits@G@mlib@@SA_NG@Z; mlib::m_traits<ushort>::isSpace(ushort)
0x18001c68e  test    al, al
0x18001c690  jz      short loc_18001C6B8
0x18001c692  add     rdi, 2
0x18001c696  jnz     short loc_18001C686
0x18001c698  xor     al, al
0x18001c69a  mov     rbx, [rsp+58h+arg_0]
0x18001c69f  mov     rbp, [rsp+58h+arg_8]
0x18001c6a4  mov     rsi, [rsp+58h+arg_18]
0x18001c6a9  add     rsp, 30h
0x18001c6ad  pop     r15
0x18001c6af  pop     r14
0x18001c6b1  pop     r13
0x18001c6b3  pop     r12
0x18001c6b5  pop     rdi
0x18001c6b6  retn
0x18001c6b8  movzx   eax, word ptr [rdi]
0x18001c6bb  mov     rbp, rbx
0x18001c6be  jmp     short loc_18001C6D3
0x18001c6c0  movzx   ecx, ax
0x18001c6c3  call    ?isSpace@?$m_traits@G@mlib@@SA_NG@Z; mlib::m_traits<ushort>::isSpace(ushort)
0x18001c6c8  test    al, al
0x18001c6ca  jnz     short loc_18001C6D8
0x18001c6cc  inc     rbp
0x18001c6cf  movzx   eax, word ptr [rdi+rbp*2]
0x18001c6d3  test    ax, ax
0x18001c6d6  jnz     short loc_18001C6C0
0x18001c6d8  mov     rax, [r12]
0x18001c6dc  mov     r15, [rax+18h]
0x18001c6e0  mov     rax, [rax]
0x18001c6e3  mov     rbx, r15
0x18001c6e6  lea     rsi, [r15+rax*2]
0x18001c6ea  mov     eax, 22h ; '"'
0x18001c6ef  mov     r14, rdi
0x18001c6f2  cmp     [rbx], ax
0x18001c6f5  jnz     short loc_18001C70F
0x18001c6f7  mov     r8d, eax
0x18001c6fa  mov     rdx, rbx
0x18001c6fd  mov     rcx, r12
0x18001c700  call    ?delimit_quoted_string@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEBAPEBGPEBGG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::delimit_quoted_string(ushort const *,ushort)
0x18001c705  mov     rbx, rax
0x18001c708  cmp     rax, rsi
0x18001c70b  jz      short loc_18001C698
0x18001c70d  jmp     short loc_18001C6EA
0x18001c70f  movzx   ecx, word ptr [rbx]
0x18001c712  call    ?isSpace@?$m_traits@G@mlib@@SA_NG@Z; mlib::m_traits<ushort>::isSpace(ushort)
0x18001c717  test    al, al
0x18001c719  jnz     loc_18001C7FC
0x18001c71f  cmp     word ptr [rbx], 2Dh ; '-'
0x18001c723  jz      short loc_18001C743
0x18001c725  cmp     word ptr [rbx], 2Fh ; '/'
0x18001c729  jz      short loc_18001C743
0x18001c72b  mov     eax, 2013h
0x18001c730  cmp     [rbx], ax
0x18001c733  jz      short loc_18001C743
0x18001c735  mov     eax, 2044h
0x18001c73a  cmp     [rbx], ax
0x18001c73d  jnz     loc_18001C81F
0x18001c743  add     rbx, 2
0x18001c747  cmp     rbx, rsi
0x18001c74a  jz      loc_18001C698
0x18001c750  mov     rax, rsi
0x18001c753  sub     rax, rbx
0x18001c756  sar     rax, 1
0x18001c759  cmp     rax, rbp
0x18001c75c  jb      loc_18001C698
0x18001c762  mov     [rsp+58h+cchCount2], ebp; cchCount2
0x18001c766  mov     r9d, ebp; cchCount1
0x18001c769  mov     r8, rbx; lpString1
0x18001c76c  mov     [rsp+58h+lpString2], r14; lpString2
0x18001c771  mov     edx, 1001h; dwCmpFlags
0x18001c776  mov     ecx, 400h; Locale
0x18001c77b  call    cs:__imp_CompareStringW
0x18001c782  nop     dword ptr [rax+rax+00h]
0x18001c787  cmp     eax, 2
0x18001c78a  mov     eax, 22h ; '"'
0x18001c78f  jnz     loc_18001C6EF
0x18001c795  lea     rdi, [rbx+rbp*2]
0x18001c799  cmp     rdi, rsi
0x18001c79c  jz      loc_18001C82D
0x18001c7a2  movzx   ecx, word ptr [rdi]
0x18001c7a5  call    ?isSpace@?$m_traits@G@mlib@@SA_NG@Z; mlib::m_traits<ushort>::isSpace(ushort)
0x18001c7aa  test    al, al
0x18001c7ac  jnz     short loc_18001C82D
0x18001c7ae  mov     rbx, rdi
0x18001c7b1  mov     rdi, r14
0x18001c7b4  movzx   ecx, word ptr [rbx]
0x18001c7b7  call    ?isSpace@?$m_traits@G@mlib@@SA_NG@Z; mlib::m_traits<ushort>::isSpace(ushort)
0x18001c7bc  test    al, al
0x18001c7be  mov     eax, 22h ; '"'
0x18001c7c3  jnz     loc_18001C6EF
0x18001c7c9  movzx   ecx, word ptr [rbx]
0x18001c7cc  call    ?isSpace@?$m_traits@G@mlib@@SA_NG@Z; mlib::m_traits<ushort>::isSpace(ushort)
0x18001c7d1  test    al, al
0x18001c7d3  jnz     loc_18001C6EA
0x18001c7d9  add     rbx, 2
0x18001c7dd  cmp     rbx, rsi
0x18001c7e0  jnz     short loc_18001C7C9
0x18001c7e2  jmp     loc_18001C698
0x18001c7e7  movzx   ecx, word ptr [rbx]
0x18001c7ea  call    ?isSpace@?$m_traits@G@mlib@@SA_NG@Z; mlib::m_traits<ushort>::isSpace(ushort)
0x18001c7ef  test    al, al
0x18001c7f1  mov     eax, 22h ; '"'
0x18001c7f6  jz      loc_18001C6EF
0x18001c7fc  add     rbx, 2
0x18001c800  cmp     rbx, rsi
0x18001c803  jnz     short loc_18001C7E7
0x18001c805  jmp     loc_18001C698
0x18001c80a  movzx   ecx, word ptr [rbx]
0x18001c80d  call    ?isSpace@?$m_traits@G@mlib@@SA_NG@Z; mlib::m_traits<ushort>::isSpace(ushort)
0x18001c812  test    al, al
0x18001c814  mov     eax, 22h ; '"'
0x18001c819  jnz     loc_18001C6EF
0x18001c81f  add     rbx, 2
0x18001c823  cmp     rbx, rsi
0x18001c826  jnz     short loc_18001C80A
0x18001c828  jmp     loc_18001C698
0x18001c82d  mov     rcx, [rsp+58h+arg_10]
0x18001c832  sub     rbx, r15
0x18001c835  sar     rbx, 1
0x18001c838  mov     al, 1
0x18001c83a  dec     rbx
0x18001c83d  mov     [rcx], rbx
0x18001c840  lea     rcx, [rbp+1]
0x18001c844  mov     [r13+0], rcx
0x18001c848  jmp     loc_18001C69A
```
