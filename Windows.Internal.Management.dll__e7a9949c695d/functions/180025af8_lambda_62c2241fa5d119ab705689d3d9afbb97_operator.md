# _lambda_62c2241fa5d119ab705689d3d9afbb97_::operator()

- ea: `0x180025af8`
- end: `0x180025bd7`
- name: `_lambda_62c2241fa5d119ab705689d3d9afbb97_::operator()`
- size: `223`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180034a90`

## callees

- `0x180004d50`
- `0x18000a2a4`
- `0x180025af8`
- `0x180039990`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180025b2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180025b2b`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180025b45`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180025b45`
- `MdmDiagnostics!__imp_?CreateLogCabOnArea@@YAJPEBG0PEAX@Z` at `0x180025b8e`
- `MdmDiagnostics!__imp_?CreateLogCabOnArea@@YAJPEBG0PEAX@Z` at `0x180025b8e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall lambda_62c2241fa5d119ab705689d3d9afbb97_::operator()(__int64 a1)
{
  HSTRING v2; // rcx
  const WCHAR *StringRawBuffer; // rax
  HRESULT v4; // eax
  unsigned int v5; // edi
  void **v7; // rax
  void *v8; // r8
  int LogCabOnArea; // eax
  int pszPathOut[132]; // [rsp+20h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+0h]

  if ( *(_QWORD *)a1 )
    v2 = **(HSTRING **)a1;
  else
    v2 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(v2, 0);
  v4 = PathCchCombine((PWSTR)pszPathOut, 0x104u, StringRawBuffer, L"MDMDiagReport.cab");
  v5 = v4;
  if ( v4 >= 0 )
  {
    v7 = *(void ***)(a1 + 24);
    if ( v7 )
      v8 = *v7;
    else
      v8 = 0;
    LogCabOnArea = CreateLogCabOnArea(
                     L"DeviceEnrollment;DeviceProvisioning;Autopilot",
                     (const unsigned __int16 *)pszPathOut,
                     v8);
    if ( LogCabOnArea < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x6F5,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
        (const char *)(unsigned int)LogCabOnArea,
        pszPathOut[0]);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6EF,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
      (const char *)(unsigned int)v4,
      pszPathOut[0]);
    return v5;
  }
}

```

## disassembly

```asm
0x180025af8  mov     [rsp+arg_8], rbx
0x180025afd  push    rdi
0x180025afe  sub     rsp, 240h
0x180025b05  mov     rax, cs:__security_cookie
0x180025b0c  xor     rax, rsp
0x180025b0f  mov     [rsp+248h+var_18], rax
0x180025b17  mov     rax, [rcx]
0x180025b1a  mov     rbx, rcx
0x180025b1d  test    rax, rax
0x180025b20  jz      short loc_180025B27
0x180025b22  mov     rcx, [rax]
0x180025b25  jmp     short loc_180025B29
0x180025b27  xor     ecx, ecx; string
0x180025b29  xor     edx, edx; length
0x180025b2b  call    cs:__imp_WindowsGetStringRawBuffer
0x180025b31  lea     r9, pszMore; "MDMDiagReport.cab"
0x180025b38  mov     edx, 104h; cchPathOut
0x180025b3d  mov     r8, rax; pszPathIn
0x180025b40  lea     rcx, [rsp+248h+pszPathOut]; pszPathOut
0x180025b45  call    cs:__imp_PathCchCombine
0x180025b4b  mov     edi, eax
0x180025b4d  test    eax, eax
0x180025b4f  jns     short loc_180025B71
0x180025b51  mov     rcx, [rsp+248h]; this
0x180025b59  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180025b60  mov     r9d, eax; char *
0x180025b63  mov     edx, 6EFh; void *
0x180025b68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025b6d  mov     eax, edi
0x180025b6f  jmp     short loc_180025BB6
0x180025b71  mov     rax, [rbx+18h]
0x180025b75  test    rax, rax
0x180025b78  jz      short loc_180025B7F
0x180025b7a  mov     r8, [rax]
0x180025b7d  jmp     short loc_180025B82
0x180025b7f  xor     r8d, r8d
0x180025b82  lea     rdx, [rsp+248h+pszPathOut]
0x180025b87  lea     rcx, aDeviceenrollme; "DeviceEnrollment;DeviceProvisioning;Aut"...
0x180025b8e  call    cs:__imp_?CreateLogCabOnArea@@YAJPEBG0PEAX@Z; CreateLogCabOnArea(ushort const *,ushort const *,void *)
0x180025b94  test    eax, eax
0x180025b96  jns     short loc_180025BB4
0x180025b98  mov     rcx, [rsp+248h]; this
0x180025ba0  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180025ba7  mov     r9d, eax; char *
0x180025baa  mov     edx, 6F5h; void *
0x180025baf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180025bb4  xor     eax, eax
0x180025bb6  mov     rcx, [rsp+248h+var_18]
0x180025bbe  xor     rcx, rsp; StackCookie
0x180025bc1  call    __security_check_cookie
0x180025bc6  mov     rbx, [rsp+248h+arg_8]
0x180025bce  add     rsp, 240h
0x180025bd5  pop     rdi
0x180025bd6  retn
```
