# MsvpCalculateNtlm2Challenge

- ea: `0x180008050`
- end: `0x1800081e6`
- name: `MsvpCalculateNtlm2Challenge`
- size: `406`
- prototype: `__int64 __fastcall(PUCHAR pbInput, PUCHAR)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180008050`
- `0x180009664`
- `0x18000c560`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x1800080fd`
- `bcrypt!BCryptHashData` at `0x180008140`
- `bcrypt!BCryptHashData` at `0x1800080fd`
- `bcrypt!BCryptHashData` at `0x180008140`
- `bcrypt!BCryptCreateHash` at `0x1800080a4`
- `bcrypt!BCryptCreateHash` at `0x1800080a4`
- `bcrypt!BCryptDestroyHash` at `0x1800081c1`
- `bcrypt!BCryptDestroyHash` at `0x1800081c1`
- `bcrypt!BCryptFinishHash` at `0x180008180`
- `bcrypt!BCryptFinishHash` at `0x180008180`

## pseudocode

```c
__int64 __fastcall MsvpCalculateNtlm2Challenge(PUCHAR pbInput, PUCHAR a2, _QWORD *a3)
{
  NTSTATUS v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  BCRYPT_HASH_HANDLE hHash; // [rsp+40h] [rbp-38h] BYREF
  UCHAR pbOutput[16]; // [rsp+48h] [rbp-30h] BYREF

  hHash = 0;
  v6 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x21, &hHash, 0, 0, 0, 0, 0);
  if ( v6 >= 0 )
  {
    v6 = BCryptHashData(hHash, pbInput, 8u, 0);
    if ( v6 >= 0 )
    {
      v6 = BCryptHashData(hHash, a2, 8u, 0);
      if ( v6 >= 0 )
      {
        v6 = BCryptFinishHash(hHash, pbOutput, 0x10u, 0);
        if ( v6 >= 0 )
        {
          *a3 = *(_QWORD *)pbOutput;
        }
        else
        {
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            v8 = 13;
            goto LABEL_5;
          }
        }
      }
      else
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v8 = 12;
          goto LABEL_5;
        }
      }
    }
    else
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v8 = 11;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v8 = 10;
LABEL_5:
      WPP_SF_D(v7[2], v8, WPP_1719d4e6f7f6337b67c9ada63d044132_Traceguids, (unsigned int)v6);
    }
  }
  if ( hHash )
    BCryptDestroyHash(hHash);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180008050  mov     r11, rsp
0x180008053  mov     [r11+20h], rbx
0x180008057  push    rbp
0x180008058  push    rsi
0x180008059  push    rdi
0x18000805a  sub     rsp, 60h
0x18000805e  mov     rax, cs:__security_cookie
0x180008065  xor     rax, rsp
0x180008068  mov     [rsp+78h+var_20], rax
0x18000806d  xor     r9d, r9d; cbHashObject
0x180008070  mov     [rsp+78h+dwFlags], 0; dwFlags
0x180008078  mov     rdi, r8
0x18000807b  mov     [rsp+78h+cbSecret], 0; cbSecret
0x180008083  mov     rbp, rdx
0x180008086  mov     qword ptr [r11-38h], 0
0x18000808e  mov     rsi, rcx
0x180008091  mov     qword ptr [r11-58h], 0
0x180008099  lea     ecx, [r9+21h]; hAlgorithm
0x18000809d  xor     r8d, r8d; pbHashObject
0x1800080a0  lea     rdx, [r11-38h]; phHash
0x1800080a4  call    cs:__imp_BCryptCreateHash
0x1800080aa  mov     ebx, eax
0x1800080ac  test    eax, eax
0x1800080ae  jns     short loc_1800080EE
0x1800080b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800080b7  lea     rax, WPP_GLOBAL_Control
0x1800080be  cmp     rcx, rax
0x1800080c1  jz      loc_1800081B7
0x1800080c7  test    byte ptr [rcx+1Ch], 8
0x1800080cb  jz      loc_1800081B7
0x1800080d1  mov     edx, 0Ah
0x1800080d6  mov     rcx, [rcx+10h]
0x1800080da  lea     r8, WPP_1719d4e6f7f6337b67c9ada63d044132_Traceguids
0x1800080e1  mov     r9d, ebx
0x1800080e4  call    WPP_SF_D
0x1800080e9  jmp     loc_1800081B7
0x1800080ee  mov     rcx, [rsp+78h+hHash]; hHash
0x1800080f3  xor     r9d, r9d; dwFlags
0x1800080f6  mov     rdx, rsi; pbInput
0x1800080f9  lea     r8d, [r9+8]; cbInput
0x1800080fd  call    cs:__imp_BCryptHashData
0x180008103  mov     ebx, eax
0x180008105  test    eax, eax
0x180008107  jns     short loc_180008131
0x180008109  mov     rcx, cs:WPP_GLOBAL_Control
0x180008110  lea     rax, WPP_GLOBAL_Control
0x180008117  cmp     rcx, rax
0x18000811a  jz      loc_1800081B7
0x180008120  test    byte ptr [rcx+1Ch], 8
0x180008124  jz      loc_1800081B7
0x18000812a  mov     edx, 0Bh
0x18000812f  jmp     short loc_1800080D6
0x180008131  mov     rcx, [rsp+78h+hHash]; hHash
0x180008136  xor     r9d, r9d; dwFlags
0x180008139  mov     rdx, rbp; pbInput
0x18000813c  lea     r8d, [r9+8]; cbInput
0x180008140  call    cs:__imp_BCryptHashData
0x180008146  mov     ebx, eax
0x180008148  test    eax, eax
0x18000814a  jns     short loc_18000816F
0x18000814c  mov     rcx, cs:WPP_GLOBAL_Control
0x180008153  lea     rax, WPP_GLOBAL_Control
0x18000815a  cmp     rcx, rax
0x18000815d  jz      short loc_1800081B7
0x18000815f  test    byte ptr [rcx+1Ch], 8
0x180008163  jz      short loc_1800081B7
0x180008165  mov     edx, 0Ch
0x18000816a  jmp     loc_1800080D6
0x18000816f  mov     rcx, [rsp+78h+hHash]; hHash
0x180008174  lea     rdx, [rsp+78h+pbOutput]; pbOutput
0x180008179  xor     r9d, r9d; dwFlags
0x18000817c  lea     r8d, [r9+10h]; cbOutput
0x180008180  call    cs:__imp_BCryptFinishHash
0x180008186  mov     ebx, eax
0x180008188  test    eax, eax
0x18000818a  jns     short loc_1800081AF
0x18000818c  mov     rcx, cs:WPP_GLOBAL_Control
0x180008193  lea     rax, WPP_GLOBAL_Control
0x18000819a  cmp     rcx, rax
0x18000819d  jz      short loc_1800081B7
0x18000819f  test    byte ptr [rcx+1Ch], 8
0x1800081a3  jz      short loc_1800081B7
0x1800081a5  mov     edx, 0Dh
0x1800081aa  jmp     loc_1800080D6
0x1800081af  mov     rax, qword ptr [rsp+78h+pbOutput]
0x1800081b4  mov     [rdi], rax
0x1800081b7  mov     rcx, [rsp+78h+hHash]; hHash
0x1800081bc  test    rcx, rcx
0x1800081bf  jz      short loc_1800081C7
0x1800081c1  call    cs:__imp_BCryptDestroyHash
0x1800081c7  mov     eax, ebx
0x1800081c9  mov     rcx, [rsp+78h+var_20]
0x1800081ce  xor     rcx, rsp; StackCookie
0x1800081d1  call    __security_check_cookie
0x1800081d6  mov     rbx, [rsp+78h+arg_18]
0x1800081de  add     rsp, 60h
0x1800081e2  pop     rdi
0x1800081e3  pop     rsi
0x1800081e4  pop     rbp
0x1800081e5  retn
```
