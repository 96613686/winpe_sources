# AslPathSplit

- ea: `0x18006bc7c`
- end: `0x18006be15`
- name: `AslPathSplit`
- size: `409`
- prototype: `__int64 __fastcall(const wchar_t *, _WORD *, unsigned int, _WORD *, __int64, _WORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18012197c`

## callees

- `0x1800197d4`
- `0x18002256c`
- `0x180059920`
- `0x18006bc7c`
- `0x180070240`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18006bccd`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18006bd5f`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18006bccd`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18006bd5f`

## string_xrefs

- `0x18006bcff`: `RtlStringCchCopyW failed [%x]`
- `0x18006bdbb`: `RtlStringCchCopyW failed [%x]`
- `0x18006bddd`: `RtlStringCchCopyW failed [%x]`
- `0x18006bd34`: `RtlStringCchCopyNW failed [%x]`
- `0x18006bd3b`: `AslPathSplit`

## pseudocode

```c
__int64 __fastcall AslPathSplit(const wchar_t *a1, _WORD *a2, unsigned int a3, _WORD *a4, __int64 a5, _WORD *a6)
{
  __int64 v8; // rbp
  wchar_t *v10; // rax
  _WORD *v11; // rdi
  _WORD *v12; // r8
  int v13; // ebx
  const char *v14; // r9
  int v15; // r8d
  wchar_t *v16; // rax
  wchar_t *v17; // rbp
  __int64 v18; // rdi
  wchar_t Str[264]; // [rsp+30h] [rbp-258h] BYREF

  *a2 = 0;
  v8 = a3;
  Str[0] = 0;
  *a6 = 0;
  *a4 = 0;
  v10 = wcsrchr(a1, 0x5Cu);
  v11 = v10;
  if ( v10 )
  {
    v13 = RtlStringCchCopyNW(a2, v8, a1, v10 - a1 + 1);
    if ( v13 < 0 )
    {
      v15 = 1231;
LABEL_9:
      v14 = "RtlStringCchCopyNW failed [%x]";
      goto LABEL_10;
    }
  }
  else
  {
    v11 = a1;
  }
  v12 = v11 + 1;
  if ( *v11 != 92 )
    v12 = v11;
  v13 = RtlStringCchCopyW(Str, 261, v12);
  if ( v13 >= 0 )
  {
    v16 = wcsrchr(Str, 0x2Eu);
    v17 = v16;
    if ( v16 )
    {
      v18 = v16 - Str;
      v13 = RtlStringCchCopyNW(a4, 260, Str, v18);
      if ( v13 < 0 )
      {
        v15 = 1264;
        goto LABEL_9;
      }
      a4[v18] = 0;
      v13 = RtlStringCchCopyW(a6, 260, v17);
      if ( v13 < 0 )
      {
        v14 = "RtlStringCchCopyW failed [%x]";
        v15 = 1271;
        goto LABEL_10;
      }
    }
    else
    {
      v13 = RtlStringCchCopyW(a4, 260, Str);
      if ( v13 < 0 )
      {
        v14 = "RtlStringCchCopyW failed [%x]";
        v15 = 1278;
        goto LABEL_10;
      }
    }
    return 0;
  }
  v14 = "RtlStringCchCopyW failed [%x]";
  v15 = 1251;
LABEL_10:
  AslLogCallPrintf(1, (unsigned int)"AslPathSplit", v15, (_DWORD)v14);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18006bc7c  push    rbx
0x18006bc7e  push    rbp
0x18006bc7f  push    rsi
0x18006bc80  push    rdi
0x18006bc81  push    r13
0x18006bc83  push    r14
0x18006bc85  push    r15
0x18006bc87  sub     rsp, 250h
0x18006bc8e  mov     rax, cs:__security_cookie
0x18006bc95  xor     rax, rsp
0x18006bc98  mov     [rsp+288h+var_48], rax
0x18006bca0  mov     r15, [rsp+288h+arg_28]
0x18006bca8  xor     eax, eax
0x18006bcaa  mov     [rdx], ax
0x18006bcad  mov     rsi, rdx
0x18006bcb0  mov     r14, r9
0x18006bcb3  mov     ebp, r8d
0x18006bcb6  mov     rbx, rcx
0x18006bcb9  mov     [rsp+288h+Str], ax
0x18006bcbe  lea     r13d, [rax+5Ch]
0x18006bcc2  mov     [r15], ax
0x18006bcc6  mov     edx, r13d; Ch
0x18006bcc9  mov     [r9], ax
0x18006bccd  call    cs:__imp_wcsrchr
0x18006bcd3  mov     rdi, rax
0x18006bcd6  test    rax, rax
0x18006bcd9  jnz     short loc_18006BD0E
0x18006bcdb  mov     rdi, rbx
0x18006bcde  cmp     [rdi], r13w
0x18006bce2  lea     r8, [rdi+2]
0x18006bce6  mov     edx, 105h
0x18006bceb  lea     rcx, [rsp+288h+Str]
0x18006bcf0  cmovnz  r8, rdi
0x18006bcf4  call    RtlStringCchCopyW
0x18006bcf9  mov     ebx, eax
0x18006bcfb  test    eax, eax
0x18006bcfd  jns     short loc_18006BD55
0x18006bcff  lea     r9, aRtlstringcchco_3; "RtlStringCchCopyW failed [%x]"
0x18006bd06  mov     r8d, 4E3h
0x18006bd0c  jmp     short loc_18006BD3B
0x18006bd0e  mov     r9, rax
0x18006bd11  mov     rdx, rbp
0x18006bd14  sub     r9, rbx
0x18006bd17  mov     r8, rbx
0x18006bd1a  sar     r9, 1
0x18006bd1d  mov     rcx, rsi
0x18006bd20  inc     r9
0x18006bd23  call    RtlStringCchCopyNW
0x18006bd28  mov     ebx, eax
0x18006bd2a  test    eax, eax
0x18006bd2c  jns     short loc_18006BCDE
0x18006bd2e  mov     r8d, 4CFh
0x18006bd34  lea     r9, aRtlstringcchco_5; "RtlStringCchCopyNW failed [%x]"
0x18006bd3b  lea     rdx, aAslpathsplit; "AslPathSplit"
0x18006bd42  mov     [rsp+288h+var_268], eax
0x18006bd46  mov     ecx, 1
0x18006bd4b  call    AslLogCallPrintf
0x18006bd50  jmp     loc_18006BDF1
0x18006bd55  mov     edx, 2Eh ; '.'; Ch
0x18006bd5a  lea     rcx, [rsp+288h+Str]; Str
0x18006bd5f  call    cs:__imp_wcsrchr
0x18006bd65  lea     r8, [rsp+288h+Str]
0x18006bd6a  mov     rcx, r14
0x18006bd6d  mov     rbp, rax
0x18006bd70  test    rax, rax
0x18006bd73  jz      short loc_18006BDCD
0x18006bd75  lea     rax, [rsp+288h+Str]
0x18006bd7a  mov     rdi, rbp
0x18006bd7d  sub     rdi, rax
0x18006bd80  mov     esi, 104h
0x18006bd85  sar     rdi, 1
0x18006bd88  mov     edx, esi
0x18006bd8a  mov     r9, rdi
0x18006bd8d  call    RtlStringCchCopyNW
0x18006bd92  mov     ebx, eax
0x18006bd94  test    eax, eax
0x18006bd96  jns     short loc_18006BDA0
0x18006bd98  mov     r8d, 4F0h
0x18006bd9e  jmp     short loc_18006BD34
0x18006bda0  xor     eax, eax
0x18006bda2  mov     r8, rbp
0x18006bda5  mov     rdx, rsi
0x18006bda8  mov     [r14+rdi*2], ax
0x18006bdad  mov     rcx, r15
0x18006bdb0  call    RtlStringCchCopyW
0x18006bdb5  mov     ebx, eax
0x18006bdb7  test    eax, eax
0x18006bdb9  jns     short loc_18006BDEF
0x18006bdbb  lea     r9, aRtlstringcchco_3; "RtlStringCchCopyW failed [%x]"
0x18006bdc2  mov     r8d, 4F7h
0x18006bdc8  jmp     loc_18006BD3B
0x18006bdcd  mov     edx, 104h
0x18006bdd2  call    RtlStringCchCopyW
0x18006bdd7  mov     ebx, eax
0x18006bdd9  test    eax, eax
0x18006bddb  jns     short loc_18006BDEF
0x18006bddd  lea     r9, aRtlstringcchco_3; "RtlStringCchCopyW failed [%x]"
0x18006bde4  mov     r8d, 4FEh
0x18006bdea  jmp     loc_18006BD3B
0x18006bdef  xor     ebx, ebx
0x18006bdf1  mov     eax, ebx
0x18006bdf3  mov     rcx, [rsp+288h+var_48]
0x18006bdfb  xor     rcx, rsp; StackCookie
0x18006bdfe  call    __security_check_cookie
0x18006be03  add     rsp, 250h
0x18006be0a  pop     r15
0x18006be0c  pop     r14
0x18006be0e  pop     r13
0x18006be10  pop     rdi
0x18006be11  pop     rsi
0x18006be12  pop     rbp
0x18006be13  pop     rbx
0x18006be14  retn
```
