# _lambda_70bdc301ed57c84e747bc014d07b6e36_::operator()

- ea: `0x180011e1c`
- end: `0x180011f23`
- name: `_lambda_70bdc301ed57c84e747bc014d07b6e36_::operator()`
- size: `263`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180013c70`
- `0x180014fa0`

## callees

- `0x180009878`
- `0x1800099c0`
- `0x180009a5c`
- `0x180011e1c`
- `0x18001daec`
- `0x1800586c6`
- `0x180058700`

## string_xrefs

- `0x180011ee6`: `Channel::PreCommand::GetData`

## pseudocode

```c
PVOID *__fastcall lambda_70bdc301ed57c84e747bc014d07b6e36_::operator()(__int64 a1)
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
                      (__int64)"Channel::PreCommand::GetData",
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
0x180011e1c  push    rbx
0x180011e1e  sub     rsp, 0B0h
0x180011e25  mov     rax, cs:__security_cookie
0x180011e2c  xor     rax, rsp
0x180011e2f  mov     [rsp+0B8h+var_18], rax
0x180011e37  mov     rbx, rcx
0x180011e3a  xor     edx, edx; Val
0x180011e3c  lea     r8d, [rdx+40h]; Size
0x180011e40  lea     rcx, [rsp+0B8h+var_58]; void *
0x180011e45  call    memset_0
0x180011e4a  mov     rax, [rbx]
0x180011e4d  cmp     byte ptr [rax], 0
0x180011e50  jz      short loc_180011E59
0x180011e52  call    ?Enter@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Enter(void)
0x180011e57  jmp     short loc_180011E5E
0x180011e59  call    ?Exit@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Exit(void)
0x180011e5e  mov     edx, eax
0x180011e60  lea     rax, [rsp+0B8h+var_58]
0x180011e65  mov     [rsp+0B8h+var_68], rax
0x180011e6a  lea     rax, [rsp+0B8h+var_18]
0x180011e72  mov     [rsp+0B8h+var_60], rax
0x180011e77  mov     rax, [rbx]
0x180011e7a  mov     cl, [rax]
0x180011e7c  neg     cl
0x180011e7e  sbb     r9b, r9b
0x180011e81  and     r9b, 2
0x180011e85  add     r9b, 3Ch ; '<'
0x180011e89  lea     rcx, [rsp+0B8h+var_68]
0x180011e8e  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x180011e93  lea     rax, WPP_GLOBAL_Control
0x180011e9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180011ea1  cmp     rcx, rax
0x180011ea4  jz      short loc_180011F08
0x180011ea6  test    byte ptr [rcx+1Ch], 2
0x180011eaa  jz      short loc_180011F08
0x180011eac  cmp     byte ptr [rcx+19h], 5
0x180011eb0  jb      short loc_180011F08
0x180011eb2  mov     r8, [rbx+18h]
0x180011eb6  mov     rax, [rbx+10h]
0x180011eba  movzx   r9d, word ptr [rax]
0x180011ebe  mov     r10, [rbx+8]
0x180011ec2  mov     edx, 1Ch
0x180011ec7  mov     rax, [r8+20h]
0x180011ecb  mov     [rsp+0B8h+var_78], rax; __int64
0x180011ed0  mov     rax, [r8+10h]
0x180011ed4  mov     [rsp+0B8h+var_80], rax; __int64
0x180011ed9  mov     dword ptr [rsp+0B8h+var_88], r9d; char
0x180011ede  mov     eax, [r10+10h]
0x180011ee2  mov     dword ptr [rsp+0B8h+var_90], eax; char
0x180011ee6  lea     rax, aChannelPrecomm_0; "Channel::PreCommand::GetData"
0x180011eed  mov     [rsp+0B8h+var_98], rax; __int64
0x180011ef2  lea     r9, [rsp+0B8h+var_58]
0x180011ef7  lea     r8, WPP_af6c915c0e3c3e5aff280afce4c18d8e_Traceguids
0x180011efe  mov     rcx, [rcx+10h]; LoggerHandle
0x180011f02  call    WPP_SF_ssLDss
0x180011f07  nop
0x180011f08  jmp     short $+2
0x180011f0a  mov     rcx, [rsp+0B8h+var_18]
0x180011f12  xor     rcx, rsp; StackCookie
0x180011f15  call    __security_check_cookie
0x180011f1a  add     rsp, 0B0h
0x180011f21  pop     rbx
0x180011f22  retn
```
