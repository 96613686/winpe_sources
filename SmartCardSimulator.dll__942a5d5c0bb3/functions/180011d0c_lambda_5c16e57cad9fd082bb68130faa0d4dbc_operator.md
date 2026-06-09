# _lambda_5c16e57cad9fd082bb68130faa0d4dbc_::operator()

- ea: `0x180011d0c`
- end: `0x180011e14`
- name: `_lambda_5c16e57cad9fd082bb68130faa0d4dbc_::operator()`
- size: `264`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180013c44`
- `0x180013fd4`

## callees

- `0x180009878`
- `0x1800099c0`
- `0x180009a5c`
- `0x180011d0c`
- `0x18001daec`
- `0x1800586c6`
- `0x180058700`

## string_xrefs

- `0x180011dd7`: `Channel::PostCommand::CreateFile`

## pseudocode

```c
PVOID *__fastcall lambda_5c16e57cad9fd082bb68130faa0d4dbc_::operator()(__int64 a1)
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
                      (__int64)"Channel::PostCommand::CreateFile",
                      *(_DWORD *)(*(_QWORD *)(a1 + 8) + 16LL),
                      *(_WORD *)(*(_QWORD *)(a1 + 16) + 4LL),
                      *(_QWORD *)(*(_QWORD *)(a1 + 24) + 16LL),
                      *(_QWORD *)(*(_QWORD *)(a1 + 24) + 32LL));
  }
  return result;
}

```

## disassembly

```asm
0x180011d0c  push    rbx
0x180011d0e  sub     rsp, 0B0h
0x180011d15  mov     rax, cs:__security_cookie
0x180011d1c  xor     rax, rsp
0x180011d1f  mov     [rsp+0B8h+var_18], rax
0x180011d27  mov     rbx, rcx
0x180011d2a  xor     edx, edx; Val
0x180011d2c  lea     r8d, [rdx+40h]; Size
0x180011d30  lea     rcx, [rsp+0B8h+var_58]; void *
0x180011d35  call    memset_0
0x180011d3a  mov     rax, [rbx]
0x180011d3d  cmp     byte ptr [rax], 0
0x180011d40  jz      short loc_180011D49
0x180011d42  call    ?Enter@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Enter(void)
0x180011d47  jmp     short loc_180011D4E
0x180011d49  call    ?Exit@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Exit(void)
0x180011d4e  mov     edx, eax
0x180011d50  lea     rax, [rsp+0B8h+var_58]
0x180011d55  mov     [rsp+0B8h+var_68], rax
0x180011d5a  lea     rax, [rsp+0B8h+var_18]
0x180011d62  mov     [rsp+0B8h+var_60], rax
0x180011d67  mov     rax, [rbx]
0x180011d6a  mov     cl, [rax]
0x180011d6c  neg     cl
0x180011d6e  sbb     r9b, r9b
0x180011d71  and     r9b, 2
0x180011d75  add     r9b, 3Ch ; '<'
0x180011d79  lea     rcx, [rsp+0B8h+var_68]
0x180011d7e  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x180011d83  lea     rax, WPP_GLOBAL_Control
0x180011d8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180011d91  cmp     rcx, rax
0x180011d94  jz      short loc_180011DF9
0x180011d96  test    byte ptr [rcx+1Ch], 2
0x180011d9a  jz      short loc_180011DF9
0x180011d9c  cmp     byte ptr [rcx+19h], 5
0x180011da0  jb      short loc_180011DF9
0x180011da2  mov     r8, [rbx+18h]
0x180011da6  mov     rax, [rbx+10h]
0x180011daa  movzx   r9d, word ptr [rax+4]
0x180011daf  mov     r10, [rbx+8]
0x180011db3  mov     edx, 1Dh
0x180011db8  mov     rax, [r8+20h]
0x180011dbc  mov     [rsp+0B8h+var_78], rax; __int64
0x180011dc1  mov     rax, [r8+10h]
0x180011dc5  mov     [rsp+0B8h+var_80], rax; __int64
0x180011dca  mov     dword ptr [rsp+0B8h+var_88], r9d; char
0x180011dcf  mov     eax, [r10+10h]
0x180011dd3  mov     dword ptr [rsp+0B8h+var_90], eax; char
0x180011dd7  lea     rax, aChannelPostcom; "Channel::PostCommand::CreateFile"
0x180011dde  mov     [rsp+0B8h+var_98], rax; __int64
0x180011de3  lea     r9, [rsp+0B8h+var_58]
0x180011de8  lea     r8, WPP_af6c915c0e3c3e5aff280afce4c18d8e_Traceguids
0x180011def  mov     rcx, [rcx+10h]; LoggerHandle
0x180011df3  call    WPP_SF_ssLDss
0x180011df8  nop
0x180011df9  jmp     short $+2
0x180011dfb  mov     rcx, [rsp+0B8h+var_18]
0x180011e03  xor     rcx, rsp; StackCookie
0x180011e06  call    __security_check_cookie
0x180011e0b  add     rsp, 0B0h
0x180011e12  pop     rbx
0x180011e13  retn
```
