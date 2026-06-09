# tip2::details::shared_data<0,0,1>::~shared_data<0,0,1>(void)

- ea: `0x14000e0b4`
- end: `0x14000e0e4`
- name: `??1?$shared_data@$0A@$0A@$00@details@tip2@@QEAA@XZ`
- size: `48`
- prototype: `void __fastcall(__int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000e034`
- `0x14001bc20`
- `0x14002d5f8`
- `0x140037dcc`
- `0x1400439f4`
- `0x140043a24`

## callees

- `0x14000e1bc`
- `0x14000e340`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000e0c4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000e0c4`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,1>::~shared_data<0,0,1>(__int64 a1)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
  wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(a1 + 240);
  tip2::test_state::~test_state((tip2::test_state *)(a1 + 8));
}

```

## disassembly

```asm
0x14000e0b4  push    rbx
0x14000e0b6  sub     rsp, 20h
0x14000e0ba  mov     rbx, rcx
0x14000e0bd  add     rcx, 0C0h; lpCriticalSection
0x14000e0c4  call    cs:__imp_DeleteCriticalSection
0x14000e0ca  lea     rcx, [rbx+0F0h]
0x14000e0d1  call    ??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)
0x14000e0d6  lea     rcx, [rbx+8]; this
0x14000e0da  add     rsp, 20h
0x14000e0de  pop     rbx
0x14000e0df  jmp     ??1test_state@tip2@@QEAA@XZ; tip2::test_state::~test_state(void)
```
