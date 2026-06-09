# Microsoft::Bluetooth::Profiles::Hfp::Streaming::ScoReader::ContinueReading(void)

- ea: `0x14002f250`
- end: `0x14002f2eb`
- name: `?ContinueReading@ScoReader@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@QEAAXXZ`
- size: `155`
- prototype: `void __fastcall(Microsoft::Bluetooth::Profiles::Hfp::Streaming::ScoReader *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14002d320`
- `0x14002e1a0`

## callees

- `0x140016a90`
- `0x140017bd8`
- `0x14002f250`
- `0x14002f2f4`

## pseudocode

```c
void __fastcall Microsoft::Bluetooth::Profiles::Hfp::Streaming::ScoReader::ContinueReading(
        Microsoft::Bluetooth::Profiles::Hfp::Streaming::ScoReader *this)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_b61ba7c6c7ba3c52b18b4774502f69e2_Traceguids, this);
  }
  while ( (int)Microsoft::Bluetooth::Profiles::Hfp::Streaming::ScoReader::GetPendingRequestCounter(this) < 3
       && Microsoft::Bluetooth::Profiles::Hfp::Streaming::ScoReader::SendRequest(this) )
    ;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_b61ba7c6c7ba3c52b18b4774502f69e2_Traceguids, this);
  }
}

```

## disassembly

```asm
0x14002f250  mov     [rsp+arg_0], rbx
0x14002f255  push    rdi
0x14002f256  sub     rsp, 20h
0x14002f25a  mov     rbx, rcx
0x14002f25d  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f264  lea     rdi, WPP_GLOBAL_Control
0x14002f26b  cmp     rcx, rdi
0x14002f26e  jz      short loc_14002F295
0x14002f270  mov     eax, [rcx+2Ch]
0x14002f273  test    al, 10h
0x14002f275  jz      short loc_14002F295
0x14002f277  cmp     byte ptr [rcx+29h], 5
0x14002f27b  jb      short loc_14002F295
0x14002f27d  mov     rcx, [rcx+18h]
0x14002f281  lea     r8, WPP_b61ba7c6c7ba3c52b18b4774502f69e2_Traceguids
0x14002f288  mov     edx, 0Ah
0x14002f28d  mov     r9, rbx
0x14002f290  call    WPP_SF_q
0x14002f295  mov     rcx, rbx; this
0x14002f298  call    ?GetPendingRequestCounter@ScoReader@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@AEBAHXZ; Microsoft::Bluetooth::Profiles::Hfp::Streaming::ScoReader::GetPendingRequestCounter(void)
0x14002f29d  cmp     eax, 3
0x14002f2a0  jge     short loc_14002F2AE
0x14002f2a2  mov     rcx, rbx; this
0x14002f2a5  call    ?SendRequest@ScoReader@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@AEAA_NXZ; Microsoft::Bluetooth::Profiles::Hfp::Streaming::ScoReader::SendRequest(void)
0x14002f2aa  test    al, al
0x14002f2ac  jnz     short loc_14002F295
0x14002f2ae  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f2b5  cmp     rcx, rdi
0x14002f2b8  jz      short loc_14002F2DF
0x14002f2ba  mov     eax, [rcx+2Ch]
0x14002f2bd  test    al, 10h
0x14002f2bf  jz      short loc_14002F2DF
0x14002f2c1  cmp     byte ptr [rcx+29h], 5
0x14002f2c5  jb      short loc_14002F2DF
0x14002f2c7  mov     rcx, [rcx+18h]
0x14002f2cb  lea     r8, WPP_b61ba7c6c7ba3c52b18b4774502f69e2_Traceguids
0x14002f2d2  mov     edx, 0Bh
0x14002f2d7  mov     r9, rbx
0x14002f2da  call    WPP_SF_q
0x14002f2df  mov     rbx, [rsp+28h+arg_0]
0x14002f2e4  add     rsp, 20h
0x14002f2e8  pop     rdi
0x14002f2e9  retn
```
