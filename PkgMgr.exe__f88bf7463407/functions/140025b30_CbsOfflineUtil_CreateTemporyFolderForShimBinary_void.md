# CbsOfflineUtil::CreateTemporyFolderForShimBinary(void)

- ea: `0x140025b30`
- end: `0x140025cac`
- name: `?CreateTemporyFolderForShimBinary@CbsOfflineUtil@@AEAAJXZ`
- size: `380`
- prototype: `__int64 __fastcall(CbsOfflineUtil *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1400253b0`

## callees

- `0x140002360`
- `0x140002d98`
- `0x140005684`
- `0x1400056ac`
- `0x14000731c`
- `0x1400258f0`
- `0x1400259d0`
- `0x140025b30`
- `0x140027b78`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x140025c31`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x140025c31`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x140025ba5`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x140025ba5`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140025be1`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140025be1`

## pseudocode

```c
__int64 __fastcall CbsOfflineUtil::CreateTemporyFolderForShimBinary(CbsOfflineUtil *this)
{
  __int64 v2; // rcx
  HRESULT TemporaryPath; // eax
  unsigned int LastError; // ebx
  __int64 v5; // rdx
  LPCWSTR v6; // rdi
  const char *v7; // r9
  int v9; // ecx
  bool v10; // zf
  LPCWSTR lpPathName; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v12[3]; // [rsp+28h] [rbp-D8h] BYREF
  GUID pguid; // [rsp+40h] [rbp-C0h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v15[528]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  memset_0(v15, 0, 0x208u);
  pguid = 0;
  memset_0(sz, 0, sizeof(sz));
  lpPathName = 0;
  TemporaryPath = GetTemporaryPath(v2, v15);
  LastError = TemporaryPath;
  if ( TemporaryPath < 0 )
  {
    v5 = 75;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\cbs\\offlineutil\\cbsofflineimagestack.cpp",
      (const char *)(unsigned int)TemporaryPath,
      (int)lpPathName);
LABEL_10:
    Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(&lpPathName);
    return LastError;
  }
  TemporaryPath = CoCreateGuid(&pguid);
  LastError = TemporaryPath;
  if ( TemporaryPath < 0 )
  {
    v5 = 76;
    goto LABEL_5;
  }
  StringFromGUID2(&pguid, sz, 40);
  v12[0] = L"\\\\?\\";
  v12[1] = v15;
  v12[2] = sz;
  TemporaryPath = ConcatManyStrings(3, v12, &lpPathName);
  LastError = TemporaryPath;
  if ( TemporaryPath < 0 )
  {
    v5 = 84;
    goto LABEL_5;
  }
  v6 = lpPathName;
  if ( !CreateDirectoryW(lpPathName, 0) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x56,
                  (unsigned int)"onecore\\base\\cbs\\offlineutil\\cbsofflineimagestack.cpp",
                  v7);
    goto LABEL_10;
  }
  Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close((char *)this + 16);
  v10 = *((_QWORD *)this + 2) == 0;
  lpPathName = 0;
  if ( !v10 )
    INTERNAL_ERROR_ACTION(v9);
  *((_QWORD *)this + 2) = v6;
  Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(&lpPathName);
  return 0;
}

```

## disassembly

```asm
0x140025b30  push    rbp
0x140025b32  push    rbx
0x140025b33  push    rsi
0x140025b34  push    rdi
0x140025b35  lea     rbp, [rsp-1C8h]
0x140025b3d  sub     rsp, 2C8h
0x140025b44  mov     rax, cs:__security_cookie
0x140025b4b  xor     rax, rsp
0x140025b4e  mov     [rbp+1E0h+var_30], rax
0x140025b55  mov     rsi, rcx
0x140025b58  xor     edx, edx; Val
0x140025b5a  lea     rcx, [rbp+1E0h+var_240]; void *
0x140025b5e  mov     r8d, 208h; Size
0x140025b64  call    memset_0
0x140025b69  xor     edx, edx; Val
0x140025b6b  lea     rcx, [rsp+2E0h+sz]; void *
0x140025b70  xorps   xmm0, xmm0
0x140025b73  movups  xmmword ptr [rsp+2E0h+pguid.Data1], xmm0
0x140025b78  lea     r8d, [rdx+50h]; Size
0x140025b7c  call    memset_0
0x140025b81  lea     rdx, [rbp+1E0h+var_240]
0x140025b85  mov     [rsp+2E0h+lpPathName], 0; int
0x140025b8e  call    GetTemporaryPath
0x140025b93  mov     ebx, eax
0x140025b95  test    eax, eax
0x140025b97  jns     short loc_140025BA0
0x140025b99  mov     edx, 4Bh ; 'K'
0x140025b9e  jmp     short loc_140025BB6
0x140025ba0  lea     rcx, [rsp+2E0h+pguid]; pguid
0x140025ba5  call    cs:__imp_CoCreateGuid
0x140025bab  mov     ebx, eax
0x140025bad  test    eax, eax
0x140025baf  jns     short loc_140025BD1
0x140025bb1  mov     edx, 4Ch ; 'L'; void *
0x140025bb6  mov     rcx, [rbp+1E8h]; this
0x140025bbd  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\offlineutil\\cbsoff"...
0x140025bc4  mov     r9d, eax; char *
0x140025bc7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140025bcc  jmp     loc_140025C53
0x140025bd1  mov     r8d, 28h ; '('; cchMax
0x140025bd7  lea     rdx, [rsp+2E0h+sz]; lpsz
0x140025bdc  lea     rcx, [rsp+2E0h+pguid]; rguid
0x140025be1  call    cs:__imp_StringFromGUID2
0x140025be7  lea     rax, asc_14002FB90; "\\\\?\\"
0x140025bee  mov     ecx, 3
0x140025bf3  mov     [rsp+2E0h+var_2B8], rax
0x140025bf8  lea     r8, [rsp+2E0h+lpPathName]
0x140025bfd  lea     rax, [rbp+1E0h+var_240]
0x140025c01  mov     [rsp+2E0h+var_2B0], rax
0x140025c06  lea     rdx, [rsp+2E0h+var_2B8]
0x140025c0b  lea     rax, [rsp+2E0h+sz]
0x140025c10  mov     [rsp+2E0h+var_2A8], rax
0x140025c15  call    ConcatManyStrings
0x140025c1a  mov     ebx, eax
0x140025c1c  test    eax, eax
0x140025c1e  jns     short loc_140025C27
0x140025c20  mov     edx, 54h ; 'T'
0x140025c25  jmp     short loc_140025BB6
0x140025c27  mov     rdi, [rsp+2E0h+lpPathName]
0x140025c2c  xor     edx, edx; lpSecurityAttributes
0x140025c2e  mov     rcx, rdi; lpPathName
0x140025c31  call    cs:__imp_CreateDirectoryW
0x140025c37  test    eax, eax
0x140025c39  jnz     short loc_140025C61
0x140025c3b  mov     rcx, [rbp+1E8h]; this
0x140025c42  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\offlineutil\\cbsoff"...
0x140025c49  lea     edx, [rax+56h]; void *
0x140025c4c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140025c51  mov     ebx, eax
0x140025c53  lea     rcx, [rsp+2E0h+lpPathName]
0x140025c58  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoHeapPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(void)
0x140025c5d  mov     eax, ebx
0x140025c5f  jmp     short loc_140025C8B
0x140025c61  lea     rbx, [rsi+10h]
0x140025c65  mov     rcx, rbx
0x140025c68  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoHeapPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(void)
0x140025c6d  cmp     qword ptr [rbx], 0
0x140025c71  mov     [rsp+2E0h+lpPathName], 0
0x140025c7a  jnz     short loc_140025CA6
0x140025c7c  lea     rcx, [rsp+2E0h+lpPathName]
0x140025c81  mov     [rbx], rdi
0x140025c84  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoHeapPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(void)
0x140025c89  xor     eax, eax
0x140025c8b  mov     rcx, [rbp+1E0h+var_30]
0x140025c92  xor     rcx, rsp; StackCookie
0x140025c95  call    __security_check_cookie
0x140025c9a  add     rsp, 2C8h
0x140025ca1  pop     rdi
0x140025ca2  pop     rsi
0x140025ca3  pop     rbx
0x140025ca4  pop     rbp
0x140025ca5  retn
0x140025ca6  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
