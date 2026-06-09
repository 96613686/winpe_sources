# Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>>)

- ea: `0x18001ea14`
- end: `0x18001ea5d`
- name: `??$As@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z`
- size: `73`
- prototype: `__int64 __fastcall(__int64 (__fastcall ****)(_QWORD, GUID *, __int64), __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f118`
- `0x18001f554`
- `0x18001f9a4`
- `0x1800203b0`
- `0x180020e9c`

## callees

- `0x180009fc0`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(
        __int64 (__fastcall ****a1)(_QWORD, GUID *, __int64),
        __int64 a2)
{
  __int64 (__fastcall ***v3)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v4)(_QWORD, GUID *, __int64); // rdi

  v3 = *a1;
  v4 = ***a1;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a2);
  return v4(v3, &GUID_d44662bc_dce3_59a8_9272_4b210f33908b, a2);
}

```

## disassembly

```asm
0x18001ea14  mov     [rsp+arg_0], rbx
0x18001ea19  mov     [rsp+arg_8], rsi
0x18001ea1e  push    rdi
0x18001ea1f  sub     rsp, 20h
0x18001ea23  mov     rbx, rdx
0x18001ea26  mov     rsi, [rcx]
0x18001ea29  mov     rax, [rsi]
0x18001ea2c  mov     rdi, [rax]
0x18001ea2f  mov     rcx, rdx
0x18001ea32  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ea37  mov     r8, rbx
0x18001ea3a  lea     rdx, _GUID_d44662bc_dce3_59a8_9272_4b210f33908b
0x18001ea41  mov     rcx, rsi
0x18001ea44  mov     rax, rdi
0x18001ea47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea4c  nop
0x18001ea4d  mov     rbx, [rsp+28h+arg_0]
0x18001ea52  mov     rsi, [rsp+28h+arg_8]
0x18001ea57  add     rsp, 20h
0x18001ea5b  pop     rdi
0x18001ea5c  retn
```
