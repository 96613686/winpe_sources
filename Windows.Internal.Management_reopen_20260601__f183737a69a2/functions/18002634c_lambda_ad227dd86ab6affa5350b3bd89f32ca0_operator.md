# _lambda_ad227dd86ab6affa5350b3bd89f32ca0_::operator()

- ea: `0x18002634c`
- end: `0x180026575`
- name: `_lambda_ad227dd86ab6affa5350b3bd89f32ca0_::operator()`
- size: `553`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180033d90`

## callees

- `0x180004eb0`
- `0x1800053e0`
- `0x180008fe4`
- `0x18000a5c4`
- `0x180020cb0`
- `0x1800232b8`
- `0x18002634c`
- `0x1800285cc`
- `0x180034088`
- `0x180036d48`

## import_xrefs

- `DMCmnUtils!MBToUnicode` at `0x180026425`
- `DMCmnUtils!MBToUnicode` at `0x180026425`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002648c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002654e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002648c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002654e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800264b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800264b4`

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
0x18002634c  push    rbp
0x18002634e  push    rbx
0x18002634f  push    rsi
0x180026350  push    rdi
0x180026351  lea     rbp, [rsp-18h]
0x180026356  sub     rsp, 118h
0x18002635d  mov     rax, cs:__security_cookie
0x180026364  xor     rax, rsp
0x180026367  mov     [rbp+30h+var_30], rax
0x18002636b  mov     rdi, rdx
0x18002636e  xor     esi, esi
0x180026370  mov     [rsp+130h+string], rsi
0x180026375  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002637c  mov     ecx, 90h; unsigned __int64
0x180026381  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180026386  mov     [rsp+130h+var_F0], rax
0x18002638b  test    rax, rax
0x18002638e  jz      loc_180026526
0x180026394  mov     rcx, rax
0x180026397  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x18002639c  mov     [rsp+130h+var_108], rax
0x1800263a1  test    rax, rax
0x1800263a4  jz      loc_18002652B
0x1800263aa  lea     rcx, [rsp+130h+var_108]
0x1800263af  mov     [rsp+130h+var_F0], rcx
0x1800263b4  mov     [rsp+130h+var_E8], 1
0x1800263b9  mov     edx, esi
0x1800263bb  lock xadd [rax+88h], rdx; unsigned __int64
0x1800263c4  lea     r8, [rsp+130h+var_C0]; char *
0x1800263c9  mov     rcx, rax; this
0x1800263cc  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x1800263d1  test    al, al
0x1800263d3  jnz     short loc_1800263F4
0x1800263d5  mov     rcx, [rbp+38h]; this
0x1800263d9  mov     ebx, 80004005h
0x1800263de  mov     r9d, ebx; char *
0x1800263e1  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800263e8  mov     edx, 1E1h; void *
0x1800263ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800263f2  jmp     short loc_18002646F
0x1800263f4  mov     [rsp+130h+sourceString], rsi; int
0x1800263f9  mov     [rsp+130h+var_F8], esi
0x1800263fd  lea     rax, [rsp+130h+sourceString]
0x180026402  mov     [rsp+130h+var_E0], rax
0x180026407  mov     [rsp+130h+var_D8], rsi
0x18002640c  mov     [rsp+130h+var_D0], 1
0x180026411  lea     r9, [rsp+130h+var_F8]
0x180026416  lea     r8, [rsp+130h+var_D8]
0x18002641b  mov     edx, 0FDE9h
0x180026420  lea     rcx, [rsp+130h+var_C0]
0x180026425  call    cs:__imp_?MBToUnicode@@YAJPEBDIPEAPEAGPEAK@Z; MBToUnicode(char const *,uint,ushort * *,ulong *)
0x18002642c  nop     dword ptr [rax+rax+00h]
0x180026431  mov     ebx, eax
0x180026433  lea     rcx, [rsp+130h+var_E0]
0x180026438  call    ??1?$out_param_t@V?$unique_ptr@GUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>(void)
0x18002643d  test    ebx, ebx
0x18002643f  jns     short loc_180026487
0x180026441  mov     r9d, ebx; char *
0x180026444  mov     edx, 1E6h; void *
0x180026449  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180026450  mov     rcx, [rbp+38h]; this
0x180026454  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026459  nop
0x18002645a  mov     rcx, [rsp+130h+sourceString]; void *
0x18002645f  test    rcx, rcx
0x180026462  mov     [rsp+130h+sourceString], rsi
0x180026467  jz      short loc_18002646F
0x180026469  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18002646e  nop
0x18002646f  mov     rcx, [rsp+130h+var_108]; this
0x180026474  test    rcx, rcx
0x180026477  jz      loc_180026549
0x18002647d  call    ??_GTraceLoggingCorrelationVector@@QEAAPEAXI@Z; TraceLoggingCorrelationVector::`scalar deleting destructor'(uint)
0x180026482  jmp     loc_180026549
0x180026487  mov     rcx, [rsp+130h+string]; string
0x18002648c  call    cs:__imp_WindowsDeleteString
0x180026493  nop     dword ptr [rax+rax+00h]
0x180026498  mov     [rsp+130h+string], rsi
0x18002649d  mov     rcx, [rsp+130h+sourceString]; sourceString
0x1800264a2  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800264a6  inc     rdx; length
0x1800264a9  cmp     [rcx+rdx*2], si
0x1800264ad  jnz     short loc_1800264A6
0x1800264af  lea     r8, [rsp+130h+string]; string
0x1800264b4  call    cs:__imp_WindowsCreateString
0x1800264bb  nop     dword ptr [rax+rax+00h]
0x1800264c0  mov     ebx, eax
0x1800264c2  test    eax, eax
0x1800264c4  jns     short loc_1800264D3
0x1800264c6  mov     r9d, eax
0x1800264c9  mov     edx, 1E7h
0x1800264ce  jmp     loc_180026449
0x1800264d3  mov     rax, [rsp+130h+string]
0x1800264d8  mov     [rsp+130h+var_F0], rax
0x1800264dd  lea     rcx, [rdi+10h]; newString
0x1800264e1  lea     rdx, [rsp+130h+var_F0]; HSTRING *
0x1800264e6  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1800264eb  mov     ebx, eax
0x1800264ed  test    eax, eax
0x1800264ef  jns     short loc_1800264FE
0x1800264f1  mov     r9d, eax
0x1800264f4  mov     edx, 1E8h
0x1800264f9  jmp     loc_180026449
0x1800264fe  mov     rcx, [rsp+130h+sourceString]; void *
0x180026503  mov     [rsp+130h+sourceString], rsi
0x180026508  test    rcx, rcx
0x18002650b  jz      short loc_180026513
0x18002650d  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x180026512  nop
0x180026513  mov     rcx, [rsp+130h+var_108]; this
0x180026518  test    rcx, rcx
0x18002651b  jz      short loc_180026522
0x18002651d  call    ??_GTraceLoggingCorrelationVector@@QEAAPEAXI@Z; TraceLoggingCorrelationVector::`scalar deleting destructor'(uint)
0x180026522  mov     ebx, esi
0x180026524  jmp     short loc_180026549
0x180026526  mov     [rsp+130h+var_108], rsi
0x18002652b  mov     rcx, [rbp+38h]; this
0x18002652f  mov     ebx, 80004005h
0x180026534  mov     r9d, ebx; char *
0x180026537  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18002653e  mov     edx, 1DCh; void *
0x180026543  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026548  nop
0x180026549  mov     rcx, [rsp+130h+string]; string
0x18002654e  call    cs:__imp_WindowsDeleteString
0x180026555  nop     dword ptr [rax+rax+00h]
0x18002655a  mov     eax, ebx
0x18002655c  mov     rcx, [rbp+30h+var_30]
0x180026560  xor     rcx, rsp; StackCookie
0x180026563  call    __security_check_cookie
0x180026568  add     rsp, 118h
0x18002656f  pop     rdi
0x180026570  pop     rsi
0x180026571  pop     rbx
0x180026572  pop     rbp
0x180026573  retn
```
