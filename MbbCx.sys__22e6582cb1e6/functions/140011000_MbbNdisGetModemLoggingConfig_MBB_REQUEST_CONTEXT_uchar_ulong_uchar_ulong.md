# MbbNdisGetModemLoggingConfig(_MBB_REQUEST_CONTEXT *,uchar *,ulong *,uchar *,ulong *)

- ea: `0x140011000`
- end: `0x140011066`
- name: `?MbbNdisGetModemLoggingConfig@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEPEAK12@Z`
- size: `102`
- prototype: `__int64 __fastcall(struct _MBB_REQUEST_CONTEXT *, unsigned __int8 *, unsigned int *, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callees

- `0x140001cf8`
- `0x140011000`
- `0x14001fc2c`

## pseudocode

```c
__int64 __fastcall MbbNdisGetModemLoggingConfig(
        struct _MBB_REQUEST_CONTEXT *a1,
        unsigned __int8 *a2,
        unsigned int *a3,
        unsigned __int8 *a4)
{
  __int64 *v4; // rax
  __int64 v5; // rdx

  v4 = (__int64 *)*((_QWORD *)a1 + 6);
  v5 = *v4;
  if ( (*(_DWORD *)(*v4 + 1088) & 0x40000) != 0 )
    return MbbUtilQueryAttributeWithParameter(a1, 0, 0);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v5) = 4;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v5,
      3,
      82,
      (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids);
  }
  return 3221225659LL;
}

```

## disassembly

```asm
0x140011000  sub     rsp, 38h
0x140011004  mov     rax, [rcx+30h]
0x140011008  mov     rdx, [rax]
0x14001100b  test    dword ptr [rdx+440h], 40000h
0x140011015  jnz     short loc_140011056
0x140011017  lea     rax, WPP_RECORDER_INITIALIZED
0x14001101e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140011025  jz      short loc_14001104F
0x140011027  mov     rcx, cs:WPP_GLOBAL_Control
0x14001102e  lea     rax, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x140011035  mov     r9d, 52h ; 'R'
0x14001103b  mov     [rsp+38h+var_18], rax
0x140011040  mov     dl, 4
0x140011042  mov     rcx, [rcx+40h]
0x140011046  lea     r8d, [r9-4Fh]
0x14001104a  call    WPP_RECORDER_SF_
0x14001104f  mov     eax, 0C00000BBh
0x140011054  jmp     short loc_140011060
0x140011056  xor     r8d, r8d; unsigned int
0x140011059  xor     edx, edx; unsigned __int8 *
0x14001105b  call    ?MbbUtilQueryAttributeWithParameter@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAEK@Z; MbbUtilQueryAttributeWithParameter(_MBB_REQUEST_CONTEXT *,uchar *,ulong)
0x140011060  add     rsp, 38h
0x140011064  retn
```
