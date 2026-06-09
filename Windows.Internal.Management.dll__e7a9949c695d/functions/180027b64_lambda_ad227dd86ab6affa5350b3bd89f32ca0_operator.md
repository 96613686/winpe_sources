# _lambda_ad227dd86ab6affa5350b3bd89f32ca0_::operator()

- ea: `0x180027b64`
- end: `0x180027d71`
- name: `_lambda_ad227dd86ab6affa5350b3bd89f32ca0_::operator()`
- size: `525`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180034cc0`

## callees

- `0x180004d50`
- `0x180005280`
- `0x180008dac`
- `0x18000a2a4`
- `0x180022668`
- `0x180024c2c`
- `0x180027b64`
- `0x180029d2c`
- `0x180034f80`
- `0x180037aa0`

## import_xrefs

- `DMCmnUtils!MBToUnicode` at `0x180027c3d`
- `DMCmnUtils!MBToUnicode` at `0x180027c3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027c9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027d51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027c9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027d51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180027cc0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180027cc0`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall lambda_ad227dd86ab6affa5350b3bd89f32ca0_::operator()(__int64 a1, __int64 a2)
{
  HSTRING v3; // rax
  volatile signed __int64 *v4; // rax
  int v5; // ebx
  unsigned int v6; // edx
  unsigned __int64 v7; // r9
  __int64 v8; // rdx
  WCHAR *v9; // rcx
  bool v10; // zf
  __int64 v11; // rdx
  HRESULT v12; // eax
  int v13; // eax
  unsigned int v14; // edx
  WCHAR *v15; // rcx
  PCNZWCH sourceString; // [rsp+20h] [rbp-E0h] BYREF
  TraceLoggingCorrelationVector *v18; // [rsp+28h] [rbp-D8h] BYREF
  HSTRING string; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v20; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING v21; // [rsp+40h] [rbp-C0h] BYREF
  char v22; // [rsp+48h] [rbp-B8h]
  PCNZWCH *p_sourceString; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v24; // [rsp+58h] [rbp-A8h] BYREF
  char v25; // [rsp+60h] [rbp-A0h]
  char v26[144]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  string = 0;
  v3 = (HSTRING)operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
  v21 = v3;
  if ( !v3 )
  {
    v18 = 0;
    goto LABEL_23;
  }
  v4 = (volatile signed __int64 *)TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(v3);
  v18 = (TraceLoggingCorrelationVector *)v4;
  if ( !v4 )
  {
LABEL_23:
    v5 = -2147467259;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1DC,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
      (const char *)0x80004005LL,
      (int)sourceString);
    goto LABEL_24;
  }
  v21 = (HSTRING)&v18;
  v22 = 1;
  if ( !TraceLoggingCorrelationVector::ToStringImpl(
          (TraceLoggingCorrelationVector *)v4,
          _InterlockedExchangeAdd64(v4 + 17, 0),
          v26) )
  {
    v5 = -2147467259;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E1,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
      (const char *)0x80004005LL,
      (int)sourceString);
LABEL_9:
    if ( v18 )
      TraceLoggingCorrelationVector::`scalar deleting destructor'(v18, v6);
    goto LABEL_24;
  }
  sourceString = 0;
  v20 = 0;
  p_sourceString = &sourceString;
  v24 = 0;
  v25 = 1;
  v5 = MBToUnicode(v26, 0xFDE9u, &v24, &v20);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>(&p_sourceString);
  if ( v5 < 0 )
  {
    v7 = (unsigned int)v5;
    v8 = 486;
    goto LABEL_7;
  }
  WindowsDeleteString(string);
  string = 0;
  v11 = -1;
  do
    ++v11;
  while ( sourceString[v11] );
  v12 = WindowsCreateString(sourceString, v11, &string);
  v5 = v12;
  if ( v12 < 0 )
  {
    v7 = (unsigned int)v12;
    v8 = 487;
    goto LABEL_7;
  }
  v21 = string;
  v13 = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)(a2 + 16), &v21);
  v5 = v13;
  if ( v13 < 0 )
  {
    v7 = (unsigned int)v13;
    v8 = 488;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
      (const char *)v7,
      (int)sourceString);
    v9 = (WCHAR *)sourceString;
    v10 = sourceString == 0;
    sourceString = 0;
    if ( !v10 )
      MemoryFree(v9);
    goto LABEL_9;
  }
  v15 = (WCHAR *)sourceString;
  sourceString = 0;
  if ( v15 )
    MemoryFree(v15);
  if ( v18 )
    TraceLoggingCorrelationVector::`scalar deleting destructor'(v18, v14);
  v5 = 0;
LABEL_24:
  WindowsDeleteString(string);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180027b64  push    rbp
0x180027b66  push    rbx
0x180027b67  push    rsi
0x180027b68  push    rdi
0x180027b69  lea     rbp, [rsp-18h]
0x180027b6e  sub     rsp, 118h
0x180027b75  mov     rax, cs:__security_cookie
0x180027b7c  xor     rax, rsp
0x180027b7f  mov     [rbp+30h+var_30], rax
0x180027b83  mov     rdi, rdx
0x180027b86  xor     esi, esi
0x180027b88  mov     [rsp+130h+string], rsi
0x180027b8d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180027b94  mov     ecx, 90h; unsigned __int64
0x180027b99  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180027b9e  mov     [rsp+130h+var_F0], rax
0x180027ba3  test    rax, rax
0x180027ba6  jz      loc_180027D29
0x180027bac  mov     rcx, rax
0x180027baf  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x180027bb4  mov     [rsp+130h+var_108], rax
0x180027bb9  test    rax, rax
0x180027bbc  jz      loc_180027D2E
0x180027bc2  lea     rcx, [rsp+130h+var_108]
0x180027bc7  mov     [rsp+130h+var_F0], rcx
0x180027bcc  mov     [rsp+130h+var_E8], 1
0x180027bd1  mov     edx, esi
0x180027bd3  lock xadd [rax+88h], rdx; unsigned __int64
0x180027bdc  lea     r8, [rsp+130h+var_C0]; char *
0x180027be1  mov     rcx, rax; this
0x180027be4  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x180027be9  test    al, al
0x180027beb  jnz     short loc_180027C0C
0x180027bed  mov     rcx, [rbp+38h]; this
0x180027bf1  mov     ebx, 80004005h
0x180027bf6  mov     r9d, ebx; char *
0x180027bf9  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180027c00  mov     edx, 1E1h; void *
0x180027c05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027c0a  jmp     short loc_180027C81
0x180027c0c  mov     [rsp+130h+sourceString], rsi; int
0x180027c11  mov     [rsp+130h+var_F8], esi
0x180027c15  lea     rax, [rsp+130h+sourceString]
0x180027c1a  mov     [rsp+130h+var_E0], rax
0x180027c1f  mov     [rsp+130h+var_D8], rsi
0x180027c24  mov     [rsp+130h+var_D0], 1
0x180027c29  lea     r9, [rsp+130h+var_F8]
0x180027c2e  lea     r8, [rsp+130h+var_D8]
0x180027c33  mov     edx, 0FDE9h
0x180027c38  lea     rcx, [rsp+130h+var_C0]
0x180027c3d  call    cs:__imp_?MBToUnicode@@YAJPEBDIPEAPEAGPEAK@Z; MBToUnicode(char const *,uint,ushort * *,ulong *)
0x180027c43  mov     ebx, eax
0x180027c45  lea     rcx, [rsp+130h+var_E0]
0x180027c4a  call    ??1?$out_param_t@V?$unique_ptr@GUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>(void)
0x180027c4f  test    ebx, ebx
0x180027c51  jns     short loc_180027C99
0x180027c53  mov     r9d, ebx; char *
0x180027c56  mov     edx, 1E6h; void *
0x180027c5b  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180027c62  mov     rcx, [rbp+38h]; this
0x180027c66  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027c6b  nop
0x180027c6c  mov     rcx, [rsp+130h+sourceString]; void *
0x180027c71  test    rcx, rcx
0x180027c74  mov     [rsp+130h+sourceString], rsi
0x180027c79  jz      short loc_180027C81
0x180027c7b  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x180027c80  nop
0x180027c81  mov     rcx, [rsp+130h+var_108]; this
0x180027c86  test    rcx, rcx
0x180027c89  jz      loc_180027D4C
0x180027c8f  call    ??_GTraceLoggingCorrelationVector@@QEAAPEAXI@Z; TraceLoggingCorrelationVector::`scalar deleting destructor'(uint)
0x180027c94  jmp     loc_180027D4C
0x180027c99  mov     rcx, [rsp+130h+string]; string
0x180027c9e  call    cs:__imp_WindowsDeleteString
0x180027ca4  mov     [rsp+130h+string], rsi
0x180027ca9  mov     rcx, [rsp+130h+sourceString]; sourceString
0x180027cae  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180027cb2  inc     rdx; length
0x180027cb5  cmp     [rcx+rdx*2], si
0x180027cb9  jnz     short loc_180027CB2
0x180027cbb  lea     r8, [rsp+130h+string]; string
0x180027cc0  call    cs:__imp_WindowsCreateString
0x180027cc6  mov     ebx, eax
0x180027cc8  test    eax, eax
0x180027cca  jns     short loc_180027CD6
0x180027ccc  mov     r9d, eax
0x180027ccf  mov     edx, 1E7h
0x180027cd4  jmp     short loc_180027C5B
0x180027cd6  mov     rax, [rsp+130h+string]
0x180027cdb  mov     [rsp+130h+var_F0], rax
0x180027ce0  lea     rcx, [rdi+10h]; newString
0x180027ce4  lea     rdx, [rsp+130h+var_F0]; HSTRING *
0x180027ce9  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180027cee  mov     ebx, eax
0x180027cf0  test    eax, eax
0x180027cf2  jns     short loc_180027D01
0x180027cf4  mov     r9d, eax
0x180027cf7  mov     edx, 1E8h
0x180027cfc  jmp     loc_180027C5B
0x180027d01  mov     rcx, [rsp+130h+sourceString]; void *
0x180027d06  mov     [rsp+130h+sourceString], rsi
0x180027d0b  test    rcx, rcx
0x180027d0e  jz      short loc_180027D16
0x180027d10  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x180027d15  nop
0x180027d16  mov     rcx, [rsp+130h+var_108]; this
0x180027d1b  test    rcx, rcx
0x180027d1e  jz      short loc_180027D25
0x180027d20  call    ??_GTraceLoggingCorrelationVector@@QEAAPEAXI@Z; TraceLoggingCorrelationVector::`scalar deleting destructor'(uint)
0x180027d25  mov     ebx, esi
0x180027d27  jmp     short loc_180027D4C
0x180027d29  mov     [rsp+130h+var_108], rsi
0x180027d2e  mov     rcx, [rbp+38h]; this
0x180027d32  mov     ebx, 80004005h
0x180027d37  mov     r9d, ebx; char *
0x180027d3a  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180027d41  mov     edx, 1DCh; void *
0x180027d46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027d4b  nop
0x180027d4c  mov     rcx, [rsp+130h+string]; string
0x180027d51  call    cs:__imp_WindowsDeleteString
0x180027d57  mov     eax, ebx
0x180027d59  mov     rcx, [rbp+30h+var_30]
0x180027d5d  xor     rcx, rsp; StackCookie
0x180027d60  call    __security_check_cookie
0x180027d65  add     rsp, 118h
0x180027d6c  pop     rdi
0x180027d6d  pop     rsi
0x180027d6e  pop     rbx
0x180027d6f  pop     rbp
0x180027d70  retn
```
