# CWUSLSParse::Init(wchar_t * const &)

- ea: `0x14003d5b0`
- end: `0x14003d873`
- name: `?Init@CWUSLSParse@@QEAAJAEBQEA_W@Z`
- size: `707`
- prototype: `__int64 __fastcall(CWUSLSParse *__hidden this, wchar_t *const *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003d4fc`

## callees

- `0x140008de4`
- `0x14000d7e4`
- `0x1400154b4`
- `0x14003d5b0`
- `0x140045dc0`
- `0x14004cd00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14003d63a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14003d63a`
- `OLEAUT32!__imp_SysFreeString` at `0x14003d772`
- `OLEAUT32!__imp_SysFreeString` at `0x14003d7f8`
- `OLEAUT32!__imp_SysFreeString` at `0x14003d772`
- `OLEAUT32!__imp_SysFreeString` at `0x14003d7f8`
- `OLEAUT32!__imp_SysStringLen` at `0x14003d5f3`
- `OLEAUT32!__imp_SysStringLen` at `0x14003d5f3`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall CWUSLSParse::Init(CWUSLSParse *this, BSTR *a2)
{
  char v4; // r15
  HRESULT Instance; // esi
  __int64 v6; // rdx
  _QWORD *v7; // r14
  int v8; // eax
  int v9; // eax
  __int64 v10; // rbx
  unsigned int (__fastcall *v11)(__int64, BSTR *); // rdi
  int ppv; // [rsp+20h] [rbp-50h]
  __int16 v14; // [rsp+50h] [rbp-20h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-18h] BYREF
  __int64 v16; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  v4 = 1;
  if ( !SysStringLen(*a2) )
  {
    Instance = -2147024809;
    v6 = 236;
LABEL_9:
    v7 = (_QWORD *)((char *)this + 8);
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\wusls.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
    goto LABEL_31;
  }
  v7 = (_QWORD *)((char *)this + 8);
  if ( *((_QWORD *)this + 1) )
  {
    Instance = -2145103617;
    v6 = 239;
    goto LABEL_9;
  }
  Instance = CoCreateInstance(
               &CLSID_DOMDocument60,
               0,
               1u,
               &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
               (LPVOID *)this + 1);
  if ( Instance < 0 )
  {
    v6 = 241;
    goto LABEL_9;
  }
  Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v7 + 504LL))(*v7, 0);
  if ( Instance < 0 )
  {
    v6 = 243;
    goto LABEL_9;
  }
  Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v7 + 544LL))(*v7, 0);
  if ( Instance < 0 )
  {
    v6 = 244;
    goto LABEL_22;
  }
  Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v7 + 560LL))(*v7, 0);
  if ( Instance < 0 )
  {
    v6 = 245;
    goto LABEL_22;
  }
  v14 = 0;
  v8 = (*(__int64 (__fastcall **)(_QWORD, BSTR, __int16 *))(*(_QWORD *)*v7 + 520LL))(*v7, *a2, &v14);
  Instance = v8;
  if ( !v14 || v8 == 1 )
  {
    v16 = 0;
    bstrString = 0;
    if ( !(*(unsigned int (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v7 + 480LL))(*v7, &v16) )
    {
      v10 = v16;
      v11 = *(unsigned int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v16 + 72LL);
      SysFreeString(bstrString);
      bstrString = 0;
      if ( !v11(v10, &bstrString) )
        WUTrace(0, 0, 4, 3, 0, L"Failed parsing %ws");
    }
    if ( Instance < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x105,
        (int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\wusls.cpp",
        (const char *)(unsigned int)Instance);
    Instance = -2145103871;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x107,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\wusls.cpp",
      (const char *)0x80245001LL,
      ppv);
    SysFreeString(bstrString);
    bstrString = 0;
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  else
  {
    if ( v8 < 0 )
    {
      v6 = 267;
      goto LABEL_22;
    }
    v9 = (*(__int64 (__fastcall **)(_QWORD, CWUSLSParse *))(*(_QWORD *)*v7 + 360LL))(*v7, this);
    Instance = v9;
    if ( v9 == 1 )
    {
      Instance = -2145103870;
LABEL_21:
      v6 = 275;
      goto LABEL_22;
    }
    if ( v9 < 0 )
      goto LABEL_21;
    v4 = 0;
    Instance = 0;
  }
LABEL_31:
  if ( v4 )
  {
    if ( *(_QWORD *)this )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)this + 16LL))(*(_QWORD *)this);
    *(_QWORD *)this = 0;
    if ( *v7 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 16LL))(*v7);
    *v7 = 0;
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x14003d5b0  mov     [rsp-38h+arg_10], rbx
0x14003d5b5  push    rbp
0x14003d5b6  push    rsi
0x14003d5b7  push    rdi
0x14003d5b8  push    r12
0x14003d5ba  push    r13
0x14003d5bc  push    r14
0x14003d5be  push    r15
0x14003d5c0  mov     rbp, rsp
0x14003d5c3  sub     rsp, 70h
0x14003d5c7  mov     rax, cs:__security_cookie
0x14003d5ce  xor     rax, rsp
0x14003d5d1  mov     [rbp+var_8], rax
0x14003d5d5  mov     rbx, rdx
0x14003d5d8  mov     r12, rcx
0x14003d5db  xorps   xmm0, xmm0
0x14003d5de  movups  [rbp+var_30], xmm0
0x14003d5e2  mov     qword ptr [rbp+var_30], rcx
0x14003d5e6  mov     r15d, 1
0x14003d5ec  mov     byte ptr [rbp+var_30+8], r15b
0x14003d5f0  mov     rcx, [rdx]; pbstr
0x14003d5f3  call    cs:__imp_SysStringLen
0x14003d5f9  xor     r13d, r13d
0x14003d5fc  test    eax, eax
0x14003d5fe  jnz     short loc_14003D60C
0x14003d600  mov     esi, 80070057h
0x14003d605  mov     edx, 0ECh
0x14003d60a  jmp     short loc_14003D66C
0x14003d60c  lea     r14, [r12+8]
0x14003d611  cmp     [r14], r13
0x14003d614  jz      short loc_14003D622
0x14003d616  mov     esi, 802450FFh
0x14003d61b  mov     edx, 0EFh
0x14003d620  jmp     short loc_14003D66C
0x14003d622  mov     [rsp+70h+ppv], r14; int
0x14003d627  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x14003d62e  mov     r8d, r15d; dwClsContext
0x14003d631  xor     edx, edx; pUnkOuter
0x14003d633  lea     rcx, CLSID_DOMDocument60; rclsid
0x14003d63a  call    cs:__imp_CoCreateInstance
0x14003d640  mov     esi, eax
0x14003d642  test    eax, eax
0x14003d644  jns     short loc_14003D64D
0x14003d646  mov     edx, 0F1h
0x14003d64b  jmp     short loc_14003D66C
0x14003d64d  mov     rcx, [r14]
0x14003d650  xor     edx, edx
0x14003d652  mov     rax, [rcx]
0x14003d655  mov     rax, [rax+1F8h]
0x14003d65c  call    _guard_dispatch_icall
0x14003d661  mov     esi, eax
0x14003d663  test    eax, eax
0x14003d665  jns     short loc_14003D676
0x14003d667  mov     edx, 0F3h
0x14003d66c  lea     r14, [r12+8]
0x14003d671  jmp     loc_14003D71E
0x14003d676  mov     rcx, [r14]
0x14003d679  xor     edx, edx
0x14003d67b  mov     rax, [rcx]
0x14003d67e  mov     rax, [rax+220h]
0x14003d685  call    _guard_dispatch_icall
0x14003d68a  mov     esi, eax
0x14003d68c  test    eax, eax
0x14003d68e  jns     short loc_14003D69A
0x14003d690  mov     edx, 0F4h
0x14003d695  jmp     loc_14003D71E
0x14003d69a  mov     rcx, [r14]
0x14003d69d  xor     edx, edx
0x14003d69f  mov     rax, [rcx]
0x14003d6a2  mov     rax, [rax+230h]
0x14003d6a9  call    _guard_dispatch_icall
0x14003d6ae  mov     esi, eax
0x14003d6b0  test    eax, eax
0x14003d6b2  jns     short loc_14003D6BB
0x14003d6b4  mov     edx, 0F5h
0x14003d6b9  jmp     short loc_14003D71E
0x14003d6bb  mov     [rbp+var_20], r13w
0x14003d6c0  mov     rcx, [r14]
0x14003d6c3  mov     rax, [rcx]
0x14003d6c6  lea     r8, [rbp+var_20]
0x14003d6ca  mov     rdx, [rbx]
0x14003d6cd  mov     rax, [rax+208h]
0x14003d6d4  call    _guard_dispatch_icall
0x14003d6d9  mov     esi, eax
0x14003d6db  cmp     r13w, [rbp+var_20]
0x14003d6e0  jz      short loc_14003D741
0x14003d6e2  cmp     eax, r15d
0x14003d6e5  jz      short loc_14003D741
0x14003d6e7  test    eax, eax
0x14003d6e9  jns     short loc_14003D6F2
0x14003d6eb  mov     edx, 10Bh
0x14003d6f0  jmp     short loc_14003D71E
0x14003d6f2  mov     rcx, [r14]
0x14003d6f5  mov     rax, [rcx]
0x14003d6f8  mov     rdx, r12
0x14003d6fb  mov     rax, [rax+168h]
0x14003d702  call    _guard_dispatch_icall
0x14003d707  mov     esi, eax
0x14003d709  cmp     eax, r15d
0x14003d70c  jnz     short loc_14003D715
0x14003d70e  mov     esi, 80245002h
0x14003d713  jmp     short loc_14003D719
0x14003d715  test    eax, eax
0x14003d717  jns     short loc_14003D736
0x14003d719  mov     edx, 113h; void *
0x14003d71e  mov     rcx, [rbp+38h]; this
0x14003d722  mov     r9d, esi; char *
0x14003d725  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003d72c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003d731  jmp     loc_14003D818
0x14003d736  mov     r15b, r13b
0x14003d739  mov     esi, r13d
0x14003d73c  jmp     loc_14003D818
0x14003d741  mov     [rbp+var_10], r13
0x14003d745  mov     [rbp+bstrString], r13
0x14003d749  mov     rcx, [r14]
0x14003d74c  mov     rax, [rcx]
0x14003d74f  lea     rdx, [rbp+var_10]
0x14003d753  mov     rax, [rax+1E0h]
0x14003d75a  call    _guard_dispatch_icall
0x14003d75f  test    eax, eax
0x14003d761  jnz     short loc_14003D7BA
0x14003d763  mov     rbx, [rbp+var_10]
0x14003d767  mov     rax, [rbx]
0x14003d76a  mov     rdi, [rax+48h]
0x14003d76e  mov     rcx, [rbp+bstrString]; bstrString
0x14003d772  call    cs:__imp_SysFreeString
0x14003d778  mov     [rbp+bstrString], r13
0x14003d77c  lea     rdx, [rbp+bstrString]
0x14003d780  mov     rcx, rbx
0x14003d783  mov     rax, rdi
0x14003d786  call    _guard_dispatch_icall
0x14003d78b  test    eax, eax
0x14003d78d  jnz     short loc_14003D7BA
0x14003d78f  mov     rax, [rbp+bstrString]
0x14003d793  mov     [rsp+70h+var_40], rax
0x14003d798  lea     rax, aFailedParsingW; "Failed parsing %ws"
0x14003d79f  mov     [rsp+70h+var_48], rax
0x14003d7a4  mov     [rsp+70h+ppv], r13; int
0x14003d7a9  xor     edx, edx
0x14003d7ab  xor     ecx, ecx
0x14003d7ad  lea     r9d, [rdx+3]
0x14003d7b1  lea     r8d, [rdx+4]
0x14003d7b5  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14003d7ba  mov     rcx, [rbp+38h]; this
0x14003d7be  test    esi, esi
0x14003d7c0  jns     short loc_14003D7D6
0x14003d7c2  mov     r9d, esi; char *
0x14003d7c5  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003d7cc  mov     edx, 105h; void *
0x14003d7d1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14003d7d6  mov     rcx, [rbp+38h]; this
0x14003d7da  mov     esi, 80245001h
0x14003d7df  mov     r9d, esi; char *
0x14003d7e2  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003d7e9  mov     edx, 107h; void *
0x14003d7ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003d7f3  nop
0x14003d7f4  mov     rcx, [rbp+bstrString]; bstrString
0x14003d7f8  call    cs:__imp_SysFreeString
0x14003d7fe  mov     [rbp+bstrString], r13
0x14003d802  mov     rcx, [rbp+var_10]
0x14003d806  test    rcx, rcx
0x14003d809  jz      short loc_14003D818
0x14003d80b  mov     rax, [rcx]
0x14003d80e  mov     rax, [rax+10h]
0x14003d812  call    _guard_dispatch_icall
0x14003d817  nop
0x14003d818  test    r15b, r15b
0x14003d81b  jz      short loc_14003D84D
0x14003d81d  mov     rcx, [r12]
0x14003d821  test    rcx, rcx
0x14003d824  jz      short loc_14003D832
0x14003d826  mov     rax, [rcx]
0x14003d829  mov     rax, [rax+10h]
0x14003d82d  call    _guard_dispatch_icall
0x14003d832  mov     [r12], r13
0x14003d836  mov     rcx, [r14]
0x14003d839  test    rcx, rcx
0x14003d83c  jz      short loc_14003D84A
0x14003d83e  mov     rdx, [rcx]
0x14003d841  mov     rax, [rdx+10h]
0x14003d845  call    _guard_dispatch_icall
0x14003d84a  mov     [r14], r13
0x14003d84d  mov     eax, esi
0x14003d84f  mov     rcx, [rbp+var_8]
0x14003d853  xor     rcx, rsp; StackCookie
0x14003d856  call    __security_check_cookie
0x14003d85b  mov     rbx, [rsp+70h+arg_10]
0x14003d863  add     rsp, 70h
0x14003d867  pop     r15
0x14003d869  pop     r14
0x14003d86b  pop     r13
0x14003d86d  pop     r12
0x14003d86f  pop     rdi
0x14003d870  pop     rsi
0x14003d871  pop     rbp
0x14003d872  retn
```
