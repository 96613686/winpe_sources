# ShellMRTHelper::Common::ConvertMsAppXUriToMsResourceUri(Windows::Foundation::IUriRuntimeClass *,ushort * *)

- ea: `0x1800c1ac0`
- end: `0x1800c1e4a`
- name: `?ConvertMsAppXUriToMsResourceUri@Common@ShellMRTHelper@@YAJPEAUIUriRuntimeClass@Foundation@Windows@@PEAPEAG@Z`
- size: `906`
- prototype: `__int64 __fastcall(ShellMRTHelper::Common *__hidden this, struct Windows::Foundation::IUriRuntimeClass *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18036c10c`

## callees

- `0x18001aca4`
- `0x1800c1680`
- `0x1800c172c`
- `0x1800c18c4`
- `0x1800c1900`
- `0x1800c1ac0`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1aec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1b47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1b82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1bb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1bed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1cac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1cba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1dc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1dd4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1e0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1e1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1e31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1aec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1b47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1b82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1bb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1bed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1cac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1cba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1dc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1dd4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1e0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1e1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c1e31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c1b31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c1b9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c1c04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c1b31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c1b9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c1c04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1e03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1e03`

## string_xrefs

- `0x1800c1b12`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`
- `0x1800c1b6d`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`
- `0x1800c1bd8`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`
- `0x1800c1c93`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`
- `0x1800c1de9`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`

## pseudocode

```c
__int64 __fastcall ShellMRTHelper::Common::ConvertMsAppXUriToMsResourceUri(
        ShellMRTHelper::Common *this,
        struct Windows::Foundation::IUriRuntimeClass *a2,
        unsigned __int16 **a3)
{
  __int64 (__fastcall *v5)(ShellMRTHelper::Common *, HSTRING *); // rbx
  int v6; // eax
  unsigned int v7; // ebx
  PCWSTR StringRawBuffer; // r12
  __int64 (__fastcall *v9)(ShellMRTHelper::Common *, HSTRING *); // rbx
  int v10; // eax
  PCWSTR v11; // r13
  __int64 (__fastcall *v12)(ShellMRTHelper::Common *, HSTRING *); // rbx
  int v13; // eax
  PCWSTR v14; // r15
  unsigned __int64 v15; // rsi
  __int64 v16; // rdi
  int v17; // eax
  int v18; // eax
  __int64 v19; // rdx
  LPVOID v20; // rax
  HSTRING v22; // [rsp+20h] [rbp-38h] BYREF
  HSTRING v23; // [rsp+28h] [rbp-30h] BYREF
  HSTRING string; // [rsp+30h] [rbp-28h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-20h] BYREF
  __int64 v26; // [rsp+40h] [rbp-18h]
  __int64 v27; // [rsp+48h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]
  UINT32 v29; // [rsp+A0h] [rbp+48h] BYREF
  UINT32 length; // [rsp+A8h] [rbp+50h] BYREF
  UINT32 v31; // [rsp+B0h] [rbp+58h] BYREF
  int v32; // [rsp+B8h] [rbp+60h] BYREF

  *(_QWORD *)a2 = 0;
  string = 0;
  v5 = *(__int64 (__fastcall **)(ShellMRTHelper::Common *, HSTRING *))(*(_QWORD *)this + 104LL);
  WindowsDeleteString(0);
  string = 0;
  v6 = v5(this, &string);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x68,
      (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
      (const char *)(unsigned int)v6,
      (int)v22);
    goto LABEL_32;
  }
  length = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
  v22 = 0;
  v9 = *(__int64 (__fastcall **)(ShellMRTHelper::Common *, HSTRING *))(*(_QWORD *)this + 112LL);
  WindowsDeleteString(0);
  v22 = 0;
  v10 = v9(this, &v22);
  v7 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6E,
      (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
      (const char *)(unsigned int)v10,
      (int)v22);
LABEL_5:
    WindowsDeleteString(v22);
    v22 = 0;
    goto LABEL_32;
  }
  v31 = 0;
  v11 = WindowsGetStringRawBuffer(v22, &v31);
  v23 = 0;
  v12 = *(__int64 (__fastcall **)(ShellMRTHelper::Common *, HSTRING *))(*(_QWORD *)this + 88LL);
  WindowsDeleteString(0);
  v23 = 0;
  v13 = v12(this, &v23);
  v7 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x74,
      (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
      (const char *)(unsigned int)v13,
      (int)v22);
    WindowsDeleteString(v23);
    v23 = 0;
    goto LABEL_5;
  }
  v29 = 0;
  v14 = WindowsGetStringRawBuffer(v23, &v29);
  pv = 0;
  v26 = 0;
  v27 = 0;
  v15 = v31 + v29 + length + 20;
  v16 = 12;
  if ( v15 < 0xC )
    v16 = (unsigned int)v15;
  v17 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(&pv);
  v7 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7D,
      (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
      (const char *)(unsigned int)v17,
      (int)v22);
    if ( pv )
      CoTaskMemFree(pv);
    WindowsDeleteString(v23);
    v23 = 0;
    WindowsDeleteString(v22);
    v22 = 0;
  }
  else
  {
    StringCchCopyNW((unsigned __int16 *)pv, v15 + 1, L"ms-resource:", (unsigned int)v16);
    v26 = v16;
    v32 = 47;
    v18 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(&pv, &v32, 1);
    v7 = v18;
    if ( v18 >= 0 )
    {
      v32 = 47;
      v18 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(&pv, &v32, 1);
      v7 = v18;
      if ( v18 >= 0 )
      {
        if ( v29
          && (v18 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
                      &pv,
                      v14,
                      v29),
              v7 = v18,
              v18 < 0) )
        {
          v19 = 131;
        }
        else
        {
          v32 = 47;
          v18 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
                  &pv,
                  &v32,
                  1);
          v7 = v18;
          if ( v18 >= 0 )
          {
            v18 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
                    &pv,
                    L"files",
                    5);
            v7 = v18;
            if ( v18 >= 0 )
            {
              v18 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
                      &pv,
                      StringRawBuffer,
                      length);
              v7 = v18;
              if ( v18 >= 0 )
              {
                if ( !v31
                  || (v18 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
                              &pv,
                              v11,
                              v31),
                      v7 = v18,
                      v18 >= 0) )
                {
                  v20 = pv;
                  pv = 0;
                  v27 = 0;
                  v26 = 0;
                  *(_QWORD *)a2 = v20;
                  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
                  WindowsDeleteString(v23);
                  v23 = 0;
                  WindowsDeleteString(v22);
                  v22 = 0;
                  v7 = 0;
                  goto LABEL_32;
                }
                v19 = 143;
              }
              else
              {
                v19 = 138;
              }
            }
            else
            {
              v19 = 135;
            }
          }
          else
          {
            v19 = 134;
          }
        }
      }
      else
      {
        v19 = 127;
      }
    }
    else
    {
      v19 = 126;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
      (const char *)(unsigned int)v18,
      (int)v22);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
    WindowsDeleteString(v23);
    v23 = 0;
    WindowsDeleteString(v22);
    v22 = 0;
  }
LABEL_32:
  WindowsDeleteString(string);
  return v7;
}

```

## disassembly

```asm
0x1800c1ac0  push    rbp
0x1800c1ac2  push    rbx
0x1800c1ac3  push    rsi
0x1800c1ac4  push    rdi
0x1800c1ac5  push    r12
0x1800c1ac7  push    r13
0x1800c1ac9  push    r14
0x1800c1acb  push    r15
0x1800c1acd  mov     rbp, rsp
0x1800c1ad0  sub     rsp, 58h
0x1800c1ad4  mov     r14, rdx
0x1800c1ad7  mov     rdi, rcx
0x1800c1ada  xor     esi, esi
0x1800c1adc  mov     [rdx], rsi
0x1800c1adf  mov     [rbp+string], rsi
0x1800c1ae3  mov     rax, [rcx]
0x1800c1ae6  mov     rbx, [rax+68h]
0x1800c1aea  xor     ecx, ecx; string
0x1800c1aec  call    cs:__imp_WindowsDeleteString
0x1800c1af2  mov     [rbp+string], rsi
0x1800c1af6  lea     rdx, [rbp+string]
0x1800c1afa  mov     rcx, rdi
0x1800c1afd  mov     rax, rbx
0x1800c1b00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1b05  mov     ebx, eax
0x1800c1b07  test    eax, eax
0x1800c1b09  jns     short loc_1800C1B26
0x1800c1b0b  mov     rcx, [rbp+40h]; this
0x1800c1b0f  mov     r9d, eax; char *
0x1800c1b12  lea     r8, aShellcommondes; "ShellCommonDesktopBase\\Internal\\Shell"...
0x1800c1b19  lea     edx, [rsi+68h]; void *
0x1800c1b1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c1b21  jmp     loc_1800C1E2D
0x1800c1b26  mov     [rbp+length], esi
0x1800c1b29  lea     rdx, [rbp+length]; length
0x1800c1b2d  mov     rcx, [rbp+string]; string
0x1800c1b31  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c1b37  mov     r12, rax
0x1800c1b3a  mov     [rbp+var_38], rsi
0x1800c1b3e  mov     rcx, [rdi]
0x1800c1b41  mov     rbx, [rcx+70h]
0x1800c1b45  xor     ecx, ecx; string
0x1800c1b47  call    cs:__imp_WindowsDeleteString
0x1800c1b4d  mov     [rbp+var_38], rsi
0x1800c1b51  lea     rdx, [rbp+var_38]
0x1800c1b55  mov     rcx, rdi
0x1800c1b58  mov     rax, rbx
0x1800c1b5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1b60  mov     ebx, eax
0x1800c1b62  test    eax, eax
0x1800c1b64  jns     short loc_1800C1B91
0x1800c1b66  mov     rcx, [rbp+40h]; this
0x1800c1b6a  mov     r9d, eax; char *
0x1800c1b6d  lea     r8, aShellcommondes; "ShellCommonDesktopBase\\Internal\\Shell"...
0x1800c1b74  mov     edx, 6Eh ; 'n'; void *
0x1800c1b79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c1b7e  mov     rcx, [rbp+var_38]; string
0x1800c1b82  call    cs:__imp_WindowsDeleteString
0x1800c1b88  mov     [rbp+var_38], rsi
0x1800c1b8c  jmp     loc_1800C1E2D
0x1800c1b91  mov     [rbp+arg_10], esi
0x1800c1b94  lea     rdx, [rbp+arg_10]; length
0x1800c1b98  mov     rcx, [rbp+var_38]; string
0x1800c1b9c  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c1ba2  mov     r13, rax
0x1800c1ba5  mov     [rbp+var_30], rsi
0x1800c1ba9  mov     rcx, [rdi]
0x1800c1bac  mov     rbx, [rcx+58h]
0x1800c1bb0  xor     ecx, ecx; string
0x1800c1bb2  call    cs:__imp_WindowsDeleteString
0x1800c1bb8  mov     [rbp+var_30], rsi
0x1800c1bbc  lea     rdx, [rbp+var_30]
0x1800c1bc0  mov     rcx, rdi
0x1800c1bc3  mov     rax, rbx
0x1800c1bc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1bcb  mov     ebx, eax
0x1800c1bcd  test    eax, eax
0x1800c1bcf  jns     short loc_1800C1BF9
0x1800c1bd1  mov     rcx, [rbp+40h]; this
0x1800c1bd5  mov     r9d, eax; char *
0x1800c1bd8  lea     r8, aShellcommondes; "ShellCommonDesktopBase\\Internal\\Shell"...
0x1800c1bdf  mov     edx, 74h ; 't'; void *
0x1800c1be4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c1be9  mov     rcx, [rbp+var_30]; string
0x1800c1bed  call    cs:__imp_WindowsDeleteString
0x1800c1bf3  mov     [rbp+var_30], rsi
0x1800c1bf7  jmp     short loc_1800C1B7E
0x1800c1bf9  mov     [rbp+arg_0], esi
0x1800c1bfc  lea     rdx, [rbp+arg_0]; length
0x1800c1c00  mov     rcx, [rbp+var_30]; string
0x1800c1c04  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c1c0a  mov     r15, rax
0x1800c1c0d  mov     [rbp+pv], rsi
0x1800c1c11  mov     [rbp+var_18], rsi
0x1800c1c15  mov     [rbp+var_10], rsi
0x1800c1c19  mov     r8d, [rbp+arg_0]
0x1800c1c1d  add     r8d, [rbp+arg_10]
0x1800c1c21  mov     edx, [rbp+length]
0x1800c1c24  add     edx, 14h
0x1800c1c27  add     edx, r8d
0x1800c1c2a  mov     esi, edx
0x1800c1c2c  mov     edi, 0Ch
0x1800c1c31  cmp     rsi, rdi
0x1800c1c34  cmovb   edi, esi
0x1800c1c37  lea     rcx, [rbp+pv]
0x1800c1c3b  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x1800c1c40  mov     ebx, eax
0x1800c1c42  test    eax, eax
0x1800c1c44  js      loc_1800C1DE2
0x1800c1c4a  lea     rdx, [rsi+1]; unsigned __int64
0x1800c1c4e  mov     r9d, edi; unsigned __int64
0x1800c1c51  lea     r8, ?c_msResourceUriScheme@Common@ShellMRTHelper@@3QBGB; "ms-resource:"
0x1800c1c58  mov     rcx, [rbp+pv]; unsigned __int16 *
0x1800c1c5c  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800c1c61  mov     [rbp+var_18], rdi
0x1800c1c65  mov     [rbp+arg_18], 2Fh ; '/'
0x1800c1c6c  mov     esi, 1
0x1800c1c71  mov     r8d, esi
0x1800c1c74  lea     rdx, [rbp+arg_18]
0x1800c1c78  lea     rcx, [rbp+pv]
0x1800c1c7c  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x1800c1c81  mov     ebx, eax
0x1800c1c83  xor     edi, edi
0x1800c1c85  test    eax, eax
0x1800c1c87  jns     short loc_1800C1CC9
0x1800c1c89  lea     edx, [rsi+7Dh]; void *
0x1800c1c8c  mov     rcx, [rbp+40h]; this
0x1800c1c90  mov     r9d, eax; char *
0x1800c1c93  lea     r8, aShellcommondes; "ShellCommonDesktopBase\\Internal\\Shell"...
0x1800c1c9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c1c9f  lea     rcx, [rbp+pv]
0x1800c1ca3  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800c1ca8  mov     rcx, [rbp+var_30]; string
0x1800c1cac  call    cs:__imp_WindowsDeleteString
0x1800c1cb2  mov     [rbp+var_30], rdi
0x1800c1cb6  mov     rcx, [rbp+var_38]; string
0x1800c1cba  call    cs:__imp_WindowsDeleteString
0x1800c1cc0  mov     [rbp+var_38], rdi
0x1800c1cc4  jmp     loc_1800C1E2D
0x1800c1cc9  mov     [rbp+arg_18], 2Fh ; '/'
0x1800c1cd0  mov     r8, rsi
0x1800c1cd3  lea     rdx, [rbp+arg_18]
0x1800c1cd7  lea     rcx, [rbp+pv]
0x1800c1cdb  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x1800c1ce0  mov     ebx, eax
0x1800c1ce2  test    eax, eax
0x1800c1ce4  jns     short loc_1800C1CED
0x1800c1ce6  mov     edx, 7Fh
0x1800c1ceb  jmp     short loc_1800C1C8C
0x1800c1ced  mov     eax, [rbp+arg_0]
0x1800c1cf0  test    eax, eax
0x1800c1cf2  jz      short loc_1800C1D13
0x1800c1cf4  mov     r8d, eax
0x1800c1cf7  mov     rdx, r15
0x1800c1cfa  lea     rcx, [rbp+pv]
0x1800c1cfe  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x1800c1d03  mov     ebx, eax
0x1800c1d05  test    eax, eax
0x1800c1d07  jns     short loc_1800C1D13
0x1800c1d09  mov     edx, 83h
0x1800c1d0e  jmp     loc_1800C1C8C
0x1800c1d13  mov     [rbp+arg_18], 2Fh ; '/'
0x1800c1d1a  mov     r8, rsi
0x1800c1d1d  lea     rdx, [rbp+arg_18]
0x1800c1d21  lea     rcx, [rbp+pv]
0x1800c1d25  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x1800c1d2a  mov     ebx, eax
0x1800c1d2c  test    eax, eax
0x1800c1d2e  jns     short loc_1800C1D3A
0x1800c1d30  mov     edx, 86h
0x1800c1d35  jmp     loc_1800C1C8C
0x1800c1d3a  mov     r8d, 5
0x1800c1d40  lea     rdx, ?c_msResourceUriFilesPathPrefix@Common@ShellMRTHelper@@3QBGB; "files"
0x1800c1d47  lea     rcx, [rbp+pv]
0x1800c1d4b  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x1800c1d50  mov     ebx, eax
0x1800c1d52  test    eax, eax
0x1800c1d54  jns     short loc_1800C1D60
0x1800c1d56  mov     edx, 87h
0x1800c1d5b  jmp     loc_1800C1C8C
0x1800c1d60  mov     r8d, [rbp+length]
0x1800c1d64  mov     rdx, r12
0x1800c1d67  lea     rcx, [rbp+pv]
0x1800c1d6b  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x1800c1d70  mov     ebx, eax
0x1800c1d72  test    eax, eax
0x1800c1d74  jns     short loc_1800C1D80
0x1800c1d76  mov     edx, 8Ah
0x1800c1d7b  jmp     loc_1800C1C8C
0x1800c1d80  mov     eax, [rbp+arg_10]
0x1800c1d83  test    eax, eax
0x1800c1d85  jz      short loc_1800C1DA6
0x1800c1d87  mov     r8d, eax
0x1800c1d8a  mov     rdx, r13
0x1800c1d8d  lea     rcx, [rbp+pv]
0x1800c1d91  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x1800c1d96  mov     ebx, eax
0x1800c1d98  test    eax, eax
0x1800c1d9a  jns     short loc_1800C1DA6
0x1800c1d9c  mov     edx, 8Fh
0x1800c1da1  jmp     loc_1800C1C8C
0x1800c1da6  mov     rax, [rbp+pv]
0x1800c1daa  mov     [rbp+pv], rdi
0x1800c1dae  mov     [rbp+var_10], rdi
0x1800c1db2  mov     [rbp+var_18], rdi
0x1800c1db6  mov     [r14], rax
0x1800c1db9  lea     rcx, [rbp+pv]
0x1800c1dbd  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800c1dc2  mov     rcx, [rbp+var_30]; string
0x1800c1dc6  call    cs:__imp_WindowsDeleteString
0x1800c1dcc  mov     [rbp+var_30], rdi
0x1800c1dd0  mov     rcx, [rbp+var_38]; string
0x1800c1dd4  call    cs:__imp_WindowsDeleteString
0x1800c1dda  mov     [rbp+var_38], rdi
0x1800c1dde  mov     ebx, edi
0x1800c1de0  jmp     short loc_1800C1E2D
0x1800c1de2  mov     rcx, [rbp+40h]; this
0x1800c1de6  mov     r9d, eax; char *
0x1800c1de9  lea     r8, aShellcommondes; "ShellCommonDesktopBase\\Internal\\Shell"...
0x1800c1df0  mov     edx, 7Dh ; '}'; void *
0x1800c1df5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c1dfa  mov     rcx, [rbp+pv]; pv
0x1800c1dfe  test    rcx, rcx
0x1800c1e01  jz      short loc_1800C1E09
0x1800c1e03  call    cs:__imp_CoTaskMemFree
0x1800c1e09  mov     rcx, [rbp+var_30]; string
0x1800c1e0d  call    cs:__imp_WindowsDeleteString
0x1800c1e13  mov     [rbp+var_30], 0
0x1800c1e1b  mov     rcx, [rbp+var_38]; string
0x1800c1e1f  call    cs:__imp_WindowsDeleteString
0x1800c1e25  mov     [rbp+var_38], 0
0x1800c1e2d  mov     rcx, [rbp+string]; string
0x1800c1e31  call    cs:__imp_WindowsDeleteString
0x1800c1e37  mov     eax, ebx
0x1800c1e39  add     rsp, 58h
0x1800c1e3d  pop     r15
0x1800c1e3f  pop     r14
0x1800c1e41  pop     r13
0x1800c1e43  pop     r12
0x1800c1e45  pop     rdi
0x1800c1e46  pop     rsi
0x1800c1e47  pop     rbx
0x1800c1e48  pop     rbp
0x1800c1e49  retn
```
