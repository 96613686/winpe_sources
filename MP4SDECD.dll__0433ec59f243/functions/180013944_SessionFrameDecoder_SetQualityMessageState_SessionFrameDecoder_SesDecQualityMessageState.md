# SessionFrameDecoder::SetQualityMessageState(SessionFrameDecoder::SesDecQualityMessageState)

- ea: `0x180013944`
- end: `0x1800139e0`
- name: `?SetQualityMessageState@SessionFrameDecoder@@QEAAJW4SesDecQualityMessageState@1@@Z`
- size: `156`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180013cf8`
- `0x180013e14`
- `0x1800149ac`
- `0x18002db80`
- `0x18002e040`

## callees

- `0x180012a08`
- `0x180013944`
- `0x18002aac0`

## pseudocode

```c
__int64 __fastcall SessionFrameDecoder::SetQualityMessageState(__int64 a1, int a2)
{
  __int64 v3; // r8
  int v4; // ecx
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+20h] [rbp-28h] BYREF
  int v7; // [rsp+58h] [rbp+10h] BYREF

  v7 = a2;
  if ( g_petwPro )
  {
    *(_QWORD *)&v6.Size = 4;
    v6.Ptr = (ULONGLONG)&v7;
    ETWWrite(a1, (const EVENT_DESCRIPTOR *)MP4SDECD_QM_DropMode_Info, 1u, &v6);
    a2 = v7;
  }
  v3 = *(_QWORD *)(a1 + 16);
  if ( !v3 )
    return 0xFFFFFFFFLL;
  v4 = 0;
  if ( a2 >= 0 )
    v4 = a2;
  if ( v4 >= 6 )
    v4 = 5;
  *(_DWORD *)(v3 + 6536) = v4;
  *(_DWORD *)(v3 + 6552) = v4 == 0;
  return 0;
}

```

## disassembly

```asm
0x180013944  mov     [rsp+arg_8], edx
0x180013948  mov     r11, rsp
0x18001394b  push    rbx
0x18001394c  sub     rsp, 40h
0x180013950  mov     rax, cs:__security_cookie
0x180013957  xor     rax, rsp
0x18001395a  mov     [rsp+48h+var_18], rax
0x18001395f  cmp     cs:g_petwPro, 0
0x180013967  mov     rbx, rcx
0x18001396a  jz      short loc_180013996
0x18001396c  lea     rax, [r11+10h]
0x180013970  mov     qword ptr [r11-20h], 4
0x180013978  lea     r9, [r11-28h]
0x18001397c  mov     [r11-28h], rax
0x180013980  mov     r8d, 1
0x180013986  lea     rdx, MP4SDECD_QM_DropMode_Info
0x18001398d  call    ETWWrite
0x180013992  mov     edx, [rsp+48h+arg_8]
0x180013996  mov     r8, [rbx+10h]
0x18001399a  test    r8, r8
0x18001399d  jz      short loc_1800139DB
0x18001399f  xor     ecx, ecx
0x1800139a1  mov     eax, 5
0x1800139a6  test    edx, edx
0x1800139a8  cmovns  ecx, edx
0x1800139ab  cmp     ecx, 6
0x1800139ae  cmovge  ecx, eax
0x1800139b1  xor     eax, eax
0x1800139b3  test    ecx, ecx
0x1800139b5  mov     [r8+1988h], ecx
0x1800139bc  setz    al
0x1800139bf  mov     [r8+1998h], eax
0x1800139c6  xor     eax, eax
0x1800139c8  mov     rcx, [rsp+48h+var_18]
0x1800139cd  xor     rcx, rsp; StackCookie
0x1800139d0  call    __security_check_cookie
0x1800139d5  add     rsp, 40h
0x1800139d9  pop     rbx
0x1800139da  retn
0x1800139db  or      eax, 0FFFFFFFFh
0x1800139de  jmp     short loc_1800139C8
```
