# MbbNdisGetSarConfig(_MBB_REQUEST_CONTEXT *,uchar *,ulong *,uchar *,ulong *)

- ea: `0x1400117c0`
- end: `0x140011826`
- name: `?MbbNdisGetSarConfig@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEPEAK12@Z`
- size: `102`
- prototype: `__int64 __fastcall(struct _MBB_REQUEST_CONTEXT *, unsigned __int8 *, unsigned int *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callees

- `0x140001cf8`
- `0x1400117c0`
- `0x14001fc2c`

## pseudocode

```c
__int64 __fastcall MbbNdisGetSarConfig(
        struct _MBB_REQUEST_CONTEXT *a1,
        unsigned __int8 *a2,
        unsigned int *a3,
        unsigned __int8 *a4)
{
  __int64 *v4; // rax
  __int64 v5; // rdx

  v4 = (__int64 *)*((_QWORD *)a1 + 6);
  v5 = *v4;
  if ( (*(_DWORD *)(*v4 + 1088) & 0x400) != 0 )
    return MbbUtilQueryAttributeWithParameter(a1, 0, 0);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v5) = 4;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v5,
      3,
      78,
      (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids);
  }
  return 3221225659LL;
}

```

## disassembly

```asm
0x1400117c0  sub     rsp, 38h
0x1400117c4  mov     rax, [rcx+30h]
0x1400117c8  mov     rdx, [rax]
0x1400117cb  test    dword ptr [rdx+440h], 400h
0x1400117d5  jnz     short loc_140011816
0x1400117d7  lea     rax, WPP_RECORDER_INITIALIZED
0x1400117de  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400117e5  jz      short loc_14001180F
0x1400117e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400117ee  lea     rax, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x1400117f5  mov     r9d, 4Eh ; 'N'
0x1400117fb  mov     [rsp+38h+var_18], rax
0x140011800  mov     dl, 4
0x140011802  mov     rcx, [rcx+40h]
0x140011806  lea     r8d, [r9-4Bh]
0x14001180a  call    WPP_RECORDER_SF_
0x14001180f  mov     eax, 0C00000BBh
0x140011814  jmp     short loc_140011820
0x140011816  xor     r8d, r8d; unsigned int
0x140011819  xor     edx, edx; unsigned __int8 *
0x14001181b  call    ?MbbUtilQueryAttributeWithParameter@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEK@Z; MbbUtilQueryAttributeWithParameter(_MBB_REQUEST_CONTEXT *,uchar *,ulong)
0x140011820  add     rsp, 38h
0x140011824  retn
```
