# CIEAdminBrokerObject::UpdateDistributionUnit(ushort *,ushort const *,ushort const *,ulong,ulong *,ushort const *,int,ushort const *,ushort const *,long,ushort const *,ushort const *,ushort const *,ulong,ushort const * *,ulong,ushort const * *,ulong,ushort const * *,ushort const * *)

- ea: `0x405f20`
- end: `0x405f7b`
- name: `?UpdateDistributionUnit@CIEAdminBrokerObject@@UAGJPAGPBG1KPAK1H11J111KPAPBGK3K33@Z`
- size: `91`
- prototype: `int(CIEAdminBrokerObject *__hidden this, unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int *, const unsigned __int16 *, int, const unsigned __int16 *, const unsigned __int16 *, int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const unsigned __int16 **, unsigned int, const unsigned __int16 **, unsigned int, const unsigned __int16 **, const unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x404c02`
- `0x405f20`

## pseudocode

```c

```

## disassembly

```asm
0x405f20  mov     edi, edi
0x405f22  push    ebp; unsigned __int16 **
0x405f23  mov     ebp, esp
0x405f25  mov     eax, [ebp+this]
0x405f28  mov     ecx, 80004005h
0x405f2d  cmp     dword ptr [eax+8], 0
0x405f31  jz      short loc_405F75
0x405f33  sub     esp, 0Ch
0x405f36  mov     edx, [ebp+arg_4]
0x405f39  mov     ecx, [eax+8]
0x405f3c  push    [ebp+arg_44]; int *
0x405f3f  push    [ebp+arg_40]; unsigned __int16 **
0x405f42  push    0; unsigned int
0x405f44  push    [ebp+arg_3C]; unsigned __int16 *
0x405f47  push    [ebp+arg_38]; unsigned __int16 *
0x405f4a  push    [ebp+arg_34]; unsigned __int16 *
0x405f4d  push    [ebp+arg_30]; int
0x405f50  push    [ebp+arg_2C]; unsigned __int16 *
0x405f53  push    [ebp+arg_28]; unsigned __int16 *
0x405f56  push    [ebp+arg_24]; int
0x405f59  push    [ebp+arg_20]; unsigned __int16 *
0x405f5c  push    [ebp+arg_1C]; unsigned int *
0x405f5f  push    [ebp+arg_18]; unsigned int
0x405f62  push    [ebp+arg_14]; unsigned __int16 *
0x405f65  push    [ebp+arg_10]; unsigned __int16 *
0x405f68  push    [ebp+arg_C]; unsigned __int16 *
0x405f6b  push    [ebp+arg_8]; this
0x405f6e  call    ?UpdateDistributionUnit2@CActiveXInstallBroker@@QAGJPAGPBG1KPAK1H11J111KPAPBGPAHK3K33@Z; CActiveXInstallBroker::UpdateDistributionUnit2(ushort *,ushort const *,ushort const *,ulong,ulong *,ushort const *,int,ushort const *,ushort const *,long,ushort const *,ushort const *,ushort const *,ulong,ushort const * *,int *,ulong,ushort const * *,ulong,ushort const * *,ushort const * *)
0x405f73  mov     ecx, eax
0x405f75  mov     eax, ecx
0x405f77  pop     ebp
0x405f78  retn    54h ; 'T'
```
