# _lambda_d67deec0bf479253ff4f6257aa25e1d9_::operator()

- ea: `0x1800429a8`
- end: `0x180042ab0`
- name: `_lambda_d67deec0bf479253ff4f6257aa25e1d9_::operator()`
- size: `264`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18004582c`
- `0x180047dbc`

## callees

- `0x180009878`
- `0x1800099c0`
- `0x180009a5c`
- `0x18001daec`
- `0x1800429a8`
- `0x1800586c6`
- `0x180058700`

## string_xrefs

- `0x180042a73`: `GidsApplication::CreateFile`

## pseudocode

```c
PVOID *__fastcall lambda_d67deec0bf479253ff4f6257aa25e1d9_::operator()(__int64 a1)
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
                      (__int64)"GidsApplication::CreateFile",
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
0x1800429a8  push    rbx
0x1800429aa  sub     rsp, 0B0h
0x1800429b1  mov     rax, cs:__security_cookie
0x1800429b8  xor     rax, rsp
0x1800429bb  mov     [rsp+0B8h+var_18], rax
0x1800429c3  mov     rbx, rcx
0x1800429c6  xor     edx, edx; Val
0x1800429c8  lea     r8d, [rdx+40h]; Size
0x1800429cc  lea     rcx, [rsp+0B8h+var_58]; void *
0x1800429d1  call    memset_0
0x1800429d6  mov     rax, [rbx]
0x1800429d9  cmp     byte ptr [rax], 0
0x1800429dc  jz      short loc_1800429E5
0x1800429de  call    ?Enter@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Enter(void)
0x1800429e3  jmp     short loc_1800429EA
0x1800429e5  call    ?Exit@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Exit(void)
0x1800429ea  mov     edx, eax
0x1800429ec  lea     rax, [rsp+0B8h+var_58]
0x1800429f1  mov     [rsp+0B8h+var_68], rax
0x1800429f6  lea     rax, [rsp+0B8h+var_18]
0x1800429fe  mov     [rsp+0B8h+var_60], rax
0x180042a03  mov     rax, [rbx]
0x180042a06  mov     cl, [rax]
0x180042a08  neg     cl
0x180042a0a  sbb     r9b, r9b
0x180042a0d  and     r9b, 2
0x180042a11  add     r9b, 3Ch ; '<'
0x180042a15  lea     rcx, [rsp+0B8h+var_68]
0x180042a1a  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x180042a1f  lea     rax, WPP_GLOBAL_Control
0x180042a26  mov     rcx, cs:WPP_GLOBAL_Control
0x180042a2d  cmp     rcx, rax
0x180042a30  jz      short loc_180042A95
0x180042a32  test    byte ptr [rcx+1Ch], 2
0x180042a36  jz      short loc_180042A95
0x180042a38  cmp     byte ptr [rcx+19h], 5
0x180042a3c  jb      short loc_180042A95
0x180042a3e  mov     r8, [rbx+18h]
0x180042a42  mov     rax, [rbx+10h]
0x180042a46  movzx   r9d, word ptr [rax+4]
0x180042a4b  mov     r10, [rbx+8]
0x180042a4f  mov     edx, 15h
0x180042a54  mov     rax, [r8+20h]
0x180042a58  mov     [rsp+0B8h+var_78], rax; __int64
0x180042a5d  mov     rax, [r8+10h]
0x180042a61  mov     [rsp+0B8h+var_80], rax; __int64
0x180042a66  mov     dword ptr [rsp+0B8h+var_88], r9d; char
0x180042a6b  mov     eax, [r10+10h]
0x180042a6f  mov     dword ptr [rsp+0B8h+var_90], eax; char
0x180042a73  lea     rax, aGidsapplicatio_8; "GidsApplication::CreateFile"
0x180042a7a  mov     [rsp+0B8h+var_98], rax; __int64
0x180042a7f  lea     r9, [rsp+0B8h+var_58]
0x180042a84  lea     r8, WPP_0ce2c06117c939fb31b3fe04e838cd7b_Traceguids
0x180042a8b  mov     rcx, [rcx+10h]; LoggerHandle
0x180042a8f  call    WPP_SF_ssLDss
0x180042a94  nop
0x180042a95  jmp     short $+2
0x180042a97  mov     rcx, [rsp+0B8h+var_18]
0x180042a9f  xor     rcx, rsp; StackCookie
0x180042aa2  call    __security_check_cookie
0x180042aa7  add     rsp, 0B0h
0x180042aae  pop     rbx
0x180042aaf  retn
```
