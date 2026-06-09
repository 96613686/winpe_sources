# CbsOfflineUtil::CreateTemporyFolderForShimBinary(void)

- ea: `0x18003f960`
- end: `0x18003fafc`
- name: `?CreateTemporyFolderForShimBinary@CbsOfflineUtil@@AEAAJXZ`
- size: `412`
- prototype: `__int64 __fastcall(CbsOfflineUtil *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18003f250`

## callees

- `0x1800104e4`
- `0x18001e4fc`
- `0x18001e51c`
- `0x18001fd10`
- `0x1800293a0`
- `0x18003f818`
- `0x18003f960`
- `0x18006c1d0`
- `0x180099cb0`

## import_xrefs

- `KERNEL32!CreateDirectoryW` at `0x18003fa75`
- `KERNEL32!CreateDirectoryW` at `0x18003fa75`
- `OLE32!StringFromGUID2` at `0x18003fa1f`
- `OLE32!StringFromGUID2` at `0x18003fa1f`
- `OLE32!CoCreateGuid` at `0x18003f9dd`
- `OLE32!CoCreateGuid` at `0x18003f9dd`

## pseudocode

```c
__int64 __fastcall CbsOfflineUtil::CreateTemporyFolderForShimBinary(CbsOfflineUtil *this)
{
  HRESULT TemporaryPath; // eax
  unsigned int LastError; // ebx
  __int64 v4; // rdx
  LPCWSTR v5; // rdi
  const char *v6; // r9
  bool v8; // zf
  LPCWSTR lpPathName; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v10[3]; // [rsp+28h] [rbp-D8h] BYREF
  GUID pguid; // [rsp+40h] [rbp-C0h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[264]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  memset(Buffer, 0, 0x208u);
  pguid = 0;
  memset(sz, 0, sizeof(sz));
  lpPathName = 0;
  TemporaryPath = GetTemporaryPath(0x104u, Buffer);
  LastError = TemporaryPath;
  if ( TemporaryPath < 0 )
  {
    v4 = 75;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
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
    v4 = 76;
    goto LABEL_5;
  }
  StringFromGUID2(&pguid, sz, 40);
  v10[0] = L"\\\\?\\";
  v10[1] = Buffer;
  v10[2] = sz;
  TemporaryPath = ConcatManyStrings(3, v10, &lpPathName);
  LastError = TemporaryPath;
  if ( TemporaryPath < 0 )
  {
    v4 = 84;
    goto LABEL_5;
  }
  v5 = lpPathName;
  if ( !CreateDirectoryW(lpPathName, 0) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x56,
                  (unsigned int)"onecore\\base\\cbs\\offlineutil\\cbsofflineimagestack.cpp",
                  v6);
    goto LABEL_10;
  }
  Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close((char *)this + 16);
  v8 = *((_QWORD *)this + 2) == 0;
  lpPathName = 0;
  if ( !v8 )
  {
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x18003FAFBLL);
  }
  *((_QWORD *)this + 2) = v5;
  Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(&lpPathName);
  return 0;
}

```

## disassembly

```asm
0x18003f960  push    rbp
0x18003f962  push    rbx
0x18003f963  push    rsi
0x18003f964  push    rdi
0x18003f965  lea     rbp, [rsp-1C8h]
0x18003f96d  sub     rsp, 2C8h
0x18003f974  mov     rax, cs:__security_cookie
0x18003f97b  xor     rax, rsp
0x18003f97e  mov     [rbp+1E0h+var_30], rax
0x18003f985  mov     rsi, rcx
0x18003f988  xor     edx, edx; Val
0x18003f98a  lea     rcx, [rbp+1E0h+Buffer]; void *
0x18003f98e  mov     r8d, 208h; Size
0x18003f994  call    memset
0x18003f999  xor     edx, edx; Val
0x18003f99b  lea     rcx, [rsp+2E0h+sz]; void *
0x18003f9a0  xorps   xmm0, xmm0
0x18003f9a3  movups  xmmword ptr [rsp+2E0h+pguid.Data1], xmm0
0x18003f9a8  lea     r8d, [rdx+50h]; Size
0x18003f9ac  call    memset
0x18003f9b1  xor     r8d, r8d
0x18003f9b4  mov     [rsp+2E0h+lpPathName], 0; int
0x18003f9bd  lea     rdx, [rbp+1E0h+Buffer]; lpBuffer
0x18003f9c1  mov     ecx, 104h; nBufferLength
0x18003f9c6  call    GetTemporaryPath
0x18003f9cb  mov     ebx, eax
0x18003f9cd  test    eax, eax
0x18003f9cf  jns     short loc_18003F9D8
0x18003f9d1  mov     edx, 4Bh ; 'K'
0x18003f9d6  jmp     short loc_18003F9F4
0x18003f9d8  lea     rcx, [rsp+2E0h+pguid]; pguid
0x18003f9dd  call    cs:__imp_CoCreateGuid
0x18003f9e4  nop     dword ptr [rax+rax+00h]
0x18003f9e9  mov     ebx, eax
0x18003f9eb  test    eax, eax
0x18003f9ed  jns     short loc_18003FA0F
0x18003f9ef  mov     edx, 4Ch ; 'L'; void *
0x18003f9f4  mov     rcx, [rbp+1E8h]; this
0x18003f9fb  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\offlineutil\\cbsoff"...
0x18003fa02  mov     r9d, eax; char *
0x18003fa05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fa0a  jmp     loc_18003FA9D
0x18003fa0f  mov     r8d, 28h ; '('; cchMax
0x18003fa15  lea     rdx, [rsp+2E0h+sz]; lpsz
0x18003fa1a  lea     rcx, [rsp+2E0h+pguid]; rguid
0x18003fa1f  call    cs:__imp_StringFromGUID2
0x18003fa26  nop     dword ptr [rax+rax+00h]
0x18003fa2b  lea     rax, String1; "\\\\?\\"
0x18003fa32  mov     ecx, 3
0x18003fa37  mov     [rsp+2E0h+var_2B8], rax
0x18003fa3c  lea     r8, [rsp+2E0h+lpPathName]
0x18003fa41  lea     rax, [rbp+1E0h+Buffer]
0x18003fa45  mov     [rsp+2E0h+var_2B0], rax
0x18003fa4a  lea     rdx, [rsp+2E0h+var_2B8]
0x18003fa4f  lea     rax, [rsp+2E0h+sz]
0x18003fa54  mov     [rsp+2E0h+var_2A8], rax
0x18003fa59  call    ConcatManyStrings
0x18003fa5e  mov     ebx, eax
0x18003fa60  test    eax, eax
0x18003fa62  jns     short loc_18003FA6B
0x18003fa64  mov     edx, 54h ; 'T'
0x18003fa69  jmp     short loc_18003F9F4
0x18003fa6b  mov     rdi, [rsp+2E0h+lpPathName]
0x18003fa70  xor     edx, edx; lpSecurityAttributes
0x18003fa72  mov     rcx, rdi; lpPathName
0x18003fa75  call    cs:__imp_CreateDirectoryW
0x18003fa7c  nop     dword ptr [rax+rax+00h]
0x18003fa81  test    eax, eax
0x18003fa83  jnz     short loc_18003FAAB
0x18003fa85  mov     rcx, [rbp+1E8h]; this
0x18003fa8c  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\offlineutil\\cbsoff"...
0x18003fa93  lea     edx, [rax+56h]; void *
0x18003fa96  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003fa9b  mov     ebx, eax
0x18003fa9d  lea     rcx, [rsp+2E0h+lpPathName]
0x18003faa2  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoHeapPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(void)
0x18003faa7  mov     eax, ebx
0x18003faa9  jmp     short loc_18003FAD5
0x18003faab  lea     rbx, [rsi+10h]
0x18003faaf  mov     rcx, rbx
0x18003fab2  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoHeapPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(void)
0x18003fab7  cmp     qword ptr [rbx], 0
0x18003fabb  mov     [rsp+2E0h+lpPathName], 0
0x18003fac4  jnz     short loc_18003FAF1
0x18003fac6  lea     rcx, [rsp+2E0h+lpPathName]
0x18003facb  mov     [rbx], rdi
0x18003face  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoHeapPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(void)
0x18003fad3  xor     eax, eax
0x18003fad5  mov     rcx, [rbp+1E0h+var_30]
0x18003fadc  xor     rcx, rsp; StackCookie
0x18003fadf  call    __security_check_cookie
0x18003fae4  add     rsp, 2C8h
0x18003faeb  pop     rdi
0x18003faec  pop     rsi
0x18003faed  pop     rbx
0x18003faee  pop     rbp
0x18003faef  retn
0x18003faf1  mov     ecx, 0C00000E5h; int
0x18003faf6  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
