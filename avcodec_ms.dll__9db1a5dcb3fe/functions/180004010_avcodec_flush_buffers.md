# avcodec_flush_buffers

- ea: `0x180004010`
- end: `0x1800040cd`
- name: `avcodec_flush_buffers`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180010a18`

## callees

- `0x180004010`
- `0x180007a84`
- `0x18000a5f8`
- `0x18000f940`
- `0x180010a18`
- `0x180012050`
- `0x18002269e`
- `0x18002276a`
- `0x180024140`

## string_xrefs

- `0x18000403e`: `Ignoring attempt to flush encoder that doesn't support it\n`

## pseudocode

```c
__int64 (__fastcall *__fastcall avcodec_flush_buffers(__int64 a1))(__int64)
{
  __int64 v1; // rdi
  __int64 (__fastcall *result)(__int64); // rax
  __int64 v4; // rcx
  __int64 v5; // rcx

  v1 = *(_QWORD *)(a1 + 40);
  if ( (unsigned int)av_codec_is_encoder(*(_QWORD *)(a1 + 16)) )
  {
    if ( (*(_DWORD *)(*(_QWORD *)(a1 + 16) + 24LL) & 0x200000) == 0 )
      return (__int64 (__fastcall *)(__int64))av_log(
                                                a1,
                                                24,
                                                "Ignoring attempt to flush encoder that doesn't support it\n");
    sub_18000A5F8(a1);
  }
  else
  {
    sub_180007A84(a1);
  }
  v4 = *(_QWORD *)(v1 + 136);
  *(_DWORD *)(v1 + 120) = 0;
  *(_DWORD *)(v1 + 144) = 0;
  if ( v4 )
    av_frame_unref(v4);
  v5 = *(_QWORD *)(v1 + 128);
  if ( v5 )
    av_packet_unref(v5);
  if ( (*(_BYTE *)(a1 + 664) & 1) != 0 && !*(_DWORD *)(v1 + 4) )
    return (__int64 (__fastcall *)(__int64))sub_180010A18(a1);
  result = *(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 16) + 152LL);
  if ( result )
    return (__int64 (__fastcall *)(__int64))result(a1);
  return result;
}

```

## disassembly

```asm
0x180004010  mov     [rsp+arg_0], rbx
0x180004015  push    rdi
0x180004016  sub     rsp, 20h
0x18000401a  mov     rdi, [rcx+28h]
0x18000401e  mov     rbx, rcx
0x180004021  mov     rcx, [rcx+10h]
0x180004025  call    av_codec_is_encoder
0x18000402a  mov     rcx, rbx
0x18000402d  test    eax, eax
0x18000402f  jz      short loc_180004058
0x180004031  mov     rax, [rbx+10h]
0x180004035  test    dword ptr [rax+18h], 200000h
0x18000403c  jnz     short loc_180004051
0x18000403e  lea     r8, aIgnoringAttemp; "Ignoring attempt to flush encoder that "...
0x180004045  mov     edx, 18h
0x18000404a  call    av_log
0x18000404f  jmp     short loc_1800040C2
0x180004051  call    sub_18000A5F8
0x180004056  jmp     short loc_18000405D
0x180004058  call    sub_180007A84
0x18000405d  mov     rcx, [rdi+88h]
0x180004064  mov     dword ptr [rdi+78h], 0
0x18000406b  mov     dword ptr [rdi+90h], 0
0x180004075  test    rcx, rcx
0x180004078  jz      short loc_18000407F
0x18000407a  call    av_frame_unref
0x18000407f  mov     rcx, [rdi+80h]
0x180004086  test    rcx, rcx
0x180004089  jz      short loc_180004090
0x18000408b  call    av_packet_unref
0x180004090  test    byte ptr [rbx+298h], 1
0x180004097  jz      short loc_1800040A9
0x180004099  cmp     dword ptr [rdi+4], 0
0x18000409d  jnz     short loc_1800040A9
0x18000409f  mov     rcx, rbx
0x1800040a2  call    sub_180010A18
0x1800040a7  jmp     short loc_1800040C2
0x1800040a9  mov     rax, [rbx+10h]
0x1800040ad  mov     rax, [rax+98h]
0x1800040b4  test    rax, rax
0x1800040b7  jz      short loc_1800040C2
0x1800040b9  mov     rcx, rbx
0x1800040bc  call    cs:__guard_dispatch_icall_fptr
0x1800040c2  mov     rbx, [rsp+28h+arg_0]
0x1800040c7  add     rsp, 20h
0x1800040cb  pop     rdi
0x1800040cc  retn
```
