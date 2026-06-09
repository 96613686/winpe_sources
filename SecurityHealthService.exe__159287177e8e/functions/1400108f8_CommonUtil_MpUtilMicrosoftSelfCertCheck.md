# CommonUtil::MpUtilMicrosoftSelfCertCheck

- ea: `0x1400108f8`
- end: `0x140010b17`
- name: `CommonUtil::MpUtilMicrosoftSelfCertCheck`
- size: `543`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14001088c`

## callees

- `0x1400015d0`
- `0x14000202c`
- `0x140003640`
- `0x140010458`
- `0x1400108f8`
- `0x140010b20`
- `0x140010bc4`
- `0x140010dcc`
- `0x140010e60`

## pseudocode

```c
__int64 __fastcall CommonUtil::MpUtilMicrosoftSelfCertCheck(__int64 a1, unsigned int a2)
{
  int v4; // ebx
  int v5; // eax
  LONG v6; // eax
  int v7; // r8d
  int v8; // edi
  int v9; // edx
  int v10; // r8d
  _QWORD *v11; // rcx
  int v12; // eax
  __int64 v14; // [rsp+40h] [rbp-89h] BYREF
  int v15; // [rsp+48h] [rbp-81h]
  unsigned int v16; // [rsp+4Ch] [rbp-7Dh]
  int v17; // [rsp+50h] [rbp-79h]
  __int64 v18; // [rsp+54h] [rbp-75h]
  int v19; // [rsp+5Ch] [rbp-6Dh]
  _DWORD v20[2]; // [rsp+60h] [rbp-69h] BYREF
  __int64 v21; // [rsp+68h] [rbp-61h]
  __int64 v22; // [rsp+70h] [rbp-59h]
  __int64 v23; // [rsp+78h] [rbp-51h]
  _DWORD v24[6]; // [rsp+80h] [rbp-49h] BYREF
  __int64 v25; // [rsp+98h] [rbp-31h]
  int v26; // [rsp+A0h] [rbp-29h]
  _DWORD *v27; // [rsp+A8h] [rbp-21h]
  int v28; // [rsp+B0h] [rbp-19h]
  __int64 v29; // [rsp+B8h] [rbp-11h]
  int v30; // [rsp+C8h] [rbp-1h]
  __int64 *v31; // [rsp+D0h] [rbp+7h]
  GUID v32; // [rsp+E0h] [rbp+17h] BYREF

  v32.Data1 = 11191659;
  *(_DWORD *)&v32.Data2 = 298896708;
  v4 = 0;
  *(_DWORD *)v32.Data4 = -1073692020;
  *(_DWORD *)&v32.Data4[4] = -292175281;
  memset_0(v24, 0, 0x58u);
  v20[1] = 0;
  v27 = v20;
  v5 = 0;
  v31 = &v14;
  v23 = 0;
  v16 = 0;
  if ( (a2 & 8) == 0 )
    v5 = 16;
  v18 = 0;
  v30 = v5;
  v19 = 0;
  v24[0] = 88;
  v26 = 1;
  v25 = 2;
  if ( (a2 & 0x10) == 0 )
    v30 = v5 | 0x1000;
  v21 = a1;
  v20[0] = 32;
  v14 = 32;
  v22 = 0;
  v15 = 3;
  while ( 1 )
  {
    v29 = 0;
    v28 = 1;
    v17 = 0;
    v6 = CommonUtil::HrWinVerifyTrust(HWND_MESSAGE|0x2LL, &v32, (__int64)v24);
    v8 = v6;
    if ( v6 < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_16;
      WPP_SF_SDDd(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, v7, a1, SBYTE4(v14), v16, v6);
      goto LABEL_15;
    }
    if ( !v29 )
      return 2147549183LL;
    v8 = CommonUtil::UtilMicrosoftCertChainCheck(v29, a2);
    CommonUtil::UtilCloseWinVerifyTrust(v24);
    if ( v8 >= 0 )
      break;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_16;
    WPP_SF_SDDd(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, v10, a1, SBYTE4(v14), v16, v8);
LABEL_15:
    v11 = WPP_GLOBAL_Control;
LABEL_16:
    v12 = HIDWORD(v14);
    if ( !HIDWORD(v14) )
      v4 = v8;
    ++HIDWORD(v14);
    if ( v12 + 1 > v16 )
    {
      if ( v4 >= 0 )
        v4 = -2147467259;
      if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 )
        WPP_SF_d(v11[2], 21, &WPP_adde249b3c3e3d6a586c05ab82af40e6_Traceguids, (unsigned int)v4);
      return (unsigned int)v4;
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_SDD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, v10, a1, SBYTE4(v14), v16);
  return 0;
}

```

## disassembly

```asm
0x1400108f8  mov     [rsp-8+arg_10], rbx
0x1400108fd  push    rbp
0x1400108fe  push    rsi
0x1400108ff  push    rdi
0x140010900  push    r12
0x140010902  push    r14
0x140010904  lea     rbp, [rsp-37h]
0x140010909  sub     rsp, 100h
0x140010910  mov     rax, cs:__security_cookie
0x140010917  xor     rax, rsp
0x14001091a  mov     [rbp+57h+var_30], rax
0x14001091e  mov     r14d, edx
0x140010921  mov     [rbp+57h+var_40], 0AAC56Bh
0x140010928  mov     rsi, rcx
0x14001092b  mov     [rbp+57h+var_3C], 11D0CD44h
0x140010932  xor     ebx, ebx
0x140010934  mov     [rbp+57h+var_38], 0C000C28Ch
0x14001093b  xor     edx, edx; Val
0x14001093d  mov     [rbp+57h+var_34], 0EE95C24Fh
0x140010944  lea     rcx, [rbp+57h+var_A0]; void *
0x140010948  lea     edi, [rbx+58h]
0x14001094b  mov     r8d, edi; Size
0x14001094e  call    memset_0
0x140010953  lea     rax, [rbp+57h+var_C0]
0x140010957  mov     [rbp+57h+var_BC], ebx
0x14001095a  mov     [rbp+57h+var_78], rax
0x14001095e  lea     rcx, [rsp+120h+var_E0]
0x140010963  xor     eax, eax
0x140010965  mov     [rbp+57h+var_50], rcx
0x140010969  test    r14b, 8
0x14001096d  mov     [rbp+57h+var_A8], rbx
0x140010971  lea     ecx, [rbx+10h]
0x140010974  mov     [rbp+57h+var_D4], ebx
0x140010977  cmovz   eax, ecx
0x14001097a  mov     [rbp+57h+var_CC], rbx
0x14001097e  mov     [rbp+57h+var_58], eax
0x140010981  mov     [rbp+57h+var_C4], ebx
0x140010984  mov     [rbp+57h+var_A0], edi
0x140010987  mov     [rbp+57h+var_80], 1
0x14001098e  mov     [rbp+57h+var_88], 2
0x140010996  test    cl, r14b
0x140010999  jnz     short loc_1400109A2
0x14001099b  bts     eax, 0Ch
0x14001099f  mov     [rbp+57h+var_58], eax
0x1400109a2  mov     eax, 20h ; ' '
0x1400109a7  mov     [rbp+57h+var_B8], rsi
0x1400109ab  mov     [rbp+57h+var_C0], eax
0x1400109ae  lea     r12, WPP_GLOBAL_Control
0x1400109b5  mov     [rsp+120h+var_E0], rax
0x1400109ba  mov     [rbp+57h+var_B0], rbx
0x1400109be  mov     [rsp+120h+var_D8], 3
0x1400109c6  lea     r8, [rbp+57h+var_A0]
0x1400109ca  mov     [rbp+57h+var_68], 0
0x1400109d2  lea     rdx, [rbp+57h+var_40]
0x1400109d6  mov     [rbp+57h+var_70], 1
0x1400109dd  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400109e1  mov     [rbp+57h+var_D0], 0
0x1400109e8  call    CommonUtil__HrWinVerifyTrust
0x1400109ed  mov     edi, eax
0x1400109ef  test    eax, eax
0x1400109f1  js      short loc_140010A38
0x1400109f3  mov     rcx, [rbp+57h+var_68]
0x1400109f7  test    rcx, rcx
0x1400109fa  jz      loc_140010B10
0x140010a00  mov     edx, r14d
0x140010a03  call    CommonUtil__UtilMicrosoftCertChainCheck
0x140010a08  lea     rcx, [rbp+57h+var_A0]
0x140010a0c  mov     edi, eax
0x140010a0e  call    CommonUtil__UtilCloseWinVerifyTrust
0x140010a13  test    edi, edi
0x140010a15  jns     loc_140010ADF
0x140010a1b  mov     rcx, cs:WPP_GLOBAL_Control
0x140010a22  cmp     rcx, r12
0x140010a25  jz      short loc_140010A75
0x140010a27  test    byte ptr [rcx+1Ch], 4
0x140010a2b  jz      short loc_140010A75
0x140010a2d  mov     edx, 13h
0x140010a32  mov     [rsp+120h+var_F0], edi
0x140010a36  jmp     short loc_140010A53
0x140010a38  mov     rcx, cs:WPP_GLOBAL_Control
0x140010a3f  cmp     rcx, r12
0x140010a42  jz      short loc_140010A75
0x140010a44  test    byte ptr [rcx+1Ch], 4
0x140010a48  jz      short loc_140010A75
0x140010a4a  mov     edx, 14h
0x140010a4f  mov     [rsp+120h+var_F0], eax
0x140010a53  mov     eax, [rbp+57h+var_D4]
0x140010a56  mov     r9, rsi
0x140010a59  mov     rcx, [rcx+10h]
0x140010a5d  mov     [rsp+120h+var_F8], eax
0x140010a61  mov     eax, dword ptr [rsp+120h+var_E0+4]
0x140010a65  mov     [rsp+120h+var_100], eax
0x140010a69  call    WPP_SF_SDDd
0x140010a6e  mov     rcx, cs:WPP_GLOBAL_Control
0x140010a75  mov     eax, dword ptr [rsp+120h+var_E0+4]
0x140010a79  test    eax, eax
0x140010a7b  cmovz   ebx, edi
0x140010a7e  inc     eax
0x140010a80  mov     dword ptr [rsp+120h+var_E0+4], eax
0x140010a84  cmp     eax, [rbp+57h+var_D4]
0x140010a87  jbe     loc_1400109C6
0x140010a8d  test    ebx, ebx
0x140010a8f  mov     eax, 80004005h
0x140010a94  cmovns  ebx, eax
0x140010a97  cmp     rcx, r12
0x140010a9a  jz      short loc_140010ABA
0x140010a9c  test    byte ptr [rcx+1Ch], 1
0x140010aa0  jz      short loc_140010ABA
0x140010aa2  mov     rcx, [rcx+10h]
0x140010aa6  lea     r8, WPP_adde249b3c3e3d6a586c05ab82af40e6_Traceguids
0x140010aad  mov     edx, 15h
0x140010ab2  mov     r9d, ebx
0x140010ab5  call    WPP_SF_d
0x140010aba  mov     eax, ebx
0x140010abc  mov     rcx, [rbp+57h+var_30]
0x140010ac0  xor     rcx, rsp; StackCookie
0x140010ac3  call    __security_check_cookie
0x140010ac8  mov     rbx, [rsp+120h+arg_10]
0x140010ad0  add     rsp, 100h
0x140010ad7  pop     r14
0x140010ad9  pop     r12
0x140010adb  pop     rdi
0x140010adc  pop     rsi
0x140010add  pop     rbp
0x140010ade  retn
0x140010adf  mov     rcx, cs:WPP_GLOBAL_Control
0x140010ae6  cmp     rcx, r12
0x140010ae9  jz      short loc_140010B0C
0x140010aeb  test    byte ptr [rcx+1Ch], 10h
0x140010aef  jz      short loc_140010B0C
0x140010af1  mov     eax, [rbp+57h+var_D4]
0x140010af4  mov     r9, rsi
0x140010af7  mov     rcx, [rcx+10h]
0x140010afb  mov     [rsp+120h+var_F8], eax
0x140010aff  mov     eax, dword ptr [rsp+120h+var_E0+4]
0x140010b03  mov     [rsp+120h+var_100], eax
0x140010b07  call    WPP_SF_SDD
0x140010b0c  xor     eax, eax
0x140010b0e  jmp     short loc_140010ABC
0x140010b10  mov     eax, 8000FFFFh
0x140010b15  jmp     short loc_140010ABC
```
