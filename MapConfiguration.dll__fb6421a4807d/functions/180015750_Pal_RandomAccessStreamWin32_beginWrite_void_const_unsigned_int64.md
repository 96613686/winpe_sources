# Pal::RandomAccessStreamWin32::beginWrite(void const *,unsigned __int64)

- ea: `0x180015750`
- end: `0x180015850`
- name: `?beginWrite@RandomAccessStreamWin32@Pal@@UEAA?AV?$shared_ptr@V?$AsyncOperation@_K@Pal@@@std@@PEBX_K@Z`
- size: `256`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callees

- `0x18000cb24`
- `0x18000fac4`
- `0x180010f34`
- `0x180013da8`
- `0x180015750`
- `0x180016330`
- `0x18001646c`
- `0x180016bc0`
- `0x180016ce8`
- `0x18001b824`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800157e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800157e9`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800157df`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800157df`

## pseudocode

```c
struct _OVERLAPPED **__fastcall Pal::RandomAccessStreamWin32::beginWrite(
        Pal::RandomAccessStreamWin32 *a1,
        struct _OVERLAPPED **a2,
        const void *a3,
        DWORD a4)
{
  __int64 v8; // rax
  _QWORD *v9; // rax
  struct _OVERLAPPED *lpOverlapped; // rdx
  DWORD LastError; // eax
  unsigned int *v12; // rax
  _QWORD *Failed; // rax
  struct _OVERLAPPED *v15; // [rsp+38h] [rbp-40h] BYREF
  std::_Ref_count_base *v16; // [rsp+40h] [rbp-38h]
  _BYTE v17[16]; // [rsp+48h] [rbp-30h] BYREF
  _QWORD v18[4]; // [rsp+58h] [rbp-20h] BYREF
  char v19; // [rsp+B0h] [rbp+38h] BYREF

  Pal::RandomAccessStreamWin32::ensureNotClosed(a1);
  v8 = Core::requirePresent<MapControl::LocaleMapConfiguration>((__int64)v17, (_QWORD *)a1 + 1);
  Pal::StreamOperationWin32::create(&v15, v8);
  Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(v17);
  v9 = std::shared_ptr<Pal::Detail::WrlTimerWrapper>::shared_ptr<Pal::Detail::WrlTimerWrapper>(v18, &v15);
  Pal::UntypedAsyncOperationCancelList::add((char *)a1 + 32, v9);
  lpOverlapped = v15 + 8;
  v15[8].Pointer = (PVOID)*((_QWORD *)a1 + 3);
  if ( WriteFile(**((HANDLE **)a1 + 1), a3, a4, 0, lpOverlapped) || (LastError = GetLastError(), LastError == 997) )
  {
    *a2 = v15;
    a2[1] = (struct _OVERLAPPED *)v16;
  }
  else
  {
    v12 = (unsigned int *)PalWindows::errorCodeFromWin32Error(&v19, LastError);
    Failed = (_QWORD *)Pal::AsyncOperation<unsigned __int64>::createFailed(v18, *v12);
    std::shared_ptr<Pal::Detail::WrlTimerWrapper>::shared_ptr<Pal::Detail::WrlTimerWrapper>(a2, Failed);
    Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(v18);
    if ( v16 )
      std::_Ref_count_base::_Decref(v16);
  }
  return a2;
}

```

## disassembly

```asm
0x180015750  push    rbp
0x180015752  push    rbx
0x180015753  push    rsi
0x180015754  push    rdi
0x180015755  push    r14
0x180015757  push    r15
0x180015759  mov     rbp, rsp
0x18001575c  sub     rsp, 78h
0x180015760  mov     rsi, r9
0x180015763  mov     r14, r8
0x180015766  mov     r15, rdx
0x180015769  mov     rdi, rcx
0x18001576c  call    ?ensureNotClosed@RandomAccessStreamWin32@Pal@@AEAAXXZ; Pal::RandomAccessStreamWin32::ensureNotClosed(void)
0x180015771  lea     rdx, [rdi+8]
0x180015775  lea     rcx, [rbp+var_30]
0x180015779  call    ??$requirePresent@VLocaleMapConfiguration@MapControl@@@Core@@YA?AV?$PresentSharedPtr@VLocaleMapConfiguration@MapControl@@@0@AEBV?$shared_ptr@VLocaleMapConfiguration@MapControl@@@std@@@Z; Core::requirePresent<MapControl::LocaleMapConfiguration>(std::shared_ptr<MapControl::LocaleMapConfiguration> const &)
0x18001577e  nop
0x18001577f  mov     rdx, rax
0x180015782  lea     rcx, [rbp+var_40]
0x180015786  call    ?create@StreamOperationWin32@Pal@@SA?AV?$shared_ptr@VStreamOperationWin32@Pal@@@std@@AEBV?$PresentSharedPtr@VFileHandle@Pal@@@Core@@@Z; Pal::StreamOperationWin32::create(Core::PresentSharedPtr<Pal::FileHandle> const &)
0x18001578b  nop
0x18001578c  lea     rcx, [rbp+var_30]
0x180015790  call    ??1?$PresentSharedPtr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@Core@@QEAA@XZ; Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(void)
0x180015795  lea     rdx, [rbp+var_40]
0x180015799  lea     rcx, [rbp+var_20]
0x18001579d  call    ??0?$shared_ptr@VWrlTimerWrapper@Detail@Pal@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Pal::Detail::WrlTimerWrapper>::shared_ptr<Pal::Detail::WrlTimerWrapper>(std::shared_ptr<Pal::Detail::WrlTimerWrapper> const &)
0x1800157a2  lea     rcx, [rdi+20h]
0x1800157a6  mov     rdx, rax
0x1800157a9  call    ?add@UntypedAsyncOperationCancelList@Pal@@QEAAXV?$shared_ptr@VUntypedAsyncOperation@Pal@@@std@@@Z; Pal::UntypedAsyncOperationCancelList::add(std::shared_ptr<Pal::UntypedAsyncOperation>)
0x1800157ae  mov     rdx, [rbp+var_40]
0x1800157b2  add     rdx, 100h
0x1800157b9  mov     eax, [rdi+18h]
0x1800157bc  mov     [rdx+10h], eax
0x1800157bf  mov     rax, [rdi+18h]
0x1800157c3  shr     rax, 20h
0x1800157c7  mov     [rdx+14h], eax
0x1800157ca  mov     r8d, esi; nNumberOfBytesToWrite
0x1800157cd  mov     rcx, [rdi+8]
0x1800157d1  mov     [rsp+78h+lpOverlapped], rdx; lpOverlapped
0x1800157d6  xor     r9d, r9d; lpNumberOfBytesWritten
0x1800157d9  mov     rdx, r14; lpBuffer
0x1800157dc  mov     rcx, [rcx]; hFile
0x1800157df  call    cs:__imp_WriteFile
0x1800157e5  test    eax, eax
0x1800157e7  jnz     short loc_180015831
0x1800157e9  call    cs:__imp_GetLastError
0x1800157ef  cmp     eax, 3E5h
0x1800157f4  jz      short loc_180015831
0x1800157f6  mov     edx, eax
0x1800157f8  lea     rcx, [rbp+arg_0]
0x1800157fc  call    ?errorCodeFromWin32Error@PalWindows@@YA?AVStatusCode@Core@@K@Z; PalWindows::errorCodeFromWin32Error(ulong)
0x180015801  mov     edx, [rax]
0x180015803  lea     rcx, [rbp+var_20]
0x180015807  call    ?createFailed@?$AsyncOperation@_K@Pal@@SA?AV?$PresentSharedPtr@V?$AsyncOperation@_K@Pal@@@Core@@VStatusCode@4@@Z; Pal::AsyncOperation<unsigned __int64>::createFailed(Core::StatusCode)
0x18001580c  mov     rdx, rax
0x18001580f  mov     rcx, r15
0x180015812  call    ??0?$shared_ptr@VWrlTimerWrapper@Detail@Pal@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Pal::Detail::WrlTimerWrapper>::shared_ptr<Pal::Detail::WrlTimerWrapper>(std::shared_ptr<Pal::Detail::WrlTimerWrapper> const &)
0x180015817  lea     rcx, [rbp+var_20]
0x18001581b  call    ??1?$PresentSharedPtr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@Core@@QEAA@XZ; Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(void)
0x180015820  nop
0x180015821  mov     rcx, [rbp+var_38]; this
0x180015825  test    rcx, rcx
0x180015828  jz      short loc_180015840
0x18001582a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001582f  jmp     short loc_180015840
0x180015831  mov     rax, [rbp+var_40]
0x180015835  mov     [r15], rax
0x180015838  mov     rax, [rbp+var_38]
0x18001583c  mov     [r15+8], rax
0x180015840  mov     rax, r15
0x180015843  add     rsp, 78h
0x180015847  pop     r15
0x180015849  pop     r14
0x18001584b  pop     rdi
0x18001584c  pop     rsi
0x18001584d  pop     rbx
0x18001584e  pop     rbp
0x18001584f  retn
```
