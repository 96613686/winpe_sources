# Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::operator=(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray> &&)

- ea: `0x14000a500`
- end: `0x14000a53d`
- name: `??4?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z`
- size: `61`
- prototype: `__int64 *__fastcall(__int64 *, __int64 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000be20`
- `0x14000ed9c`
- `0x140011851`

## callees

- `0x14000a500`
- `0x14000d49c`

## pseudocode

```c
__int64 *__fastcall Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::operator=(__int64 *a1, __int64 *a2)
{
  __int64 v3; // rcx
  __int64 v4; // rax
  _QWORD v6[3]; // [rsp+20h] [rbp-18h] BYREF

  v3 = 0;
  if ( v6 != a2 )
  {
    v3 = *a2;
    *a2 = 0;
  }
  v4 = *a1;
  *a1 = v3;
  v6[0] = v4;
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(v6);
  return a1;
}

```

## disassembly

```asm
0x14000a500  push    rbx
0x14000a502  sub     rsp, 30h
0x14000a506  mov     rbx, rcx
0x14000a509  lea     rax, [rsp+38h+var_18]
0x14000a50e  xor     ecx, ecx
0x14000a510  cmp     rax, rdx
0x14000a513  jz      short loc_14000A51F
0x14000a515  mov     rcx, [rdx]
0x14000a518  mov     qword ptr [rdx], 0
0x14000a51f  mov     rax, [rbx]
0x14000a522  mov     [rbx], rcx
0x14000a525  lea     rcx, [rsp+38h+var_18]
0x14000a52a  mov     [rsp+38h+var_18], rax
0x14000a52f  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000a534  mov     rax, rbx
0x14000a537  add     rsp, 30h
0x14000a53b  pop     rbx
0x14000a53c  retn
```
