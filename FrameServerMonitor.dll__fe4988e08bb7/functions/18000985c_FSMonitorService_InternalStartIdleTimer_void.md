# FSMonitorService::InternalStartIdleTimer(void)

- ea: `0x18000985c`
- end: `0x1800099a4`
- name: `?InternalStartIdleTimer@FSMonitorService@@IEAAJXZ`
- size: `328`
- prototype: `__int64 __fastcall(FSMonitorService *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180007820`
- `0x18000c100`

## callees

- `0x1800060e8`
- `0x1800060f8`
- `0x180006a98`
- `0x18000985c`
- `0x18000d7c4`
- `0x18000d820`

## import_xrefs

- `MFPlat!MFScheduleWorkItem` at `0x1800098db`
- `MFPlat!MFScheduleWorkItem` at `0x1800098db`

## pseudocode

```c
__int64 __fastcall FSMonitorService::InternalStartIdleTimer(FSMonitorService *this)
{
  int v1; // ebp
  HRESULT v3; // ebx
  unsigned int *v4; // r14
  MFWORKITEM_KEY *v5; // rsi
  __int64 v6; // rcx
  __int64 v7; // r8
  unsigned __int8 Level; // al
  __int64 v9; // rdx

  v1 = *((_DWORD *)this + 38);
  v3 = 0;
  v4 = (unsigned int *)((char *)this + 120);
  v5 = (MFWORKITEM_KEY *)((char *)this + 112);
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
    WPP_SF_qidD(*((_QWORD *)WPP_GLOBAL_Control + 27), 163, v7, v6, *v5, v1, *v4);
  if ( *v5 || v1 || *v4 == -1 )
    goto LABEL_16;
  v3 = MFScheduleWorkItem((IMFAsyncCallback *)this + 3, 0, -(__int64)*v4, v5);
  if ( v3 < 0 )
  {
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 164, &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids, this, v3);
    if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() )
    {
      v9 = 166;
      goto LABEL_14;
    }
    return (unsigned int)v3;
  }
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() < 8u )
  {
LABEL_16:
    Level = _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel();
  }
  else
  {
    WPP_SF_qqD(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      165,
      &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids,
      this,
      *v5,
      *v4);
    Level = _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel();
  }
  if ( Level >= 8u )
  {
    v9 = 167;
LABEL_14:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v9, &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids, this, v3);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000985c  push    rbx
0x18000985e  push    rbp
0x18000985f  push    rsi
0x180009860  push    rdi
0x180009861  push    r14
0x180009863  sub     rsp, 40h
0x180009867  mov     ebp, [rcx+98h]
0x18000986d  mov     rdi, rcx
0x180009870  xor     ebx, ebx
0x180009872  lea     r14, [rcx+78h]
0x180009876  lea     rsi, [rcx+70h]
0x18000987a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x18000987f  cmp     al, 8
0x180009881  jb      short loc_1800098B1
0x180009883  mov     eax, [r14]
0x180009886  mov     r9, rcx
0x180009889  mov     rcx, cs:WPP_GLOBAL_Control
0x180009890  mov     edx, 0A3h
0x180009895  mov     [rsp+68h+var_38], eax
0x180009899  mov     rax, [rsi]
0x18000989c  mov     [rsp+68h+var_40], ebp
0x1800098a0  mov     rcx, [rcx+0D8h]
0x1800098a7  mov     [rsp+68h+var_48], rax
0x1800098ac  call    WPP_SF_qidD
0x1800098b1  cmp     [rsi], rbx
0x1800098b4  jnz     loc_180009990
0x1800098ba  test    ebp, ebp
0x1800098bc  jnz     loc_180009990
0x1800098c2  cmp     dword ptr [r14], 0FFFFFFFFh
0x1800098c6  jz      loc_180009990
0x1800098cc  mov     r8d, [r14]
0x1800098cf  lea     rcx, [rdi+18h]; pCallback
0x1800098d3  neg     r8; Timeout
0x1800098d6  mov     r9, rsi; pKey
0x1800098d9  xor     edx, edx; pState
0x1800098db  call    cs:__imp_MFScheduleWorkItem
0x1800098e1  mov     ebx, eax
0x1800098e3  test    eax, eax
0x1800098e5  jns     short loc_18000991A
0x1800098e7  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800098ec  cmp     al, 1
0x1800098ee  jb      short loc_180009913
0x1800098f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800098f7  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x1800098fe  mov     edx, 0A4h
0x180009903  mov     dword ptr [rsp+68h+var_48], ebx
0x180009907  mov     r9, rdi
0x18000990a  mov     rcx, [rcx+10h]
0x18000990e  call    WPP_SF_qD
0x180009913  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180009918  jmp     short loc_180009999
0x18000991a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x18000991f  cmp     al, 8
0x180009921  jb      short loc_180009990
0x180009923  mov     eax, [r14]
0x180009926  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x18000992d  mov     rcx, cs:WPP_GLOBAL_Control
0x180009934  mov     edx, 0A5h
0x180009939  mov     [rsp+68h+var_40], eax
0x18000993d  mov     r9, rdi
0x180009940  mov     rax, [rsi]
0x180009943  mov     [rsp+68h+var_48], rax
0x180009948  mov     rcx, [rcx+0D8h]
0x18000994f  call    WPP_SF_qqD
0x180009954  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180009959  cmp     al, 8
0x18000995b  jb      short loc_180009983
0x18000995d  mov     edx, 0A7h
0x180009962  mov     rcx, cs:WPP_GLOBAL_Control
0x180009969  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x180009970  mov     r9, rdi
0x180009973  mov     dword ptr [rsp+68h+var_48], ebx
0x180009977  mov     rcx, [rcx+0D8h]
0x18000997e  call    WPP_SF_qD
0x180009983  mov     eax, ebx
0x180009985  add     rsp, 40h
0x180009989  pop     r14
0x18000998b  pop     rdi
0x18000998c  pop     rsi
0x18000998d  pop     rbp
0x18000998e  pop     rbx
0x18000998f  retn
0x180009990  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180009995  test    ebx, ebx
0x180009997  jns     short loc_180009959
0x180009999  cmp     al, 1
0x18000999b  jb      short loc_180009983
0x18000999d  mov     edx, 0A6h
0x1800099a2  jmp     short loc_180009962
```
