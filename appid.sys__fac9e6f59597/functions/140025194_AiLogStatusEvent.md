# AiLogStatusEvent

- ea: `0x140025194`
- end: `0x140025226`
- name: `AiLogStatusEvent`
- size: `146`
- prototype: `NTSTATUS __fastcall(REGHANDLE, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14003825c`

## callees

- `0x140002018`
- `0x140006a20`
- `0x140025194`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x1400251d6`
- `ntoskrnl!EtwWrite` at `0x1400251d6`

## pseudocode

```c
NTSTATUS __fastcall AiLogStatusEvent(REGHANDLE a1, __int64 a2, unsigned int a3)
{
  NTSTATUS result; // eax
  __int64 v4; // r8
  __int64 Timer_high; // rdx
  unsigned int v6; // [rsp+30h] [rbp-28h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+38h] [rbp-20h] BYREF

  v6 = a3;
  v7.Ptr = (ULONGLONG)&v6;
  *(_QWORD *)&v7.Size = 4;
  result = EtwWrite(a1, &AppIdDriverFailed, 0, 1u, &v7);
  if ( result < 0 && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (Timer_high & 1) != 0 )
      return WPP_SF_DD(WPP_GLOBAL_Control->AttachedDevice, Timer_high, v4, v6, result);
  }
  return result;
}

```

## disassembly

```asm
0x140025194  mov     r11, rsp
0x140025197  sub     rsp, 58h
0x14002519b  mov     rax, cs:__security_cookie
0x1400251a2  xor     rax, rsp
0x1400251a5  mov     [rsp+58h+var_10], rax
0x1400251aa  mov     [r11-28h], r8d
0x1400251ae  lea     rax, [r11-28h]
0x1400251b2  mov     [r11-20h], rax
0x1400251b6  lea     rdx, AppIdDriverFailed; EventDescriptor
0x1400251bd  lea     rax, [r11-20h]
0x1400251c1  mov     qword ptr [r11-18h], 4
0x1400251c9  mov     r9d, 1; UserDataCount
0x1400251cf  mov     [r11-38h], rax
0x1400251d3  xor     r8d, r8d; ActivityId
0x1400251d6  call    cs:__imp_EtwWrite
0x1400251dd  nop     dword ptr [rax+rax+00h]
0x1400251e2  test    eax, eax
0x1400251e4  jns     short loc_140025213
0x1400251e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400251ed  lea     rdx, WPP_GLOBAL_Control
0x1400251f4  cmp     rcx, rdx
0x1400251f7  jz      short loc_140025213
0x1400251f9  mov     edx, [rcx+2Ch]
0x1400251fc  test    dl, 1
0x1400251ff  jz      short loc_140025213
0x140025201  mov     r9d, [rsp+58h+var_28]
0x140025206  mov     rcx, [rcx+18h]
0x14002520a  mov     [rsp+58h+var_38], eax
0x14002520e  call    WPP_SF_DD
0x140025213  mov     rcx, [rsp+58h+var_10]
0x140025218  xor     rcx, rsp; StackCookie
0x14002521b  call    __security_check_cookie
0x140025220  add     rsp, 58h
0x140025224  retn
```
