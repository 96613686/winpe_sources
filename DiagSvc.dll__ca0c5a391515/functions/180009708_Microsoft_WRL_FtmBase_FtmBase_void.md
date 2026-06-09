# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x180009708`
- end: `0x18000978e`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `134`
- prototype: `Microsoft::WRL::FtmBase *__fastcall(Microsoft::WRL::FtmBase *this)`
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180008950`
- `0x180009638`
- `0x180014268`
- `0x1800143a8`
- `0x1800144e8`
- `0x180014628`
- `0x18001504c`

## callees

- `0x18000517c`
- `0x180009708`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180009744`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180009744`

## pseudocode

```c
Microsoft::WRL::FtmBase *__fastcall Microsoft::WRL::FtmBase::FtmBase(Microsoft::WRL::FtmBase *this)
{
  char *v2; // r14
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  *(_QWORD *)this = &Microsoft::WRL::FtmBase::`vftable';
  v2 = (char *)this + 24;
  *((_QWORD *)this + 3) = 0;
  ppunkMarshal = 0;
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&ppunkMarshal);
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v3 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(v2);
    ((void (__fastcall *)(LPUNKNOWN, GUID *, char *))QueryInterface)(v3, &GUID_00000003_0000_0000_c000_000000000046, v2);
  }
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&ppunkMarshal);
  return this;
}

```

## disassembly

```asm
0x180009708  push    rbx
0x18000970a  push    rsi
0x18000970b  push    rdi
0x18000970c  push    r14
0x18000970e  sub     rsp, 28h
0x180009712  mov     rsi, rcx
0x180009715  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x18000971c  mov     [rcx], rax
0x18000971f  lea     r14, [rcx+18h]
0x180009723  mov     qword ptr [r14], 0
0x18000972a  mov     [rsp+48h+ppunkMarshal], 0
0x180009733  lea     rcx, [rsp+48h+ppunkMarshal]
0x180009738  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18000973d  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x180009742  xor     ecx, ecx; punkOuter
0x180009744  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18000974a  test    eax, eax
0x18000974c  js      short loc_180009777
0x18000974e  mov     rbx, [rsp+48h+ppunkMarshal]
0x180009753  mov     rax, [rbx]
0x180009756  mov     rdi, [rax]
0x180009759  mov     rcx, r14
0x18000975c  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180009761  mov     r8, r14
0x180009764  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18000976b  mov     rcx, rbx
0x18000976e  mov     rax, rdi
0x180009771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009776  nop
0x180009777  lea     rcx, [rsp+48h+ppunkMarshal]
0x18000977c  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180009781  mov     rax, rsi
0x180009784  add     rsp, 28h
0x180009788  pop     r14
0x18000978a  pop     rdi
0x18000978b  pop     rsi
0x18000978c  pop     rbx
0x18000978d  retn
```
