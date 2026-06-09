# Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)

- ea: `0x180009fc0`
- end: `0x180009fe6`
- name: `?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ`
- size: `38`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `49`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800050e4`
- `0x180006f00`
- `0x1800077fc`
- `0x180008750`
- `0x18000d58c`
- `0x18000fa98`
- `0x18000fbc0`
- `0x18000fce8`
- `0x180010678`
- `0x1800107b8`
- `0x1800108f8`
- `0x180011cc4`
- `0x18001295c`
- `0x180012d60`
- `0x180013a2c`
- `0x180016b54`
- `0x180017144`
- `0x1800179e8`
- `0x180017b98`
- `0x18001ea14`
- `0x18001ea64`
- `0x18001ef30`
- `0x18001f118`
- `0x18001f554`
- `0x18001f77c`
- `0x18001f9a4`
- `0x1800203b0`
- `0x180020e9c`
- `0x1800214dc`
- `0x1800215d8`
- `0x180021be4`
- `0x180021d44`
- `0x180022084`
- `0x180022790`
- `0x180022a1c`
- `0x1800230d0`
- `0x1800235d0`
- `0x1800237f0`
- `0x180023a40`
- `0x1800249a8`
- `0x180024ca0`
- `0x180024de0`
- `0x180024f40`
- `0x180024fe0`
- `0x180025108`
- `0x1800251d0`
- `0x180025614`
- `0x1800256ac`
- `0x180026630`

## callees

- `0x180009fc0`
- `0x18002b010`

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
0x180009fc0  sub     rsp, 28h
0x180009fc4  mov     rdx, rcx
0x180009fc7  xor     eax, eax
0x180009fc9  mov     rcx, [rcx]
0x180009fcc  test    rcx, rcx
0x180009fcf  jz      short loc_180009FE1
0x180009fd1  mov     [rdx], rax
0x180009fd4  mov     rax, [rcx]
0x180009fd7  mov     rax, [rax+10h]
0x180009fdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fe0  nop
0x180009fe1  add     rsp, 28h
0x180009fe5  retn
```
