# RunManager::~RunManager(void)

- ea: `0x18000a1f0`
- end: `0x18000a29b`
- name: `??1RunManager@@MEAA@XZ`
- size: `171`
- prototype: `void __fastcall(RunManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a600`

## callees

- `0x18000517c`
- `0x180009c68`
- `0x180009dd0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a22c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a241`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a253`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a265`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a22c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a241`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a253`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a265`

## pseudocode

```c
void __fastcall RunManager::~RunManager(RunManager *this)
{
  *(_QWORD *)this = &RunManager::`vftable';
  *((_QWORD *)this + 1) = &RunManager::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 2) = &RunManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>((char *)this + 400);
  WindowsDeleteString(*((HSTRING *)this + 49));
  *((_QWORD *)this + 49) = 0;
  WindowsDeleteString(*((HSTRING *)this + 13));
  *((_QWORD *)this + 13) = 0;
  WindowsDeleteString(*((HSTRING *)this + 12));
  *((_QWORD *)this + 12) = 0;
  WindowsDeleteString(*((HSTRING *)this + 11));
  *((_QWORD *)this + 11) = 0;
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease((char *)this + 80);
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease((char *)this + 72);
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease((char *)this + 64);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,IRunManager,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,IRunManager,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x18000a1f0  push    rbx
0x18000a1f2  sub     rsp, 20h
0x18000a1f6  lea     rax, ??_7RunManager@@6B@; const RunManager::`vftable'
0x18000a1fd  mov     rbx, rcx
0x18000a200  mov     [rcx], rax
0x18000a203  lea     rax, ??_7RunManager@@6BIWeakReferenceSource@@@; const RunManager::`vftable'{for `IWeakReferenceSource'}
0x18000a20a  mov     [rcx+8], rax
0x18000a20e  lea     rax, ??_7RunManager@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const RunManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000a215  mov     [rcx+10h], rax
0x18000a219  add     rcx, 190h
0x18000a220  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x18000a225  mov     rcx, [rbx+188h]; string
0x18000a22c  call    cs:__imp_WindowsDeleteString
0x18000a232  mov     qword ptr [rbx+188h], 0
0x18000a23d  mov     rcx, [rbx+68h]; string
0x18000a241  call    cs:__imp_WindowsDeleteString
0x18000a247  mov     qword ptr [rbx+68h], 0
0x18000a24f  mov     rcx, [rbx+60h]; string
0x18000a253  call    cs:__imp_WindowsDeleteString
0x18000a259  mov     qword ptr [rbx+60h], 0
0x18000a261  mov     rcx, [rbx+58h]; string
0x18000a265  call    cs:__imp_WindowsDeleteString
0x18000a26b  lea     rcx, [rbx+50h]
0x18000a26f  mov     qword ptr [rbx+58h], 0
0x18000a277  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18000a27c  lea     rcx, [rbx+48h]
0x18000a280  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18000a285  lea     rcx, [rbx+40h]
0x18000a289  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18000a28e  mov     rcx, rbx
0x18000a291  add     rsp, 20h
0x18000a295  pop     rbx
0x18000a296  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIRunManager@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,IRunManager,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,IRunManager,Microsoft::WRL::FtmBase>(void)
```
