# InitializeLID(ushort *,WString &)

- ea: `0x1400055fc`
- end: `0x140005726`
- name: `?InitializeLID@@YAJPEAGAEAVWString@@@Z`
- size: `298`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct WString *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140005560`

## callees

- `0x1400055fc`
- `0x140005810`
- `0x140014ad0`

## import_xrefs

- `msvcrt!wcstoul` at `0x1400056d3`
- `msvcrt!wcstoul` at `0x1400056d3`
- `msvcrt!iswxdigit` at `0x140005659`
- `msvcrt!iswxdigit` at `0x140005659`
- `wbemcomn!??4WString@@QEAAAEAV0@PEBG@Z` at `0x14000571a`
- `wbemcomn!??4WString@@QEAAAEAV0@PEBG@Z` at `0x14000571a`
- `wbemcomn!??0WString@@QEAA@PEAGH@Z` at `0x14000562c`
- `wbemcomn!??0WString@@QEAA@PEAGH@Z` at `0x14000562c`
- `wbemcomn!?DeleteString@WString@@AEAAXPEAG@Z` at `0x14000568b`
- `wbemcomn!?DeleteString@WString@@AEAAXPEAG@Z` at `0x14000568b`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetSystemDefaultUILanguage` at `0x1400056db`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetSystemDefaultUILanguage` at `0x1400056db`

## pseudocode

```c
__int64 __fastcall InitializeLID(unsigned __int16 *a1, struct WString *a2)
{
  wchar_t *v3; // rdi
  unsigned __int64 v4; // rbp
  __int64 v5; // rbx
  int v6; // esi
  unsigned int v7; // eax
  unsigned int v8; // ebx
  __int16 v10; // di
  unsigned __int16 SystemDefaultUILanguage; // ax
  wchar_t *String[2]; // [rsp+20h] [rbp-88h] BYREF
  unsigned __int16 v13[32]; // [rsp+30h] [rbp-78h] BYREF

  WString::WString((WString *)String, a1, 0);
  v3 = String[0];
  v4 = -1;
  v5 = -1;
  do
    ++v5;
  while ( String[0][v5] );
  v6 = 0;
  if ( (_DWORD)v5 )
  {
    while ( iswxdigit(v3[v6]) )
    {
      if ( ++v6 >= (unsigned int)v5 )
      {
        v7 = 0;
        while ( *v3 == 48 )
        {
          ++v7;
          ++v3;
          if ( v7 >= (unsigned int)v5 )
            goto LABEL_9;
        }
        do
          ++v4;
        while ( v3[v4] );
        if ( v4 <= 3 )
        {
          v8 = 0;
          v10 = wcstoul(v3, 0, 16);
          SystemDefaultUILanguage = GetSystemDefaultUILanguage();
          if ( (SystemDefaultUILanguage & 0x3FF) != v10 )
            SystemDefaultUILanguage = v10 | 0x400;
          StringCchPrintfW(v13, 0x20u, L"MS_%hX", SystemDefaultUILanguage);
          WString::operator=(a2, v13);
          goto LABEL_10;
        }
        break;
      }
    }
  }
LABEL_9:
  v8 = -2147217407;
LABEL_10:
  WString::DeleteString((WString *)String, String[0]);
  return v8;
}

```

## disassembly

```asm
0x1400055fc  mov     [rsp+arg_10], rbx
0x140005601  push    rbp
0x140005602  push    rsi
0x140005603  push    rdi
0x140005604  push    r14
0x140005606  push    r15
0x140005608  sub     rsp, 80h
0x14000560f  mov     rax, cs:__security_cookie
0x140005616  xor     rax, rsp
0x140005619  mov     [rsp+0A8h+var_38], rax
0x14000561e  mov     r14, rdx
0x140005621  xor     r8d, r8d
0x140005624  mov     rdx, rcx
0x140005627  lea     rcx, [rsp+0A8h+String]
0x14000562c  call    cs:__imp_??0WString@@QEAA@PEAGH@Z; WString::WString(ushort *,int)
0x140005632  nop
0x140005633  mov     rdi, [rsp+0A8h+String]
0x140005638  or      rbp, 0FFFFFFFFFFFFFFFFh
0x14000563c  mov     rbx, rbp
0x14000563f  xor     r15d, r15d
0x140005642  inc     rbx
0x140005645  cmp     [rdi+rbx*2], r15w
0x14000564a  jnz     short loc_140005642
0x14000564c  mov     esi, r15d
0x14000564f  test    ebx, ebx
0x140005651  jz      short loc_14000567C
0x140005653  mov     ecx, esi
0x140005655  movzx   ecx, word ptr [rdi+rcx*2]; C
0x140005659  call    cs:__imp_iswxdigit
0x14000565f  test    eax, eax
0x140005661  jz      short loc_14000567C
0x140005663  inc     esi
0x140005665  cmp     esi, ebx
0x140005667  jb      short loc_140005653
0x140005669  mov     eax, r15d
0x14000566c  cmp     word ptr [rdi], 30h ; '0'
0x140005670  jnz     short loc_1400056B7
0x140005672  inc     eax
0x140005674  add     rdi, 2
0x140005678  cmp     eax, ebx
0x14000567a  jb      short loc_14000566C
0x14000567c  mov     ebx, 80041001h
0x140005681  mov     rdx, [rsp+0A8h+String]
0x140005686  lea     rcx, [rsp+0A8h+String]
0x14000568b  call    cs:__imp_?DeleteString@WString@@AEAAXPEAG@Z; WString::DeleteString(ushort *)
0x140005691  mov     eax, ebx
0x140005693  mov     rcx, [rsp+0A8h+var_38]
0x140005698  xor     rcx, rsp; StackCookie
0x14000569b  call    __security_check_cookie
0x1400056a0  mov     rbx, [rsp+0A8h+arg_10]
0x1400056a8  add     rsp, 80h
0x1400056af  pop     r15
0x1400056b1  pop     r14
0x1400056b3  pop     rdi
0x1400056b4  pop     rsi
0x1400056b5  pop     rbp
0x1400056b6  retn
0x1400056b7  inc     rbp
0x1400056ba  cmp     [rdi+rbp*2], r15w
0x1400056bf  jnz     short loc_1400056B7
0x1400056c1  cmp     rbp, 3
0x1400056c5  ja      short loc_14000567C
0x1400056c7  mov     ebx, r15d
0x1400056ca  xor     edx, edx; EndPtr
0x1400056cc  lea     r8d, [rdx+10h]; Radix
0x1400056d0  mov     rcx, rdi; String
0x1400056d3  call    cs:__imp_wcstoul
0x1400056d9  mov     edi, eax
0x1400056db  call    cs:__imp_GetSystemDefaultUILanguage
0x1400056e1  movzx   ecx, ax
0x1400056e4  mov     edx, 3FFh
0x1400056e9  and     cx, dx
0x1400056ec  cmp     cx, di
0x1400056ef  jz      short loc_1400056F8
0x1400056f1  movzx   eax, di
0x1400056f4  or      ax, 400h
0x1400056f8  movzx   r9d, ax
0x1400056fc  lea     r8, aMsHx; "MS_%hX"
0x140005703  mov     edx, 20h ; ' '; unsigned __int64
0x140005708  lea     rcx, [rsp+0A8h+var_78]; unsigned __int16 *
0x14000570d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140005712  lea     rdx, [rsp+0A8h+var_78]
0x140005717  mov     rcx, r14
0x14000571a  call    cs:__imp_??4WString@@QEAAAEAV0@PEBG@Z; WString::operator=(ushort const *)
0x140005720  jmp     loc_140005681
```
