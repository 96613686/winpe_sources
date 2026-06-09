# CommonUtil::UtilGetFileSecurity(CommonUtil::ISecurityAttributes * *,ushort const *,ulong)

- ea: `0x180007fdc`
- end: `0x1800081d9`
- name: `?UtilGetFileSecurity@CommonUtil@@YAJPEAPEAUISecurityAttributes@1@PEBGK@Z`
- size: `509`
- prototype: `int(CommonUtil *__hidden this, struct CommonUtil::ISecurityAttributes **, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180006a2c`

## callees

- `0x18000126c`
- `0x180006898`
- `0x180007dec`
- `0x180007e24`
- `0x180007fdc`
- `0x1800090e4`
- `0x18000a010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000800b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000803f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000819c`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800081bf`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000800b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000803f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000819c`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800081bf`
- `ADVAPI32!GetFileSecurityW` at `0x18000807d`
- `ADVAPI32!GetFileSecurityW` at `0x18000807d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CommonUtil::UtilGetFileSecurity(CommonUtil *this, const WCHAR *a2, const unsigned __int16 *a3)
{
  PSECURITY_DESCRIPTOR v5; // rdi
  DWORD i; // ebx
  int v7; // edi
  __int64 v9; // rcx
  int LastFailure; // esi
  CommonUtil::CSecurityAttributesHolder *v11; // rax
  CommonUtil *v12; // rcx
  CommonUtil::CSecurityAttributesHolder *v13; // rbx
  __int64 v14; // [rsp+0h] [rbp-78h] BYREF
  CommonUtil::CSecurityAttributesHolder *v15; // [rsp+30h] [rbp-48h]
  CommonUtil::CSecurityAttributesHolder *v16; // [rsp+38h] [rbp-40h]
  const exception *v17; // [rsp+40h] [rbp-38h] BYREF
  DWORD nLengthNeeded; // [rsp+90h] [rbp+18h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+98h] [rbp+20h] BYREF

  nLengthNeeded = (unsigned int)a3;
  v5 = 0;
  pSecurityDescriptor = 0;
  for ( i = 160; ; i = nLengthNeeded )
  {
    if ( v5 )
    {
      operator delete(v5);
      pSecurityDescriptor = 0;
    }
    v7 = CommonUtil::MpNewAlloc((CommonUtil *)&pSecurityDescriptor, (void **)i, (unsigned __int64)a3);
    if ( v7 < 0 )
    {
      if ( pSecurityDescriptor )
        operator delete(pSecurityDescriptor);
      return (unsigned int)v7;
    }
    nLengthNeeded = i;
    v5 = pSecurityDescriptor;
    if ( GetFileSecurityW(a2, 4u, pSecurityDescriptor, i, &nLengthNeeded) )
      goto LABEL_31;
    LastFailure = HrGetLastFailure(v9);
    if ( LastFailure != -2147024774 )
      break;
    if ( i >= nLengthNeeded )
    {
      LastFailure = -2147418113;
      goto LABEL_27;
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      (unsigned int)WPP_917185ddc84637471a8d5a2f656085a7_Traceguids,
      (_DWORD)a2,
      LastFailure);
  if ( LastFailure >= 0 )
  {
LABEL_31:
    try
    {
      v15 = 0;
      v11 = (CommonUtil::CSecurityAttributesHolder *)operator new(0x40u);
      v13 = v11;
      v16 = v11;
      if ( v11 )
      {
        CommonUtil::CSecurityAttributesHolder::CSecurityAttributesHolder(v11, v5);
        *(_QWORD *)v13 = &CommonUtil::CSecurityAttributesAlloc<CommonUtil::CUniqueHandle<CommonUtil::CAutoGenericBufferDelete>>::`vftable';
        v5 = 0;
        pSecurityDescriptor = 0;
      }
      if ( v13 )
      {
        if ( *((_DWORD *)v13 + 2) )
          _InterlockedIncrement((volatile signed __int32 *)v13 + 2);
        else
          *((_DWORD *)v13 + 2) = 1;
      }
      v15 = v13;
    }
    catch ( const exception *v17 )
    {
      CommonUtil::HrFromStdException(v12, (const struct exception *)&v14);
    }
    *(_QWORD *)this = v13;
    if ( v5 )
      operator delete(v5);
    return 0;
  }
LABEL_27:
  if ( v5 )
    operator delete(v5);
  return (unsigned int)LastFailure;
}

```

## disassembly

```asm
0x180007fdc  mov     rax, rsp
0x180007fdf  mov     [rax+18h], r8d
0x180007fe3  mov     [rax+8], rcx
0x180007fe7  push    rbx
0x180007fe8  push    rsi
0x180007fe9  push    rdi
0x180007fea  push    r14
0x180007fec  push    r15
0x180007fee  sub     rsp, 50h
0x180007ff2  mov     r15, rdx
0x180007ff5  mov     r14, rcx
0x180007ff8  xor     edi, edi
0x180007ffa  mov     [rax+20h], rdi
0x180007ffe  mov     ebx, 0A0h
0x180008003  test    rdi, rdi
0x180008006  jz      short loc_18000801D
0x180008008  mov     rcx, rdi
0x18000800b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008011  mov     [rsp+78h+pSecurityDescriptor], 0
0x18000801d  mov     edx, ebx; void **
0x18000801f  lea     rcx, [rsp+78h+pSecurityDescriptor]; this
0x180008027  call    ?MpNewAlloc@CommonUtil@@YAJPEAPEAX_K@Z; CommonUtil::MpNewAlloc(void * *,unsigned __int64)
0x18000802c  mov     edi, eax
0x18000802e  test    eax, eax
0x180008030  jns     short loc_180008053
0x180008032  mov     rcx, [rsp+78h+pSecurityDescriptor]
0x18000803a  test    rcx, rcx
0x18000803d  jz      short loc_180008045
0x18000803f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008045  mov     eax, edi
0x180008047  add     rsp, 50h
0x18000804b  pop     r15
0x18000804d  pop     r14
0x18000804f  pop     rdi
0x180008050  pop     rsi
0x180008051  pop     rbx
0x180008052  retn
0x180008053  mov     [rsp+78h+nLengthNeeded], ebx
0x18000805a  lea     rax, [rsp+78h+nLengthNeeded]
0x180008062  mov     [rsp+78h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180008067  mov     r9d, ebx; nLength
0x18000806a  mov     rdi, [rsp+78h+pSecurityDescriptor]
0x180008072  mov     r8, rdi; pSecurityDescriptor
0x180008075  mov     edx, 4; RequestedInformation
0x18000807a  mov     rcx, r15; lpFileName
0x18000807d  call    cs:__imp_GetFileSecurityW
0x180008083  test    eax, eax
0x180008085  jz      short loc_18000808B
0x180008087  xor     esi, esi
0x180008089  jmp     short loc_1800080DA
0x18000808b  call    HrGetLastFailure
0x180008090  mov     esi, eax
0x180008092  cmp     eax, 8007007Ah
0x180008097  jz      loc_1800081A9
0x18000809d  lea     rax, WPP_GLOBAL_Control
0x1800080a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800080ab  cmp     rcx, rax
0x1800080ae  jz      short loc_1800080D2
0x1800080b0  test    byte ptr [rcx+1Ch], 1
0x1800080b4  jz      short loc_1800080D2
0x1800080b6  mov     edx, 16h
0x1800080bb  mov     dword ptr [rsp+78h+lpnLengthNeeded], esi
0x1800080bf  mov     r9, r15
0x1800080c2  lea     r8, WPP_917185ddc84637471a8d5a2f656085a7_Traceguids
0x1800080c9  mov     rcx, [rcx+10h]
0x1800080cd  call    WPP_SF_Sd
0x1800080d2  test    esi, esi
0x1800080d4  js      loc_1800081B7
0x1800080da  mov     [rsp+78h+var_48], 0
0x1800080e3  mov     ecx, 40h ; '@'; Size
0x1800080e8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800080ed  mov     rbx, rax
0x1800080f0  mov     [rsp+78h+var_40], rax
0x1800080f5  test    rbx, rbx
0x1800080f8  jz      short loc_180008119
0x1800080fa  mov     rdx, rdi; void *
0x1800080fd  mov     rcx, rax; this
0x180008100  call    ??0CSecurityAttributesHolder@CommonUtil@@IEAA@PEAX@Z; CommonUtil::CSecurityAttributesHolder::CSecurityAttributesHolder(void *)
0x180008105  lea     rax, ??_7?$CSecurityAttributesAlloc@V?$CUniqueHandle@UCAutoGenericBufferDelete@CommonUtil@@@CommonUtil@@@CommonUtil@@6B@; const CommonUtil::CSecurityAttributesAlloc<CommonUtil::CUniqueHandle<CommonUtil::CAutoGenericBufferDelete>>::`vftable'
0x18000810c  mov     [rbx], rax
0x18000810f  xor     edi, edi
0x180008111  mov     [rsp+78h+pSecurityDescriptor], rdi
0x180008119  test    rbx, rbx
0x18000811c  jz      short loc_180008132
0x18000811e  mov     eax, [rbx+8]
0x180008121  test    eax, eax
0x180008123  jnz     short loc_18000812E
0x180008125  mov     dword ptr [rbx+8], 1
0x18000812c  jmp     short loc_180008132
0x18000812e  lock inc dword ptr [rbx+8]
0x180008132  mov     [rsp+78h+var_48], rbx
0x180008137  jmp     short loc_180008155
0x180008139  mov     r14, [rsp+78h+arg_0]
0x180008141  mov     esi, [rsp+78h+nLengthNeeded]
0x180008148  mov     rdi, [rsp+78h+pSecurityDescriptor]
0x180008150  mov     rbx, [rsp+78h+var_48]
0x180008155  test    esi, esi
0x180008157  jns     short loc_180008191
0x180008159  test    rbx, rbx
0x18000815c  jz      short loc_1800081B7
0x18000815e  mov     eax, [rbx+8]
0x180008161  cmp     eax, 1
0x180008164  jnz     short loc_18000816F
0x180008166  mov     dword ptr [rbx+8], 0
0x18000816d  jmp     short loc_18000817C
0x18000816f  or      eax, 0FFFFFFFFh
0x180008172  lock xadd [rbx+8], eax
0x180008177  sub     eax, 1
0x18000817a  jg      short loc_1800081B7
0x18000817c  mov     rax, [rbx]
0x18000817f  mov     edx, 1
0x180008184  mov     rcx, rbx
0x180008187  mov     rax, [rax]
0x18000818a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000818f  jmp     short loc_1800081B7
0x180008191  mov     [r14], rbx
0x180008194  test    rdi, rdi
0x180008197  jz      short loc_1800081A2
0x180008199  mov     rcx, rdi
0x18000819c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800081a2  xor     eax, eax
0x1800081a4  jmp     loc_180008047
0x1800081a9  cmp     ebx, [rsp+78h+nLengthNeeded]
0x1800081b0  jb      short loc_1800081CC
0x1800081b2  mov     esi, 8000FFFFh
0x1800081b7  test    rdi, rdi
0x1800081ba  jz      short loc_1800081C5
0x1800081bc  mov     rcx, rdi
0x1800081bf  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800081c5  mov     eax, esi
0x1800081c7  jmp     loc_180008047
0x1800081cc  mov     ebx, [rsp+78h+nLengthNeeded]
0x1800081d3  jmp     loc_180008003
```
