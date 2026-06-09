# CIEAdminBrokerObject::UpdateDistributionUnit2(ushort *,ushort const *,ushort const *,ulong,ulong *,ushort const *,int,ushort const *,ushort const *,long,ushort const *,ushort const *,ushort const *,ulong,ushort const * *,int *,ulong,ushort const * *,ulong,ushort const * *,ushort const * *)

- ea: `0x405f90`
- end: `0x405fec`
- name: `?UpdateDistributionUnit2@CIEAdminBrokerObject@@UAGJPAGPBG1KPAK1H11J111KPAPBGPAHK3K33@Z`
- size: `92`
- prototype: `int(CIEAdminBrokerObject *__hidden this, unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int *, const unsigned __int16 *, int, const unsigned __int16 *, const unsigned __int16 *, int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const unsigned __int16 **, int *, unsigned int, const unsigned __int16 **, unsigned int, const unsigned __int16 **, const unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x404c02`
- `0x405f90`

## pseudocode

```c

```

## disassembly

```asm
0x405f90  mov     edi, edi
0x405f92  push    ebp; unsigned __int16 **
0x405f93  mov     ebp, esp
0x405f95  mov     eax, [ebp+this]
0x405f98  mov     ecx, 80004005h
0x405f9d  cmp     dword ptr [eax+8], 0
0x405fa1  jz      short loc_405FE6
0x405fa3  sub     esp, 0Ch
0x405fa6  mov     edx, [ebp+arg_4]
0x405fa9  mov     ecx, [eax+8]
0x405fac  push    [ebp+arg_48]; int *
0x405faf  push    [ebp+arg_44]; unsigned __int16 **
0x405fb2  push    [ebp+arg_40]; unsigned int
0x405fb5  push    [ebp+arg_3C]; unsigned __int16 *
0x405fb8  push    [ebp+arg_38]; unsigned __int16 *
0x405fbb  push    [ebp+arg_34]; unsigned __int16 *
0x405fbe  push    [ebp+arg_30]; int
0x405fc1  push    [ebp+arg_2C]; unsigned __int16 *
0x405fc4  push    [ebp+arg_28]; unsigned __int16 *
0x405fc7  push    [ebp+arg_24]; int
0x405fca  push    [ebp+arg_20]; unsigned __int16 *
0x405fcd  push    [ebp+arg_1C]; unsigned int *
0x405fd0  push    [ebp+arg_18]; unsigned int
0x405fd3  push    [ebp+arg_14]; unsigned __int16 *
0x405fd6  push    [ebp+arg_10]; unsigned __int16 *
0x405fd9  push    [ebp+arg_C]; unsigned __int16 *
0x405fdc  push    [ebp+arg_8]; this
0x405fdf  call    ?UpdateDistributionUnit2@CActiveXInstallBroker@@QAGJPAGPBG1KPAK1H11J111KPAPBGPAHK3K33@Z; CActiveXInstallBroker::UpdateDistributionUnit2(ushort *,ushort const *,ushort const *,ulong,ulong *,ushort const *,int,ushort const *,ushort const *,long,ushort const *,ushort const *,ushort const *,ulong,ushort const * *,int *,ulong,ushort const * *,ulong,ushort const * *,ushort const * *)
0x405fe4  mov     ecx, eax
0x405fe6  mov     eax, ecx
0x405fe8  pop     ebp
0x405fe9  retn    58h ; 'X'
```
