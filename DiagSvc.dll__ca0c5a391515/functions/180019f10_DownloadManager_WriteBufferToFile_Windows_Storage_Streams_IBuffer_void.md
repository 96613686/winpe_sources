# DownloadManager::WriteBufferToFile(Windows::Storage::Streams::IBuffer *,void *)

- ea: `0x180019f10`
- end: `0x18001a015`
- name: `?WriteBufferToFile@DownloadManager@@AEAAJPEAUIBuffer@Streams@Storage@Windows@@PEAX@Z`
- size: `261`
- prototype: `__int64 __fastcall(DownloadManager *this, __int64 (__fastcall ***)(struct Windows::Storage::Streams::IBuffer *, GUID *, __int64 *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001a01c`

## callees

- `0x18000517c`
- `0x180019f10`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019ff1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019ff1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180019fd5`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180019fd5`

## pseudocode

```c
__int64 __fastcall DownloadManager::WriteBufferToFile(
        DownloadManager *this,
        __int64 (__fastcall ***a2)(struct Windows::Storage::Streams::IBuffer *, GUID *, __int64 *),
        void *a3)
{
  int v5; // ebx
  __int64 (__fastcall *v6)(struct Windows::Storage::Streams::IBuffer *, GUID *, __int64 *); // rbx
  signed int LastError; // eax
  DWORD nNumberOfBytesToWrite; // [rsp+50h] [rbp+20h] BYREF
  int v10; // [rsp+54h] [rbp+24h]
  __int64 NumberOfBytesWritten; // [rsp+58h] [rbp+28h] BYREF
  LPCVOID lpBuffer; // [rsp+68h] [rbp+38h] BYREF

  v10 = HIDWORD(this);
  nNumberOfBytesToWrite = 0;
  v5 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(struct Windows::Storage::Streams::IBuffer *, GUID *, __int64 *), DWORD *))(*a2)[7])(
         a2,
         &nNumberOfBytesToWrite);
  if ( v5 >= 0 && nNumberOfBytesToWrite )
  {
    lpBuffer = 0;
    NumberOfBytesWritten = 0;
    v6 = **a2;
    Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&NumberOfBytesWritten);
    v5 = v6(
           (struct Windows::Storage::Streams::IBuffer *)a2,
           &GUID_905a0fef_bc53_11df_8c49_001e4fc686da,
           &NumberOfBytesWritten);
    if ( v5 >= 0 )
      v5 = (*(__int64 (__fastcall **)(__int64, LPCVOID *))(*(_QWORD *)NumberOfBytesWritten + 24LL))(
             NumberOfBytesWritten,
             &lpBuffer);
    Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&NumberOfBytesWritten);
    if ( v5 >= 0 )
    {
      LODWORD(NumberOfBytesWritten) = 0;
      if ( WriteFile(a3, lpBuffer, nNumberOfBytesToWrite, (LPDWORD)&NumberOfBytesWritten, 0) )
      {
        return nNumberOfBytesToWrite != (_DWORD)NumberOfBytesWritten ? 0x8003001D : 0;
      }
      else
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          return (unsigned __int16)LastError | 0x80070000;
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180019f10  mov     [rsp-18h+arg_10], rbx
0x180019f15  mov     qword ptr [rsp-18h+nNumberOfBytesToWrite], rcx
0x180019f1a  push    rbp
0x180019f1b  push    rsi
0x180019f1c  push    rdi
0x180019f1d  mov     rbp, rsp
0x180019f20  sub     rsp, 30h
0x180019f24  mov     rsi, r8
0x180019f27  mov     rdi, rdx
0x180019f2a  mov     [rbp+nNumberOfBytesToWrite], 0
0x180019f31  mov     rax, [rdx]
0x180019f34  lea     rdx, [rbp+nNumberOfBytesToWrite]
0x180019f38  mov     rcx, rdi
0x180019f3b  mov     rax, [rax+38h]
0x180019f3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f44  mov     ebx, eax
0x180019f46  test    eax, eax
0x180019f48  js      loc_18001A006
0x180019f4e  cmp     [rbp+nNumberOfBytesToWrite], 0
0x180019f52  jbe     loc_18001A006
0x180019f58  mov     [rbp+lpBuffer], 0
0x180019f60  mov     [rbp+NumberOfBytesWritten], 0
0x180019f68  mov     rax, [rdi]
0x180019f6b  mov     rbx, [rax]
0x180019f6e  lea     rcx, [rbp+NumberOfBytesWritten]
0x180019f72  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180019f77  lea     r8, [rbp+NumberOfBytesWritten]
0x180019f7b  lea     rdx, _GUID_905a0fef_bc53_11df_8c49_001e4fc686da
0x180019f82  mov     rcx, rdi
0x180019f85  mov     rax, rbx
0x180019f88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f8d  mov     ebx, eax
0x180019f8f  test    eax, eax
0x180019f91  js      short loc_180019FA9
0x180019f93  mov     rcx, [rbp+NumberOfBytesWritten]
0x180019f97  mov     rax, [rcx]
0x180019f9a  lea     rdx, [rbp+lpBuffer]
0x180019f9e  mov     rax, [rax+18h]
0x180019fa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019fa7  mov     ebx, eax
0x180019fa9  lea     rcx, [rbp+NumberOfBytesWritten]
0x180019fad  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180019fb2  test    ebx, ebx
0x180019fb4  js      short loc_18001A006
0x180019fb6  mov     dword ptr [rbp+NumberOfBytesWritten], 0
0x180019fbd  mov     [rsp+30h+lpOverlapped], 0; lpOverlapped
0x180019fc6  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180019fca  mov     r8d, [rbp+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x180019fce  mov     rdx, [rbp+lpBuffer]; lpBuffer
0x180019fd2  mov     rcx, rsi; hFile
0x180019fd5  call    cs:__imp_WriteFile
0x180019fdb  test    eax, eax
0x180019fdd  jz      short loc_180019FF1
0x180019fdf  mov     eax, dword ptr [rbp+NumberOfBytesWritten]
0x180019fe2  sub     eax, [rbp+nNumberOfBytesToWrite]
0x180019fe5  neg     eax
0x180019fe7  sbb     ebx, ebx
0x180019fe9  and     ebx, 8003001Dh
0x180019fef  jmp     short loc_18001A006
0x180019ff1  call    cs:__imp_GetLastError
0x180019ff7  mov     ebx, eax
0x180019ff9  test    eax, eax
0x180019ffb  jle     short loc_18001A006
0x180019ffd  movzx   ebx, ax
0x18001a000  or      ebx, 80070000h
0x18001a006  mov     eax, ebx
0x18001a008  mov     rbx, [rsp+30h+arg_10]
0x18001a00d  add     rsp, 30h
0x18001a011  pop     rdi
0x18001a012  pop     rsi
0x18001a013  pop     rbp
0x18001a014  retn
```
