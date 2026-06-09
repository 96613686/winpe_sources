# MsvpNtlm3Response

- ea: `0x180009090`
- end: `0x1800093cc`
- name: `MsvpNtlm3Response`
- size: `828`
- prototype: `__int64 __fastcall(PUCHAR pbSecret, __int64, __int64, int, PUCHAR pbInput, __int64, PUCHAR pbOutput, PUCHAR, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180008a90`
- `0x18000a680`

## callees

- `0x180008370`
- `0x180009090`
- `0x180009664`
- `0x180009718`
- `0x18000c560`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x1800091df`
- `bcrypt!BCryptHashData` at `0x18000922b`
- `bcrypt!BCryptHashData` at `0x18000931e`
- `bcrypt!BCryptHashData` at `0x1800091df`
- `bcrypt!BCryptHashData` at `0x18000922b`
- `bcrypt!BCryptHashData` at `0x18000931e`
- `bcrypt!BCryptCreateHash` at `0x18000919a`
- `bcrypt!BCryptCreateHash` at `0x1800092da`
- `bcrypt!BCryptCreateHash` at `0x18000919a`
- `bcrypt!BCryptCreateHash` at `0x1800092da`
- `bcrypt!BCryptDestroyHash` at `0x1800092ae`
- `bcrypt!BCryptDestroyHash` at `0x18000938d`
- `bcrypt!BCryptDestroyHash` at `0x1800093a7`
- `bcrypt!BCryptDestroyHash` at `0x1800092ae`
- `bcrypt!BCryptDestroyHash` at `0x18000938d`
- `bcrypt!BCryptDestroyHash` at `0x1800093a7`
- `bcrypt!BCryptFinishHash` at `0x180009273`
- `bcrypt!BCryptFinishHash` at `0x18000935a`
- `bcrypt!BCryptFinishHash` at `0x180009273`
- `bcrypt!BCryptFinishHash` at `0x18000935a`

## pseudocode

```c
__int64 __fastcall MsvpNtlm3Response(
        PUCHAR pbSecret,
        __int64 a2,
        __int64 a3,
        int a4,
        PUCHAR pbInput,
        __int64 a6,
        PUCHAR pbOutput,
        PUCHAR a8,
        _QWORD *a9)
{
  NTSTATUS v10; // ebx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-38h] BYREF
  int v15; // [rsp+48h] [rbp-30h]
  __int64 v16; // [rsp+50h] [rbp-28h]
  UCHAR v17[16]; // [rsp+58h] [rbp-20h] BYREF

  v16 = a6;
  v15 = a4;
  phHash = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_sZZ(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, a3, (unsigned int)"MsvpNtlm3Response", a3, a2);
  v10 = MsvpCalculateNtlm3Owf(pbSecret);
  if ( v10 >= 0 )
  {
    v10 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x91, &phHash, 0, 0, v17, 0x10u, 0);
    if ( v10 >= 0 )
    {
      v10 = BCryptHashData(phHash, pbInput, 8u, 0);
      if ( v10 >= 0 )
      {
        v10 = BCryptHashData(phHash, (PUCHAR)(v16 + 16), v15 + 32, 0);
        if ( v10 >= 0 )
        {
          v10 = BCryptFinishHash(phHash, pbOutput, 0x10u, 0);
          if ( v10 >= 0 )
          {
            BCryptDestroyHash(phHash);
            phHash = 0;
            v10 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x91, &phHash, 0, 0, v17, 0x10u, 0);
            if ( v10 >= 0 )
            {
              v10 = BCryptHashData(phHash, pbOutput, 0x10u, 0);
              if ( v10 >= 0 )
              {
                v10 = BCryptFinishHash(phHash, a8, 0x10u, 0);
                if ( v10 >= 0 )
                {
                  BCryptDestroyHash(phHash);
                  *a9 = *(_QWORD *)a8;
                  phHash = 0;
                }
                else
                {
                  v11 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                  {
                    v12 = 39;
                    goto LABEL_8;
                  }
                }
              }
              else
              {
                v11 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                {
                  v12 = 38;
                  goto LABEL_8;
                }
              }
            }
            else
            {
              v11 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                v12 = 37;
                goto LABEL_8;
              }
            }
          }
          else
          {
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            {
              v12 = 36;
              goto LABEL_8;
            }
          }
        }
        else
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            v12 = 35;
            goto LABEL_8;
          }
        }
      }
      else
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v12 = 34;
          goto LABEL_8;
        }
      }
    }
    else
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v12 = 33;
        goto LABEL_8;
      }
    }
  }
  else
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v12 = 32;
LABEL_8:
      WPP_SF_D(v11[2], v12, WPP_1719d4e6f7f6337b67c9ada63d044132_Traceguids, (unsigned int)v10);
    }
  }
  if ( phHash )
    BCryptDestroyHash(phHash);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180009090  push    rbp
0x180009092  push    rbx
0x180009093  push    rsi
0x180009094  push    rdi
0x180009095  push    r12
0x180009097  push    r13
0x180009099  push    r14
0x18000909b  push    r15
0x18000909d  mov     rbp, rsp
0x1800090a0  sub     rsp, 78h
0x1800090a4  mov     rax, cs:__security_cookie
0x1800090ab  xor     rax, rsp
0x1800090ae  mov     [rbp+var_10], rax
0x1800090b2  mov     rax, [rbp+arg_28]
0x1800090b6  mov     rdi, r8
0x1800090b9  mov     r12, [rbp+pbInput]
0x1800090bd  mov     rbx, rdx
0x1800090c0  mov     r14, [rbp+pbOutput]
0x1800090c4  mov     r15, rcx
0x1800090c7  mov     rsi, [rbp+arg_38]
0x1800090ce  mov     r13, [rbp+arg_40]
0x1800090d5  mov     [rbp+var_28], rax
0x1800090d9  mov     [rbp+var_30], r9d
0x1800090dd  mov     [rbp+phHash], 0
0x1800090e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800090ec  lea     rax, WPP_GLOBAL_Control
0x1800090f3  cmp     rcx, rax
0x1800090f6  jz      short loc_18000911D
0x1800090f8  test    byte ptr [rcx+1Ch], 8
0x1800090fc  jz      short loc_18000911D
0x1800090fe  mov     rcx, [rcx+10h]
0x180009102  lea     r9, aMsvpntlm3respo_0; "MsvpNtlm3Response"
0x180009109  mov     edx, 1Fh
0x18000910e  mov     qword ptr [rsp+78h+cbSecret], rbx
0x180009113  mov     [rsp+78h+pbSecret], r8
0x180009118  call    WPP_SF_sZZ
0x18000911d  lea     r9, [rbp+var_20]
0x180009121  mov     r8, rdi
0x180009124  mov     rdx, rbx
0x180009127  mov     rcx, r15; pbSecret
0x18000912a  call    MsvpCalculateNtlm3Owf
0x18000912f  xor     r15d, r15d
0x180009132  mov     ebx, eax
0x180009134  test    eax, eax
0x180009136  jns     short loc_180009175
0x180009138  mov     rcx, cs:WPP_GLOBAL_Control
0x18000913f  lea     rax, WPP_GLOBAL_Control
0x180009146  cmp     rcx, rax
0x180009149  jz      loc_18000939E
0x18000914f  test    byte ptr [rcx+1Ch], 8
0x180009153  jz      loc_18000939E
0x180009159  lea     edx, [r15+20h]
0x18000915d  mov     rcx, [rcx+10h]
0x180009161  lea     r8, WPP_1719d4e6f7f6337b67c9ada63d044132_Traceguids
0x180009168  mov     r9d, ebx
0x18000916b  call    WPP_SF_D
0x180009170  jmp     loc_18000939E
0x180009175  mov     [rsp+78h+dwFlags], r15d; dwFlags
0x18000917a  lea     rax, [rbp+var_20]
0x18000917e  mov     [rsp+78h+cbSecret], 10h; cbSecret
0x180009186  lea     rdx, [rbp+phHash]; phHash
0x18000918a  xor     r9d, r9d; cbHashObject
0x18000918d  mov     [rsp+78h+pbSecret], rax; pbSecret
0x180009192  xor     r8d, r8d; pbHashObject
0x180009195  mov     ecx, 91h; hAlgorithm
0x18000919a  call    cs:__imp_BCryptCreateHash
0x1800091a0  mov     ebx, eax
0x1800091a2  test    eax, eax
0x1800091a4  jns     short loc_1800091CE
0x1800091a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800091ad  lea     rax, WPP_GLOBAL_Control
0x1800091b4  cmp     rcx, rax
0x1800091b7  jz      loc_18000939E
0x1800091bd  test    byte ptr [rcx+1Ch], 8
0x1800091c1  jz      loc_18000939E
0x1800091c7  mov     edx, 21h ; '!'
0x1800091cc  jmp     short loc_18000915D
0x1800091ce  mov     rcx, [rbp+phHash]; hHash
0x1800091d2  xor     r9d, r9d; dwFlags
0x1800091d5  mov     rdx, r12; pbInput
0x1800091d8  lea     edi, [r9+8]
0x1800091dc  mov     r8d, edi; cbInput
0x1800091df  call    cs:__imp_BCryptHashData
0x1800091e5  mov     ebx, eax
0x1800091e7  test    eax, eax
0x1800091e9  jns     short loc_180009214
0x1800091eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800091f2  lea     rax, WPP_GLOBAL_Control
0x1800091f9  cmp     rcx, rax
0x1800091fc  jz      loc_18000939E
0x180009202  test    [rcx+1Ch], dil
0x180009206  jz      loc_18000939E
0x18000920c  lea     edx, [rdi+1Ah]
0x18000920f  jmp     loc_18000915D
0x180009214  mov     r8d, [rbp+var_30]
0x180009218  xor     r9d, r9d; dwFlags
0x18000921b  mov     rdx, [rbp+var_28]
0x18000921f  add     r8d, 20h ; ' '; cbInput
0x180009223  mov     rcx, [rbp+phHash]; hHash
0x180009227  add     rdx, 10h; pbInput
0x18000922b  call    cs:__imp_BCryptHashData
0x180009231  mov     ebx, eax
0x180009233  test    eax, eax
0x180009235  jns     short loc_180009262
0x180009237  mov     rcx, cs:WPP_GLOBAL_Control
0x18000923e  lea     rax, WPP_GLOBAL_Control
0x180009245  cmp     rcx, rax
0x180009248  jz      loc_18000939E
0x18000924e  test    [rcx+1Ch], dil
0x180009252  jz      loc_18000939E
0x180009258  mov     edx, 23h ; '#'
0x18000925d  jmp     loc_18000915D
0x180009262  mov     rcx, [rbp+phHash]; hHash
0x180009266  xor     r9d, r9d; dwFlags
0x180009269  mov     rdx, r14; pbOutput
0x18000926c  lea     r12d, [r9+10h]
0x180009270  mov     r8d, r12d; cbOutput
0x180009273  call    cs:__imp_BCryptFinishHash
0x180009279  mov     ebx, eax
0x18000927b  test    eax, eax
0x18000927d  jns     short loc_1800092AA
0x18000927f  mov     rcx, cs:WPP_GLOBAL_Control
0x180009286  lea     rax, WPP_GLOBAL_Control
0x18000928d  cmp     rcx, rax
0x180009290  jz      loc_18000939E
0x180009296  test    [rcx+1Ch], dil
0x18000929a  jz      loc_18000939E
0x1800092a0  lea     edx, [r12+14h]
0x1800092a5  jmp     loc_18000915D
0x1800092aa  mov     rcx, [rbp+phHash]; hHash
0x1800092ae  call    cs:__imp_BCryptDestroyHash
0x1800092b4  lea     rax, [rbp+var_20]
0x1800092b8  mov     [rsp+78h+dwFlags], r15d; dwFlags
0x1800092bd  mov     [rsp+78h+cbSecret], r12d; cbSecret
0x1800092c2  lea     rdx, [rbp+phHash]; phHash
0x1800092c6  xor     r9d, r9d; cbHashObject
0x1800092c9  mov     [rsp+78h+pbSecret], rax; pbSecret
0x1800092ce  xor     r8d, r8d; pbHashObject
0x1800092d1  mov     [rbp+phHash], r15
0x1800092d5  mov     ecx, 91h; hAlgorithm
0x1800092da  call    cs:__imp_BCryptCreateHash
0x1800092e0  mov     ebx, eax
0x1800092e2  test    eax, eax
0x1800092e4  jns     short loc_180009311
0x1800092e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800092ed  lea     rax, WPP_GLOBAL_Control
0x1800092f4  cmp     rcx, rax
0x1800092f7  jz      loc_18000939E
0x1800092fd  test    [rcx+1Ch], dil
0x180009301  jz      loc_18000939E
0x180009307  mov     edx, 25h ; '%'
0x18000930c  jmp     loc_18000915D
0x180009311  mov     rcx, [rbp+phHash]; hHash
0x180009315  xor     r9d, r9d; dwFlags
0x180009318  mov     r8d, r12d; cbInput
0x18000931b  mov     rdx, r14; pbInput
0x18000931e  call    cs:__imp_BCryptHashData
0x180009324  mov     ebx, eax
0x180009326  test    eax, eax
0x180009328  jns     short loc_18000934D
0x18000932a  mov     rcx, cs:WPP_GLOBAL_Control
0x180009331  lea     rax, WPP_GLOBAL_Control
0x180009338  cmp     rcx, rax
0x18000933b  jz      short loc_18000939E
0x18000933d  test    [rcx+1Ch], dil
0x180009341  jz      short loc_18000939E
0x180009343  mov     edx, 26h ; '&'
0x180009348  jmp     loc_18000915D
0x18000934d  mov     rcx, [rbp+phHash]; hHash
0x180009351  xor     r9d, r9d; dwFlags
0x180009354  mov     r8d, r12d; cbOutput
0x180009357  mov     rdx, rsi; pbOutput
0x18000935a  call    cs:__imp_BCryptFinishHash
0x180009360  mov     ebx, eax
0x180009362  test    eax, eax
0x180009364  jns     short loc_180009389
0x180009366  mov     rcx, cs:WPP_GLOBAL_Control
0x18000936d  lea     rax, WPP_GLOBAL_Control
0x180009374  cmp     rcx, rax
0x180009377  jz      short loc_18000939E
0x180009379  test    [rcx+1Ch], dil
0x18000937d  jz      short loc_18000939E
0x18000937f  mov     edx, 27h ; '''
0x180009384  jmp     loc_18000915D
0x180009389  mov     rcx, [rbp+phHash]; hHash
0x18000938d  call    cs:__imp_BCryptDestroyHash
0x180009393  mov     rax, [rsi]
0x180009396  mov     [r13+0], rax
0x18000939a  mov     [rbp+phHash], r15
0x18000939e  mov     rcx, [rbp+phHash]; hHash
0x1800093a2  test    rcx, rcx
0x1800093a5  jz      short loc_1800093AD
0x1800093a7  call    cs:__imp_BCryptDestroyHash
0x1800093ad  mov     eax, ebx
0x1800093af  mov     rcx, [rbp+var_10]
0x1800093b3  xor     rcx, rsp; StackCookie
0x1800093b6  call    __security_check_cookie
0x1800093bb  add     rsp, 78h
0x1800093bf  pop     r15
0x1800093c1  pop     r14
0x1800093c3  pop     r13
0x1800093c5  pop     r12
0x1800093c7  pop     rdi
0x1800093c8  pop     rsi
0x1800093c9  pop     rbx
0x1800093ca  pop     rbp
0x1800093cb  retn
```
