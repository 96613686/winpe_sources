# CsQueue::RemoveIrp(void)

- ea: `0x14005b8a0`
- end: `0x14005b94b`
- name: `?RemoveIrp@CsQueue@@UEAAPEAU_IRP@@XZ`
- size: `171`
- prototype: `struct _IRP *__fastcall(CsQueue *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140089620`

## callees

- `0x140003530`
- `0x14002d890`
- `0x14005b8a0`

## import_xrefs

- `ntoskrnl!IoCsqRemoveNextIrp` at `0x14005b938`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x14005b938`

## pseudocode

```c
PIRP __fastcall CsQueue::RemoveIrp(CsQueue *this, __int64 a2, __int64 a3, __int64 a4)
{
  int v5; // edx
  int v6; // r8d

  if ( !(unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(this, a2, a3, a4) )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || (LOBYTE(v5) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    {
      LOBYTE(v5) = 0;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
      || (LOBYTE(v6) = 1, !LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(v6) = 0;
    }
    if ( (_BYTE)v5 || (_BYTE)v6 )
      WPP_RECORDER_AND_TRACE_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        v5,
        v6,
        WPP_GLOBAL_Control->DeviceExtension,
        5,
        1,
        14,
        (__int64)WPP_6372fbb7e78435cbabebbbab2162309b_Traceguids,
        (char)this);
  }
  return IoCsqRemoveNextIrp((PIO_CSQ)((char *)this + 40), 0);
}

```

## disassembly

```asm
0x14005b8a0  push    rbx
0x14005b8a2  sub     rsp, 50h
0x14005b8a6  mov     rbx, rcx
0x14005b8a9  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x14005b8ae  xor     r9d, r9d
0x14005b8b1  test    eax, eax
0x14005b8b3  jnz     short loc_14005B932
0x14005b8b5  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b8bc  lea     rax, WPP_GLOBAL_Control
0x14005b8c3  cmp     rcx, rax
0x14005b8c6  jz      short loc_14005B8D7
0x14005b8c8  mov     eax, [rcx+2Ch]
0x14005b8cb  test    al, 1
0x14005b8cd  jz      short loc_14005B8D7
0x14005b8cf  cmp     byte ptr [rcx+29h], 5
0x14005b8d3  mov     dl, 1
0x14005b8d5  jnb     short loc_14005B8DA
0x14005b8d7  mov     dl, r9b
0x14005b8da  lea     rax, WPP_RECORDER_INITIALIZED
0x14005b8e1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14005b8e8  jz      short loc_14005B8F4
0x14005b8ea  mov     r8b, 1
0x14005b8ed  cmp     [rcx+48h], r9w
0x14005b8f2  jnz     short loc_14005B8F7
0x14005b8f4  mov     r8b, r9b
0x14005b8f7  test    dl, dl
0x14005b8f9  jnz     short loc_14005B900
0x14005b8fb  test    r8b, r8b
0x14005b8fe  jz      short loc_14005B932
0x14005b900  mov     r9, [rcx+40h]
0x14005b904  lea     rax, WPP_6372fbb7e78435cbabebbbab2162309b_Traceguids
0x14005b90b  mov     rcx, [rcx+18h]
0x14005b90f  mov     [rsp+58h+var_18], rbx
0x14005b914  mov     [rsp+58h+var_20], rax
0x14005b919  mov     [rsp+58h+var_28], 0Eh
0x14005b920  mov     [rsp+58h+var_30], 1
0x14005b928  mov     [rsp+58h+var_38], 5
0x14005b92d  call    WPP_RECORDER_AND_TRACE_SF_q
0x14005b932  lea     rcx, [rbx+28h]; Csq
0x14005b936  xor     edx, edx; PeekContext
0x14005b938  call    cs:__imp_IoCsqRemoveNextIrp
0x14005b93f  nop     dword ptr [rax+rax+00h]
0x14005b944  add     rsp, 50h
0x14005b948  pop     rbx
0x14005b949  retn
```
