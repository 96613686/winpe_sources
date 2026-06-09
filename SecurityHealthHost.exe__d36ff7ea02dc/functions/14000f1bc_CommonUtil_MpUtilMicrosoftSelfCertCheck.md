# CommonUtil::MpUtilMicrosoftSelfCertCheck

- ea: `0x14000f1bc`
- end: `0x14000f3db`
- name: `CommonUtil::MpUtilMicrosoftSelfCertCheck`
- size: `543`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140005fdc`

## callees

- `0x1400015f0`
- `0x1400022ec`
- `0x140003040`
- `0x14000ed88`
- `0x14000f1bc`
- `0x14000f3e4`
- `0x14000f488`
- `0x14000f690`
- `0x14000f724`

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
0x14000f1bc  mov     [rsp-8+arg_10], rbx
0x14000f1c1  push    rbp
0x14000f1c2  push    rsi
0x14000f1c3  push    rdi
0x14000f1c4  push    r12
0x14000f1c6  push    r14
0x14000f1c8  lea     rbp, [rsp-37h]
0x14000f1cd  sub     rsp, 100h
0x14000f1d4  mov     rax, cs:__security_cookie
0x14000f1db  xor     rax, rsp
0x14000f1de  mov     [rbp+57h+var_30], rax
0x14000f1e2  mov     r14d, edx
0x14000f1e5  mov     [rbp+57h+var_40], 0AAC56Bh
0x14000f1ec  mov     rsi, rcx
0x14000f1ef  mov     [rbp+57h+var_3C], 11D0CD44h
0x14000f1f6  xor     ebx, ebx
0x14000f1f8  mov     [rbp+57h+var_38], 0C000C28Ch
0x14000f1ff  xor     edx, edx; Val
0x14000f201  mov     [rbp+57h+var_34], 0EE95C24Fh
0x14000f208  lea     rcx, [rbp+57h+var_A0]; void *
0x14000f20c  lea     edi, [rbx+58h]
0x14000f20f  mov     r8d, edi; Size
0x14000f212  call    memset_0
0x14000f217  lea     rax, [rbp+57h+var_C0]
0x14000f21b  mov     [rbp+57h+var_BC], ebx
0x14000f21e  mov     [rbp+57h+var_78], rax
0x14000f222  lea     rcx, [rsp+120h+var_E0]
0x14000f227  xor     eax, eax
0x14000f229  mov     [rbp+57h+var_50], rcx
0x14000f22d  test    r14b, 8
0x14000f231  mov     [rbp+57h+var_A8], rbx
0x14000f235  lea     ecx, [rbx+10h]
0x14000f238  mov     [rbp+57h+var_D4], ebx
0x14000f23b  cmovz   eax, ecx
0x14000f23e  mov     [rbp+57h+var_CC], rbx
0x14000f242  mov     [rbp+57h+var_58], eax
0x14000f245  mov     [rbp+57h+var_C4], ebx
0x14000f248  mov     [rbp+57h+var_A0], edi
0x14000f24b  mov     [rbp+57h+var_80], 1
0x14000f252  mov     [rbp+57h+var_88], 2
0x14000f25a  test    cl, r14b
0x14000f25d  jnz     short loc_14000F266
0x14000f25f  bts     eax, 0Ch
0x14000f263  mov     [rbp+57h+var_58], eax
0x14000f266  mov     eax, 20h ; ' '
0x14000f26b  mov     [rbp+57h+var_B8], rsi
0x14000f26f  mov     [rbp+57h+var_C0], eax
0x14000f272  lea     r12, WPP_GLOBAL_Control
0x14000f279  mov     [rsp+120h+var_E0], rax
0x14000f27e  mov     [rbp+57h+var_B0], rbx
0x14000f282  mov     [rsp+120h+var_D8], 3
0x14000f28a  lea     r8, [rbp+57h+var_A0]
0x14000f28e  mov     [rbp+57h+var_68], 0
0x14000f296  lea     rdx, [rbp+57h+var_40]
0x14000f29a  mov     [rbp+57h+var_70], 1
0x14000f2a1  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000f2a5  mov     [rbp+57h+var_D0], 0
0x14000f2ac  call    CommonUtil__HrWinVerifyTrust
0x14000f2b1  mov     edi, eax
0x14000f2b3  test    eax, eax
0x14000f2b5  js      short loc_14000F2FC
0x14000f2b7  mov     rcx, [rbp+57h+var_68]
0x14000f2bb  test    rcx, rcx
0x14000f2be  jz      loc_14000F3D4
0x14000f2c4  mov     edx, r14d
0x14000f2c7  call    CommonUtil__UtilMicrosoftCertChainCheck
0x14000f2cc  lea     rcx, [rbp+57h+var_A0]
0x14000f2d0  mov     edi, eax
0x14000f2d2  call    CommonUtil__UtilCloseWinVerifyTrust
0x14000f2d7  test    edi, edi
0x14000f2d9  jns     loc_14000F3A3
0x14000f2df  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f2e6  cmp     rcx, r12
0x14000f2e9  jz      short loc_14000F339
0x14000f2eb  test    byte ptr [rcx+1Ch], 4
0x14000f2ef  jz      short loc_14000F339
0x14000f2f1  mov     edx, 13h
0x14000f2f6  mov     [rsp+120h+var_F0], edi
0x14000f2fa  jmp     short loc_14000F317
0x14000f2fc  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f303  cmp     rcx, r12
0x14000f306  jz      short loc_14000F339
0x14000f308  test    byte ptr [rcx+1Ch], 4
0x14000f30c  jz      short loc_14000F339
0x14000f30e  mov     edx, 14h
0x14000f313  mov     [rsp+120h+var_F0], eax
0x14000f317  mov     eax, [rbp+57h+var_D4]
0x14000f31a  mov     r9, rsi
0x14000f31d  mov     rcx, [rcx+10h]
0x14000f321  mov     [rsp+120h+var_F8], eax
0x14000f325  mov     eax, dword ptr [rsp+120h+var_E0+4]
0x14000f329  mov     [rsp+120h+var_100], eax
0x14000f32d  call    WPP_SF_SDDd
0x14000f332  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f339  mov     eax, dword ptr [rsp+120h+var_E0+4]
0x14000f33d  test    eax, eax
0x14000f33f  cmovz   ebx, edi
0x14000f342  inc     eax
0x14000f344  mov     dword ptr [rsp+120h+var_E0+4], eax
0x14000f348  cmp     eax, [rbp+57h+var_D4]
0x14000f34b  jbe     loc_14000F28A
0x14000f351  test    ebx, ebx
0x14000f353  mov     eax, 80004005h
0x14000f358  cmovns  ebx, eax
0x14000f35b  cmp     rcx, r12
0x14000f35e  jz      short loc_14000F37E
0x14000f360  test    byte ptr [rcx+1Ch], 1
0x14000f364  jz      short loc_14000F37E
0x14000f366  mov     rcx, [rcx+10h]
0x14000f36a  lea     r8, WPP_adde249b3c3e3d6a586c05ab82af40e6_Traceguids
0x14000f371  mov     edx, 15h
0x14000f376  mov     r9d, ebx
0x14000f379  call    WPP_SF_d
0x14000f37e  mov     eax, ebx
0x14000f380  mov     rcx, [rbp+57h+var_30]
0x14000f384  xor     rcx, rsp; StackCookie
0x14000f387  call    __security_check_cookie
0x14000f38c  mov     rbx, [rsp+120h+arg_10]
0x14000f394  add     rsp, 100h
0x14000f39b  pop     r14
0x14000f39d  pop     r12
0x14000f39f  pop     rdi
0x14000f3a0  pop     rsi
0x14000f3a1  pop     rbp
0x14000f3a2  retn
0x14000f3a3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f3aa  cmp     rcx, r12
0x14000f3ad  jz      short loc_14000F3D0
0x14000f3af  test    byte ptr [rcx+1Ch], 10h
0x14000f3b3  jz      short loc_14000F3D0
0x14000f3b5  mov     eax, [rbp+57h+var_D4]
0x14000f3b8  mov     r9, rsi
0x14000f3bb  mov     rcx, [rcx+10h]
0x14000f3bf  mov     [rsp+120h+var_F8], eax
0x14000f3c3  mov     eax, dword ptr [rsp+120h+var_E0+4]
0x14000f3c7  mov     [rsp+120h+var_100], eax
0x14000f3cb  call    WPP_SF_SDD
0x14000f3d0  xor     eax, eax
0x14000f3d2  jmp     short loc_14000F380
0x14000f3d4  mov     eax, 8000FFFFh
0x14000f3d9  jmp     short loc_14000F380
```
