# CSyncSharePartnershipDescriptor::~CSyncSharePartnershipDescriptor(void)

- ea: `0x1800157b4`
- end: `0x18001582e`
- name: `??1CSyncSharePartnershipDescriptor@@QEAA@XZ`
- size: `122`
- prototype: `void __fastcall(CSyncSharePartnershipDescriptor *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180015470`
- `0x180127478`
- `0x180127aa6`

## callees

- `0x180009134`
- `0x180009188`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800157e2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800157ed`
- `OLEAUT32!__imp_SysFreeString` at `0x1800157f8`
- `OLEAUT32!__imp_SysFreeString` at `0x180015803`
- `OLEAUT32!__imp_SysFreeString` at `0x18001580e`
- `OLEAUT32!__imp_SysFreeString` at `0x180015819`
- `OLEAUT32!__imp_SysFreeString` at `0x1800157e2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800157ed`
- `OLEAUT32!__imp_SysFreeString` at `0x1800157f8`
- `OLEAUT32!__imp_SysFreeString` at `0x180015803`
- `OLEAUT32!__imp_SysFreeString` at `0x18001580e`
- `OLEAUT32!__imp_SysFreeString` at `0x180015819`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800157c8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800157c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall CSyncSharePartnershipDescriptor::~CSyncSharePartnershipDescriptor(
        CSyncSharePartnershipDescriptor *this)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 120);
  SysFreeString(*((BSTR *)this + 13));
  SysFreeString(*((BSTR *)this + 12));
  SysFreeString(*((BSTR *)this + 11));
  SysFreeString(*((BSTR *)this + 10));
  SysFreeString(*((BSTR *)this + 9));
  SysFreeString(*((BSTR *)this + 8));
  ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>((char *)this + 8);
}

```

## disassembly

```asm
0x1800157b4  mov     [rsp+arg_0], rcx
0x1800157b9  push    rbx
0x1800157ba  sub     rsp, 20h
0x1800157be  mov     rbx, rcx
0x1800157c1  add     rcx, 88h; lpCriticalSection
0x1800157c8  call    cs:__imp_DeleteCriticalSection
0x1800157ce  nop
0x1800157cf  lea     rcx, [rbx+78h]
0x1800157d3  mov     [rsp+28h+arg_8], rcx
0x1800157d8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800157dd  nop
0x1800157de  mov     rcx, [rbx+68h]; bstrString
0x1800157e2  call    cs:__imp_SysFreeString
0x1800157e8  nop
0x1800157e9  mov     rcx, [rbx+60h]; bstrString
0x1800157ed  call    cs:__imp_SysFreeString
0x1800157f3  nop
0x1800157f4  mov     rcx, [rbx+58h]; bstrString
0x1800157f8  call    cs:__imp_SysFreeString
0x1800157fe  nop
0x1800157ff  mov     rcx, [rbx+50h]; bstrString
0x180015803  call    cs:__imp_SysFreeString
0x180015809  nop
0x18001580a  mov     rcx, [rbx+48h]; bstrString
0x18001580e  call    cs:__imp_SysFreeString
0x180015814  nop
0x180015815  mov     rcx, [rbx+40h]; bstrString
0x180015819  call    cs:__imp_SysFreeString
0x18001581f  nop
0x180015820  lea     rcx, [rbx+8]
0x180015824  add     rsp, 20h
0x180015828  pop     rbx
0x180015829  jmp     ??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)
```
