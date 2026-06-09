# QueueCommandSS

- ea: `0x14000c368`
- end: `0x14000c54a`
- name: `QueueCommandSS`
- size: `482`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140002320`

## callees

- `0x140004adc`
- `0x14000785c`
- `0x14000bd7c`
- `0x14000be7c`
- `0x14000c368`
- `0x14000d7f0`

## import_xrefs

- `storport!StorPortNotification` at `0x14000c51f`
- `storport!StorPortNotification` at `0x14000c51f`
- `storport!StorPortExtendedFunction` at `0x14000c3aa`
- `storport!StorPortExtendedFunction` at `0x14000c3f7`
- `storport!StorPortExtendedFunction` at `0x14000c3aa`
- `storport!StorPortExtendedFunction` at `0x14000c3f7`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000c42c`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000c4eb`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000c42c`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000c4eb`

## pseudocode

```c
__int64 __fastcall QueueCommandSS(__int64 a1, __int64 a2, __int64 a3)
{
  __int128 *v5; // r14
  char v6; // bp
  int v7; // eax
  __int64 v8; // rbx
  int Default; // eax
  int v10; // edx
  int v11; // r8d
  __int64 v12; // r9
  int v13; // ebp
  char v14; // bl
  int v15; // eax
  int v16; // edx
  __int64 v18; // [rsp+40h] [rbp-58h] BYREF
  __int128 v19; // [rsp+48h] [rbp-50h] BYREF

  v18 = 0;
  v19 = 0;
  v5 = &v19;
  if ( (unsigned int)StorPortExtendedFunction(40, a1, a3, &v19) )
    v5 = 0;
  if ( (*(_DWORD *)(a3 + 12) & 0xC0) != 0
    && ((v6 = 1, !*(_QWORD *)(a3 + 48)) || (v7 = StorPortExtendedFunction(6, a2, a3, &v18), v6 = v7, v7)) )
  {
    if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v8 = *(_QWORD *)(a3 + 24);
      Default = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
      WPP_RECORDER_SF_iiD(Default, v10, v11, 10, (__int64)WPP_b606bc35c7ef35d872dd65732ef04e06_Traceguids, a3, v8, v6);
    }
    v12 = 0;
    v18 = 0;
  }
  else
  {
    v12 = v18;
  }
  v13 = IssueCommandSS((_QWORD *)a2, a3, v5, v12);
  if ( v13 != -1073741670 )
  {
LABEL_15:
    if ( v13 >= 0 )
      return (unsigned int)v13;
    goto LABEL_16;
  }
  if ( *(_DWORD *)(a3 + 16) <= 0x1000u && *(_BYTE *)(a2 + 988) )
  {
    QueueCancel(a2);
    v13 = IssueCommandSS((_QWORD *)a2, a3, v5, v18);
    goto LABEL_15;
  }
LABEL_16:
  if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v14 = *(_BYTE *)(a3 + 3);
    v15 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
    LOBYTE(v16) = 4;
    WPP_RECORDER_SF_iD(v15, v16, 5, 11, (__int64)WPP_b606bc35c7ef35d872dd65732ef04e06_Traceguids, a3, v14);
  }
  StorPortNotification(0, a2, a3);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14000c368  push    rbx
0x14000c36a  push    rbp
0x14000c36b  push    rsi
0x14000c36c  push    rdi
0x14000c36d  push    r13
0x14000c36f  push    r14
0x14000c371  push    r15
0x14000c373  sub     rsp, 60h
0x14000c377  mov     rax, cs:__security_cookie
0x14000c37e  xor     rax, rsp
0x14000c381  mov     [rsp+98h+var_40], rax
0x14000c386  mov     rsi, rdx
0x14000c389  mov     [rsp+98h+var_58], 0
0x14000c392  mov     rdx, rcx
0x14000c395  lea     r9, [rsp+98h+var_50]
0x14000c39a  xorps   xmm0, xmm0
0x14000c39d  mov     ecx, 28h ; '('
0x14000c3a2  mov     rdi, r8
0x14000c3a5  movups  [rsp+98h+var_50], xmm0
0x14000c3aa  call    cs:__imp_StorPortExtendedFunction
0x14000c3b1  nop     dword ptr [rax+rax+00h]
0x14000c3b6  xor     ecx, ecx
0x14000c3b8  lea     r14, [rsp+98h+var_50]
0x14000c3bd  test    eax, eax
0x14000c3bf  lea     r13, WPP_RECORDER_INITIALIZED
0x14000c3c6  mov     eax, [rdi+0Ch]
0x14000c3c9  lea     r15, WPP_b606bc35c7ef35d872dd65732ef04e06_Traceguids
0x14000c3d0  cmovnz  r14, rcx
0x14000c3d4  test    al, 0C0h
0x14000c3d6  jz      loc_14000C46F
0x14000c3dc  mov     ebp, 0C1000001h
0x14000c3e1  cmp     [rdi+30h], rcx
0x14000c3e5  jz      short loc_14000C409
0x14000c3e7  lea     r9, [rsp+98h+var_58]
0x14000c3ec  mov     r8, rdi
0x14000c3ef  mov     rdx, rsi
0x14000c3f2  mov     ecx, 6
0x14000c3f7  call    cs:__imp_StorPortExtendedFunction
0x14000c3fe  nop     dword ptr [rax+rax+00h]
0x14000c403  mov     ebp, eax
0x14000c405  test    eax, eax
0x14000c407  jz      short loc_14000C46F
0x14000c409  cmp     cs:gTracingEnabled, 0
0x14000c410  jz      short loc_14000C465
0x14000c412  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14000c419  jz      short loc_14000C465
0x14000c41b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c422  mov     r15d, 0Ah
0x14000c428  mov     rbx, [rdi+18h]
0x14000c42c  call    cs:__imp_imp_WppRecorderLogGetDefault
0x14000c433  nop     dword ptr [rax+rax+00h]
0x14000c438  mov     [rsp+98h+var_60], ebp
0x14000c43c  movzx   r9d, r15w
0x14000c440  mov     rcx, rax
0x14000c443  mov     [rsp+98h+var_68], rbx
0x14000c448  lea     rax, WPP_b606bc35c7ef35d872dd65732ef04e06_Traceguids
0x14000c44f  mov     [rsp+98h+var_70], rdi
0x14000c454  mov     [rsp+98h+var_78], rax
0x14000c459  call    WPP_RECORDER_SF_iiD
0x14000c45e  lea     r15, WPP_b606bc35c7ef35d872dd65732ef04e06_Traceguids
0x14000c465  xor     r9d, r9d
0x14000c468  mov     [rsp+98h+var_58], r9
0x14000c46d  jmp     short loc_14000C474
0x14000c46f  mov     r9, [rsp+98h+var_58]
0x14000c474  mov     r8, r14
0x14000c477  mov     byte ptr [rsp+98h+var_70], 0
0x14000c47c  mov     rdx, rdi
0x14000c47f  mov     rcx, rsi
0x14000c482  call    IssueCommandSS
0x14000c487  mov     ebp, eax
0x14000c489  cmp     eax, 0C000009Ah
0x14000c48e  jnz     short loc_14000C4C4
0x14000c490  cmp     dword ptr [rdi+10h], 1000h
0x14000c497  ja      short loc_14000C4C8
0x14000c499  cmp     byte ptr [rsi+3DCh], 0
0x14000c4a0  jz      short loc_14000C4C8
0x14000c4a2  mov     rcx, rsi
0x14000c4a5  call    QueueCancel
0x14000c4aa  mov     r9, [rsp+98h+var_58]
0x14000c4af  mov     r8, r14
0x14000c4b2  mov     rdx, rdi
0x14000c4b5  mov     byte ptr [rsp+98h+var_70], 1
0x14000c4ba  mov     rcx, rsi
0x14000c4bd  call    IssueCommandSS
0x14000c4c2  mov     ebp, eax
0x14000c4c4  test    ebp, ebp
0x14000c4c6  jns     short loc_14000C52B
0x14000c4c8  cmp     cs:gTracingEnabled, 0
0x14000c4cf  jz      short loc_14000C517
0x14000c4d1  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14000c4d8  jz      short loc_14000C517
0x14000c4da  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c4e1  mov     r14d, 0Bh
0x14000c4e7  movzx   ebx, byte ptr [rdi+3]
0x14000c4eb  call    cs:__imp_imp_WppRecorderLogGetDefault
0x14000c4f2  nop     dword ptr [rax+rax+00h]
0x14000c4f7  mov     dword ptr [rsp+98h+var_68], ebx
0x14000c4fb  lea     r8d, [r14-6]
0x14000c4ff  mov     rcx, rax
0x14000c502  mov     [rsp+98h+var_70], rdi
0x14000c507  movzx   r9d, r14w
0x14000c50b  mov     [rsp+98h+var_78], r15
0x14000c510  mov     dl, 4
0x14000c512  call    WPP_RECORDER_SF_iD
0x14000c517  mov     r8, rdi
0x14000c51a  mov     rdx, rsi
0x14000c51d  xor     ecx, ecx
0x14000c51f  call    cs:__imp_StorPortNotification
0x14000c526  nop     dword ptr [rax+rax+00h]
0x14000c52b  mov     eax, ebp
0x14000c52d  mov     rcx, [rsp+98h+var_40]
0x14000c532  xor     rcx, rsp; StackCookie
0x14000c535  call    __security_check_cookie
0x14000c53a  add     rsp, 60h
0x14000c53e  pop     r15
0x14000c540  pop     r14
0x14000c542  pop     r13
0x14000c544  pop     rdi
0x14000c545  pop     rsi
0x14000c546  pop     rbp
0x14000c547  pop     rbx
0x14000c548  retn
```
