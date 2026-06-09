# FileOperationServiceDrivenAction::Run(void)

- ea: `0x18003c7a0`
- end: `0x18003c96a`
- name: `?Run@FileOperationServiceDrivenAction@@UEAAXXZ`
- size: `458`
- prototype: `void __fastcall(FileOperationServiceDrivenAction *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180017c84`
- `0x18002bc50`
- `0x18002bd64`
- `0x18002c958`
- `0x18002db58`
- `0x18003c10c`
- `0x18003c360`
- `0x18003c7a0`
- `0x18003c970`
- `0x180042f54`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18003c7bb`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18003c833`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18003c7bb`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18003c833`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003c7cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003c86c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003c8f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003c7cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003c86c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003c8f7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003c801`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003c801`

## string_xrefs

- `0x18003c7ec`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\fileoperationservicedrivenaction.cpp`
- `0x18003c813`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\fileoperationservicedrivenaction.cpp`
- `0x18003c8e0`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\fileoperationservicedrivenaction.cpp`
- `0x18003c91a`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\fileoperationservicedrivenaction.cpp`
- `0x18003c942`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\fileoperationservicedrivenaction.cpp`

## pseudocode

```c
void __fastcall FileOperationServiceDrivenAction::Run(FileOperationServiceDrivenAction *this)
{
  BOOL v2; // eax
  wil *v3; // rcx
  const unsigned __int16 *StringRawBuffer; // rdx
  int ContentFromFileAndVerifySha256Hash; // eax
  BOOL v6; // eax
  const char *v7; // r9
  unsigned int v8; // eax
  int v9; // esi
  struct MitigationContext *MitigationContext; // rax
  const unsigned __int16 *v11; // rax
  int v12; // eax
  int v13; // eax
  unsigned int v14; // eax
  __int64 v15; // rax
  __int64 v16; // rax
  int v17; // [rsp+20h] [rbp-228h]
  int v18; // [rsp+20h] [rbp-228h]
  IID rclsid; // [rsp+30h] [rbp-218h] BYREF
  char *v20; // [rsp+40h] [rbp-208h] BYREF
  __int64 v21; // [rsp+48h] [rbp-200h] BYREF
  char v22; // [rsp+50h] [rbp-1F8h]
  const wil::ResultException *v23; // [rsp+58h] [rbp-1F0h] BYREF
  _BYTE v24[432]; // [rsp+60h] [rbp-1E8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+0h]
  int v26; // [rsp+250h] [rbp+8h] BYREF

  v2 = PathFileExistsW(*((LPCWSTR *)this + 7));
  try
  {
    if ( v2 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 14), 0);
      ContentFromFileAndVerifySha256Hash = FileUtils::GetContentFromFileAndVerifySha256Hash(
                                             *((const unsigned __int16 **)this + 7),
                                             StringRawBuffer);
      v3 = retaddr;
      if ( ContentFromFileAndVerifySha256Hash < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x55,
          (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\fileoperationservicedrivenaction.cpp",
          (const char *)(unsigned int)ContentFromFileAndVerifySha256Hash,
          v17);
        v6 = DeleteFileW(*((LPCWSTR *)this + 7));
        v3 = retaddr;
        if ( !v6 )
          wil::details::in1diag3::_Throw_GetLastError(
            retaddr,
            (void *)0x57,
            (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\fileoperationservicedrivenaction.cpp",
            v7);
      }
    }
    if ( !*((_DWORD *)this + 36) && !PathFileExistsW(*((LPCWSTR *)this + 7)) )
    {
      v26 = 0;
      v20 = (char *)this + 120;
      v21 = 0;
      v22 = 1;
      v8 = (unsigned int)WindowsGetStringRawBuffer(*((HSTRING *)this + 13), 0);
      rclsid = *(IID *)&off_18005EE80;
      v9 = FileUtils::DownloadContentFromURL(
             v8,
             (unsigned int)&rclsid,
             (unsigned int)&v21,
             (int)this + 128,
             (unsigned int)&v26);
      wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>>(&v20);
      rclsid = (IID)xmmword_180080698;
      MitigationContext = MitigationExecutionContext::GetMitigationContext(&rclsid);
      *((_DWORD *)MitigationContext + 44) = v26;
      if ( v9 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x64,
          (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\fileoperationservicedrivenaction.cpp",
          (const char *)(unsigned int)v9,
          v18);
      v11 = WindowsGetStringRawBuffer(*((HSTRING *)this + 14), 0);
      v12 = FileUtils::VerifyContentSha256Hash(*((unsigned __int8 **)this + 15), *((_DWORD *)this + 32), v11);
      if ( v12 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x67,
          (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\fileoperationservicedrivenaction.cpp",
          (const char *)(unsigned int)v12,
          v18);
      v13 = FileOperationServiceDrivenAction::FlushContentToFile(this);
      v3 = retaddr;
      if ( v13 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x69,
          (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\fileoperationservicedrivenaction.cpp",
          (const char *)(unsigned int)v13,
          v18);
    }
  }
  catch ( const wil::ResultException *v23 )
  {
    v16 = MitigationException::MitigationException(v24, 2, v23);
    wil::details::ReportFailure_CustomException<MitigationException>(
      retaddr,
      110,
      "onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\fileoperationservicedrivenaction.cpp",
      v16);
  }
  catch ( ... )
  {
    v14 = wil::ResultFromCaughtException(v3);
    v15 = MitigationException::MitigationException(v24, 2, v14);
    wil::details::ReportFailure_CustomException<MitigationException>(
      retaddr,
      115,
      "onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\fileoperationservicedrivenaction.cpp",
      v15);
  }
}

```

## disassembly

```asm
0x18003c7a0  mov     rax, rsp
0x18003c7a3  push    rbx
0x18003c7a4  push    rsi
0x18003c7a5  push    r14
0x18003c7a7  push    r15
0x18003c7a9  sub     rsp, 228h
0x18003c7b0  movaps  xmmword ptr [rax-38h], xmm6
0x18003c7b4  mov     rbx, rcx
0x18003c7b7  mov     rcx, [rcx+38h]; pszPath
0x18003c7bb  call    cs:__imp_PathFileExistsW
0x18003c7c1  test    eax, eax
0x18003c7c3  jz      short loc_18003C822
0x18003c7c5  xor     edx, edx; length
0x18003c7c7  mov     rcx, [rbx+70h]; string
0x18003c7cb  call    cs:__imp_WindowsGetStringRawBuffer
0x18003c7d1  mov     rdx, rax; unsigned __int16 *
0x18003c7d4  mov     rcx, [rbx+38h]; unsigned __int16 *
0x18003c7d8  call    ?GetContentFromFileAndVerifySha256Hash@FileUtils@@SAJPEBGQEBG@Z; FileUtils::GetContentFromFileAndVerifySha256Hash(ushort const *,ushort const * const)
0x18003c7dd  mov     rcx, [rsp+248h]; this
0x18003c7e5  test    eax, eax
0x18003c7e7  jns     short loc_18003C822
0x18003c7e9  mov     r9d, eax; char *
0x18003c7ec  lea     r8, aOnecoreBaseDia_22; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003c7f3  mov     edx, 55h ; 'U'; void *
0x18003c7f8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003c7fd  mov     rcx, [rbx+38h]; lpFileName
0x18003c801  call    cs:__imp_DeleteFileW
0x18003c807  mov     rcx, [rsp+248h]; this
0x18003c80f  test    eax, eax
0x18003c811  jnz     short loc_18003C822
0x18003c813  lea     r8, aOnecoreBaseDia_22; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003c81a  lea     edx, [rax+57h]; void *
0x18003c81d  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18003c822  cmp     dword ptr [rbx+90h], 0
0x18003c829  jnz     loc_18003C954
0x18003c82f  mov     rcx, [rbx+38h]; pszPath
0x18003c833  call    cs:__imp_PathFileExistsW
0x18003c839  test    eax, eax
0x18003c83b  jnz     loc_18003C954
0x18003c841  mov     [rsp+248h+arg_0], eax
0x18003c848  lea     r14, [rbx+78h]
0x18003c84c  mov     [rsp+248h+var_208], r14
0x18003c851  mov     [rsp+248h+var_200], 0
0x18003c85a  mov     [rsp+248h+var_1F8], 1
0x18003c85f  movups  xmm6, xmmword ptr cs:off_18005EE80; "ca9d613c-a9a4-46e9-a010-8054ace6ee02"
0x18003c866  xor     edx, edx; length
0x18003c868  mov     rcx, [rbx+68h]; string
0x18003c86c  call    cs:__imp_WindowsGetStringRawBuffer
0x18003c872  movdqu  xmmword ptr [rsp+248h+rclsid.Data1], xmm6
0x18003c878  lea     r15, [rbx+80h]
0x18003c87f  lea     rcx, [rsp+248h+arg_0]
0x18003c887  mov     qword ptr [rsp+248h+var_228], rcx; int
0x18003c88c  mov     r9, r15
0x18003c88f  lea     r8, [rsp+248h+var_200]
0x18003c894  lea     rdx, [rsp+248h+rclsid]
0x18003c899  mov     rcx, rax
0x18003c89c  call    ?DownloadContentFromURL@FileUtils@@SAJPEBGV?$basic_string_view@GU?$char_traits@G@std@@@std@@PEAPEAEPEAKAEAH@Z; FileUtils::DownloadContentFromURL(ushort const *,std::basic_string_view<ushort>,uchar * *,ulong *,int &)
0x18003c8a1  mov     esi, eax
0x18003c8a3  lea     rcx, [rsp+248h+var_208]
0x18003c8a8  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>>::~out_param_t<wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>>(void)
0x18003c8ad  movups  xmm0, cs:xmmword_180080698
0x18003c8b4  movdqu  xmmword ptr [rsp+248h+rclsid.Data1], xmm0
0x18003c8ba  lea     rcx, [rsp+248h+rclsid]; rclsid
0x18003c8bf  call    ?GetMitigationContext@MitigationExecutionContext@@SAAEAVMitigationContext@@U_GUID@@@Z; MitigationExecutionContext::GetMitigationContext(_GUID)
0x18003c8c4  mov     ecx, [rsp+248h+arg_0]
0x18003c8cb  mov     [rax+0B0h], ecx
0x18003c8d1  mov     rcx, [rsp+248h]; this
0x18003c8d9  test    esi, esi
0x18003c8db  jns     short loc_18003C8F1
0x18003c8dd  mov     r9d, esi; char *
0x18003c8e0  lea     r8, aOnecoreBaseDia_22; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003c8e7  mov     edx, 64h ; 'd'; void *
0x18003c8ec  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003c8f1  xor     edx, edx; length
0x18003c8f3  mov     rcx, [rbx+70h]; string
0x18003c8f7  call    cs:__imp_WindowsGetStringRawBuffer
0x18003c8fd  mov     r8, rax; unsigned __int16 *
0x18003c900  mov     edx, [r15]; unsigned int
0x18003c903  mov     rcx, [r14]; unsigned __int8 *
0x18003c906  call    ?VerifyContentSha256Hash@FileUtils@@SAJPEAEKQEBG@Z; FileUtils::VerifyContentSha256Hash(uchar *,ulong,ushort const * const)
0x18003c90b  mov     rcx, [rsp+248h]; this
0x18003c913  test    eax, eax
0x18003c915  jns     short loc_18003C92B
0x18003c917  mov     r9d, eax; char *
0x18003c91a  lea     r8, aOnecoreBaseDia_22; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003c921  mov     edx, 67h ; 'g'; void *
0x18003c926  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003c92b  mov     rcx, rbx; this
0x18003c92e  call    ?FlushContentToFile@FileOperationServiceDrivenAction@@AEAAJXZ; FileOperationServiceDrivenAction::FlushContentToFile(void)
0x18003c933  mov     rcx, [rsp+248h]; this
0x18003c93b  test    eax, eax
0x18003c93d  jns     short loc_18003C954
0x18003c93f  mov     r9d, eax; char *
0x18003c942  lea     r8, aOnecoreBaseDia_22; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003c949  mov     edx, 69h ; 'i'; void *
0x18003c94e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003c954  movaps  xmm6, [rsp+248h+var_38]
0x18003c95c  add     rsp, 228h
0x18003c963  pop     r15
0x18003c965  pop     r14
0x18003c967  pop     rsi
0x18003c968  pop     rbx
0x18003c969  retn
```
