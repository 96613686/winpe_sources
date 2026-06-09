# Apx::ApfIpcIoLink::ApfLogReplyCmd(APF_MESSAGE_REPLY_COMMAND *)

- ea: `0x180027800`
- end: `0x1800278d0`
- name: `?ApfLogReplyCmd@ApfIpcIoLink@Apx@@AEAAXPEAUAPF_MESSAGE_REPLY_COMMAND@@@Z`
- size: `208`
- prototype: `void __fastcall(Apx::ApfIpcIoLink *__hidden this, struct APF_MESSAGE_REPLY_COMMAND *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180027990`

## callees

- `0x180027800`
- `0x1800292ec`
- `0x180029370`

## pseudocode

```c
void __fastcall Apx::ApfIpcIoLink::ApfLogReplyCmd(Apx::ApfIpcIoLink *this, struct APF_MESSAGE_REPLY_COMMAND *a2)
{
  if ( (*((_BYTE *)a2 + 4) & 0x10) != 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_iqiidDd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        *((unsigned __int16 *)a2 + 13),
        *((unsigned __int16 *)a2 + 12),
        *((_QWORD *)this + 8),
        a2,
        *((_QWORD *)a2 + 2),
        *((_QWORD *)a2 + 6),
        *((unsigned __int16 *)a2 + 12),
        *((unsigned __int16 *)a2 + 13),
        *((_DWORD *)a2 + 14));
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && *((char *)WPP_GLOBAL_Control + 28) < 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_iqidD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      72,
      *((unsigned __int16 *)a2 + 12),
      *((_QWORD *)this + 8),
      a2,
      *((_QWORD *)a2 + 2),
      *((unsigned __int16 *)a2 + 12),
      *((unsigned __int16 *)a2 + 13));
  }
}

```

## disassembly

```asm
0x180027800  mov     r11, rsp
0x180027803  sub     rsp, 58h
0x180027807  test    byte ptr [rdx+4], 10h
0x18002780b  mov     r9, rdx
0x18002780e  mov     r10, rcx
0x180027811  jz      short loc_18002787A
0x180027813  mov     rcx, cs:WPP_GLOBAL_Control
0x18002781a  lea     rax, WPP_GLOBAL_Control
0x180027821  cmp     rcx, rax
0x180027824  jz      loc_1800278CB
0x18002782a  test    byte ptr [rcx+1Ch], 80h
0x18002782e  jz      loc_1800278CB
0x180027834  cmp     byte ptr [rcx+19h], 5
0x180027838  jb      loc_1800278CB
0x18002783e  mov     eax, [r9+38h]
0x180027842  movzx   r8d, word ptr [r9+18h]
0x180027847  movzx   edx, word ptr [rdx+1Ah]
0x18002784b  mov     rcx, [rcx+10h]
0x18002784f  mov     [rsp+58h+var_10], eax
0x180027853  mov     rax, [r9+30h]
0x180027857  mov     [rsp+58h+var_18], edx
0x18002785b  mov     [r11-20h], r8d
0x18002785f  mov     [r11-28h], rax
0x180027863  mov     rax, [r9+10h]
0x180027867  mov     [r11-30h], rax
0x18002786b  mov     [r11-38h], r9
0x18002786f  mov     r9, [r10+40h]
0x180027873  call    WPP_SF_iqiidDd
0x180027878  jmp     short loc_1800278CB
0x18002787a  mov     rcx, cs:WPP_GLOBAL_Control
0x180027881  lea     rax, WPP_GLOBAL_Control
0x180027888  cmp     rcx, rax
0x18002788b  jz      short loc_1800278CB
0x18002788d  test    byte ptr [rcx+1Ch], 80h
0x180027891  jz      short loc_1800278CB
0x180027893  cmp     byte ptr [rcx+19h], 4
0x180027897  jb      short loc_1800278CB
0x180027899  movzx   eax, word ptr [rdx+1Ah]
0x18002789d  movzx   r8d, word ptr [rdx+18h]
0x1800278a2  mov     edx, 48h ; 'H'
0x1800278a7  mov     rcx, [rcx+10h]
0x1800278ab  mov     [rsp+58h+var_20], eax
0x1800278af  mov     rax, [r9+10h]
0x1800278b3  mov     [rsp+58h+var_28], r8d
0x1800278b8  mov     [rsp+58h+var_30], rax
0x1800278bd  mov     [rsp+58h+var_38], r9
0x1800278c2  mov     r9, [r10+40h]
0x1800278c6  call    WPP_SF_iqidD
0x1800278cb  add     rsp, 58h
0x1800278cf  retn
```
