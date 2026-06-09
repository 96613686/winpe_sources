# CQueueMgr::SetQMGuid(void)

- ea: `0x1800190f4`
- end: `0x1800192e8`
- name: `?SetQMGuid@CQueueMgr@@SAJXZ`
- size: `500`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002ed40`

## callees

- `0x18000d1f0`
- `0x18000f35c`
- `0x1800190f4`
- `0x18002c61c`
- `0x1800cffcc`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x1800191b8`
- `RPCRT4!UuidCreate` at `0x1800191b8`
- `mqsec!GetFalconKeyValue` at `0x180019133`
- `mqsec!GetFalconKeyValue` at `0x180019171`
- `mqsec!GetFalconKeyValue` at `0x180019133`
- `mqsec!GetFalconKeyValue` at `0x180019171`
- `mqsec!DeleteFalconKeyValue` at `0x180019263`
- `mqsec!DeleteFalconKeyValue` at `0x180019263`
- `mqsec!SetFalconKeyValue` at `0x1800191de`
- `mqsec!SetFalconKeyValue` at `0x1800191de`

## string_xrefs

- `0x18001912c`: `MachineCache\QMId`
- `0x1800191d7`: `MachineCache\QMId`
- `0x18001921d`: `MachineCache\QMId`
- `0x1800192b2`: `MachineCache\QMId`

## pseudocode

```c
__int64 CQueueMgr::SetQMGuid(void)
{
  signed int FalconKeyValue; // ebx
  unsigned int v1; // eax
  bool v2; // sf
  unsigned __int16 v3; // r8
  bool v5; // sf
  unsigned int v6; // [rsp+50h] [rbp+20h] BYREF
  unsigned int v7; // [rsp+58h] [rbp+28h] BYREF
  int v8; // [rsp+60h] [rbp+30h] BYREF

  v7 = 3;
  v6 = 16;
  FalconKeyValue = GetFalconKeyValue(L"MachineCache\\QMId", &v7, &CQueueMgr::m_guidQmQueue, &v6, 0);
  if ( FalconKeyValue )
  {
    v8 = 0;
    v6 = 4;
    v7 = 4;
    GetFalconKeyValue(L"Sysprep", &v7, &v8, &v6, 0);
    if ( !v8 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          52,
          WPP_29ec7c04fef53c01da80d97243eda25e_Traceguids,
          (unsigned int)FalconKeyValue);
      EvReportWithError(0xC00007D0, FalconKeyValue, 1u, L"MachineCache\\QMId");
      v5 = FalconKeyValue < 0;
      if ( FalconKeyValue > 0 )
      {
        FalconKeyValue = (unsigned __int16)FalconKeyValue | 0x80070000;
        v5 = FalconKeyValue < 0;
      }
      if ( !v5 )
        return (unsigned int)FalconKeyValue;
      v3 = 1130;
      goto LABEL_14;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 50, WPP_29ec7c04fef53c01da80d97243eda25e_Traceguids);
    UuidCreate(&CQueueMgr::m_guidQmQueue);
    v7 = 3;
    v6 = 16;
    v1 = SetFalconKeyValue(L"MachineCache\\QMId", &v7, &CQueueMgr::m_guidQmQueue, &v6);
    FalconKeyValue = v1;
    if ( v1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 51, WPP_29ec7c04fef53c01da80d97243eda25e_Traceguids, v1);
      EvReportWithError(0xC00007D1, FalconKeyValue, 1u, L"MachineCache\\QMId");
      v2 = FalconKeyValue < 0;
      if ( FalconKeyValue > 0 )
      {
        FalconKeyValue = (unsigned __int16)FalconKeyValue | 0x80070000;
        v2 = FalconKeyValue < 0;
      }
      if ( !v2 )
        return (unsigned int)FalconKeyValue;
      v3 = 1129;
LABEL_14:
      LogMsgHR(FalconKeyValue, (wchar_t *)L"cqmgr", v3);
      return (unsigned int)FalconKeyValue;
    }
    DeleteFalconKeyValue(L"Sysprep");
  }
  return 0;
}

```

## disassembly

```asm
0x1800190f4  mov     [rsp-18h+arg_18], rbx
0x1800190f9  push    rbp
0x1800190fa  push    rsi
0x1800190fb  push    rdi
0x1800190fc  mov     rbp, rsp
0x1800190ff  sub     rsp, 30h
0x180019103  lea     rdi, ?m_guidQmQueue@CQueueMgr@@0U_GUID@@A; _GUID CQueueMgr::m_guidQmQueue
0x18001910a  mov     [rbp+arg_8], 3
0x180019111  mov     r8, rdi
0x180019114  mov     [rbp+arg_0], 10h
0x18001911b  lea     r9, [rbp+arg_0]
0x18001911f  mov     [rsp+30h+var_10], 0
0x180019128  lea     rdx, [rbp+arg_8]
0x18001912c  lea     rcx, aMachinecacheQm; "MachineCache\\QMId"
0x180019133  call    cs:__imp_?GetFalconKeyValue@@YAJPEB_WPEAKPEAX10@Z; GetFalconKeyValue(wchar_t const *,ulong *,void *,ulong *,wchar_t const *)
0x180019139  mov     ebx, eax
0x18001913b  test    eax, eax
0x18001913d  jz      loc_180019269
0x180019143  mov     eax, 4
0x180019148  mov     [rbp+arg_10], 0
0x18001914f  lea     r9, [rbp+arg_0]
0x180019153  mov     [rbp+arg_0], eax
0x180019156  lea     r8, [rbp+arg_10]
0x18001915a  mov     [rbp+arg_8], eax
0x18001915d  lea     rdx, [rbp+arg_8]
0x180019161  mov     [rsp+30h+var_10], 0
0x18001916a  lea     rcx, aSysprep; "Sysprep"
0x180019171  call    cs:__imp_?GetFalconKeyValue@@YAJPEB_WPEAKPEAX10@Z; GetFalconKeyValue(wchar_t const *,ulong *,void *,ulong *,wchar_t const *)
0x180019177  cmp     [rbp+arg_10], 0
0x18001917b  jz      loc_180019278
0x180019181  mov     rcx, cs:WPP_GLOBAL_Control
0x180019188  lea     rsi, WPP_GLOBAL_Control
0x18001918f  cmp     rcx, rsi
0x180019192  jz      short loc_1800191B5
0x180019194  test    byte ptr [rcx+0E4h], 2
0x18001919b  jz      short loc_1800191B5
0x18001919d  mov     rcx, [rcx+0D8h]
0x1800191a4  lea     r8, WPP_29ec7c04fef53c01da80d97243eda25e_Traceguids
0x1800191ab  mov     edx, 32h ; '2'
0x1800191b0  call    WPP_SF_
0x1800191b5  mov     rcx, rdi; Uuid
0x1800191b8  call    cs:__imp_UuidCreate
0x1800191be  lea     r9, [rbp+arg_0]
0x1800191c2  mov     [rbp+arg_8], 3
0x1800191c9  mov     r8, rdi
0x1800191cc  mov     [rbp+arg_0], 10h
0x1800191d3  lea     rdx, [rbp+arg_8]
0x1800191d7  lea     rcx, aMachinecacheQm; "MachineCache\\QMId"
0x1800191de  call    cs:__imp_?SetFalconKeyValue@@YAJPEB_WPEAKPEBX1@Z; SetFalconKeyValue(wchar_t const *,ulong *,void const *,ulong *)
0x1800191e4  mov     ebx, eax
0x1800191e6  test    eax, eax
0x1800191e8  jz      short loc_18001925C
0x1800191ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800191f1  mov     edi, 1
0x1800191f6  cmp     rcx, rsi
0x1800191f9  jz      short loc_18001921D
0x1800191fb  test    [rcx+0E4h], dil
0x180019202  jz      short loc_18001921D
0x180019204  mov     rcx, [rcx+0D8h]
0x18001920b  lea     edx, [rdi+32h]
0x18001920e  mov     r9d, eax
0x180019211  lea     r8, WPP_29ec7c04fef53c01da80d97243eda25e_Traceguids
0x180019218  call    WPP_SF_d
0x18001921d  lea     r9, aMachinecacheQm; "MachineCache\\QMId"
0x180019224  mov     r8d, edi; unsigned __int16
0x180019227  mov     edx, ebx; dwMessageId
0x180019229  mov     ecx, 0C00007D1h; unsigned int
0x18001922e  call    ?EvReportWithError@@YAXKJGZZ; EvReportWithError(ulong,long,ushort,...)
0x180019233  test    ebx, ebx
0x180019235  jle     short loc_180019242
0x180019237  movzx   ebx, bx
0x18001923a  or      ebx, 80070000h
0x180019240  test    ebx, ebx
0x180019242  jns     short loc_180019258
0x180019244  mov     r8d, 469h; unsigned __int16
0x18001924a  lea     rdx, aCqmgr; "cqmgr"
0x180019251  mov     ecx, ebx; int
0x180019253  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180019258  mov     eax, ebx
0x18001925a  jmp     short loc_18001926B
0x18001925c  lea     rcx, aSysprep; "Sysprep"
0x180019263  call    cs:__imp_?DeleteFalconKeyValue@@YAJPEB_W@Z; DeleteFalconKeyValue(wchar_t const *)
0x180019269  xor     eax, eax
0x18001926b  mov     rbx, [rsp+30h+arg_18]
0x180019270  add     rsp, 30h
0x180019274  pop     rdi
0x180019275  pop     rsi
0x180019276  pop     rbp
0x180019277  retn
0x180019278  mov     rcx, cs:WPP_GLOBAL_Control
0x18001927f  lea     rsi, WPP_GLOBAL_Control
0x180019286  mov     edi, 1
0x18001928b  cmp     rcx, rsi
0x18001928e  jz      short loc_1800192B2
0x180019290  test    [rcx+0E4h], dil
0x180019297  jz      short loc_1800192B2
0x180019299  mov     rcx, [rcx+0D8h]
0x1800192a0  lea     edx, [rdi+33h]
0x1800192a3  mov     r9d, ebx
0x1800192a6  lea     r8, WPP_29ec7c04fef53c01da80d97243eda25e_Traceguids
0x1800192ad  call    WPP_SF_d
0x1800192b2  lea     r9, aMachinecacheQm; "MachineCache\\QMId"
0x1800192b9  mov     r8d, edi; unsigned __int16
0x1800192bc  mov     edx, ebx; dwMessageId
0x1800192be  mov     ecx, 0C00007D0h; unsigned int
0x1800192c3  call    ?EvReportWithError@@YAXKJGZZ; EvReportWithError(ulong,long,ushort,...)
0x1800192c8  test    ebx, ebx
0x1800192ca  jle     short loc_1800192D7
0x1800192cc  movzx   ebx, bx
0x1800192cf  or      ebx, 80070000h
0x1800192d5  test    ebx, ebx
0x1800192d7  jns     loc_180019258
0x1800192dd  mov     r8d, 46Ah
0x1800192e3  jmp     loc_18001924A
```
