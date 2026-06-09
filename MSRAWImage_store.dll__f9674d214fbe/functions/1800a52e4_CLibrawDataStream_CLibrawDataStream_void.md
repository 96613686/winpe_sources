# CLibrawDataStream::~CLibrawDataStream(void)

- ea: `0x1800a52e4`
- end: `0x1800a533d`
- name: `??1CLibrawDataStream@@UEAA@XZ`
- size: `89`
- prototype: `void __fastcall(CLibrawDataStream *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800a5800`

## callees

- `0x18009c44c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a5318`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a5318`

## pseudocode

```c
void __fastcall CLibrawDataStream::~CLibrawDataStream(CLibrawDataStream *this)
{
  *(_QWORD *)this = &CLibrawDataStream::`vftable'{for `Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>'};
  *((_QWORD *)this + 2) = &CLibrawDataStream::`vftable'{for `LibRaw_abstract_datastream'};
  Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease((char *)this + 64);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  *((_QWORD *)this + 2) = &LibRaw_abstract_datastream::`vftable';
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x1800a52e4  push    rbx
0x1800a52e6  sub     rsp, 30h
0x1800a52ea  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800a52f3  mov     rbx, rcx
0x1800a52f6  lea     rax, ??_7CLibrawDataStream@@6B?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIUnknown@@@WRL@Microsoft@@@; const CLibrawDataStream::`vftable'{for `Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>'}
0x1800a52fd  mov     [rcx], rax
0x1800a5300  lea     rax, ??_7CLibrawDataStream@@6BLibRaw_abstract_datastream@@@; const CLibrawDataStream::`vftable'{for `LibRaw_abstract_datastream'}
0x1800a5307  mov     [rcx+10h], rax
0x1800a530b  add     rcx, 40h ; '@'
0x1800a530f  call    ?InternalRelease@?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(void)
0x1800a5314  lea     rcx, [rbx+18h]; lpCriticalSection
0x1800a5318  call    cs:__imp_DeleteCriticalSection
0x1800a531f  nop     dword ptr [rax+rax+00h]
0x1800a5324  lea     rax, ??_7LibRaw_abstract_datastream@@6B@; const LibRaw_abstract_datastream::`vftable'
0x1800a532b  mov     [rbx+10h], rax
0x1800a532f  mov     dword ptr [rbx+0Ch], 0C0000001h
0x1800a5336  add     rsp, 30h
0x1800a533a  pop     rbx
0x1800a533b  retn
```
