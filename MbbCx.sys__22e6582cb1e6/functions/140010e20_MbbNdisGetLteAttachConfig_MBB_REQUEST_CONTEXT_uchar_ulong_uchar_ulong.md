# MbbNdisGetLteAttachConfig(_MBB_REQUEST_CONTEXT *,uchar *,ulong *,uchar *,ulong *)

- ea: `0x140010e20`
- end: `0x140010e86`
- name: `?MbbNdisGetLteAttachConfig@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEPEAK12@Z`
- size: `102`
- prototype: `__int64 __fastcall(struct _MBB_REQUEST_CONTEXT *, unsigned __int8 *, unsigned int *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callees

- `0x140001cf8`
- `0x140010e20`
- `0x14001fc2c`

## pseudocode

```c
__int64 __fastcall MbbNdisGetLteAttachConfig(
        struct _MBB_REQUEST_CONTEXT *a1,
        unsigned __int8 *a2,
        unsigned int *a3,
        unsigned __int8 *a4)
{
  __int64 *v4; // rax
  __int64 v5; // rdx

  v4 = (__int64 *)*((_QWORD *)a1 + 6);
  v5 = *v4;
  if ( (*(_DWORD *)(*v4 + 1088) & 0x800) != 0 )
    return MbbUtilQueryAttributeWithParameter(a1, 0, 0);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v5) = 4;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v5,
      3,
      80,
      (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids);
  }
  return 3221225659LL;
}

```

## disassembly

```asm
0x140010e20  sub     rsp, 38h
0x140010e24  mov     rax, [rcx+30h]
0x140010e28  mov     rdx, [rax]
0x140010e2b  test    dword ptr [rdx+440h], 800h
0x140010e35  jnz     short loc_140010E76
0x140010e37  lea     rax, WPP_RECORDER_INITIALIZED
0x140010e3e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140010e45  jz      short loc_140010E6F
0x140010e47  mov     rcx, cs:WPP_GLOBAL_Control
0x140010e4e  lea     rax, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x140010e55  mov     r9d, 50h ; 'P'
0x140010e5b  mov     [rsp+38h+var_18], rax
0x140010e60  mov     dl, 4
0x140010e62  mov     rcx, [rcx+40h]
0x140010e66  lea     r8d, [r9-4Dh]
0x140010e6a  call    WPP_RECORDER_SF_
0x140010e6f  mov     eax, 0C00000BBh
0x140010e74  jmp     short loc_140010E80
0x140010e76  xor     r8d, r8d; unsigned int
0x140010e79  xor     edx, edx; unsigned __int8 *
0x140010e7b  call    ?MbbUtilQueryAttributeWithParameter@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEK@Z; MbbUtilQueryAttributeWithParameter(_MBB_REQUEST_CONTEXT *,uchar *,ulong)
0x140010e80  add     rsp, 38h
0x140010e84  retn
```
