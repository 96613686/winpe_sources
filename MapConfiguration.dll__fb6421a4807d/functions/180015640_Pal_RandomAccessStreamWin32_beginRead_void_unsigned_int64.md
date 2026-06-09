# Pal::RandomAccessStreamWin32::beginRead(void *,unsigned __int64)

- ea: `0x180015640`
- end: `0x180015740`
- name: `?beginRead@RandomAccessStreamWin32@Pal@@UEAA?AV?$shared_ptr@V?$AsyncOperation@_K@Pal@@@std@@PEAX_K@Z`
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
- `0x180015640`
- `0x180016330`
- `0x18001646c`
- `0x180016bc0`
- `0x180016ce8`
- `0x18001b824`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800156d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800156d9`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800156cf`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800156cf`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct _OVERLAPPED **__fastcall Pal::RandomAccessStreamWin32::beginRead(
        Pal::RandomAccessStreamWin32 *a1,
        struct _OVERLAPPED **a2,
        void *a3,
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
  if ( ReadFile(**((HANDLE **)a1 + 1), a3, a4, 0, lpOverlapped) || (LastError = GetLastError(), LastError == 997) )
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
0x180015640  push    rbp
0x180015642  push    rbx
0x180015643  push    rsi
0x180015644  push    rdi
0x180015645  push    r14
0x180015647  push    r15
0x180015649  mov     rbp, rsp
0x18001564c  sub     rsp, 78h
0x180015650  mov     rsi, r9
0x180015653  mov     r14, r8
0x180015656  mov     r15, rdx
0x180015659  mov     rdi, rcx
0x18001565c  call    ?ensureNotClosed@RandomAccessStreamWin32@Pal@@AEAAXXZ; Pal::RandomAccessStreamWin32::ensureNotClosed(void)
0x180015661  lea     rdx, [rdi+8]
0x180015665  lea     rcx, [rbp+var_30]
0x180015669  call    ??$requirePresent@VLocaleMapConfiguration@MapControl@@@Core@@YA?AV?$PresentSharedPtr@VLocaleMapConfiguration@MapControl@@@0@AEBV?$shared_ptr@VLocaleMapConfiguration@MapControl@@@std@@@Z; Core::requirePresent<MapControl::LocaleMapConfiguration>(std::shared_ptr<MapControl::LocaleMapConfiguration> const &)
0x18001566e  nop
0x18001566f  mov     rdx, rax
0x180015672  lea     rcx, [rbp+var_40]
0x180015676  call    ?create@StreamOperationWin32@Pal@@SA?AV?$shared_ptr@VStreamOperationWin32@Pal@@@std@@AEBV?$PresentSharedPtr@VFileHandle@Pal@@@Core@@@Z; Pal::StreamOperationWin32::create(Core::PresentSharedPtr<Pal::FileHandle> const &)
0x18001567b  nop
0x18001567c  lea     rcx, [rbp+var_30]
0x180015680  call    ??1?$PresentSharedPtr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@Core@@QEAA@XZ; Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(void)
0x180015685  lea     rdx, [rbp+var_40]
0x180015689  lea     rcx, [rbp+var_20]
0x18001568d  call    ??0?$shared_ptr@VWrlTimerWrapper@Detail@Pal@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Pal::Detail::WrlTimerWrapper>::shared_ptr<Pal::Detail::WrlTimerWrapper>(std::shared_ptr<Pal::Detail::WrlTimerWrapper> const &)
0x180015692  lea     rcx, [rdi+20h]
0x180015696  mov     rdx, rax
0x180015699  call    ?add@UntypedAsyncOperationCancelList@Pal@@QEAAXV?$shared_ptr@VUntypedAsyncOperation@Pal@@@std@@@Z; Pal::UntypedAsyncOperationCancelList::add(std::shared_ptr<Pal::UntypedAsyncOperation>)
0x18001569e  mov     rdx, [rbp+var_40]
0x1800156a2  add     rdx, 100h
0x1800156a9  mov     eax, [rdi+18h]
0x1800156ac  mov     [rdx+10h], eax
0x1800156af  mov     rax, [rdi+18h]
0x1800156b3  shr     rax, 20h
0x1800156b7  mov     [rdx+14h], eax
0x1800156ba  mov     r8d, esi; nNumberOfBytesToRead
0x1800156bd  mov     rcx, [rdi+8]
0x1800156c1  mov     [rsp+78h+lpOverlapped], rdx; lpOverlapped
0x1800156c6  xor     r9d, r9d; lpNumberOfBytesRead
0x1800156c9  mov     rdx, r14; lpBuffer
0x1800156cc  mov     rcx, [rcx]; hFile
0x1800156cf  call    cs:__imp_ReadFile
0x1800156d5  test    eax, eax
0x1800156d7  jnz     short loc_180015721
0x1800156d9  call    cs:__imp_GetLastError
0x1800156df  cmp     eax, 3E5h
0x1800156e4  jz      short loc_180015721
0x1800156e6  mov     edx, eax
0x1800156e8  lea     rcx, [rbp+arg_0]
0x1800156ec  call    ?errorCodeFromWin32Error@PalWindows@@YA?AVStatusCode@Core@@K@Z; PalWindows::errorCodeFromWin32Error(ulong)
0x1800156f1  mov     edx, [rax]
0x1800156f3  lea     rcx, [rbp+var_20]
0x1800156f7  call    ?createFailed@?$AsyncOperation@_K@Pal@@SA?AV?$PresentSharedPtr@V?$AsyncOperation@_K@Pal@@@Core@@VStatusCode@4@@Z; Pal::AsyncOperation<unsigned __int64>::createFailed(Core::StatusCode)
0x1800156fc  mov     rdx, rax
0x1800156ff  mov     rcx, r15
0x180015702  call    ??0?$shared_ptr@VWrlTimerWrapper@Detail@Pal@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Pal::Detail::WrlTimerWrapper>::shared_ptr<Pal::Detail::WrlTimerWrapper>(std::shared_ptr<Pal::Detail::WrlTimerWrapper> const &)
0x180015707  lea     rcx, [rbp+var_20]
0x18001570b  call    ??1?$PresentSharedPtr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@Core@@QEAA@XZ; Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(void)
0x180015710  nop
0x180015711  mov     rcx, [rbp+var_38]; this
0x180015715  test    rcx, rcx
0x180015718  jz      short loc_180015730
0x18001571a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001571f  jmp     short loc_180015730
0x180015721  mov     rax, [rbp+var_40]
0x180015725  mov     [r15], rax
0x180015728  mov     rax, [rbp+var_38]
0x18001572c  mov     [r15+8], rax
0x180015730  mov     rax, r15
0x180015733  add     rsp, 78h
0x180015737  pop     r15
0x180015739  pop     r14
0x18001573b  pop     rdi
0x18001573c  pop     rsi
0x18001573d  pop     rbx
0x18001573e  pop     rbp
0x18001573f  retn
```
