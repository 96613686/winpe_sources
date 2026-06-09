# Microsoft::Bluetooth::Profiles::Hfp::Streaming::TransportFormatter::WriteFrameBytes(Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteReader *)

- ea: `0x1400177c8`
- end: `0x140017891`
- name: `?WriteFrameBytes@TransportFormatter@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@QEAAXPEAVByteReader@23456@@Z`
- size: `201`
- prototype: `void __fastcall(Microsoft::Bluetooth::Profiles::Hfp::Streaming::TransportFormatter *__hidden this, struct Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteReader *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14002de78`

## callees

- `0x140016a90`
- `0x140016e64`
- `0x140016ed0`
- `0x1400177c8`

## pseudocode

```c
void __fastcall Microsoft::Bluetooth::Profiles::Hfp::Streaming::TransportFormatter::WriteFrameBytes(
        Microsoft::Bluetooth::Profiles::Hfp::Streaming::TransportFormatter *this,
        struct Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteReader *a2)
{
  int v3; // eax
  __int64 v4; // rdx

  if ( !*(_DWORD *)this )
  {
    Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer::WriteBytes(
      (Microsoft::Bluetooth::Profiles::Hfp::Streaming::TransportFormatter *)((char *)this + 40),
      a2);
    if ( *((_QWORD *)this + 8) == *((_QWORD *)this + 9) )
    {
      v3 = *((_DWORD *)this + 1);
      if ( v3 )
      {
        if ( v3 == 1 )
        {
          v4 = *((_QWORD *)this + 4);
          *(_WORD *)v4 = 2049;
          *(_BYTE *)(v4 + 1) = (16 * *((_BYTE *)&qword_14001E438 + *((int *)this + 24))) | 8;
          *((_DWORD *)this + 24) = (*((_DWORD *)this + 24) + 1) % 4;
        }
      }
      else
      {
        ++*((_DWORD *)this + 24);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_557c46c806da38115779eb8769b05e8d_Traceguids, this);
      }
      Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer::SetBuffer(
        (Microsoft::Bluetooth::Profiles::Hfp::Streaming::TransportFormatter *)((char *)this + 40),
        *((char **)this + 4),
        *((_QWORD *)this + 3));
      *(_DWORD *)this = 1;
    }
  }
}

```

## disassembly

```asm
0x1400177c8  mov     [rsp+arg_0], rbx
0x1400177cd  push    rdi
0x1400177ce  sub     rsp, 20h
0x1400177d2  cmp     dword ptr [rcx], 0
0x1400177d5  mov     rbx, rcx
0x1400177d8  jnz     loc_140017885
0x1400177de  add     rcx, 28h ; '('; this
0x1400177e2  call    ?WriteBytes@ByteBuffer@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@UEAA_KPEAVByteReader@23456@@Z; Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer::WriteBytes(Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteReader *)
0x1400177e7  mov     rdx, [rbx+48h]
0x1400177eb  cmp     [rbx+40h], rdx
0x1400177ef  jnz     loc_140017885
0x1400177f5  mov     eax, [rbx+4]
0x1400177f8  test    eax, eax
0x1400177fa  jnz     short loc_140017801
0x1400177fc  inc     dword ptr [rbx+60h]
0x1400177ff  jmp     short loc_140017836
0x140017801  cmp     eax, 1
0x140017804  jnz     short loc_140017836
0x140017806  mov     rdx, [rbx+20h]
0x14001780a  lea     rcx, qword_14001E438
0x140017811  mov     word ptr [rdx], 801h
0x140017816  movsxd  rax, dword ptr [rbx+60h]
0x14001781a  mov     cl, [rax+rcx]
0x14001781d  shl     cl, 4
0x140017820  or      cl, 8
0x140017823  mov     [rdx+1], cl
0x140017826  mov     ecx, 4
0x14001782b  mov     eax, [rbx+60h]
0x14001782e  inc     eax
0x140017830  cdq
0x140017831  idiv    ecx
0x140017833  mov     [rbx+60h], edx
0x140017836  mov     rcx, cs:WPP_GLOBAL_Control
0x14001783d  lea     rax, WPP_GLOBAL_Control
0x140017844  cmp     rcx, rax
0x140017847  jz      short loc_14001786E
0x140017849  mov     eax, [rcx+2Ch]
0x14001784c  test    al, 40h
0x14001784e  jz      short loc_14001786E
0x140017850  cmp     byte ptr [rcx+29h], 5
0x140017854  jb      short loc_14001786E
0x140017856  mov     rcx, [rcx+18h]
0x14001785a  lea     r8, WPP_557c46c806da38115779eb8769b05e8d_Traceguids
0x140017861  mov     edx, 0Bh
0x140017866  mov     r9, rbx
0x140017869  call    WPP_SF_q
0x14001786e  mov     r8, [rbx+18h]; unsigned __int64
0x140017872  lea     rcx, [rbx+28h]; this
0x140017876  mov     rdx, [rbx+20h]; char *
0x14001787a  call    ?SetBuffer@ByteBuffer@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@QEAAXPEAD_K_N@Z; Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteBuffer::SetBuffer(char *,unsigned __int64,bool)
0x14001787f  mov     dword ptr [rbx], 1
0x140017885  mov     rbx, [rsp+28h+arg_0]
0x14001788a  add     rsp, 20h
0x14001788e  pop     rdi
0x14001788f  retn
```
