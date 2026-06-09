# Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioOutputQueue::IsReadyToProcessNextRequest(void)

- ea: `0x14002d400`
- end: `0x14002d46c`
- name: `?IsReadyToProcessNextRequest@AudioOutputQueue@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@UEBA_NXZ`
- size: `108`
- prototype: `bool __fastcall(Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioOutputQueue *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400161f8`
- `0x140016ba8`
- `0x14002d400`

## pseudocode

```c
bool __fastcall Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioOutputQueue::IsReadyToProcessNextRequest(
        Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioOutputQueue *this)
{
  int NumSentScoRequests; // eax
  __int64 v3; // r8
  __int64 v4; // r9
  bool v5; // bl

  NumSentScoRequests = Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioOutputQueue::GetNumSentScoRequests(this);
  v4 = *((_QWORD *)this + 3);
  v5 = !v4 && NumSentScoRequests < 2;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qdq(WPP_GLOBAL_Control->AttachedDevice, 20, v3, v4, NumSentScoRequests, this);
  }
  return v5;
}

```

## disassembly

```asm
0x14002d400  mov     [rsp+arg_0], rbx
0x14002d405  push    rdi
0x14002d406  sub     rsp, 30h
0x14002d40a  mov     rdi, rcx
0x14002d40d  call    ?GetNumSentScoRequests@AudioOutputQueue@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@AEBAHXZ; Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioOutputQueue::GetNumSentScoRequests(void)
0x14002d412  mov     r9, [rdi+18h]
0x14002d416  test    r9, r9
0x14002d419  jnz     short loc_14002D424
0x14002d41b  cmp     eax, 2
0x14002d41e  jge     short loc_14002D424
0x14002d420  mov     bl, 1
0x14002d422  jmp     short loc_14002D426
0x14002d424  xor     bl, bl
0x14002d426  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d42d  lea     rdx, WPP_GLOBAL_Control
0x14002d434  cmp     rcx, rdx
0x14002d437  jz      short loc_14002D45E
0x14002d439  mov     edx, [rcx+2Ch]
0x14002d43c  test    dl, 20h
0x14002d43f  jz      short loc_14002D45E
0x14002d441  cmp     byte ptr [rcx+29h], 5
0x14002d445  jb      short loc_14002D45E
0x14002d447  mov     rcx, [rcx+18h]
0x14002d44b  mov     edx, 14h
0x14002d450  mov     [rsp+38h+var_10], rdi
0x14002d455  mov     [rsp+38h+var_18], eax
0x14002d459  call    WPP_SF_qdq
0x14002d45e  mov     al, bl
0x14002d460  mov     rbx, [rsp+38h+arg_0]
0x14002d465  add     rsp, 30h
0x14002d469  pop     rdi
0x14002d46a  retn
```
