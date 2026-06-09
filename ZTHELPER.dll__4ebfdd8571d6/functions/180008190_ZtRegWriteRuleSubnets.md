# ZtRegWriteRuleSubnets

- ea: `0x180008190`
- end: `0x180008359`
- name: `ZtRegWriteRuleSubnets`
- size: `457`
- prototype: `__int64 __fastcall(HKEY hKey, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180008360`

## callees

- `0x1800014b0`
- `0x18000206a`
- `0x1800077b0`
- `0x180008190`
- `0x18000ee64`
- `0x18000f78c`
- `0x180012564`
- `0x1800125d4`
- `0x180015008`

## pseudocode

```c
__int64 __fastcall ZtRegWriteRuleSubnets(HKEY hKey, __int64 a2)
{
  BYTE *v4; // rsi
  signed int v5; // ebx
  __int64 v6; // rax
  wchar_t *v7; // rax
  unsigned int i; // edi
  int v9; // eax
  int appended; // eax
  int v11; // eax
  STRSAFE_LPWSTR ppszDestEnd; // [rsp+38h] [rbp-E0h] BYREF
  __int64 v14; // [rsp+40h] [rbp-D8h]
  WCHAR S[72]; // [rsp+50h] [rbp-C8h] BYREF

  v4 = 0;
  ppszDestEnd = 0;
  v14 = 0;
  memset_0(S, 0, 0x8Au);
  if ( a2 )
  {
    if ( hKey )
    {
      v5 = 0;
      if ( *(_DWORD *)(a2 + 40) )
      {
        v6 = *(unsigned int *)(a2 + 40);
        v14 = 69 * v6;
        v7 = (wchar_t *)Dns_Allocate(138 * v6);
        v4 = (BYTE *)v7;
        if ( v7 )
        {
          ppszDestEnd = v7;
          for ( i = 0; i < *(_DWORD *)(a2 + 40); ++i )
          {
            v9 = DnsConvertSockaddrInetToString(S);
            v5 = v9;
            if ( v9 > 0 )
              v5 = (unsigned __int16)v9 | 0x80070000;
            if ( v5 < 0 )
              goto LABEL_21;
            appended = ZtAppendSubnet(S, &ppszDestEnd);
            v5 = appended;
            if ( appended > 0 )
              v5 = (unsigned __int16)appended | 0x80070000;
            if ( v5 < 0 )
              goto LABEL_21;
          }
          v11 = SetRegistryString(hKey, L"Subnets", v4);
          v5 = v11;
          if ( v11 > 0 )
            v5 = (unsigned __int16)v11 | 0x80070000;
        }
        else
        {
          v5 = -2147024809;
        }
      }
    }
    else
    {
      v5 = -2147024809;
    }
  }
  else
  {
    v5 = -2147024809;
  }
LABEL_21:
  Dns_Free(v4);
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_d(1026, 0x1Au, (ULONGLONG)WPP_5daa81f1f60e30d3715838f17166c4a8_Traceguids, v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180008190  mov     [rsp+arg_10], rbx
0x180008195  push    rbp
0x180008196  push    rsi
0x180008197  push    rdi
0x180008198  push    r14
0x18000819a  push    r15
0x18000819c  sub     rsp, 0F0h
0x1800081a3  mov     rax, cs:__security_cookie
0x1800081aa  xor     rax, rsp
0x1800081ad  mov     [rsp+118h+var_38], rax
0x1800081b5  mov     rbp, rdx
0x1800081b8  mov     [rsp+118h+var_E4], 0
0x1800081c0  mov     r15, rcx
0x1800081c3  xor     esi, esi
0x1800081c5  xor     edx, edx; Val
0x1800081c7  mov     [rsp+118h+var_E0], rsi
0x1800081cc  lea     rcx, [rsp+118h+S]; void *
0x1800081d1  mov     [rsp+118h+var_D8], rsi
0x1800081d6  mov     r8d, 8Ah; Size
0x1800081dc  call    memset_0
0x1800081e1  test    rbp, rbp
0x1800081e4  jnz     short loc_1800081F8
0x1800081e6  mov     ebx, 80070057h
0x1800081eb  mov     [rsp+118h+var_E4], 0BDh
0x1800081f3  jmp     loc_180008306
0x1800081f8  test    r15, r15
0x1800081fb  jnz     short loc_18000820F
0x1800081fd  mov     ebx, 80070057h
0x180008202  mov     [rsp+118h+var_E4], 0BEh
0x18000820a  jmp     loc_180008306
0x18000820f  xor     ebx, ebx
0x180008211  cmp     [rbp+28h], ebx
0x180008214  jz      loc_180008306
0x18000821a  mov     eax, [rbp+28h]
0x18000821d  imul    rcx, rax, 45h ; 'E'
0x180008221  mov     [rsp+118h+var_D8], rcx
0x180008226  add     rcx, rcx
0x180008229  call    Dns_Allocate
0x18000822e  mov     rsi, rax
0x180008231  test    rax, rax
0x180008234  jnz     short loc_180008248
0x180008236  mov     ebx, 80070057h
0x18000823b  mov     [rsp+118h+var_E4], 0C7h
0x180008243  jmp     loc_180008306
0x180008248  mov     [rsp+118h+var_E0], rsi
0x18000824d  xor     edi, edi
0x18000824f  cmp     edi, [rbp+28h]
0x180008252  jnb     loc_1800082D9
0x180008258  mov     rdx, [rbp+20h]
0x18000825c  lea     rcx, [rsp+118h+S]; S
0x180008261  mov     r14d, edi
0x180008264  shl     r14, 5
0x180008268  add     rdx, r14
0x18000826b  call    DnsConvertSockaddrInetToString
0x180008270  mov     ebx, eax
0x180008272  test    eax, eax
0x180008274  jle     short loc_18000827F
0x180008276  movzx   ebx, ax
0x180008279  or      ebx, 80070000h
0x18000827f  test    ebx, ebx
0x180008281  js      short loc_1800082CF
0x180008283  mov     rdx, [rbp+20h]
0x180008287  lea     rax, [rsp+118h+var_E0]
0x18000828c  xor     r8d, r8d
0x18000828f  mov     [rsp+118h+ppszDestEnd], rax; ppszDestEnd
0x180008294  test    edi, edi
0x180008296  lea     r9, [rsp+118h+var_D8]
0x18000829b  lea     rcx, [rsp+118h+S]; pszSrc
0x1800082a0  mov     dl, [r14+rdx+1Ch]
0x1800082a5  setnz   r8b
0x1800082a9  call    ZtAppendSubnet
0x1800082ae  mov     ebx, eax
0x1800082b0  test    eax, eax
0x1800082b2  jle     short loc_1800082BD
0x1800082b4  movzx   ebx, ax
0x1800082b7  or      ebx, 80070000h
0x1800082bd  test    ebx, ebx
0x1800082bf  js      short loc_1800082C5
0x1800082c1  inc     edi
0x1800082c3  jmp     short loc_18000824F
0x1800082c5  mov     [rsp+118h+var_E4], 0D4h
0x1800082cd  jmp     short loc_180008306
0x1800082cf  mov     [rsp+118h+var_E4], 0CEh
0x1800082d7  jmp     short loc_180008306
0x1800082d9  mov     r8, rsi; lpData
0x1800082dc  lea     rdx, aSubnets; "Subnets"
0x1800082e3  mov     rcx, r15; hKey
0x1800082e6  call    SetRegistryString
0x1800082eb  mov     ebx, eax
0x1800082ed  test    eax, eax
0x1800082ef  jle     short loc_1800082FA
0x1800082f1  movzx   ebx, ax
0x1800082f4  or      ebx, 80070000h
0x1800082fa  test    ebx, ebx
0x1800082fc  jns     short loc_180008306
0x1800082fe  mov     [rsp+118h+var_E4], 0D9h
0x180008306  mov     rcx, rsi; lpMem
0x180008309  call    Dns_Free
0x18000830e  test    byte ptr cs:xmmword_18001F260, 4
0x180008315  jz      short loc_180008330
0x180008317  mov     edx, 1Ah
0x18000831c  lea     r8, WPP_5daa81f1f60e30d3715838f17166c4a8_Traceguids
0x180008323  mov     ecx, 402h
0x180008328  mov     r9d, ebx
0x18000832b  call    WPP_SF_d
0x180008330  mov     eax, ebx
0x180008332  mov     rcx, [rsp+118h+var_38]
0x18000833a  xor     rcx, rsp; StackCookie
0x18000833d  call    __security_check_cookie
0x180008342  mov     rbx, [rsp+118h+arg_10]
0x18000834a  add     rsp, 0F0h
0x180008351  pop     r15
0x180008353  pop     r14
0x180008355  pop     rdi
0x180008356  pop     rsi
0x180008357  pop     rbp
0x180008358  retn
```
