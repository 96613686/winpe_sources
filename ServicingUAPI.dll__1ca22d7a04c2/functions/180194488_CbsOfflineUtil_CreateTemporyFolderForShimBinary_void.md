# CbsOfflineUtil::CreateTemporyFolderForShimBinary(void)

- ea: `0x180194488`
- end: `0x18019469c`
- name: `?CreateTemporyFolderForShimBinary@CbsOfflineUtil@@AEAAJXZ`
- size: `532`
- prototype: `__int64 __fastcall(CbsOfflineUtil *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180193980`

## callees

- `0x1800031d0`
- `0x180003c64`
- `0x18000ba14`
- `0x18000ba40`
- `0x180051244`
- `0x180194310`
- `0x180194488`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1801945c4`
- `ntdll!RtlFreeHeap` at `0x18019462b`
- `ntdll!RtlFreeHeap` at `0x18019465c`
- `ntdll!RtlFreeHeap` at `0x1801945c4`
- `ntdll!RtlFreeHeap` at `0x18019462b`
- `ntdll!RtlFreeHeap` at `0x18019465c`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18019451e`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18019451e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180194547`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180194547`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1801945ec`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1801945ec`

## pseudocode

```c
__int64 __fastcall CbsOfflineUtil::CreateTemporyFolderForShimBinary(CbsOfflineUtil *this)
{
  __int64 v2; // rcx
  HRESULT TemporaryPath; // ebx
  __int64 v4; // rdx
  int v6; // eax
  int v7; // eax
  PVOID v8; // rbx
  const char *v9; // r9
  unsigned int LastError; // edi
  int v11; // eax
  void *v12; // r8
  int v13; // eax
  PVOID P; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v15[3]; // [rsp+28h] [rbp-D8h] BYREF
  GUID pguid; // [rsp+40h] [rbp-C0h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v18[528]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  memset_0(v18, 0, 0x208u);
  pguid = 0;
  memset_0(sz, 0, sizeof(sz));
  P = 0;
  TemporaryPath = GetTemporaryPath(v2, v18);
  if ( TemporaryPath < 0 )
  {
    v4 = 75;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\base\\cbs\\offlineutil\\cbsofflineimagestack.cpp",
      (const char *)(unsigned int)TemporaryPath,
      (int)P);
    return (unsigned int)TemporaryPath;
  }
  TemporaryPath = CoCreateGuid(&pguid);
  if ( TemporaryPath < 0 )
  {
    v4 = 76;
    goto LABEL_3;
  }
  StringFromGUID2(&pguid, sz, 40);
  v15[0] = L"\\\\?\\";
  v15[1] = v18;
  v15[2] = sz;
  v6 = ConcatManyStrings(3, v15, &P);
  TemporaryPath = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x54,
      (unsigned int)"onecore\\base\\cbs\\offlineutil\\cbsofflineimagestack.cpp",
      (const char *)(unsigned int)v6,
      (int)P);
    if ( P )
    {
      LOBYTE(v7) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
      if ( !v7 )
        __fastfail(7u);
    }
    return (unsigned int)TemporaryPath;
  }
  v8 = P;
  if ( CreateDirectoryW((LPCWSTR)P, 0) )
  {
    v12 = (void *)*((_QWORD *)this + 2);
    if ( v12 )
    {
      LOBYTE(v13) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
      if ( !v13 )
        __fastfail(7u);
    }
    *((_QWORD *)this + 2) = v8;
    return 0;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x56,
                  (unsigned int)"onecore\\base\\cbs\\offlineutil\\cbsofflineimagestack.cpp",
                  v9);
    if ( v8 )
    {
      LOBYTE(v11) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
      if ( !v11 )
        __fastfail(7u);
    }
    return LastError;
  }
}

```

## disassembly

```asm
0x180194488  mov     [rsp-8+arg_8], rbx
0x18019448d  mov     [rsp-8+arg_10], rdi
0x180194492  push    rbp
0x180194493  lea     rbp, [rsp-1C0h]
0x18019449b  sub     rsp, 2C0h
0x1801944a2  mov     rax, cs:__security_cookie
0x1801944a9  xor     rax, rsp
0x1801944ac  mov     [rbp+1C0h+var_10], rax
0x1801944b3  mov     rdi, rcx
0x1801944b6  xor     edx, edx; Val
0x1801944b8  lea     rcx, [rbp+1C0h+var_220]; void *
0x1801944bc  mov     r8d, 208h; Size
0x1801944c2  call    memset_0
0x1801944c7  xor     edx, edx; Val
0x1801944c9  lea     rcx, [rsp+2C0h+sz]; void *
0x1801944ce  xorps   xmm0, xmm0
0x1801944d1  movups  xmmword ptr [rsp+2C0h+pguid.Data1], xmm0
0x1801944d6  lea     r8d, [rdx+50h]; Size
0x1801944da  call    memset_0
0x1801944df  lea     rdx, [rbp+1C0h+var_220]
0x1801944e3  mov     [rsp+2C0h+P], 0; int
0x1801944ec  call    GetTemporaryPath
0x1801944f1  mov     ebx, eax
0x1801944f3  test    eax, eax
0x1801944f5  jns     short loc_180194519
0x1801944f7  mov     edx, 4Bh ; 'K'; void *
0x1801944fc  mov     rcx, [rbp+1C8h]; this
0x180194503  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\offlineutil\\cbsoff"...
0x18019450a  mov     r9d, ebx; char *
0x18019450d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180194512  mov     eax, ebx
0x180194514  jmp     loc_180194677
0x180194519  lea     rcx, [rsp+2C0h+pguid]; pguid
0x18019451e  call    cs:__imp_CoCreateGuid
0x180194525  nop     dword ptr [rax+rax+00h]
0x18019452a  mov     ebx, eax
0x18019452c  test    eax, eax
0x18019452e  jns     short loc_180194537
0x180194530  mov     edx, 4Ch ; 'L'
0x180194535  jmp     short loc_1801944FC
0x180194537  mov     r8d, 28h ; '('; cchMax
0x18019453d  lea     rdx, [rsp+2C0h+sz]; lpsz
0x180194542  lea     rcx, [rsp+2C0h+pguid]; rguid
0x180194547  call    cs:__imp_StringFromGUID2
0x18019454e  nop     dword ptr [rax+rax+00h]
0x180194553  lea     rax, String1; "\\\\?\\"
0x18019455a  mov     ecx, 3
0x18019455f  mov     [rsp+2C0h+var_298], rax
0x180194564  lea     r8, [rsp+2C0h+P]
0x180194569  lea     rax, [rbp+1C0h+var_220]
0x18019456d  mov     [rsp+2C0h+var_290], rax
0x180194572  lea     rdx, [rsp+2C0h+var_298]
0x180194577  lea     rax, [rsp+2C0h+sz]
0x18019457c  mov     [rsp+2C0h+var_288], rax
0x180194581  call    ConcatManyStrings
0x180194586  mov     ebx, eax
0x180194588  test    eax, eax
0x18019458a  jns     short loc_1801945E2
0x18019458c  mov     rcx, [rbp+1C8h]; this
0x180194593  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\offlineutil\\cbsoff"...
0x18019459a  mov     r9d, eax; char *
0x18019459d  mov     edx, 54h ; 'T'; void *
0x1801945a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801945a7  mov     r8, [rsp+2C0h+P]; P
0x1801945ac  test    r8, r8
0x1801945af  jz      loc_180194512
0x1801945b5  mov     rcx, gs:60h
0x1801945be  xor     edx, edx; Flags
0x1801945c0  mov     rcx, [rcx+30h]; HeapHandle
0x1801945c4  call    cs:__imp_RtlFreeHeap
0x1801945cb  nop     dword ptr [rax+rax+00h]
0x1801945d0  test    eax, eax
0x1801945d2  jnz     loc_180194512
0x1801945d8  lea     ecx, [rax+7]
0x1801945db  int     29h; Win8: RtlFailFast(ecx)
0x1801945dd  jmp     loc_180194512
0x1801945e2  mov     rbx, [rsp+2C0h+P]
0x1801945e7  xor     edx, edx; lpSecurityAttributes
0x1801945e9  mov     rcx, rbx; lpPathName
0x1801945ec  call    cs:__imp_CreateDirectoryW
0x1801945f3  nop     dword ptr [rax+rax+00h]
0x1801945f8  test    eax, eax
0x1801945fa  jnz     short loc_180194644
0x1801945fc  mov     rcx, [rbp+1C8h]; this
0x180194603  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\offlineutil\\cbsoff"...
0x18019460a  lea     edx, [rax+56h]; void *
0x18019460d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180194612  mov     edi, eax
0x180194614  test    rbx, rbx
0x180194617  jz      short loc_180194640
0x180194619  mov     rcx, gs:60h
0x180194622  mov     r8, rbx; P
0x180194625  xor     edx, edx; Flags
0x180194627  mov     rcx, [rcx+30h]; HeapHandle
0x18019462b  call    cs:__imp_RtlFreeHeap
0x180194632  nop     dword ptr [rax+rax+00h]
0x180194637  test    eax, eax
0x180194639  jnz     short loc_180194640
0x18019463b  lea     ecx, [rax+7]
0x18019463e  int     29h; Win8: RtlFailFast(ecx)
0x180194640  mov     eax, edi
0x180194642  jmp     short loc_180194677
0x180194644  mov     r8, [rdi+10h]; P
0x180194648  test    r8, r8
0x18019464b  jz      short loc_180194671
0x18019464d  mov     rcx, gs:60h
0x180194656  xor     edx, edx; Flags
0x180194658  mov     rcx, [rcx+30h]; HeapHandle
0x18019465c  call    cs:__imp_RtlFreeHeap
0x180194663  nop     dword ptr [rax+rax+00h]
0x180194668  test    eax, eax
0x18019466a  jnz     short loc_180194671
0x18019466c  lea     ecx, [rax+7]
0x18019466f  int     29h; Win8: RtlFailFast(ecx)
0x180194671  mov     [rdi+10h], rbx
0x180194675  xor     eax, eax
0x180194677  mov     rcx, [rbp+1C0h+var_10]
0x18019467e  xor     rcx, rsp; StackCookie
0x180194681  call    __security_check_cookie
0x180194686  lea     r11, [rsp+2C0h+var_s0]
0x18019468e  mov     rbx, [r11+18h]
0x180194692  mov     rdi, [r11+20h]
0x180194696  mov     rsp, r11
0x180194699  pop     rbp
0x18019469a  retn
```
