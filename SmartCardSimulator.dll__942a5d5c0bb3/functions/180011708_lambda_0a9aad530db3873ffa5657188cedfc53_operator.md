# _lambda_0a9aad530db3873ffa5657188cedfc53_::operator()

- ea: `0x180011708`
- end: `0x18001180f`
- name: `_lambda_0a9aad530db3873ffa5657188cedfc53_::operator()`
- size: `263`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180013b3c`
- `0x1800166fc`

## callees

- `0x180009878`
- `0x1800099c0`
- `0x180009a5c`
- `0x180011708`
- `0x18001daec`
- `0x1800586c6`
- `0x180058700`

## string_xrefs

- `0x1800117d2`: `Channel::PostCommand::PutKey`

## pseudocode

```c
PVOID *__fastcall lambda_0a9aad530db3873ffa5657188cedfc53_::operator()(__int64 a1)
{
  unsigned int v2; // eax
  __int64 v3; // r8
  __int64 v4; // r9
  PVOID *result; // rax
  _QWORD v6[2]; // [rsp+50h] [rbp-68h] BYREF
  _BYTE v7[64]; // [rsp+60h] [rbp-58h] BYREF
  __int64 v8; // [rsp+A0h] [rbp-18h] BYREF

  memset_0(v7, 0, sizeof(v7));
  if ( **(_BYTE **)a1 )
    v2 = ReportIndentTracker::Enter();
  else
    v2 = ReportIndentTracker::Exit();
  v6[0] = v7;
  v6[1] = &v8;
  LOBYTE(v4) = **(_BYTE **)a1 != 0 ? 62 : 60;
  ReportIndentTracker::Format(v6, v2, v3, v4);
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    return (PVOID *)WPP_SF_ssLDss(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      (__int64)"Channel::PostCommand::PutKey",
                      *(_DWORD *)(*(_QWORD *)(a1 + 8) + 16LL),
                      **(_WORD **)(a1 + 16),
                      *(_QWORD *)(*(_QWORD *)(a1 + 24) + 16LL),
                      *(_QWORD *)(*(_QWORD *)(a1 + 24) + 32LL));
  }
  return result;
}

```

## disassembly

```asm
0x180011708  push    rbx
0x18001170a  sub     rsp, 0B0h
0x180011711  mov     rax, cs:__security_cookie
0x180011718  xor     rax, rsp
0x18001171b  mov     [rsp+0B8h+var_18], rax
0x180011723  mov     rbx, rcx
0x180011726  xor     edx, edx; Val
0x180011728  lea     r8d, [rdx+40h]; Size
0x18001172c  lea     rcx, [rsp+0B8h+var_58]; void *
0x180011731  call    memset_0
0x180011736  mov     rax, [rbx]
0x180011739  cmp     byte ptr [rax], 0
0x18001173c  jz      short loc_180011745
0x18001173e  call    ?Enter@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Enter(void)
0x180011743  jmp     short loc_18001174A
0x180011745  call    ?Exit@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Exit(void)
0x18001174a  mov     edx, eax
0x18001174c  lea     rax, [rsp+0B8h+var_58]
0x180011751  mov     [rsp+0B8h+var_68], rax
0x180011756  lea     rax, [rsp+0B8h+var_18]
0x18001175e  mov     [rsp+0B8h+var_60], rax
0x180011763  mov     rax, [rbx]
0x180011766  mov     cl, [rax]
0x180011768  neg     cl
0x18001176a  sbb     r9b, r9b
0x18001176d  and     r9b, 2
0x180011771  add     r9b, 3Ch ; '<'
0x180011775  lea     rcx, [rsp+0B8h+var_68]
0x18001177a  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x18001177f  lea     rax, WPP_GLOBAL_Control
0x180011786  mov     rcx, cs:WPP_GLOBAL_Control
0x18001178d  cmp     rcx, rax
0x180011790  jz      short loc_1800117F4
0x180011792  test    byte ptr [rcx+1Ch], 2
0x180011796  jz      short loc_1800117F4
0x180011798  cmp     byte ptr [rcx+19h], 5
0x18001179c  jb      short loc_1800117F4
0x18001179e  mov     r8, [rbx+18h]
0x1800117a2  mov     rax, [rbx+10h]
0x1800117a6  movzx   r9d, word ptr [rax]
0x1800117aa  mov     r10, [rbx+8]
0x1800117ae  mov     edx, 21h ; '!'
0x1800117b3  mov     rax, [r8+20h]
0x1800117b7  mov     [rsp+0B8h+var_78], rax; __int64
0x1800117bc  mov     rax, [r8+10h]
0x1800117c0  mov     [rsp+0B8h+var_80], rax; __int64
0x1800117c5  mov     dword ptr [rsp+0B8h+var_88], r9d; char
0x1800117ca  mov     eax, [r10+10h]
0x1800117ce  mov     dword ptr [rsp+0B8h+var_90], eax; char
0x1800117d2  lea     rax, aChannelPostcom_0; "Channel::PostCommand::PutKey"
0x1800117d9  mov     [rsp+0B8h+var_98], rax; __int64
0x1800117de  lea     r9, [rsp+0B8h+var_58]
0x1800117e3  lea     r8, WPP_af6c915c0e3c3e5aff280afce4c18d8e_Traceguids
0x1800117ea  mov     rcx, [rcx+10h]; LoggerHandle
0x1800117ee  call    WPP_SF_ssLDss
0x1800117f3  nop
0x1800117f4  jmp     short $+2
0x1800117f6  mov     rcx, [rsp+0B8h+var_18]
0x1800117fe  xor     rcx, rsp; StackCookie
0x180011801  call    __security_check_cookie
0x180011806  add     rsp, 0B0h
0x18001180d  pop     rbx
0x18001180e  retn
```
