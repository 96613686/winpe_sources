# Avdtp_impl::ReleaseRemoveLock(void)

- ea: `0x14000f7e0`
- end: `0x14000f896`
- name: `?ReleaseRemoveLock@Avdtp_impl@@QEAAXXZ`
- size: `182`
- prototype: `void __fastcall(Avdtp_impl *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400132a0`
- `0x140019718`
- `0x140019c50`
- `0x1400473d0`

## callees

- `0x140006a88`
- `0x14000f7e0`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000f800`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000f800`

## pseudocode

```c
void __fastcall Avdtp_impl::ReleaseRemoveLock(Avdtp_impl *this)
{
  struct _IO_REMOVE_LOCK *v2; // rcx
  int v3; // edx
  int v4; // r8d

  v2 = (struct _IO_REMOVE_LOCK *)*((_QWORD *)this + 224);
  if ( v2 )
  {
    IoReleaseRemoveLockEx(v2, (PVOID)0x41564454, 0x20u);
    LOBYTE(v3) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v4) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_Dq(
        WPP_GLOBAL_Control->AttachedDevice,
        v3,
        v4,
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        4,
        19,
        (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids,
        *(_DWORD *)(*((_QWORD *)this + 224) + 4LL),
        this);
    }
  }
}

```

## disassembly

```asm
0x14000f7e0  push    rbx
0x14000f7e2  sub     rsp, 50h
0x14000f7e6  mov     rbx, rcx
0x14000f7e9  mov     rcx, [rcx+700h]; RemoveLock
0x14000f7f0  test    rcx, rcx
0x14000f7f3  jz      short loc_14000F83C
0x14000f7f5  mov     edx, 41564454h; Tag
0x14000f7fa  mov     r8d, 20h ; ' '; RemlockSize
0x14000f800  call    cs:__imp_IoReleaseRemoveLockEx
0x14000f807  nop     dword ptr [rax+rax+00h]
0x14000f80c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f813  lea     rax, WPP_GLOBAL_Control
0x14000f81a  cmp     rcx, rax
0x14000f81d  jnz     short loc_14000F843
0x14000f81f  xor     dl, dl
0x14000f821  lea     rax, WPP_RECORDER_INITIALIZED
0x14000f828  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000f82f  setnz   r8b
0x14000f833  test    dl, dl
0x14000f835  jnz     short loc_14000F854
0x14000f837  test    r8b, r8b
0x14000f83a  jnz     short loc_14000F854
0x14000f83c  add     rsp, 50h
0x14000f840  pop     rbx
0x14000f841  retn
0x14000f843  mov     eax, [rcx+2Ch]
0x14000f846  test    al, 8
0x14000f848  jz      short loc_14000F81F
0x14000f84a  cmp     byte ptr [rcx+29h], 4
0x14000f84e  jb      short loc_14000F81F
0x14000f850  mov     dl, 1
0x14000f852  jmp     short loc_14000F821
0x14000f854  mov     rax, [rbx+700h]
0x14000f85b  mov     r9, [rcx+40h]
0x14000f85f  mov     rcx, [rcx+18h]
0x14000f863  mov     [rsp+58h+var_10], rbx
0x14000f868  mov     eax, [rax+4]
0x14000f86b  mov     [rsp+58h+var_18], eax
0x14000f86f  lea     rax, WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids
0x14000f876  mov     [rsp+58h+var_20], rax
0x14000f87b  mov     [rsp+58h+var_28], 13h
0x14000f882  mov     [rsp+58h+var_30], 4
0x14000f88a  mov     [rsp+58h+var_38], 4
0x14000f88f  call    WPP_RECORDER_AND_TRACE_SF_Dq
0x14000f894  jmp     short loc_14000F83C
```
