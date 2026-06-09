# BthServHandleRefreshBrServicesEvent(unsigned __int64 const &)

- ea: `0x18000c21c`
- end: `0x18000c3f3`
- name: `?BthServHandleRefreshBrServicesEvent@@YAXAEB_K@Z`
- size: `471`
- prototype: `void __fastcall(const unsigned __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000d5b0`

## callees

- `0x180001b9c`
- `0x18000c21c`
- `0x1800110fc`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000c2cc`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000c2cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c387`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c387`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c2a3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c2a3`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000c32a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000c32a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall BthServHandleRefreshBrServicesEvent(const unsigned __int64 *a1)
{
  char v2; // di
  bool v3; // dl
  PSRWLOCK v4; // rsi
  __int64 v5; // rbp
  _QWORD *Ptr; // rbx
  _QWORD *v7; // rax
  _QWORD *v8; // rcx
  bool v9; // dl

  v2 = 1;
  v3 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v3,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  v4 = qword_180044BC0;
  v5 = *a1;
  AcquireSRWLockExclusive(qword_180044BC0);
  if ( v4[3].Ptr == (PVOID)0x7FFFFFFFFFFFFFFLL )
    std::_Xlength_error("list too long");
  Ptr = v4[2].Ptr;
  v7 = operator new(0x20u);
  v7[3] = v5 & 0xFFFFFFFFFFFFLL;
  v7[2] = &Microsoft::Bluetooth::BluetoothBRAddress::`vftable';
  ++v4[3].Ptr;
  v8 = (_QWORD *)Ptr[1];
  *v7 = Ptr;
  v7[1] = v8;
  Ptr[1] = v7;
  *v8 = v7;
  if ( LOBYTE(v4[1].Ptr) )
  {
    v9 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
    if ( v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v9,
        WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
        *((_QWORD *)WPP_GLOBAL_Control + 5));
  }
  else
  {
    SubmitThreadpoolWork((PTP_WORK)v4[4].Ptr);
    LOBYTE(v4[1].Ptr) = 1;
  }
  ReleaseSRWLockExclusive(v4);
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
    v2 = 0;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
}

```

## disassembly

```asm
0x18000c21c  mov     [rsp+arg_8], rbx
0x18000c221  mov     [rsp+arg_10], rbp
0x18000c226  push    rsi
0x18000c227  push    rdi
0x18000c228  push    r12
0x18000c22a  push    r13
0x18000c22c  push    r14
0x18000c22e  sub     rsp, 60h
0x18000c232  mov     rbp, rcx
0x18000c235  lea     r12, WPP_GLOBAL_Control
0x18000c23c  mov     edi, 1
0x18000c241  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c248  cmp     rcx, r12
0x18000c24b  jz      short loc_18000C258
0x18000c24d  cmp     byte ptr [rcx+19h], 5
0x18000c251  jb      short loc_18000C258
0x18000c253  mov     dl, dil
0x18000c256  jmp     short loc_18000C25A
0x18000c258  xor     dl, dl
0x18000c25a  lea     r13, WPP_RECORDER_INITIALIZED
0x18000c261  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18000c268  setnz   r8b
0x18000c26c  lea     r9, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x18000c273  test    dl, dl
0x18000c275  jnz     short loc_18000C27C
0x18000c277  test    r8b, r8b
0x18000c27a  jz      short loc_18000C295
0x18000c27c  mov     [rsp+88h+var_50], r9
0x18000c281  mov     [rsp+88h+var_58], 7Eh ; '~'
0x18000c288  mov     r9, [rcx+28h]
0x18000c28c  mov     rcx, [rcx+10h]
0x18000c290  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000c295  mov     rsi, cs:qword_180044BC0
0x18000c29c  mov     rbp, [rbp+0]
0x18000c2a0  mov     rcx, rsi; SRWLock
0x18000c2a3  call    cs:__imp_AcquireSRWLockExclusive
0x18000c2a9  mov     [rsp+88h+arg_0], rsi
0x18000c2b1  lea     r14, [rsi+10h]
0x18000c2b5  mov     rax, 7FFFFFFFFFFFFFFh
0x18000c2bf  cmp     [r14+8], rax
0x18000c2c3  jnz     short loc_18000C2D3
0x18000c2c5  lea     rcx, aListTooLong; "list too long"
0x18000c2cc  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000c2d3  mov     rax, 0FFFFFFFFFFFFh
0x18000c2dd  and     rbp, rax
0x18000c2e0  mov     rbx, [r14]
0x18000c2e3  mov     [rsp+88h+var_38], r14
0x18000c2e8  mov     [rsp+88h+var_30], 0
0x18000c2f1  mov     ecx, 20h ; ' '; Size
0x18000c2f6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c2fb  mov     [rax+18h], rbp
0x18000c2ff  lea     rcx, ??_7BluetoothBRAddress@Bluetooth@Microsoft@@6B@; const Microsoft::Bluetooth::BluetoothBRAddress::`vftable'
0x18000c306  mov     [rax+10h], rcx
0x18000c30a  add     [r14+8], rdi
0x18000c30e  mov     rcx, [rbx+8]
0x18000c312  mov     [rax], rbx
0x18000c315  mov     [rax+8], rcx
0x18000c319  mov     [rbx+8], rax
0x18000c31d  mov     [rcx], rax
0x18000c320  cmp     byte ptr [rsi+8], 0
0x18000c324  jnz     short loc_18000C336
0x18000c326  mov     rcx, [rsi+20h]; pwk
0x18000c32a  call    cs:__imp_SubmitThreadpoolWork
0x18000c330  mov     [rsi+8], dil
0x18000c334  jmp     short loc_18000C384
0x18000c336  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c33d  cmp     rcx, r12
0x18000c340  jz      short loc_18000C34D
0x18000c342  cmp     byte ptr [rcx+19h], 5
0x18000c346  jb      short loc_18000C34D
0x18000c348  mov     dl, dil
0x18000c34b  jmp     short loc_18000C34F
0x18000c34d  xor     dl, dl
0x18000c34f  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18000c356  setnz   r8b
0x18000c35a  test    dl, dl
0x18000c35c  jnz     short loc_18000C363
0x18000c35e  test    r8b, r8b
0x18000c361  jz      short loc_18000C384
0x18000c363  lea     rax, WPP_21eeecb372ac35bdc1c1ea9e0d2ef949_Traceguids
0x18000c36a  mov     [rsp+88h+var_50], rax
0x18000c36f  mov     [rsp+88h+var_58], 0Ah
0x18000c376  mov     r9, [rcx+28h]
0x18000c37a  mov     rcx, [rcx+10h]
0x18000c37e  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000c383  nop
0x18000c384  mov     rcx, rsi; SRWLock
0x18000c387  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c38d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c394  cmp     rcx, r12
0x18000c397  jz      short loc_18000C39F
0x18000c399  cmp     byte ptr [rcx+19h], 5
0x18000c39d  jnb     short loc_18000C3A2
0x18000c39f  xor     dil, dil
0x18000c3a2  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18000c3a9  setnz   r8b
0x18000c3ad  test    dil, dil
0x18000c3b0  jnz     short loc_18000C3B7
0x18000c3b2  test    r8b, r8b
0x18000c3b5  jz      short loc_18000C3DA
0x18000c3b7  lea     rdx, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x18000c3be  mov     [rsp+88h+var_50], rdx
0x18000c3c3  mov     [rsp+88h+var_58], 7Fh
0x18000c3ca  mov     r9, [rcx+28h]
0x18000c3ce  mov     dl, dil
0x18000c3d1  mov     rcx, [rcx+10h]
0x18000c3d5  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000c3da  lea     r11, [rsp+88h+var_28]
0x18000c3df  mov     rbx, [r11+38h]
0x18000c3e3  mov     rbp, [r11+40h]
0x18000c3e7  mov     rsp, r11
0x18000c3ea  pop     r14
0x18000c3ec  pop     r13
0x18000c3ee  pop     r12
0x18000c3f0  pop     rdi
0x18000c3f1  pop     rsi
0x18000c3f2  retn
```
