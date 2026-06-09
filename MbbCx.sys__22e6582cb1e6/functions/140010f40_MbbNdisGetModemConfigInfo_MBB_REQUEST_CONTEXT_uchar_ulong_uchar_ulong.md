# MbbNdisGetModemConfigInfo(_MBB_REQUEST_CONTEXT *,uchar *,ulong *,uchar *,ulong *)

- ea: `0x140010f40`
- end: `0x140010ff4`
- name: `?MbbNdisGetModemConfigInfo@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEPEAK12@Z`
- size: `180`
- prototype: `__int64 __fastcall(struct _MBB_REQUEST_CONTEXT *, unsigned __int8 *, unsigned int *, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x140001cf8`
- `0x140001db8`
- `0x140010f40`
- `0x14001fc2c`

## pseudocode

```c
__int64 __fastcall MbbNdisGetModemConfigInfo(
        struct _MBB_REQUEST_CONTEXT *a1,
        unsigned __int8 *a2,
        unsigned int *a3,
        unsigned __int8 *a4)
{
  __int64 v4; // rax
  int v5; // edx
  int v7; // [rsp+28h] [rbp-10h]

  v4 = **((_QWORD **)a1 + 6);
  v5 = *(unsigned __int16 *)(v4 + 82);
  if ( (unsigned __int16)v5 < 0x300u )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v7 = *(unsigned __int16 *)(v4 + 82);
      LOBYTE(v5) = 4;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v5,
        3,
        83,
        (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids,
        v7);
    }
    return 3221225659LL;
  }
  if ( (*(_DWORD *)(v4 + 1088) & 0x2000000) == 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = 4;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v5,
        3,
        84,
        (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids);
    }
    return 3221225659LL;
  }
  return MbbUtilQueryAttributeWithParameter(a1, 0, 0);
}

```

## disassembly

```asm
0x140010f40  sub     rsp, 38h
0x140010f44  mov     rax, [rcx+30h]
0x140010f48  mov     r8d, 300h
0x140010f4e  mov     rax, [rax]
0x140010f51  movzx   edx, word ptr [rax+52h]
0x140010f55  cmp     dx, r8w
0x140010f59  jnb     short loc_140010F99
0x140010f5b  lea     rax, WPP_RECORDER_INITIALIZED
0x140010f62  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140010f69  jz      short loc_140010FDD
0x140010f6b  mov     rcx, cs:WPP_GLOBAL_Control
0x140010f72  lea     rax, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x140010f79  mov     [rsp+38h+var_10], edx
0x140010f7d  mov     r9d, 53h ; 'S'
0x140010f83  mov     dl, 4
0x140010f85  mov     [rsp+38h+var_18], rax
0x140010f8a  mov     rcx, [rcx+40h]
0x140010f8e  lea     r8d, [r9-50h]
0x140010f92  call    WPP_RECORDER_SF_d
0x140010f97  jmp     short loc_140010FDD
0x140010f99  test    dword ptr [rax+440h], 2000000h
0x140010fa3  jnz     short loc_140010FE4
0x140010fa5  lea     rax, WPP_RECORDER_INITIALIZED
0x140010fac  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140010fb3  jz      short loc_140010FDD
0x140010fb5  mov     rcx, cs:WPP_GLOBAL_Control
0x140010fbc  lea     rax, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x140010fc3  mov     r9d, 54h ; 'T'
0x140010fc9  mov     [rsp+38h+var_18], rax
0x140010fce  mov     dl, 4
0x140010fd0  mov     rcx, [rcx+40h]
0x140010fd4  lea     r8d, [r9-51h]
0x140010fd8  call    WPP_RECORDER_SF_
0x140010fdd  mov     eax, 0C00000BBh
0x140010fe2  jmp     short loc_140010FEE
0x140010fe4  xor     r8d, r8d; unsigned int
0x140010fe7  xor     edx, edx; unsigned __int8 *
0x140010fe9  call    ?MbbUtilQueryAttributeWithParameter@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEK@Z; MbbUtilQueryAttributeWithParameter(_MBB_REQUEST_CONTEXT *,uchar *,ulong)
0x140010fee  add     rsp, 38h
0x140010ff2  retn
```
