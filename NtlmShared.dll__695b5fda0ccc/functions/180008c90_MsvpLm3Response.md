# MsvpLm3Response

- ea: `0x180008c90`
- end: `0x180008fd0`
- name: `MsvpLm3Response`
- size: `832`
- prototype: `__int64 __fastcall(PUCHAR pbSecret, __int64, __int64, UCHAR *, __int64, PUCHAR pbOutput, PUCHAR, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180008a90`
- `0x18000a550`

## callees

- `0x180008370`
- `0x180008c90`
- `0x180009664`
- `0x180009718`
- `0x18000c560`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x180008dd8`
- `bcrypt!BCryptHashData` at `0x180008e1f`
- `bcrypt!BCryptHashData` at `0x180008f23`
- `bcrypt!BCryptHashData` at `0x180008dd8`
- `bcrypt!BCryptHashData` at `0x180008e1f`
- `bcrypt!BCryptHashData` at `0x180008f23`
- `bcrypt!BCryptCreateHash` at `0x180008d93`
- `bcrypt!BCryptCreateHash` at `0x180008edf`
- `bcrypt!BCryptCreateHash` at `0x180008d93`
- `bcrypt!BCryptCreateHash` at `0x180008edf`
- `bcrypt!BCryptDestroyHash` at `0x180008ea1`
- `bcrypt!BCryptDestroyHash` at `0x180008f92`
- `bcrypt!BCryptDestroyHash` at `0x180008fab`
- `bcrypt!BCryptDestroyHash` at `0x180008ea1`
- `bcrypt!BCryptDestroyHash` at `0x180008f92`
- `bcrypt!BCryptDestroyHash` at `0x180008fab`
- `bcrypt!BCryptFinishHash` at `0x180008e67`
- `bcrypt!BCryptFinishHash` at `0x180008f5f`
- `bcrypt!BCryptFinishHash` at `0x180008e67`
- `bcrypt!BCryptFinishHash` at `0x180008f5f`

## pseudocode

```c
__int64 __fastcall MsvpLm3Response(
        PUCHAR pbSecret,
        __int64 a2,
        __int64 a3,
        UCHAR *a4,
        __int64 a5,
        PUCHAR pbOutput,
        PUCHAR a7,
        _QWORD *a8)
{
  NTSTATUS v10; // ebx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-38h] BYREF
  __int64 v15; // [rsp+48h] [rbp-30h]
  UCHAR v16[16]; // [rsp+50h] [rbp-28h] BYREF

  v15 = a5;
  phHash = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_sZZ(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, a3, (unsigned int)"MsvpLm3Response", a3, a2);
  v10 = MsvpCalculateNtlm3Owf(pbSecret);
  if ( v10 >= 0 )
  {
    v10 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x91, &phHash, 0, 0, v16, 0x10u, 0);
    if ( v10 >= 0 )
    {
      v10 = BCryptHashData(phHash, a4, 8u, 0);
      if ( v10 >= 0 )
      {
        v10 = BCryptHashData(phHash, (PUCHAR)(v15 + 16), 8u, 0);
        if ( v10 >= 0 )
        {
          v10 = BCryptFinishHash(phHash, pbOutput, 0x10u, 0);
          if ( v10 >= 0 )
          {
            BCryptDestroyHash(phHash);
            phHash = 0;
            if ( !a7 || !a8 )
              return (unsigned int)v10;
            v10 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x91, &phHash, 0, 0, v16, 0x10u, 0);
            if ( v10 >= 0 )
            {
              v10 = BCryptHashData(phHash, pbOutput, 0x10u, 0);
              if ( v10 >= 0 )
              {
                v10 = BCryptFinishHash(phHash, a7, 0x10u, 0);
                if ( v10 >= 0 )
                {
                  BCryptDestroyHash(phHash);
                  *a8 = *(_QWORD *)a7;
                  phHash = 0;
                }
                else
                {
                  v11 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                  {
                    v12 = 30;
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
                  v12 = 29;
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
                v12 = 28;
                goto LABEL_8;
              }
            }
          }
          else
          {
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            {
              v12 = 27;
              goto LABEL_8;
            }
          }
        }
        else
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            v12 = 26;
            goto LABEL_8;
          }
        }
      }
      else
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v12 = 25;
          goto LABEL_8;
        }
      }
    }
    else
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v12 = 24;
        goto LABEL_8;
      }
    }
  }
  else
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v12 = 23;
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
0x180008c90  push    rbp
0x180008c92  push    rbx
0x180008c93  push    rsi
0x180008c94  push    rdi
0x180008c95  push    r12
0x180008c97  push    r13
0x180008c99  push    r14
0x180008c9b  push    r15
0x180008c9d  mov     rbp, rsp
0x180008ca0  sub     rsp, 78h
0x180008ca4  mov     rax, cs:__security_cookie
0x180008cab  xor     rax, rsp
0x180008cae  mov     [rbp+var_18], rax
0x180008cb2  mov     rax, [rbp+arg_20]
0x180008cb6  mov     r13, r9
0x180008cb9  mov     r15, [rbp+pbOutput]
0x180008cbd  mov     rsi, r8
0x180008cc0  mov     rdi, [rbp+arg_30]
0x180008cc4  mov     rbx, rdx
0x180008cc7  mov     r14, [rbp+arg_38]
0x180008cce  mov     r12, rcx
0x180008cd1  mov     [rbp+var_30], rax
0x180008cd5  mov     [rbp+phHash], 0
0x180008cdd  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ce4  lea     rax, WPP_GLOBAL_Control
0x180008ceb  cmp     rcx, rax
0x180008cee  jz      short loc_180008D15
0x180008cf0  test    byte ptr [rcx+1Ch], 8
0x180008cf4  jz      short loc_180008D15
0x180008cf6  mov     rcx, [rcx+10h]
0x180008cfa  lea     r9, aMsvplm3respons_0; "MsvpLm3Response"
0x180008d01  mov     edx, 16h
0x180008d06  mov     qword ptr [rsp+78h+cbSecret], rbx
0x180008d0b  mov     [rsp+78h+pbSecret], r8
0x180008d10  call    WPP_SF_sZZ
0x180008d15  lea     r9, [rbp+var_28]
0x180008d19  mov     r8, rsi
0x180008d1c  mov     rdx, rbx
0x180008d1f  mov     rcx, r12; pbSecret
0x180008d22  call    MsvpCalculateNtlm3Owf
0x180008d27  xor     r12d, r12d
0x180008d2a  mov     ebx, eax
0x180008d2c  test    eax, eax
0x180008d2e  jns     short loc_180008D6E
0x180008d30  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d37  lea     rax, WPP_GLOBAL_Control
0x180008d3e  cmp     rcx, rax
0x180008d41  jz      loc_180008FA2
0x180008d47  test    byte ptr [rcx+1Ch], 8
0x180008d4b  jz      loc_180008FA2
0x180008d51  lea     edx, [r12+17h]
0x180008d56  mov     rcx, [rcx+10h]
0x180008d5a  lea     r8, WPP_1719d4e6f7f6337b67c9ada63d044132_Traceguids
0x180008d61  mov     r9d, ebx
0x180008d64  call    WPP_SF_D
0x180008d69  jmp     loc_180008FA2
0x180008d6e  mov     [rsp+78h+dwFlags], r12d; dwFlags
0x180008d73  lea     rax, [rbp+var_28]
0x180008d77  mov     [rsp+78h+cbSecret], 10h; cbSecret
0x180008d7f  lea     rdx, [rbp+phHash]; phHash
0x180008d83  xor     r9d, r9d; cbHashObject
0x180008d86  mov     [rsp+78h+pbSecret], rax; pbSecret
0x180008d8b  xor     r8d, r8d; pbHashObject
0x180008d8e  mov     ecx, 91h; hAlgorithm
0x180008d93  call    cs:__imp_BCryptCreateHash
0x180008d99  mov     ebx, eax
0x180008d9b  test    eax, eax
0x180008d9d  jns     short loc_180008DC7
0x180008d9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008da6  lea     rax, WPP_GLOBAL_Control
0x180008dad  cmp     rcx, rax
0x180008db0  jz      loc_180008FA2
0x180008db6  test    byte ptr [rcx+1Ch], 8
0x180008dba  jz      loc_180008FA2
0x180008dc0  mov     edx, 18h
0x180008dc5  jmp     short loc_180008D56
0x180008dc7  mov     rcx, [rbp+phHash]; hHash
0x180008dcb  xor     r9d, r9d; dwFlags
0x180008dce  mov     rdx, r13; pbInput
0x180008dd1  lea     esi, [r9+8]
0x180008dd5  mov     r8d, esi; cbInput
0x180008dd8  call    cs:__imp_BCryptHashData
0x180008dde  mov     ebx, eax
0x180008de0  test    eax, eax
0x180008de2  jns     short loc_180008E0D
0x180008de4  mov     rcx, cs:WPP_GLOBAL_Control
0x180008deb  lea     rax, WPP_GLOBAL_Control
0x180008df2  cmp     rcx, rax
0x180008df5  jz      loc_180008FA2
0x180008dfb  test    [rcx+1Ch], sil
0x180008dff  jz      loc_180008FA2
0x180008e05  lea     edx, [rsi+11h]
0x180008e08  jmp     loc_180008D56
0x180008e0d  mov     rdx, [rbp+var_30]
0x180008e11  xor     r9d, r9d; dwFlags
0x180008e14  mov     rcx, [rbp+phHash]; hHash
0x180008e18  add     rdx, 10h; pbInput
0x180008e1c  mov     r8d, esi; cbInput
0x180008e1f  call    cs:__imp_BCryptHashData
0x180008e25  mov     ebx, eax
0x180008e27  test    eax, eax
0x180008e29  jns     short loc_180008E56
0x180008e2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e32  lea     rax, WPP_GLOBAL_Control
0x180008e39  cmp     rcx, rax
0x180008e3c  jz      loc_180008FA2
0x180008e42  test    [rcx+1Ch], sil
0x180008e46  jz      loc_180008FA2
0x180008e4c  mov     edx, 1Ah
0x180008e51  jmp     loc_180008D56
0x180008e56  mov     rcx, [rbp+phHash]; hHash
0x180008e5a  xor     r9d, r9d; dwFlags
0x180008e5d  mov     rdx, r15; pbOutput
0x180008e60  lea     r13d, [r9+10h]
0x180008e64  mov     r8d, r13d; cbOutput
0x180008e67  call    cs:__imp_BCryptFinishHash
0x180008e6d  mov     ebx, eax
0x180008e6f  test    eax, eax
0x180008e71  jns     short loc_180008E9D
0x180008e73  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e7a  lea     rax, WPP_GLOBAL_Control
0x180008e81  cmp     rcx, rax
0x180008e84  jz      loc_180008FA2
0x180008e8a  test    [rcx+1Ch], sil
0x180008e8e  jz      loc_180008FA2
0x180008e94  lea     edx, [r13+0Bh]
0x180008e98  jmp     loc_180008D56
0x180008e9d  mov     rcx, [rbp+phHash]; hHash
0x180008ea1  call    cs:__imp_BCryptDestroyHash
0x180008ea7  mov     [rbp+phHash], r12
0x180008eab  test    rdi, rdi
0x180008eae  jz      loc_180008FB1
0x180008eb4  test    r14, r14
0x180008eb7  jz      loc_180008FB1
0x180008ebd  mov     [rsp+78h+dwFlags], r12d; dwFlags
0x180008ec2  lea     rax, [rbp+var_28]
0x180008ec6  mov     [rsp+78h+cbSecret], r13d; cbSecret
0x180008ecb  lea     rdx, [rbp+phHash]; phHash
0x180008ecf  xor     r9d, r9d; cbHashObject
0x180008ed2  mov     [rsp+78h+pbSecret], rax; pbSecret
0x180008ed7  xor     r8d, r8d; pbHashObject
0x180008eda  mov     ecx, 91h; hAlgorithm
0x180008edf  call    cs:__imp_BCryptCreateHash
0x180008ee5  mov     ebx, eax
0x180008ee7  test    eax, eax
0x180008ee9  jns     short loc_180008F16
0x180008eeb  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ef2  lea     rax, WPP_GLOBAL_Control
0x180008ef9  cmp     rcx, rax
0x180008efc  jz      loc_180008FA2
0x180008f02  test    [rcx+1Ch], sil
0x180008f06  jz      loc_180008FA2
0x180008f0c  mov     edx, 1Ch
0x180008f11  jmp     loc_180008D56
0x180008f16  mov     rcx, [rbp+phHash]; hHash
0x180008f1a  xor     r9d, r9d; dwFlags
0x180008f1d  mov     r8d, r13d; cbInput
0x180008f20  mov     rdx, r15; pbInput
0x180008f23  call    cs:__imp_BCryptHashData
0x180008f29  mov     ebx, eax
0x180008f2b  test    eax, eax
0x180008f2d  jns     short loc_180008F52
0x180008f2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f36  lea     rax, WPP_GLOBAL_Control
0x180008f3d  cmp     rcx, rax
0x180008f40  jz      short loc_180008FA2
0x180008f42  test    [rcx+1Ch], sil
0x180008f46  jz      short loc_180008FA2
0x180008f48  mov     edx, 1Dh
0x180008f4d  jmp     loc_180008D56
0x180008f52  mov     rcx, [rbp+phHash]; hHash
0x180008f56  xor     r9d, r9d; dwFlags
0x180008f59  mov     r8d, r13d; cbOutput
0x180008f5c  mov     rdx, rdi; pbOutput
0x180008f5f  call    cs:__imp_BCryptFinishHash
0x180008f65  mov     ebx, eax
0x180008f67  test    eax, eax
0x180008f69  jns     short loc_180008F8E
0x180008f6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f72  lea     rax, WPP_GLOBAL_Control
0x180008f79  cmp     rcx, rax
0x180008f7c  jz      short loc_180008FA2
0x180008f7e  test    [rcx+1Ch], sil
0x180008f82  jz      short loc_180008FA2
0x180008f84  mov     edx, 1Eh
0x180008f89  jmp     loc_180008D56
0x180008f8e  mov     rcx, [rbp+phHash]; hHash
0x180008f92  call    cs:__imp_BCryptDestroyHash
0x180008f98  mov     rax, [rdi]
0x180008f9b  mov     [r14], rax
0x180008f9e  mov     [rbp+phHash], r12
0x180008fa2  mov     rcx, [rbp+phHash]; hHash
0x180008fa6  test    rcx, rcx
0x180008fa9  jz      short loc_180008FB1
0x180008fab  call    cs:__imp_BCryptDestroyHash
0x180008fb1  mov     eax, ebx
0x180008fb3  mov     rcx, [rbp+var_18]
0x180008fb7  xor     rcx, rsp; StackCookie
0x180008fba  call    __security_check_cookie
0x180008fbf  add     rsp, 78h
0x180008fc3  pop     r15
0x180008fc5  pop     r14
0x180008fc7  pop     r13
0x180008fc9  pop     r12
0x180008fcb  pop     rdi
0x180008fcc  pop     rsi
0x180008fcd  pop     rbx
0x180008fce  pop     rbp
0x180008fcf  retn
```
