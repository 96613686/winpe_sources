# CommonUtil::CSprintfAlloc<CommonUtil::CNewSprintfPolicy<wchar_t>,260>::DoFormating(unsigned __int64 *,wchar_t * *,wchar_t const *,char *,unsigned __int64)

- ea: `0x1400030e4`
- end: `0x140003251`
- name: `?DoFormating@?$CSprintfAlloc@U?$CNewSprintfPolicy@_W@CommonUtil@@$0BAE@@CommonUtil@@SAJPEA_KPEAPEA_WPEB_WPEAD_K@Z`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000329c`

## callees

- `0x140002650`
- `0x1400030e4`
- `0x140003310`
- `0x140005c20`
- `0x140010dd0`
- `0x140025080`

## pseudocode

```c
__int64 __fastcall CommonUtil::CSprintfAlloc<CommonUtil::CNewSprintfPolicy<wchar_t>,260>::DoFormating(
        unsigned __int64 *a1,
        void **a2,
        int a3,
        __int64 a4,
        unsigned __int64 a5)
{
  unsigned __int64 v5; // rbx
  void *v7; // rdx
  size_t v11; // rbx
  int v12; // edx
  __int64 result; // rax
  int NoCopy; // ecx
  int v15; // eax
  _QWORD v16[2]; // [rsp+30h] [rbp-258h] BYREF
  wchar_t String[264]; // [rsp+40h] [rbp-248h] BYREF

  v5 = *a1;
  v7 = *a2;
  v16[0] = 0;
  if ( v7 )
  {
    result = MpStringCchVPrintfW(v5, (_DWORD)v7, (unsigned int)v16, a3, a4);
    if ( (_DWORD)result == -2147024774 )
    {
LABEL_10:
      while ( 1 )
      {
        v5 = v5 >= v16[0] ? (3 * v5) >> 1 : v16[0];
        if ( a5 < v5 )
          break;
        _mm_lfence();
        NoCopy = CommonUtil::CNewSprintfPolicy<wchar_t>::ReAllocateNoCopy(a2, v5);
        _mm_lfence();
        if ( NoCopy < 0 )
        {
          if ( !*a2 )
            *a1 = 0;
          return (unsigned int)NoCopy;
        }
        *a1 = v5;
        v15 = MpStringCchVPrintfW(v5, (unsigned int)*a2, (unsigned int)v16, a3, a4);
        NoCopy = v15;
        if ( v15 != -2147024774 )
        {
          if ( v15 >= 0 )
            return 0;
          _mm_lfence();
          return (unsigned int)NoCopy;
        }
      }
      return 2147942522LL;
    }
  }
  else
  {
    v5 = 260;
    if ( (int)MpStringCchVPrintfW(260, (unsigned int)String, (unsigned int)v16, a3, a4) < 0 )
      goto LABEL_10;
    v11 = wcslen(String) + 1;
    v12 = CommonUtil::CNewSprintfPolicy<wchar_t>::ReAllocateNoCopy(a2, v11);
    if ( v12 >= 0 )
    {
      memmove(*a2, String, 2 * v11);
      v12 = 0;
    }
    if ( v12 >= 0 )
    {
      *a1 = wcslen(String) + 1;
      return 0;
    }
    else
    {
      return (unsigned int)v12;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400030e4  push    rbx
0x1400030e6  push    rbp
0x1400030e7  push    rsi
0x1400030e8  push    rdi
0x1400030e9  push    r14
0x1400030eb  sub     rsp, 260h
0x1400030f2  mov     rax, cs:__security_cookie
0x1400030f9  xor     rax, rsp
0x1400030fc  mov     [rsp+288h+var_38], rax
0x140003104  mov     rbx, [rcx]
0x140003107  mov     rdi, rdx
0x14000310a  mov     rdx, [rdx]
0x14000310d  mov     r14, r9
0x140003110  mov     [rsp+288h+var_268], r9
0x140003115  mov     rbp, r8
0x140003118  mov     [rsp+288h+var_258], 0
0x140003121  mov     r9, r8
0x140003124  lea     r8, [rsp+288h+var_258]
0x140003129  mov     rsi, rcx
0x14000312c  test    rdx, rdx
0x14000312f  jnz     short loc_1400031A5
0x140003131  mov     ebx, 104h
0x140003136  lea     rdx, [rsp+288h+String]
0x14000313b  mov     ecx, ebx
0x14000313d  call    MpStringCchVPrintfW
0x140003142  shr     eax, 1Fh
0x140003145  test    al, al
0x140003147  jnz     short loc_1400031B4
0x140003149  lea     rcx, [rsp+288h+String]; String
0x14000314e  call    wcslen
0x140003153  mov     rcx, rdi
0x140003156  lea     rbx, [rax+1]
0x14000315a  mov     rdx, rbx
0x14000315d  call    ?ReAllocateNoCopy@?$CNewSprintfPolicy@_W@CommonUtil@@SAJPEAPEA_W_K@Z; CommonUtil::CNewSprintfPolicy<wchar_t>::ReAllocateNoCopy(wchar_t * *,unsigned __int64)
0x140003162  mov     edx, eax
0x140003164  shr     eax, 1Fh
0x140003167  test    al, al
0x140003169  jnz     short loc_14000317E
0x14000316b  mov     rcx, [rdi]; void *
0x14000316e  lea     r8, [rbx+rbx]; Size
0x140003172  lea     rdx, [rsp+288h+String]; Src
0x140003177  call    memmove
0x14000317c  xor     edx, edx
0x14000317e  mov     ecx, edx
0x140003180  shr     ecx, 1Fh
0x140003183  test    cl, cl
0x140003185  jz      short loc_14000318E
0x140003187  mov     eax, edx
0x140003189  jmp     loc_140003233
0x14000318e  lea     rcx, [rsp+288h+String]; String
0x140003193  call    wcslen
0x140003198  inc     rax
0x14000319b  mov     [rsi], rax
0x14000319e  xor     eax, eax
0x1400031a0  jmp     loc_140003233
0x1400031a5  mov     rcx, rbx
0x1400031a8  call    MpStringCchVPrintfW
0x1400031ad  cmp     eax, 8007007Ah
0x1400031b2  jnz     short loc_140003233
0x1400031b4  cmp     rbx, [rsp+288h+var_258]
0x1400031b9  jnb     short loc_1400031C2
0x1400031bb  mov     rbx, [rsp+288h+var_258]
0x1400031c0  jmp     short loc_1400031C9
0x1400031c2  lea     rbx, [rbx+rbx*2]
0x1400031c6  shr     rbx, 1
0x1400031c9  cmp     [rsp+288h+arg_20], rbx
0x1400031d1  jb      short loc_14000322E
0x1400031d3  lfence
0x1400031d6  mov     rdx, rbx
0x1400031d9  mov     rcx, rdi
0x1400031dc  call    ?ReAllocateNoCopy@?$CNewSprintfPolicy@_W@CommonUtil@@SAJPEAPEA_W_K@Z; CommonUtil::CNewSprintfPolicy<wchar_t>::ReAllocateNoCopy(wchar_t * *,unsigned __int64)
0x1400031e1  mov     ecx, eax
0x1400031e3  shr     eax, 1Fh
0x1400031e6  lfence
0x1400031e9  test    al, al
0x1400031eb  jnz     short loc_14000321D
0x1400031ed  mov     [rsi], rbx
0x1400031f0  lea     r8, [rsp+288h+var_258]
0x1400031f5  mov     rdx, [rdi]
0x1400031f8  mov     r9, rbp
0x1400031fb  mov     rcx, rbx
0x1400031fe  mov     [rsp+288h+var_268], r14
0x140003203  call    MpStringCchVPrintfW
0x140003208  mov     ecx, eax
0x14000320a  cmp     eax, 8007007Ah
0x14000320f  jz      short loc_1400031B4
0x140003211  shr     eax, 1Fh
0x140003214  test    al, al
0x140003216  jz      short loc_14000319E
0x140003218  lfence
0x14000321b  jmp     short loc_14000322A
0x14000321d  cmp     qword ptr [rdi], 0
0x140003221  jnz     short loc_14000322A
0x140003223  mov     qword ptr [rsi], 0
0x14000322a  mov     eax, ecx
0x14000322c  jmp     short loc_140003233
0x14000322e  mov     eax, 8007007Ah
0x140003233  mov     rcx, [rsp+288h+var_38]
0x14000323b  xor     rcx, rsp; StackCookie
0x14000323e  call    __security_check_cookie
0x140003243  add     rsp, 260h
0x14000324a  pop     r14
0x14000324c  pop     rdi
0x14000324d  pop     rsi
0x14000324e  pop     rbp
0x14000324f  pop     rbx
0x140003250  retn
```
