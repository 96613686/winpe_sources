# DiagnosticServer::~DiagnosticServer(void)

- ea: `0x18000542c`
- end: `0x180005457`
- name: `??1DiagnosticServer@@UEAA@XZ`
- size: `43`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005490`
- `0x180026e80`

## callees

- `0x18000517c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005443`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005443`

## pseudocode

```c
void __fastcall DiagnosticServer::~DiagnosticServer(struct _RTL_CRITICAL_SECTION *this)
{
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&DiagnosticServer::`vftable';
  DeleteCriticalSection(this + 2);
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&this[1].SpinCount);
}

```

## disassembly

```asm
0x18000542c  push    rbx
0x18000542e  sub     rsp, 20h
0x180005432  lea     rax, ??_7DiagnosticServer@@6B@; const DiagnosticServer::`vftable'
0x180005439  mov     rbx, rcx
0x18000543c  mov     [rcx], rax
0x18000543f  add     rcx, 50h ; 'P'; lpCriticalSection
0x180005443  call    cs:__imp_DeleteCriticalSection
0x180005449  lea     rcx, [rbx+48h]
0x18000544d  add     rsp, 20h
0x180005451  pop     rbx
0x180005452  jmp     ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
```
