# UndockedComponentInfo::Init(long,UndockedComponentLoadFlags,wchar_t const *,wchar_t const *,wchar_t const *)

- ea: `0x18000d538`
- end: `0x18000d6ef`
- name: `?Init@UndockedComponentInfo@@QEAAJJW4UndockedComponentLoadFlags@@PEB_W11@Z`
- size: `439`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180003128`

## callees

- `0x180006858`
- `0x18000a150`
- `0x18000d538`
- `0x18000e174`
- `0x18000e3ac`
- `0x18000e8a8`
- `0x18000ed40`

## pseudocode

```c
__int64 __fastcall UndockedComponentInfo::Init(__int64 a1, int a2, int a3, void *a4, _WORD *Src, void *a6)
{
  _QWORD *v6; // rdi
  void *v9; // rcx
  int v10; // eax
  unsigned int v11; // edi
  __int64 v12; // rdx
  void *v14; // rcx
  int v15; // eax
  void *v16; // rcx
  int v17; // eax
  int FileVersion; // ebx
  __int64 v19; // rdx
  void *v20; // rcx
  unsigned __int64 v21; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v6 = (_QWORD *)(a1 + 8);
  *(_DWORD *)a1 = a2;
  *(_DWORD *)(a1 + 4) = a3;
  v9 = *(void **)(a1 + 8);
  if ( v9 )
  {
    SusFree(v9);
    *v6 = 0;
  }
  v10 = SusStrCchDup<wchar_t const *,wchar_t *>(a4);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x212,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\StringUtil.cpp",
      (const char *)(unsigned int)v10,
      v21);
    v12 = 15;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\UndockingTelemetry\\UndockingTelemetry.cpp",
      (const char *)v11,
      v21);
    return v11;
  }
  v14 = *(void **)(a1 + 16);
  if ( v14 )
  {
    SusFree(v14);
    *(_QWORD *)(a1 + 16) = 0;
  }
  v15 = SusStrCchDup<wchar_t const *,wchar_t *>(Src);
  v11 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x212,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\StringUtil.cpp",
      (const char *)(unsigned int)v15,
      v21);
    v12 = 17;
    goto LABEL_5;
  }
  v16 = *(void **)(a1 + 32);
  if ( v16 )
  {
    SusFree(v16);
    *(_QWORD *)(a1 + 32) = 0;
  }
  v17 = SusStrCchDup<wchar_t const *,wchar_t *>(a6);
  v11 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x212,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\StringUtil.cpp",
      (const char *)(unsigned int)v17,
      v21);
    v12 = 19;
    goto LABEL_5;
  }
  if ( Src && *Src )
  {
    v21 = 0;
    FileVersion = GetFileVersion(Src, &v21);
    if ( FileVersion < 0 )
    {
      v19 = 24;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\UndockingTelemetry\\UndockingTelemetry.cpp",
        (const char *)(unsigned int)FileVersion,
        v21);
      return (unsigned int)FileVersion;
    }
    v20 = *(void **)(a1 + 24);
    if ( v20 )
    {
      SusFree(v20);
      *(_QWORD *)(a1 + 24) = 0;
    }
    FileVersion = ConvertFileVerToStringW(v21, (wchar_t **)(a1 + 24));
    if ( FileVersion < 0 )
    {
      v19 = 25;
      goto LABEL_18;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000d538  mov     [rsp+arg_8], rbx
0x18000d53d  push    rbp
0x18000d53e  push    rsi
0x18000d53f  push    rdi
0x18000d540  push    r14
0x18000d542  push    r15
0x18000d544  sub     rsp, 30h
0x18000d548  mov     rax, cs:__security_cookie
0x18000d54f  xor     rax, rsp
0x18000d552  mov     [rsp+58h+var_30], rax
0x18000d557  mov     rbx, [rsp+58h+Src]
0x18000d55f  lea     rdi, [rcx+8]
0x18000d563  mov     r14, [rsp+58h+arg_28]
0x18000d56b  mov     rsi, rcx
0x18000d56e  mov     [rcx], edx
0x18000d570  xor     r15d, r15d
0x18000d573  mov     [rcx+4], r8d
0x18000d577  mov     rbp, r9
0x18000d57a  mov     rcx, [rdi]; lpMem
0x18000d57d  test    rcx, rcx
0x18000d580  jz      short loc_18000D58A
0x18000d582  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18000d587  mov     [rdi], r15
0x18000d58a  mov     r8, rdi
0x18000d58d  mov     rcx, rbp; Src
0x18000d590  call    ??$SusStrCchDup@PEB_WPEA_W@@YAJPEB_WIPEAPEA_W@Z; SusStrCchDup<wchar_t const *,wchar_t *>(wchar_t const *,uint,wchar_t * *)
0x18000d595  mov     edi, eax
0x18000d597  test    eax, eax
0x18000d599  jns     short loc_18000D5D4
0x18000d59b  mov     rcx, [rsp+58h]; this
0x18000d5a0  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000d5a7  mov     r9d, eax; char *
0x18000d5aa  mov     edx, 212h; void *
0x18000d5af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d5b4  mov     edx, 0Fh; void *
0x18000d5b9  mov     rcx, [rsp+58h]; this
0x18000d5be  lea     r8, aCW1SSrcClientL_1; "C:\\__w\\1\\s\\src\\Client\\lib\\Undock"...
0x18000d5c5  mov     r9d, edi; char *
0x18000d5c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d5cd  mov     eax, edi
0x18000d5cf  jmp     loc_18000D6D1
0x18000d5d4  lea     rdi, [rsi+10h]
0x18000d5d8  mov     rcx, [rdi]; lpMem
0x18000d5db  test    rcx, rcx
0x18000d5de  jz      short loc_18000D5E8
0x18000d5e0  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18000d5e5  mov     [rdi], r15
0x18000d5e8  mov     r8, rdi
0x18000d5eb  mov     rcx, rbx; Src
0x18000d5ee  call    ??$SusStrCchDup@PEB_WPEA_W@@YAJPEB_WIPEAPEA_W@Z; SusStrCchDup<wchar_t const *,wchar_t *>(wchar_t const *,uint,wchar_t * *)
0x18000d5f3  mov     edi, eax
0x18000d5f5  test    eax, eax
0x18000d5f7  jns     short loc_18000D619
0x18000d5f9  mov     rcx, [rsp+58h]; this
0x18000d5fe  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000d605  mov     r9d, eax; char *
0x18000d608  mov     edx, 212h; void *
0x18000d60d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d612  mov     edx, 11h
0x18000d617  jmp     short loc_18000D5B9
0x18000d619  lea     rdi, [rsi+20h]
0x18000d61d  mov     rcx, [rdi]; lpMem
0x18000d620  test    rcx, rcx
0x18000d623  jz      short loc_18000D62D
0x18000d625  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18000d62a  mov     [rdi], r15
0x18000d62d  mov     r8, rdi
0x18000d630  mov     rcx, r14; Src
0x18000d633  call    ??$SusStrCchDup@PEB_WPEA_W@@YAJPEB_WIPEAPEA_W@Z; SusStrCchDup<wchar_t const *,wchar_t *>(wchar_t const *,uint,wchar_t * *)
0x18000d638  mov     edi, eax
0x18000d63a  test    eax, eax
0x18000d63c  jns     short loc_18000D661
0x18000d63e  mov     rcx, [rsp+58h]; this
0x18000d643  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000d64a  mov     r9d, eax; char *
0x18000d64d  mov     edx, 212h; void *
0x18000d652  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d657  mov     edx, 13h
0x18000d65c  jmp     loc_18000D5B9
0x18000d661  test    rbx, rbx
0x18000d664  jz      short loc_18000D6CF
0x18000d666  cmp     [rbx], r15w
0x18000d66a  jz      short loc_18000D6CF
0x18000d66c  lea     rdx, [rsp+58h+var_38]
0x18000d671  mov     [rsp+58h+var_38], r15; int
0x18000d676  mov     rcx, rbx
0x18000d679  call    ?GetFileVersion@@YAJPEB_WPEA_KW4GetFileVersionFlag@@@Z; GetFileVersion(wchar_t const *,unsigned __int64 *,GetFileVersionFlag)
0x18000d67e  mov     ebx, eax
0x18000d680  test    eax, eax
0x18000d682  jns     short loc_18000D6A1
0x18000d684  mov     edx, 18h; void *
0x18000d689  mov     rcx, [rsp+58h]; this
0x18000d68e  lea     r8, aCW1SSrcClientL_1; "C:\\__w\\1\\s\\src\\Client\\lib\\Undock"...
0x18000d695  mov     r9d, ebx; char *
0x18000d698  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d69d  mov     eax, ebx
0x18000d69f  jmp     short loc_18000D6D1
0x18000d6a1  lea     rbx, [rsi+18h]
0x18000d6a5  mov     rcx, [rbx]; lpMem
0x18000d6a8  test    rcx, rcx
0x18000d6ab  jz      short loc_18000D6B5
0x18000d6ad  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18000d6b2  mov     [rbx], r15
0x18000d6b5  mov     rcx, [rsp+58h+var_38]; unsigned __int64
0x18000d6ba  mov     rdx, rbx; wchar_t **
0x18000d6bd  call    ?ConvertFileVerToStringW@@YAJ_KPEAPEA_W@Z; ConvertFileVerToStringW(unsigned __int64,wchar_t * *)
0x18000d6c2  mov     ebx, eax
0x18000d6c4  test    eax, eax
0x18000d6c6  jns     short loc_18000D6CF
0x18000d6c8  mov     edx, 19h
0x18000d6cd  jmp     short loc_18000D689
0x18000d6cf  xor     eax, eax
0x18000d6d1  mov     rcx, [rsp+58h+var_30]
0x18000d6d6  xor     rcx, rsp; StackCookie
0x18000d6d9  call    __security_check_cookie
0x18000d6de  mov     rbx, [rsp+58h+arg_8]
0x18000d6e3  add     rsp, 30h
0x18000d6e7  pop     r15
0x18000d6e9  pop     r14
0x18000d6eb  pop     rdi
0x18000d6ec  pop     rsi
0x18000d6ed  pop     rbp
0x18000d6ee  retn
```
