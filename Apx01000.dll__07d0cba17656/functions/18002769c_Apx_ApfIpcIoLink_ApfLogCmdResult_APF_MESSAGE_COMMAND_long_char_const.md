# Apx::ApfIpcIoLink::ApfLogCmdResult(APF_MESSAGE_COMMAND *,long,char const *)

- ea: `0x18002769c`
- end: `0x18002774d`
- name: `?ApfLogCmdResult@ApfIpcIoLink@Apx@@AEAAXPEAUAPF_MESSAGE_COMMAND@@JPEBD@Z`
- size: `177`
- prototype: `void __fastcall(Apx::ApfIpcIoLink *__hidden this, struct APF_MESSAGE_COMMAND *, int, const char *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180027990`

## callees

- `0x18002769c`
- `0x180029408`

## string_xrefs

- `0x180027729`: `command operation completed`

## pseudocode

```c
void __fastcall Apx::ApfIpcIoLink::ApfLogCmdResult(
        Apx::ApfIpcIoLink *this,
        struct APF_MESSAGE_COMMAND *a2,
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
      v7 = 68;
LABEL_15:
      WPP_SF_iqsd(v6[2], v7, a3, *((_QWORD *)this + 8), v4, (__int64)"command operation completed", a3);
    }
  }
  else if ( a3 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = 70;
      goto LABEL_15;
    }
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v7 = 69;
      goto LABEL_15;
    }
  }
}

```

## disassembly

```asm
0x18002769c  sub     rsp, 48h
0x1800276a0  test    byte ptr [rdx+4], 10h
0x1800276a4  mov     r9, rdx
0x1800276a7  mov     r10, rcx
0x1800276aa  jz      short loc_1800276D6
0x1800276ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800276b3  lea     rax, WPP_GLOBAL_Control
0x1800276ba  cmp     rcx, rax
0x1800276bd  jz      loc_180027748
0x1800276c3  test    byte ptr [rcx+1Ch], 80h
0x1800276c7  jz      short loc_180027748
0x1800276c9  cmp     byte ptr [rcx+19h], 5
0x1800276cd  jb      short loc_180027748
0x1800276cf  mov     edx, 44h ; 'D'
0x1800276d4  jmp     short loc_180027725
0x1800276d6  test    r8d, r8d
0x1800276d9  js      short loc_180027701
0x1800276db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800276e2  lea     rax, WPP_GLOBAL_Control
0x1800276e9  cmp     rcx, rax
0x1800276ec  jz      short loc_180027748
0x1800276ee  test    byte ptr [rcx+1Ch], 80h
0x1800276f2  jz      short loc_180027748
0x1800276f4  cmp     byte ptr [rcx+19h], 4
0x1800276f8  jb      short loc_180027748
0x1800276fa  mov     edx, 45h ; 'E'
0x1800276ff  jmp     short loc_180027725
0x180027701  mov     rcx, cs:WPP_GLOBAL_Control
0x180027708  lea     rax, WPP_GLOBAL_Control
0x18002770f  cmp     rcx, rax
0x180027712  jz      short loc_180027748
0x180027714  test    byte ptr [rcx+1Ch], 80h
0x180027718  jz      short loc_180027748
0x18002771a  cmp     byte ptr [rcx+19h], 2
0x18002771e  jb      short loc_180027748
0x180027720  mov     edx, 46h ; 'F'
0x180027725  mov     rcx, [rcx+10h]
0x180027729  lea     rax, aCommandOperati; "command operation completed"
0x180027730  mov     [rsp+48h+var_18], r8d
0x180027735  mov     [rsp+48h+var_20], rax
0x18002773a  mov     [rsp+48h+var_28], r9
0x18002773f  mov     r9, [r10+40h]
0x180027743  call    WPP_SF_iqsd
0x180027748  add     rsp, 48h
0x18002774c  retn
```
