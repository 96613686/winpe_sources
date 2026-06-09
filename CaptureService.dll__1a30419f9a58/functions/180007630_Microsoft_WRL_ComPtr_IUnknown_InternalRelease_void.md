# Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)

- ea: `0x180007630`
- end: `0x180007656`
- name: `?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ`
- size: `38`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `58`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800050d0`
- `0x180005850`
- `0x18000b9a4`
- `0x18000bbb0`
- `0x18000bc00`
- `0x18000bf00`
- `0x18000c0ac`
- `0x18000c148`
- `0x18000c5bc`
- `0x18000cd90`
- `0x18000d740`
- `0x18000d970`
- `0x18000d9ac`
- `0x18000d9d4`
- `0x18000da10`
- `0x18000da20`
- `0x18000dafc`
- `0x18000db40`
- `0x18000dc54`
- `0x18000dcf4`
- `0x18000e080`
- `0x18000e1ac`
- `0x18000e264`
- `0x18000e2ac`
- `0x18000e3b8`
- `0x18000e630`
- `0x18000f340`
- `0x18000f53c`
- `0x18000f6e8`
- `0x18000fe60`
- `0x18000ff50`
- `0x180010170`
- `0x18001024c`
- `0x180010568`
- `0x180010f5c`
- `0x180011740`
- `0x180011928`
- `0x180013150`
- `0x180013230`
- `0x180014824`
- `0x180014a24`
- `0x180016dc4`
- `0x180017318`
- `0x180017768`
- `0x1800177f8`
- `0x180018700`
- `0x180018da4`
- `0x18001932c`
- `0x180019368`
- `0x180019390`

## callees

- `0x180007630`
- `0x180022010`

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
0x180007630  sub     rsp, 28h
0x180007634  mov     rdx, rcx
0x180007637  xor     eax, eax
0x180007639  mov     rcx, [rcx]
0x18000763c  test    rcx, rcx
0x18000763f  jz      short loc_180007651
0x180007641  mov     [rdx], rax
0x180007644  mov     rax, [rcx]
0x180007647  mov     rax, [rax+10h]
0x18000764b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007650  nop
0x180007651  add     rsp, 28h
0x180007655  retn
```
