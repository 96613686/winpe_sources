# CWICRawMetadataBlockEnumerator::~CWICRawMetadataBlockEnumerator(void)

- ea: `0x180098684`
- end: `0x1800986c4`
- name: `??1CWICRawMetadataBlockEnumerator@@UEAA@XZ`
- size: `64`
- prototype: `void __fastcall(CWICRawMetadataBlockEnumerator *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800989c0`

## callees

- `0x1800967ac`
- `0x18009c44c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800986a3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800986a3`

## pseudocode

```c
void __fastcall CWICRawMetadataBlockEnumerator::~CWICRawMetadataBlockEnumerator(CWICRawMetadataBlockEnumerator *this)
{
  Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease((char *)this + 96);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  *((_DWORD *)this + 11) = -1073741823;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 32);
}

```

## disassembly

```asm
0x180098684  push    rbx
0x180098686  sub     rsp, 30h
0x18009868a  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180098693  mov     rbx, rcx
0x180098696  add     rcx, 60h ; '`'
0x18009869a  call    ?InternalRelease@?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(void)
0x18009869f  lea     rcx, [rbx+30h]; lpCriticalSection
0x1800986a3  call    cs:__imp_DeleteCriticalSection
0x1800986aa  nop     dword ptr [rax+rax+00h]
0x1800986af  mov     dword ptr [rbx+2Ch], 0C0000001h
0x1800986b6  lea     rcx, [rbx+20h]
0x1800986ba  add     rsp, 30h
0x1800986be  pop     rbx
0x1800986bf  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
