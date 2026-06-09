# UtilElevatedManager::InstallDrivers(HSTRING__ *)

- ea: `0x1800499f0`
- end: `0x180049ca7`
- name: `?InstallDrivers@UtilElevatedManager@@UEAAJPEAUHSTRING__@@@Z`
- size: `695`
- prototype: `__int64 __fastcall(UtilElevatedManager *this, HSTRING)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800052ac`
- `0x1800135ec`
- `0x180013a74`
- `0x180015310`
- `0x18001a540`
- `0x18001b004`
- `0x180026478`
- `0x180049260`
- `0x1800492d0`
- `0x1800496d4`
- `0x1800499f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180049b89`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180049b89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180049a13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180049a13`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180049bea`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180049bea`
- `SHELL32!ShellExecuteExW` at `0x180049b39`
- `SHELL32!ShellExecuteExW` at `0x180049b39`

## string_xrefs

- `0x180049b4b`: `onecoreuap\shell\cloudexperiencehost\onecore\comapi\utilelevatedmanager.cpp`
- `0x180049b9e`: `onecoreuap\shell\cloudexperiencehost\onecore\comapi\utilelevatedmanager.cpp`
- `0x180049bfc`: `onecoreuap\shell\cloudexperiencehost\onecore\comapi\utilelevatedmanager.cpp`
- `0x180049c3d`: `onecoreuap\shell\cloudexperiencehost\onecore\comapi\utilelevatedmanager.cpp`
- `0x180049a74`: `\*.inf" /subdirs /install`

## pseudocode

```c
__int64 __fastcall UtilElevatedManager::InstallDrivers(UtilElevatedManager *this, HSTRING a2)
{
  PCWSTR StringRawBuffer; // rdx
  __int64 v3; // rax
  __int64 v4; // rdx
  __int64 v5; // r8
  __m256i *v6; // rcx
  __int64 v7; // rax
  const char *v8; // r9
  unsigned int v9; // ebx
  DWORD v11; // eax
  unsigned int v12; // ebx
  struct _PROCESS_INFORMATION *v13; // rdx
  struct _PROCESS_INFORMATION *v14; // rdx
  const char *v15; // r9
  unsigned int LastError; // ebx
  struct _PROCESS_INFORMATION *v17; // rdx
  unsigned int v18; // ebx
  struct _PROCESS_INFORMATION *v19; // rdx
  __m256i v20; // [rsp+20h] [rbp-E8h] BYREF
  _BYTE v21[32]; // [rsp+40h] [rbp-C8h] BYREF
  SHELLEXECUTEINFOW pExecInfo; // [rsp+60h] [rbp-A8h] BYREF
  DWORD ExitCode; // [rsp+D0h] [rbp-38h] BYREF
  __int128 v24; // [rsp+D8h] [rbp-30h] BYREF
  __int128 v25; // [rsp+E8h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  v3 = std::wstring::wstring(v21, StringRawBuffer);
  v6 = (__m256i *)std::wstring::_Insert<unsigned short>(v3, v4, v5, 13);
  memset(&v20, 0, sizeof(v20));
  v20 = *v6;
  v6->m256i_i64[2] = 0;
  v6->m256i_i64[3] = 7;
  v6->m256i_i16[0] = 0;
  v7 = std::wstring::_Append<unsigned short>(&v20, L"\\*.inf\" /subdirs /install", 25);
  v24 = 0;
  v25 = 0;
  v24 = *(_OWORD *)v7;
  v25 = *(_OWORD *)(v7 + 16);
  *(_QWORD *)(v7 + 16) = 0;
  *(_QWORD *)(v7 + 24) = 7;
  *(_WORD *)v7 = 0;
  std::wstring::_Tidy_deallocate(&v20);
  std::wstring::_Tidy_deallocate(v21);
  memset_0(&pExecInfo, 0, sizeof(pExecInfo));
  pExecInfo.cbSize = 112;
  pExecInfo.fMask = 64;
  pExecInfo.lpVerb = L"runas";
  pExecInfo.lpFile = L"pnputil";
  pExecInfo.lpParameters = (LPCWSTR)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v24);
  pExecInfo.nShow = 0;
  if ( ShellExecuteExW(&pExecInfo) )
  {
    *(_OWORD *)&v20.m256i_u64[1] = 0;
    v20.m256i_i64[0] = (__int64)pExecInfo.hProcess;
    v11 = WaitForSingleObject(pExecInfo.hProcess, 0xFFFFFFFF);
    if ( v11 )
    {
      v12 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x68,
              (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\comapi\\utilelevatedmanager.cpp",
              (const char *)v11,
              v20.m256i_u32[0]);
      wil::details::CloseProcessInformation((wil::details *)&v20, v13);
      std::wstring::_Tidy_deallocate(&v24);
      return v12;
    }
    else
    {
      ExitCode = 0;
      if ( GetExitCodeProcess(pExecInfo.hProcess, &ExitCode) )
      {
        if ( ExitCode )
        {
          v18 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x6C,
                  (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\comapi\\utilelevatedmanager.cpp",
                  (const char *)ExitCode,
                  v20.m256i_u32[0]);
          wil::details::CloseProcessInformation((wil::details *)&v20, v19);
          std::wstring::_Tidy_deallocate(&v24);
          return v18;
        }
        else
        {
          wil::details::CloseProcessInformation((wil::details *)&v20, v14);
          std::wstring::_Tidy_deallocate(&v24);
          return 0;
        }
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x6B,
                      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\comapi\\utilelevatedmanager.cpp",
                      v15);
        wil::details::CloseProcessInformation((wil::details *)&v20, v17);
        std::wstring::_Tidy_deallocate(&v24);
        return LastError;
      }
    }
  }
  else
  {
    v9 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x63,
           (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\comapi\\utilelevatedmanager.cpp",
           v8);
    std::wstring::_Tidy_deallocate(&v24);
    return v9;
  }
}

```

## disassembly

```asm
0x1800499f0  push    rbx
0x1800499f2  sub     rsp, 100h
0x1800499f9  mov     rax, cs:__security_cookie
0x180049a00  xor     rax, rsp
0x180049a03  mov     [rsp+108h+var_10], rax
0x180049a0b  mov     rax, rdx
0x180049a0e  xor     edx, edx; length
0x180049a10  mov     rcx, rax; string
0x180049a13  call    cs:__imp_WindowsGetStringRawBuffer
0x180049a19  mov     rdx, rax
0x180049a1c  lea     rcx, [rsp+108h+var_C8]
0x180049a21  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180049a26  nop
0x180049a27  mov     r9d, 0Dh
0x180049a2d  mov     rcx, rax
0x180049a30  call    ??$_Insert@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KQEBG0@Z; std::wstring::_Insert<ushort>(unsigned __int64,ushort const * const,unsigned __int64)
0x180049a35  mov     rcx, rax
0x180049a38  xorps   xmm0, xmm0
0x180049a3b  movups  xmmword ptr [rsp+108h+var_E8], xmm0
0x180049a40  xorps   xmm1, xmm1
0x180049a43  movdqu  [rsp+108h+var_D8], xmm1
0x180049a49  movups  xmm0, xmmword ptr [rax]
0x180049a4c  movups  xmmword ptr [rsp+108h+var_E8], xmm0
0x180049a51  movups  xmm1, xmmword ptr [rax+10h]
0x180049a55  movups  [rsp+108h+var_D8], xmm1
0x180049a5a  mov     qword ptr [rax+10h], 0
0x180049a62  mov     ebx, 7
0x180049a67  mov     [rax+18h], rbx
0x180049a6b  xor     eax, eax
0x180049a6d  mov     [rcx], ax
0x180049a70  lea     r8d, [rbx+12h]
0x180049a74  lea     rdx, aInfSubdirsInst; "\\*.inf\" /subdirs /install"
0x180049a7b  lea     rcx, [rsp+108h+var_E8]
0x180049a80  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180049a85  mov     rcx, rax
0x180049a88  xorps   xmm0, xmm0
0x180049a8b  movups  [rsp+108h+var_30], xmm0
0x180049a93  xorps   xmm1, xmm1
0x180049a96  movdqu  [rsp+108h+var_20], xmm1
0x180049a9f  movups  xmm0, xmmword ptr [rax]
0x180049aa2  movups  [rsp+108h+var_30], xmm0
0x180049aaa  movups  xmm1, xmmword ptr [rax+10h]
0x180049aae  movups  [rsp+108h+var_20], xmm1
0x180049ab6  mov     qword ptr [rax+10h], 0
0x180049abe  mov     [rax+18h], rbx
0x180049ac2  xor     eax, eax
0x180049ac4  mov     [rcx], ax
0x180049ac7  lea     rcx, [rsp+108h+var_E8]
0x180049acc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180049ad1  nop
0x180049ad2  lea     rcx, [rsp+108h+var_C8]
0x180049ad7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180049adc  mov     ebx, 70h ; 'p'
0x180049ae1  mov     r8d, ebx; Size
0x180049ae4  xor     edx, edx; Val
0x180049ae6  lea     rcx, [rsp+108h+pExecInfo]; void *
0x180049aeb  call    memset_0
0x180049af0  mov     [rsp+108h+pExecInfo.cbSize], ebx
0x180049af4  mov     [rsp+108h+pExecInfo.fMask], 40h ; '@'
0x180049afc  lea     rax, aRunas; "runas"
0x180049b03  mov     [rsp+108h+pExecInfo.lpVerb], rax
0x180049b08  lea     rax, aPnputil; "pnputil"
0x180049b0f  mov     [rsp+108h+pExecInfo.lpFile], rax
0x180049b14  lea     rcx, [rsp+108h+var_30]
0x180049b1c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180049b21  mov     [rsp+108h+pExecInfo.lpParameters], rax
0x180049b29  mov     [rsp+108h+pExecInfo.nShow], 0
0x180049b34  lea     rcx, [rsp+108h+pExecInfo]; pExecInfo
0x180049b39  call    cs:__imp_ShellExecuteExW
0x180049b3f  test    eax, eax
0x180049b41  jnz     short loc_180049B70
0x180049b43  mov     rcx, [rsp+108h]; this
0x180049b4b  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\cloudexperiencehost"...
0x180049b52  lea     edx, [rbx-0Dh]; void *
0x180049b55  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180049b5a  mov     ebx, eax
0x180049b5c  lea     rcx, [rsp+108h+var_30]
0x180049b64  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180049b69  mov     eax, ebx
0x180049b6b  jmp     loc_180049C8D
0x180049b70  xorps   xmm0, xmm0
0x180049b73  movdqu  xmmword ptr [rsp+108h+var_E8+8], xmm0
0x180049b79  mov     rcx, [rsp+108h+pExecInfo.hProcess]; hHandle
0x180049b81  mov     qword ptr [rsp+108h+var_E8], rcx; unsigned int
0x180049b86  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180049b89  call    cs:__imp_WaitForSingleObject
0x180049b8f  test    eax, eax
0x180049b91  jz      short loc_180049BCF
0x180049b93  mov     rcx, [rsp+108h]; this
0x180049b9b  mov     r9d, eax; char *
0x180049b9e  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\cloudexperiencehost"...
0x180049ba5  mov     edx, 68h ; 'h'; void *
0x180049baa  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180049baf  mov     ebx, eax
0x180049bb1  lea     rcx, [rsp+108h+var_E8]; this
0x180049bb6  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x180049bbb  lea     rcx, [rsp+108h+var_30]
0x180049bc3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180049bc8  mov     eax, ebx
0x180049bca  jmp     loc_180049C8D
0x180049bcf  mov     [rsp+108h+ExitCode], 0
0x180049bda  lea     rdx, [rsp+108h+ExitCode]; lpExitCode
0x180049be2  mov     rcx, [rsp+108h+pExecInfo.hProcess]; hProcess
0x180049bea  call    cs:__imp_GetExitCodeProcess
0x180049bf0  test    eax, eax
0x180049bf2  jnz     short loc_180049C28
0x180049bf4  mov     rcx, [rsp+108h]; this
0x180049bfc  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\cloudexperiencehost"...
0x180049c03  lea     edx, [rax+6Bh]; void *
0x180049c06  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180049c0b  mov     ebx, eax
0x180049c0d  lea     rcx, [rsp+108h+var_E8]; this
0x180049c12  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x180049c17  lea     rcx, [rsp+108h+var_30]
0x180049c1f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180049c24  mov     eax, ebx
0x180049c26  jmp     short loc_180049C8D
0x180049c28  mov     r9d, [rsp+108h+ExitCode]; char *
0x180049c30  test    r9d, r9d
0x180049c33  jz      short loc_180049C6B
0x180049c35  mov     rcx, [rsp+108h]; this
0x180049c3d  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\cloudexperiencehost"...
0x180049c44  mov     edx, 6Ch ; 'l'; void *
0x180049c49  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180049c4e  mov     ebx, eax
0x180049c50  lea     rcx, [rsp+108h+var_E8]; this
0x180049c55  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x180049c5a  lea     rcx, [rsp+108h+var_30]
0x180049c62  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180049c67  mov     eax, ebx
0x180049c69  jmp     short loc_180049C8D
0x180049c6b  lea     rcx, [rsp+108h+var_E8]; this
0x180049c70  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x180049c75  lea     rcx, [rsp+108h+var_30]
0x180049c7d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180049c82  xor     eax, eax
0x180049c84  jmp     short loc_180049C8D
0x180049c86  mov     eax, [rsp+108h+ExitCode]
0x180049c8d  mov     rcx, [rsp+108h+var_10]
0x180049c95  xor     rcx, rsp; StackCookie
0x180049c98  call    __security_check_cookie
0x180049c9d  add     rsp, 100h
0x180049ca4  pop     rbx
0x180049ca5  retn
```
