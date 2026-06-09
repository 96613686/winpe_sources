# ComputeFileCacheDirectoryFromFontCacheDirectory(DWrite::RefString const &)

- ea: `0x1800b0ef8`
- end: `0x1800b101e`
- name: `?ComputeFileCacheDirectoryFromFontCacheDirectory@@YA?AVRefString@DWrite@@AEBV12@@Z`
- size: `294`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800b0b54`

## callees

- `0x18000d7ec`
- `0x18000e920`
- `0x1800aa650`
- `0x1800b0ef8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0f67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0f67`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800b0f59`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800b0f59`

## pseudocode

```c
__int64 __fastcall ComputeFileCacheDirectoryFromFontCacheDirectory(__int64 a1, __int64 *a2)
{
  __int64 v3; // rcx
  signed int LastError; // eax
  unsigned int v5; // ecx
  __int128 v7; // [rsp+30h] [rbp-9h] BYREF
  const wchar_t *v8; // [rsp+40h] [rbp+7h]
  __int64 v9; // [rsp+48h] [rbp+Fh]
  _DWORD v10[6]; // [rsp+58h] [rbp+1Fh] BYREF
  __int64 v11; // [rsp+70h] [rbp+37h]
  int v12; // [rsp+78h] [rbp+3Fh]
  int v13; // [rsp+7Ch] [rbp+43h]
  int v14; // [rsp+80h] [rbp+47h]
  int v15; // [rsp+84h] [rbp+4Bh]

  *(_QWORD *)&v7 = a1;
  v3 = *a2;
  v9 = 6;
  *(_QWORD *)&v7 = v3 + 8;
  *((_QWORD *)&v7 + 1) = *(unsigned int *)(v3 + 4);
  v8 = L"Fonts\\";
  DWrite::RefString::RefString(a1, &v7);
  if ( !CreateDirectoryW((LPCWSTR)(*(_QWORD *)a1 + 8LL), 0) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError != 183 )
    {
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      v10[2] = v5;
      v10[1] = 0;
      v10[3] = 0;
      v7 = 0;
      v13 = 0;
      v10[5] = 0;
      v15 = 0;
      v10[0] = 1;
      v12 = 1;
      v10[4] = 0;
      v11 = 0x68746170746E6F66LL;
      v14 = 448;
      EventLogger::LogGenericEvent(0, 0, 0x726F727265LL, v10, 3);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1800b0ef8  mov     [rsp-8+arg_8], rbx
0x1800b0efd  push    rbp
0x1800b0efe  lea     rbp, [rsp-57h]
0x1800b0f03  sub     rsp, 90h
0x1800b0f0a  mov     rax, cs:__security_cookie
0x1800b0f11  xor     rax, rsp
0x1800b0f14  mov     [rbp+57h+var_8], rax
0x1800b0f18  mov     qword ptr [rbp+57h+var_60], rcx
0x1800b0f1c  mov     rbx, rcx
0x1800b0f1f  mov     rcx, [rdx]
0x1800b0f22  lea     rdx, [rbp+57h+var_60]
0x1800b0f26  mov     [rbp+57h+var_48], 6
0x1800b0f2e  lea     rax, [rcx+8]
0x1800b0f32  mov     qword ptr [rbp+57h+var_60], rax
0x1800b0f36  mov     eax, [rcx+4]
0x1800b0f39  mov     rcx, rbx
0x1800b0f3c  mov     qword ptr [rbp+57h+var_60+8], rax
0x1800b0f40  lea     rax, aFonts_0; "Fonts\\"
0x1800b0f47  mov     [rbp+57h+var_50], rax
0x1800b0f4b  call    ??$?0V?$StringSum@PEB_WPEB_W@@@RefString@DWrite@@QEAA@AEBV?$StringExpr@V?$StringSum@PEB_WPEB_W@@@@@Z; DWrite::RefString::RefString(StringExpr<StringSum<wchar_t const *,wchar_t const *>> const &)
0x1800b0f50  mov     rcx, [rbx]
0x1800b0f53  xor     edx, edx; lpSecurityAttributes
0x1800b0f55  add     rcx, 8; lpPathName
0x1800b0f59  call    cs:__imp_CreateDirectoryW
0x1800b0f5f  test    eax, eax
0x1800b0f61  jnz     loc_1800B0FFE
0x1800b0f67  call    cs:__imp_GetLastError
0x1800b0f6d  mov     ecx, eax
0x1800b0f6f  cmp     eax, 0B7h
0x1800b0f74  jz      loc_1800B0FFE
0x1800b0f7a  test    eax, eax
0x1800b0f7c  jle     short loc_1800B0F87
0x1800b0f7e  movzx   ecx, ax
0x1800b0f81  or      ecx, 80070000h
0x1800b0f87  xorps   xmm0, xmm0
0x1800b0f8a  mov     [rbp+57h+var_30], ecx
0x1800b0f8d  movups  [rbp+57h+var_60], xmm0
0x1800b0f91  mov     eax, dword ptr [rbp+57h+var_60+4]
0x1800b0f94  lea     r9, [rbp+57h+var_38]
0x1800b0f98  mov     [rbp+57h+var_34], eax
0x1800b0f9b  mov     edx, 1
0x1800b0fa0  mov     eax, dword ptr [rbp+57h+var_60+0Ch]
0x1800b0fa3  mov     r8, 726F727265h
0x1800b0fad  mov     [rbp+57h+var_2C], eax
0x1800b0fb0  movups  [rbp+57h+var_60], xmm0
0x1800b0fb4  mov     eax, dword ptr [rbp+57h+var_60+4]
0x1800b0fb7  movups  [rbp+57h+var_60], xmm0
0x1800b0fbb  mov     ecx, dword ptr [rbp+57h+var_60+4]
0x1800b0fbe  mov     [rbp+57h+var_14], ecx
0x1800b0fc1  mov     ecx, dword ptr [rbp+57h+var_60+0Ch]
0x1800b0fc4  mov     [rbp+57h+var_24], eax
0x1800b0fc7  mov     rax, 68746170746E6F66h
0x1800b0fd1  mov     [rbp+57h+var_C], ecx
0x1800b0fd4  xor     ecx, ecx
0x1800b0fd6  mov     [rbp+57h+var_38], edx
0x1800b0fd9  mov     [rbp+57h+var_18], edx
0x1800b0fdc  xor     edx, edx
0x1800b0fde  mov     [rbp+57h+var_28], 0
0x1800b0fe5  mov     [rbp+57h+var_20], rax
0x1800b0fe9  mov     [rbp+57h+var_10], 1C0h
0x1800b0ff0  mov     [rsp+90h+var_70], 3
0x1800b0ff9  call    ?LogGenericEvent@EventLogger@@SAXIVEventTag@@0PEBU__MIDL___MIDL_itf_serverinterface_0000_0000_0002@@_K@Z; EventLogger::LogGenericEvent(uint,EventTag,EventTag,__MIDL___MIDL_itf_serverinterface_0000_0000_0002 const *,unsigned __int64)
0x1800b0ffe  mov     rax, rbx
0x1800b1001  mov     rcx, [rbp+57h+var_8]
0x1800b1005  xor     rcx, rsp; StackCookie
0x1800b1008  call    __security_check_cookie
0x1800b100d  mov     rbx, [rsp+90h+arg_8]
0x1800b1015  add     rsp, 90h
0x1800b101c  pop     rbp
0x1800b101d  retn
```
