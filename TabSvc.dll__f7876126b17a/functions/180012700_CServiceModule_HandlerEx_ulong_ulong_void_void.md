# CServiceModule::HandlerEx(ulong,ulong,void *,void *)

- ea: `0x180012700`
- end: `0x180012b5c`
- name: `?HandlerEx@CServiceModule@@QEAAKKKPEAX0@Z`
- size: `1116`
- prototype: `__int64 __fastcall(CServiceModule *this, int, int, _DWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x1800126e0`

## callees

- `0x180010c30`
- `0x180012700`
- `0x180014890`
- `0x18001bbe0`
- `0x18002b3a8`
- `0x18002b404`
- `0x18002b478`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x180012a6d`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x180012a6d`
- `ntdll!EtwEventWriteTransfer` at `0x18001283c`
- `ntdll!EtwEventWriteTransfer` at `0x18001283c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800129a2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180012aa0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800129a2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180012aa0`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180012a93`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180012a93`

## string_xrefs

- `0x180012983`: `PENSERVICE_CServiceModule::_StopServiceAsync`
- `0x1800129c6`: `PENSERVICE_CServiceModule::_StopServiceAsync`
- `0x180012742`: `PENSERVICE_CServiceModule::HandlerEx`
- `0x180012877`: `PENSERVICE_CServiceModule::HandlerEx`
- `0x1800128bc`: `PENSERVICE_CServiceModule::HandlerEx`
- `0x180012900`: `PENSERVICE_CServiceModule::HandlerEx`
- `0x180012944`: `PENSERVICE_CServiceModule::HandlerEx`
- `0x1800129f9`: `PENSERVICE_CServiceModule::HandlerEx`
- `0x180012a47`: `PENSERVICE_CServiceModule::HandlerEx`
- `0x180012ae9`: `PENSERVICE_CServiceModule::HandlerEx`

## pseudocode

```c
__int64 __fastcall CServiceModule::HandlerEx(CServiceModule *this, int a2, int a3, _DWORD *a4)
{
  struct _GUID *v7; // rcx
  int v8; // eax
  struct _SLIST_ENTRY *v9; // rax
  _DWORD v11[2]; // [rsp+30h] [rbp-78h] BYREF
  _DWORD v12[2]; // [rsp+38h] [rbp-70h] BYREF
  __int64 v13; // [rsp+40h] [rbp-68h]
  __int16 *v14; // [rsp+48h] [rbp-60h] BYREF
  int v15; // [rsp+50h] [rbp-58h]
  int v16; // [rsp+54h] [rbp-54h]
  char *v17; // [rsp+58h] [rbp-50h]
  int v18; // [rsp+60h] [rbp-48h]
  int v19; // [rsp+64h] [rbp-44h]
  _DWORD *v20; // [rsp+68h] [rbp-40h]
  __int64 v21; // [rsp+70h] [rbp-38h]

  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      86,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::HandlerEx");
  if ( (unsigned int)dword_1800411A8 > 5
    && (qword_1800411B8 & 0x4000000) != 0
    && (qword_1800411C0 & 0x4000000) == qword_1800411C0 )
  {
    v11[0] = a2;
    v20 = v11;
    v12[1] = 5;
    v14 = (__int16 *)off_1800411B0;
    v21 = 4;
    v12[0] = 184549376;
    v13 = 0x4000000;
    v15 = *(unsigned __int16 *)off_1800411B0;
    v17 = byte_18003A2B3;
    v16 = 2;
    v18 = 59;
    v19 = 1;
    v11[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EtwEventWriteTransfer(qword_1800411C8, v12, 0, 0, 3, &v14);
  }
  switch ( a2 )
  {
    case 1:
      if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
        WPP_SF_s(
          *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
          90,
          WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
          "PENSERVICE_CServiceModule::HandlerEx");
      CServiceModule::SetServiceStatusHelper((CServiceModule *)&_Module, 3u);
      if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
        WPP_SF_s(
          *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
          62,
          WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
          "PENSERVICE_CServiceModule::_StopServiceAsync");
      SetEvent(qword_180041290);
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control )
      {
        if ( (WPP_GLOBAL_Control[1].Data4[4] & 0x10) == 0 )
          goto LABEL_45;
        WPP_SF_s(
          *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
          63,
          WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
          "PENSERVICE_CServiceModule::_StopServiceAsync");
        goto LABEL_44;
      }
      return 1;
    case 2:
      if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
        WPP_SF_s(
          *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
          88,
          WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
          "PENSERVICE_CServiceModule::HandlerEx");
      CServiceModule::SetServiceStatusHelper((CServiceModule *)&_Module, 7u);
      goto LABEL_44;
    case 3:
      if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
        WPP_SF_s(
          *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
          89,
          WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
          "PENSERVICE_CServiceModule::HandlerEx");
      CServiceModule::SetServiceStatusHelper((CServiceModule *)&_Module, 4u);
      goto LABEL_44;
    case 4:
      if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
        WPP_SF_s(
          *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
          87,
          WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
          "PENSERVICE_CServiceModule::HandlerEx");
      CServiceModule::SetServiceStatusHelper((CServiceModule *)&_Module, dword_180041244);
      goto LABEL_44;
    case 11:
      goto LABEL_37;
    case 13:
      if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
        WPP_SF_sd(
          *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
          92,
          (unsigned int)WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
          (unsigned int)"PENSERVICE_CServiceModule::HandlerEx",
          a3);
LABEL_37:
      v9 = (struct _SLIST_ENTRY *)_aligned_malloc(0x30u, 0x10u);
      if ( v9 )
      {
        LODWORD(v9[1].Next) = a2;
        HIDWORD(v9[1].Next) = a3;
        *((_DWORD *)&v9[1].Next + 2) = -1;
        v9[2].Next = 0;
        InterlockedPushEntrySList(&ListHead, v9);
        SetEvent(hEvent);
        v8 = 0;
      }
      else
      {
        v8 = -2147024882;
      }
      goto LABEL_40;
    case 14:
      if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
        WPP_SF_sd(
          *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
          91,
          (unsigned int)WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
          (unsigned int)"PENSERVICE_CServiceModule::HandlerEx",
          a3);
      v8 = CServiceModule::AddScmEvent((CServiceModule *)&_Module, a2, a3, a4[1], 0);
LABEL_40:
      if ( v8 >= 0 )
        goto LABEL_44;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control )
      {
        if ( (WPP_GLOBAL_Control[1].Data4[4] & 4) != 0 )
        {
          WPP_SF_sL(*(_QWORD *)&WPP_GLOBAL_Control[1].Data1);
LABEL_44:
          v7 = WPP_GLOBAL_Control;
        }
LABEL_45:
        if ( v7 != (struct _GUID *)&WPP_GLOBAL_Control && (v7[1].Data4[4] & 0x10) != 0 )
          WPP_SF_s(
            *(_QWORD *)&v7[1].Data1,
            94,
            WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
            "PENSERVICE_CServiceModule::HandlerEx");
      }
      return 1;
    default:
      goto LABEL_44;
  }
}

```

## disassembly

```asm
0x180012700  push    rbx
0x180012702  push    rbp
0x180012703  push    rsi
0x180012704  push    rdi
0x180012705  push    r14
0x180012707  sub     rsp, 80h
0x18001270e  mov     rax, cs:__security_cookie
0x180012715  xor     rax, rsp
0x180012718  mov     [rsp+0A8h+var_30], rax
0x18001271d  mov     rsi, r9
0x180012720  mov     ebx, r8d
0x180012723  mov     edi, edx
0x180012725  mov     rcx, cs:WPP_GLOBAL_Control
0x18001272c  lea     rbp, WPP_GLOBAL_Control
0x180012733  cmp     rcx, rbp
0x180012736  jz      short loc_18001275A
0x180012738  test    byte ptr [rcx+1Ch], 10h
0x18001273c  jz      short loc_18001275A
0x18001273e  mov     rcx, [rcx+10h]
0x180012742  lea     r9, aPenserviceCser_1; "PENSERVICE_CServiceModule::HandlerEx"
0x180012749  mov     edx, 56h ; 'V'
0x18001274e  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180012755  call    WPP_SF_s
0x18001275a  mov     eax, cs:dword_1800411A8
0x180012760  xor     r14d, r14d
0x180012763  cmp     eax, 5
0x180012766  jbe     loc_180012842
0x18001276c  mov     rcx, cs:qword_1800411C0
0x180012773  mov     rax, cs:qword_1800411B8
0x18001277a  bt      rax, 1Ah
0x18001277f  jnb     loc_180012842
0x180012785  mov     rax, rcx
0x180012788  and     eax, 4000000h
0x18001278d  cmp     rax, rcx
0x180012790  jnz     loc_180012842
0x180012796  lea     rax, [rsp+0A8h+var_78]
0x18001279b  mov     [rsp+0A8h+var_78], edi
0x18001279f  mov     [rsp+0A8h+var_40], rax
0x1800127a4  lea     rcx, _TraceLoggingMetadata
0x1800127ab  movzx   eax, cs:word_18003A2A9
0x1800127b2  lea     rdx, [rsp+0A8h+var_70]
0x1800127b7  mov     [rsp+0A8h+var_6C], eax
0x1800127bb  xor     r9d, r9d
0x1800127be  mov     rax, cs:off_1800411B0
0x1800127c5  xor     r8d, r8d
0x1800127c8  mov     [rsp+0A8h+var_60], rax
0x1800127cd  mov     [rsp+0A8h+var_38], 4
0x1800127d6  mov     [rsp+0A8h+var_70], 0B000000h
0x1800127de  mov     [rsp+0A8h+var_68], 4000000h
0x1800127e7  movzx   eax, word ptr [rax]
0x1800127ea  mov     [rsp+0A8h+var_58], eax
0x1800127ee  lea     rax, byte_18003A2B3
0x1800127f5  mov     [rsp+0A8h+var_50], rax
0x1800127fa  lea     rax, _TraceLoggingMetadataEnd
0x180012801  sub     eax, ecx
0x180012803  mov     [rsp+0A8h+var_54], 2
0x18001280b  mov     [rsp+0A8h+var_48], 3Bh ; ';'
0x180012813  mov     [rsp+0A8h+var_44], 1
0x18001281b  mov     [rsp+0A8h+var_74], eax
0x18001281f  mov     eax, [rsp+0A8h+var_74]
0x180012823  mov     rcx, cs:qword_1800411C8
0x18001282a  lea     rax, [rsp+0A8h+var_60]
0x18001282f  mov     [rsp+0A8h+var_80], rax
0x180012834  mov     dword ptr [rsp+0A8h+var_88], 3
0x18001283c  call    cs:__imp_EtwEventWriteTransfer
0x180012842  lea     eax, [rdi-1]; switch 14 cases
0x180012845  cmp     eax, 0Dh
0x180012848  ja      def_18001285F; jumptable 000000018001285F default case, cases 5-10,12
0x18001284e  lea     rcx, __ImageBase
0x180012855  mov     eax, ds:(jpt_18001285F - 180000000h)[rcx+rax*4]
0x18001285c  add     rax, rcx
0x18001285f  jmp     rax; switch jump
0x180012861  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 000000018001285F case 4
0x180012868  cmp     rcx, rbp
0x18001286b  jz      short loc_18001288F
0x18001286d  test    byte ptr [rcx+1Ch], 10h
0x180012871  jz      short loc_18001288F
0x180012873  mov     rcx, [rcx+10h]
0x180012877  lea     r9, aPenserviceCser_1; "PENSERVICE_CServiceModule::HandlerEx"
0x18001287e  mov     edx, 57h ; 'W'
0x180012883  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x18001288a  call    WPP_SF_s
0x18001288f  mov     edx, cs:dword_180041244; unsigned int
0x180012895  lea     rcx, ?_Module@@3VCServiceModule@@A; this
0x18001289c  call    ?SetServiceStatusHelper@CServiceModule@@QEAAXK@Z; CServiceModule::SetServiceStatusHelper(ulong)
0x1800128a1  jmp     def_18001285F; jumptable 000000018001285F default case, cases 5-10,12
0x1800128a6  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 000000018001285F case 2
0x1800128ad  cmp     rcx, rbp
0x1800128b0  jz      short loc_1800128D4
0x1800128b2  test    byte ptr [rcx+1Ch], 10h
0x1800128b6  jz      short loc_1800128D4
0x1800128b8  mov     rcx, [rcx+10h]
0x1800128bc  lea     r9, aPenserviceCser_1; "PENSERVICE_CServiceModule::HandlerEx"
0x1800128c3  mov     edx, 58h ; 'X'
0x1800128c8  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x1800128cf  call    WPP_SF_s
0x1800128d4  mov     edx, 7; unsigned int
0x1800128d9  lea     rcx, ?_Module@@3VCServiceModule@@A; this
0x1800128e0  call    ?SetServiceStatusHelper@CServiceModule@@QEAAXK@Z; CServiceModule::SetServiceStatusHelper(ulong)
0x1800128e5  jmp     def_18001285F; jumptable 000000018001285F default case, cases 5-10,12
0x1800128ea  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 000000018001285F case 3
0x1800128f1  cmp     rcx, rbp
0x1800128f4  jz      short loc_180012918
0x1800128f6  test    byte ptr [rcx+1Ch], 10h
0x1800128fa  jz      short loc_180012918
0x1800128fc  mov     rcx, [rcx+10h]
0x180012900  lea     r9, aPenserviceCser_1; "PENSERVICE_CServiceModule::HandlerEx"
0x180012907  mov     edx, 59h ; 'Y'
0x18001290c  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180012913  call    WPP_SF_s
0x180012918  mov     edx, 4; unsigned int
0x18001291d  lea     rcx, ?_Module@@3VCServiceModule@@A; this
0x180012924  call    ?SetServiceStatusHelper@CServiceModule@@QEAAXK@Z; CServiceModule::SetServiceStatusHelper(ulong)
0x180012929  jmp     def_18001285F; jumptable 000000018001285F default case, cases 5-10,12
0x18001292e  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 000000018001285F case 1
0x180012935  cmp     rcx, rbp
0x180012938  jz      short loc_18001295C
0x18001293a  test    byte ptr [rcx+1Ch], 10h
0x18001293e  jz      short loc_18001295C
0x180012940  mov     rcx, [rcx+10h]
0x180012944  lea     r9, aPenserviceCser_1; "PENSERVICE_CServiceModule::HandlerEx"
0x18001294b  mov     edx, 5Ah ; 'Z'
0x180012950  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180012957  call    WPP_SF_s
0x18001295c  mov     edx, 3; unsigned int
0x180012961  lea     rcx, ?_Module@@3VCServiceModule@@A; this
0x180012968  call    ?SetServiceStatusHelper@CServiceModule@@QEAAXK@Z; CServiceModule::SetServiceStatusHelper(ulong)
0x18001296d  mov     rcx, cs:WPP_GLOBAL_Control
0x180012974  cmp     rcx, rbp
0x180012977  jz      short loc_18001299B
0x180012979  test    byte ptr [rcx+1Ch], 10h
0x18001297d  jz      short loc_18001299B
0x18001297f  mov     rcx, [rcx+10h]
0x180012983  lea     r9, aPenserviceCser_10; "PENSERVICE_CServiceModule::_StopService"...
0x18001298a  mov     edx, 3Eh ; '>'
0x18001298f  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180012996  call    WPP_SF_s
0x18001299b  mov     rcx, cs:qword_180041290; hEvent
0x1800129a2  call    cs:__imp_SetEvent
0x1800129a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800129af  cmp     rcx, rbp
0x1800129b2  jz      loc_180012B01
0x1800129b8  test    byte ptr [rcx+1Ch], 10h
0x1800129bc  jz      loc_180012ADA
0x1800129c2  mov     rcx, [rcx+10h]
0x1800129c6  lea     r9, aPenserviceCser_10; "PENSERVICE_CServiceModule::_StopService"...
0x1800129cd  mov     edx, 3Fh ; '?'
0x1800129d2  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x1800129d9  call    WPP_SF_s
0x1800129de  jmp     def_18001285F; jumptable 000000018001285F default case, cases 5-10,12
0x1800129e3  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 000000018001285F case 14
0x1800129ea  cmp     rcx, rbp
0x1800129ed  jz      short loc_180012A15
0x1800129ef  test    byte ptr [rcx+1Ch], 10h
0x1800129f3  jz      short loc_180012A15
0x1800129f5  mov     rcx, [rcx+10h]
0x1800129f9  lea     r9, aPenserviceCser_1; "PENSERVICE_CServiceModule::HandlerEx"
0x180012a00  mov     edx, 5Bh ; '['
0x180012a05  mov     dword ptr [rsp+0A8h+var_88], ebx
0x180012a09  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180012a10  call    WPP_SF_sd
0x180012a15  mov     r9d, [rsi+4]; unsigned int
0x180012a19  lea     rcx, ?_Module@@3VCServiceModule@@A; this
0x180012a20  mov     r8d, ebx; unsigned int
0x180012a23  mov     [rsp+0A8h+var_88], r14; void *
0x180012a28  mov     edx, edi; unsigned int
0x180012a2a  call    ?AddScmEvent@CServiceModule@@QEAAJKKKPEAX@Z; CServiceModule::AddScmEvent(ulong,ulong,ulong,void *)
0x180012a2f  jmp     short loc_180012AB0
0x180012a31  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 000000018001285F case 13
0x180012a38  cmp     rcx, rbp
0x180012a3b  jz      short loc_180012A63; jumptable 000000018001285F case 11
0x180012a3d  test    byte ptr [rcx+1Ch], 10h
0x180012a41  jz      short loc_180012A63; jumptable 000000018001285F case 11
0x180012a43  mov     rcx, [rcx+10h]
0x180012a47  lea     r9, aPenserviceCser_1; "PENSERVICE_CServiceModule::HandlerEx"
0x180012a4e  mov     edx, 5Ch ; '\'
0x180012a53  mov     dword ptr [rsp+0A8h+var_88], ebx
0x180012a57  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180012a5e  call    WPP_SF_sd
0x180012a63  mov     edx, 10h; jumptable 000000018001285F case 11
0x180012a68  mov     ecx, 30h ; '0'; Size
0x180012a6d  call    cs:__imp__aligned_malloc
0x180012a73  test    rax, rax
0x180012a76  jz      short loc_180012AAB
0x180012a78  mov     rdx, rax; ListEntry
0x180012a7b  mov     [rax+10h], edi
0x180012a7e  lea     rcx, ListHead; ListHead
0x180012a85  mov     [rax+14h], ebx
0x180012a88  mov     dword ptr [rax+18h], 0FFFFFFFFh
0x180012a8f  mov     [rax+20h], r14
0x180012a93  call    cs:__imp_InterlockedPushEntrySList
0x180012a99  mov     rcx, cs:hEvent; hEvent
0x180012aa0  call    cs:__imp_SetEvent
0x180012aa6  mov     eax, r14d
0x180012aa9  jmp     short loc_180012AB0
0x180012aab  mov     eax, 8007000Eh
0x180012ab0  test    eax, eax
0x180012ab2  jns     short def_18001285F; jumptable 000000018001285F default case, cases 5-10,12
0x180012ab4  mov     rcx, cs:WPP_GLOBAL_Control
0x180012abb  cmp     rcx, rbp
0x180012abe  jz      short loc_180012B01
0x180012ac0  test    byte ptr [rcx+1Ch], 4
0x180012ac4  jz      short loc_180012ADA
0x180012ac6  mov     rcx, [rcx+10h]
0x180012aca  mov     dword ptr [rsp+0A8h+var_88], eax
0x180012ace  call    WPP_SF_sL
0x180012ad3  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 000000018001285F default case, cases 5-10,12
0x180012ada  cmp     rcx, rbp
0x180012add  jz      short loc_180012B01
0x180012adf  test    byte ptr [rcx+1Ch], 10h
0x180012ae3  jz      short loc_180012B01
0x180012ae5  mov     rcx, [rcx+10h]
0x180012ae9  lea     r9, aPenserviceCser_1; "PENSERVICE_CServiceModule::HandlerEx"
0x180012af0  mov     edx, 5Eh ; '^'
0x180012af5  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180012afc  call    WPP_SF_s
0x180012b01  mov     eax, 1
0x180012b06  mov     rcx, [rsp+0A8h+var_30]
0x180012b0b  xor     rcx, rsp; StackCookie
0x180012b0e  call    __security_check_cookie
0x180012b13  add     rsp, 80h
0x180012b1a  pop     r14
0x180012b1c  pop     rdi
0x180012b1d  pop     rsi
0x180012b1e  pop     rbp
0x180012b1f  pop     rbx
0x180012b20  retn
```
