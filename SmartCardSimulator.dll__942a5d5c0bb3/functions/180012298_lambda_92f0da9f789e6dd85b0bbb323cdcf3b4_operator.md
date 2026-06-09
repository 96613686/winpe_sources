# _lambda_92f0da9f789e6dd85b0bbb323cdcf3b4_::operator()

- ea: `0x180012298`
- end: `0x1800123c5`
- name: `_lambda_92f0da9f789e6dd85b0bbb323cdcf3b4_::operator()`
- size: `301`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180013d20`
- `0x180016a5c`

## callees

- `0x180009878`
- `0x1800099c0`
- `0x180009a5c`
- `0x180012298`
- `0x18001dc34`
- `0x1800586c6`
- `0x180058700`

## string_xrefs

- `0x180012380`: `Channel::PreCommand::Select`

## pseudocode

```c
PVOID *__fastcall lambda_92f0da9f789e6dd85b0bbb323cdcf3b4_::operator()(__int64 a1)
{
  unsigned int v2; // eax
  __int64 v3; // r8
  __int64 v4; // r9
  PVOID *result; // rax
  _QWORD v6[2]; // [rsp+60h] [rbp-68h] BYREF
  _BYTE v7[64]; // [rsp+70h] [rbp-58h] BYREF
  __int64 v8; // [rsp+B0h] [rbp-18h] BYREF

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
    return (PVOID *)WPP_SF_ssLLLLDss(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      (__int64)"Channel::PreCommand::Select",
                      *(_DWORD *)(*(_QWORD *)(a1 + 8) + 16LL),
                      **(_DWORD **)(a1 + 16),
                      **(_DWORD **)(a1 + 24),
                      **(_DWORD **)(a1 + 32),
                      **(_WORD **)(a1 + 40),
                      *(_QWORD *)(*(_QWORD *)(a1 + 48) + 16LL),
                      *(_QWORD *)(*(_QWORD *)(a1 + 48) + 32LL));
  }
  return result;
}

```

## disassembly

```asm
0x180012298  mov     [rsp+arg_8], rbx
0x18001229d  push    rdi
0x18001229e  sub     rsp, 0C0h
0x1800122a5  mov     rax, cs:__security_cookie
0x1800122ac  xor     rax, rsp
0x1800122af  mov     [rsp+0C8h+var_18], rax
0x1800122b7  mov     rbx, rcx
0x1800122ba  xor     edx, edx; Val
0x1800122bc  lea     r8d, [rdx+40h]; Size
0x1800122c0  lea     rcx, [rsp+0C8h+var_58]; void *
0x1800122c5  call    memset_0
0x1800122ca  mov     rax, [rbx]
0x1800122cd  cmp     byte ptr [rax], 0
0x1800122d0  jz      short loc_1800122D9
0x1800122d2  call    ?Enter@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Enter(void)
0x1800122d7  jmp     short loc_1800122DE
0x1800122d9  call    ?Exit@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Exit(void)
0x1800122de  mov     edx, eax
0x1800122e0  lea     rax, [rsp+0C8h+var_58]
0x1800122e5  mov     [rsp+0C8h+var_68], rax
0x1800122ea  lea     rax, [rsp+0C8h+var_18]
0x1800122f2  mov     [rsp+0C8h+var_60], rax
0x1800122f7  mov     rax, [rbx]
0x1800122fa  mov     cl, [rax]
0x1800122fc  neg     cl
0x1800122fe  sbb     r9b, r9b
0x180012301  and     r9b, 2
0x180012305  add     r9b, 3Ch ; '<'
0x180012309  lea     rcx, [rsp+0C8h+var_68]
0x18001230e  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x180012313  lea     rax, WPP_GLOBAL_Control
0x18001231a  mov     rdi, cs:WPP_GLOBAL_Control
0x180012321  cmp     rdi, rax
0x180012324  jz      short loc_1800123A2
0x180012326  test    byte ptr [rdi+1Ch], 2
0x18001232a  jz      short loc_1800123A2
0x18001232c  cmp     byte ptr [rdi+19h], 5
0x180012330  jb      short loc_1800123A2
0x180012332  mov     rcx, [rbx+30h]
0x180012336  mov     rax, [rbx+28h]
0x18001233a  movzx   edx, word ptr [rax]
0x18001233d  mov     r8, [rbx+20h]
0x180012341  mov     r9, [rbx+18h]
0x180012345  mov     r10, [rbx+10h]
0x180012349  mov     r11, [rbx+8]
0x18001234d  mov     rax, [rcx+20h]
0x180012351  mov     [rsp+0C8h+var_70], rax; __int64
0x180012356  mov     rax, [rcx+10h]
0x18001235a  mov     [rsp+0C8h+var_78], rax; __int64
0x18001235f  mov     dword ptr [rsp+0C8h+var_80], edx; char
0x180012363  mov     eax, [r8]
0x180012366  mov     dword ptr [rsp+0C8h+var_88], eax; char
0x18001236a  mov     eax, [r9]
0x18001236d  mov     dword ptr [rsp+0C8h+var_90], eax; char
0x180012371  mov     eax, [r10]
0x180012374  mov     dword ptr [rsp+0C8h+var_98], eax; char
0x180012378  mov     eax, [r11+10h]
0x18001237c  mov     dword ptr [rsp+0C8h+var_A0], eax; char
0x180012380  lea     rax, aChannelPrecomm; "Channel::PreCommand::Select"
0x180012387  mov     [rsp+0C8h+var_A8], rax; __int64
0x18001238c  lea     r9, [rsp+0C8h+var_58]
0x180012391  lea     r8, WPP_af6c915c0e3c3e5aff280afce4c18d8e_Traceguids
0x180012398  mov     rcx, [rdi+10h]; LoggerHandle
0x18001239c  call    WPP_SF_ssLLLLDss
0x1800123a1  nop
0x1800123a2  jmp     short $+2
0x1800123a4  mov     rcx, [rsp+0C8h+var_18]
0x1800123ac  xor     rcx, rsp; StackCookie
0x1800123af  call    __security_check_cookie
0x1800123b4  mov     rbx, [rsp+0C8h+arg_8]
0x1800123bc  add     rsp, 0C0h
0x1800123c3  pop     rdi
0x1800123c4  retn
```
