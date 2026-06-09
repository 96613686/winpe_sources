# IssueDataTransferRequest

- ea: `0x140009fe0`
- end: `0x14000a227`
- name: `IssueDataTransferRequest`
- size: `583`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000a450`

## callees

- `0x140001020`
- `0x140004adc`
- `0x140009fe0`
- `0x14000bd7c`

## import_xrefs

- `storport!StorPortExtendedFunction` at `0x14000a08c`
- `storport!StorPortExtendedFunction` at `0x14000a08c`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000a0c6`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000a182`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000a1e0`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000a0c6`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000a182`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x14000a1e0`

## pseudocode

```c
__int64 __fastcall IssueDataTransferRequest(__int64 a1)
{
  __int64 v1; // rdi
  __int64 v3; // rcx
  int v4; // eax
  int v5; // r13d
  __int64 *v6; // rbx
  __int64 v7; // r12
  bool v8; // cf
  int v9; // r15d
  __int64 v10; // rbx
  int Default; // eax
  int v12; // edx
  int v13; // r8d
  unsigned int v14; // edi
  unsigned __int16 v15; // r9
  int v16; // edi
  __int64 v17; // rbx
  __int64 v18; // rax
  __int64 v19; // rbx
  __int64 v20; // rax
  __int64 v22; // [rsp+30h] [rbp-58h]
  __int64 v23; // [rsp+30h] [rbp-58h]
  int v24; // [rsp+90h] [rbp+8h]
  __int64 v25; // [rsp+98h] [rbp+10h] BYREF

  v1 = *(_QWORD *)(a1 + 32);
  v3 = 0;
  v25 = 0;
  v4 = *(_DWORD *)(v1 + 12) & 0xC0;
  if ( v4 )
  {
    if ( v4 == 64 )
    {
      v5 = 3;
      goto LABEL_6;
    }
    if ( v4 == 128 )
    {
      v5 = 0;
LABEL_6:
      v6 = (__int64 *)(a1 + 160);
      v7 = *(_QWORD *)a1;
      v8 = *(_BYTE *)(a1 + 201) != 0;
      *(_DWORD *)(a1 + 12) = 2;
      v9 = v8 ? 0x10 : 0;
      if ( !*(_QWORD *)(v7 + 8) )
      {
        v3 = *(_QWORD *)(v1 + 24);
        v25 = v3;
        goto LABEL_15;
      }
      if ( !*v6 )
      {
        v24 = StorPortExtendedFunction(5, v7, v1, &v25);
        if ( v24 )
        {
          if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v10 = *(_QWORD *)(v1 + 24);
            Default = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
            WPP_RECORDER_SF_iiD(
              Default,
              v12,
              v13,
              10,
              (__int64)WPP_32736fb5ed073acc00a38acab6f2acca_Traceguids,
              v1,
              v10,
              v24);
          }
          *(_BYTE *)(v1 + 3) = 4;
          v14 = -1073741670;
          goto LABEL_21;
        }
        v3 = v25;
      }
LABEL_15:
      v15 = *(_WORD *)(a1 + 40);
      *(_DWORD *)(a1 + 12) = 2;
      v16 = IssueBulkRequest(
              v7,
              a1,
              2,
              v15,
              v3,
              *v6,
              *(_DWORD *)(v1 + 16),
              v5 | (unsigned int)v9,
              (__int64)DataCompletion);
      if ( v16 < 0 && gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v17 = *(_QWORD *)(a1 + 32);
        v18 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
        LODWORD(v23) = v16;
        WPP_RECORDER_SF_iD(v18, 2u, 1u, 0xBu, (__int64)WPP_32736fb5ed073acc00a38acab6f2acca_Traceguids, v17, v23);
      }
      return 0;
    }
  }
  v14 = -1073741811;
LABEL_21:
  if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v19 = *(_QWORD *)(a1 + 32);
    v20 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
    LODWORD(v22) = v14;
    WPP_RECORDER_SF_iD(v20, 2u, 1u, 0xCu, (__int64)WPP_32736fb5ed073acc00a38acab6f2acca_Traceguids, v19, v22);
  }
  return v14;
}

```

## disassembly

```asm
0x140009fe0  mov     rax, rsp
0x140009fe3  mov     [rax+18h], rbx
0x140009fe7  push    rbp
0x140009fe8  push    rsi
0x140009fe9  push    rdi
0x140009fea  push    r12
0x140009fec  push    r13
0x140009fee  push    r14
0x140009ff0  push    r15
0x140009ff2  sub     rsp, 50h
0x140009ff6  mov     rdi, [rcx+20h]
0x140009ffa  lea     rbp, WPP_RECORDER_INITIALIZED
0x14000a001  mov     rsi, rcx
0x14000a004  lea     r14, WPP_32736fb5ed073acc00a38acab6f2acca_Traceguids
0x14000a00b  xor     ecx, ecx
0x14000a00d  mov     [rax+10h], rcx
0x14000a011  mov     eax, [rdi+0Ch]
0x14000a014  and     eax, 0C0h
0x14000a019  jz      loc_14000A1B9
0x14000a01f  cmp     eax, 40h ; '@'
0x14000a022  jnz     short loc_14000A02A
0x14000a024  lea     r13d, [rcx+3]
0x14000a028  jmp     short loc_14000A038
0x14000a02a  cmp     eax, 80h
0x14000a02f  jnz     loc_14000A1B9
0x14000a035  xor     r13d, r13d
0x14000a038  mov     al, [rsi+0C9h]
0x14000a03e  lea     rbx, [rsi+0A0h]
0x14000a045  mov     r12, [rsi]
0x14000a048  neg     al
0x14000a04a  mov     dword ptr [rsi+0Ch], 2
0x14000a051  sbb     r15d, r15d
0x14000a054  and     r15d, 10h
0x14000a058  cmp     [r12+8], rcx
0x14000a05d  jnz     short loc_14000A070
0x14000a05f  mov     rcx, [rdi+18h]
0x14000a063  mov     [rsp+88h+arg_8], rcx
0x14000a06b  jmp     loc_14000A10E
0x14000a070  cmp     [rbx], rcx
0x14000a073  jnz     loc_14000A10E
0x14000a079  lea     r9, [rsp+88h+arg_8]
0x14000a081  mov     r8, rdi
0x14000a084  mov     rdx, r12
0x14000a087  mov     ecx, 5
0x14000a08c  call    cs:__imp_StorPortExtendedFunction
0x14000a093  nop     dword ptr [rax+rax+00h]
0x14000a098  mov     [rsp+88h+arg_0], eax
0x14000a09f  test    eax, eax
0x14000a0a1  jz      short loc_14000A106
0x14000a0a3  cmp     cs:gTracingEnabled, 0
0x14000a0aa  jz      short loc_14000A0F8
0x14000a0ac  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000a0b3  jz      short loc_14000A0F8
0x14000a0b5  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a0bc  mov     r15d, 0Ah
0x14000a0c2  mov     rbx, [rdi+18h]
0x14000a0c6  call    cs:__imp_imp_WppRecorderLogGetDefault
0x14000a0cd  nop     dword ptr [rax+rax+00h]
0x14000a0d2  mov     rcx, rax
0x14000a0d5  movzx   r9d, r15w
0x14000a0d9  mov     eax, [rsp+88h+arg_0]
0x14000a0e0  mov     [rsp+88h+var_50], eax
0x14000a0e4  mov     [rsp+88h+var_58], rbx
0x14000a0e9  mov     [rsp+88h+var_60], rdi
0x14000a0ee  mov     [rsp+88h+var_68], r14
0x14000a0f3  call    WPP_RECORDER_SF_iiD
0x14000a0f8  mov     byte ptr [rdi+3], 4
0x14000a0fc  mov     edi, 0C000009Ah
0x14000a101  jmp     loc_14000A1BE
0x14000a106  mov     rcx, [rsp+88h+arg_8]
0x14000a10e  movzx   r9d, word ptr [rsi+28h]
0x14000a113  lea     rax, DataCompletion
0x14000a11a  mov     [rsp+88h+var_48], rax
0x14000a11f  or      r15d, r13d
0x14000a122  mov     [rsp+88h+var_50], r15d
0x14000a127  mov     r8d, 2
0x14000a12d  mov     dword ptr [rsi+0Ch], 2
0x14000a134  mov     rdx, rsi
0x14000a137  mov     eax, [rdi+10h]
0x14000a13a  mov     dword ptr [rsp+88h+var_58], eax
0x14000a13e  mov     rax, [rbx]
0x14000a141  mov     [rsp+88h+var_60], rax
0x14000a146  mov     [rsp+88h+var_68], rcx
0x14000a14b  mov     rcx, r12
0x14000a14e  call    IssueBulkRequest
0x14000a153  mov     edi, eax
0x14000a155  test    eax, eax
0x14000a157  jns     short loc_14000A1B5
0x14000a159  cmp     cs:gTracingEnabled, 0
0x14000a160  jz      short loc_14000A1B5
0x14000a162  lea     rbp, WPP_RECORDER_INITIALIZED
0x14000a169  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000a170  jz      short loc_14000A1B5
0x14000a172  mov     rbx, [rsi+20h]
0x14000a176  mov     esi, 0Bh
0x14000a17b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a182  call    cs:__imp_imp_WppRecorderLogGetDefault
0x14000a189  nop     dword ptr [rax+rax+00h]
0x14000a18e  mov     dword ptr [rsp+88h+var_58], edi
0x14000a192  lea     r14, WPP_32736fb5ed073acc00a38acab6f2acca_Traceguids
0x14000a199  mov     rcx, rax
0x14000a19c  mov     [rsp+88h+var_60], rbx
0x14000a1a1  movzx   r9d, si
0x14000a1a5  mov     [rsp+88h+var_68], r14
0x14000a1aa  lea     r8d, [rsi-0Ah]
0x14000a1ae  mov     dl, 2
0x14000a1b0  call    WPP_RECORDER_SF_iD
0x14000a1b5  xor     edi, edi
0x14000a1b7  jmp     short loc_14000A20C
0x14000a1b9  mov     edi, 0C000000Dh
0x14000a1be  cmp     cs:gTracingEnabled, 0
0x14000a1c5  jz      short loc_14000A20C
0x14000a1c7  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000a1ce  jz      short loc_14000A20C
0x14000a1d0  mov     rbx, [rsi+20h]
0x14000a1d4  mov     esi, 0Ch
0x14000a1d9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a1e0  call    cs:__imp_imp_WppRecorderLogGetDefault
0x14000a1e7  nop     dword ptr [rax+rax+00h]
0x14000a1ec  mov     dword ptr [rsp+88h+var_58], edi
0x14000a1f0  lea     r8d, [rsi-0Bh]
0x14000a1f4  mov     rcx, rax
0x14000a1f7  mov     [rsp+88h+var_60], rbx
0x14000a1fc  movzx   r9d, si
0x14000a200  mov     [rsp+88h+var_68], r14
0x14000a205  mov     dl, 2
0x14000a207  call    WPP_RECORDER_SF_iD
0x14000a20c  mov     rbx, [rsp+88h+arg_10]
0x14000a214  mov     eax, edi
0x14000a216  add     rsp, 50h
0x14000a21a  pop     r15
0x14000a21c  pop     r14
0x14000a21e  pop     r13
0x14000a220  pop     r12
0x14000a222  pop     rdi
0x14000a223  pop     rsi
0x14000a224  pop     rbp
0x14000a225  retn
```
