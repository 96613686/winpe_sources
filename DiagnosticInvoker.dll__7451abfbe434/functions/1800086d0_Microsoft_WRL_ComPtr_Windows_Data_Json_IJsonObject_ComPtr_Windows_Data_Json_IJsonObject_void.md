# Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::~ComPtr<Windows::Data::Json::IJsonObject>(void)

- ea: `0x1800086d0`
- end: `0x1800086f8`
- name: `??1?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `13`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800102c9`
- `0x1800102db`
- `0x1800102ed`
- `0x1800102ff`
- `0x180010311`
- `0x180010323`
- `0x180010347`
- `0x18001036b`
- `0x18001037d`
- `0x18001038f`
- `0x1800103a1`
- `0x1800103b3`
- `0x1800103e9`

## callees

- `0x1800086d0`
- `0x180011010`

## pseudocode

```c
void __fastcall Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::~ComPtr<Windows::Data::Json::IJsonObject>(
        __int64 *a1)
{
  __int64 v2; // rcx

  v2 = *a1;
  if ( v2 )
  {
    *a1 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
}

```

## disassembly

```asm
0x1800086d0  sub     rsp, 28h
0x1800086d4  mov     rax, rcx
0x1800086d7  mov     rcx, [rcx]
0x1800086da  test    rcx, rcx
0x1800086dd  jz      short loc_1800086F3
0x1800086df  mov     qword ptr [rax], 0
0x1800086e6  mov     rax, [rcx]
0x1800086e9  mov     rax, [rax+10h]
0x1800086ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086f2  nop
0x1800086f3  add     rsp, 28h
0x1800086f7  retn
```
