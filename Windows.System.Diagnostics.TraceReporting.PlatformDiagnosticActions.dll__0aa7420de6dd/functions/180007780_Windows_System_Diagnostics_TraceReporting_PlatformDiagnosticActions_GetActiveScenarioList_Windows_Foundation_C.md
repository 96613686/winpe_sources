# Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticActions::GetActiveScenarioList(Windows::Foundation::Collections::IVectorView<_GUID> * *)

- ea: `0x180007780`
- end: `0x180007a96`
- name: `?GetActiveScenarioList@PlatformDiagnosticActions@TraceReporting@Diagnostics@System@Windows@@UEAAJPEAPEAU?$IVectorView@U_GUID@@@Collections@Foundation@5@@Z`
- size: `790`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800016a0`
- `0x180001a70`
- `0x180004bc4`
- `0x18000710c`
- `0x180007780`
- `0x180008a10`
- `0x180009b30`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000781f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000781f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000783e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000783e`

## pseudocode

```c
__int64 __fastcall Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticActions::GetActiveScenarioList(
        __int64 a1,
        __int64 a2)
{
  __int64 result; // rax
  unsigned __int64 v4; // rdx
  int ActiveScenarioList; // esi
  unsigned int v6; // r8d
  const char *v7; // r9
  HRESULT v8; // eax
  int v9; // edx
  unsigned int v10; // r8d
  int ActivationFactory; // ebx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rcx
  unsigned __int64 v17; // rdx
  unsigned int i; // ebx
  int v19; // eax
  unsigned int v20; // edi
  unsigned __int64 v21; // rdx
  int v22; // eax
  unsigned int v23; // ebx
  unsigned __int64 v24; // rdx
  int v25; // [rsp+20h] [rbp-78h]
  int v26[2]; // [rsp+20h] [rbp-78h]
  int v27[2]; // [rsp+20h] [rbp-78h]
  int v28[2]; // [rsp+20h] [rbp-78h]
  int v29[2]; // [rsp+20h] [rbp-78h]
  __int64 v30; // [rsp+28h] [rbp-70h] BYREF
  void *v31; // [rsp+30h] [rbp-68h] BYREF
  unsigned int v32; // [rsp+38h] [rbp-60h]
  int v33[4]; // [rsp+40h] [rbp-58h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-48h] BYREF
  HSTRING string; // [rsp+68h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x136,
      (unsigned int)"onecoreuap\\base\\telemetry\\utcapi\\winrt\\lib\\platformdiagnosticactionsimpl.cpp",
      (const char *)0x80004003LL,
      v25);
    return 2147500035LL;
  }
  try
  {
    v31 = 0;
    v32 = 0;
    ActiveScenarioList = Microsoft::Diagnostics::UtcApiWrapper::GetActiveScenarioList(
                           (Microsoft::Diagnostics::UtcApiWrapper *)(a1 + 56),
                           (struct Microsoft::Diagnostics::UtcApiWrapper::AutoScenarioList *)&v31);
    if ( ActiveScenarioList >= 0 )
    {
      *(_QWORD *)v26 = 0;
      v30 = 0;
      string = 0;
      v8 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &hstringHeader, &string);
      if ( v8 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v8, v9, v10);
        JUMPOUT(0x180007A94LL);
      }
      ActivationFactory = RoGetActivationFactory(string, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v30);
      if ( ActivationFactory >= 0 )
      {
        *(_QWORD *)v33 = 0;
        ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{224,{flat}}(v30, v33);
        if ( ActivationFactory >= 0 )
        {
          v15 = *(_QWORD *)v33;
          *(_QWORD *)v33 = 0;
          *(_QWORD *)v26 = v15;
          v16 = v30;
          if ( v30 )
          {
            v30 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
          }
          ActivationFactory = 0;
        }
        else
        {
          v13 = *(_QWORD *)v33;
          if ( *(_QWORD *)v33 )
          {
            *(_QWORD *)v33 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
          }
          v14 = v30;
          if ( v30 )
          {
            v30 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
          }
        }
      }
      else
      {
        v12 = v30;
        if ( v30 )
        {
          v30 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        }
      }
      if ( ActivationFactory < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x13E,
          (unsigned int)"onecoreuap\\base\\telemetry\\utcapi\\winrt\\lib\\platformdiagnosticactionsimpl.cpp",
          (const char *)(unsigned int)ActivationFactory,
          v26[0]);
        if ( *(_QWORD *)v27 )
          (*(void (__fastcall **)(int *))(**(_QWORD **)v27 + 16LL))(*(int **)v27);
        if ( v31 )
          operator delete(v31, v17);
        return (unsigned int)ActivationFactory;
      }
      for ( i = 0; i < v32; ++i )
      {
        *(_OWORD *)v33 = *((_OWORD *)v31 + i);
        v19 = (*(__int64 (__fastcall **)(int *, int *))(**(_QWORD **)v26 + 104LL))(*(int **)v26, v33);
        v20 = v19;
        if ( v19 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x142,
            (unsigned int)"onecoreuap\\base\\telemetry\\utcapi\\winrt\\lib\\platformdiagnosticactionsimpl.cpp",
            (const char *)(unsigned int)v19,
            v26[0]);
          if ( *(_QWORD *)v28 )
            (*(void (__fastcall **)(int *))(**(_QWORD **)v28 + 16LL))(*(int **)v28);
          if ( v31 )
            operator delete(v31, v21);
          return v20;
        }
      }
      v22 = (*(__int64 (__fastcall **)(int *, __int64))(**(_QWORD **)v26 + 64LL))(*(int **)v26, a2);
      v23 = v22;
      if ( v22 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x145,
          (unsigned int)"onecoreuap\\base\\telemetry\\utcapi\\winrt\\lib\\platformdiagnosticactionsimpl.cpp",
          (const char *)(unsigned int)v22,
          v26[0]);
        if ( *(_QWORD *)v29 )
          (*(void (__fastcall **)(int *))(**(_QWORD **)v29 + 16LL))(*(int **)v29);
        if ( v31 )
          operator delete(v31, v24);
        return v23;
      }
      if ( *(_QWORD *)v26 )
        (*(void (__fastcall **)(int *))(**(_QWORD **)v26 + 16LL))(*(int **)v26);
    }
    if ( v31 )
      operator delete(v31, v4);
    result = (unsigned int)ActiveScenarioList;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x14A, v6, v7);
  }
  return result;
}

```

## disassembly

```asm
0x180007780  mov     [rsp+arg_10], rbx
0x180007785  mov     [rsp+arg_18], rsi
0x18000778a  push    rdi
0x18000778b  push    r14
0x18000778d  push    r15
0x18000778f  sub     rsp, 80h
0x180007796  mov     rax, cs:__security_cookie
0x18000779d  xor     rax, rsp
0x1800077a0  mov     [rsp+98h+var_28], rax
0x1800077a5  mov     r14, rdx
0x1800077a8  xor     r15d, r15d
0x1800077ab  test    rdx, rdx
0x1800077ae  jnz     short loc_1800077D8
0x1800077b0  mov     rcx, [rsp+98h]; this
0x1800077b8  mov     ebx, 80004003h
0x1800077bd  mov     r9d, ebx; char *
0x1800077c0  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\telemetry\\utcapi\\wi"...
0x1800077c7  mov     edx, 136h; void *
0x1800077cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800077d1  mov     eax, ebx
0x1800077d3  jmp     loc_180007A67
0x1800077d8  mov     [rsp+98h+var_68], r15
0x1800077dd  mov     [rsp+98h+var_60], r15d
0x1800077e2  add     rcx, 38h ; '8'; this
0x1800077e6  lea     rdx, [rsp+98h+var_68]; struct Microsoft::Diagnostics::UtcApiWrapper::AutoScenarioList *
0x1800077eb  call    ?GetActiveScenarioList@UtcApiWrapper@Diagnostics@Microsoft@@QEBAJAEAVAutoScenarioList@123@@Z; Microsoft::Diagnostics::UtcApiWrapper::GetActiveScenarioList(Microsoft::Diagnostics::UtcApiWrapper::AutoScenarioList &)
0x1800077f0  mov     esi, eax
0x1800077f2  test    eax, eax
0x1800077f4  js      loc_180007A50
0x1800077fa  mov     qword ptr [rsp+98h+var_78], r15
0x1800077ff  mov     [rsp+98h+var_70], r15
0x180007804  mov     [rsp+98h+string], r15
0x180007809  lea     r9, [rsp+98h+string]; string
0x18000780e  lea     r8, [rsp+98h+hstringHeader]; hstringHeader
0x180007813  mov     edx, 2Ch ; ','; length
0x180007818  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x18000781f  call    cs:__imp_WindowsCreateStringReference
0x180007825  test    eax, eax
0x180007827  js      loc_180007A8D
0x18000782d  lea     r8, [rsp+98h+var_70]
0x180007832  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x180007839  mov     rcx, [rsp+98h+string]
0x18000783e  call    cs:__imp_RoGetActivationFactory
0x180007844  mov     ebx, eax
0x180007846  test    eax, eax
0x180007848  jns     short loc_18000786B
0x18000784a  mov     rcx, [rsp+98h+var_70]
0x18000784f  test    rcx, rcx
0x180007852  jz      short loc_180007866
0x180007854  mov     [rsp+98h+var_70], r15
0x180007859  mov     rax, [rcx]
0x18000785c  mov     rax, [rax+10h]
0x180007860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007865  nop
0x180007866  jmp     loc_1800078ED
0x18000786b  mov     qword ptr [rsp+98h+var_58], r15
0x180007870  lea     rdx, [rsp+98h+var_58]
0x180007875  mov     rcx, [rsp+98h+var_70]
0x18000787a  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BOA@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{224,{flat}}
0x18000787f  mov     ebx, eax
0x180007881  test    eax, eax
0x180007883  jns     short loc_1800078BF
0x180007885  mov     rcx, qword ptr [rsp+98h+var_58]
0x18000788a  test    rcx, rcx
0x18000788d  jz      short loc_1800078A1
0x18000788f  mov     qword ptr [rsp+98h+var_58], r15
0x180007894  mov     rax, [rcx]
0x180007897  mov     rax, [rax+10h]
0x18000789b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078a0  nop
0x1800078a1  mov     rcx, [rsp+98h+var_70]
0x1800078a6  test    rcx, rcx
0x1800078a9  jz      short loc_1800078BD
0x1800078ab  mov     [rsp+98h+var_70], r15
0x1800078b0  mov     rax, [rcx]
0x1800078b3  mov     rax, [rax+10h]
0x1800078b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078bc  nop
0x1800078bd  jmp     short loc_1800078ED
0x1800078bf  mov     rax, qword ptr [rsp+98h+var_58]
0x1800078c4  mov     qword ptr [rsp+98h+var_58], r15
0x1800078c9  mov     qword ptr [rsp+98h+var_78], rax; int
0x1800078ce  mov     rcx, [rsp+98h+var_70]
0x1800078d3  test    rcx, rcx
0x1800078d6  jz      short loc_1800078EA
0x1800078d8  mov     [rsp+98h+var_70], r15
0x1800078dd  mov     rax, [rcx]
0x1800078e0  mov     rax, [rax+10h]
0x1800078e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078e9  nop
0x1800078ea  mov     ebx, r15d
0x1800078ed  test    ebx, ebx
0x1800078ef  jns     short loc_180007940
0x1800078f1  mov     rcx, [rsp+98h]; this
0x1800078f9  mov     r9d, ebx; char *
0x1800078fc  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\telemetry\\utcapi\\wi"...
0x180007903  mov     edx, 13Eh; void *
0x180007908  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000790d  nop
0x18000790e  mov     rcx, qword ptr [rsp+98h+var_78]
0x180007913  test    rcx, rcx
0x180007916  jz      short loc_18000792A
0x180007918  mov     qword ptr [rsp+98h+var_78], r15
0x18000791d  mov     rax, [rcx]
0x180007920  mov     rax, [rax+10h]
0x180007924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007929  nop
0x18000792a  mov     rcx, [rsp+98h+var_68]; void *
0x18000792f  test    rcx, rcx
0x180007932  jz      short loc_180007939
0x180007934  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007939  mov     eax, ebx
0x18000793b  jmp     loc_180007A67
0x180007940  mov     ebx, r15d
0x180007943  mov     rcx, qword ptr [rsp+98h+var_78]
0x180007948  cmp     ebx, [rsp+98h+var_60]
0x18000794c  jnb     loc_1800079D3
0x180007952  mov     edx, ebx
0x180007954  add     rdx, rdx
0x180007957  mov     rax, [rsp+98h+var_68]
0x18000795c  movups  xmm0, xmmword ptr [rax+rdx*8]
0x180007960  movdqu  xmmword ptr [rsp+98h+var_58], xmm0
0x180007966  mov     rax, [rcx]
0x180007969  lea     rdx, [rsp+98h+var_58]
0x18000796e  mov     rax, [rax+68h]
0x180007972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007977  mov     edi, eax
0x180007979  test    eax, eax
0x18000797b  jns     short loc_1800079CC
0x18000797d  mov     rcx, [rsp+98h]; this
0x180007985  mov     r9d, eax; char *
0x180007988  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\telemetry\\utcapi\\wi"...
0x18000798f  mov     edx, 142h; void *
0x180007994  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007999  nop
0x18000799a  mov     rcx, qword ptr [rsp+98h+var_78]
0x18000799f  test    rcx, rcx
0x1800079a2  jz      short loc_1800079B6
0x1800079a4  mov     qword ptr [rsp+98h+var_78], r15
0x1800079a9  mov     rax, [rcx]
0x1800079ac  mov     rax, [rax+10h]
0x1800079b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079b5  nop
0x1800079b6  mov     rcx, [rsp+98h+var_68]; void *
0x1800079bb  test    rcx, rcx
0x1800079be  jz      short loc_1800079C5
0x1800079c0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800079c5  mov     eax, edi
0x1800079c7  jmp     loc_180007A67
0x1800079cc  inc     ebx
0x1800079ce  jmp     loc_180007943
0x1800079d3  mov     rax, [rcx]
0x1800079d6  mov     rdx, r14
0x1800079d9  mov     rax, [rax+40h]
0x1800079dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079e2  mov     ebx, eax
0x1800079e4  test    eax, eax
0x1800079e6  jns     short loc_180007A34
0x1800079e8  mov     rcx, [rsp+98h]; this
0x1800079f0  mov     r9d, eax; char *
0x1800079f3  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\telemetry\\utcapi\\wi"...
0x1800079fa  mov     edx, 145h; void *
0x1800079ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007a04  nop
0x180007a05  mov     rcx, qword ptr [rsp+98h+var_78]
0x180007a0a  test    rcx, rcx
0x180007a0d  jz      short loc_180007A21
0x180007a0f  mov     qword ptr [rsp+98h+var_78], r15
0x180007a14  mov     rax, [rcx]
0x180007a17  mov     rax, [rax+10h]
0x180007a1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a20  nop
0x180007a21  mov     rcx, [rsp+98h+var_68]; void *
0x180007a26  test    rcx, rcx
0x180007a29  jz      short loc_180007A30
0x180007a2b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007a30  mov     eax, ebx
0x180007a32  jmp     short loc_180007A67
0x180007a34  mov     rcx, qword ptr [rsp+98h+var_78]
0x180007a39  test    rcx, rcx
0x180007a3c  jz      short loc_180007A50
0x180007a3e  mov     qword ptr [rsp+98h+var_78], r15
0x180007a43  mov     rax, [rcx]
0x180007a46  mov     rax, [rax+10h]
0x180007a4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a4f  nop
0x180007a50  mov     rcx, [rsp+98h+var_68]; void *
0x180007a55  test    rcx, rcx
0x180007a58  jz      short loc_180007A5F
0x180007a5a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007a5f  mov     eax, esi
0x180007a61  jmp     short loc_180007A67
0x180007a63  mov     eax, [rsp+98h+var_78]
0x180007a67  mov     rcx, [rsp+98h+var_28]
0x180007a6c  xor     rcx, rsp; StackCookie
0x180007a6f  call    __security_check_cookie
0x180007a74  lea     r11, [rsp+98h+var_18]
0x180007a7c  mov     rbx, [r11+30h]
0x180007a80  mov     rsi, [r11+38h]
0x180007a84  mov     rsp, r11
0x180007a87  pop     r15
0x180007a89  pop     r14
0x180007a8b  pop     rdi
0x180007a8c  retn
0x180007a8d  mov     ecx, eax; this
0x180007a8f  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
