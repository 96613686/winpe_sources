# _lambda_1f2fa7ec6605b0250b290bf8a6443ef1_::operator()

- ea: `0x18002ade8`
- end: `0x18002aee2`
- name: `_lambda_1f2fa7ec6605b0250b290bf8a6443ef1_::operator()`
- size: `250`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18002efb8`
- `0x180031370`

## callees

- `0x180009878`
- `0x1800099c0`
- `0x180009a5c`
- `0x1800250f8`
- `0x18002ade8`
- `0x1800586c6`
- `0x180058700`

## string_xrefs

- `0x18002aea5`: `FileSystem::CreateFilesystem`

## pseudocode

```c
PVOID *__fastcall lambda_1f2fa7ec6605b0250b290bf8a6443ef1_::operator()(__int64 a1)
{
  unsigned int v2; // eax
  __int64 v3; // r8
  __int64 v4; // r9
  PVOID *result; // rax
  __int64 *v6; // r8
  _QWORD v7[2]; // [rsp+40h] [rbp-68h] BYREF
  _BYTE v8[64]; // [rsp+50h] [rbp-58h] BYREF
  __int64 v9; // [rsp+90h] [rbp-18h] BYREF

  memset_0(v8, 0, sizeof(v8));
  if ( **(_BYTE **)a1 )
    v2 = ReportIndentTracker::Enter();
  else
    v2 = ReportIndentTracker::Exit();
  v7[0] = v8;
  v7[1] = &v9;
  LOBYTE(v4) = **(_BYTE **)a1 != 0 ? 62 : 60;
  ReportIndentTracker::Format(v7, v2, v3, v4);
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v6 = *(__int64 **)(a1 + 8);
    if ( (unsigned __int64)v6[3] < 8 )
      v6 = (__int64 *)(a1 + 8);
    return (PVOID *)WPP_SF_ssSD(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      (__int64)"FileSystem::CreateFilesystem",
                      *v6,
                      **(_DWORD **)(a1 + 16));
  }
  return result;
}

```

## disassembly

```asm
0x18002ade8  push    rbx
0x18002adea  sub     rsp, 0A0h
0x18002adf1  mov     rax, cs:__security_cookie
0x18002adf8  xor     rax, rsp
0x18002adfb  mov     [rsp+0A8h+var_18], rax
0x18002ae03  mov     rbx, rcx
0x18002ae06  xor     edx, edx; Val
0x18002ae08  lea     r8d, [rdx+40h]; Size
0x18002ae0c  lea     rcx, [rsp+0A8h+var_58]; void *
0x18002ae11  call    memset_0
0x18002ae16  mov     rax, [rbx]
0x18002ae19  cmp     byte ptr [rax], 0
0x18002ae1c  jz      short loc_18002AE25
0x18002ae1e  call    ?Enter@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Enter(void)
0x18002ae23  jmp     short loc_18002AE2A
0x18002ae25  call    ?Exit@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Exit(void)
0x18002ae2a  mov     edx, eax
0x18002ae2c  lea     rax, [rsp+0A8h+var_58]
0x18002ae31  mov     [rsp+0A8h+var_68], rax
0x18002ae36  lea     rax, [rsp+0A8h+var_18]
0x18002ae3e  mov     [rsp+0A8h+var_60], rax
0x18002ae43  mov     rax, [rbx]
0x18002ae46  mov     cl, [rax]
0x18002ae48  neg     cl
0x18002ae4a  sbb     r9b, r9b
0x18002ae4d  and     r9b, 2
0x18002ae51  add     r9b, 3Ch ; '<'
0x18002ae55  lea     rcx, [rsp+0A8h+var_68]
0x18002ae5a  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x18002ae5f  lea     rax, WPP_GLOBAL_Control
0x18002ae66  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ae6d  cmp     rcx, rax
0x18002ae70  jz      short loc_18002AEC7
0x18002ae72  test    byte ptr [rcx+1Ch], 2
0x18002ae76  jz      short loc_18002AEC7
0x18002ae78  cmp     byte ptr [rcx+19h], 5
0x18002ae7c  jb      short loc_18002AEC7
0x18002ae7e  lea     rdx, [rbx+8]
0x18002ae82  mov     r8, [rdx]
0x18002ae85  mov     rax, [rbx+10h]
0x18002ae89  cmp     qword ptr [r8+18h], 8
0x18002ae8e  cmovb   r8, rdx
0x18002ae92  mov     edx, 15h
0x18002ae97  mov     eax, [rax]
0x18002ae99  mov     dword ptr [rsp+0A8h+var_78], eax; char
0x18002ae9d  mov     rax, [r8]
0x18002aea0  mov     [rsp+0A8h+var_80], rax; __int64
0x18002aea5  lea     rax, aFilesystemCrea; "FileSystem::CreateFilesystem"
0x18002aeac  mov     [rsp+0A8h+var_88], rax; __int64
0x18002aeb1  lea     r9, [rsp+0A8h+var_58]
0x18002aeb6  lea     r8, WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids
0x18002aebd  mov     rcx, [rcx+10h]; LoggerHandle
0x18002aec1  call    WPP_SF_ssSD
0x18002aec6  nop
0x18002aec7  jmp     short $+2
0x18002aec9  mov     rcx, [rsp+0A8h+var_18]
0x18002aed1  xor     rcx, rsp; StackCookie
0x18002aed4  call    __security_check_cookie
0x18002aed9  add     rsp, 0A0h
0x18002aee0  pop     rbx
0x18002aee1  retn
```
