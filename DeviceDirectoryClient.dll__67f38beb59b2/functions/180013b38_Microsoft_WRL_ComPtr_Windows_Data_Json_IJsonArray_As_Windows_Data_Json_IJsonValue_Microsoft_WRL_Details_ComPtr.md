# Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)

- ea: `0x180013b38`
- end: `0x180013b81`
- name: `??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z`
- size: `73`
- prototype: `__int64 __fastcall(__int64 (__fastcall ****)(_QWORD, GUID *, __int64), __int64)`
- caller_count: `15`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015120`
- `0x180015504`
- `0x180015fbc`
- `0x18001691c`
- `0x18001bf54`
- `0x18001c978`
- `0x18001dcfc`
- `0x18001e164`
- `0x180020068`
- `0x1800204a4`
- `0x180020d2c`
- `0x18002166c`
- `0x180022240`
- `0x180023f8c`
- `0x180027dc8`

## callees

- `0x180004060`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
        __int64 (__fastcall ****a1)(_QWORD, GUID *, __int64),
        __int64 a2)
{
  __int64 (__fastcall ***v3)(_QWORD, GUID *, __int64); // rsi
  __int64 (__fastcall *v4)(_QWORD, GUID *, __int64); // rdi

  v3 = *a1;
  v4 = ***a1;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a2);
  return v4(v3, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, a2);
}

```

## disassembly

```asm
0x180013b38  mov     [rsp+arg_0], rbx
0x180013b3d  mov     [rsp+arg_8], rsi
0x180013b42  push    rdi
0x180013b43  sub     rsp, 20h
0x180013b47  mov     rbx, rdx
0x180013b4a  mov     rsi, [rcx]
0x180013b4d  mov     rax, [rsi]
0x180013b50  mov     rdi, [rax]
0x180013b53  mov     rcx, rdx
0x180013b56  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013b5b  mov     r8, rbx
0x180013b5e  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x180013b65  mov     rcx, rsi
0x180013b68  mov     rax, rdi
0x180013b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b70  nop
0x180013b71  mov     rbx, [rsp+28h+arg_0]
0x180013b76  mov     rsi, [rsp+28h+arg_8]
0x180013b7b  add     rsp, 20h
0x180013b7f  pop     rdi
0x180013b80  retn
```
