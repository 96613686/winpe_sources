# ConnectedStorage::CallerInfo::~CallerInfo(void)

- ea: `0x18001253c`
- end: `0x180012576`
- name: `??1CallerInfo@ConnectedStorage@@QEAA@XZ`
- size: `58`
- prototype: `void __fastcall(ConnectedStorage::CallerInfo *__hidden this)`
- caller_count: `25`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180011e7c`
- `0x1800126f4`
- `0x18001278c`
- `0x180031120`
- `0x18004ae14`
- `0x18004b1f0`
- `0x18004b894`
- `0x18004cf90`
- `0x180052bc0`
- `0x18005b134`
- `0x18005c3dc`
- `0x180073d1c`
- `0x1800859c0`
- `0x180085a6e`
- `0x180085d79`
- `0x180085f5d`
- `0x180087c73`
- `0x1800883f2`
- `0x18008a0ca`
- `0x18008a67f`
- `0x18008ad63`
- `0x18008ae37`
- `0x18008b023`
- `0x18008b15c`
- `0x18008c41d`

## callees

- `0x18000a040`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012552`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012563`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012552`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012563`

## pseudocode

```c
void __fastcall ConnectedStorage::CallerInfo::~CallerInfo(HSTRING *this)
{
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 4);
  WindowsDeleteString(this[1]);
  this[1] = 0;
  WindowsDeleteString(*this);
  *this = 0;
}

```

## disassembly

```asm
0x18001253c  push    rbx
0x18001253e  sub     rsp, 20h
0x180012542  mov     rbx, rcx
0x180012545  add     rcx, 20h ; ' '
0x180012549  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001254e  mov     rcx, [rbx+8]; string
0x180012552  call    cs:__imp_WindowsDeleteString
0x180012558  mov     qword ptr [rbx+8], 0
0x180012560  mov     rcx, [rbx]; string
0x180012563  call    cs:__imp_WindowsDeleteString
0x180012569  mov     qword ptr [rbx], 0
0x180012570  add     rsp, 20h
0x180012574  pop     rbx
0x180012575  retn
```
