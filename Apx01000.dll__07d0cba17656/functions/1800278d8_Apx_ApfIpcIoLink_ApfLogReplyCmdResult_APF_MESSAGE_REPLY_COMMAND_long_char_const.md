# Apx::ApfIpcIoLink::ApfLogReplyCmdResult(APF_MESSAGE_REPLY_COMMAND *,long,char const *)

- ea: `0x1800278d8`
- end: `0x180027989`
- name: `?ApfLogReplyCmdResult@ApfIpcIoLink@Apx@@AEAAXPEAUAPF_MESSAGE_REPLY_COMMAND@@JPEBD@Z`
- size: `177`
- prototype: `void __fastcall(Apx::ApfIpcIoLink *__hidden this, struct APF_MESSAGE_REPLY_COMMAND *, int, const char *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180027990`

## callees

- `0x1800278d8`
- `0x180029408`

## string_xrefs

- `0x180027965`: `reply command operation completed`

## pseudocode

```c
void __fastcall Apx::ApfIpcIoLink::ApfLogReplyCmdResult(
        Apx::ApfIpcIoLink *this,
        struct APF_MESSAGE_REPLY_COMMAND *a2,
        int a3,
        const char *a4)
{
  char v4; // r9
  _QWORD *v6; // rcx
  int v7; // edx

  v4 = (char)a2;
  if ( (*((_BYTE *)a2 + 4) & 0x10) != 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v7 = 73;
LABEL_15:
      WPP_SF_iqsd(v6[2], v7, a3, *((_QWORD *)this + 8), v4, (__int64)"reply command operation completed", a3);
    }
  }
  else if ( a3 >= 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v7 = 75;
      goto LABEL_15;
    }
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = 74;
      goto LABEL_15;
    }
  }
}

```

## disassembly

```asm
0x1800278d8  sub     rsp, 48h
0x1800278dc  test    byte ptr [rdx+4], 10h
0x1800278e0  mov     r9, rdx
0x1800278e3  mov     r10, rcx
0x1800278e6  jz      short loc_180027912
0x1800278e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800278ef  lea     rax, WPP_GLOBAL_Control
0x1800278f6  cmp     rcx, rax
0x1800278f9  jz      loc_180027984
0x1800278ff  test    byte ptr [rcx+1Ch], 80h
0x180027903  jz      short loc_180027984
0x180027905  cmp     byte ptr [rcx+19h], 5
0x180027909  jb      short loc_180027984
0x18002790b  mov     edx, 49h ; 'I'
0x180027910  jmp     short loc_180027961
0x180027912  test    r8d, r8d
0x180027915  jns     short loc_18002793D
0x180027917  mov     rcx, cs:WPP_GLOBAL_Control
0x18002791e  lea     rax, WPP_GLOBAL_Control
0x180027925  cmp     rcx, rax
0x180027928  jz      short loc_180027984
0x18002792a  test    byte ptr [rcx+1Ch], 80h
0x18002792e  jz      short loc_180027984
0x180027930  cmp     byte ptr [rcx+19h], 2
0x180027934  jb      short loc_180027984
0x180027936  mov     edx, 4Ah ; 'J'
0x18002793b  jmp     short loc_180027961
0x18002793d  mov     rcx, cs:WPP_GLOBAL_Control
0x180027944  lea     rax, WPP_GLOBAL_Control
0x18002794b  cmp     rcx, rax
0x18002794e  jz      short loc_180027984
0x180027950  test    byte ptr [rcx+1Ch], 80h
0x180027954  jz      short loc_180027984
0x180027956  cmp     byte ptr [rcx+19h], 4
0x18002795a  jb      short loc_180027984
0x18002795c  mov     edx, 4Bh ; 'K'
0x180027961  mov     rcx, [rcx+10h]
0x180027965  lea     rax, aReplyCommandOp; "reply command operation completed"
0x18002796c  mov     [rsp+48h+var_18], r8d
0x180027971  mov     [rsp+48h+var_20], rax
0x180027976  mov     [rsp+48h+var_28], r9
0x18002797b  mov     r9, [r10+40h]
0x18002797f  call    WPP_SF_iqsd
0x180027984  add     rsp, 48h
0x180027988  retn
```
