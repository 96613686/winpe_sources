# PrecacheStoreLicenseForPackageResume

- ea: `0x180010c90`
- end: `0x180010cba`
- name: `PrecacheStoreLicenseForPackageResume`
- size: `42`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000640c`

## pseudocode

```c
__int64 __fastcall PrecacheStoreLicenseForPackageResume(__int64 a1, unsigned int a2, __int64 a3)
{
  unsigned int v4; // [rsp+38h] [rbp+10h] BYREF
  __int64 v5; // [rsp+40h] [rbp+18h] BYREF

  v5 = a3;
  v4 = a2;
  return CallV2ApiWithPsmKey<long (*)(unsigned short const *,unsigned long,void *),unsigned short const *,unsigned long &,void * &>(
           (__int64 (__fastcall *)(_BYTE *, _QWORD, _QWORD))PrecacheStoreLicenseForPackageResume2,
           a1,
           &v4,
           &v5);
}

```

## disassembly

```asm
0x180010c90  mov     rax, rsp
0x180010c93  mov     [rax+18h], r8
0x180010c97  mov     [rax+10h], edx
0x180010c9a  sub     rsp, 28h
0x180010c9e  mov     rdx, rcx
0x180010ca1  lea     r9, [rax+18h]
0x180010ca5  lea     rcx, PrecacheStoreLicenseForPackageResume2
0x180010cac  lea     r8, [rax+10h]
0x180010cb0  call    ??$CallV2ApiWithPsmKey@P6AJPEBGKPEAX@ZPEBGAEAKAEAPEAX@@YAJP6AJPEBGKPEAX@Z0AEAKAEAPEAX@Z; CallV2ApiWithPsmKey<long (*)(ushort const *,ulong,void *),ushort const *,ulong &,void * &>(long (*)(ushort const *,ulong,void *),ushort const *,ulong &,void * &)
0x180010cb5  add     rsp, 28h
0x180010cb9  retn
```
