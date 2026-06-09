# CRegistryChangeListener::Release(void)

- ea: `0x180009320`
- end: `0x180009359`
- name: `?Release@CRegistryChangeListener@@UEAAKXZ`
- size: `57`
- prototype: `__int64 __fastcall(CRegistryChangeListener *this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x180009180`
- `0x180009360`
- `0x1800093b4`

## callees

- `0x1800019f8`
- `0x1800090dc`
- `0x180009320`

## pseudocode

```c
__int64 __fastcall CRegistryChangeListener::Release(CRegistryChangeListener *this)
{
  unsigned __int32 v2; // edi

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 4);
  if ( !v2 && this )
  {
    CRegistryChangeListener::~CRegistryChangeListener(this);
    operator delete(this);
  }
  return v2;
}

```

## disassembly

```asm
0x180009320  mov     [rsp+arg_0], rbx
0x180009325  push    rdi
0x180009326  sub     rsp, 20h
0x18000932a  mov     rbx, rcx
0x18000932d  or      edi, 0FFFFFFFFh
0x180009330  lock xadd [rcx+10h], edi
0x180009335  sub     edi, 1
0x180009338  jnz     short loc_18000934C
0x18000933a  test    rcx, rcx
0x18000933d  jz      short loc_18000934C
0x18000933f  call    ??1CRegistryChangeListener@@AEAA@XZ; CRegistryChangeListener::~CRegistryChangeListener(void)
0x180009344  mov     rcx, rbx; Block
0x180009347  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000934c  mov     rbx, [rsp+28h+arg_0]
0x180009351  mov     eax, edi
0x180009353  add     rsp, 20h
0x180009357  pop     rdi
0x180009358  retn
```
