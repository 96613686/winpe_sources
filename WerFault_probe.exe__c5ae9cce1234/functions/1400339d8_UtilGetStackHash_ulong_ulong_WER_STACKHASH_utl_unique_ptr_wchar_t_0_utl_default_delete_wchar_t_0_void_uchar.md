# UtilGetStackHash(ulong,ulong,WER_STACKHASH *,utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *,void * *,uchar *)

- ea: `0x1400339d8`
- end: `0x140033c2c`
- name: `?UtilGetStackHash@@YAJKKPEAUWER_STACKHASH@@PEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@PEAPEAXPEAE@Z`
- size: `596`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x140029a14`

## callees

- `0x140002470`
- `0x140002728`
- `0x14001444c`
- `0x140014474`
- `0x1400334c0`
- `0x1400339d8`
- `0x140033c34`
- `0x140034150`

## import_xrefs

- `bcrypt!BCryptFinishHash` at `0x140033bd3`
- `bcrypt!BCryptFinishHash` at `0x140033bd3`
- `bcrypt!BCryptDestroyHash` at `0x140033be6`
- `bcrypt!BCryptDestroyHash` at `0x140033be6`
- `bcrypt!BCryptCreateHash` at `0x140033b93`
- `bcrypt!BCryptCreateHash` at `0x140033b93`
- `bcrypt!BCryptHashData` at `0x140033bb5`
- `bcrypt!BCryptHashData` at `0x140033bb5`

## pseudocode

```c
__int64 __fastcall UtilGetStackHash(DWORD a1, DWORD a2, __int64 a3)
{
  int StackTrace; // eax
  const struct std::nothrow_t *v6; // rdx
  CUserModeHangReport *v7; // rcx
  unsigned int v8; // esi
  unsigned int v9; // ebx
  __int64 v10; // rbx
  int StackHash; // eax
  __int64 v12; // rcx
  __int64 v13; // xmm1_8
  int pbSecret; // [rsp+20h] [rbp-49h]
  ULONG cbSecret; // [rsp+28h] [rbp-41h]
  unsigned int v17; // [rsp+40h] [rbp-29h] BYREF
  struct _WER_STACK_FRAME *v18; // [rsp+48h] [rbp-21h] BYREF
  UCHAR pbInput[8]; // [rsp+50h] [rbp-19h] BYREF
  __int128 v20; // [rsp+58h] [rbp-11h] BYREF
  __int64 v21; // [rsp+68h] [rbp-1h]
  BCRYPT_HASH_HANDLE phHash[2]; // [rsp+70h] [rbp+7h] BYREF
  __int64 v23; // [rsp+80h] [rbp+17h]

  v18 = 0;
  v23 = 0;
  v17 = 0;
  *(_QWORD *)pbInput = 0;
  *(_OWORD *)phHash = 0;
  StackTrace = UtilGetStackTrace(a1, a2, (void **)&v18, &v17, pbSecret, cbSecret, pbInput);
  if ( StackTrace >= 0 )
  {
    v8 = v17;
    v7 = WPP_GLOBAL_Control;
  }
  else
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        &WPP_c528859db29c31ff546031011001ad2a_Traceguids,
        (unsigned int)StackTrace);
      v7 = WPP_GLOBAL_Control;
    }
    v8 = 0;
  }
  if ( a3 )
  {
    v10 = 0;
    do
    {
      v20 = 0;
      LODWORD(v20) = v10;
      v21 = 0;
      StackHash = WerpGenerateStackHash(v18, v8, (struct WER_STACKHASH *)&v20);
      if ( StackHash < 0 )
      {
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            &WPP_c528859db29c31ff546031011001ad2a_Traceguids,
            (unsigned int)StackHash);
        }
      }
      else
      {
        v12 = 3 * v10;
        v13 = v21;
        *(_OWORD *)(a3 + 8 * v12) = v20;
        *(_QWORD *)(a3 + 8 * v12 + 16) = v13;
      }
      v10 = (unsigned int)(v10 + 1);
    }
    while ( (unsigned int)v10 < 2 );
    LogStackTrace(a2, v18, v8, a3);
    if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x21, phHash, 0, 0, 0, 0, 0) < 0 )
      __fastfail(7u);
    if ( BCryptHashData(phHash[0], pbInput, 8u, 0) < 0 )
      __fastfail(7u);
    if ( BCryptFinishHash(phHash[0], (PUCHAR)&phHash[1], 0x10u, 0) < 0 )
      __fastfail(7u);
    BCryptDestroyHash(phHash[0]);
    v9 = 0;
    phHash[0] = 0;
  }
  else
  {
    if ( v7 != (CUserModeHangReport *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)v7 + 2), 12, &WPP_c528859db29c31ff546031011001ad2a_Traceguids);
      v7 = WPP_GLOBAL_Control;
    }
    v9 = -2147024809;
    if ( v7 != (CUserModeHangReport *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)v7 + 2), 11, &WPP_c528859db29c31ff546031011001ad2a_Traceguids, 2147942487LL);
  }
  if ( v18 )
    operator delete(v18, v6);
  return v9;
}

```

## disassembly

```asm
0x1400339d8  mov     [rsp-8+arg_18], rbx
0x1400339dd  push    rbp
0x1400339de  push    rsi
0x1400339df  push    r13
0x1400339e1  push    r14
0x1400339e3  push    r15
0x1400339e5  lea     rbp, [rsp-27h]
0x1400339ea  sub     rsp, 90h
0x1400339f1  mov     rax, cs:__security_cookie
0x1400339f8  xor     rax, rsp
0x1400339fb  mov     [rbp+47h+var_28], rax
0x1400339ff  xor     eax, eax
0x140033a01  mov     [rbp+47h+var_68], 0
0x140033a09  mov     [rbp+47h+var_30], rax
0x140033a0d  lea     r9, [rbp+47h+var_70]
0x140033a11  lea     rax, [rbp+47h+pbInput]
0x140033a15  mov     [rbp+47h+var_70], 0
0x140033a1c  mov     r14, r8
0x140033a1f  mov     qword ptr [rsp+0B0h+dwFlags], rax; __int64
0x140033a24  xorps   xmm0, xmm0
0x140033a27  mov     qword ptr [rbp+47h+pbInput], 0
0x140033a2f  lea     r8, [rbp+47h+var_68]
0x140033a33  mov     r15d, edx
0x140033a36  movups  xmmword ptr [rbp+47h+phHash], xmm0
0x140033a3a  call    ?UtilGetStackTrace@@YAJKKPEAV?$unique_ptr@$$BY0A@U_WER_STACK_FRAME@@U?$default_delete@$$BY0A@U_WER_STACK_FRAME@@@utl@@@utl@@PEAKPEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@2@PEAPEAX3@Z; UtilGetStackTrace(ulong,ulong,utl::unique_ptr<_WER_STACK_FRAME [0],utl::default_delete<_WER_STACK_FRAME [0]>> *,ulong *,utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *,void * *,void * *)
0x140033a3f  lea     r13, WPP_GLOBAL_Control
0x140033a46  test    eax, eax
0x140033a48  jns     short loc_140033A7F
0x140033a4a  mov     rcx, cs:WPP_GLOBAL_Control
0x140033a51  cmp     rcx, r13
0x140033a54  jz      short loc_140033A7B
0x140033a56  test    byte ptr [rcx+1Ch], 2
0x140033a5a  jz      short loc_140033A7B
0x140033a5c  mov     rcx, [rcx+10h]
0x140033a60  lea     r8, WPP_c528859db29c31ff546031011001ad2a_Traceguids
0x140033a67  mov     edx, 0Ah
0x140033a6c  mov     r9d, eax
0x140033a6f  call    WPP_SF_d
0x140033a74  mov     rcx, cs:WPP_GLOBAL_Control
0x140033a7b  xor     esi, esi
0x140033a7d  jmp     short loc_140033A89
0x140033a7f  mov     esi, [rbp+47h+var_70]
0x140033a82  mov     rcx, cs:WPP_GLOBAL_Control
0x140033a89  test    r14, r14
0x140033a8c  jnz     short loc_140033AE9
0x140033a8e  cmp     rcx, r13
0x140033a91  jz      short loc_140033AB4
0x140033a93  test    byte ptr [rcx+1Ch], 1
0x140033a97  jz      short loc_140033AB4
0x140033a99  mov     rcx, [rcx+10h]
0x140033a9d  lea     edx, [r14+0Ch]
0x140033aa1  lea     r8, WPP_c528859db29c31ff546031011001ad2a_Traceguids
0x140033aa8  call    WPP_SF_
0x140033aad  mov     rcx, cs:WPP_GLOBAL_Control
0x140033ab4  mov     ebx, 80070057h
0x140033ab9  cmp     rcx, r13
0x140033abc  jz      loc_140033BF6
0x140033ac2  test    byte ptr [rcx+1Ch], 1
0x140033ac6  jz      loc_140033BF6
0x140033acc  mov     rcx, [rcx+10h]
0x140033ad0  lea     r8, WPP_c528859db29c31ff546031011001ad2a_Traceguids
0x140033ad7  mov     edx, 0Bh
0x140033adc  mov     r9d, ebx
0x140033adf  call    WPP_SF_d
0x140033ae4  jmp     loc_140033BF6
0x140033ae9  xor     ebx, ebx
0x140033aeb  mov     rcx, [rbp+47h+var_68]; struct _WER_STACK_FRAME *
0x140033aef  lea     r8, [rbp+47h+var_58]; struct WER_STACKHASH *
0x140033af3  xorps   xmm0, xmm0
0x140033af6  xor     eax, eax
0x140033af8  movups  [rbp+47h+var_58], xmm0
0x140033afc  mov     edx, esi; unsigned int
0x140033afe  mov     dword ptr [rbp+47h+var_58], ebx
0x140033b01  mov     [rbp+47h+var_48], rax
0x140033b05  call    ?WerpGenerateStackHash@@YAJPEAU_WER_STACK_FRAME@@KPEAUWER_STACKHASH@@@Z; WerpGenerateStackHash(_WER_STACK_FRAME *,ulong,WER_STACKHASH *)
0x140033b0a  test    eax, eax
0x140033b0c  js      short loc_140033B29
0x140033b0e  movups  xmm0, [rbp+47h+var_58]
0x140033b12  lea     rcx, [rbx+rbx*2]
0x140033b16  movsd   xmm1, [rbp+47h+var_48]
0x140033b1b  movups  xmmword ptr [r14+rcx*8], xmm0
0x140033b20  movsd   qword ptr [r14+rcx*8+10h], xmm1
0x140033b27  jmp     short loc_140033B53
0x140033b29  mov     rcx, cs:WPP_GLOBAL_Control
0x140033b30  cmp     rcx, r13
0x140033b33  jz      short loc_140033B53
0x140033b35  test    byte ptr [rcx+1Ch], 2
0x140033b39  jz      short loc_140033B53
0x140033b3b  mov     rcx, [rcx+10h]
0x140033b3f  lea     r8, WPP_c528859db29c31ff546031011001ad2a_Traceguids
0x140033b46  mov     edx, 0Dh
0x140033b4b  mov     r9d, eax
0x140033b4e  call    WPP_SF_d
0x140033b53  inc     ebx
0x140033b55  cmp     ebx, 2
0x140033b58  jb      short loc_140033AEB
0x140033b5a  mov     rdx, [rbp+47h+var_68]
0x140033b5e  mov     r9, r14
0x140033b61  mov     r8d, esi
0x140033b64  mov     ecx, r15d
0x140033b67  call    LogStackTrace
0x140033b6c  xor     r9d, r9d; cbHashObject
0x140033b6f  mov     [rsp+0B0h+dwFlags], 0; dwFlags
0x140033b77  mov     [rsp+0B0h+cbSecret], 0; cbSecret
0x140033b7f  lea     rdx, [rbp+47h+phHash]; phHash
0x140033b83  xor     r8d, r8d; pbHashObject
0x140033b86  mov     [rsp+0B0h+pbSecret], 0; pbSecret
0x140033b8f  lea     ecx, [r9+21h]; hAlgorithm
0x140033b93  call    cs:__imp_BCryptCreateHash
0x140033b99  mov     ebx, 7
0x140033b9e  test    eax, eax
0x140033ba0  jns     short loc_140033BA6
0x140033ba2  mov     ecx, ebx
0x140033ba4  int     29h; Win8: RtlFailFast(ecx)
0x140033ba6  mov     rcx, [rbp+47h+phHash]; hHash
0x140033baa  lea     rdx, [rbp+47h+pbInput]; pbInput
0x140033bae  xor     r9d, r9d; dwFlags
0x140033bb1  lea     r8d, [r9+8]; cbInput
0x140033bb5  call    cs:__imp_BCryptHashData
0x140033bbb  test    eax, eax
0x140033bbd  jns     short loc_140033BC4
0x140033bbf  mov     rcx, rbx
0x140033bc2  int     29h; Win8: RtlFailFast(ecx)
0x140033bc4  mov     rcx, [rbp+47h+phHash]; hHash
0x140033bc8  lea     rdx, [rbp+47h+phHash+8]; pbOutput
0x140033bcc  xor     r9d, r9d; dwFlags
0x140033bcf  lea     r8d, [r9+10h]; cbOutput
0x140033bd3  call    cs:__imp_BCryptFinishHash
0x140033bd9  test    eax, eax
0x140033bdb  jns     short loc_140033BE2
0x140033bdd  mov     rcx, rbx
0x140033be0  int     29h; Win8: RtlFailFast(ecx)
0x140033be2  mov     rcx, [rbp+47h+phHash]; hHash
0x140033be6  call    cs:__imp_BCryptDestroyHash
0x140033bec  xor     ebx, ebx
0x140033bee  mov     [rbp+47h+phHash], 0
0x140033bf6  cmp     [rbp+47h+var_68], 0
0x140033bfb  jz      short loc_140033C06
0x140033bfd  mov     rcx, [rbp+47h+var_68]; void *
0x140033c01  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140033c06  mov     eax, ebx
0x140033c08  mov     rcx, [rbp+47h+var_28]
0x140033c0c  xor     rcx, rsp; StackCookie
0x140033c0f  call    __security_check_cookie
0x140033c14  mov     rbx, [rsp+0B0h+arg_18]
0x140033c1c  add     rsp, 90h
0x140033c23  pop     r15
0x140033c25  pop     r14
0x140033c27  pop     r13
0x140033c29  pop     rsi
0x140033c2a  pop     rbp
0x140033c2b  retn
```
