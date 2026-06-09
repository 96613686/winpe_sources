# PerformanceTraceHandler::GetTraceFolderPath(ushort * *)

- ea: `0x180011a84`
- end: `0x180011b75`
- name: `?GetTraceFolderPath@PerformanceTraceHandler@@AEAAJPEAPEAG@Z`
- size: `241`
- prototype: `__int64 __fastcall(PCWSTR *this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001124c`

## callees

- `0x180002c00`
- `0x180007f3c`
- `0x180010a90`
- `0x180010ca4`
- `0x180011a84`

## import_xrefs

- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180011aab`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180011aab`
- `api-ms-win-crt-private-l1-1-0!_o__localtime64` at `0x180011abb`
- `api-ms-win-crt-private-l1-1-0!_o__localtime64` at `0x180011abb`
- `api-ms-win-crt-private-l1-1-0!_o_wcsftime` at `0x180011ad5`
- `api-ms-win-crt-private-l1-1-0!_o_wcsftime` at `0x180011ad5`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180011b1a`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180011b1a`

## string_xrefs

- `0x180011af2`: `pcshell\shell\performancetracehandler\dll\performancetracehandler.cpp`

## pseudocode

```c
__int64 __fastcall PerformanceTraceHandler::GetTraceFolderPath(PCWSTR *this, unsigned __int16 **a2)
{
  const struct tm *v4; // rax
  HRESULT v5; // ebx
  __int64 v6; // rdx
  int v8[2]; // [rsp+20h] [rbp-238h] BYREF
  _BYTE v9[8]; // [rsp+28h] [rbp-230h] BYREF
  wchar_t Buffer[264]; // [rsp+30h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  *(_QWORD *)v8 = _time64(0);
  v4 = (const struct tm *)_o__localtime64(v8);
  if ( !wcsftime(Buffer, 0x104u, L"Trace_%Y_%m_%d_%H_%M_%S", v4) )
  {
    v5 = -2147467259;
    v6 = 169;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"pcshell\\shell\\performancetracehandler\\dll\\performancetracehandler.cpp",
      (const char *)(unsigned int)v5,
      v8[0]);
    return (unsigned int)v5;
  }
  v5 = PathAllocCombine(this[21], Buffer, 1u, a2);
  if ( v5 < 0 )
  {
    v6 = 170;
    goto LABEL_3;
  }
  *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::operator->(
                          this + 24,
                          v9)
           + 278LL) = 1;
  tip2::test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::~test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>(v9);
  return 0;
}

```

## disassembly

```asm
0x180011a84  mov     [rsp+arg_10], rbx
0x180011a89  push    rdi
0x180011a8a  sub     rsp, 250h
0x180011a91  mov     rax, cs:__security_cookie
0x180011a98  xor     rax, rsp
0x180011a9b  mov     [rsp+258h+var_18], rax
0x180011aa3  mov     rdi, rcx
0x180011aa6  mov     rbx, rdx
0x180011aa9  xor     ecx, ecx; Time
0x180011aab  call    cs:__imp__time64
0x180011ab1  lea     rcx, [rsp+258h+var_238]
0x180011ab6  mov     qword ptr [rsp+258h+var_238], rax; int
0x180011abb  call    cs:__imp__o__localtime64
0x180011ac1  lea     r8, aTraceYMDHMS; "Trace_%Y_%m_%d_%H_%M_%S"
0x180011ac8  mov     edx, 104h; SizeInWords
0x180011acd  mov     r9, rax; Tm
0x180011ad0  lea     rcx, [rsp+258h+Buffer]; Buffer
0x180011ad5  call    cs:__imp_wcsftime
0x180011adb  test    rax, rax
0x180011ade  jnz     short loc_180011B05
0x180011ae0  mov     ebx, 80004005h
0x180011ae5  mov     edx, 0A9h; void *
0x180011aea  mov     rcx, [rsp+258h]; this
0x180011af2  lea     r8, aPcshellShellPe_3; "pcshell\\shell\\performancetracehandler"...
0x180011af9  mov     r9d, ebx; char *
0x180011afc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011b01  mov     eax, ebx
0x180011b03  jmp     short loc_180011B54
0x180011b05  mov     rcx, [rdi+0A8h]; pszPathIn
0x180011b0c  lea     rdx, [rsp+258h+Buffer]; pszMore
0x180011b11  mov     r9, rbx; ppszPathOut
0x180011b14  mov     r8d, 1; dwFlags
0x180011b1a  call    cs:__imp_PathAllocCombine
0x180011b20  mov     ebx, eax
0x180011b22  test    eax, eax
0x180011b24  jns     short loc_180011B2D
0x180011b26  mov     edx, 0AAh
0x180011b2b  jmp     short loc_180011AEA
0x180011b2d  lea     rcx, [rdi+0C0h]
0x180011b34  lea     rdx, [rsp+258h+var_230]
0x180011b39  call    ??C?$tip_test@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::operator->(void)
0x180011b3e  mov     rcx, [rax]
0x180011b41  mov     byte ptr [rcx+116h], 1
0x180011b48  lea     rcx, [rsp+258h+var_230]
0x180011b4d  call    ??1?$test_data_control@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::~test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>(void)
0x180011b52  xor     eax, eax
0x180011b54  mov     rcx, [rsp+258h+var_18]
0x180011b5c  xor     rcx, rsp; StackCookie
0x180011b5f  call    __security_check_cookie
0x180011b64  mov     rbx, [rsp+258h+arg_10]
0x180011b6c  add     rsp, 250h
0x180011b73  pop     rdi
0x180011b74  retn
```
