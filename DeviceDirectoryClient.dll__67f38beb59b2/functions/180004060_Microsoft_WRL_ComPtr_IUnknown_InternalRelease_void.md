# Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)

- ea: `0x180004060`
- end: `0x180004086`
- name: `?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ`
- size: `38`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `63`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800037bc`
- `0x18000921c`
- `0x18000c034`
- `0x18000ca4c`
- `0x1800101f0`
- `0x1800107e0`
- `0x1800115e0`
- `0x1800128fc`
- `0x180013ae8`
- `0x180013b38`
- `0x18001488c`
- `0x180014c44`
- `0x180015120`
- `0x180015504`
- `0x180015a4c`
- `0x180015fbc`
- `0x18001691c`
- `0x180016aa4`
- `0x1800183c4`
- `0x180018c8c`
- `0x18001bf54`
- `0x18001c978`
- `0x18001cd18`
- `0x18001ce80`
- `0x18001cfe8`
- `0x18001d150`
- `0x18001d2b8`
- `0x18001d420`
- `0x18001d588`
- `0x18001dcfc`
- `0x18001e164`
- `0x18001e8a0`
- `0x18001f23c`
- `0x18001f2e0`
- `0x18001fd74`
- `0x180020068`
- `0x1800204a4`
- `0x180020d2c`
- `0x18002166c`
- `0x180022240`
- `0x180023180`
- `0x180023f8c`
- `0x1800243d8`
- `0x18002450c`
- `0x1800246a8`
- `0x1800247e0`
- `0x180024830`
- `0x180024ae0`
- `0x180025584`
- `0x1800256b8`

## callees

- `0x180004060`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(__int64 *a1)
{
  __int64 result; // rax
  __int64 v3; // rcx

  result = 0;
  v3 = *a1;
  if ( v3 )
  {
    *a1 = 0;
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  return result;
}

```

## disassembly

```asm
0x180004060  sub     rsp, 28h
0x180004064  mov     rdx, rcx
0x180004067  xor     eax, eax
0x180004069  mov     rcx, [rcx]
0x18000406c  test    rcx, rcx
0x18000406f  jz      short loc_180004081
0x180004071  mov     [rdx], rax
0x180004074  mov     rax, [rcx]
0x180004077  mov     rax, [rax+10h]
0x18000407b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004080  nop
0x180004081  add     rsp, 28h
0x180004085  retn
```
