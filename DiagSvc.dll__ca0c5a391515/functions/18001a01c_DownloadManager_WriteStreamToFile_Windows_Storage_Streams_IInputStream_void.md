# DownloadManager::WriteStreamToFile(Windows::Storage::Streams::IInputStream *,void *)

- ea: `0x18001a01c`
- end: `0x18001a16f`
- name: `?WriteStreamToFile@DownloadManager@@AEAAJPEAUIInputStream@Streams@Storage@Windows@@PEAX@Z`
- size: `339`
- prototype: `__int64 __fastcall(DownloadManager *this, struct Windows::Storage::Streams::IInputStream *, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180016d70`

## callees

- `0x18000517c`
- `0x180014bcc`
- `0x180019f10`
- `0x18001a01c`
- `0x18001b2c0`
- `0x180027010`

## pseudocode

```c
__int64 __fastcall DownloadManager::WriteStreamToFile(
        DownloadManager *this,
        struct Windows::Storage::Streams::IInputStream *a2,
        void *a3)
{
  unsigned int v5; // ecx
  int v6; // ebx
  bool v7; // si
  __int64 (__fastcall *v8)(struct Windows::Storage::Streams::IInputStream *, struct Windows::Storage::Streams::IBuffer *, __int64, __int64, __int64 *); // rbx
  __int64 v9; // rdi
  DownloadManager *v10; // rcx
  struct Windows::Storage::Streams::IBuffer *v12; // [rsp+30h] [rbp-10h] BYREF
  __int64 v13; // [rsp+38h] [rbp-8h] BYREF
  DownloadManager *v14; // [rsp+70h] [rbp+30h] BYREF
  struct Windows::Storage::Streams::IBuffer *v15; // [rsp+88h] [rbp+48h] BYREF

  v14 = this;
  v12 = 0;
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v12);
  v6 = HelperClass::CreateBuffer(v5, &v12);
  if ( v6 >= 0 )
  {
    v7 = 0;
    do
    {
      if ( v7 )
        break;
      (*(void (__fastcall **)(struct Windows::Storage::Streams::IBuffer *, _QWORD))(*(_QWORD *)v12 + 64LL))(v12, 0);
      v13 = 0;
      v8 = *(__int64 (__fastcall **)(struct Windows::Storage::Streams::IInputStream *, struct Windows::Storage::Streams::IBuffer *, __int64, __int64, __int64 *))(*(_QWORD *)a2 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v13);
      v6 = v8(a2, v12, 0x8000, 2, &v13);
      if ( v6 >= 0 )
      {
        v15 = 0;
        v9 = v13;
        Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v15);
        v6 = WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,unsigned int>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,unsigned int>>(v9);
        if ( v6 >= 0 )
        {
          v6 = (*(__int64 (__fastcall **)(__int64, struct Windows::Storage::Streams::IBuffer **))(*(_QWORD *)v9 + 80LL))(
                 v9,
                 &v15);
          if ( v6 >= 0 )
          {
            LODWORD(v14) = 0;
            v6 = (*(__int64 (__fastcall **)(struct Windows::Storage::Streams::IBuffer *, DownloadManager **))(*(_QWORD *)v15 + 56LL))(
                   v15,
                   &v14);
            if ( v6 >= 0 )
            {
              v7 = (_DWORD)v14 != 0x8000;
              v6 = DownloadManager::WriteBufferToFile(
                     v10,
                     (__int64 (__fastcall ***)(struct Windows::Storage::Streams::IBuffer *, GUID *, __int64 *))v15,
                     a3);
            }
          }
        }
        Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v15);
      }
      Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v13);
    }
    while ( v6 >= 0 );
  }
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v12);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001a01c  mov     [rsp-28h+arg_8], rbx
0x18001a021  mov     [rsp-28h+arg_0], rcx
0x18001a026  push    rbp
0x18001a027  push    rsi
0x18001a028  push    rdi
0x18001a029  push    r14
0x18001a02b  push    r15
0x18001a02d  mov     rbp, rsp
0x18001a030  sub     rsp, 40h
0x18001a034  mov     r14, r8
0x18001a037  mov     r15, rdx
0x18001a03a  mov     [rbp+var_10], 0
0x18001a042  lea     rcx, [rbp+var_10]
0x18001a046  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001a04b  lea     rdx, [rbp+var_10]; struct Windows::Storage::Streams::IBuffer **
0x18001a04f  call    ?CreateBuffer@HelperClass@@SAJIPEAPEAUIBuffer@Streams@Storage@Windows@@@Z; HelperClass::CreateBuffer(uint,Windows::Storage::Streams::IBuffer * *)
0x18001a054  mov     ebx, eax
0x18001a056  test    eax, eax
0x18001a058  js      loc_18001A153
0x18001a05e  xor     sil, sil
0x18001a061  test    sil, sil
0x18001a064  jnz     loc_18001A153
0x18001a06a  mov     rcx, [rbp+var_10]
0x18001a06e  mov     rax, [rcx]
0x18001a071  xor     edx, edx
0x18001a073  mov     rax, [rax+40h]
0x18001a077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a07c  mov     [rbp+var_8], 0
0x18001a084  mov     rax, [r15]
0x18001a087  mov     rbx, [rax+30h]
0x18001a08b  lea     rcx, [rbp+var_8]
0x18001a08f  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001a094  lea     rax, [rbp+var_8]
0x18001a098  mov     [rsp+40h+var_20], rax
0x18001a09d  mov     r9d, 2
0x18001a0a3  mov     r8d, 8000h
0x18001a0a9  mov     rdx, [rbp+var_10]
0x18001a0ad  mov     rcx, r15
0x18001a0b0  mov     rax, rbx
0x18001a0b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0b8  mov     ebx, eax
0x18001a0ba  test    eax, eax
0x18001a0bc  js      loc_18001A142
0x18001a0c2  mov     [rbp+arg_18], 0
0x18001a0ca  mov     rdi, [rbp+var_8]
0x18001a0ce  lea     rcx, [rbp+arg_18]
0x18001a0d2  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001a0d7  mov     rcx, rdi
0x18001a0da  call    ??$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUIBuffer@Streams@Storage@Windows@@I@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,uint>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,uint> *,tagCOWAIT_FLAGS,void *)
0x18001a0df  mov     ebx, eax
0x18001a0e1  test    eax, eax
0x18001a0e3  js      short loc_18001A138
0x18001a0e5  mov     rax, [rdi]
0x18001a0e8  lea     rdx, [rbp+arg_18]
0x18001a0ec  mov     rcx, rdi
0x18001a0ef  mov     rax, [rax+50h]
0x18001a0f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0f8  mov     ebx, eax
0x18001a0fa  test    eax, eax
0x18001a0fc  js      short loc_18001A138
0x18001a0fe  mov     dword ptr [rbp+arg_0], 0
0x18001a105  mov     rcx, [rbp+arg_18]
0x18001a109  mov     rax, [rcx]
0x18001a10c  lea     rdx, [rbp+arg_0]
0x18001a110  mov     rax, [rax+38h]
0x18001a114  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a119  mov     ebx, eax
0x18001a11b  test    eax, eax
0x18001a11d  js      short loc_18001A138
0x18001a11f  cmp     dword ptr [rbp+arg_0], 8000h
0x18001a126  setnz   sil
0x18001a12a  mov     r8, r14; void *
0x18001a12d  mov     rdx, [rbp+arg_18]; struct Windows::Storage::Streams::IBuffer *
0x18001a131  call    ?WriteBufferToFile@DownloadManager@@AEAAJPEAUIBuffer@Streams@Storage@Windows@@PEAX@Z; DownloadManager::WriteBufferToFile(Windows::Storage::Streams::IBuffer *,void *)
0x18001a136  mov     ebx, eax
0x18001a138  lea     rcx, [rbp+arg_18]
0x18001a13c  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001a141  nop
0x18001a142  lea     rcx, [rbp+var_8]
0x18001a146  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001a14b  test    ebx, ebx
0x18001a14d  jns     loc_18001A061
0x18001a153  lea     rcx, [rbp+var_10]
0x18001a157  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001a15c  mov     eax, ebx
0x18001a15e  mov     rbx, [rsp+40h+arg_8]
0x18001a163  add     rsp, 40h
0x18001a167  pop     r15
0x18001a169  pop     r14
0x18001a16b  pop     rdi
0x18001a16c  pop     rsi
0x18001a16d  pop     rbp
0x18001a16e  retn
```
