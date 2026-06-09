# winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::GetWcosJob(uint,winrt::com_ptr<IPrintServiceManagerJob> &)

- ea: `0x18004f68c`
- end: `0x18004f80c`
- name: `?GetWcosJob@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@YAXIAEAU?$com_ptr@UIPrintServiceManagerJob@@@7@@Z`
- size: `384`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18004f328`
- `0x18004f59c`

## callees

- `0x1800127a4`
- `0x1800147fc`
- `0x18004f050`
- `0x18004f68c`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004f6d7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004f6d7`

## string_xrefs

- `0x18004f6e8`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportjobhandler.cpp`
- `0x18004f721`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportjobhandler.cpp`
- `0x18004f7a2`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportjobhandler.cpp`
- `0x18004f7fa`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportjobhandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::GetWcosJob(
        int a1,
        _QWORD *a2)
{
  HRESULT v4; // eax
  int v5; // eax
  __int64 i; // r8
  __int128 v7; // xmm6
  __int128 v8; // xmm7
  int v9; // r14d
  LPVOID v10; // rdi
  __int64 (__fastcall *v11)(LPVOID, _OWORD *, _QWORD *); // rsi
  int v12; // eax
  __int64 result; // rax
  int ppv; // [rsp+20h] [rbp-60h]
  _OWORD v15[2]; // [rsp+30h] [rbp-50h] BYREF
  int v16; // [rsp+50h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  LPVOID v18; // [rsp+B0h] [rbp+30h] BYREF
  _DWORD *v19; // [rsp+B8h] [rbp+38h] BYREF

  v18 = 0;
  v4 = CoCreateInstance(
         &GUID_1d50fe53_6b4c_41b2_b06c_8b2c01a53bf3,
         0,
         4u,
         &GUID_200adcf9_0683_4b90_ac8e_09c590a3a112,
         &v18);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA0,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportjobhandler.cpp",
      (const char *)(unsigned int)v4,
      ppv);
  v19 = 0;
  v5 = (*(__int64 (__fastcall **)(LPVOID, _DWORD **))(*(_QWORD *)v18 + 72LL))(v18, &v19);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA3,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportjobhandler.cpp",
      (const char *)(unsigned int)v5,
      ppv);
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= *v19 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xAF,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportjobhandler.cpp",
        (const char *)0x80070490LL,
        ppv);
    v7 = *(_OWORD *)&v19[9 * i + 1];
    v8 = *(_OWORD *)&v19[9 * i + 5];
    v9 = v19[9 * i + 9];
    if ( v9 == a1 )
      break;
  }
  v10 = v18;
  v11 = *(__int64 (__fastcall **)(LPVOID, _OWORD *, _QWORD *))(*(_QWORD *)v18 + 80LL);
  if ( *a2 )
    winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(a2);
  v15[0] = v7;
  v15[1] = v8;
  v16 = v9;
  v12 = v11(v10, v15, a2);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xAA,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportjobhandler.cpp",
      (const char *)(unsigned int)v12,
      ppv);
  result = CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v19);
  if ( v18 )
    return winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(&v18);
  return result;
}

```

## disassembly

```asm
0x18004f68c  mov     rax, rsp
0x18004f68f  mov     [rax+8], rbx
0x18004f693  mov     [rax+10h], rsi
0x18004f697  push    rbp
0x18004f698  push    rdi
0x18004f699  push    r14
0x18004f69b  mov     rbp, rsp
0x18004f69e  sub     rsp, 80h
0x18004f6a5  movaps  xmmword ptr [rax-28h], xmm6
0x18004f6a9  movaps  xmmword ptr [rax-38h], xmm7
0x18004f6ad  mov     rbx, rdx
0x18004f6b0  mov     edi, ecx
0x18004f6b2  mov     [rbp+arg_10], 0
0x18004f6ba  lea     rax, [rbp+arg_10]
0x18004f6be  mov     qword ptr [rsp+80h+ppv], rax; int
0x18004f6c3  lea     r9, _GUID_200adcf9_0683_4b90_ac8e_09c590a3a112; riid
0x18004f6ca  xor     edx, edx; pUnkOuter
0x18004f6cc  lea     r8d, [rdx+4]; dwClsContext
0x18004f6d0  lea     rcx, _GUID_1d50fe53_6b4c_41b2_b06c_8b2c01a53bf3; rclsid
0x18004f6d7  call    cs:__imp_CoCreateInstance
0x18004f6dd  mov     rcx, [rbp+18h]; this
0x18004f6e1  test    eax, eax
0x18004f6e3  jns     short loc_18004F6FA
0x18004f6e5  mov     r9d, eax; char *
0x18004f6e8  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\workflow"...
0x18004f6ef  mov     edx, 0A0h; void *
0x18004f6f4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004f6fa  mov     [rbp+arg_18], 0
0x18004f702  mov     rcx, [rbp+arg_10]
0x18004f706  mov     rax, [rcx]
0x18004f709  lea     rdx, [rbp+arg_18]
0x18004f70d  mov     rax, [rax+48h]
0x18004f711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f716  mov     rcx, [rbp+18h]; this
0x18004f71a  test    eax, eax
0x18004f71c  jns     short loc_18004F733
0x18004f71e  mov     r9d, eax; char *
0x18004f721  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\workflow"...
0x18004f728  mov     edx, 0A3h; void *
0x18004f72d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004f733  xor     r8d, r8d
0x18004f736  mov     rax, [rbp+arg_18]
0x18004f73a  cmp     r8d, [rax]
0x18004f73d  jnb     loc_18004F7F0
0x18004f743  lea     rdx, [r8+r8*8]
0x18004f747  movups  xmm6, xmmword ptr [rax+rdx*4+4]
0x18004f74c  movups  xmm7, xmmword ptr [rax+rdx*4+14h]
0x18004f751  mov     r14d, [rax+rdx*4+24h]
0x18004f756  cmp     r14d, edi
0x18004f759  jz      short loc_18004F760
0x18004f75b  inc     r8d
0x18004f75e  jmp     short loc_18004F73A
0x18004f760  mov     rdi, [rbp+arg_10]
0x18004f764  mov     rax, [rdi]
0x18004f767  mov     rsi, [rax+50h]
0x18004f76b  cmp     qword ptr [rbx], 0
0x18004f76f  jz      short loc_18004F779
0x18004f771  mov     rcx, rbx
0x18004f774  call    ?unconditional_release_ref@?$com_ptr@VProtocolActivatedEventArgsImpl@@@winrt@@AEAAXXZ; winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(void)
0x18004f779  movaps  [rbp+var_50], xmm6
0x18004f77d  movaps  [rbp+var_40], xmm7
0x18004f781  mov     [rbp+var_30], r14d
0x18004f785  mov     r8, rbx
0x18004f788  lea     rdx, [rbp+var_50]
0x18004f78c  mov     rcx, rdi
0x18004f78f  mov     rax, rsi
0x18004f792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f797  mov     rcx, [rbp+18h]; this
0x18004f79b  test    eax, eax
0x18004f79d  jns     short loc_18004F7B4
0x18004f79f  mov     r9d, eax; char *
0x18004f7a2  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\workflow"...
0x18004f7a9  mov     edx, 0AAh; void *
0x18004f7ae  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004f7b4  lea     rcx, [rbp+arg_18]
0x18004f7b8  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18004f7bd  nop
0x18004f7be  cmp     [rbp+arg_10], 0
0x18004f7c3  jz      short loc_18004F7CE
0x18004f7c5  lea     rcx, [rbp+arg_10]
0x18004f7c9  call    ?unconditional_release_ref@?$com_ptr@VProtocolActivatedEventArgsImpl@@@winrt@@AEAAXXZ; winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(void)
0x18004f7ce  lea     r11, [rsp+80h+var_s0]
0x18004f7d6  mov     rbx, [r11+20h]
0x18004f7da  mov     rsi, [r11+28h]
0x18004f7de  movaps  xmm6, [rsp+80h+var_10]
0x18004f7e3  movaps  xmm7, [rsp+80h+var_20]
0x18004f7e8  mov     rsp, r11
0x18004f7eb  pop     r14
0x18004f7ed  pop     rdi
0x18004f7ee  pop     rbp
0x18004f7ef  retn
0x18004f7f0  mov     rcx, [rbp+18h]; this
0x18004f7f4  mov     r9d, 80070490h; char *
0x18004f7fa  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\workflow"...
0x18004f801  mov     edx, 0AFh; void *
0x18004f806  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
