# Microsoft::Bluetooth::Profiles::Hfp::Streaming::TransportParser::ReadFrameBytes(Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteWriter *)

- ea: `0x140017208`
- end: `0x140017285`
- name: `?ReadFrameBytes@TransportParser@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@QEAAXPEAVByteWriter@23456@@Z`
- size: `125`
- prototype: `void __fastcall(Microsoft::Bluetooth::Profiles::Hfp::Streaming::TransportParser *__hidden this, struct Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteWriter *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14002db70`

## callees

- `0x140016a90`
- `0x140016df0`
- `0x140016e64`
- `0x140017208`

## pseudocode

```c
void __fastcall Microsoft::Bluetooth::Profiles::Hfp::Streaming::TransportParser::ReadFrameBytes(
        Microsoft::Bluetooth::Profiles::Hfp::Streaming::TransportParser *this,
        struct Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteWriter *a2)
{
  char *v3; // rdx
  __int64 v4; // r8

  if ( *((_DWORD *)this + 10) == 2 )
  {
    Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer::ReadBytes(
      (Microsoft::Bluetooth::Profiles::Hfp::Streaming::TransportParser *)((char *)this + 56),
      a2);
    if ( *((_QWORD *)this + 9) == *((_QWORD *)this + 11) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_557c46c806da38115779eb8769b05e8d_Traceguids, this);
      }
      v3 = (char *)*((_QWORD *)this + 4);
      v4 = *((_QWORD *)this + 3);
      *((_QWORD *)this + 13) = v3;
      Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer::SetBuffer(
        (Microsoft::Bluetooth::Profiles::Hfp::Streaming::TransportParser *)((char *)this + 48),
        v3,
        v4);
      *((_DWORD *)this + 10) = 0;
    }
  }
}

```

## disassembly

```asm
0x140017208  push    rbx
0x14001720a  sub     rsp, 20h
0x14001720e  cmp     dword ptr [rcx+28h], 2
0x140017212  mov     rbx, rcx
0x140017215  jnz     short loc_14001727E
0x140017217  add     rcx, 38h ; '8'; this
0x14001721b  call    ?ReadBytes@ByteBuffer@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@UEAA_KPEAVByteWriter@23456@@Z; Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer::ReadBytes(Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteWriter *)
0x140017220  mov     rdx, [rbx+58h]
0x140017224  cmp     [rbx+48h], rdx
0x140017228  jnz     short loc_14001727E
0x14001722a  mov     rcx, cs:WPP_GLOBAL_Control
0x140017231  lea     rax, WPP_GLOBAL_Control
0x140017238  cmp     rcx, rax
0x14001723b  jz      short loc_140017262
0x14001723d  mov     eax, [rcx+2Ch]
0x140017240  test    al, 40h
0x140017242  jz      short loc_140017262
0x140017244  cmp     byte ptr [rcx+29h], 5
0x140017248  jb      short loc_140017262
0x14001724a  mov     rcx, [rcx+18h]
0x14001724e  lea     r8, WPP_557c46c806da38115779eb8769b05e8d_Traceguids
0x140017255  mov     edx, 12h
0x14001725a  mov     r9, rbx
0x14001725d  call    WPP_SF_q
0x140017262  mov     rdx, [rbx+20h]; char *
0x140017266  lea     rcx, [rbx+30h]; this
0x14001726a  mov     r8, [rbx+18h]; unsigned __int64
0x14001726e  mov     [rbx+68h], rdx
0x140017272  call    ?SetBuffer@ByteBuffer@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@QEAAXPEAD_K_N@Z; Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer::SetBuffer(char *,unsigned __int64,bool)
0x140017277  mov     dword ptr [rbx+28h], 0
0x14001727e  add     rsp, 20h
0x140017282  pop     rbx
0x140017283  retn
```
