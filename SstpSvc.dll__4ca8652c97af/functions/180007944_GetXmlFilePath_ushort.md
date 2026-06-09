# GetXmlFilePath(ushort * *)

- ea: `0x180007944`
- end: `0x180007a7d`
- name: `?GetXmlFilePath@@YAKPEAPEAG@Z`
- size: `313`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000f974`
- `0x180010634`
- `0x180010b84`
- `0x180010e30`

## callees

- `0x180007944`
- `0x18000827c`
- `0x180008360`
- `0x180008850`
- `0x18001bcba`
- `0x18001bcf0`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180007a55`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007a55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800079a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007a2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800079a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007a2b`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180007994`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180007a21`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180007994`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180007a21`

## string_xrefs

- `0x18000798d`: `%windir%\System32\ras\SSTPProxy\ProxyConfig.xml`
- `0x180007a1a`: `%windir%\System32\ras\SSTPProxy\ProxyConfig.xml`
- `0x1800079c2`: `GetXmlFilePath: ExpandEnvironmentStringsW method failed with error %d`

## pseudocode

```c
__int64 __fastcall GetXmlFilePath(unsigned __int16 **a1)
{
  void **v1; // rsi
  unsigned int v2; // edi
  DWORD v3; // eax
  unsigned __int64 v4; // r14
  DWORD LastError; // eax
  WCHAR *v6; // rax
  __int64; // rax
  int v10; // [rsp+30h] [rbp-838h] BYREF
  _BYTE v11[2044]; // [rsp+34h] [rbp-834h] BYREF
  std::bad_alloc *v12; // [rsp+830h] [rbp-38h] BYREF

  v1 = (void **)a1;
  v2 = 0;
  v10 = 0;
  memset_0(v11, 0, sizeof(v11));
  *v1 = 0;
  v3 = ExpandEnvironmentStringsW(L"%windir%\\System32\\ras\\SSTPProxy\\ProxyConfig.xml", 0, 0);
  v4 = v3;
  if ( v3 || (LastError = GetLastError(), (v2 = LastError) == 0) )
  {
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v6 = (WCHAR *)operator new[](saturated_mul(v4, 2u));
      *v1 = v6;
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', &v12) )
      {
        *a1 = 0;
        v2 = 8;
        v1 = (void **)a1;
        __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180007A42);
LABEL_10:
        if ( *v1 )
          operator delete[](*v1);
        *v1 = 0;
LABEL_13:
         = v2;
      }
    }
    if ( ExpandEnvironmentStringsW(L"%windir%\\System32\\ras\\SSTPProxy\\ProxyConfig.xml", v6, v4) )
    {
      if ( !v2 )
        goto LABEL_13;
      goto LABEL_10;
    }
    LastError = GetLastError();
    v2 = LastError;
    if ( !LastError )
      goto LABEL_13;
  }
  if ( (byte_18002D803 & 8) != 0 )
  {
    LOWORD(v10) = 0;
    FormatRRASErrorString(&v10, L"GetXmlFilePath: ExpandEnvironmentStringsW method failed with error %d", LastError);
    if ( (byte_18002D803 & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v10);
  }
  goto LABEL_10;
}

```

## disassembly

```asm
0x180007944  push    rbx
0x180007946  push    rsi
0x180007947  push    rdi
0x180007948  push    r14
0x18000794a  sub     rsp, 848h
0x180007951  mov     rax, cs:__security_cookie
0x180007958  xor     rax, rsp
0x18000795b  mov     [rsp+868h+var_30], rax
0x180007963  mov     rsi, rcx
0x180007966  mov     [rsp+868h+var_840], rcx
0x18000796b  xor     ebx, ebx
0x18000796d  mov     edi, ebx
0x18000796f  mov     [rsp+868h+var_838], ebx
0x180007973  xor     edx, edx; Val
0x180007975  mov     r8d, 7FCh; Size
0x18000797b  lea     rcx, [rsp+868h+var_834]; void *
0x180007980  call    memset_0
0x180007985  mov     [rsi], rbx
0x180007988  xor     r8d, r8d; nSize
0x18000798b  xor     edx, edx; lpDst
0x18000798d  lea     rcx, Src; "%windir%\\System32\\ras\\SSTPProxy\\Pro"...
0x180007994  call    cs:__imp_ExpandEnvironmentStringsW
0x18000799a  mov     r14d, eax
0x18000799d  test    eax, eax
0x18000799f  jnz     short loc_1800079F6
0x1800079a1  call    cs:__imp_GetLastError
0x1800079a7  mov     edi, eax
0x1800079a9  test    eax, eax
0x1800079ab  jz      short loc_1800079F6
0x1800079ad  test    cs:byte_18002D803, 8
0x1800079b4  jz      loc_180007A4D
0x1800079ba  mov     word ptr [rsp+868h+var_838], bx
0x1800079bf  mov     r8d, eax
0x1800079c2  lea     rdx, aGetxmlfilepath; "GetXmlFilePath: ExpandEnvironmentString"...
0x1800079c9  lea     rcx, [rsp+868h+var_838]
0x1800079ce  call    FormatRRASErrorString
0x1800079d3  test    cs:byte_18002D803, 8
0x1800079da  jz      short loc_180007A4D
0x1800079dc  lea     r8, [rsp+868h+var_838]
0x1800079e1  lea     rdx, RasSSTPSvcTraceError
0x1800079e8  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800079ef  call    McTemplateU0z_EventWriteTransfer
0x1800079f4  jmp     short loc_180007A4D
0x1800079f6  mov     eax, 2
0x1800079fb  mul     r14
0x1800079fe  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180007a05  cmovb   rax, rcx
0x180007a09  mov     rcx, rax; unsigned __int64
0x180007a0c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180007a11  mov     [rsi], rax
0x180007a14  mov     r8d, r14d; nSize
0x180007a17  mov     rdx, rax; lpDst
0x180007a1a  lea     rcx, Src; "%windir%\\System32\\ras\\SSTPProxy\\Pro"...
0x180007a21  call    cs:__imp_ExpandEnvironmentStringsW
0x180007a27  test    eax, eax
0x180007a29  jnz     short loc_180007A3C
0x180007a2b  call    cs:__imp_GetLastError
0x180007a31  mov     edi, eax
0x180007a33  test    eax, eax
0x180007a35  jz      short loc_180007A5E
0x180007a37  jmp     loc_1800079AD
0x180007a3c  test    edi, edi
0x180007a3e  jnz     short loc_180007A4D
0x180007a40  jmp     short loc_180007A5E
0x180007a42  xor     ebx, ebx
0x180007a44  mov     edi, [rsp+868h+var_848]
0x180007a48  mov     rsi, [rsp+868h+var_840]
0x180007a4d  cmp     [rsi], rbx
0x180007a50  jz      short loc_180007A5B
0x180007a52  mov     rcx, [rsi]
0x180007a55  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180007a5b  mov     [rsi], rbx
0x180007a5e  mov     eax, edi
0x180007a60  mov     rcx, [rsp+868h+var_30]
0x180007a68  xor     rcx, rsp; StackCookie
0x180007a6b  call    __security_check_cookie
0x180007a70  add     rsp, 848h
0x180007a77  pop     r14
0x180007a79  pop     rdi
0x180007a7a  pop     rsi
0x180007a7b  pop     rbx
0x180007a7c  retn
```
