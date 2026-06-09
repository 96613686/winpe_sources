# UtilGetStackHash(ulong,ulong,WER_STACKHASH *,utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *,void * *,uchar *)

- ea: `0x140035de0`
- end: `0x14003604d`
- name: `?UtilGetStackHash@@YAJKKPEAUWER_STACKHASH@@PEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@PEAPEAXPEAE@Z`
- size: `621`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x14002b5d8`

## callees

- `0x140002490`
- `0x140002748`
- `0x140014ee4`
- `0x140014f14`
- `0x1400358b0`
- `0x140035de0`
- `0x140036054`
- `0x1400365b4`

## import_xrefs

- `bcrypt!BCryptFinishHash` at `0x140035fe7`
- `bcrypt!BCryptFinishHash` at `0x140035fe7`
- `bcrypt!BCryptDestroyHash` at `0x140036000`
- `bcrypt!BCryptDestroyHash` at `0x140036000`
- `bcrypt!BCryptCreateHash` at `0x140035f9b`
- `bcrypt!BCryptCreateHash` at `0x140035f9b`
- `bcrypt!BCryptHashData` at `0x140035fc3`
- `bcrypt!BCryptHashData` at `0x140035fc3`

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
        WPP_c528859db29c31ff546031011001ad2a_Traceguids,
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
            WPP_c528859db29c31ff546031011001ad2a_Traceguids,
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
      WPP_SF_(*((_QWORD *)v7 + 2), 12, WPP_c528859db29c31ff546031011001ad2a_Traceguids);
      v7 = WPP_GLOBAL_Control;
    }
    v9 = -2147024809;
    if ( v7 != (CUserModeHangReport *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)v7 + 2), 11, WPP_c528859db29c31ff546031011001ad2a_Traceguids, 2147942487LL);
  }
  if ( v18 )
    operator delete(v18, v6);
  return v9;
}

```

## disassembly

```asm
0x140035de0  mov     [rsp-8+arg_18], rbx
0x140035de5  push    rbp
0x140035de6  push    rsi
0x140035de7  push    r13
0x140035de9  push    r14
0x140035deb  push    r15
0x140035ded  lea     rbp, [rsp-27h]
0x140035df2  sub     rsp, 90h
0x140035df9  mov     rax, cs:__security_cookie
0x140035e00  xor     rax, rsp
0x140035e03  mov     [rbp+47h+var_28], rax
0x140035e07  xor     eax, eax
0x140035e09  mov     [rbp+47h+var_68], 0
0x140035e11  mov     [rbp+47h+var_30], rax
0x140035e15  lea     r9, [rbp+47h+var_70]
0x140035e19  lea     rax, [rbp+47h+pbInput]
0x140035e1d  mov     [rbp+47h+var_70], 0
0x140035e24  mov     r14, r8
0x140035e27  mov     qword ptr [rsp+0B0h+dwFlags], rax; __int64
0x140035e2c  xorps   xmm0, xmm0
0x140035e2f  mov     qword ptr [rbp+47h+pbInput], 0
0x140035e37  lea     r8, [rbp+47h+var_68]
0x140035e3b  mov     r15d, edx
0x140035e3e  movups  xmmword ptr [rbp+47h+phHash], xmm0
0x140035e42  call    ?UtilGetStackTrace@@YAJKKPEAV?$unique_ptr@$$BY0A@U_WER_STACK_FRAME@@U?$default_delete@$$BY0A@U_WER_STACK_FRAME@@@utl@@@utl@@PEAKPEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@2@PEAPEAX3@Z; UtilGetStackTrace(ulong,ulong,utl::unique_ptr<_WER_STACK_FRAME [0],utl::default_delete<_WER_STACK_FRAME [0]>> *,ulong *,utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *,void * *,void * *)
0x140035e47  lea     r13, WPP_GLOBAL_Control
0x140035e4e  test    eax, eax
0x140035e50  jns     short loc_140035E87
0x140035e52  mov     rcx, cs:WPP_GLOBAL_Control
0x140035e59  cmp     rcx, r13
0x140035e5c  jz      short loc_140035E83
0x140035e5e  test    byte ptr [rcx+1Ch], 2
0x140035e62  jz      short loc_140035E83
0x140035e64  mov     rcx, [rcx+10h]
0x140035e68  lea     r8, WPP_c528859db29c31ff546031011001ad2a_Traceguids
0x140035e6f  mov     edx, 0Ah
0x140035e74  mov     r9d, eax
0x140035e77  call    WPP_SF_d
0x140035e7c  mov     rcx, cs:WPP_GLOBAL_Control
0x140035e83  xor     esi, esi
0x140035e85  jmp     short loc_140035E91
0x140035e87  mov     esi, [rbp+47h+var_70]
0x140035e8a  mov     rcx, cs:WPP_GLOBAL_Control
0x140035e91  test    r14, r14
0x140035e94  jnz     short loc_140035EF1
0x140035e96  cmp     rcx, r13
0x140035e99  jz      short loc_140035EBC
0x140035e9b  test    byte ptr [rcx+1Ch], 1
0x140035e9f  jz      short loc_140035EBC
0x140035ea1  mov     rcx, [rcx+10h]
0x140035ea5  lea     edx, [r14+0Ch]
0x140035ea9  lea     r8, WPP_c528859db29c31ff546031011001ad2a_Traceguids
0x140035eb0  call    WPP_SF_
0x140035eb5  mov     rcx, cs:WPP_GLOBAL_Control
0x140035ebc  mov     ebx, 80070057h
0x140035ec1  cmp     rcx, r13
0x140035ec4  jz      loc_140036016
0x140035eca  test    byte ptr [rcx+1Ch], 1
0x140035ece  jz      loc_140036016
0x140035ed4  mov     rcx, [rcx+10h]
0x140035ed8  lea     r8, WPP_c528859db29c31ff546031011001ad2a_Traceguids
0x140035edf  mov     edx, 0Bh
0x140035ee4  mov     r9d, ebx
0x140035ee7  call    WPP_SF_d
0x140035eec  jmp     loc_140036016
0x140035ef1  xor     ebx, ebx
0x140035ef3  mov     rcx, [rbp+47h+var_68]; struct _WER_STACK_FRAME *
0x140035ef7  lea     r8, [rbp+47h+var_58]; struct WER_STACKHASH *
0x140035efb  xorps   xmm0, xmm0
0x140035efe  xor     eax, eax
0x140035f00  movups  [rbp+47h+var_58], xmm0
0x140035f04  mov     edx, esi; unsigned int
0x140035f06  mov     dword ptr [rbp+47h+var_58], ebx
0x140035f09  mov     [rbp+47h+var_48], rax
0x140035f0d  call    ?WerpGenerateStackHash@@YAJPEAU_WER_STACK_FRAME@@KPEAUWER_STACKHASH@@@Z; WerpGenerateStackHash(_WER_STACK_FRAME *,ulong,WER_STACKHASH *)
0x140035f12  test    eax, eax
0x140035f14  js      short loc_140035F31
0x140035f16  movups  xmm0, [rbp+47h+var_58]
0x140035f1a  lea     rcx, [rbx+rbx*2]
0x140035f1e  movsd   xmm1, [rbp+47h+var_48]
0x140035f23  movups  xmmword ptr [r14+rcx*8], xmm0
0x140035f28  movsd   qword ptr [r14+rcx*8+10h], xmm1
0x140035f2f  jmp     short loc_140035F5B
0x140035f31  mov     rcx, cs:WPP_GLOBAL_Control
0x140035f38  cmp     rcx, r13
0x140035f3b  jz      short loc_140035F5B
0x140035f3d  test    byte ptr [rcx+1Ch], 2
0x140035f41  jz      short loc_140035F5B
0x140035f43  mov     rcx, [rcx+10h]
0x140035f47  lea     r8, WPP_c528859db29c31ff546031011001ad2a_Traceguids
0x140035f4e  mov     edx, 0Dh
0x140035f53  mov     r9d, eax
0x140035f56  call    WPP_SF_d
0x140035f5b  inc     ebx
0x140035f5d  cmp     ebx, 2
0x140035f60  jb      short loc_140035EF3
0x140035f62  mov     rdx, [rbp+47h+var_68]
0x140035f66  mov     r9, r14
0x140035f69  mov     r8d, esi
0x140035f6c  mov     ecx, r15d
0x140035f6f  call    LogStackTrace
0x140035f74  xor     r9d, r9d; cbHashObject
0x140035f77  mov     [rsp+0B0h+dwFlags], 0; dwFlags
0x140035f7f  mov     [rsp+0B0h+cbSecret], 0; cbSecret
0x140035f87  lea     rdx, [rbp+47h+phHash]; phHash
0x140035f8b  xor     r8d, r8d; pbHashObject
0x140035f8e  mov     [rsp+0B0h+pbSecret], 0; pbSecret
0x140035f97  lea     ecx, [r9+21h]; hAlgorithm
0x140035f9b  call    cs:__imp_BCryptCreateHash
0x140035fa2  nop     dword ptr [rax+rax+00h]
0x140035fa7  mov     ebx, 7
0x140035fac  test    eax, eax
0x140035fae  jns     short loc_140035FB4
0x140035fb0  mov     ecx, ebx
0x140035fb2  int     29h; Win8: RtlFailFast(ecx)
0x140035fb4  mov     rcx, [rbp+47h+phHash]; hHash
0x140035fb8  lea     rdx, [rbp+47h+pbInput]; pbInput
0x140035fbc  xor     r9d, r9d; dwFlags
0x140035fbf  lea     r8d, [r9+8]; cbInput
0x140035fc3  call    cs:__imp_BCryptHashData
0x140035fca  nop     dword ptr [rax+rax+00h]
0x140035fcf  test    eax, eax
0x140035fd1  jns     short loc_140035FD8
0x140035fd3  mov     rcx, rbx
0x140035fd6  int     29h; Win8: RtlFailFast(ecx)
0x140035fd8  mov     rcx, [rbp+47h+phHash]; hHash
0x140035fdc  lea     rdx, [rbp+47h+phHash+8]; pbOutput
0x140035fe0  xor     r9d, r9d; dwFlags
0x140035fe3  lea     r8d, [r9+10h]; cbOutput
0x140035fe7  call    cs:__imp_BCryptFinishHash
0x140035fee  nop     dword ptr [rax+rax+00h]
0x140035ff3  test    eax, eax
0x140035ff5  jns     short loc_140035FFC
0x140035ff7  mov     rcx, rbx
0x140035ffa  int     29h; Win8: RtlFailFast(ecx)
0x140035ffc  mov     rcx, [rbp+47h+phHash]; hHash
0x140036000  call    cs:__imp_BCryptDestroyHash
0x140036007  nop     dword ptr [rax+rax+00h]
0x14003600c  xor     ebx, ebx
0x14003600e  mov     [rbp+47h+phHash], 0
0x140036016  cmp     [rbp+47h+var_68], 0
0x14003601b  jz      short loc_140036026
0x14003601d  mov     rcx, [rbp+47h+var_68]; void *
0x140036021  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140036026  mov     eax, ebx
0x140036028  mov     rcx, [rbp+47h+var_28]
0x14003602c  xor     rcx, rsp; StackCookie
0x14003602f  call    __security_check_cookie
0x140036034  mov     rbx, [rsp+0B0h+arg_18]
0x14003603c  add     rsp, 90h
0x140036043  pop     r15
0x140036045  pop     r14
0x140036047  pop     r13
0x140036049  pop     rsi
0x14003604a  pop     rbp
0x14003604b  retn
```
