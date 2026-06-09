# CommonUtil::UtilGetTokenInformationImpl(void * *,void *,_TOKEN_INFORMATION_CLASS)

- ea: `0x1400107ac`
- end: `0x1400108f1`
- name: `?UtilGetTokenInformationImpl@CommonUtil@@YAJPEAPEAXPEAXW4_TOKEN_INFORMATION_CLASS@@@Z`
- size: `325`
- prototype: `int(CommonUtil *__hidden this, void **, void *, enum _TOKEN_INFORMATION_CLASS)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140088000`

## callees

- `0x1400107ac`
- `0x140015574`
- `0x140017738`
- `0x14003a5c0`
- `0x14003aa90`
- `0x14007d210`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x140010832`
- `ADVAPI32!GetTokenInformation` at `0x140010832`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilGetTokenInformationImpl(
        CommonUtil *this,
        void **a2,
        unsigned __int64 a3,
        enum _TOKEN_INFORMATION_CLASS a4)
{
  void *v4; // rbx
  TOKEN_INFORMATION_CLASS v5; // r15d
  DWORD i; // esi
  int v9; // ebx
  int LastFailure; // eax
  unsigned int v11; // edi
  DWORD ReturnLength; // [rsp+30h] [rbp-48h] BYREF
  LPVOID TokenInformation; // [rsp+38h] [rbp-40h] BYREF

  v4 = 0;
  v5 = (int)a3;
  TokenInformation = 0;
  for ( i = 64; ; i = ReturnLength )
  {
    if ( v4 )
    {
      operator delete(v4);
      TokenInformation = 0;
    }
    v9 = CommonUtil::MpNewAlloc((CommonUtil *)&TokenInformation, (void **)i, a3);
    if ( v9 < 0 )
      break;
    v4 = TokenInformation;
    ReturnLength = 0;
    if ( GetTokenInformation(a2, v5, TokenInformation, i, &ReturnLength) )
    {
      *(_QWORD *)this = v4;
      return 0;
    }
    LastFailure = HrGetLastFailure();
    v11 = LastFailure;
    if ( LastFailure < 0 && LastFailure != -2147024774 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          16,
          WPP_75abd5b169db356f85f54582dbfea5fb_Traceguids,
          (unsigned int)LastFailure);
      if ( v4 )
        operator delete(v4);
      return v11;
    }
    if ( i >= ReturnLength )
    {
      if ( v4 )
        operator delete(v4);
      return 2147549183LL;
    }
  }
  if ( TokenInformation )
    operator delete(TokenInformation);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400107ac  mov     [rsp+arg_18], rbx
0x1400107b1  push    rbp
0x1400107b2  push    rsi
0x1400107b3  push    rdi
0x1400107b4  push    r14
0x1400107b6  push    r15
0x1400107b8  sub     rsp, 50h
0x1400107bc  mov     rax, cs:__security_cookie
0x1400107c3  xor     rax, rsp
0x1400107c6  mov     [rsp+78h+var_38], rax
0x1400107cb  xor     ebx, ebx
0x1400107cd  mov     r15d, r8d
0x1400107d0  mov     rbp, rdx
0x1400107d3  mov     [rsp+78h+TokenInformation], rbx
0x1400107d8  mov     r14, rcx
0x1400107db  lea     esi, [rbx+40h]
0x1400107de  test    rbx, rbx
0x1400107e1  jz      short loc_1400107F4
0x1400107e3  mov     rcx, rbx; Block
0x1400107e6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400107eb  mov     [rsp+78h+TokenInformation], 0
0x1400107f4  mov     edx, esi; void **
0x1400107f6  lea     rcx, [rsp+78h+TokenInformation]; this
0x1400107fb  call    ?MpNewAlloc@CommonUtil@@YAJPEAPEAX_K@Z; CommonUtil::MpNewAlloc(void * *,unsigned __int64)
0x140010800  mov     ecx, eax
0x140010802  mov     ebx, eax
0x140010804  shr     ecx, 1Fh
0x140010807  test    cl, cl
0x140010809  jnz     loc_1400108BF
0x14001080f  mov     rbx, [rsp+78h+TokenInformation]
0x140010814  lea     rax, [rsp+78h+var_48]
0x140010819  mov     r8, rbx; TokenInformation
0x14001081c  mov     [rsp+78h+var_48], 0
0x140010824  mov     r9d, esi; TokenInformationLength
0x140010827  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x14001082c  mov     edx, r15d; TokenInformationClass
0x14001082f  mov     rcx, rbp; TokenHandle
0x140010832  call    cs:__imp_GetTokenInformation
0x140010838  test    eax, eax
0x14001083a  jnz     short loc_1400108B8
0x14001083c  call    HrGetLastFailure
0x140010841  mov     ecx, eax
0x140010843  mov     edi, eax
0x140010845  shr     ecx, 1Fh
0x140010848  test    cl, cl
0x14001084a  jz      short loc_140010853
0x14001084c  cmp     eax, 8007007Ah
0x140010851  jnz     short loc_140010862
0x140010853  cmp     esi, [rsp+78h+var_48]
0x140010857  jnb     short loc_1400108A4
0x140010859  mov     esi, [rsp+78h+var_48]
0x14001085d  jmp     loc_1400107DE
0x140010862  mov     rcx, cs:WPP_GLOBAL_Control
0x140010869  lea     rax, WPP_GLOBAL_Control
0x140010870  cmp     rcx, rax
0x140010873  jz      short loc_140010893
0x140010875  test    byte ptr [rcx+1Ch], 1
0x140010879  jz      short loc_140010893
0x14001087b  mov     rcx, [rcx+10h]
0x14001087f  lea     r8, WPP_75abd5b169db356f85f54582dbfea5fb_Traceguids
0x140010886  mov     edx, 10h
0x14001088b  mov     r9d, edi
0x14001088e  call    WPP_SF_d
0x140010893  test    rbx, rbx
0x140010896  jz      short loc_1400108A0
0x140010898  mov     rcx, rbx; Block
0x14001089b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400108a0  mov     eax, edi
0x1400108a2  jmp     short loc_1400108D0
0x1400108a4  test    rbx, rbx
0x1400108a7  jz      short loc_1400108B1
0x1400108a9  mov     rcx, rbx; Block
0x1400108ac  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400108b1  mov     eax, 8000FFFFh
0x1400108b6  jmp     short loc_1400108D0
0x1400108b8  mov     [r14], rbx
0x1400108bb  xor     eax, eax
0x1400108bd  jmp     short loc_1400108D0
0x1400108bf  mov     rcx, [rsp+78h+TokenInformation]; Block
0x1400108c4  test    rcx, rcx
0x1400108c7  jz      short loc_1400108CE
0x1400108c9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400108ce  mov     eax, ebx
0x1400108d0  mov     rcx, [rsp+78h+var_38]
0x1400108d5  xor     rcx, rsp; StackCookie
0x1400108d8  call    __security_check_cookie
0x1400108dd  mov     rbx, [rsp+78h+arg_18]
0x1400108e5  add     rsp, 50h
0x1400108e9  pop     r15
0x1400108eb  pop     r14
0x1400108ed  pop     rdi
0x1400108ee  pop     rsi
0x1400108ef  pop     rbp
0x1400108f0  retn
```
