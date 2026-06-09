# CRAServerModule::UpdateRegistryAppId(int)

- ea: `0x14000dc74`
- end: `0x14000dcb0`
- name: `?UpdateRegistryAppId@CRAServerModule@@SAJH@Z`
- size: `60`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x14000d6d0`

## callees

- `0x14000b238`

## pseudocode

```c
__int64 __fastcall CRAServerModule::UpdateRegistryAppId(ATL::CAtlModule *a1)
{
  _QWORD v2[2]; // [rsp+20h] [rbp-28h] BYREF
  __int128 v3; // [rsp+30h] [rbp-18h]

  v2[0] = L"APPID";
  v2[1] = L"{F8FD03A6-DDD9-4C1B-84EE-58159476A0D7}";
  v3 = 0;
  return ATL::CAtlModule::UpdateRegistryFromResourceS(a1, 0x65u, (int)a1, (struct ATL::_ATL_REGMAP_ENTRY *)v2);
}

```

## disassembly

```asm
0x14000dc74  sub     rsp, 48h
0x14000dc78  lea     rax, aAppid; "APPID"
0x14000dc7f  xorps   xmm0, xmm0
0x14000dc82  mov     [rsp+48h+var_28], rax
0x14000dc87  lea     r9, [rsp+48h+var_28]; struct ATL::_ATL_REGMAP_ENTRY *
0x14000dc8c  lea     rax, aF8fd03a6Ddd94c; "{F8FD03A6-DDD9-4C1B-84EE-58159476A0D7}"
0x14000dc93  mov     r8d, ecx; int
0x14000dc96  mov     edx, 65h ; 'e'; unsigned int
0x14000dc9b  mov     [rsp+48h+var_20], rax
0x14000dca0  movdqu  [rsp+48h+var_18], xmm0
0x14000dca6  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x14000dcab  add     rsp, 48h
0x14000dcaf  retn
```
