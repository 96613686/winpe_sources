# Endpoint_ControlEndpointResetCompletion

- ea: `0x140023f70`
- end: `0x1400241a8`
- name: `Endpoint_ControlEndpointResetCompletion`
- size: `568`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x140002568`
- `0x140005d48`
- `0x14000c264`
- `0x1400216b8`
- `0x1400233d0`
- `0x14002340c`
- `0x140023f70`
- `0x14002792c`
- `0x14002b2c0`
- `0x140032a48`
- `0x140059d80`

## string_xrefs

- `0x14002416a`: `Endpoint Reset Command failed`

## pseudocode

```c
__int64 __fastcall Endpoint_ControlEndpointResetCompletion(_QWORD *a1, int a2, __int64 a3)
{
  __int64 v3; // rbx
  char v6; // cl
  __int64 v7; // rsi
  int v8; // r10d
  __int64 v9; // r9
  __int64 DequeuePointer; // r8
  __int64 result; // rax
  int v12; // edx
  int v13; // edx

  v3 = a1[6];
  if ( a2 == 3 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 4;
      WPP_RECORDER_SF_DD(
        *(_QWORD *)(v3 + 80),
        a2,
        13,
        91,
        (__int64)WPP_efed3b2fad403e600dcc20c948898b03_Traceguids,
        *(_BYTE *)(*(_QWORD *)(v3 + 16) + 143LL),
        *(_DWORD *)(v3 + 152));
    }
  }
  else
  {
    v6 = *((_BYTE *)a1 + 60);
    if ( v6 == 1 )
    {
      v7 = *(_QWORD *)(*(_QWORD *)v3 + 144LL);
      TR_InitializeTransferRing(*(_QWORD *)(v3 + 88));
      memset(a1, 0, 0x60u);
      a1[6] = v3;
      v8 = 0x4000;
      a1[5] = Endpoint_ControlEndpointResetSetDequeuePointerCompletion;
      v9 = 0;
      *((_DWORD *)a1 + 9) = 0x4000;
      if ( *(_BYTE *)(v3 + 37) )
        DequeuePointer = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v3 + 144) + 32LL) + 24LL);
      else
        DequeuePointer = TR_GetDequeuePointer(*(_QWORD *)(v3 + 88));
      a1[3] = DequeuePointer;
      *((_DWORD *)a1 + 9) = v8 | ((*(_DWORD *)(v3 + 152) & 0x1F) << 16);
      *((_BYTE *)a1 + 39) = *(_BYTE *)(*(_QWORD *)(v3 + 16) + 143LL);
      a1[9] = v9;
      a1[10] = v9;
      a1[11] = v9;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v12 = *((_WORD *)a1 + 19) & 0x1F;
        LOBYTE(v12) = 4;
        WPP_RECORDER_SF_ddi(*(_QWORD *)(v3 + 80), v12, DequeuePointer, 93);
      }
      return Command_SendCommand(v7, a1);
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v13 = *(unsigned __int8 *)(*(_QWORD *)(v3 + 16) + 143LL);
      LOBYTE(v13) = 2;
      WPP_RECORDER_SF_ddL(
        *(_QWORD *)(v3 + 80),
        v13,
        13,
        92,
        (__int64)WPP_efed3b2fad403e600dcc20c948898b03_Traceguids,
        *(_BYTE *)(*(_QWORD *)(v3 + 16) + 143LL),
        *(_DWORD *)(v3 + 152),
        v6);
    }
    Controller_HwVerifierBreakIfEnabled(
      *(_QWORD *)v3,
      *(_QWORD *)(v3 + 8),
      *(_QWORD *)(v3 + 24),
      256,
      (__int64)"Endpoint Reset Command failed",
      (__int64)(a1 + 3),
      a3);
    Controller_ReportFatalError(*(_QWORD *)v3, 2, 4102, 0, *(_QWORD *)(v3 + 16), v3, 0);
  }
  _m_prefetchw((const void *)(v3 + 32));
  result = (unsigned int)_InterlockedOr((volatile signed __int32 *)(v3 + 32), 2u);
  if ( (result & 2) == 0 )
    return ESM_AddEsmEvent(v3, 12);
  return result;
}

```

## disassembly

```asm
0x140023f70  mov     [rsp+arg_0], rbx
0x140023f75  mov     [rsp+arg_8], rsi
0x140023f7a  push    rdi
0x140023f7b  sub     rsp, 40h
0x140023f7f  mov     rbx, [rcx+30h]
0x140023f83  mov     rsi, r8
0x140023f86  mov     rdi, rcx
0x140023f89  cmp     edx, 3
0x140023f8c  jz      loc_14002405D
0x140023f92  movzx   ecx, byte ptr [rcx+3Ch]
0x140023f96  cmp     cl, 1
0x140023f99  jnz     loc_1400240FD
0x140023f9f  mov     rax, [rbx]
0x140023fa2  mov     rcx, [rbx+58h]
0x140023fa6  mov     rsi, [rax+90h]
0x140023fad  call    TR_InitializeTransferRing
0x140023fb2  xor     edx, edx; Val
0x140023fb4  mov     rcx, rdi; void *
0x140023fb7  lea     r8d, [rdx+60h]; Size
0x140023fbb  call    memset
0x140023fc0  lea     rax, Endpoint_ControlEndpointResetSetDequeuePointerCompletion
0x140023fc7  mov     [rdi+30h], rbx
0x140023fcb  mov     r10d, 4000h
0x140023fd1  mov     [rdi+28h], rax
0x140023fd5  xor     r9d, r9d
0x140023fd8  mov     [rdi+24h], r10d
0x140023fdc  cmp     [rbx+25h], r9b
0x140023fe0  jz      short loc_14002404F
0x140023fe2  mov     rax, [rbx+90h]
0x140023fe9  mov     rcx, [rax+20h]
0x140023fed  mov     r8, [rcx+18h]
0x140023ff1  mov     [rdi+18h], r8
0x140023ff5  mov     ecx, [rbx+98h]
0x140023ffb  and     ecx, 1Fh
0x140023ffe  shl     ecx, 10h
0x140024001  or      ecx, r10d
0x140024004  mov     [rdi+24h], ecx
0x140024007  mov     rcx, [rbx+10h]
0x14002400b  movzx   r10d, byte ptr [rcx+8Fh]
0x140024013  mov     [rdi+27h], r10b
0x140024017  mov     [rdi+48h], r9
0x14002401b  mov     [rdi+50h], r9
0x14002401f  mov     [rdi+58h], r9
0x140024023  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002402a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140024031  jnz     short loc_140024093
0x140024033  mov     rdx, rdi
0x140024036  mov     rcx, rsi
0x140024039  call    Command_SendCommand
0x14002403e  mov     rbx, [rsp+48h+arg_0]
0x140024043  mov     rsi, [rsp+48h+arg_8]
0x140024048  add     rsp, 40h
0x14002404c  pop     rdi
0x14002404d  retn
0x14002404f  mov     rcx, [rbx+58h]
0x140024053  call    TR_GetDequeuePointer
0x140024058  mov     r8, rax
0x14002405b  jmp     short loc_140023FF1
0x14002405d  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140024064  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002406b  jnz     short loc_1400240BE
0x14002406d  prefetchw byte ptr [rbx+20h]
0x140024071  mov     eax, [rbx+20h]
0x140024074  mov     edx, eax
0x140024076  or      edx, 2
0x140024079  lock cmpxchg [rbx+20h], edx
0x14002407e  jnz     short loc_140024074
0x140024080  test    al, 2
0x140024082  jnz     short loc_14002403E
0x140024084  mov     edx, 0Ch
0x140024089  mov     rcx, rbx
0x14002408c  call    ESM_AddEsmEvent
0x140024091  jmp     short loc_14002403E
0x140024093  movzx   edx, word ptr [rdi+26h]
0x140024097  mov     r9d, 5Dh ; ']'
0x14002409d  mov     rcx, [rbx+50h]
0x1400240a1  and     edx, 1Fh
0x1400240a4  mov     [rsp+48h+var_10], r8
0x1400240a9  mov     dword ptr [rsp+48h+var_18], edx
0x1400240ad  mov     dl, 4
0x1400240af  mov     dword ptr [rsp+48h+var_20], r10d
0x1400240b4  call    WPP_RECORDER_SF_ddi
0x1400240b9  jmp     loc_140024033
0x1400240be  mov     rax, [rbx+10h]
0x1400240c2  mov     r9d, 5Bh ; '['
0x1400240c8  mov     dl, 4
0x1400240ca  movzx   ecx, byte ptr [rax+8Fh]
0x1400240d1  lea     r8d, [r9-4Eh]
0x1400240d5  mov     eax, [rbx+98h]
0x1400240db  mov     dword ptr [rsp+48h+var_18], eax
0x1400240df  lea     rax, WPP_efed3b2fad403e600dcc20c948898b03_Traceguids
0x1400240e6  mov     dword ptr [rsp+48h+var_20], ecx
0x1400240ea  mov     rcx, [rbx+50h]
0x1400240ee  mov     [rsp+48h+var_28], rax
0x1400240f3  call    WPP_RECORDER_SF_DD
0x1400240f8  jmp     loc_14002406D
0x1400240fd  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140024104  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002410b  jz      short loc_14002414B
0x14002410d  mov     rax, [rbx+10h]
0x140024111  mov     r9d, 5Ch ; '\'
0x140024117  mov     dword ptr [rsp+48h+var_10], ecx
0x14002411b  mov     rcx, [rbx+50h]
0x14002411f  movzx   edx, byte ptr [rax+8Fh]
0x140024126  lea     r8d, [r9-4Fh]
0x14002412a  mov     eax, [rbx+98h]
0x140024130  mov     dword ptr [rsp+48h+var_18], eax
0x140024134  lea     rax, WPP_efed3b2fad403e600dcc20c948898b03_Traceguids
0x14002413b  mov     dword ptr [rsp+48h+var_20], edx
0x14002413f  mov     dl, 2
0x140024141  mov     [rsp+48h+var_28], rax
0x140024146  call    WPP_RECORDER_SF_ddL
0x14002414b  mov     r8, [rbx+18h]
0x14002414f  lea     rax, [rdi+18h]
0x140024153  mov     rdx, [rbx+8]
0x140024157  mov     r9d, 100h
0x14002415d  mov     rcx, [rbx]
0x140024160  mov     [rsp+48h+var_18], rsi
0x140024165  mov     [rsp+48h+var_20], rax
0x14002416a  lea     rax, aEndpointResetC; "Endpoint Reset Command failed"
0x140024171  mov     [rsp+48h+var_28], rax
0x140024176  call    Controller_HwVerifierBreakIfEnabled
0x14002417b  mov     rax, [rbx+10h]
0x14002417f  xor     r9d, r9d
0x140024182  mov     rcx, [rbx]
0x140024185  mov     r8d, 1006h
0x14002418b  mov     [rsp+48h+var_18], r9
0x140024190  mov     [rsp+48h+var_20], rbx
0x140024195  lea     edx, [r9+2]
0x140024199  mov     [rsp+48h+var_28], rax
0x14002419e  call    Controller_ReportFatalError
0x1400241a3  jmp     loc_14002406D
```
