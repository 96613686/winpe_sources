# FontCacheServer::InitializeDownloadManager(void)

- ea: `0x1800b2020`
- end: `0x1800b212b`
- name: `?InitializeDownloadManager@FontCacheServer@@AEAAXXZ`
- size: `267`
- prototype: `void __fastcall(FontCacheServer *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800a7190`

## callees

- `0x180028c50`
- `0x18004ff84`
- `0x1800aaa58`
- `0x1800b1710`
- `0x1800b2020`
- `0x1800b2140`
- `0x1800b24c0`
- `0x1800b91b8`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b204e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b204e`

## string_xrefs

- `0x1800b20b3`: `FontCache`
- `0x1800b2044`: `CreateFontDownloadManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall FontCacheServer::InitializeDownloadManager(FontCacheServer *this)
{
  HMODULE DownloadManagerModule; // rax
  HMODULE v3; // rbx
  FARPROC ProcAddress; // rbp
  EventForwarder *v5; // rax
  EventForwarder *v6; // rax
  EventForwarder *v7; // rsi
  const struct DWrite::RefString *v8; // rax
  HMODULE v9; // [rsp+78h] [rbp+10h] BYREF
  struct DWrite::RefString::Data *v10; // [rsp+80h] [rbp+18h] BYREF
  EventForwarder *v11; // [rsp+88h] [rbp+20h] BYREF

  DownloadManagerModule = LoadDownloadManagerModule();
  v3 = DownloadManagerModule;
  v9 = DownloadManagerModule;
  if ( DownloadManagerModule )
  {
    ProcAddress = GetProcAddress(DownloadManagerModule, "CreateFontDownloadManager");
    if ( ProcAddress )
    {
      v5 = (EventForwarder *)operator new(0x10u);
      *(_OWORD *)v5 = 0;
      v6 = EventForwarder::EventForwarder(v5);
      v7 = v6;
      v11 = v6;
      if ( v6 )
        (*(void (__fastcall **)(EventForwarder *))(*(_QWORD *)v6 + 8LL))(v6);
      ((void (__fastcall *)(char *, EventForwarder *, _QWORD, const WCHAR *, _DWORD, char *))ProcAddress)(
        (char *)this + 48,
        v7,
        *((_QWORD *)this + 7),
        L"FontCache",
        *((_DWORD *)this + 64),
        (char *)this + 400);
      if ( *((_QWORD *)this + 50) )
        v3 = 0;
      v9 = v3;
      v8 = (const struct DWrite::RefString *)(*(__int64 (__fastcall **)(_QWORD, struct DWrite::RefString::Data **))(**((_QWORD **)this + 7) + 120LL))(
                                               *((_QWORD *)this + 7),
                                               &v10);
      FontCacheServer::SetStorageReserve(this, v8);
      DWrite::RefString::DecrementRef(v10);
      ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>(&v11);
    }
  }
  ModuleHandle::~ModuleHandle((ModuleHandle *)&v9);
}

```

## disassembly

```asm
0x1800b2020  push    rbx
0x1800b2022  push    rbp
0x1800b2023  push    rsi
0x1800b2024  push    rdi
0x1800b2025  push    r14
0x1800b2027  sub     rsp, 40h
0x1800b202b  mov     r14, rcx
0x1800b202e  call    ?LoadDownloadManagerModule@@YAPEAUHINSTANCE__@@XZ; LoadDownloadManagerModule(void)
0x1800b2033  mov     rbx, rax
0x1800b2036  mov     [rsp+68h+arg_8], rax
0x1800b203b  test    rax, rax
0x1800b203e  jz      loc_1800B2116
0x1800b2044  lea     rdx, aCreatefontdown; "CreateFontDownloadManager"
0x1800b204b  mov     rcx, rax; hModule
0x1800b204e  call    cs:__imp_GetProcAddress
0x1800b2054  mov     rbp, rax
0x1800b2057  test    rax, rax
0x1800b205a  jz      loc_1800B2116
0x1800b2060  mov     ecx, 10h; Size
0x1800b2065  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b206a  xorps   xmm0, xmm0
0x1800b206d  movups  xmmword ptr [rax], xmm0
0x1800b2070  mov     rcx, rax; this
0x1800b2073  call    ??0EventForwarder@@QEAA@XZ; EventForwarder::EventForwarder(void)
0x1800b2078  mov     rsi, rax
0x1800b207b  mov     [rsp+68h+arg_18], rax
0x1800b2083  test    rax, rax
0x1800b2086  jz      short loc_1800B2098
0x1800b2088  mov     rcx, [rax]
0x1800b208b  mov     rax, [rcx+8]
0x1800b208f  mov     rcx, rsi
0x1800b2092  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2097  nop
0x1800b2098  lea     rdi, [r14+190h]
0x1800b209f  lea     rcx, [r14+30h]
0x1800b20a3  mov     [rsp+68h+var_40], rdi
0x1800b20a8  mov     eax, [r14+100h]
0x1800b20af  mov     [rsp+68h+var_48], eax
0x1800b20b3  lea     r9, ?FontCacheServiceName@@3QB_WB; "FontCache"
0x1800b20ba  mov     r8, [r14+38h]
0x1800b20be  mov     rdx, rsi
0x1800b20c1  mov     rax, rbp
0x1800b20c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b20c9  xor     eax, eax
0x1800b20cb  cmp     [rdi], rax
0x1800b20ce  cmovnz  rbx, rax
0x1800b20d2  mov     [rsp+68h+arg_8], rbx
0x1800b20d7  mov     rcx, [r14+38h]
0x1800b20db  mov     rax, [rcx]
0x1800b20de  lea     rdx, [rsp+68h+arg_10]
0x1800b20e6  mov     rax, [rax+78h]
0x1800b20ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b20ef  mov     rdx, rax; struct DWrite::RefString *
0x1800b20f2  mov     rcx, r14; this
0x1800b20f5  call    ?SetStorageReserve@FontCacheServer@@AEAAXAEBVRefString@DWrite@@@Z; FontCacheServer::SetStorageReserve(DWrite::RefString const &)
0x1800b20fa  mov     rcx, [rsp+68h+arg_10]; struct DWrite::RefString::Data *
0x1800b2102  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x1800b2107  nop
0x1800b2108  lea     rcx, [rsp+68h+arg_18]
0x1800b2110  call    ??1?$ComPtr@UIDWriteFontFileLoader@@@@QEAA@XZ; ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>(void)
0x1800b2115  nop
0x1800b2116  lea     rcx, [rsp+68h+arg_8]; this
0x1800b211b  call    ??1ModuleHandle@@QEAA@XZ; ModuleHandle::~ModuleHandle(void)
0x1800b2120  add     rsp, 40h
0x1800b2124  pop     r14
0x1800b2126  pop     rdi
0x1800b2127  pop     rsi
0x1800b2128  pop     rbp
0x1800b2129  pop     rbx
0x1800b212a  retn
```
