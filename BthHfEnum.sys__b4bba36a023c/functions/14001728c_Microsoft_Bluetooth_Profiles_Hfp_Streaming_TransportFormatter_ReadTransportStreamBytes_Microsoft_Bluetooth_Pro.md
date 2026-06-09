# Microsoft::Bluetooth::Profiles::Hfp::Streaming::TransportFormatter::ReadTransportStreamBytes(Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteWriter *)

- ea: `0x14001728c`
- end: `0x140017307`
- name: `?ReadTransportStreamBytes@TransportFormatter@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@QEAAXPEAVByteWriter@23456@@Z`
- size: `123`
- prototype: `void __fastcall(Microsoft::Bluetooth::Profiles::Hfp::Streaming::TransportFormatter *__hidden this, struct Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteWriter *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14002de78`

## callees

- `0x140016a90`
- `0x140016df0`
- `0x140016e64`
- `0x14001728c`

## pseudocode

```c
void __fastcall Microsoft::Bluetooth::Profiles::Hfp::Streaming::TransportFormatter::ReadTransportStreamBytes(
        Microsoft::Bluetooth::Profiles::Hfp::Streaming::TransportFormatter *this,
        struct Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteWriter *a2)
{
  if ( *(_DWORD *)this == 1 )
  {
    Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer::ReadBytes(
      (Microsoft::Bluetooth::Profiles::Hfp::Streaming::TransportFormatter *)((char *)this + 48),
      a2);
    if ( *((_QWORD *)this + 8) == *((_QWORD *)this + 10) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_557c46c806da38115779eb8769b05e8d_Traceguids, this);
      }
      Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer::SetBuffer(
        (Microsoft::Bluetooth::Profiles::Hfp::Streaming::TransportFormatter *)((char *)this + 40),
        (char *)(*((_QWORD *)this + 1) + *((_QWORD *)this + 4)),
        *((_QWORD *)this + 2));
      *(_DWORD *)this = 0;
    }
  }
}

```

## disassembly

```asm
0x14001728c  push    rbx
0x14001728e  sub     rsp, 20h
0x140017292  cmp     dword ptr [rcx], 1
0x140017295  mov     rbx, rcx
0x140017298  jnz     short loc_140017300
0x14001729a  add     rcx, 30h ; '0'; this
0x14001729e  call    ?ReadBytes@ByteBuffer@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@UEAA_KPEAVByteWriter@23456@@Z; Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer::ReadBytes(Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteWriter *)
0x1400172a3  mov     rdx, [rbx+50h]
0x1400172a7  cmp     [rbx+40h], rdx
0x1400172ab  jnz     short loc_140017300
0x1400172ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400172b4  lea     rax, WPP_GLOBAL_Control
0x1400172bb  cmp     rcx, rax
0x1400172be  jz      short loc_1400172E5
0x1400172c0  mov     eax, [rcx+2Ch]
0x1400172c3  test    al, 40h
0x1400172c5  jz      short loc_1400172E5
0x1400172c7  cmp     byte ptr [rcx+29h], 5
0x1400172cb  jb      short loc_1400172E5
0x1400172cd  mov     rcx, [rcx+18h]
0x1400172d1  lea     r8, WPP_557c46c806da38115779eb8769b05e8d_Traceguids
0x1400172d8  mov     edx, 0Ch
0x1400172dd  mov     r9, rbx
0x1400172e0  call    WPP_SF_q
0x1400172e5  mov     rdx, [rbx+20h]
0x1400172e9  lea     rcx, [rbx+28h]; this
0x1400172ed  add     rdx, [rbx+8]; char *
0x1400172f1  mov     r8, [rbx+10h]; unsigned __int64
0x1400172f5  call    ?SetBuffer@ByteBuffer@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@QEAAXPEAD_K_N@Z; Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer::SetBuffer(char *,unsigned __int64,bool)
0x1400172fa  mov     dword ptr [rbx], 0
0x140017300  add     rsp, 20h
0x140017304  pop     rbx
0x140017305  retn
```
