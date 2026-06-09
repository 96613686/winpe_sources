# CloudPrint::MopriaJsonParser::ExtractPrinterDetailsObject(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>,Windows::Data::Json::IJsonObject * *)

- ea: `0x18001f554`
- end: `0x18001f752`
- name: `?ExtractPrinterDetailsObject@MopriaJsonParser@CloudPrint@@SAJV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEAPEAUIJsonObject@Json@Data@Windows@@@Z`
- size: `510`
- prototype: `__int64 __fastcall(__int64 *, _QWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001f9a4`

## callees

- `0x180003a60`
- `0x180009fc0`
- `0x18000c4cc`
- `0x18000f7a4`
- `0x180012700`
- `0x18001bfe4`
- `0x18001ea14`
- `0x18001f554`
- `0x18001f758`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall CloudPrint::MopriaJsonParser::ExtractPrinterDetailsObject(__int64 *a1, _QWORD *a2)
{
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, _QWORD, _QWORD); // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  unsigned int i; // esi
  __int64 (__fastcall ***v11)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v12)(_QWORD, GUID *, __int64); // rbx
  __int64 v13; // rdi
  int (__fastcall *v14)(__int64, _QWORD, __int64 *); // rbx
  __int64 v15; // rax
  unsigned int v17; // [rsp+20h] [rbp-79h] BYREF
  __int64 v18; // [rsp+28h] [rbp-71h] BYREF
  __int64 (__fastcall ***v19)(_QWORD, GUID *, __int64); // [rsp+30h] [rbp-69h] BYREF
  __int64 v20; // [rsp+38h] [rbp-61h] BYREF
  _QWORD v21[2]; // [rsp+40h] [rbp-59h] BYREF
  _BYTE v22[80]; // [rsp+50h] [rbp-49h] BYREF
  _BYTE v23[32]; // [rsp+A0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v21[1] = a1;
  CloudPrintHelperTelemetry::WatchCurrentThread(v22, "ExtractPrinterDetailsObject");
  *a2 = 0;
  v17 = 0;
  v19 = 0;
  v21[0] = 0;
  v20 = 0;
  v18 = 0;
  v4 = *a1;
  v5 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)*a1 + 72LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  v6 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v23, off_18003F130);
  v7 = v5(v4, *(_QWORD *)(v6 + 24), &v19);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v7 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(
           &v19,
           (__int64)v21);
    v8 = v7;
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(*(_QWORD *)v21[0] + 56LL))(v21[0], &v17);
      v8 = v7;
      if ( v7 >= 0 )
      {
        for ( i = 0; ; ++i )
        {
          if ( i >= v17 )
            goto LABEL_14;
          v11 = v19;
          v12 = (*v19)[6];
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
          v7 = v12(v11, (GUID *)i, (__int64)&v20);
          v8 = v7;
          if ( v7 < 0 )
            break;
          v13 = v20;
          v14 = *(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v20 + 64LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
          v15 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v23, off_18003F108);
          if ( v14(v13, *(_QWORD *)(v15 + 24), &v18) >= 0 )
          {
            Microsoft::WRL::ComPtr<McpService>::InternalAddRef(&v18);
            *a2 = v18;
LABEL_14:
            v8 = 0;
            goto LABEL_15;
          }
        }
        v9 = 509;
      }
      else
      {
        v9 = 503;
      }
    }
    else
    {
      v9 = 502;
    }
  }
  else
  {
    v9 = 501;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\util\\cloudprinthelperutil.cpp",
    (const char *)(unsigned int)v7,
    v17);
LABEL_15:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v21);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v22);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1);
  return v8;
}

```

## disassembly

```asm
0x18001f554  mov     [rsp-8+arg_10], rbx
0x18001f559  push    rbp
0x18001f55a  push    rsi
0x18001f55b  push    rdi
0x18001f55c  push    r14
0x18001f55e  push    r15
0x18001f560  lea     rbp, [rsp-37h]
0x18001f565  sub     rsp, 0D0h
0x18001f56c  mov     rax, cs:__security_cookie
0x18001f573  xor     rax, rsp
0x18001f576  mov     [rbp+57h+var_30], rax
0x18001f57a  mov     r15, rdx
0x18001f57d  mov     r14, rcx
0x18001f580  mov     [rbp+57h+var_A8], rcx
0x18001f584  lea     rdx, aExtractprinter; "ExtractPrinterDetailsObject"
0x18001f58b  lea     rcx, [rbp+57h+var_A0]
0x18001f58f  call    ?WatchCurrentThread@CloudPrintHelperTelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; CloudPrintHelperTelemetry::WatchCurrentThread(char const *)
0x18001f594  nop
0x18001f595  mov     qword ptr [r15], 0
0x18001f59c  mov     [rbp+57h+var_D0], 0
0x18001f5a3  mov     [rbp+57h+var_C0], 0
0x18001f5ab  mov     [rbp+57h+var_B0], 0
0x18001f5b3  mov     [rbp+57h+var_B8], 0
0x18001f5bb  mov     [rbp+57h+var_C8], 0
0x18001f5c3  mov     rdi, [r14]
0x18001f5c6  mov     rax, [rdi]
0x18001f5c9  mov     rbx, [rax+48h]
0x18001f5cd  lea     rcx, [rbp+57h+var_C0]
0x18001f5d1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f5d6  lea     rdx, off_18003F130; "details"
0x18001f5dd  lea     rcx, [rbp+57h+var_50]
0x18001f5e1  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001f5e6  nop
0x18001f5e7  lea     r8, [rbp+57h+var_C0]
0x18001f5eb  mov     rdx, [rax+18h]
0x18001f5ef  mov     rcx, rdi
0x18001f5f2  mov     rax, rbx
0x18001f5f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f5fa  mov     ebx, eax
0x18001f5fc  test    eax, eax
0x18001f5fe  jns     short loc_18001F607
0x18001f600  mov     edx, 1F5h
0x18001f605  jmp     short loc_18001F61F
0x18001f607  lea     rdx, [rbp+57h+var_B0]
0x18001f60b  lea     rcx, [rbp+57h+var_C0]
0x18001f60f  call    ??$As@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>>)
0x18001f614  mov     ebx, eax
0x18001f616  test    eax, eax
0x18001f618  jns     short loc_18001F637
0x18001f61a  mov     edx, 1F6h; void *
0x18001f61f  lea     r8, aOnecoreuapPrin_1; "onecoreuap\\printscan\\print\\shared\\c"...
0x18001f626  mov     r9d, eax; char *
0x18001f629  mov     rcx, [rbp+5Fh]; this
0x18001f62d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f632  jmp     loc_18001F6E8
0x18001f637  mov     rcx, [rbp+57h+var_B0]
0x18001f63b  mov     rax, [rcx]
0x18001f63e  lea     rdx, [rbp+57h+var_D0]
0x18001f642  mov     rax, [rax+38h]
0x18001f646  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f64b  mov     ebx, eax
0x18001f64d  test    eax, eax
0x18001f64f  jns     short loc_18001F658
0x18001f651  mov     edx, 1F7h
0x18001f656  jmp     short loc_18001F61F
0x18001f658  xor     esi, esi
0x18001f65a  cmp     esi, [rbp+57h+var_D0]
0x18001f65d  jnb     loc_18001F6E6
0x18001f663  mov     rdi, [rbp+57h+var_C0]
0x18001f667  mov     rax, [rdi]
0x18001f66a  mov     rbx, [rax+30h]
0x18001f66e  lea     rcx, [rbp+57h+var_B8]
0x18001f672  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f677  lea     r8, [rbp+57h+var_B8]
0x18001f67b  mov     edx, esi
0x18001f67d  mov     rcx, rdi
0x18001f680  mov     rax, rbx
0x18001f683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f688  mov     ebx, eax
0x18001f68a  test    eax, eax
0x18001f68c  js      loc_18001F747
0x18001f692  mov     rdi, [rbp+57h+var_B8]
0x18001f696  mov     rax, [rdi]
0x18001f699  mov     rbx, [rax+40h]
0x18001f69d  lea     rcx, [rbp+57h+var_C8]
0x18001f6a1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f6a6  lea     rdx, off_18003F108; "printer"
0x18001f6ad  lea     rcx, [rbp+57h+var_50]
0x18001f6b1  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001f6b6  nop
0x18001f6b7  lea     r8, [rbp+57h+var_C8]
0x18001f6bb  mov     rdx, [rax+18h]
0x18001f6bf  mov     rcx, rdi
0x18001f6c2  mov     rax, rbx
0x18001f6c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f6ca  nop
0x18001f6cb  shr     eax, 1Fh
0x18001f6ce  xor     al, 1
0x18001f6d0  jnz     short loc_18001F6D6
0x18001f6d2  inc     esi
0x18001f6d4  jmp     short loc_18001F65A
0x18001f6d6  lea     rcx, [rbp+57h+var_C8]
0x18001f6da  call    ?InternalAddRef@?$ComPtr@VMcpService@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<McpService>::InternalAddRef(void)
0x18001f6df  mov     rax, [rbp+57h+var_C8]
0x18001f6e3  mov     [r15], rax
0x18001f6e6  xor     ebx, ebx
0x18001f6e8  lea     rcx, [rbp+57h+var_C8]
0x18001f6ec  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f6f1  nop
0x18001f6f2  lea     rcx, [rbp+57h+var_B8]
0x18001f6f6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f6fb  nop
0x18001f6fc  lea     rcx, [rbp+57h+var_B0]
0x18001f700  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f705  nop
0x18001f706  lea     rcx, [rbp+57h+var_C0]
0x18001f70a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f70f  nop
0x18001f710  lea     rcx, [rbp+57h+var_A0]; this
0x18001f714  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x18001f719  nop
0x18001f71a  mov     rcx, r14
0x18001f71d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f722  mov     eax, ebx
0x18001f724  mov     rcx, [rbp+57h+var_30]
0x18001f728  xor     rcx, rsp; StackCookie
0x18001f72b  call    __security_check_cookie
0x18001f730  mov     rbx, [rsp+0F0h+arg_10]
0x18001f738  add     rsp, 0D0h
0x18001f73f  pop     r15
0x18001f741  pop     r14
0x18001f743  pop     rdi
0x18001f744  pop     rsi
0x18001f745  pop     rbp
0x18001f746  retn
0x18001f747  mov     edx, 1FDh
0x18001f74c  jmp     loc_18001F61F
```
