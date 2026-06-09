# Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)

- ea: `0x14000e920`
- end: `0x14000e945`
- name: `?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ`
- size: `37`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `30`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140005dd4`
- `0x140006f50`
- `0x140008380`
- `0x140008b38`
- `0x140008b68`
- `0x140009340`
- `0x14000957c`
- `0x1400099a8`
- `0x14000a150`
- `0x14000af00`
- `0x14000b200`
- `0x14000b290`
- `0x14000b320`
- `0x14000b3a8`
- `0x14000bb90`
- `0x14000e370`
- `0x140010be0`
- `0x140010d10`
- `0x140011100`
- `0x1400111ac`
- `0x1400115c4`
- `0x140013ae4`
- `0x140016940`
- `0x140018498`
- `0x14001894c`
- `0x140018c68`
- `0x14001c3d4`
- `0x14001d20c`
- `0x14001d730`
- `0x14001d968`

## callees

- `0x14000e920`
- `0x14001f010`

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
0x14000e920  sub     rsp, 28h
0x14000e924  mov     rdx, rcx
0x14000e927  xor     eax, eax
0x14000e929  mov     rcx, [rcx]
0x14000e92c  test    rcx, rcx
0x14000e92f  jz      short loc_14000E940
0x14000e931  mov     [rdx], rax
0x14000e934  mov     rax, [rcx]
0x14000e937  mov     rax, [rax+10h]
0x14000e93b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e940  add     rsp, 28h
0x14000e944  retn
```
