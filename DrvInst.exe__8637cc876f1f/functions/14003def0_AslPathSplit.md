# AslPathSplit

- ea: `0x14003def0`
- end: `0x14003e087`
- name: `AslPathSplit`
- size: `407`
- prototype: `__int64 __fastcall(const wchar_t *, _WORD *, unsigned int, _WORD *, int, _WORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14003267c`

## callees

- `0x14002fe54`
- `0x14002fea8`
- `0x14003bf18`
- `0x14003def0`
- `0x140045f30`

## import_xrefs

- `msvcrt!wcsrchr` at `0x14003df40`
- `msvcrt!wcsrchr` at `0x14003dfd2`
- `msvcrt!wcsrchr` at `0x14003df40`
- `msvcrt!wcsrchr` at `0x14003dfd2`

## string_xrefs

- `0x14003dfae`: `AslPathSplit`
- `0x14003dfa7`: `RtlStringCchCopyNW failed [%x]`
- `0x14003df72`: `RtlStringCchCopyW failed [%x]`
- `0x14003e02e`: `RtlStringCchCopyW failed [%x]`
- `0x14003e050`: `RtlStringCchCopyW failed [%x]`

## pseudocode

```c
__int64 __fastcall AslPathSplit(const wchar_t *a1, _WORD *a2, unsigned int a3, _WORD *a4, int a5, _WORD *a6)
{
  __int64 v8; // rsi
  wchar_t *v10; // rax
  const wchar_t *v11; // r11
  const wchar_t *v12; // r8
  int v13; // eax
  unsigned int v14; // ebx
  const char *v15; // r9
  __int64 v16; // r8
  wchar_t *v17; // rax
  wchar_t *v18; // rsi
  __int64 v19; // r11
  wchar_t Str[264]; // [rsp+30h] [rbp-258h] BYREF

  *a2 = 0;
  v8 = a3;
  Str[0] = 0;
  *a6 = 0;
  *a4 = 0;
  v10 = wcsrchr(a1, 0x5Cu);
  if ( v10 )
  {
    v13 = RtlStringCchCopyNW(a2, v8, a1, v10 - a1 + 1);
    v14 = v13;
    if ( v13 < 0 )
    {
      v16 = 1231;
LABEL_9:
      v15 = "RtlStringCchCopyNW failed [%x]";
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
  v14 = v13;
  if ( v13 >= 0 )
  {
    v17 = wcsrchr(Str, 0x2Eu);
    v18 = v17;
    if ( v17 )
    {
      v13 = RtlStringCchCopyNW(a4, 260, Str, v17 - Str);
      v14 = v13;
      if ( v13 < 0 )
      {
        v16 = 1264;
        goto LABEL_9;
      }
      a4[v19] = 0;
      v13 = RtlStringCchCopyW(a6, 260, v18);
      v14 = v13;
      if ( v13 < 0 )
      {
        v15 = "RtlStringCchCopyW failed [%x]";
        v16 = 1271;
        goto LABEL_10;
      }
    }
    else
    {
      v13 = RtlStringCchCopyW(a4, 260, Str);
      v14 = v13;
      if ( v13 < 0 )
      {
        v15 = "RtlStringCchCopyW failed [%x]";
        v16 = 1278;
        goto LABEL_10;
      }
    }
    return 0;
  }
  v15 = "RtlStringCchCopyW failed [%x]";
  v16 = 1251;
LABEL_10:
  AslLogCallPrintf(1, "AslPathSplit", v16, v15, v13);
  return v14;
}

```

## disassembly

```asm
0x14003def0  push    rbx
0x14003def2  push    rsi
0x14003def3  push    rdi
0x14003def4  push    r12
0x14003def6  push    r14
0x14003def8  push    r15
0x14003defa  sub     rsp, 258h
0x14003df01  mov     rax, cs:__security_cookie
0x14003df08  xor     rax, rsp
0x14003df0b  mov     [rsp+288h+var_48], rax
0x14003df13  mov     r15, [rsp+288h+arg_28]
0x14003df1b  xor     eax, eax
0x14003df1d  mov     [rdx], ax
0x14003df20  mov     rdi, rdx
0x14003df23  mov     r14, r9
0x14003df26  mov     esi, r8d
0x14003df29  mov     rbx, rcx
0x14003df2c  mov     [rsp+288h+Str], ax
0x14003df31  lea     r12d, [rax+5Ch]
0x14003df35  mov     [r15], ax
0x14003df39  mov     edx, r12d; Ch
0x14003df3c  mov     [r9], ax
0x14003df40  call    cs:__imp_wcsrchr
0x14003df46  mov     r11, rax
0x14003df49  test    rax, rax
0x14003df4c  jnz     short loc_14003DF81
0x14003df4e  mov     r11, rbx
0x14003df51  cmp     [r11], r12w
0x14003df55  lea     r8, [r11+2]
0x14003df59  mov     edx, 105h
0x14003df5e  lea     rcx, [rsp+288h+Str]
0x14003df63  cmovnz  r8, r11
0x14003df67  call    RtlStringCchCopyW
0x14003df6c  mov     ebx, eax
0x14003df6e  test    eax, eax
0x14003df70  jns     short loc_14003DFC8
0x14003df72  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x14003df79  mov     r8d, 4E3h
0x14003df7f  jmp     short loc_14003DFAE
0x14003df81  mov     r9, rax
0x14003df84  mov     rdx, rsi
0x14003df87  sub     r9, rbx
0x14003df8a  mov     r8, rbx
0x14003df8d  sar     r9, 1
0x14003df90  mov     rcx, rdi
0x14003df93  inc     r9
0x14003df96  call    RtlStringCchCopyNW
0x14003df9b  mov     ebx, eax
0x14003df9d  test    eax, eax
0x14003df9f  jns     short loc_14003DF51
0x14003dfa1  mov     r8d, 4CFh
0x14003dfa7  lea     r9, aRtlstringcchco_2; "RtlStringCchCopyNW failed [%x]"
0x14003dfae  lea     rdx, aAslpathsplit; "AslPathSplit"
0x14003dfb5  mov     [rsp+288h+var_268], eax
0x14003dfb9  mov     ecx, 1
0x14003dfbe  call    AslLogCallPrintf
0x14003dfc3  jmp     loc_14003E064
0x14003dfc8  mov     edx, 2Eh ; '.'; Ch
0x14003dfcd  lea     rcx, [rsp+288h+Str]; Str
0x14003dfd2  call    cs:__imp_wcsrchr
0x14003dfd8  lea     r8, [rsp+288h+Str]
0x14003dfdd  mov     rcx, r14
0x14003dfe0  mov     rsi, rax
0x14003dfe3  test    rax, rax
0x14003dfe6  jz      short loc_14003E040
0x14003dfe8  lea     rax, [rsp+288h+Str]
0x14003dfed  mov     r11, rsi
0x14003dff0  sub     r11, rax
0x14003dff3  mov     edi, 104h
0x14003dff8  sar     r11, 1
0x14003dffb  mov     edx, edi
0x14003dffd  mov     r9, r11
0x14003e000  call    RtlStringCchCopyNW
0x14003e005  mov     ebx, eax
0x14003e007  test    eax, eax
0x14003e009  jns     short loc_14003E013
0x14003e00b  mov     r8d, 4F0h
0x14003e011  jmp     short loc_14003DFA7
0x14003e013  xor     eax, eax
0x14003e015  mov     r8, rsi
0x14003e018  mov     rdx, rdi
0x14003e01b  mov     [r14+r11*2], ax
0x14003e020  mov     rcx, r15
0x14003e023  call    RtlStringCchCopyW
0x14003e028  mov     ebx, eax
0x14003e02a  test    eax, eax
0x14003e02c  jns     short loc_14003E062
0x14003e02e  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x14003e035  mov     r8d, 4F7h
0x14003e03b  jmp     loc_14003DFAE
0x14003e040  mov     edx, 104h
0x14003e045  call    RtlStringCchCopyW
0x14003e04a  mov     ebx, eax
0x14003e04c  test    eax, eax
0x14003e04e  jns     short loc_14003E062
0x14003e050  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x14003e057  mov     r8d, 4FEh
0x14003e05d  jmp     loc_14003DFAE
0x14003e062  xor     ebx, ebx
0x14003e064  mov     eax, ebx
0x14003e066  mov     rcx, [rsp+288h+var_48]
0x14003e06e  xor     rcx, rsp; StackCookie
0x14003e071  call    __security_check_cookie
0x14003e076  add     rsp, 258h
0x14003e07d  pop     r15
0x14003e07f  pop     r14
0x14003e081  pop     r12
0x14003e083  pop     rdi
0x14003e084  pop     rsi
0x14003e085  pop     rbx
0x14003e086  retn
```
