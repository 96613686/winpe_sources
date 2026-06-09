# CDot11RandomMacForScan::OnJobStarted(void)

- ea: `0x140069090`
- end: `0x14006941b`
- name: `?OnJobStarted@CDot11RandomMacForScan@@UEAAXXZ`
- size: `907`
- prototype: `void __fastcall(CJobBase *this)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140004c3c`
- `0x140010b20`
- `0x1400122e0`
- `0x1400147e8`
- `0x14002aa28`
- `0x14002c5d8`
- `0x140069090`
- `0x140069424`
- `0x1400d6098`
- `0x1400da4f0`
- `0x1400da680`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400691e9`
- `ntoskrnl!RtlCompareMemory` at `0x14006927b`
- `ntoskrnl!RtlCompareMemory` at `0x1400692a0`
- `ntoskrnl!RtlCompareMemory` at `0x1400692bd`
- `ntoskrnl!RtlCompareMemory` at `0x1400691e9`
- `ntoskrnl!RtlCompareMemory` at `0x14006927b`
- `ntoskrnl!RtlCompareMemory` at `0x1400692a0`
- `ntoskrnl!RtlCompareMemory` at `0x1400692bd`

## pseudocode

```c
void __fastcall CDot11RandomMacForScan::OnJobStarted(CJobBase *this, __int64 a2, int a3)
{
  __int64 v4; // rcx
  CAdapterPropertyCache *v5; // rax
  int PermanentMacAddress; // ebp
  int v7; // r8d
  int v8; // r9d
  unsigned int *p_m_NdisPortNumber; // rsi
  int v10; // r8d
  int v11; // r9d
  __int64 v12; // rcx
  _DWORD *v13; // rcx
  SIZE_T v14; // rbx
  SIZE_T v15; // r14
  SIZE_T v16; // rax
  __int64 v17; // rdx
  struct CPortPropertyCache *PortPropertyCache; // rax
  int v19; // r8d
  int started; // eax
  int v21; // edx
  int v22; // r8d
  unsigned int m_ActivityId; // [rsp+30h] [rbp-68h]
  unsigned __int8 Source2[6]; // [rsp+40h] [rbp-58h] BYREF

  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      a3,
      30,
      (__int64)WPP_730b61d8465236f9b0ea7341c6c3d9cf_Traceguids,
      (char)this,
      this->m_ActivityId);
  }
  *(_QWORD *)&this[1].m_JobPriority = CAdapter::GetPortFromNdisPortNumber(
                                        (CAdapter *)this[1].IOperationCompletionCallback::__vftable,
                                        (unsigned int)this[1].EventJobStarted);
  v5 = (CAdapterPropertyCache *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v4 + 8) + 8LL))(v4 + 8);
  PermanentMacAddress = CAdapterPropertyCache::GetPermanentMacAddress(v5, (unsigned __int8 (*)[6])Source2);
  if ( PermanentMacAddress )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v8 = 31;
      m_ActivityId = this->m_ActivityId;
LABEL_17:
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        v7,
        v8,
        (__int64)WPP_730b61d8465236f9b0ea7341c6c3d9cf_Traceguids,
        (char)this,
        m_ActivityId);
    }
LABEL_35:
    CJobBase::CompleteJob(this, PermanentMacAddress);
    goto LABEL_36;
  }
  p_m_NdisPortNumber = &this[1].m_NdisPortNumber;
  if ( !LOBYTE(this[1].m_NdisPortNumber)
    && !BYTE1(this[1].m_NdisPortNumber)
    && !BYTE2(this[1].m_NdisPortNumber)
    && !HIBYTE(this[1].m_NdisPortNumber)
    && !LOBYTE(this[1].m_JobType)
    && !BYTE1(this[1].m_JobType) )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_35;
    v8 = 32;
LABEL_16:
    m_ActivityId = this->m_ActivityId;
    goto LABEL_17;
  }
  if ( RtlCompareMemory((const void *)(*(_QWORD *)&this[1].m_JobPriority + 520LL), &this[1].m_NdisPortNumber, 6u) == 6 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
    {
LABEL_22:
      v12 = *(_QWORD *)&this[1].m_JobPriority;
      *(_DWORD *)(v12 + 526) = *p_m_NdisPortNumber;
      *(_WORD *)(v12 + 530) = this[1].m_JobType;
      goto LABEL_35;
    }
    v11 = 33;
LABEL_21:
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      v10,
      v11,
      (__int64)WPP_730b61d8465236f9b0ea7341c6c3d9cf_Traceguids,
      (char)this,
      this->m_ActivityId);
    goto LABEL_22;
  }
  v13 = *(_DWORD **)&this[1].m_JobPriority;
  if ( v13[203] == 1 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_22;
    v11 = 34;
    goto LABEL_21;
  }
  v14 = RtlCompareMemory(v13 + 130, (char *)v13 + 526, 6u);
  v15 = RtlCompareMemory((const void *)(*(_QWORD *)&this[1].m_JobPriority + 526LL), Source2, 6u);
  v16 = RtlCompareMemory(&this[1].m_NdisPortNumber, Source2, 6u);
  v17 = *(_QWORD *)&this[1].m_JobPriority;
  *(_DWORD *)(v17 + 526) = *p_m_NdisPortNumber;
  *(_WORD *)(v17 + 530) = this[1].m_JobType;
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
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_35;
    v8 = 35;
    goto LABEL_16;
  }
LABEL_29:
  PortPropertyCache = COidJobBase::GetPortPropertyCache((COidJobBase *)this);
  if ( (unsigned int)CPropertyCache::GetPropertyUchar(
                       PortPropertyCache,
                       0x49u,
                       (unsigned __int8 *)&this[7].m_FailsafeJobStartedEvent.m_Link.ListEntry.Blink)
    && *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      v19,
      36,
      (__int64)WPP_730b61d8465236f9b0ea7341c6c3d9cf_Traceguids,
      (char)this,
      this->m_ActivityId);
  }
  started = CDot11RandomMacForScan::StartResetJob(this);
  PermanentMacAddress = started;
  if ( started )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v21) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v21,
        v22,
        37,
        (__int64)WPP_730b61d8465236f9b0ea7341c6c3d9cf_Traceguids,
        (char)this,
        this->m_ActivityId,
        started);
    }
    goto LABEL_35;
  }
LABEL_36:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v21) = 5;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v21,
      v22,
      38,
      (__int64)WPP_730b61d8465236f9b0ea7341c6c3d9cf_Traceguids,
      (char)this,
      this->m_ActivityId,
      PermanentMacAddress);
  }
}

```

## disassembly

```asm
0x140069090  push    rbx
0x140069092  push    rbp
0x140069093  push    rsi
0x140069094  push    rdi
0x140069095  push    r12
0x140069097  push    r13
0x140069099  push    r14
0x14006909b  push    r15
0x14006909d  sub     rsp, 58h
0x1400690a1  mov     rax, cs:__security_cookie
0x1400690a8  xor     rax, rsp
0x1400690ab  mov     [rsp+98h+var_50], rax
0x1400690b0  mov     rdi, rcx
0x1400690b3  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400690ba  xor     r15d, r15d
0x1400690bd  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400690c4  lea     r13, WPP_730b61d8465236f9b0ea7341c6c3d9cf_Traceguids
0x1400690cb  jz      short loc_140069103
0x1400690cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400690d4  cmp     byte ptr [rcx+29h], 5
0x1400690d8  jnb     short loc_1400690E1
0x1400690da  cmp     [rcx+48h], r15w
0x1400690df  jz      short loc_140069103
0x1400690e1  mov     eax, [rdi+10h]
0x1400690e4  mov     r9d, 1Eh
0x1400690ea  mov     rcx, [rcx+40h]
0x1400690ee  mov     dl, 5
0x1400690f0  mov     [rsp+98h+var_68], eax
0x1400690f4  mov     [rsp+98h+var_70], rdi
0x1400690f9  mov     [rsp+98h+var_78], r13
0x1400690fe  call    WPP_RECORDER_SF_qD
0x140069103  mov     rcx, [rdi+200h]; this
0x14006910a  mov     edx, [rdi+218h]; unsigned int
0x140069110  call    ?GetPortFromNdisPortNumber@CAdapter@@QEAAPEAVCPort@@K@Z; CAdapter::GetPortFromNdisPortNumber(ulong)
0x140069115  mov     [rdi+230h], rax
0x14006911c  add     rcx, 8
0x140069120  mov     rax, [rcx]
0x140069123  mov     rax, [rax+8]
0x140069127  call    _guard_dispatch_icall
0x14006912c  lea     rdx, [rsp+98h+Source2]; unsigned __int8 (*)[6]
0x140069131  mov     rcx, rax; this
0x140069134  call    ?GetPermanentMacAddress@CAdapterPropertyCache@@QEAAHPEAY05E@Z; CAdapterPropertyCache::GetPermanentMacAddress(uchar (*)[6])
0x140069139  mov     ebp, eax
0x14006913b  test    eax, eax
0x14006913d  jz      short loc_14006915B
0x14006913f  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140069146  jz      loc_140069391
0x14006914c  mov     ecx, [rdi+10h]
0x14006914f  mov     r9d, 1Fh
0x140069155  mov     [rsp+98h+var_68], ecx
0x140069159  jmp     short loc_1400691AE
0x14006915b  lea     rsi, [rdi+238h]
0x140069162  cmp     [rsi], r15b
0x140069165  jnz     short loc_1400691CF
0x140069167  cmp     [rdi+239h], r15b
0x14006916e  jnz     short loc_1400691CF
0x140069170  cmp     [rdi+23Ah], r15b
0x140069177  jnz     short loc_1400691CF
0x140069179  cmp     [rdi+23Bh], r15b
0x140069180  jnz     short loc_1400691CF
0x140069182  cmp     [rdi+23Ch], r15b
0x140069189  jnz     short loc_1400691CF
0x14006918b  cmp     [rdi+23Dh], r15b
0x140069192  jnz     short loc_1400691CF
0x140069194  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14006919b  jz      loc_140069391
0x1400691a1  mov     r9d, 20h ; ' '
0x1400691a7  mov     eax, [rdi+10h]
0x1400691aa  mov     [rsp+98h+var_68], eax
0x1400691ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400691b5  mov     dl, 4
0x1400691b7  mov     [rsp+98h+var_70], rdi
0x1400691bc  mov     [rsp+98h+var_78], r13
0x1400691c1  mov     rcx, [rcx+40h]
0x1400691c5  call    WPP_RECORDER_SF_qD
0x1400691ca  jmp     loc_140069391
0x1400691cf  mov     rcx, [rdi+230h]
0x1400691d6  mov     r14d, 6
0x1400691dc  add     rcx, 208h; Source1
0x1400691e3  mov     r8d, r14d; Length
0x1400691e6  mov     rdx, rsi; Source2
0x1400691e9  call    cs:__imp_RtlCompareMemory
0x1400691f0  nop     dword ptr [rax+rax+00h]
0x1400691f5  cmp     rax, r14
0x1400691f8  jnz     short loc_140069249
0x1400691fa  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140069201  jz      short loc_14006922A
0x140069203  lea     r9d, [r14+1Bh]
0x140069207  mov     rcx, cs:WPP_GLOBAL_Control
0x14006920e  mov     dl, 4
0x140069210  mov     eax, [rdi+10h]
0x140069213  mov     [rsp+98h+var_68], eax
0x140069217  mov     [rsp+98h+var_70], rdi
0x14006921c  mov     rcx, [rcx+40h]
0x140069220  mov     [rsp+98h+var_78], r13
0x140069225  call    WPP_RECORDER_SF_qD
0x14006922a  mov     eax, [rsi]
0x14006922c  mov     rcx, [rdi+230h]
0x140069233  mov     [rcx+20Eh], eax
0x140069239  movzx   eax, word ptr [rsi+4]
0x14006923d  mov     [rcx+212h], ax
0x140069244  jmp     loc_140069391
0x140069249  mov     rcx, [rdi+230h]
0x140069250  cmp     dword ptr [rcx+32Ch], 1
0x140069257  jnz     short loc_14006926A
0x140069259  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140069260  jz      short loc_14006922A
0x140069262  mov     r9d, 22h ; '"'
0x140069268  jmp     short loc_140069207
0x14006926a  lea     rdx, [rcx+20Eh]; Source2
0x140069271  mov     r8, r14; Length
0x140069274  add     rcx, 208h; Source1
0x14006927b  call    cs:__imp_RtlCompareMemory
0x140069282  nop     dword ptr [rax+rax+00h]
0x140069287  mov     rcx, [rdi+230h]
0x14006928e  lea     rdx, [rsp+98h+Source2]; Source2
0x140069293  add     rcx, 20Eh; Source1
0x14006929a  mov     r8, r14; Length
0x14006929d  mov     rbx, rax
0x1400692a0  call    cs:__imp_RtlCompareMemory
0x1400692a7  nop     dword ptr [rax+rax+00h]
0x1400692ac  mov     r8d, 6; Length
0x1400692b2  lea     rdx, [rsp+98h+Source2]; Source2
0x1400692b7  mov     rcx, rsi; Source1
0x1400692ba  mov     r14, rax
0x1400692bd  call    cs:__imp_RtlCompareMemory
0x1400692c4  nop     dword ptr [rax+rax+00h]
0x1400692c9  mov     ecx, [rsi]
0x1400692cb  mov     rdx, [rdi+230h]
0x1400692d2  mov     [rdx+20Eh], ecx
0x1400692d8  movzx   ecx, word ptr [rsi+4]
0x1400692dc  mov     [rdx+212h], cx
0x1400692e3  cmp     rbx, 6
0x1400692e7  jnz     short loc_1400692FB
0x1400692e9  cmp     r14, rbx
0x1400692ec  jnz     loc_1400693FD
0x1400692f2  cmp     rax, rbx
0x1400692f5  jz      loc_140069407
0x1400692fb  mov     rcx, rdi; this
0x1400692fe  call    ?GetPortPropertyCache@COidJobBase@@IEAAPEAVCPortPropertyCache@@XZ; COidJobBase::GetPortPropertyCache(void)
0x140069303  lea     r8, [rdi+0EC0h]; unsigned __int8 *
0x14006930a  mov     edx, 49h ; 'I'; unsigned int
0x14006930f  mov     rcx, rax; this
0x140069312  call    ?GetPropertyUchar@CPropertyCache@@QEAAHKPEAE@Z; CPropertyCache::GetPropertyUchar(ulong,uchar *)
0x140069317  test    eax, eax
0x140069319  jz      short loc_14006934D
0x14006931b  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140069322  jz      short loc_14006934D
0x140069324  mov     rcx, cs:WPP_GLOBAL_Control
0x14006932b  mov     r9d, 24h ; '$'
0x140069331  mov     eax, [rdi+10h]
0x140069334  mov     dl, 4
0x140069336  mov     [rsp+98h+var_68], eax
0x14006933a  mov     [rsp+98h+var_70], rdi
0x14006933f  mov     rcx, [rcx+40h]
0x140069343  mov     [rsp+98h+var_78], r13
0x140069348  call    WPP_RECORDER_SF_qD
0x14006934d  mov     rcx, rdi; this
0x140069350  call    ?StartResetJob@CDot11RandomMacForScan@@AEAAHXZ; CDot11RandomMacForScan::StartResetJob(void)
0x140069355  mov     ebp, eax
0x140069357  test    eax, eax
0x140069359  jz      short loc_14006939B
0x14006935b  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140069362  jz      short loc_140069391
0x140069364  mov     rcx, cs:WPP_GLOBAL_Control
0x14006936b  mov     r9d, 25h ; '%'
0x140069371  mov     [rsp+98h+var_60], eax
0x140069375  mov     dl, 2
0x140069377  mov     eax, [rdi+10h]
0x14006937a  mov     [rsp+98h+var_68], eax
0x14006937e  mov     rcx, [rcx+40h]
0x140069382  mov     [rsp+98h+var_70], rdi
0x140069387  mov     [rsp+98h+var_78], r13
0x14006938c  call    WPP_RECORDER_SF_qDD
0x140069391  mov     edx, ebp; int
0x140069393  mov     rcx, rdi; this
0x140069396  call    ?CompleteJob@CJobBase@@IEAAHH@Z; CJobBase::CompleteJob(int)
0x14006939b  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x1400693a2  jz      short loc_1400693DE
0x1400693a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400693ab  cmp     byte ptr [rcx+29h], 5
0x1400693af  jnb     short loc_1400693B8
0x1400693b1  cmp     [rcx+48h], r15w
0x1400693b6  jz      short loc_1400693DE
0x1400693b8  mov     eax, [rdi+10h]
0x1400693bb  mov     r9d, 26h ; '&'
0x1400693c1  mov     rcx, [rcx+40h]
0x1400693c5  mov     dl, 5
0x1400693c7  mov     [rsp+98h+var_60], ebp
0x1400693cb  mov     [rsp+98h+var_68], eax
0x1400693cf  mov     [rsp+98h+var_70], rdi
0x1400693d4  mov     [rsp+98h+var_78], r13
0x1400693d9  call    WPP_RECORDER_SF_qDD
0x1400693de  mov     rcx, [rsp+98h+var_50]
0x1400693e3  xor     rcx, rsp; StackCookie
0x1400693e6  call    __security_check_cookie
0x1400693eb  add     rsp, 58h
0x1400693ef  pop     r15
0x1400693f1  pop     r14
0x1400693f3  pop     r13
0x1400693f5  pop     r12
0x1400693f7  pop     rdi
0x1400693f8  pop     rsi
0x1400693f9  pop     rbp
0x1400693fa  pop     rbx
0x1400693fb  retn
0x1400693fd  cmp     rax, 6
0x140069401  jz      loc_1400692FB
0x140069407  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14006940e  jz      short loc_140069391
0x140069410  mov     r9d, 23h ; '#'
0x140069416  jmp     loc_1400691A7
```
