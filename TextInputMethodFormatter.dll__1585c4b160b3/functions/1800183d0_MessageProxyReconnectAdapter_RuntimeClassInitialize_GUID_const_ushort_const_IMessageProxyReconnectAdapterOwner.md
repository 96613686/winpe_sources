# MessageProxyReconnectAdapter::RuntimeClassInitialize(_GUID const &,ushort const *,IMessageProxyReconnectAdapterOwner *)

- ea: `0x1800183d0`
- end: `0x18001869e`
- name: `?RuntimeClassInitialize@MessageProxyReconnectAdapter@@QEAAJAEBU_GUID@@PEBGPEAUIMessageProxyReconnectAdapterOwner@@@Z`
- size: `718`
- prototype: `__int64 __fastcall(MessageProxyReconnectAdapter *__hidden this, const struct _GUID *, const unsigned __int16 *, struct IMessageProxyReconnectAdapterOwner *)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180028b14`
- `0x18002bd40`
- `0x180036a80`

## callees

- `0x180006a14`
- `0x180017bec`
- `0x1800183d0`
- `0x1800186a4`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018446`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018446`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180018457`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180018457`
- `CoreMessaging!CoreUICreate` at `0x18001848a`
- `CoreMessaging!CoreUICreate` at `0x18001848a`
- `CoreUIComponents!CoreUIFactoryCreate` at `0x180018577`
- `CoreUIComponents!CoreUIFactoryCreate` at `0x180018577`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MessageProxyReconnectAdapter::RuntimeClassInitialize(
        MessageProxyReconnectAdapter *this,
        const struct _GUID *a2,
        const unsigned __int16 *a3,
        struct IMessageProxyReconnectAdapterOwner *a4)
{
  unsigned int String; // ebx
  __int64 v8; // rdx
  unsigned __int64 v9; // rsi
  HSTRING *v10; // rbx
  _QWORD *v11; // rbx
  __int64 v12; // rcx
  int v13; // eax
  unsigned int v14; // esi
  int v16; // eax
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // rcx
  int v23; // eax
  __int64 v24; // rcx
  int started; // eax
  __int64 v26; // rcx
  __int64 v27; // rcx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+28h]
  __int64 v30; // [rsp+60h] [rbp+40h] BYREF

  if ( !a3 )
  {
    String = -2147024809;
    v8 = 61;
LABEL_41:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"mincore\\textinput\\dev\\sharedlibs\\messageproxyreconnectadapter\\messageproxyreconnectadapter.cpp",
      (const char *)String,
      savedregs);
    return String;
  }
  if ( !a4 )
  {
    String = -2147024809;
    v8 = 62;
    goto LABEL_41;
  }
  *(struct _GUID *)((char *)this + 24) = *a2;
  v9 = -1;
  do
    ++v9;
  while ( a3[v9] );
  if ( v9 > 0xFFFFFFFF )
  {
    String = -2147024362;
    goto LABEL_40;
  }
  v10 = (HSTRING *)((char *)this + 88);
  WindowsDeleteString(*((HSTRING *)this + 11));
  *v10 = 0;
  String = WindowsCreateString(a3, v9, v10);
  if ( (String & 0x80000000) != 0 )
  {
LABEL_40:
    v8 = 65;
    goto LABEL_41;
  }
  *((_QWORD *)this + 6) = a4;
  v11 = (_QWORD *)((char *)this + 72);
  v12 = *((_QWORD *)this + 9);
  if ( v12 )
  {
    *v11 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  v13 = CoreUICreate((char *)this + 72);
  v14 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x44,
      (unsigned int)"mincore\\textinput\\dev\\sharedlibs\\messageproxyreconnectadapter\\messageproxyreconnectadapter.cpp",
      (const char *)(unsigned int)v13,
      savedregs);
    return v14;
  }
  v30 = 0;
  v16 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v11 + 40LL))(*v11, &v30);
  String = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4A,
      (unsigned int)"mincore\\textinput\\dev\\sharedlibs\\messageproxyreconnectadapter\\messageproxyreconnectadapter.cpp",
      (const char *)(unsigned int)v16,
      savedregs);
    v17 = v30;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    return String;
  }
  v18 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 56LL))(v30);
  String = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4B,
      (unsigned int)"mincore\\textinput\\dev\\sharedlibs\\messageproxyreconnectadapter\\messageproxyreconnectadapter.cpp",
      (const char *)(unsigned int)v18,
      savedregs);
    v19 = v30;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    return String;
  }
  v20 = *((_QWORD *)this + 7);
  if ( v20 )
  {
    *((_QWORD *)this + 7) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  }
  v21 = CoreUIFactoryCreate((char *)this + 56);
  String = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"mincore\\textinput\\dev\\sharedlibs\\messageproxyreconnectadapter\\messageproxyreconnectadapter.cpp",
      (const char *)(unsigned int)v21,
      savedregs);
    v22 = v30;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    return String;
  }
  v23 = MessageProxyReconnectAdapter::AttemptPullProxy(this);
  String = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4F,
      (unsigned int)"mincore\\textinput\\dev\\sharedlibs\\messageproxyreconnectadapter\\messageproxyreconnectadapter.cpp",
      (const char *)(unsigned int)v23,
      savedregs);
    v24 = v30;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    }
    return String;
  }
  if ( !*((_QWORD *)this + 8) )
  {
    started = MessageProxyReconnectAdapter::StartConnectionRetryTimer(this);
    String = started;
    if ( started < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x53,
        (unsigned int)"mincore\\textinput\\dev\\sharedlibs\\messageproxyreconnectadapter\\messageproxyreconnectadapter.cpp",
        (const char *)(unsigned int)started,
        savedregs);
      v26 = v30;
      if ( v30 )
      {
        v30 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      }
      return String;
    }
  }
  v27 = v30;
  if ( v30 )
  {
    v30 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  }
  return 0;
}

```

## disassembly

```asm
0x1800183d0  mov     [rsp-28h+arg_0], rbx
0x1800183d5  mov     [rsp-28h+arg_8], rsi
0x1800183da  push    rbp
0x1800183db  push    rdi
0x1800183dc  push    r12
0x1800183de  push    r14
0x1800183e0  push    r15; int
0x1800183e2  mov     rbp, rsp
0x1800183e5  sub     rsp, 20h
0x1800183e9  mov     r14, r9
0x1800183ec  mov     r15, r8
0x1800183ef  mov     rdi, rcx
0x1800183f2  xor     r12d, r12d
0x1800183f5  test    r8, r8
0x1800183f8  jnz     short loc_180018408
0x1800183fa  mov     ebx, 80070057h
0x1800183ff  lea     edx, [r8+3Dh]
0x180018403  jmp     loc_180018672
0x180018408  test    r14, r14
0x18001840b  jnz     short loc_18001841B
0x18001840d  mov     ebx, 80070057h
0x180018412  lea     edx, [r14+3Eh]
0x180018416  jmp     loc_180018672
0x18001841b  movups  xmm0, xmmword ptr [rdx]
0x18001841e  movdqu  xmmword ptr [rcx+18h], xmm0
0x180018423  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180018427  inc     rsi
0x18001842a  cmp     [r8+rsi*2], r12w
0x18001842f  jnz     short loc_180018427
0x180018431  mov     eax, 0FFFFFFFFh
0x180018436  cmp     rsi, rax
0x180018439  ja      loc_180018668
0x18001843f  lea     rbx, [rcx+58h]
0x180018443  mov     rcx, [rbx]; string
0x180018446  call    cs:__imp_WindowsDeleteString
0x18001844c  mov     [rbx], r12
0x18001844f  mov     edx, esi; length
0x180018451  mov     r8, rbx; string
0x180018454  mov     rcx, r15; sourceString
0x180018457  call    cs:__imp_WindowsCreateString
0x18001845d  mov     ebx, eax
0x18001845f  test    eax, eax
0x180018461  js      loc_18001866D
0x180018467  mov     [rdi+30h], r14
0x18001846b  lea     rbx, [rdi+48h]
0x18001846f  mov     rcx, [rbx]
0x180018472  test    rcx, rcx
0x180018475  jz      short loc_180018487
0x180018477  mov     [rbx], r12
0x18001847a  mov     rax, [rcx]
0x18001847d  mov     rax, [rax+10h]
0x180018481  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018486  nop
0x180018487  mov     rcx, rbx
0x18001848a  call    cs:__imp_CoreUICreate
0x180018490  mov     esi, eax
0x180018492  test    eax, eax
0x180018494  jns     short loc_1800184B5
0x180018496  mov     rcx, [rbp+28h]; this
0x18001849a  mov     r9d, eax; char *
0x18001849d  lea     r8, aMincoreTextinp_8; "mincore\\textinput\\dev\\sharedlibs\\me"...
0x1800184a4  mov     edx, 44h ; 'D'; void *
0x1800184a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800184ae  mov     eax, esi
0x1800184b0  jmp     loc_180018687
0x1800184b5  mov     [rbp+arg_10], r12
0x1800184b9  mov     rcx, [rbx]
0x1800184bc  mov     rax, [rcx]
0x1800184bf  lea     rdx, [rbp+arg_10]
0x1800184c3  mov     rax, [rax+28h]
0x1800184c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800184cc  mov     ebx, eax
0x1800184ce  test    eax, eax
0x1800184d0  jns     short loc_18001850A
0x1800184d2  mov     rcx, [rbp+28h]; this
0x1800184d6  mov     r9d, eax; char *
0x1800184d9  lea     r8, aMincoreTextinp_8; "mincore\\textinput\\dev\\sharedlibs\\me"...
0x1800184e0  mov     edx, 4Ah ; 'J'; void *
0x1800184e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800184ea  nop
0x1800184eb  mov     rcx, [rbp+arg_10]
0x1800184ef  test    rcx, rcx
0x1800184f2  jz      short loc_180018505
0x1800184f4  mov     [rbp+arg_10], r12
0x1800184f8  mov     rax, [rcx]
0x1800184fb  mov     rax, [rax+10h]
0x1800184ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018504  nop
0x180018505  jmp     loc_180018685
0x18001850a  mov     rcx, [rbp+arg_10]
0x18001850e  mov     rax, [rcx]
0x180018511  mov     rax, [rax+38h]
0x180018515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001851a  mov     ebx, eax
0x18001851c  test    eax, eax
0x18001851e  jns     short loc_180018558
0x180018520  mov     rcx, [rbp+28h]; this
0x180018524  mov     r9d, eax; char *
0x180018527  lea     r8, aMincoreTextinp_8; "mincore\\textinput\\dev\\sharedlibs\\me"...
0x18001852e  mov     edx, 4Bh ; 'K'; void *
0x180018533  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018538  nop
0x180018539  mov     rcx, [rbp+arg_10]
0x18001853d  test    rcx, rcx
0x180018540  jz      short loc_180018553
0x180018542  mov     [rbp+arg_10], r12
0x180018546  mov     rax, [rcx]
0x180018549  mov     rax, [rax+10h]
0x18001854d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018552  nop
0x180018553  jmp     loc_180018685
0x180018558  lea     rbx, [rdi+38h]
0x18001855c  mov     rcx, [rbx]
0x18001855f  test    rcx, rcx
0x180018562  jz      short loc_180018574
0x180018564  mov     [rbx], r12
0x180018567  mov     rax, [rcx]
0x18001856a  mov     rax, [rax+10h]
0x18001856e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018573  nop
0x180018574  mov     rcx, rbx
0x180018577  call    cs:__imp_CoreUIFactoryCreate
0x18001857d  mov     ebx, eax
0x18001857f  test    eax, eax
0x180018581  jns     short loc_1800185BB
0x180018583  mov     rcx, [rbp+28h]; this
0x180018587  mov     r9d, eax; char *
0x18001858a  lea     r8, aMincoreTextinp_8; "mincore\\textinput\\dev\\sharedlibs\\me"...
0x180018591  mov     edx, 4Dh ; 'M'; void *
0x180018596  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001859b  nop
0x18001859c  mov     rcx, [rbp+arg_10]
0x1800185a0  test    rcx, rcx
0x1800185a3  jz      short loc_1800185B6
0x1800185a5  mov     [rbp+arg_10], r12
0x1800185a9  mov     rax, [rcx]
0x1800185ac  mov     rax, [rax+10h]
0x1800185b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185b5  nop
0x1800185b6  jmp     loc_180018685
0x1800185bb  mov     rcx, rdi; this
0x1800185be  call    ?AttemptPullProxy@MessageProxyReconnectAdapter@@AEAAJXZ; MessageProxyReconnectAdapter::AttemptPullProxy(void)
0x1800185c3  mov     ebx, eax
0x1800185c5  test    eax, eax
0x1800185c7  jns     short loc_180018601
0x1800185c9  mov     rcx, [rbp+28h]; this
0x1800185cd  mov     r9d, eax; char *
0x1800185d0  lea     r8, aMincoreTextinp_8; "mincore\\textinput\\dev\\sharedlibs\\me"...
0x1800185d7  mov     edx, 4Fh ; 'O'; void *
0x1800185dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800185e1  nop
0x1800185e2  mov     rcx, [rbp+arg_10]
0x1800185e6  test    rcx, rcx
0x1800185e9  jz      short loc_1800185FC
0x1800185eb  mov     [rbp+arg_10], r12
0x1800185ef  mov     rax, [rcx]
0x1800185f2  mov     rax, [rax+10h]
0x1800185f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185fb  nop
0x1800185fc  jmp     loc_180018685
0x180018601  cmp     [rdi+40h], r12
0x180018605  jnz     short loc_18001864A
0x180018607  mov     rcx, rdi; this
0x18001860a  call    ?StartConnectionRetryTimer@MessageProxyReconnectAdapter@@AEAAJXZ; MessageProxyReconnectAdapter::StartConnectionRetryTimer(void)
0x18001860f  mov     ebx, eax
0x180018611  test    eax, eax
0x180018613  jns     short loc_18001864A
0x180018615  mov     rcx, [rbp+28h]; this
0x180018619  mov     r9d, eax; char *
0x18001861c  lea     r8, aMincoreTextinp_8; "mincore\\textinput\\dev\\sharedlibs\\me"...
0x180018623  mov     edx, 53h ; 'S'; void *
0x180018628  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001862d  nop
0x18001862e  mov     rcx, [rbp+arg_10]
0x180018632  test    rcx, rcx
0x180018635  jz      short loc_180018648
0x180018637  mov     [rbp+arg_10], r12
0x18001863b  mov     rax, [rcx]
0x18001863e  mov     rax, [rax+10h]
0x180018642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018647  nop
0x180018648  jmp     short loc_180018685
0x18001864a  mov     rcx, [rbp+arg_10]
0x18001864e  test    rcx, rcx
0x180018651  jz      short loc_180018664
0x180018653  mov     [rbp+arg_10], r12
0x180018657  mov     rax, [rcx]
0x18001865a  mov     rax, [rax+10h]
0x18001865e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018663  nop
0x180018664  xor     eax, eax
0x180018666  jmp     short loc_180018687
0x180018668  mov     ebx, 80070216h
0x18001866d  mov     edx, 41h ; 'A'; void *
0x180018672  mov     r9d, ebx; char *
0x180018675  lea     r8, aMincoreTextinp_8; "mincore\\textinput\\dev\\sharedlibs\\me"...
0x18001867c  mov     rcx, [rbp+28h]; this
0x180018680  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018685  mov     eax, ebx
0x180018687  mov     rbx, [rsp+20h+arg_0]
0x18001868c  mov     rsi, [rsp+20h+arg_8]
0x180018691  add     rsp, 20h
0x180018695  pop     r15
0x180018697  pop     r14
0x180018699  pop     r12
0x18001869b  pop     rdi
0x18001869c  pop     rbp
0x18001869d  retn
```
