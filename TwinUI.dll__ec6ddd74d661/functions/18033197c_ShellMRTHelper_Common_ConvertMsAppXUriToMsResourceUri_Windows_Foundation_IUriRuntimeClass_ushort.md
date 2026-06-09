# ShellMRTHelper::Common::ConvertMsAppXUriToMsResourceUri(Windows::Foundation::IUriRuntimeClass *,ushort * *)

- ea: `0x18033197c`
- end: `0x180331cc8`
- name: `?ConvertMsAppXUriToMsResourceUri@Common@ShellMRTHelper@@YAJPEAUIUriRuntimeClass@Foundation@Windows@@PEAPEAG@Z`
- size: `844`
- prototype: `__int64 __fastcall(ShellMRTHelper::Common *__hidden this, struct Windows::Foundation::IUriRuntimeClass *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000a850`

## callees

- `0x18000e2b0`
- `0x1800378dc`
- `0x180041f54`
- `0x1800b4190`
- `0x18033197c`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803319a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180331a13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180331a54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180331a8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180331ace`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180331c7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180331c91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180331ca8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803319a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180331a13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180331a54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180331a8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180331ace`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180331c7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180331c91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180331ca8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1803319f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180331a71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180331aef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1803319f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180331a71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180331aef`

## string_xrefs

- `0x1803319d5`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`
- `0x180331a3f`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`
- `0x180331ab9`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`
- `0x180331b36`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.Common.h`

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
  PCWSTR StringRawBuffer; // r14
  __int64 (__fastcall *v9)(ShellMRTHelper::Common *, HSTRING *); // rbx
  int v10; // eax
  PCWSTR v11; // r15
  __int64 (__fastcall *v12)(ShellMRTHelper::Common *, HSTRING *); // rbx
  int v13; // eax
  PCWSTR v14; // rdi
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rax
  HSTRING v19; // [rsp+20h] [rbp-38h] BYREF
  HSTRING v20; // [rsp+28h] [rbp-30h] BYREF
  HSTRING string; // [rsp+30h] [rbp-28h] BYREF
  __int64 v22; // [rsp+38h] [rbp-20h] BYREF
  __int64 v23; // [rsp+40h] [rbp-18h]
  __int64 v24; // [rsp+48h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]
  UINT32 v26; // [rsp+A0h] [rbp+48h] BYREF
  UINT32 length; // [rsp+A8h] [rbp+50h] BYREF
  UINT32 v28; // [rsp+B0h] [rbp+58h] BYREF
  int v29; // [rsp+B8h] [rbp+60h] BYREF

  *(_QWORD *)a2 = 0;
  string = 0;
  v5 = *(__int64 (__fastcall **)(ShellMRTHelper::Common *, HSTRING *))(*(_QWORD *)this + 104LL);
  WindowsDeleteString(0);
  string = 0;
  v6 = v5(this, &string);
  v7 = v6;
  if ( v6 >= 0 )
  {
    length = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
    v19 = 0;
    v9 = *(__int64 (__fastcall **)(ShellMRTHelper::Common *, HSTRING *))(*(_QWORD *)this + 112LL);
    WindowsDeleteString(0);
    v19 = 0;
    v10 = v9(this, &v19);
    v7 = v10;
    if ( v10 >= 0 )
    {
      v28 = 0;
      v11 = WindowsGetStringRawBuffer(v19, &v28);
      v20 = 0;
      v12 = *(__int64 (__fastcall **)(ShellMRTHelper::Common *, HSTRING *))(*(_QWORD *)this + 88LL);
      WindowsDeleteString(0);
      v20 = 0;
      v13 = v12(this, &v20);
      v7 = v13;
      if ( v13 >= 0 )
      {
        v26 = 0;
        v14 = WindowsGetStringRawBuffer(v20, &v26);
        v22 = 0;
        v23 = 0;
        v24 = 0;
        v15 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                &v22,
                L"ms-resource:",
                length + 20 + v28 + v26);
        v7 = v15;
        if ( v15 >= 0 )
        {
          v29 = 47;
          v15 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
                  &v22,
                  &v29,
                  1);
          v7 = v15;
          if ( v15 >= 0 )
          {
            v29 = 47;
            v15 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
                    &v22,
                    &v29,
                    1);
            v7 = v15;
            if ( v15 >= 0 )
            {
              if ( v26
                && (v15 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
                            &v22,
                            v14,
                            v26),
                    v7 = v15,
                    v15 < 0) )
              {
                v16 = 131;
              }
              else
              {
                v29 = 47;
                v15 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
                        &v22,
                        &v29,
                        1);
                v7 = v15;
                if ( v15 >= 0 )
                {
                  v15 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
                          &v22,
                          L"files",
                          5);
                  v7 = v15;
                  if ( v15 >= 0 )
                  {
                    v15 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
                            &v22,
                            StringRawBuffer,
                            length);
                    v7 = v15;
                    if ( v15 >= 0 )
                    {
                      if ( !v28
                        || (v15 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
                                    &v22,
                                    v11,
                                    v28),
                            v7 = v15,
                            v15 >= 0) )
                      {
                        v17 = v22;
                        v22 = 0;
                        v24 = 0;
                        v23 = 0;
                        *(_QWORD *)a2 = v17;
                        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v22);
                        WindowsDeleteString(v20);
                        v20 = 0;
                        WindowsDeleteString(v19);
                        v7 = 0;
                        goto LABEL_29;
                      }
                      v16 = 143;
                    }
                    else
                    {
                      v16 = 138;
                    }
                  }
                  else
                  {
                    v16 = 135;
                  }
                }
                else
                {
                  v16 = 134;
                }
              }
            }
            else
            {
              v16 = 127;
            }
          }
          else
          {
            v16 = 126;
          }
        }
        else
        {
          v16 = 125;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v16,
          (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
          (const char *)(unsigned int)v15,
          (int)v19);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v22);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x74,
          (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
          (const char *)(unsigned int)v13,
          (int)v19);
      }
      WindowsDeleteString(v20);
      v20 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6E,
        (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
        (const char *)(unsigned int)v10,
        (int)v19);
    }
    WindowsDeleteString(v19);
LABEL_29:
    v19 = 0;
    goto LABEL_30;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x68,
    (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.Common.h",
    (const char *)(unsigned int)v6,
    (int)v19);
LABEL_30:
  WindowsDeleteString(string);
  return v7;
}

```

## disassembly

```asm
0x18033197c  push    rbp
0x18033197e  push    rbx
0x18033197f  push    rsi
0x180331980  push    rdi
0x180331981  push    r12
0x180331983  push    r13
0x180331985  push    r14
0x180331987  push    r15
0x180331989  mov     rbp, rsp
0x18033198c  sub     rsp, 58h
0x180331990  mov     rsi, rdx
0x180331993  mov     rdi, rcx
0x180331996  xor     r12d, r12d
0x180331999  mov     [rdx], r12
0x18033199c  mov     [rbp+string], r12
0x1803319a0  mov     rax, [rcx]
0x1803319a3  mov     rbx, [rax+68h]
0x1803319a7  xor     ecx, ecx; string
0x1803319a9  call    cs:__imp_WindowsDeleteString
0x1803319b0  nop     dword ptr [rax+rax+00h]
0x1803319b5  mov     [rbp+string], r12
0x1803319b9  lea     rdx, [rbp+string]
0x1803319bd  mov     rcx, rdi
0x1803319c0  mov     rax, rbx
0x1803319c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803319c8  mov     ebx, eax
0x1803319ca  test    eax, eax
0x1803319cc  jns     short loc_1803319EB
0x1803319ce  mov     rcx, [rbp+40h]; this
0x1803319d2  mov     r9d, eax; char *
0x1803319d5  lea     r8, aShellcommondes_9; "ShellCommonDesktopBase\\Internal\\Shell"...
0x1803319dc  lea     edx, [r12+68h]; void *
0x1803319e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803319e6  jmp     loc_180331CA4
0x1803319eb  mov     [rbp+length], r12d
0x1803319ef  lea     rdx, [rbp+length]; length
0x1803319f3  mov     rcx, [rbp+string]; string
0x1803319f7  call    cs:__imp_WindowsGetStringRawBuffer
0x1803319fe  nop     dword ptr [rax+rax+00h]
0x180331a03  mov     r14, rax
0x180331a06  mov     [rbp+var_38], r12
0x180331a0a  mov     rcx, [rdi]
0x180331a0d  mov     rbx, [rcx+70h]
0x180331a11  xor     ecx, ecx; string
0x180331a13  call    cs:__imp_WindowsDeleteString
0x180331a1a  nop     dword ptr [rax+rax+00h]
0x180331a1f  mov     [rbp+var_38], r12
0x180331a23  lea     rdx, [rbp+var_38]
0x180331a27  mov     rcx, rdi
0x180331a2a  mov     rax, rbx
0x180331a2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180331a32  mov     ebx, eax
0x180331a34  test    eax, eax
0x180331a36  jns     short loc_180331A65
0x180331a38  mov     rcx, [rbp+40h]; this
0x180331a3c  mov     r9d, eax; char *
0x180331a3f  lea     r8, aShellcommondes_9; "ShellCommonDesktopBase\\Internal\\Shell"...
0x180331a46  mov     edx, 6Eh ; 'n'; void *
0x180331a4b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180331a50  mov     rcx, [rbp+var_38]; string
0x180331a54  call    cs:__imp_WindowsDeleteString
0x180331a5b  nop     dword ptr [rax+rax+00h]
0x180331a60  jmp     loc_180331CA0
0x180331a65  mov     [rbp+arg_10], r12d
0x180331a69  lea     rdx, [rbp+arg_10]; length
0x180331a6d  mov     rcx, [rbp+var_38]; string
0x180331a71  call    cs:__imp_WindowsGetStringRawBuffer
0x180331a78  nop     dword ptr [rax+rax+00h]
0x180331a7d  mov     r15, rax
0x180331a80  mov     [rbp+var_30], r12
0x180331a84  mov     rcx, [rdi]
0x180331a87  mov     rbx, [rcx+58h]
0x180331a8b  xor     ecx, ecx; string
0x180331a8d  call    cs:__imp_WindowsDeleteString
0x180331a94  nop     dword ptr [rax+rax+00h]
0x180331a99  mov     [rbp+var_30], r12
0x180331a9d  lea     rdx, [rbp+var_30]
0x180331aa1  mov     rcx, rdi
0x180331aa4  mov     rax, rbx
0x180331aa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180331aac  mov     ebx, eax
0x180331aae  test    eax, eax
0x180331ab0  jns     short loc_180331AE3
0x180331ab2  mov     rcx, [rbp+40h]; this
0x180331ab6  mov     r9d, eax; char *
0x180331ab9  lea     r8, aShellcommondes_9; "ShellCommonDesktopBase\\Internal\\Shell"...
0x180331ac0  mov     edx, 74h ; 't'; void *
0x180331ac5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180331aca  mov     rcx, [rbp+var_30]; string
0x180331ace  call    cs:__imp_WindowsDeleteString
0x180331ad5  nop     dword ptr [rax+rax+00h]
0x180331ada  mov     [rbp+var_30], r12
0x180331ade  jmp     loc_180331A50
0x180331ae3  mov     [rbp+arg_0], r12d
0x180331ae7  lea     rdx, [rbp+arg_0]; length
0x180331aeb  mov     rcx, [rbp+var_30]; string
0x180331aef  call    cs:__imp_WindowsGetStringRawBuffer
0x180331af6  nop     dword ptr [rax+rax+00h]
0x180331afb  mov     rdi, rax
0x180331afe  mov     [rbp+var_20], r12
0x180331b02  mov     [rbp+var_18], r12
0x180331b06  mov     [rbp+var_10], r12
0x180331b0a  mov     r8d, [rbp+arg_0]
0x180331b0e  add     r8d, [rbp+arg_10]
0x180331b12  mov     ecx, [rbp+length]
0x180331b15  add     ecx, 14h
0x180331b18  add     r8d, ecx
0x180331b1b  lea     rdx, ?c_msResourceUriScheme@Common@ShellMRTHelper@@3QBGB; "ms-resource:"
0x180331b22  lea     rcx, [rbp+var_20]
0x180331b26  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180331b2b  mov     ebx, eax
0x180331b2d  test    eax, eax
0x180331b2f  jns     short loc_180331B57
0x180331b31  mov     edx, 7Dh ; '}'; void *
0x180331b36  lea     r8, aShellcommondes_9; "ShellCommonDesktopBase\\Internal\\Shell"...
0x180331b3d  mov     r9d, eax; char *
0x180331b40  mov     rcx, [rbp+40h]; this
0x180331b44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180331b49  lea     rcx, [rbp+var_20]
0x180331b4d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180331b52  jmp     loc_180331ACA
0x180331b57  mov     [rbp+arg_18], 2Fh ; '/'
0x180331b5e  mov     r13d, 1
0x180331b64  mov     r8d, r13d
0x180331b67  lea     rdx, [rbp+arg_18]
0x180331b6b  lea     rcx, [rbp+var_20]
0x180331b6f  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x180331b74  mov     ebx, eax
0x180331b76  test    eax, eax
0x180331b78  jns     short loc_180331B80
0x180331b7a  lea     edx, [r13+7Dh]
0x180331b7e  jmp     short loc_180331B36
0x180331b80  mov     [rbp+arg_18], 2Fh ; '/'
0x180331b87  mov     r8, r13
0x180331b8a  lea     rdx, [rbp+arg_18]
0x180331b8e  lea     rcx, [rbp+var_20]
0x180331b92  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x180331b97  mov     ebx, eax
0x180331b99  test    eax, eax
0x180331b9b  jns     short loc_180331BA4
0x180331b9d  mov     edx, 7Fh
0x180331ba2  jmp     short loc_180331B36
0x180331ba4  mov     eax, [rbp+arg_0]
0x180331ba7  test    eax, eax
0x180331ba9  jz      short loc_180331BCA
0x180331bab  mov     r8d, eax
0x180331bae  mov     rdx, rdi
0x180331bb1  lea     rcx, [rbp+var_20]
0x180331bb5  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x180331bba  mov     ebx, eax
0x180331bbc  test    eax, eax
0x180331bbe  jns     short loc_180331BCA
0x180331bc0  mov     edx, 83h
0x180331bc5  jmp     loc_180331B36
0x180331bca  mov     [rbp+arg_18], 2Fh ; '/'
0x180331bd1  mov     r8, r13
0x180331bd4  lea     rdx, [rbp+arg_18]
0x180331bd8  lea     rcx, [rbp+var_20]
0x180331bdc  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x180331be1  mov     ebx, eax
0x180331be3  test    eax, eax
0x180331be5  jns     short loc_180331BF1
0x180331be7  mov     edx, 86h
0x180331bec  jmp     loc_180331B36
0x180331bf1  mov     r8d, 5
0x180331bf7  lea     rdx, ?c_msResourceUriFilesPathPrefix@Common@ShellMRTHelper@@3QBGB; "files"
0x180331bfe  lea     rcx, [rbp+var_20]
0x180331c02  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x180331c07  mov     ebx, eax
0x180331c09  test    eax, eax
0x180331c0b  jns     short loc_180331C17
0x180331c0d  mov     edx, 87h
0x180331c12  jmp     loc_180331B36
0x180331c17  mov     r8d, [rbp+length]
0x180331c1b  mov     rdx, r14
0x180331c1e  lea     rcx, [rbp+var_20]
0x180331c22  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x180331c27  mov     ebx, eax
0x180331c29  test    eax, eax
0x180331c2b  jns     short loc_180331C37
0x180331c2d  mov     edx, 8Ah
0x180331c32  jmp     loc_180331B36
0x180331c37  mov     eax, [rbp+arg_10]
0x180331c3a  test    eax, eax
0x180331c3c  jz      short loc_180331C5D
0x180331c3e  mov     r8d, eax
0x180331c41  mov     rdx, r15
0x180331c44  lea     rcx, [rbp+var_20]
0x180331c48  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x180331c4d  mov     ebx, eax
0x180331c4f  test    eax, eax
0x180331c51  jns     short loc_180331C5D
0x180331c53  mov     edx, 8Fh
0x180331c58  jmp     loc_180331B36
0x180331c5d  mov     rax, [rbp+var_20]
0x180331c61  mov     [rbp+var_20], r12
0x180331c65  mov     [rbp+var_10], r12
0x180331c69  mov     [rbp+var_18], r12
0x180331c6d  mov     [rsi], rax
0x180331c70  lea     rcx, [rbp+var_20]
0x180331c74  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180331c79  mov     rcx, [rbp+var_30]; string
0x180331c7d  call    cs:__imp_WindowsDeleteString
0x180331c84  nop     dword ptr [rax+rax+00h]
0x180331c89  mov     [rbp+var_30], r12
0x180331c8d  mov     rcx, [rbp+var_38]; string
0x180331c91  call    cs:__imp_WindowsDeleteString
0x180331c98  nop     dword ptr [rax+rax+00h]
0x180331c9d  mov     ebx, r12d
0x180331ca0  mov     [rbp+var_38], r12
0x180331ca4  mov     rcx, [rbp+string]; string
0x180331ca8  call    cs:__imp_WindowsDeleteString
0x180331caf  nop     dword ptr [rax+rax+00h]
0x180331cb4  mov     eax, ebx
0x180331cb6  add     rsp, 58h
0x180331cba  pop     r15
0x180331cbc  pop     r14
0x180331cbe  pop     r13
0x180331cc0  pop     r12
0x180331cc2  pop     rdi
0x180331cc3  pop     rsi
0x180331cc4  pop     rbx
0x180331cc5  pop     rbp
0x180331cc6  retn
```
