# Windows::Storage::StateABIImplementation::ClearOperation::InternalClear(ushort const *)

- ea: `0x180023cbc`
- end: `0x180023eb1`
- name: `?InternalClear@ClearOperation@StateABIImplementation@Storage@Windows@@AEAAJPEBG@Z`
- size: `501`
- prototype: `__int64 __fastcall(Windows::Storage::StateABIImplementation::ClearOperation *this, wchar_t *folderName)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003fa48`

## callees

- `0x180005ee0`
- `0x180009778`
- `0x180021fc4`
- `0x180023cbc`
- `0x1800240a8`
- `0x180024fc4`
- `0x180025004`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023d3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023e01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023d3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023e01`
- `ext-ms-win-appmodel-state-ext-l1-2-0!GetPublisherCacheFolder` at `0x180023cf4`
- `ext-ms-win-appmodel-state-ext-l1-2-0!GetPublisherCacheFolder` at `0x180023df7`
- `ext-ms-win-appmodel-state-ext-l1-2-0!GetPublisherCacheFolder` at `0x180023cf4`
- `ext-ms-win-appmodel-state-ext-l1-2-0!GetPublisherCacheFolder` at `0x180023df7`

## string_xrefs

- `0x180023d14`: `GetPublisherCacheFolder %ws`
- `0x180023d70`: `GetPublisherCacheFolder %ws size %u`
- `0x180023e33`: `GetPublisherCacheFolder %ws size %u`
- `0x180023e70`: `RemoveDirectoryTree %ws %ws`

## pseudocode

```c
__int64 __fastcall Windows::Storage::StateABIImplementation::ClearOperation::InternalClear(
        Windows::Storage::StateABIImplementation::ClearOperation *this,
        wchar_t *folderName)
{
  HRESULT v4; // ebx
  signed int LastError; // eax
  Windows::Storage::IStorageFolder **v6; // rax
  wchar_t *v7; // rbp
  unsigned int v8; // edx
  int (__fastcall *v9)(const wchar_t *); // r8
  int (__fastcall *v10)(const wchar_t *, const ActionType, const int, void *); // r9
  signed int v11; // eax
  int v12; // eax
  void *retaddr; // [rsp+68h] [rbp+0h]

  if ( !this->m_applicationStateHandle )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( GetPublisherCacheFolder(
         (Windows::Storage::IApplicationData3 *)this->m_applicationStateHandle,
         (HSTRING__ *const)folderName,
         0) )
  {
    v4 = -2147418113;
    Windows::Storage::StateABIHelpers::ReportError(-2147418113, 3u);
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x11Bu,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.clearoperation.cpp",
      -2147418113,
      "GetPublisherCacheFolder %ws",
      folderName);
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError == 122 )
    {
      v6 = (Windows::Storage::IStorageFolder **)operator new(saturated_mul(0, 2u));
      v7 = (wchar_t *)v6;
      if ( v6 )
      {
        if ( GetPublisherCacheFolder(
               (Windows::Storage::IApplicationData3 *)this->m_applicationStateHandle,
               (HSTRING__ *const)folderName,
               v6) )
        {
          this->m_fileDeleteErrorLogged = 0;
          v12 = RemoveDirectoryTree(v7, v8, v9, v10, this);
          v4 = v12;
          if ( v12 > 0 )
            v4 = (unsigned __int16)v12 | 0x80070000;
          if ( v4 == -2147023673 || v4 >= 0 )
            v4 = 0;
          else
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              0x13Du,
              "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.clearoperation.cpp",
              v4,
              "RemoveDirectoryTree %ws %ws",
              folderName,
              v7);
        }
        else
        {
          v11 = GetLastError();
          v4 = v11;
          if ( v11 > 0 )
            v4 = (unsigned __int16)v11 | 0x80070000;
          Windows::Storage::StateABIHelpers::ReportError(v4, 3u);
          if ( v4 < 0 )
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              0x130u,
              "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.clearoperation.cpp",
              v4,
              "GetPublisherCacheFolder %ws size %u",
              folderName,
              0);
        }
        operator delete(v7);
      }
      else
      {
        v4 = -2147024882;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          0x128u,
          "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.clearoperation.cpp",
          -2147024882,
          "new %ws size %u",
          folderName,
          0);
      }
    }
    else
    {
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      Windows::Storage::StateABIHelpers::ReportError(v4, 3u);
      if ( v4 < 0 )
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          0x123u,
          "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.clearoperation.cpp",
          v4,
          "GetPublisherCacheFolder %ws size %u",
          folderName,
          0);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180023cbc  push    rbx
0x180023cbe  push    rbp
0x180023cbf  push    rsi
0x180023cc0  push    rdi
0x180023cc1  sub     rsp, 48h
0x180023cc5  cmp     qword ptr [this+0A8h], 0
0x180023ccd  mov     rsi, folderName
0x180023cd0  mov     rdi, this
0x180023cd3  mov     [rsp+68h+folderPathCch], 0
0x180023cdb  jnz     short loc_180023CE2
0x180023cdd  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "m_applicationStateHandle != INVALID_STATE_HANDLE")
0x180023ce2  mov     this, [rdi+0A8h]; this
0x180023ce9  lea     r9, [rsp+68h+folderPathCch]
0x180023cee  xor     r8d, r8d; Windows::Storage::IStorageFolder **
0x180023cf1  mov     folderName, rsi; HSTRING__ *
0x180023cf4  call    cs:__imp_GetPublisherCacheFolder
0x180023cfa  test    eax, eax
0x180023cfc  jz      short loc_180023D3E
0x180023cfe  mov     ebx, 8000FFFFh
0x180023d03  mov     edx, 3; idsValue
0x180023d08  mov     ecx, ebx; hr
0x180023d0a  call    ?ReportError@StateABIHelpers@Storage@Windows@@YAXJG@Z; Windows::Storage::StateABIHelpers::ReportError(long,ushort)
0x180023d0f  mov     this, [rsp+68h]; callerReturnAddress
0x180023d14  lea     folderName, aGetpublisherca_0; "GetPublisherCacheFolder %ws"
0x180023d1b  mov     [rsp+68h+var_40], rsi
0x180023d20  lea     r8, aOnecoreuapBase_23; "onecoreuap\\base\\appmodel\\statemanage"...
0x180023d27  mov     [rsp+68h+formatString], folderName; formatString
0x180023d2c  mov     r9d, ebx; hr
0x180023d2f  mov     edx, 11Bh; lineNumber
0x180023d34  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180023d39  jmp     loc_180023EA6
0x180023d3e  call    cs:__imp_GetLastError
0x180023d44  mov     ebx, eax
0x180023d46  cmp     eax, 7Ah ; 'z'
0x180023d49  jz      short loc_180023DA3
0x180023d4b  test    eax, eax
0x180023d4d  jle     short loc_180023D58
0x180023d4f  movzx   ebx, ax
0x180023d52  or      ebx, 80070000h
0x180023d58  mov     edx, 3; idsValue
0x180023d5d  mov     ecx, ebx; hr
0x180023d5f  call    ?ReportError@StateABIHelpers@Storage@Windows@@YAXJG@Z; Windows::Storage::StateABIHelpers::ReportError(long,ushort)
0x180023d64  test    ebx, ebx
0x180023d66  jns     loc_180023EA6
0x180023d6c  mov     edx, [rsp+68h+folderPathCch]
0x180023d70  lea     rax, aGetpublisherca_2; "GetPublisherCacheFolder %ws size %u"
0x180023d77  mov     dword ptr [rsp+68h+var_38], edx
0x180023d7b  mov     edx, 123h; lineNumber
0x180023d80  mov     this, [rsp+68h]; callerReturnAddress
0x180023d85  lea     r8, aOnecoreuapBase_23; "onecoreuap\\base\\appmodel\\statemanage"...
0x180023d8c  mov     [rsp+68h+var_40], rsi
0x180023d91  mov     r9d, ebx; hr
0x180023d94  mov     [rsp+68h+formatString], rax; formatString
0x180023d99  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180023d9e  jmp     loc_180023EA6
0x180023da3  mov     ecx, [rsp+68h+folderPathCch]
0x180023da7  mov     eax, 2
0x180023dac  mul     this
0x180023daf  mov     this, 0FFFFFFFFFFFFFFFFh
0x180023db6  cmovb   rax, this
0x180023dba  mov     this, rax; cb
0x180023dbd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180023dc2  mov     rbp, rax
0x180023dc5  test    rax, rax
0x180023dc8  jnz     short loc_180023DE5
0x180023dca  mov     eax, [rsp+68h+folderPathCch]
0x180023dce  mov     ebx, 8007000Eh
0x180023dd3  mov     dword ptr [rsp+68h+var_38], eax
0x180023dd7  mov     edx, 128h
0x180023ddc  lea     rax, aNewWsSizeU; "new %ws size %u"
0x180023de3  jmp     short loc_180023D80
0x180023de5  mov     this, [rdi+0A8h]; this
0x180023dec  lea     r9, [rsp+68h+folderPathCch]
0x180023df1  mov     r8, rbp; Windows::Storage::IStorageFolder **
0x180023df4  mov     folderName, rsi; HSTRING__ *
0x180023df7  call    cs:__imp_GetPublisherCacheFolder
0x180023dfd  test    eax, eax
0x180023dff  jnz     short loc_180023E3C
0x180023e01  call    cs:__imp_GetLastError
0x180023e07  mov     ebx, eax
0x180023e09  test    eax, eax
0x180023e0b  jle     short loc_180023E16
0x180023e0d  movzx   ebx, ax
0x180023e10  or      ebx, 80070000h
0x180023e16  mov     edx, 3; idsValue
0x180023e1b  mov     ecx, ebx; hr
0x180023e1d  call    ?ReportError@StateABIHelpers@Storage@Windows@@YAXJG@Z; Windows::Storage::StateABIHelpers::ReportError(long,ushort)
0x180023e22  test    ebx, ebx
0x180023e24  jns     short loc_180023E9E
0x180023e26  mov     eax, [rsp+68h+folderPathCch]
0x180023e2a  mov     edx, 130h
0x180023e2f  mov     dword ptr [rsp+68h+var_38], eax
0x180023e33  lea     rax, aGetpublisherca_2; "GetPublisherCacheFolder %ws size %u"
0x180023e3a  jmp     short loc_180023E7C
0x180023e3c  mov     this, rbp; path
0x180023e3f  mov     byte ptr [rdi+0C9h], 0
0x180023e46  mov     [rsp+68h+formatString], rdi; fnDeleteFile
0x180023e4b  call    RemoveDirectoryTree
0x180023e50  mov     ebx, eax
0x180023e52  test    eax, eax
0x180023e54  jle     short loc_180023E5F
0x180023e56  movzx   ebx, ax
0x180023e59  or      ebx, 80070000h
0x180023e5f  cmp     ebx, 800704C7h
0x180023e65  jz      short loc_180023E9C
0x180023e67  test    ebx, ebx
0x180023e69  jns     short loc_180023E9C
0x180023e6b  mov     [rsp+68h+var_38], rbp
0x180023e70  lea     rax, aRemovedirector_0; "RemoveDirectoryTree %ws %ws"
0x180023e77  mov     edx, 13Dh; lineNumber
0x180023e7c  mov     this, [rsp+68h]; callerReturnAddress
0x180023e81  lea     r8, aOnecoreuapBase_23; "onecoreuap\\base\\appmodel\\statemanage"...
0x180023e88  mov     [rsp+68h+var_40], rsi
0x180023e8d  mov     r9d, ebx; hr
0x180023e90  mov     [rsp+68h+formatString], rax; formatString
0x180023e95  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180023e9a  jmp     short loc_180023E9E
0x180023e9c  xor     ebx, ebx
0x180023e9e  mov     this, rbp; p
0x180023ea1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180023ea6  mov     eax, ebx
0x180023ea8  add     rsp, 48h
0x180023eac  pop     rdi
0x180023ead  pop     rsi
0x180023eae  pop     rbp
0x180023eaf  pop     rbx
0x180023eb0  retn
```
