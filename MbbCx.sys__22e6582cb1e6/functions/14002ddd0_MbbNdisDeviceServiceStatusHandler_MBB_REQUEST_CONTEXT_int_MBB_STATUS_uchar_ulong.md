# MbbNdisDeviceServiceStatusHandler(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)

- ea: `0x14002ddd0`
- end: `0x14002de8d`
- name: `?MbbNdisDeviceServiceStatusHandler@@YAHPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z`
- size: `189`
- prototype: `__int64 __fastcall(__int64, int, unsigned int, const void *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x140018610`
- `0x14002d18c`
- `0x14002daa0`
- `0x14002ddd0`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14002ddfd`
- `ntoskrnl!RtlCompareMemory` at `0x14002ddfd`

## pseudocode

```c
__int64 __fastcall MbbNdisDeviceServiceStatusHandler(
        __int64 a1,
        int a2,
        unsigned int a3,
        const void *a4,
        unsigned int a5)
{
  __int64 v5; // r14
  int v10; // edx
  int v11; // r8d

  v5 = a1 + 704;
  if ( RtlCompareMemory((const void *)(a1 + 704), &MBB_UUID_INVALID, 0x10u) == 16 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_D_guid_(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        v11,
        193,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *(_DWORD *)(a1 + 16),
        v5);
    }
    return 3221291029LL;
  }
  else if ( *(_BYTE *)(a1 + 576) )
  {
    return MbbNdisDeviceServiceEventStatusHandler(a1, a2, a3, a4, a5);
  }
  else
  {
    return MbbNdisDeviceServiceResponseStatusHandler(a1, a2, a3, a4, a5);
  }
}

```

## disassembly

```asm
0x14002ddd0  push    rbx
0x14002ddd2  push    rbp
0x14002ddd3  push    rsi
0x14002ddd4  push    rdi
0x14002ddd5  push    r14
0x14002ddd7  sub     rsp, 40h
0x14002dddb  lea     r14, [rcx+2C0h]
0x14002dde2  mov     esi, r8d
0x14002dde5  mov     ebp, edx
0x14002dde7  mov     rbx, rcx
0x14002ddea  mov     rcx, r14; Source1
0x14002dded  lea     rdx, MBB_UUID_INVALID; Source2
0x14002ddf4  mov     r8d, 10h; Length
0x14002ddfa  mov     rdi, r9
0x14002ddfd  call    cs:__imp_RtlCompareMemory
0x14002de04  nop     dword ptr [rax+rax+00h]
0x14002de09  cmp     rax, 10h
0x14002de0d  jnz     short loc_14002DE56
0x14002de0f  lea     rax, WPP_RECORDER_INITIALIZED
0x14002de16  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002de1d  jz      short loc_14002DE4F
0x14002de1f  mov     eax, [rbx+10h]
0x14002de22  mov     r9d, 0C1h
0x14002de28  mov     rcx, cs:WPP_GLOBAL_Control
0x14002de2f  mov     dl, 2
0x14002de31  mov     [rsp+68h+var_38], r14
0x14002de36  mov     [rsp+68h+var_40], eax
0x14002de3a  lea     rax, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14002de41  mov     [rsp+68h+var_48], rax
0x14002de46  mov     rcx, [rcx+40h]
0x14002de4a  call    WPP_RECORDER_SF_D_guid_
0x14002de4f  mov     eax, 0C0010015h
0x14002de54  jmp     short loc_14002DE81
0x14002de56  cmp     byte ptr [rbx+240h], 0
0x14002de5d  mov     r9, rdi
0x14002de60  mov     eax, [rsp+68h+arg_20]
0x14002de67  mov     r8d, esi
0x14002de6a  mov     dword ptr [rsp+68h+var_48], eax
0x14002de6e  mov     edx, ebp
0x14002de70  mov     rcx, rbx
0x14002de73  jz      short loc_14002DE7C
0x14002de75  call    ?MbbNdisDeviceServiceEventStatusHandler@@YAHPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z; MbbNdisDeviceServiceEventStatusHandler(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)
0x14002de7a  jmp     short loc_14002DE81
0x14002de7c  call    ?MbbNdisDeviceServiceResponseStatusHandler@@YAHPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z; MbbNdisDeviceServiceResponseStatusHandler(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)
0x14002de81  add     rsp, 40h
0x14002de85  pop     r14
0x14002de87  pop     rdi
0x14002de88  pop     rsi
0x14002de89  pop     rbp
0x14002de8a  pop     rbx
0x14002de8b  retn
```
