# _lambda_2e17cd588ec0305ca15fed111eef73b6_::operator()

- ea: `0x180040f90`
- end: `0x180041099`
- name: `_lambda_2e17cd588ec0305ca15fed111eef73b6_::operator()`
- size: `265`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18004540c`
- `0x18004b618`

## callees

- `0x180009878`
- `0x1800099c0`
- `0x180009a5c`
- `0x180040f90`
- `0x180052af0`
- `0x1800586c6`
- `0x180058700`

## string_xrefs

- `0x180041063`: `GidsApplication::PerformSecurityOperation`

## pseudocode

```c
PVOID *__fastcall lambda_2e17cd588ec0305ca15fed111eef73b6_::operator()(__int64 a1)
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
    return (PVOID *)WPP_SF_ssLLDss(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      (__int64)"GidsApplication::PerformSecurityOperation",
                      *(_DWORD *)(*(_QWORD *)(a1 + 8) + 16LL),
                      **(_DWORD **)(a1 + 16),
                      **(_DWORD **)(a1 + 24),
                      *(_QWORD *)(*(_QWORD *)(a1 + 32) + 16LL),
                      *(_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL));
  }
  return result;
}

```

## disassembly

```asm
0x180040f90  push    rbx
0x180040f92  sub     rsp, 0B0h
0x180040f99  mov     rax, cs:__security_cookie
0x180040fa0  xor     rax, rsp
0x180040fa3  mov     [rsp+0B8h+var_18], rax
0x180040fab  mov     rbx, rcx
0x180040fae  xor     edx, edx; Val
0x180040fb0  lea     r8d, [rdx+40h]; Size
0x180040fb4  lea     rcx, [rsp+0B8h+var_58]; void *
0x180040fb9  call    memset_0
0x180040fbe  mov     rax, [rbx]
0x180040fc1  cmp     byte ptr [rax], 0
0x180040fc4  jz      short loc_180040FCD
0x180040fc6  call    ?Enter@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Enter(void)
0x180040fcb  jmp     short loc_180040FD2
0x180040fcd  call    ?Exit@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Exit(void)
0x180040fd2  mov     edx, eax
0x180040fd4  lea     rax, [rsp+0B8h+var_58]
0x180040fd9  mov     [rsp+0B8h+var_68], rax
0x180040fde  lea     rax, [rsp+0B8h+var_18]
0x180040fe6  mov     [rsp+0B8h+var_60], rax
0x180040feb  mov     rax, [rbx]
0x180040fee  mov     cl, [rax]
0x180040ff0  neg     cl
0x180040ff2  sbb     r9b, r9b
0x180040ff5  and     r9b, 2
0x180040ff9  add     r9b, 3Ch ; '<'
0x180040ffd  lea     rcx, [rsp+0B8h+var_68]
0x180041002  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x180041007  lea     rax, WPP_GLOBAL_Control
0x18004100e  mov     rcx, cs:WPP_GLOBAL_Control
0x180041015  cmp     rcx, rax
0x180041018  jz      short loc_18004107E
0x18004101a  test    byte ptr [rcx+1Ch], 2
0x18004101e  jz      short loc_18004107E
0x180041020  cmp     byte ptr [rcx+19h], 5
0x180041024  jb      short loc_18004107E
0x180041026  mov     r8, [rbx+20h]
0x18004102a  mov     r9, [rbx+18h]
0x18004102e  mov     r10, [rbx+10h]
0x180041032  mov     r11, [rbx+8]
0x180041036  mov     edx, 24h ; '$'
0x18004103b  mov     rax, [r8+20h]
0x18004103f  mov     [rsp+0B8h+var_70], rax; __int64
0x180041044  mov     rax, [r8+10h]
0x180041048  mov     [rsp+0B8h+var_78], rax; __int64
0x18004104d  mov     eax, [r9]
0x180041050  mov     dword ptr [rsp+0B8h+var_80], eax; char
0x180041054  mov     eax, [r10]
0x180041057  mov     dword ptr [rsp+0B8h+var_88], eax; char
0x18004105b  mov     eax, [r11+10h]
0x18004105f  mov     dword ptr [rsp+0B8h+var_90], eax; char
0x180041063  lea     rax, aGidsapplicatio_12; "GidsApplication::PerformSecurityOperati"...
0x18004106a  mov     [rsp+0B8h+var_98], rax; __int64
0x18004106f  lea     r9, [rsp+0B8h+var_58]
0x180041074  mov     rcx, [rcx+10h]; LoggerHandle
0x180041078  call    WPP_SF_ssLLDss
0x18004107d  nop
0x18004107e  jmp     short $+2
0x180041080  mov     rcx, [rsp+0B8h+var_18]
0x180041088  xor     rcx, rsp; StackCookie
0x18004108b  call    __security_check_cookie
0x180041090  add     rsp, 0B0h
0x180041097  pop     rbx
0x180041098  retn
```
