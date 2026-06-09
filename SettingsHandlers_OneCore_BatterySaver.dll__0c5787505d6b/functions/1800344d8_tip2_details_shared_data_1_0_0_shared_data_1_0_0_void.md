# tip2::details::shared_data<1,0,0>::~shared_data<1,0,0>(void)

- ea: `0x1800344d8`
- end: `0x180034508`
- name: `??1?$shared_data@$00$0A@$0A@@details@tip2@@QEAA@XZ`
- size: `48`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800344a8`
- `0x1800403e0`

## callees

- `0x1800345bc`
- `0x18003480c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800344e8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800344e8`

## pseudocode

```c
void __fastcall tip2::details::shared_data<1,0,0>::~shared_data<1,0,0>(__int64 a1)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
  wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(a1 + 240);
  tip2::test_state::~test_state((tip2::test_state *)(a1 + 8));
}

```

## disassembly

```asm
0x1800344d8  push    rbx
0x1800344da  sub     rsp, 20h
0x1800344de  mov     rbx, rcx
0x1800344e1  add     rcx, 0C0h; lpCriticalSection
0x1800344e8  call    cs:__imp_DeleteCriticalSection
0x1800344ee  lea     rcx, [rbx+0F0h]
0x1800344f5  call    ??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)
0x1800344fa  lea     rcx, [rbx+8]; this
0x1800344fe  add     rsp, 20h
0x180034502  pop     rbx
0x180034503  jmp     ??1test_state@tip2@@QEAA@XZ; tip2::test_state::~test_state(void)
```
