# Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(void)

- ea: `0x1400098dc`
- end: `0x140009902`
- name: `?InternalRelease@?$ComPtr@UIPackageLocationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ`
- size: `38`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `16`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140007dfc`
- `0x140008368`
- `0x1400083b4`
- `0x1400084d0`
- `0x140008600`
- `0x140008758`
- `0x140009448`
- `0x1400095e4`
- `0x140009758`
- `0x140009918`
- `0x140009cd8`
- `0x14000a8a8`
- `0x14000aa08`
- `0x14000eeb0`
- `0x14000eef0`
- `0x14000ef10`

## callees

- `0x1400098dc`
- `0x14000f010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(
        __int64 *a1)
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
0x1400098dc  sub     rsp, 28h
0x1400098e0  mov     rdx, rcx
0x1400098e3  xor     eax, eax
0x1400098e5  mov     rcx, [rcx]
0x1400098e8  test    rcx, rcx
0x1400098eb  jz      short loc_1400098FD
0x1400098ed  mov     [rdx], rax
0x1400098f0  mov     rax, [rcx]
0x1400098f3  mov     rax, [rax+10h]
0x1400098f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400098fc  nop
0x1400098fd  add     rsp, 28h
0x140009901  retn
```
