# DSService::~DSService(void)

- ea: `0x180006590`
- end: `0x1800065bc`
- name: `??1DSService@@MEAA@XZ`
- size: `44`
- prototype: `void __fastcall(DSService *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800065e0`

## callees

- `0x18000517c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800065b5`

## pseudocode

```c
void __fastcall DSService::~DSService(DSService *this)
{
  *(_QWORD *)this = &DSService::`vftable';
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease((char *)this + 80);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x180006590  push    rbx
0x180006592  sub     rsp, 20h
0x180006596  lea     rax, ??_7DSService@@6B@; const DSService::`vftable'
0x18000659d  mov     rbx, rcx
0x1800065a0  mov     [rcx], rax
0x1800065a3  add     rcx, 50h ; 'P'
0x1800065a7  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x1800065ac  lea     rcx, [rbx+10h]
0x1800065b0  add     rsp, 20h
0x1800065b4  pop     rbx
0x1800065b5  jmp     cs:__imp_DeleteCriticalSection
```
