# SessionFrameDecoder::SetPostProcessingState(SessionFrameDecoder::SesDecPostProcessingState)

- ea: `0x18001385c`
- end: `0x1800138d4`
- name: `?SetPostProcessingState@SessionFrameDecoder@@QEAAJW4SesDecPostProcessingState@1@@Z`
- size: `120`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x180013cf8`
- `0x180013e14`
- `0x1800149ac`
- `0x18002dec0`
- `0x18002e040`

## callees

- `0x180012a08`
- `0x18001385c`
- `0x1800138dc`
- `0x18002aac0`

## pseudocode

```c
__int64 __fastcall SessionFrameDecoder::SetPostProcessingState(__int64 a1, int a2)
{
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+20h] [rbp-28h] BYREF
  int v5; // [rsp+58h] [rbp+10h] BYREF

  v5 = a2;
  if ( g_petwPro )
  {
    *(_QWORD *)&v4.Size = 4;
    v4.Ptr = (ULONGLONG)&v5;
    ETWWrite(a1, (const EVENT_DESCRIPTOR *)MP4SDECD_QM_PostProcessing_Info, 1u, &v4);
  }
  if ( *(_QWORD *)(a1 + 16) )
    return CVideoObjectDecoder::SetPostProcessingState();
  else
    return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x18001385c  mov     [rsp+arg_8], edx
0x180013860  mov     r11, rsp
0x180013863  push    rbx
0x180013864  sub     rsp, 40h
0x180013868  mov     rax, cs:__security_cookie
0x18001386f  xor     rax, rsp
0x180013872  mov     [rsp+48h+var_18], rax
0x180013877  cmp     cs:g_petwPro, 0
0x18001387f  mov     rbx, rcx
0x180013882  jz      short loc_1800138AE
0x180013884  lea     rax, [r11+10h]
0x180013888  mov     qword ptr [r11-20h], 4
0x180013890  lea     r9, [r11-28h]
0x180013894  mov     [r11-28h], rax
0x180013898  mov     r8d, 1
0x18001389e  lea     rdx, MP4SDECD_QM_PostProcessing_Info
0x1800138a5  call    ETWWrite
0x1800138aa  mov     edx, [rsp+48h+arg_8]
0x1800138ae  mov     rcx, [rbx+10h]
0x1800138b2  test    rcx, rcx
0x1800138b5  jz      short loc_1800138CF
0x1800138b7  call    ?SetPostProcessingState@CVideoObjectDecoder@@QEAAJW4PostProcessingState@1@@Z; CVideoObjectDecoder::SetPostProcessingState(CVideoObjectDecoder::PostProcessingState)
0x1800138bc  mov     rcx, [rsp+48h+var_18]
0x1800138c1  xor     rcx, rsp; StackCookie
0x1800138c4  call    __security_check_cookie
0x1800138c9  add     rsp, 40h
0x1800138cd  pop     rbx
0x1800138ce  retn
0x1800138cf  or      eax, 0FFFFFFFFh
0x1800138d2  jmp     short loc_1800138BC
```
