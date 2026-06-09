# Task::get_TaskDeviceCommand(DeviceCommand * *)

- ea: `0x140063240`
- end: `0x1400632f4`
- name: `?get_TaskDeviceCommand@Task@@QEAAHPEAPEAVDeviceCommand@@@Z`
- size: `180`
- prototype: `__int64 __fastcall(Task *__hidden this, struct DeviceCommand **)`
- caller_count: `12`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140063764`
- `0x14006b410`
- `0x140071c10`
- `0x14007bbd0`
- `0x14007f3bc`
- `0x140081588`
- `0x14009292c`
- `0x1400ad300`
- `0x1400b511c`
- `0x1400ba93c`
- `0x1400bb1b0`
- `0x1400c5aa0`

## callees

- `0x14001e2c0`
- `0x14001eed0`
- `0x140063240`

## pseudocode

```c
__int64 __fastcall Task::get_TaskDeviceCommand(Task *this, struct DeviceCommand **a2, int a3)
{
  unsigned int v4; // ebx

  if ( a2 )
  {
    v4 = 0;
    *a2 = (Task *)((char *)this + 56);
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        a3,
        59,
        (__int64)WPP_a1b4414c73513c72229efa91c05f01c7_Traceguids,
        (char)this,
        *((_DWORD *)this + 8));
    }
    v4 = -1073741811;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = 5;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        *((_DWORD *)this + 8),
        60,
        (__int64)WPP_a1b4414c73513c72229efa91c05f01c7_Traceguids,
        (char)this,
        *((_DWORD *)this + 8),
        v4);
  }
  return v4;
}

```

## disassembly

```asm
0x140063240  push    rbx
0x140063242  push    rbp
0x140063243  push    rsi
0x140063244  push    rdi
0x140063245  push    r14
0x140063247  sub     rsp, 40h
0x14006324b  xor     esi, esi
0x14006324d  lea     rbp, WPP_RECORDER_INITIALIZED
0x140063254  lea     r14, WPP_a1b4414c73513c72229efa91c05f01c7_Traceguids
0x14006325b  mov     rdi, rcx
0x14006325e  test    rdx, rdx
0x140063261  jnz     short loc_14006329A
0x140063263  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14006326a  jz      short loc_140063293
0x14006326c  mov     eax, [rcx+20h]
0x14006326f  lea     r9d, [rsi+3Bh]
0x140063273  mov     [rsp+68h+var_38], eax
0x140063277  mov     dl, 2
0x140063279  mov     [rsp+68h+var_40], rcx
0x14006327e  mov     rcx, cs:WPP_GLOBAL_Control
0x140063285  mov     [rsp+68h+var_48], r14
0x14006328a  mov     rcx, [rcx+40h]
0x14006328e  call    WPP_RECORDER_SF_qD
0x140063293  mov     ebx, 0C000000Dh
0x140063298  jmp     short loc_1400632A3
0x14006329a  lea     rax, [rcx+38h]
0x14006329e  mov     ebx, esi
0x1400632a0  mov     [rdx], rax
0x1400632a3  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400632aa  jz      short loc_1400632E6
0x1400632ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400632b3  mov     dl, 5
0x1400632b5  cmp     [rcx+29h], dl
0x1400632b8  jnb     short loc_1400632C0
0x1400632ba  cmp     [rcx+48h], si
0x1400632be  jz      short loc_1400632E6
0x1400632c0  mov     r8d, [rdi+20h]
0x1400632c4  mov     r9d, 3Ch ; '<'
0x1400632ca  mov     rcx, [rcx+40h]
0x1400632ce  mov     [rsp+68h+var_30], ebx
0x1400632d2  mov     [rsp+68h+var_38], r8d
0x1400632d7  mov     [rsp+68h+var_40], rdi
0x1400632dc  mov     [rsp+68h+var_48], r14
0x1400632e1  call    WPP_RECORDER_SF_qDD
0x1400632e6  mov     eax, ebx
0x1400632e8  add     rsp, 40h
0x1400632ec  pop     r14
0x1400632ee  pop     rdi
0x1400632ef  pop     rsi
0x1400632f0  pop     rbp
0x1400632f1  pop     rbx
0x1400632f2  retn
```
