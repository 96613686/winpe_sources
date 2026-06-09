# RunManager::MakeDownloadManager(void)

- ea: `0x18000e210`
- end: `0x18000e2c7`
- name: `?MakeDownloadManager@RunManager@@MEAAJXZ`
- size: `183`
- prototype: `__int64 __fastcall(RunManager *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000517c`
- `0x180008844`
- `0x18000e210`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e232`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e2b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e232`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e2b7`

## pseudocode

```c
__int64 __fastcall RunManager::MakeDownloadManager(RunManager *this)
{
  __int64 (__fastcall *v2)(RunManager *, HSTRING *); // rbx
  int v3; // ebx
  __int64 v5; // [rsp+40h] [rbp-10h] BYREF
  HSTRING string; // [rsp+70h] [rbp+20h] BYREF
  HSTRING v7; // [rsp+78h] [rbp+28h] BYREF
  __int64 v8; // [rsp+80h] [rbp+30h] BYREF
  __int64 v9; // [rsp+88h] [rbp+38h] BYREF

  string = 0;
  v2 = *(__int64 (__fastcall **)(RunManager *, HSTRING *))(*(_QWORD *)this + 136LL);
  WindowsDeleteString(0);
  string = 0;
  v3 = v2(this, &string);
  if ( v3 >= 0 )
  {
    v7 = string;
    v8 = *((_QWORD *)this + 13);
    v9 = *((_QWORD *)this + 12);
    v5 = *((_QWORD *)this + 11);
    Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease((char *)this + 72);
    v3 = Microsoft::WRL::Details::MakeAndInitialize<DownloadManager,IDownloadManager,char (&)[129],char (&)[129],HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *>(
           (char *)this + 72,
           (char *)this + 241,
           (char *)this + 112,
           &v5,
           &v9,
           &v8,
           &v7);
  }
  WindowsDeleteString(string);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000e210  push    rbp
0x18000e212  push    rbx
0x18000e213  push    rdi
0x18000e214  mov     rbp, rsp
0x18000e217  sub     rsp, 50h
0x18000e21b  mov     rdi, rcx
0x18000e21e  mov     [rbp+string], 0
0x18000e226  mov     rax, [rcx]
0x18000e229  mov     rbx, [rax+88h]
0x18000e230  xor     ecx, ecx; string
0x18000e232  call    cs:__imp_WindowsDeleteString
0x18000e238  mov     [rbp+string], 0
0x18000e240  lea     rdx, [rbp+string]
0x18000e244  mov     rcx, rdi
0x18000e247  mov     rax, rbx
0x18000e24a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e24f  mov     ebx, eax
0x18000e251  test    eax, eax
0x18000e253  js      short loc_18000E2B3
0x18000e255  mov     rax, [rbp+string]
0x18000e259  mov     [rbp+arg_8], rax
0x18000e25d  mov     rax, [rdi+68h]
0x18000e261  mov     [rbp+arg_10], rax
0x18000e265  mov     rax, [rdi+60h]
0x18000e269  mov     [rbp+arg_18], rax
0x18000e26d  mov     rax, [rdi+58h]
0x18000e271  mov     [rbp+var_10], rax
0x18000e275  lea     rcx, [rdi+48h]
0x18000e279  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18000e27e  lea     r8, [rdi+70h]
0x18000e282  lea     rdx, [rdi+0F1h]
0x18000e289  lea     rax, [rbp+arg_8]
0x18000e28d  mov     [rsp+50h+var_20], rax
0x18000e292  lea     rax, [rbp+arg_10]
0x18000e296  mov     [rsp+50h+var_28], rax
0x18000e29b  lea     rax, [rbp+arg_18]
0x18000e29f  mov     [rsp+50h+var_30], rax
0x18000e2a4  lea     r9, [rbp+var_10]
0x18000e2a8  lea     rcx, [rdi+48h]
0x18000e2ac  call    ??$MakeAndInitialize@VDownloadManager@@UIDownloadManager@@AEAY0IB@DAEAY0IB@DPEAUHSTRING__@@PEAU3@PEAU3@PEAU3@@Details@WRL@Microsoft@@YAJPEAPEAUIDownloadManager@@AEAY0IB@D1$$QEAPEAUHSTRING__@@222@Z; Microsoft::WRL::Details::MakeAndInitialize<DownloadManager,IDownloadManager,char (&)[129],char (&)[129],HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *>(IDownloadManager * *,char (&)[129],char (&)[129],HSTRING__ * &&,HSTRING__ * &&,HSTRING__ * &&,HSTRING__ * &&)
0x18000e2b1  mov     ebx, eax
0x18000e2b3  mov     rcx, [rbp+string]; string
0x18000e2b7  call    cs:__imp_WindowsDeleteString
0x18000e2bd  mov     eax, ebx
0x18000e2bf  add     rsp, 50h
0x18000e2c3  pop     rdi
0x18000e2c4  pop     rbx
0x18000e2c5  pop     rbp
0x18000e2c6  retn
```
