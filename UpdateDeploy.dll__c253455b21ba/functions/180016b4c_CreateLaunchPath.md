# CreateLaunchPath

- ea: `0x180016b4c`
- end: `0x180016d97`
- name: `CreateLaunchPath`
- size: `587`
- prototype: `__int64 __fastcall(wchar_t *Buffer, __int64, __int64, const UUID *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180016f8c`

## callees

- `0x180003180`
- `0x180003c94`
- `0x18000c640`
- `0x18000dce4`
- `0x1800110fc`
- `0x180016384`
- `0x180016b4c`
- `0x180061960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016c2d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016c2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016c1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016c1a`
- `RPCRT4!UuidToStringW` at `0x180016c99`
- `RPCRT4!UuidToStringW` at `0x180016c99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016c25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016d59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016c25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016d59`

## string_xrefs

- `0x180016d16`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\uhmgr.cpp`
- `0x180016c5c`: `Worker process launch path: %ws`
- `0x180016ccf`: `/ClassId`
- `0x180016ce0`: `/DeploymentHandlerFullPath`
- `0x180016cbe`: `/RunHandlerComServer`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CreateLaunchPath(wchar_t *Buffer, __int64 a2, __int64 a3, const UUID *a4, __int64 a5, _QWORD *a6)
{
  wchar_t *v7; // r14
  _QWORD *v8; // rdi
  __int64 v9; // rbx
  signed int v10; // esi
  __int64 v11; // rdx
  void *v12; // r12
  HANDLE v13; // r14
  DWORD LastError; // edi
  RPC_STATUS v15; // eax
  HANDLE v16; // rax
  const char *v18; // [rsp+20h] [rbp-69h]
  void *v19; // [rsp+58h] [rbp-31h] BYREF
  char v20; // [rsp+60h] [rbp-29h]
  __int64 v21; // [rsp+68h] [rbp-21h]
  wchar_t *v22; // [rsp+70h] [rbp-19h]
  __int64 v23; // [rsp+78h] [rbp-11h]
  void *lpMem; // [rsp+80h] [rbp-9h] BYREF
  HANDLE hObject; // [rsp+88h] [rbp-1h]
  RPC_WSTR StringUuid; // [rsp+90h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+4Fh]

  v23 = a3;
  v7 = Buffer;
  v22 = Buffer;
  v8 = a6;
  v21 = (__int64)a6;
  StringUuid = 0;
  v9 = -1;
  hObject = (HANDLE)-1LL;
  lpMem = 0;
  if ( !Buffer )
  {
    v10 = -2147467261;
    v11 = 57;
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\uhmgr.cpp",
      (const char *)(unsigned int)v10,
      (int)v18);
    v9 = (__int64)hObject;
    goto LABEL_20;
  }
  v19 = 0;
  v20 = 1;
  v10 = UndockedModuleLoader::Load(
          (unsigned int)L"wu.wuaucltcore",
          (unsigned int)L"wuaucltcore.exe",
          1,
          a5,
          0,
          (__int64)&v19,
          (__int64)&lpMem);
  if ( v20 )
  {
    v12 = v19;
    v13 = hObject;
    if ( hObject != (HANDLE)-1LL && hObject )
    {
      LastError = GetLastError();
      CloseHandle(v13);
      SetLastError(LastError);
      v8 = (_QWORD *)v21;
    }
    hObject = v12;
    v7 = v22;
  }
  if ( v10 < 0 )
  {
    v11 = 70;
    goto LABEL_18;
  }
  WUTrace(0, 0, 0x1000000, 4, 0, L"Worker process launch path: %ws");
  if ( StringUuid )
  {
    XPtrRpcStringFree(StringUuid);
    StringUuid = 0;
  }
  v15 = UuidToStringW(a4, &StringUuid);
  v10 = v15;
  if ( v15 >= 1 )
    v10 = (unsigned __int16)v15 | 0x80010000;
  if ( v10 < 0 )
  {
    v11 = 75;
    goto LABEL_18;
  }
  v18 = L"/DeploymentHandlerFullPath";
  v10 = StringCchPrintfW(v7, 0x14Eu, L"\"%ls\" %ls %ls %ls %ls %ls", lpMem);
  if ( v10 < 0 )
  {
    v11 = 85;
    goto LABEL_18;
  }
  v16 = hObject;
  hObject = (HANDLE)-1LL;
  *v8 = v16;
  v10 = 0;
LABEL_20:
  if ( lpMem )
  {
    SusFree(lpMem);
    lpMem = 0;
    v9 = (__int64)hObject;
  }
  if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v9);
  if ( StringUuid )
    XPtrRpcStringFree(StringUuid);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180016b4c  mov     [rsp-8+arg_8], rbx
0x180016b51  push    rbp
0x180016b52  push    rsi
0x180016b53  push    rdi
0x180016b54  push    r12
0x180016b56  push    r13
0x180016b58  push    r14
0x180016b5a  push    r15
0x180016b5c  lea     rbp, [rsp-17h]
0x180016b61  sub     rsp, 0A0h
0x180016b68  mov     rax, cs:__security_cookie
0x180016b6f  xor     rax, rsp
0x180016b72  mov     [rbp+47h+var_38], rax
0x180016b76  mov     r13, r9
0x180016b79  mov     r15, r8
0x180016b7c  mov     [rbp+47h+var_58], r8
0x180016b80  mov     r14, rcx
0x180016b83  mov     [rbp+47h+var_60], rcx
0x180016b87  mov     r9, [rbp+47h+arg_20]
0x180016b8b  mov     rdi, [rbp+47h+arg_28]
0x180016b8f  mov     [rbp+47h+var_68], rdi
0x180016b93  xor     r12d, r12d
0x180016b96  mov     [rbp+47h+StringUuid], r12
0x180016b9a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180016b9e  mov     [rbp+47h+hObject], rbx
0x180016ba2  mov     [rbp+47h+lpMem], r12
0x180016ba6  test    rcx, rcx
0x180016ba9  jnz     short loc_180016BB8
0x180016bab  mov     esi, 80004003h
0x180016bb0  lea     edx, [rcx+39h]
0x180016bb3  jmp     loc_180016D0F
0x180016bb8  lea     rax, [rbp+47h+hObject]
0x180016bbc  mov     [rbp+47h+var_80], rax
0x180016bc0  mov     [rbp+47h+var_78], r12
0x180016bc4  mov     [rbp+47h+var_70], 1
0x180016bc8  mov     [rsp+0D0h+var_98], r12
0x180016bcd  lea     rax, [rbp+47h+lpMem]
0x180016bd1  mov     [rsp+0D0h+var_A0], rax
0x180016bd6  lea     rax, [rbp+47h+var_78]
0x180016bda  mov     [rsp+0D0h+var_A8], rax
0x180016bdf  mov     qword ptr [rsp+0D0h+var_B0], r12
0x180016be4  mov     r8d, 1
0x180016bea  lea     rdx, ?c_szWuaucltCoreExe@@3QB_WB; "wuaucltcore.exe"
0x180016bf1  lea     rcx, aWuWuaucltcore; "wu.wuaucltcore"
0x180016bf8  call    UndockedModuleLoader__Load
0x180016bfd  mov     esi, eax
0x180016bff  cmp     [rbp+47h+var_70], r12b
0x180016c03  jz      short loc_180016C45
0x180016c05  mov     r12, [rbp+47h+var_78]
0x180016c09  mov     r15, [rbp+47h+var_80]
0x180016c0d  mov     r14, [r15]
0x180016c10  cmp     r14, rbx
0x180016c13  jz      short loc_180016C37
0x180016c15  test    r14, r14
0x180016c18  jz      short loc_180016C37
0x180016c1a  call    cs:__imp_GetLastError
0x180016c20  mov     edi, eax
0x180016c22  mov     rcx, r14; hObject
0x180016c25  call    cs:__imp_CloseHandle
0x180016c2b  mov     ecx, edi; dwErrCode
0x180016c2d  call    cs:__imp_SetLastError
0x180016c33  mov     rdi, [rbp+47h+var_68]
0x180016c37  mov     [r15], r12
0x180016c3a  mov     r14, [rbp+47h+var_60]
0x180016c3e  mov     r15, [rbp+47h+var_58]
0x180016c42  xor     r12d, r12d
0x180016c45  test    esi, esi
0x180016c47  jns     short loc_180016C53
0x180016c49  mov     edx, 46h ; 'F'
0x180016c4e  jmp     loc_180016D0F
0x180016c53  mov     rax, [rbp+47h+lpMem]
0x180016c57  mov     [rsp+0D0h+var_A0], rax
0x180016c5c  lea     rax, aWorkerProcessL; "Worker process launch path: %ws"
0x180016c63  mov     [rsp+0D0h+var_A8], rax
0x180016c68  mov     qword ptr [rsp+0D0h+var_B0], r12
0x180016c6d  xor     edx, edx
0x180016c6f  xor     ecx, ecx
0x180016c71  lea     r9d, [rdx+4]
0x180016c75  mov     r8d, 1000000h
0x180016c7b  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180016c80  mov     rcx, [rbp+47h+StringUuid]; void *
0x180016c84  test    rcx, rcx
0x180016c87  jz      short loc_180016C92
0x180016c89  call    ?XPtrRpcStringFree@@YAXPEAX@Z; XPtrRpcStringFree(void *)
0x180016c8e  mov     [rbp+47h+StringUuid], r12
0x180016c92  lea     rdx, [rbp+47h+StringUuid]; StringUuid
0x180016c96  mov     rcx, r13; Uuid
0x180016c99  call    cs:__imp_UuidToStringW
0x180016c9f  mov     esi, eax
0x180016ca1  cmp     eax, 1
0x180016ca4  jl      short loc_180016CAF
0x180016ca6  movzx   esi, ax
0x180016ca9  or      esi, 80010000h
0x180016caf  test    esi, esi
0x180016cb1  jns     short loc_180016CBA
0x180016cb3  mov     edx, 4Bh ; 'K'
0x180016cb8  jmp     short loc_180016D0F
0x180016cba  mov     rax, [rbp+47h+StringUuid]
0x180016cbe  lea     rcx, aRunhandlercoms; "/RunHandlerComServer"
0x180016cc5  mov     [rsp+0D0h+var_90], rcx
0x180016cca  mov     [rsp+0D0h+var_98], rax
0x180016ccf  lea     rax, aClassid; "/ClassId"
0x180016cd6  mov     [rsp+0D0h+var_A0], rax
0x180016cdb  mov     [rsp+0D0h+var_A8], r15
0x180016ce0  lea     rax, aDeploymenthand; "/DeploymentHandlerFullPath"
0x180016ce7  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x180016cec  mov     r9, [rbp+47h+lpMem]
0x180016cf0  lea     r8, aLsLsLsLsLsLs; "\"%ls\" %ls %ls %ls %ls %ls"
0x180016cf7  mov     edx, 14Eh; unsigned __int64
0x180016cfc  mov     rcx, r14; Buffer
0x180016cff  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180016d04  mov     esi, eax
0x180016d06  test    eax, eax
0x180016d08  jns     short loc_180016D28
0x180016d0a  mov     edx, 55h ; 'U'; void *
0x180016d0f  mov     rcx, [rbp+4Fh]; this
0x180016d13  mov     r9d, esi; char *
0x180016d16  lea     r8, aCW1SSrcClientU_4; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180016d1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016d22  mov     rbx, [rbp+47h+hObject]
0x180016d26  jmp     short loc_180016D36
0x180016d28  mov     rax, [rbp+47h+hObject]
0x180016d2c  mov     [rbp+47h+hObject], rbx
0x180016d30  mov     [rdi], rax
0x180016d33  mov     esi, r12d
0x180016d36  mov     rcx, [rbp+47h+lpMem]; lpMem
0x180016d3a  test    rcx, rcx
0x180016d3d  jz      short loc_180016D4C
0x180016d3f  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180016d44  mov     [rbp+47h+lpMem], r12
0x180016d48  mov     rbx, [rbp+47h+hObject]
0x180016d4c  lea     rax, [rbx-1]
0x180016d50  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180016d54  ja      short loc_180016D60
0x180016d56  mov     rcx, rbx; hObject
0x180016d59  call    cs:__imp_CloseHandle
0x180016d5f  nop
0x180016d60  mov     rcx, [rbp+47h+StringUuid]; void *
0x180016d64  test    rcx, rcx
0x180016d67  jz      short loc_180016D6E
0x180016d69  call    ?XPtrRpcStringFree@@YAXPEAX@Z; XPtrRpcStringFree(void *)
0x180016d6e  mov     eax, esi
0x180016d70  mov     rcx, [rbp+47h+var_38]
0x180016d74  xor     rcx, rsp; StackCookie
0x180016d77  call    __security_check_cookie
0x180016d7c  mov     rbx, [rsp+0D0h+arg_8]
0x180016d84  add     rsp, 0A0h
0x180016d8b  pop     r15
0x180016d8d  pop     r14
0x180016d8f  pop     r13
0x180016d91  pop     r12
0x180016d93  pop     rdi
0x180016d94  pop     rsi
0x180016d95  pop     rbp
0x180016d96  retn
```
