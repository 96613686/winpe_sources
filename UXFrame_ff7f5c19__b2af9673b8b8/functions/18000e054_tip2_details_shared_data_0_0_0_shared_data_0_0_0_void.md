# tip2::details::shared_data<0,0,0>::~shared_data<0,0,0>(void)

- ea: `0x18000e054`
- end: `0x18000e084`
- name: `??1?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@XZ`
- size: `48`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000dff0`
- `0x180021dec`
- `0x18003e8e8`

## callees

- `0x18000e244`
- `0x18000ea44`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e064`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e064`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,0>::~shared_data<0,0,0>(__int64 a1)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
  wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(a1 + 240);
  tip2::test_state::~test_state((tip2::test_state *)(a1 + 8));
}

```

## disassembly

```asm
0x18000e054  push    rbx
0x18000e056  sub     rsp, 20h
0x18000e05a  mov     rbx, rcx
0x18000e05d  add     rcx, 0C0h; lpCriticalSection
0x18000e064  call    cs:__imp_DeleteCriticalSection
0x18000e06a  lea     rcx, [rbx+0F0h]
0x18000e071  call    ??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)
0x18000e076  lea     rcx, [rbx+8]; this
0x18000e07a  add     rsp, 20h
0x18000e07e  pop     rbx
0x18000e07f  jmp     ??1test_state@tip2@@QEAA@XZ; tip2::test_state::~test_state(void)
```
