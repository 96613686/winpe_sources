# Microsoft::Windows::Autopilot::AutoPilotStringFile::ReadFromFile(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)

- ea: `0x18002553c`
- end: `0x180025885`
- name: `?ReadFromFile@AutoPilotStringFile@Autopilot@Windows@Microsoft@@SAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `841`
- prototype: `__int64 __fastcall(const WCHAR *, HSTRING *)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180019ef0`
- `0x18001a280`
- `0x18001c234`

## callees

- `0x18000d5a8`
- `0x1800105d4`
- `0x1800105f4`
- `0x1800253d4`
- `0x18002553c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002579f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025859`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002579f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025859`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025738`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025738`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025687`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800257dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025687`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800257dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002569a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800257f0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002569a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800257f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPromoteStringBuffer` at `0x180025800`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPromoteStringBuffer` at `0x180025800`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x180025717`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x180025717`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1800256fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180025791`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18002584b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1800256fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180025791`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18002584b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800256aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800256aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025692`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800257e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025692`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800257e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025865`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025865`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18002563c`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18002563c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800255c5`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180025769`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800255c5`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180025769`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002560d`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002560d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180025579`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180025579`

## string_xrefs

- `0x18002561e`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotconfigurationfile.cpp`
- `0x18002566a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotconfigurationfile.cpp`
- `0x1800256e3`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotconfigurationfile.cpp`
- `0x180025777`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotconfigurationfile.cpp`
- `0x1800257bf`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotconfigurationfile.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall Microsoft::Windows::Autopilot::AutoPilotStringFile::ReadFromFile(const WCHAR *a1, HSTRING *a2)
{
  char v3; // r12
  unsigned int v4; // ebx
  wil::details *v5; // rcx
  char *FileW; // rsi
  unsigned int LastError; // ebx
  const char *v8; // r9
  __int64 v9; // rdx
  int v10; // r15d
  __int64 v11; // rdx
  __int64 v12; // r9
  DWORD v13; // edi
  HSTRING v14; // rdi
  DWORD v15; // ebx
  HRESULT String; // eax
  __int64 v17; // rdx
  unsigned __int64 v18; // r9
  HRESULT v19; // eax
  WCHAR *v20; // rdx
  void *v21; // rbx
  LPVOID v22; // rax
  const char *v23; // r9
  HRESULT v24; // edi
  __int64 v25; // rdx
  HSTRING v26; // r15
  DWORD v27; // edi
  HSTRING_BUFFER v28; // rcx
  int lpOverlapped; // [rsp+20h] [rbp-40h]
  int lpOverlappeda; // [rsp+20h] [rbp-40h]
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-20h] BYREF
  HSTRING_BUFFER bufferHandle; // [rsp+48h] [rbp-18h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+50h] [rbp-10h] BYREF
  WCHAR *charBuffer; // [rsp+58h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  int Buffer; // [rsp+B0h] [rbp+50h] BYREF
  DWORD v38; // [rsp+B8h] [rbp+58h] BYREF

  v3 = 1;
  v4 = 3;
  FileW = (char *)CreateFileW(a1, 0x120089u, 1u, 0, 3u, 0, 0);
  if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    Buffer = 0;
    NumberOfBytesRead = 0;
    if ( !ReadFile(FileW, &Buffer, 4u, &NumberOfBytesRead, 0) )
    {
      v9 = 57;
LABEL_13:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v9,
                    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotconfigurationfile.cpp",
                    v8);
LABEL_59:
      CloseHandle(FileW);
      return LastError;
    }
    if ( (Buffer & 0xFFFFFF) == 0xBFBBEF )
    {
      v10 = 1;
    }
    else if ( (_WORD)Buffer == 0xFEFF )
    {
      v4 = 2;
      v10 = 2;
    }
    else
    {
      v4 = 0;
      v10 = 0;
    }
    if ( !SetFilePointerEx(FileW, (LARGE_INTEGER)v4, 0, 0) )
    {
      v9 = 68;
      goto LABEL_13;
    }
    FileSize.QuadPart = 0;
    if ( !GetFileSizeEx(FileW, &FileSize) )
    {
      v9 = 71;
      goto LABEL_13;
    }
    if ( FileSize.QuadPart >= 0xFFFFFFFFLL )
    {
      LastError = -2147024362;
      v11 = 72;
      v12 = 2147942934LL;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotconfigurationfile.cpp",
        (const char *)v12,
        lpOverlapped);
      goto LABEL_59;
    }
    v13 = FileSize.LowPart - v4;
    if ( FileSize.LowPart == v4 )
    {
      v14 = *a2;
      if ( *a2 )
      {
        v15 = GetLastError();
        WindowsDeleteString(v14);
        SetLastError(v15);
      }
      *a2 = 0;
      String = WindowsCreateString(0, 0, a2);
      LastError = String;
      if ( String < 0 )
      {
        v12 = (unsigned int)String;
        v11 = 77;
        goto LABEL_18;
      }
LABEL_58:
      LastError = 0;
      goto LABEL_59;
    }
    bufferHandle = 0;
    if ( v10 == 2 )
    {
      if ( (v13 & 1) != 0 )
      {
        LastError = -2147024883;
        v17 = 94;
LABEL_27:
        v18 = LastError;
        goto LABEL_28;
      }
      charBuffer = 0;
      v19 = WindowsPreallocateStringBuffer(v13 >> 1, &charBuffer, &bufferHandle);
      LastError = v19;
      if ( v19 < 0 )
      {
        v18 = (unsigned int)v19;
        v17 = 99;
LABEL_28:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v17,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotconfigurationfile.cpp",
          (const char *)v18,
          lpOverlapped);
        if ( bufferHandle )
          WindowsDeleteStringBuffer(bufferHandle);
        goto LABEL_59;
      }
      v20 = charBuffer;
      v21 = 0;
    }
    else
    {
      v22 = CoTaskMemAlloc(v13);
      v21 = v22;
      if ( !v22 )
      {
        LastError = -2147024882;
        v17 = 107;
        goto LABEL_27;
      }
      v3 = 0;
      v20 = (WCHAR *)v22;
    }
    v38 = 0;
    if ( !ReadFile(FileW, v20, v13, &v38, 0) )
    {
      v24 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x76,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotconfigurationfile.cpp",
              v23);
LABEL_38:
      if ( bufferHandle )
        WindowsDeleteStringBuffer(bufferHandle);
      if ( v21 )
        CoTaskMemFree(v21);
      LastError = v24;
      goto LABEL_59;
    }
    if ( v13 != v38 )
    {
      v24 = -2147418113;
      v25 = 122;
LABEL_45:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v25,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotconfigurationfile.cpp",
        (const char *)(unsigned int)v24,
        lpOverlappeda);
      goto LABEL_38;
    }
    if ( v3 )
    {
      v26 = *a2;
      if ( *a2 )
      {
        v27 = GetLastError();
        WindowsDeleteString(v26);
        SetLastError(v27);
      }
      v28 = bufferHandle;
      *a2 = 0;
      v24 = WindowsPromoteStringBuffer(v28, a2);
      if ( v24 < 0 )
      {
        v25 = 126;
        goto LABEL_45;
      }
      bufferHandle = 0;
    }
    else
    {
      v24 = Microsoft::Windows::Autopilot::AutoPilotStringFile::ConvertRawBytesToString(
              v10 != 0 ? 0xFDE9 : 0,
              (LPCCH)v21,
              v13,
              a2);
      if ( v24 < 0 )
      {
        v25 = 131;
        goto LABEL_45;
      }
      if ( bufferHandle )
        WindowsDeleteStringBuffer(bufferHandle);
    }
    if ( v21 )
      CoTaskMemFree(v21);
    goto LABEL_58;
  }
  LastError = wil::details::GetLastErrorFailHr(v5);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    goto LABEL_59;
  return LastError;
}

```

## disassembly

```asm
0x18002553c  mov     rax, rsp
0x18002553f  mov     [rax+8], rbx
0x180025543  push    rbp
0x180025544  push    rsi
0x180025545  push    rdi
0x180025546  push    r12
0x180025548  push    r13
0x18002554a  push    r14
0x18002554c  push    r15
0x18002554e  mov     rbp, rsp
0x180025551  sub     rsp, 60h
0x180025555  xor     r13d, r13d
0x180025558  mov     r14, rdx
0x18002555b  mov     [rax-68h], r13
0x18002555f  xor     r9d, r9d; lpSecurityAttributes
0x180025562  mov     [rax-70h], r13d
0x180025566  mov     edx, 120089h; dwDesiredAccess
0x18002556b  lea     r12d, [r13+1]
0x18002556f  lea     ebx, [r13+3]
0x180025573  mov     r8d, r12d; dwShareMode
0x180025576  mov     [rax-78h], ebx
0x180025579  call    cs:__imp_CreateFileW
0x18002557f  mov     rsi, rax
0x180025582  inc     rax
0x180025585  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002558b  jnz     short loc_1800255A7
0x18002558d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180025592  lea     rcx, [rsi-1]
0x180025596  mov     ebx, eax
0x180025598  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002559c  ja      loc_18002586B
0x1800255a2  jmp     loc_180025862
0x1800255a7  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800255ab  mov     [rbp+Buffer], r13d
0x1800255af  mov     r8d, 4; nNumberOfBytesToRead
0x1800255b5  mov     [rbp+NumberOfBytesRead], r13d
0x1800255b9  lea     rdx, [rbp+Buffer]; lpBuffer
0x1800255bd  mov     qword ptr [rsp+60h+lpOverlapped], r13; int
0x1800255c2  mov     rcx, rsi; hFile
0x1800255c5  call    cs:__imp_ReadFile
0x1800255cb  test    eax, eax
0x1800255cd  jnz     short loc_1800255D4
0x1800255cf  lea     edx, [rax+39h]
0x1800255d2  jmp     short loc_18002561A
0x1800255d4  mov     eax, [rbp+Buffer]
0x1800255d7  mov     ecx, 2
0x1800255dc  and     eax, 0FFFFFFh
0x1800255e1  cmp     eax, 0BFBBEFh
0x1800255e6  jnz     short loc_1800255ED
0x1800255e8  mov     r15d, r12d
0x1800255eb  jmp     short loc_180025602
0x1800255ed  cmp     word ptr [rbp+Buffer], 0FEFFh
0x1800255f3  jnz     short loc_1800255FC
0x1800255f5  mov     ebx, ecx
0x1800255f7  mov     r15d, ecx
0x1800255fa  jmp     short loc_180025602
0x1800255fc  mov     ebx, r13d
0x1800255ff  mov     r15d, r13d
0x180025602  mov     edx, ebx; liDistanceToMove
0x180025604  xor     r9d, r9d; dwMoveMethod
0x180025607  xor     r8d, r8d; lpNewFilePointer
0x18002560a  mov     rcx, rsi; hFile
0x18002560d  call    cs:__imp_SetFilePointerEx
0x180025613  test    eax, eax
0x180025615  jnz     short loc_180025631
0x180025617  lea     edx, [rax+44h]; void *
0x18002561a  mov     rcx, [rbp+38h]; this
0x18002561e  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\moderndeployment\\au"...
0x180025625  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002562a  mov     ebx, eax
0x18002562c  jmp     loc_180025862
0x180025631  lea     rdx, [rbp+FileSize]; lpFileSize
0x180025635  mov     qword ptr [rbp+FileSize], r13
0x180025639  mov     rcx, rsi; hFile
0x18002563c  call    cs:__imp_GetFileSizeEx
0x180025642  test    eax, eax
0x180025644  jnz     short loc_18002564B
0x180025646  lea     edx, [rax+47h]
0x180025649  jmp     short loc_18002561A
0x18002564b  mov     rdi, qword ptr [rbp+FileSize]
0x18002564f  mov     eax, 0FFFFFFFFh
0x180025654  cmp     rdi, rax
0x180025657  jl      short loc_18002567B
0x180025659  mov     ebx, 80070216h
0x18002565e  mov     edx, 48h ; 'H'; void *
0x180025663  mov     r9d, ebx; char *
0x180025666  mov     rcx, [rbp+38h]; this
0x18002566a  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\moderndeployment\\au"...
0x180025671  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025676  jmp     loc_180025862
0x18002567b  sub     edi, ebx
0x18002567d  jnz     short loc_1800256C4
0x18002567f  mov     rdi, [r14]
0x180025682  test    rdi, rdi
0x180025685  jz      short loc_1800256A0
0x180025687  call    cs:__imp_GetLastError
0x18002568d  mov     rcx, rdi; string
0x180025690  mov     ebx, eax
0x180025692  call    cs:__imp_WindowsDeleteString
0x180025698  mov     ecx, ebx; dwErrCode
0x18002569a  call    cs:__imp_SetLastError
0x1800256a0  mov     r8, r14; string
0x1800256a3  mov     [r14], r13
0x1800256a6  xor     edx, edx; length
0x1800256a8  xor     ecx, ecx; sourceString
0x1800256aa  call    cs:__imp_WindowsCreateString
0x1800256b0  mov     ebx, eax
0x1800256b2  test    eax, eax
0x1800256b4  jns     loc_18002585F
0x1800256ba  mov     r9d, eax
0x1800256bd  mov     edx, 4Dh ; 'M'
0x1800256c2  jmp     short loc_180025666
0x1800256c4  mov     [rbp+bufferHandle], r13
0x1800256c8  cmp     r15d, 2
0x1800256cc  jnz     short loc_180025736
0x1800256ce  test    r12b, dil
0x1800256d1  jz      short loc_180025707
0x1800256d3  mov     ebx, 8007000Dh
0x1800256d8  lea     edx, [r15+5Ch]; void *
0x1800256dc  mov     r9d, ebx; char *
0x1800256df  mov     rcx, [rbp+38h]; this
0x1800256e3  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800256ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800256ef  mov     rcx, [rbp+bufferHandle]; bufferHandle
0x1800256f3  test    rcx, rcx
0x1800256f6  jz      loc_180025862
0x1800256fc  call    cs:__imp_WindowsDeleteStringBuffer
0x180025702  jmp     loc_180025862
0x180025707  mov     ecx, edi
0x180025709  mov     [rbp+charBuffer], r13
0x18002570d  shr     ecx, 1; length
0x18002570f  lea     r8, [rbp+bufferHandle]; bufferHandle
0x180025713  lea     rdx, [rbp+charBuffer]; charBuffer
0x180025717  call    cs:__imp_WindowsPreallocateStringBuffer
0x18002571d  mov     ebx, eax
0x18002571f  test    eax, eax
0x180025721  jns     short loc_18002572D
0x180025723  mov     r9d, eax
0x180025726  mov     edx, 63h ; 'c'
0x18002572b  jmp     short loc_1800256DF
0x18002572d  mov     rdx, [rbp+charBuffer]
0x180025731  mov     rbx, r13
0x180025734  jmp     short loc_180025756
0x180025736  mov     ecx, edi; cb
0x180025738  call    cs:__imp_CoTaskMemAlloc
0x18002573e  mov     rbx, rax
0x180025741  test    rax, rax
0x180025744  jnz     short loc_180025750
0x180025746  mov     ebx, 8007000Eh
0x18002574b  lea     edx, [rax+6Bh]
0x18002574e  jmp     short loc_1800256DC
0x180025750  mov     r12b, r13b
0x180025753  mov     rdx, rax; lpBuffer
0x180025756  lea     r9, [rbp+arg_18]; lpNumberOfBytesRead
0x18002575a  mov     [rbp+arg_18], r13d
0x18002575e  mov     r8d, edi; nNumberOfBytesToRead
0x180025761  mov     qword ptr [rsp+60h+lpOverlapped], r13; int
0x180025766  mov     rcx, rsi; hFile
0x180025769  call    cs:__imp_ReadFile
0x18002576f  test    eax, eax
0x180025771  jnz     short loc_1800257AC
0x180025773  mov     rcx, [rbp+38h]; this
0x180025777  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\moderndeployment\\au"...
0x18002577e  lea     edx, [rax+76h]; void *
0x180025781  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180025786  mov     edi, eax
0x180025788  mov     rcx, [rbp+bufferHandle]; bufferHandle
0x18002578c  test    rcx, rcx
0x18002578f  jz      short loc_180025797
0x180025791  call    cs:__imp_WindowsDeleteStringBuffer
0x180025797  test    rbx, rbx
0x18002579a  jz      short loc_1800257A5
0x18002579c  mov     rcx, rbx; pv
0x18002579f  call    cs:__imp_CoTaskMemFree
0x1800257a5  mov     ebx, edi
0x1800257a7  jmp     loc_180025862
0x1800257ac  cmp     edi, [rbp+arg_18]
0x1800257af  jz      short loc_1800257D0
0x1800257b1  mov     edi, 8000FFFFh
0x1800257b6  mov     edx, 7Ah ; 'z'; void *
0x1800257bb  mov     rcx, [rbp+38h]; this
0x1800257bf  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800257c6  mov     r9d, edi; char *
0x1800257c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800257ce  jmp     short loc_180025788
0x1800257d0  test    r12b, r12b
0x1800257d3  jz      short loc_180025819
0x1800257d5  mov     r15, [r14]
0x1800257d8  test    r15, r15
0x1800257db  jz      short loc_1800257F6
0x1800257dd  call    cs:__imp_GetLastError
0x1800257e3  mov     rcx, r15; string
0x1800257e6  mov     edi, eax
0x1800257e8  call    cs:__imp_WindowsDeleteString
0x1800257ee  mov     ecx, edi; dwErrCode
0x1800257f0  call    cs:__imp_SetLastError
0x1800257f6  mov     rcx, [rbp+bufferHandle]; bufferHandle
0x1800257fa  mov     rdx, r14; string
0x1800257fd  mov     [r14], r13
0x180025800  call    cs:__imp_WindowsPromoteStringBuffer
0x180025806  mov     edi, eax
0x180025808  test    eax, eax
0x18002580a  js      short loc_180025812
0x18002580c  mov     [rbp+bufferHandle], r13
0x180025810  jmp     short loc_180025851
0x180025812  mov     edx, 7Eh ; '~'
0x180025817  jmp     short loc_1800257BB
0x180025819  neg     r15d
0x18002581c  mov     r9, r14; string
0x18002581f  mov     r8d, edi; cbMultiByte
0x180025822  mov     rdx, rbx; lpMultiByteStr
0x180025825  sbb     ecx, ecx
0x180025827  and     ecx, 0FDE9h; CodePage
0x18002582d  call    ?ConvertRawBytesToString@AutoPilotStringFile@Autopilot@Windows@Microsoft@@SAJIPEBDHAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Autopilot::AutoPilotStringFile::ConvertRawBytesToString(uint,char const *,int,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)
0x180025832  mov     edi, eax
0x180025834  test    eax, eax
0x180025836  jns     short loc_180025842
0x180025838  mov     edx, 83h
0x18002583d  jmp     loc_1800257BB
0x180025842  mov     rcx, [rbp+bufferHandle]; bufferHandle
0x180025846  test    rcx, rcx
0x180025849  jz      short loc_180025851
0x18002584b  call    cs:__imp_WindowsDeleteStringBuffer
0x180025851  test    rbx, rbx
0x180025854  jz      short loc_18002585F
0x180025856  mov     rcx, rbx; pv
0x180025859  call    cs:__imp_CoTaskMemFree
0x18002585f  mov     ebx, r13d
0x180025862  mov     rcx, rsi; hObject
0x180025865  call    cs:__imp_CloseHandle
0x18002586b  mov     eax, ebx
0x18002586d  mov     rbx, [rsp+60h+arg_0]
0x180025875  add     rsp, 60h
0x180025879  pop     r15
0x18002587b  pop     r14
0x18002587d  pop     r13
0x18002587f  pop     r12
0x180025881  pop     rdi
0x180025882  pop     rsi
0x180025883  pop     rbp
0x180025884  retn
```
