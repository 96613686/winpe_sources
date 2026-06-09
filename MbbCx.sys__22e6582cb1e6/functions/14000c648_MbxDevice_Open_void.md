# MbxDevice::Open(void)

- ea: `0x14000c648`
- end: `0x14000c6c2`
- name: `?Open@MbxDevice@@QEAAJXZ`
- size: `122`
- prototype: `__int64 __fastcall(MbxDevice *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000b670`
- `0x14000c37c`

## callees

- `0x140009104`
- `0x14000c648`
- `0x1400174d8`

## pseudocode

```c
__int64 __fastcall MbxDevice::Open(KSPIN_LOCK *this)
{
  int v2; // edx
  int v3; // edi

  v3 = MbbOpen(this + 8);
  if ( v3 >= 0 )
  {
    *((_BYTE *)this + 1552) = 1;
    return 0;
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v2) = 2;
      WPP_RECORDER_SF_qd(
        WPP_GLOBAL_Control->DeviceExtension,
        v2,
        11,
        67,
        (__int64)WPP_87eee639879b3392f87380bbab0baecf_Traceguids,
        this[1],
        v3);
    }
    return (unsigned int)v3;
  }
}

```

## disassembly

```asm
0x14000c648  mov     [rsp+arg_0], rbx
0x14000c64d  push    rdi
0x14000c64e  sub     rsp, 40h
0x14000c652  mov     rbx, rcx
0x14000c655  add     rcx, 40h ; '@'; SpinLock
0x14000c659  call    ?MbbOpen@@YAJPEAU_MINIPORT_ADAPTER_CONTEXT@@@Z; MbbOpen(_MINIPORT_ADAPTER_CONTEXT *)
0x14000c65e  mov     edi, eax
0x14000c660  test    eax, eax
0x14000c662  jns     short loc_14000C6AD
0x14000c664  lea     rax, WPP_RECORDER_INITIALIZED
0x14000c66b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000c672  jz      short loc_14000C6A9
0x14000c674  mov     rcx, [rbx+8]
0x14000c678  lea     rax, WPP_87eee639879b3392f87380bbab0baecf_Traceguids
0x14000c67f  mov     [rsp+48h+var_18], edi
0x14000c683  mov     r9d, 43h ; 'C'
0x14000c689  mov     [rsp+48h+var_20], rcx
0x14000c68e  mov     dl, 2
0x14000c690  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c697  mov     [rsp+48h+var_28], rax
0x14000c69c  lea     r8d, [r9-38h]
0x14000c6a0  mov     rcx, [rcx+40h]
0x14000c6a4  call    WPP_RECORDER_SF_qd
0x14000c6a9  mov     eax, edi
0x14000c6ab  jmp     short loc_14000C6B6
0x14000c6ad  mov     byte ptr [rbx+610h], 1
0x14000c6b4  xor     eax, eax
0x14000c6b6  mov     rbx, [rsp+48h+arg_0]
0x14000c6bb  add     rsp, 40h
0x14000c6bf  pop     rdi
0x14000c6c0  retn
```
