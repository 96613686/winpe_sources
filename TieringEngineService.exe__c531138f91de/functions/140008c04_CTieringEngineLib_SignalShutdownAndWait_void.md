# CTieringEngineLib::SignalShutdownAndWait(void)

- ea: `0x140008c04`
- end: `0x140008dfb`
- name: `?SignalShutdownAndWait@CTieringEngineLib@@QEAAXXZ`
- size: `503`
- prototype: `void __fastcall(CTieringEngineLib *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140003e38`
- `0x1400046d4`

## callees

- `0x14000108c`
- `0x140004a40`
- `0x140008c04`
- `0x140009f1c`
- `0x14003fbb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140008c9e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140008c9e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x140008d0a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x140008d0a`

## pseudocode

```c
void __fastcall CTieringEngineLib::SignalShutdownAndWait(CTieringEngineLib *this)
{
  PVOID v1; // rbx
  _QWORD *v2; // rcx
  int v3; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v4[32]; // [rsp+38h] [rbp-40h] BYREF
  int *v5; // [rsp+58h] [rbp-20h]
  __int64 v6; // [rsp+60h] [rbp-18h]

  v1 = TieringEngineLibInstance;
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      27,
      &WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids,
      TieringEngineLibInstance);
    v2 = WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)v1 + 26) )
  {
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 4u )
      WPP_SF_(v2[2], 28, &WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids);
    SetEvent(*((HANDLE *)v1 + 26));
    goto LABEL_15;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 4u )
  {
    WPP_SF_(v2[2], 29, &WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids);
LABEL_15:
    v2 = WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)v1 + 51) )
  {
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 4u )
      WPP_SF_q(v2[2], 30, &WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids, v1);
    WaitForThreadpoolWaitCallbacks(*((PTP_WAIT *)v1 + 51), 1);
    goto LABEL_26;
  }
  if ( v2 == &WPP_GLOBAL_Control )
    goto LABEL_31;
  if ( (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 4u )
  {
    WPP_SF_(v2[2], 31, &WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids);
LABEL_26:
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 4u )
    WPP_SF_q(v2[2], 32, &WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids, v1);
LABEL_31:
  if ( (unsigned int)dword_14004C098 > 5
    && (qword_14004C0A8 & 0x200000000000LL) != 0
    && (qword_14004C0B0 & 0x200000000000LL) == qword_14004C0B0 )
  {
    v3 = *((_DWORD *)v1 + 34);
    v6 = 4;
    v5 = &v3;
    tlgWriteTransfer_EventWriteTransfer(&dword_14004C098, word_140045C4A, 0, 0, 3, v4);
  }
}

```

## disassembly

```asm
0x140008c04  mov     [rsp+arg_0], rbx
0x140008c09  mov     [rsp+arg_8], rbp
0x140008c0e  push    r14
0x140008c10  sub     rsp, 70h
0x140008c14  mov     rax, cs:__security_cookie
0x140008c1b  xor     rax, rsp
0x140008c1e  mov     [rsp+78h+var_10], rax
0x140008c23  mov     rbx, cs:?TieringEngineLibInstance@@3PEAVCTieringEngineLib@@EA; CTieringEngineLib * TieringEngineLibInstance
0x140008c2a  mov     rcx, cs:WPP_GLOBAL_Control
0x140008c31  lea     rbp, WPP_GLOBAL_Control
0x140008c38  lea     r14, WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids
0x140008c3f  cmp     rcx, rbp
0x140008c42  jz      short loc_140008C6B
0x140008c44  test    byte ptr [rcx+1Ch], 1
0x140008c48  jz      short loc_140008C6B
0x140008c4a  cmp     byte ptr [rcx+19h], 4
0x140008c4e  jb      short loc_140008C6B
0x140008c50  mov     rcx, [rcx+10h]
0x140008c54  mov     edx, 1Bh
0x140008c59  mov     r9, rbx
0x140008c5c  mov     r8, r14
0x140008c5f  call    WPP_SF_q
0x140008c64  mov     rcx, cs:WPP_GLOBAL_Control
0x140008c6b  cmp     qword ptr [rbx+0D0h], 0
0x140008c73  jz      short loc_140008CA6
0x140008c75  cmp     rcx, rbp
0x140008c78  jz      short loc_140008C97
0x140008c7a  test    byte ptr [rcx+1Ch], 1
0x140008c7e  jz      short loc_140008C97
0x140008c80  cmp     byte ptr [rcx+19h], 4
0x140008c84  jb      short loc_140008C97
0x140008c86  mov     rcx, [rcx+10h]
0x140008c8a  mov     edx, 1Ch
0x140008c8f  mov     r8, r14
0x140008c92  call    WPP_SF_
0x140008c97  mov     rcx, [rbx+0D0h]; hEvent
0x140008c9e  call    cs:__imp_SetEvent
0x140008ca4  jmp     short loc_140008CC8
0x140008ca6  cmp     rcx, rbp
0x140008ca9  jz      short loc_140008CCF
0x140008cab  test    byte ptr [rcx+1Ch], 1
0x140008caf  jz      short loc_140008CCF
0x140008cb1  cmp     byte ptr [rcx+19h], 4
0x140008cb5  jb      short loc_140008CCF
0x140008cb7  mov     rcx, [rcx+10h]
0x140008cbb  mov     edx, 1Dh
0x140008cc0  mov     r8, r14
0x140008cc3  call    WPP_SF_
0x140008cc8  mov     rcx, cs:WPP_GLOBAL_Control
0x140008ccf  cmp     qword ptr [rbx+198h], 0
0x140008cd7  jz      short loc_140008D12
0x140008cd9  cmp     rcx, rbp
0x140008cdc  jz      short loc_140008CFE
0x140008cde  test    byte ptr [rcx+1Ch], 1
0x140008ce2  jz      short loc_140008CFE
0x140008ce4  cmp     byte ptr [rcx+19h], 4
0x140008ce8  jb      short loc_140008CFE
0x140008cea  mov     rcx, [rcx+10h]
0x140008cee  mov     edx, 1Eh
0x140008cf3  mov     r9, rbx
0x140008cf6  mov     r8, r14
0x140008cf9  call    WPP_SF_q
0x140008cfe  mov     rcx, [rbx+198h]; pwa
0x140008d05  mov     edx, 1; fCancelPendingCallbacks
0x140008d0a  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x140008d10  jmp     short loc_140008D34
0x140008d12  cmp     rcx, rbp
0x140008d15  jz      short loc_140008D60
0x140008d17  test    byte ptr [rcx+1Ch], 1
0x140008d1b  jz      short loc_140008D3B
0x140008d1d  cmp     byte ptr [rcx+19h], 4
0x140008d21  jb      short loc_140008D3B
0x140008d23  mov     rcx, [rcx+10h]
0x140008d27  mov     edx, 1Fh
0x140008d2c  mov     r8, r14
0x140008d2f  call    WPP_SF_
0x140008d34  mov     rcx, cs:WPP_GLOBAL_Control
0x140008d3b  cmp     rcx, rbp
0x140008d3e  jz      short loc_140008D60
0x140008d40  test    byte ptr [rcx+1Ch], 1
0x140008d44  jz      short loc_140008D60
0x140008d46  cmp     byte ptr [rcx+19h], 4
0x140008d4a  jb      short loc_140008D60
0x140008d4c  mov     rcx, [rcx+10h]
0x140008d50  mov     edx, 20h ; ' '
0x140008d55  mov     r9, rbx
0x140008d58  mov     r8, r14
0x140008d5b  call    WPP_SF_q
0x140008d60  mov     eax, cs:dword_14004C098
0x140008d66  cmp     eax, 5
0x140008d69  jbe     short loc_140008DDB
0x140008d6b  mov     rcx, cs:qword_14004C0B0
0x140008d72  mov     rdx, 200000000000h
0x140008d7c  mov     rax, cs:qword_14004C0A8
0x140008d83  test    rdx, rax
0x140008d86  jz      short loc_140008DDB
0x140008d88  mov     rax, rcx
0x140008d8b  and     rax, rdx
0x140008d8e  cmp     rax, rcx
0x140008d91  jnz     short loc_140008DDB
0x140008d93  mov     eax, [rbx+88h]
0x140008d99  lea     rdx, word_140045C4A
0x140008da0  mov     [rsp+78h+var_48], eax
0x140008da4  lea     rcx, dword_14004C098
0x140008dab  lea     rax, [rsp+78h+var_48]
0x140008db0  mov     [rsp+78h+var_18], 4
0x140008db9  mov     [rsp+78h+var_20], rax
0x140008dbe  xor     r9d, r9d
0x140008dc1  lea     rax, [rsp+78h+var_40]
0x140008dc6  xor     r8d, r8d
0x140008dc9  mov     [rsp+78h+var_50], rax
0x140008dce  mov     [rsp+78h+var_58], 3
0x140008dd6  call    _tlgWriteTransfer_EventWriteTransfer
0x140008ddb  mov     rcx, [rsp+78h+var_10]
0x140008de0  xor     rcx, rsp; StackCookie
0x140008de3  call    __security_check_cookie
0x140008de8  lea     r11, [rsp+78h+var_8]
0x140008ded  mov     rbx, [r11+10h]
0x140008df1  mov     rbp, [r11+18h]
0x140008df5  mov     rsp, r11
0x140008df8  pop     r14
0x140008dfa  retn
```
