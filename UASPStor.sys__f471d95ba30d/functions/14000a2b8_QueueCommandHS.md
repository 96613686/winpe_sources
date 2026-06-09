# QueueCommandHS

- ea: `0x14000a2b8`
- end: `0x14000a43b`
- name: `QueueCommandHS`
- size: `387`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140002320`

## callees

- `0x140009c10`
- `0x14000a2b8`
- `0x14000bd7c`
- `0x14000d7f0`

## import_xrefs

- `storport!StorPortNotification` at `0x14000a40b`
- `storport!StorPortNotification` at `0x14000a40b`
- `storport!StorPortExtendedFunction` at `0x14000a2fb`
- `storport!StorPortExtendedFunction` at `0x14000a33a`
- `storport!StorPortExtendedFunction` at `0x14000a2fb`
- `storport!StorPortExtendedFunction` at `0x14000a33a`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000a376`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000a376`

## pseudocode

```c
__int64 __fastcall QueueCommandHS(__int64 a1, __int64 a2, __int64 a3)
{
  __int128 *v5; // r14
  char v6; // bp
  int v7; // eax
  __int64 v8; // rbx
  int Default; // eax
  int v10; // edx
  int v11; // r8d
  __int64 v12; // r9
  int v13; // ebx
  __int64 v15; // [rsp+20h] [rbp-68h]
  __int64 v16; // [rsp+20h] [rbp-68h]
  __int64 v17; // [rsp+40h] [rbp-48h] BYREF
  __int128 v18; // [rsp+48h] [rbp-40h] BYREF

  v17 = 0;
  v18 = 0;
  v5 = &v18;
  if ( (unsigned int)StorPortExtendedFunction(40, a1, a3, &v18) )
    v5 = 0;
  if ( (*(_DWORD *)(a3 + 12) & 0xC0) != 0
    && ((v6 = 1, !*(_QWORD *)(a3 + 48)) || (v7 = StorPortExtendedFunction(6, a2, a3, &v17), v6 = v7, v7)) )
  {
    if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v8 = *(_QWORD *)(a3 + 24);
      Default = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
      WPP_RECORDER_SF_iiD(Default, v10, v11, 41, (__int64)WPP_32736fb5ed073acc00a38acab6f2acca_Traceguids, a3, v8, v6);
    }
    v12 = 0;
    v17 = 0;
  }
  else
  {
    v12 = v17;
  }
  v13 = IssueCommandHS((_QWORD *)a2, a3, v5, v12, v15, 0);
  if ( v13 == -1073741670 )
  {
    if ( *(_DWORD *)(a3 + 16) > 0x1000u || !*(_BYTE *)(a2 + 988) )
      goto LABEL_16;
    v13 = IssueCommandHS((_QWORD *)a2, a3, v5, v17, v16, 1);
  }
  if ( v13 < 0 )
LABEL_16:
    StorPortNotification(0, a2, a3);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14000a2b8  mov     [rsp+arg_18], rbx
0x14000a2bd  push    rbp
0x14000a2be  push    rsi
0x14000a2bf  push    rdi
0x14000a2c0  push    r14
0x14000a2c2  push    r15
0x14000a2c4  sub     rsp, 60h
0x14000a2c8  mov     rax, cs:__security_cookie
0x14000a2cf  xor     rax, rsp
0x14000a2d2  mov     [rsp+88h+var_30], rax
0x14000a2d7  mov     rsi, rdx
0x14000a2da  mov     [rsp+88h+var_48], 0
0x14000a2e3  mov     rdx, rcx
0x14000a2e6  lea     r9, [rsp+88h+var_40]
0x14000a2eb  xorps   xmm0, xmm0
0x14000a2ee  mov     ecx, 28h ; '('
0x14000a2f3  mov     rdi, r8
0x14000a2f6  movups  [rsp+88h+var_40], xmm0
0x14000a2fb  call    cs:__imp_StorPortExtendedFunction
0x14000a302  nop     dword ptr [rax+rax+00h]
0x14000a307  xor     ecx, ecx
0x14000a309  lea     r14, [rsp+88h+var_40]
0x14000a30e  test    eax, eax
0x14000a310  mov     eax, [rdi+0Ch]
0x14000a313  cmovnz  r14, rcx
0x14000a317  test    al, 0C0h
0x14000a319  jz      loc_14000A3B2
0x14000a31f  mov     ebp, 0C1000001h
0x14000a324  cmp     [rdi+30h], rcx
0x14000a328  jz      short loc_14000A34C
0x14000a32a  lea     r9, [rsp+88h+var_48]
0x14000a32f  mov     r8, rdi
0x14000a332  mov     rdx, rsi
0x14000a335  mov     ecx, 6
0x14000a33a  call    cs:__imp_StorPortExtendedFunction
0x14000a341  nop     dword ptr [rax+rax+00h]
0x14000a346  mov     ebp, eax
0x14000a348  test    eax, eax
0x14000a34a  jz      short loc_14000A3B2
0x14000a34c  cmp     cs:gTracingEnabled, 0
0x14000a353  jz      short loc_14000A3A8
0x14000a355  lea     rax, WPP_RECORDER_INITIALIZED
0x14000a35c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000a363  jz      short loc_14000A3A8
0x14000a365  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a36c  mov     r15d, 29h ; ')'
0x14000a372  mov     rbx, [rdi+18h]
0x14000a376  call    cs:__imp_imp_WppRecorderLogGetDefault
0x14000a37d  nop     dword ptr [rax+rax+00h]
0x14000a382  mov     [rsp+88h+var_50], ebp
0x14000a386  movzx   r9d, r15w
0x14000a38a  mov     rcx, rax
0x14000a38d  mov     [rsp+88h+var_58], rbx
0x14000a392  lea     rax, WPP_32736fb5ed073acc00a38acab6f2acca_Traceguids
0x14000a399  mov     [rsp+88h+var_60], rdi
0x14000a39e  mov     [rsp+88h+var_68], rax
0x14000a3a3  call    WPP_RECORDER_SF_iiD
0x14000a3a8  xor     r9d, r9d
0x14000a3ab  mov     [rsp+88h+var_48], r9
0x14000a3b0  jmp     short loc_14000A3B7
0x14000a3b2  mov     r9, [rsp+88h+var_48]
0x14000a3b7  mov     r8, r14
0x14000a3ba  mov     byte ptr [rsp+88h+var_60], 0
0x14000a3bf  mov     rdx, rdi
0x14000a3c2  mov     rcx, rsi
0x14000a3c5  call    IssueCommandHS
0x14000a3ca  mov     ebx, eax
0x14000a3cc  cmp     eax, 0C000009Ah
0x14000a3d1  jnz     short loc_14000A3FF
0x14000a3d3  cmp     dword ptr [rdi+10h], 1000h
0x14000a3da  ja      short loc_14000A403
0x14000a3dc  cmp     byte ptr [rsi+3DCh], 0
0x14000a3e3  jz      short loc_14000A403
0x14000a3e5  mov     r9, [rsp+88h+var_48]
0x14000a3ea  mov     r8, r14
0x14000a3ed  mov     rdx, rdi
0x14000a3f0  mov     byte ptr [rsp+88h+var_60], 1
0x14000a3f5  mov     rcx, rsi
0x14000a3f8  call    IssueCommandHS
0x14000a3fd  mov     ebx, eax
0x14000a3ff  test    ebx, ebx
0x14000a401  jns     short loc_14000A417
0x14000a403  mov     r8, rdi
0x14000a406  mov     rdx, rsi
0x14000a409  xor     ecx, ecx
0x14000a40b  call    cs:__imp_StorPortNotification
0x14000a412  nop     dword ptr [rax+rax+00h]
0x14000a417  mov     eax, ebx
0x14000a419  mov     rcx, [rsp+88h+var_30]
0x14000a41e  xor     rcx, rsp; StackCookie
0x14000a421  call    __security_check_cookie
0x14000a426  mov     rbx, [rsp+88h+arg_18]
0x14000a42e  add     rsp, 60h
0x14000a432  pop     r15
0x14000a434  pop     r14
0x14000a436  pop     rdi
0x14000a437  pop     rsi
0x14000a438  pop     rbp
0x14000a439  retn
```
