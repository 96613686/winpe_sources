# tip2::details::shared_data<1,0,0>::~shared_data<1,0,0>(void)

- ea: `0x18001fedc`
- end: `0x18001ff0c`
- name: `??1?$shared_data@$00$0A@$0A@@details@tip2@@QEAA@XZ`
- size: `48`
- prototype: ``
- caller_count: `29`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001feac`
- `0x180036364`
- `0x180036394`
- `0x180075dcc`
- `0x18008c6f0`
- `0x180092444`
- `0x180092474`
- `0x18009a634`
- `0x18009a664`
- `0x1800a05a4`
- `0x1800a05d4`
- `0x1800a2a9c`
- `0x1800b4500`
- `0x1800b4530`
- `0x1800bbd88`
- `0x1800bbdb8`
- `0x1800c28e0`
- `0x1800d3df0`
- `0x1800d3e38`
- `0x1800dae44`
- `0x1800dae8c`
- `0x1800e2a70`
- `0x1800e2aa0`
- `0x1800e5cb8`
- `0x1800eb834`
- `0x1800eb864`
- `0x1800fca50`
- `0x1800fca80`
- `0x1800fe8b8`

## callees

- `0x18001ffc8`
- `0x1800200d4`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001feec`
- `KERNEL32!DeleteCriticalSection` at `0x18001feec`

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
0x18001fedc  push    rbx
0x18001fede  sub     rsp, 20h
0x18001fee2  mov     rbx, rcx
0x18001fee5  add     rcx, 0C0h; lpCriticalSection
0x18001feec  call    cs:__imp_DeleteCriticalSection
0x18001fef2  lea     rcx, [rbx+0F0h]
0x18001fef9  call    ??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)
0x18001fefe  lea     rcx, [rbx+8]; this
0x18001ff02  add     rsp, 20h
0x18001ff06  pop     rbx
0x18001ff07  jmp     ??1test_state@tip2@@QEAA@XZ; tip2::test_state::~test_state(void)
```
