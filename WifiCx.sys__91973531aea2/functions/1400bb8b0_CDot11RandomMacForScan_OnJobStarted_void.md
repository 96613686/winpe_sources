# CDot11RandomMacForScan::OnJobStarted(void)

- ea: `0x1400bb8b0`
- end: `0x1400bbc3b`
- name: `?OnJobStarted@CDot11RandomMacForScan@@UEAAXXZ`
- size: `907`
- prototype: `void __fastcall(CDot11RandomMacForScan *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140012f80`
- `0x140017130`
- `0x14001e2c0`
- `0x14001eed0`
- `0x14001f8e4`
- `0x1400672f0`
- `0x140071720`
- `0x1400bb8b0`
- `0x1400bc1b8`
- `0x1400dfd00`
- `0x1400dfd40`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400bba09`
- `ntoskrnl!RtlCompareMemory` at `0x1400bba9b`
- `ntoskrnl!RtlCompareMemory` at `0x1400bbac0`
- `ntoskrnl!RtlCompareMemory` at `0x1400bbadd`
- `ntoskrnl!RtlCompareMemory` at `0x1400bba09`
- `ntoskrnl!RtlCompareMemory` at `0x1400bba9b`
- `ntoskrnl!RtlCompareMemory` at `0x1400bbac0`
- `ntoskrnl!RtlCompareMemory` at `0x1400bbadd`

## pseudocode

```c
void __fastcall CDot11RandomMacForScan::OnJobStarted(CDot11RandomMacForScan *this, __int64 a2, int a3)
{
  __int64 v4; // rcx
  CAdapterPropertyCache *v5; // rax
  int PermanentMacAddress; // ebp
  int v7; // r8d
  int v8; // r9d
  _DWORD *v9; // rsi
  int v10; // r8d
  int v11; // r9d
  __int64 v12; // rcx
  _DWORD *v13; // rcx
  SIZE_T v14; // rbx
  SIZE_T v15; // r14
  SIZE_T v16; // rax
  __int64 v17; // rdx
  CPropertyCache *PortPropertyCache; // rax
  int v19; // r8d
  int started; // eax
  int v21; // edx
  int v22; // r8d
  int v23; // [rsp+30h] [rbp-68h]
  __int64 v24; // [rsp+38h] [rbp-60h]
  unsigned __int8 Source2[6]; // [rsp+40h] [rbp-58h] BYREF

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      a3,
      30,
      (__int64)WPP_39144c5d48eb330c153897318434860d_Traceguids,
      (char)this,
      *((_DWORD *)this + 4));
  }
  *((_QWORD *)this + 73) = CAdapter::GetPortFromNdisPortNumber(*((CAdapter **)this + 67), *((_DWORD *)this + 140));
  v5 = (CAdapterPropertyCache *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v4 + 8) + 8LL))(v4 + 8);
  PermanentMacAddress = CAdapterPropertyCache::GetPermanentMacAddress(v5, (unsigned __int8 (*)[6])Source2);
  if ( PermanentMacAddress )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v8 = 31;
      v23 = *((_DWORD *)this + 4);
LABEL_17:
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        v7,
        v8,
        (__int64)WPP_39144c5d48eb330c153897318434860d_Traceguids,
        (char)this,
        v23);
    }
LABEL_35:
    CJobBase::CompleteJob(this, PermanentMacAddress);
    goto LABEL_36;
  }
  v9 = (_DWORD *)((char *)this + 592);
  if ( !*((_BYTE *)this + 592)
    && !*((_BYTE *)this + 593)
    && !*((_BYTE *)this + 594)
    && !*((_BYTE *)this + 595)
    && !*((_BYTE *)this + 596)
    && !*((_BYTE *)this + 597) )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_35;
    v8 = 32;
LABEL_16:
    v23 = *((_DWORD *)this + 4);
    goto LABEL_17;
  }
  if ( RtlCompareMemory((const void *)(*((_QWORD *)this + 73) + 184LL), (char *)this + 592, 6u) == 6 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
LABEL_22:
      v12 = *((_QWORD *)this + 73);
      *(_DWORD *)(v12 + 190) = *v9;
      *(_WORD *)(v12 + 194) = *((_WORD *)this + 298);
      goto LABEL_35;
    }
    v11 = 33;
LABEL_21:
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      v10,
      v11,
      (__int64)WPP_39144c5d48eb330c153897318434860d_Traceguids,
      (char)this,
      *((_DWORD *)this + 4));
    goto LABEL_22;
  }
  v13 = (_DWORD *)*((_QWORD *)this + 73);
  if ( v13[97] == 1 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_22;
    v11 = 34;
    goto LABEL_21;
  }
  v14 = RtlCompareMemory(v13 + 46, (char *)v13 + 190, 6u);
  v15 = RtlCompareMemory((const void *)(*((_QWORD *)this + 73) + 190LL), Source2, 6u);
  v16 = RtlCompareMemory((char *)this + 592, Source2, 6u);
  v17 = *((_QWORD *)this + 73);
  *(_DWORD *)(v17 + 190) = *v9;
  *(_WORD *)(v17 + 194) = *((_WORD *)this + 298);
  if ( v14 == 6 )
  {
    if ( v15 == 6 )
    {
      if ( v16 != 6 )
        goto LABEL_29;
    }
    else if ( v16 == 6 )
    {
      goto LABEL_29;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_35;
    v8 = 35;
    goto LABEL_16;
  }
LABEL_29:
  PortPropertyCache = COidJobBase::GetPortPropertyCache(this);
  if ( (unsigned int)CPropertyCache::GetPropertyBoolean(PortPropertyCache, 0x4Au, (unsigned __int8 *)this + 3872)
    && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      v19,
      36,
      (__int64)WPP_39144c5d48eb330c153897318434860d_Traceguids,
      (char)this,
      *((_DWORD *)this + 4));
  }
  started = CDot11RandomMacForScan::StartResetJob(this);
  PermanentMacAddress = started;
  if ( started )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v21) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v21,
        v22,
        37,
        (__int64)WPP_39144c5d48eb330c153897318434860d_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        started);
    }
    goto LABEL_35;
  }
LABEL_36:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v21) = 5;
    LODWORD(v24) = PermanentMacAddress;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v21,
      v22,
      38,
      (__int64)WPP_39144c5d48eb330c153897318434860d_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v24);
  }
}

```

## disassembly

```asm
0x1400bb8b0  push    rbx
0x1400bb8b2  push    rbp
0x1400bb8b3  push    rsi
0x1400bb8b4  push    rdi
0x1400bb8b5  push    r12
0x1400bb8b7  push    r13
0x1400bb8b9  push    r14
0x1400bb8bb  push    r15
0x1400bb8bd  sub     rsp, 58h
0x1400bb8c1  mov     rax, cs:__security_cookie
0x1400bb8c8  xor     rax, rsp
0x1400bb8cb  mov     [rsp+98h+var_50], rax
0x1400bb8d0  mov     rdi, rcx
0x1400bb8d3  lea     r12, WPP_RECORDER_INITIALIZED
0x1400bb8da  xor     r15d, r15d
0x1400bb8dd  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400bb8e4  lea     r13, WPP_39144c5d48eb330c153897318434860d_Traceguids
0x1400bb8eb  jz      short loc_1400BB923
0x1400bb8ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bb8f4  cmp     byte ptr [rcx+29h], 5
0x1400bb8f8  jnb     short loc_1400BB901
0x1400bb8fa  cmp     [rcx+48h], r15w
0x1400bb8ff  jz      short loc_1400BB923
0x1400bb901  mov     eax, [rdi+10h]
0x1400bb904  mov     r9d, 1Eh
0x1400bb90a  mov     rcx, [rcx+40h]
0x1400bb90e  mov     dl, 5
0x1400bb910  mov     [rsp+98h+var_68], eax
0x1400bb914  mov     [rsp+98h+var_70], rdi
0x1400bb919  mov     [rsp+98h+var_78], r13
0x1400bb91e  call    WPP_RECORDER_SF_qD
0x1400bb923  mov     rcx, [rdi+218h]; this
0x1400bb92a  mov     edx, [rdi+230h]; unsigned int
0x1400bb930  call    ?GetPortFromNdisPortNumber@CAdapter@@QEBAPEAVCPort@@K@Z; CAdapter::GetPortFromNdisPortNumber(ulong)
0x1400bb935  mov     [rdi+248h], rax
0x1400bb93c  add     rcx, 8
0x1400bb940  mov     rax, [rcx]
0x1400bb943  mov     rax, [rax+8]
0x1400bb947  call    _guard_dispatch_icall
0x1400bb94c  lea     rdx, [rsp+98h+Source2]; unsigned __int8 (*)[6]
0x1400bb951  mov     rcx, rax; this
0x1400bb954  call    ?GetPermanentMacAddress@CAdapterPropertyCache@@QEAAHPEAY05E@Z; CAdapterPropertyCache::GetPermanentMacAddress(uchar (*)[6])
0x1400bb959  mov     ebp, eax
0x1400bb95b  test    eax, eax
0x1400bb95d  jz      short loc_1400BB97B
0x1400bb95f  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400bb966  jz      loc_1400BBBB1
0x1400bb96c  mov     ecx, [rdi+10h]
0x1400bb96f  mov     r9d, 1Fh
0x1400bb975  mov     [rsp+98h+var_68], ecx
0x1400bb979  jmp     short loc_1400BB9CE
0x1400bb97b  lea     rsi, [rdi+250h]
0x1400bb982  cmp     [rsi], r15b
0x1400bb985  jnz     short loc_1400BB9EF
0x1400bb987  cmp     [rdi+251h], r15b
0x1400bb98e  jnz     short loc_1400BB9EF
0x1400bb990  cmp     [rdi+252h], r15b
0x1400bb997  jnz     short loc_1400BB9EF
0x1400bb999  cmp     [rdi+253h], r15b
0x1400bb9a0  jnz     short loc_1400BB9EF
0x1400bb9a2  cmp     [rdi+254h], r15b
0x1400bb9a9  jnz     short loc_1400BB9EF
0x1400bb9ab  cmp     [rdi+255h], r15b
0x1400bb9b2  jnz     short loc_1400BB9EF
0x1400bb9b4  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400bb9bb  jz      loc_1400BBBB1
0x1400bb9c1  mov     r9d, 20h ; ' '
0x1400bb9c7  mov     eax, [rdi+10h]
0x1400bb9ca  mov     [rsp+98h+var_68], eax
0x1400bb9ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bb9d5  mov     dl, 4
0x1400bb9d7  mov     [rsp+98h+var_70], rdi
0x1400bb9dc  mov     [rsp+98h+var_78], r13
0x1400bb9e1  mov     rcx, [rcx+40h]
0x1400bb9e5  call    WPP_RECORDER_SF_qD
0x1400bb9ea  jmp     loc_1400BBBB1
0x1400bb9ef  mov     rcx, [rdi+248h]
0x1400bb9f6  mov     r14d, 6
0x1400bb9fc  add     rcx, 0B8h; Source1
0x1400bba03  mov     r8d, r14d; Length
0x1400bba06  mov     rdx, rsi; Source2
0x1400bba09  call    cs:__imp_RtlCompareMemory
0x1400bba10  nop     dword ptr [rax+rax+00h]
0x1400bba15  cmp     rax, r14
0x1400bba18  jnz     short loc_1400BBA69
0x1400bba1a  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400bba21  jz      short loc_1400BBA4A
0x1400bba23  lea     r9d, [r14+1Bh]
0x1400bba27  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bba2e  mov     dl, 4
0x1400bba30  mov     eax, [rdi+10h]
0x1400bba33  mov     [rsp+98h+var_68], eax
0x1400bba37  mov     [rsp+98h+var_70], rdi
0x1400bba3c  mov     rcx, [rcx+40h]
0x1400bba40  mov     [rsp+98h+var_78], r13
0x1400bba45  call    WPP_RECORDER_SF_qD
0x1400bba4a  mov     eax, [rsi]
0x1400bba4c  mov     rcx, [rdi+248h]
0x1400bba53  mov     [rcx+0BEh], eax
0x1400bba59  movzx   eax, word ptr [rsi+4]
0x1400bba5d  mov     [rcx+0C2h], ax
0x1400bba64  jmp     loc_1400BBBB1
0x1400bba69  mov     rcx, [rdi+248h]
0x1400bba70  cmp     dword ptr [rcx+184h], 1
0x1400bba77  jnz     short loc_1400BBA8A
0x1400bba79  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400bba80  jz      short loc_1400BBA4A
0x1400bba82  mov     r9d, 22h ; '"'
0x1400bba88  jmp     short loc_1400BBA27
0x1400bba8a  lea     rdx, [rcx+0BEh]; Source2
0x1400bba91  mov     r8, r14; Length
0x1400bba94  add     rcx, 0B8h; Source1
0x1400bba9b  call    cs:__imp_RtlCompareMemory
0x1400bbaa2  nop     dword ptr [rax+rax+00h]
0x1400bbaa7  mov     rcx, [rdi+248h]
0x1400bbaae  lea     rdx, [rsp+98h+Source2]; Source2
0x1400bbab3  add     rcx, 0BEh; Source1
0x1400bbaba  mov     r8, r14; Length
0x1400bbabd  mov     rbx, rax
0x1400bbac0  call    cs:__imp_RtlCompareMemory
0x1400bbac7  nop     dword ptr [rax+rax+00h]
0x1400bbacc  mov     r8d, 6; Length
0x1400bbad2  lea     rdx, [rsp+98h+Source2]; Source2
0x1400bbad7  mov     rcx, rsi; Source1
0x1400bbada  mov     r14, rax
0x1400bbadd  call    cs:__imp_RtlCompareMemory
0x1400bbae4  nop     dword ptr [rax+rax+00h]
0x1400bbae9  mov     ecx, [rsi]
0x1400bbaeb  mov     rdx, [rdi+248h]
0x1400bbaf2  mov     [rdx+0BEh], ecx
0x1400bbaf8  movzx   ecx, word ptr [rsi+4]
0x1400bbafc  mov     [rdx+0C2h], cx
0x1400bbb03  cmp     rbx, 6
0x1400bbb07  jnz     short loc_1400BBB1B
0x1400bbb09  cmp     r14, rbx
0x1400bbb0c  jnz     loc_1400BBC1D
0x1400bbb12  cmp     rax, rbx
0x1400bbb15  jz      loc_1400BBC27
0x1400bbb1b  mov     rcx, rdi; this
0x1400bbb1e  call    ?GetPortPropertyCache@COidJobBase@@IEAAPEAVCPortPropertyCache@@XZ; COidJobBase::GetPortPropertyCache(void)
0x1400bbb23  lea     r8, [rdi+0F20h]; unsigned __int8 *
0x1400bbb2a  mov     edx, 4Ah ; 'J'; unsigned int
0x1400bbb2f  mov     rcx, rax; this
0x1400bbb32  call    ?GetPropertyBoolean@CPropertyCache@@QEAAHKPEAE@Z; CPropertyCache::GetPropertyBoolean(ulong,uchar *)
0x1400bbb37  test    eax, eax
0x1400bbb39  jz      short loc_1400BBB6D
0x1400bbb3b  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400bbb42  jz      short loc_1400BBB6D
0x1400bbb44  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bbb4b  mov     r9d, 24h ; '$'
0x1400bbb51  mov     eax, [rdi+10h]
0x1400bbb54  mov     dl, 4
0x1400bbb56  mov     [rsp+98h+var_68], eax
0x1400bbb5a  mov     [rsp+98h+var_70], rdi
0x1400bbb5f  mov     rcx, [rcx+40h]
0x1400bbb63  mov     [rsp+98h+var_78], r13
0x1400bbb68  call    WPP_RECORDER_SF_qD
0x1400bbb6d  mov     rcx, rdi; this
0x1400bbb70  call    ?StartResetJob@CDot11RandomMacForScan@@AEAAHXZ; CDot11RandomMacForScan::StartResetJob(void)
0x1400bbb75  mov     ebp, eax
0x1400bbb77  test    eax, eax
0x1400bbb79  jz      short loc_1400BBBBB
0x1400bbb7b  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400bbb82  jz      short loc_1400BBBB1
0x1400bbb84  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bbb8b  mov     r9d, 25h ; '%'
0x1400bbb91  mov     dword ptr [rsp+98h+var_60], eax
0x1400bbb95  mov     dl, 2
0x1400bbb97  mov     eax, [rdi+10h]
0x1400bbb9a  mov     [rsp+98h+var_68], eax
0x1400bbb9e  mov     rcx, [rcx+40h]
0x1400bbba2  mov     [rsp+98h+var_70], rdi
0x1400bbba7  mov     [rsp+98h+var_78], r13
0x1400bbbac  call    WPP_RECORDER_SF_qDD
0x1400bbbb1  mov     edx, ebp; int
0x1400bbbb3  mov     rcx, rdi; this
0x1400bbbb6  call    ?CompleteJob@CJobBase@@IEAAHH@Z; CJobBase::CompleteJob(int)
0x1400bbbbb  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400bbbc2  jz      short loc_1400BBBFE
0x1400bbbc4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bbbcb  cmp     byte ptr [rcx+29h], 5
0x1400bbbcf  jnb     short loc_1400BBBD8
0x1400bbbd1  cmp     [rcx+48h], r15w
0x1400bbbd6  jz      short loc_1400BBBFE
0x1400bbbd8  mov     eax, [rdi+10h]
0x1400bbbdb  mov     r9d, 26h ; '&'
0x1400bbbe1  mov     rcx, [rcx+40h]
0x1400bbbe5  mov     dl, 5
0x1400bbbe7  mov     dword ptr [rsp+98h+var_60], ebp
0x1400bbbeb  mov     [rsp+98h+var_68], eax
0x1400bbbef  mov     [rsp+98h+var_70], rdi
0x1400bbbf4  mov     [rsp+98h+var_78], r13
0x1400bbbf9  call    WPP_RECORDER_SF_qDD
0x1400bbbfe  mov     rcx, [rsp+98h+var_50]
0x1400bbc03  xor     rcx, rsp; StackCookie
0x1400bbc06  call    __security_check_cookie
0x1400bbc0b  add     rsp, 58h
0x1400bbc0f  pop     r15
0x1400bbc11  pop     r14
0x1400bbc13  pop     r13
0x1400bbc15  pop     r12
0x1400bbc17  pop     rdi
0x1400bbc18  pop     rsi
0x1400bbc19  pop     rbp
0x1400bbc1a  pop     rbx
0x1400bbc1b  retn
0x1400bbc1d  cmp     rax, 6
0x1400bbc21  jz      loc_1400BBB1B
0x1400bbc27  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400bbc2e  jz      short loc_1400BBBB1
0x1400bbc30  mov     r9d, 23h ; '#'
0x1400bbc36  jmp     loc_1400BB9C7
```
