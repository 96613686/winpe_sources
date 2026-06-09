# MbxDevice::ReportFirstIndication(_MBB_COMMAND &)

- ea: `0x14000d3d0`
- end: `0x14000d495`
- name: `?ReportFirstIndication@MbxDevice@@QEAAXAEAU_MBB_COMMAND@@@Z`
- size: `197`
- prototype: `void(MbxDevice *__hidden this, struct _MBB_COMMAND *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400130b8`

## callees

- `0x140001cf8`
- `0x14000d3d0`
- `0x14000dab8`
- `0x14003e100`

## pseudocode

```c
void __fastcall MbxDevice::ReportFirstIndication(MbxDevice *this, struct _MBB_COMMAND *a2)
{
  struct _MBB_COMMAND *v2; // rdi
  int v4; // ebx
  char (near **CommandString)[32]; // rax
  int v6; // edx

  v2 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = 5;
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType)
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        8,
        136,
        (__int64)WPP_87eee639879b3392f87380bbab0baecf_Traceguids);
    }
  }
  if ( *((_BYTE *)this + 1558) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v4 = *((_DWORD *)v2 + 4);
      CommandString = MbbUtilGetCommandString(v2);
      WPP_RECORDER_SF__guid_sd(
        WPP_GLOBAL_Control->DeviceExtension,
        v6,
        8,
        137,
        (__int64)WPP_87eee639879b3392f87380bbab0baecf_Traceguids,
        (__int64)v2,
        (__int64)CommandString,
        v4);
    }
    *(_OWORD *)((char *)this + 1559) = *(_OWORD *)v2;
    *(_DWORD *)((char *)this + 1575) = *((_DWORD *)v2 + 4);
  }
}

```

## disassembly

```asm
0x14000d3d0  push    rbx
0x14000d3d2  push    rsi
0x14000d3d3  push    rdi
0x14000d3d4  push    r14
0x14000d3d6  sub     rsp, 48h
0x14000d3da  mov     rdi, rdx
0x14000d3dd  mov     rsi, rcx
0x14000d3e0  lea     rbx, WPP_RECORDER_INITIALIZED
0x14000d3e7  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14000d3ee  lea     r14, WPP_87eee639879b3392f87380bbab0baecf_Traceguids
0x14000d3f5  jz      short loc_14000D42B
0x14000d3f7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d3fe  mov     dl, 5
0x14000d400  cmp     word ptr [rcx+48h], 0
0x14000d405  jnz     short loc_14000D413
0x14000d407  mov     eax, [rcx+2Ch]
0x14000d40a  test    al, al
0x14000d40c  jns     short loc_14000D42B
0x14000d40e  cmp     [rcx+29h], dl
0x14000d411  jb      short loc_14000D42B
0x14000d413  mov     rcx, [rcx+40h]
0x14000d417  mov     r9d, 88h
0x14000d41d  mov     [rsp+68h+var_48], r14
0x14000d422  lea     r8d, [r9-80h]
0x14000d426  call    WPP_RECORDER_SF_
0x14000d42b  cmp     byte ptr [rsi+616h], 0
0x14000d432  jz      short loc_14000D48A
0x14000d434  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14000d43b  jz      short loc_14000D477
0x14000d43d  mov     ebx, [rdi+10h]
0x14000d440  mov     rcx, rdi; Source1
0x14000d443  call    ?MbbUtilGetCommandString@@YAPEADPEAU_MBB_COMMAND@@@Z; MbbUtilGetCommandString(_MBB_COMMAND *)
0x14000d448  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d44f  mov     r9d, 89h
0x14000d455  mov     [rsp+68h+var_30], ebx
0x14000d459  mov     r8d, 8
0x14000d45f  mov     [rsp+68h+var_38], rax
0x14000d464  mov     [rsp+68h+var_40], rdi
0x14000d469  mov     rcx, [rcx+40h]
0x14000d46d  mov     [rsp+68h+var_48], r14
0x14000d472  call    WPP_RECORDER_SF__guid_sd
0x14000d477  movups  xmm0, xmmword ptr [rdi]
0x14000d47a  movups  xmmword ptr [rsi+617h], xmm0
0x14000d481  mov     eax, [rdi+10h]
0x14000d484  mov     [rsi+627h], eax
0x14000d48a  add     rsp, 48h
0x14000d48e  pop     r14
0x14000d490  pop     rdi
0x14000d491  pop     rsi
0x14000d492  pop     rbx
0x14000d493  retn
```
