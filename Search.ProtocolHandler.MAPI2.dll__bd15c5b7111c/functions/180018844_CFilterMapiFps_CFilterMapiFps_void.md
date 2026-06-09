# CFilterMapiFps::~CFilterMapiFps(void)

- ea: `0x180018844`
- end: `0x18001888f`
- name: `??1CFilterMapiFps@@QEAA@XZ`
- size: `75`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800184c0`

## callees

- `0x18000ea18`
- `0x180011884`
- `0x180017870`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018851`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018851`

## pseudocode

```c
void __fastcall CFilterMapiFps::~CFilterMapiFps(LPVOID *this)
{
  CoTaskMemFree(this[14]);
  wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
    this + 10,
    0);
  ATL::CStringData::Release((ATL::CStringData *)((char *)this[9] - 24));
  TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(this + 6);
  TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(this + 5);
  TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(this + 4);
}

```

## disassembly

```asm
0x180018844  push    rbx
0x180018846  sub     rsp, 20h
0x18001884a  mov     rbx, rcx
0x18001884d  mov     rcx, [rcx+70h]; pv
0x180018851  call    cs:__imp_CoTaskMemFree
0x180018857  lea     rcx, [rbx+50h]
0x18001885b  xor     edx, edx
0x18001885d  call    ?reset@?$unique_ptr@UtagPROPVARIANT@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUtagPROPVARIANT@@@Z; wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(tagPROPVARIANT *)
0x180018862  mov     rcx, [rbx+48h]
0x180018866  sub     rcx, 18h; this
0x18001886a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001886f  lea     rcx, [rbx+30h]
0x180018873  call    ??1?$TComNoUnkPointer@VCFilterMapiFps@@@@QEAA@XZ; TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(void)
0x180018878  lea     rcx, [rbx+28h]
0x18001887c  call    ??1?$TComNoUnkPointer@VCFilterMapiFps@@@@QEAA@XZ; TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(void)
0x180018881  lea     rcx, [rbx+20h]
0x180018885  add     rsp, 20h
0x180018889  pop     rbx
0x18001888a  jmp     ??1?$TComNoUnkPointer@VCFilterMapiFps@@@@QEAA@XZ; TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(void)
```
