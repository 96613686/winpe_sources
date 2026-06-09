# MbbNdisMiniportOidRequestCompletion(void *,_MBB_REQUEST_CONTEXT *,int)

- ea: `0x1400124a0`
- end: `0x140012888`
- name: `?MbbNdisMiniportOidRequestCompletion@@YAXPEAXPEAU_MBB_REQUEST_CONTEXT@@H@Z`
- size: `1000`
- prototype: `void __fastcall(void *, struct _MBB_REQUEST_CONTEXT *, int)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400010b4`
- `0x140001db8`
- `0x1400051ac`
- `0x14000f900`
- `0x1400124a0`
- `0x140018518`
- `0x140019f78`
- `0x14001dc00`
- `0x140041664`
- `0x140047e50`
- `0x140047e90`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140012796`
- `ntoskrnl!KeSetEvent` at `0x140012796`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012737`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012776`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012737`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012776`

## pseudocode

```c
void __fastcall MbbNdisMiniportOidRequestCompletion(void *a1, struct _MBB_REQUEST_CONTEXT *a2, int a3)
{
  struct _MBB_REQUEST_CONTEXT *v3; // rbx
  char v4; // r15
  char *v5; // rsi
  __int64 v6; // rcx
  bool v7; // zf
  __int64 v8; // r14
  __int32 v9; // ecx
  int v10; // eax
  const char *OidName; // rax
  __int64 v12; // r9
  __int64 v13; // r11
  void (__fastcall *v14)(struct _MBB_REQUEST_CONTEXT *, _QWORD); // rax
  void *v15; // rcx
  void *v16; // rcx
  int v17; // [rsp+28h] [rbp-B1h]
  int v18; // [rsp+C0h] [rbp-19h] BYREF
  _QWORD v19[2]; // [rsp+C8h] [rbp-11h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v20; // [rsp+D8h] [rbp-1h] BYREF

  v19[1] = a1;
  v3 = a2;
  v18 = a3;
  if ( a3 == 65537 )
  {
    v4 = 1;
    v18 = 0;
  }
  else
  {
    v4 = 0;
    if ( a3 )
    {
      v5 = (char *)a2 + 80;
      v7 = a3 == 259;
      goto LABEL_7;
    }
  }
  v5 = (char *)a2 + 80;
  v6 = *((_QWORD *)a2 + 10);
  if ( (*(_DWORD *)(v6 + 4) & 8) == 0 )
    goto LABEL_8;
  v18 = 1076035585;
  v7 = (*(_DWORD *)(v6 + 4) & 0x10) == 0;
LABEL_7:
  if ( !v7 )
  {
LABEL_8:
    v8 = -1;
    v19[0] = _InterlockedExchange64((volatile __int64 *)a2 + 53, -1);
    if ( v19[0] == -1 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v17 = *((_DWORD *)a2 + 4);
        LOBYTE(a2) = 3;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)a2,
          3,
          12,
          (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids,
          v17);
      }
    }
    else
    {
      *((_DWORD *)a2 + 112) = v18;
      v9 = _InterlockedExchange((volatile __int32 *)a2 + 114, 4);
      if ( ((v9 - 1) & 0xFFFFFFFD) != 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v10 = *((_DWORD *)a2 + 4);
          LOBYTE(a2) = 4;
          WPP_RECORDER_SF_DD(
            WPP_GLOBAL_Control->DeviceExtension,
            (_DWORD)a2,
            3,
            11,
            (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids,
            v10,
            v9);
        }
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_DLd(
            WPP_GLOBAL_Control->DeviceExtension,
            (_DWORD)a2,
            a3,
            10,
            (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids,
            *((_DWORD *)a2 + 4),
            v9,
            v18);
        OidName = GetOidName(*(_DWORD *)(v19[0] + 32LL));
        do
          ++v8;
        while ( OidName[v8] );
        MbbWriteEvent(
          &REQUEST_COMPLETE_EVENT,
          0,
          0,
          0xAu,
          v13 + 32,
          4,
          v19,
          8,
          v19[0] + 32LL,
          4,
          OidName,
          v8 + 1,
          v12 + 16,
          8,
          v12 + 24,
          8,
          v12 + 4,
          4,
          v19[0] + 52LL,
          4,
          v19[0] + 56LL,
          4,
          &v18,
          4);
        MbbCompleteRequest(v3, v18);
      }
    }
  }
  v14 = *(void (__fastcall **)(struct _MBB_REQUEST_CONTEXT *, _QWORD))(*(_QWORD *)v5 + 80LL);
  if ( v14 )
    v14(v3, (unsigned int)v18);
  v15 = (void *)*((_QWORD *)v3 + 70);
  if ( v15 )
  {
    ExFreePoolWithTag(v15, 0);
    *((_QWORD *)v3 + 70) = 0;
  }
  if ( v4 )
    goto LABEL_26;
  if ( v18 == 259 )
    return;
  if ( v18 != 1076035585 )
  {
LABEL_26:
    v16 = (void *)*((_QWORD *)v3 + 71);
    if ( v16 )
    {
      ExFreePoolWithTag(v16, 0);
      *((_QWORD *)v3 + 71) = 0;
    }
    KeSetEvent((PRKEVENT)((char *)v3 + 56), 0, 0);
    MbbReqMgrDerefRequest(v3);
  }
  if ( v18 != 259 && v18 != 1076035585 && v18 && **(_DWORD **)v5 == 234946819 )
  {
    if ( (unsigned int)dword_14005E0C8 > 5 )
    {
      LODWORD(a2) = 0;
      if ( (qword_14005E0D8 & 0x400000000000LL) != 0 && (qword_14005E0E0 & 0x400000000000LL) == qword_14005E0E0 )
        tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_14005E0C8, (unsigned __int8 *)&byte_140058797, 0, 0, 2u, &v20);
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        3,
        13,
        (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids,
        v18);
    }
  }
}

```

## disassembly

```asm
0x1400124a0  push    rbp
0x1400124a2  push    rbx
0x1400124a3  push    rsi
0x1400124a4  push    r12
0x1400124a6  push    r13
0x1400124a8  push    r14
0x1400124aa  push    r15
0x1400124ac  lea     rbp, [rsp-27h]
0x1400124b1  sub     rsp, 100h
0x1400124b8  mov     rax, cs:__security_cookie
0x1400124bf  xor     rax, rsp
0x1400124c2  mov     [rbp+57h+var_38], rax
0x1400124c6  mov     [rbp+57h+var_60], rcx
0x1400124ca  mov     rbx, rdx
0x1400124cd  mov     [rbp+57h+var_70], r8d
0x1400124d1  mov     r11, rcx
0x1400124d4  lea     r13, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x1400124db  lea     r12, WPP_RECORDER_INITIALIZED
0x1400124e2  cmp     r8d, 10001h
0x1400124e9  jnz     short loc_1400124F7
0x1400124eb  mov     r15b, 1
0x1400124ee  mov     [rbp+57h+var_70], 0
0x1400124f5  jmp     short loc_1400124FF
0x1400124f7  xor     r15b, r15b
0x1400124fa  test    r8d, r8d
0x1400124fd  jnz     short loc_14001251B
0x1400124ff  lea     rsi, [rdx+50h]
0x140012503  mov     rcx, [rsi]
0x140012506  mov     eax, [rcx+4]
0x140012509  test    al, 8
0x14001250b  jz      short loc_14001252C
0x14001250d  mov     [rbp+57h+var_70], 40230001h
0x140012514  mov     eax, [rcx+4]
0x140012517  test    al, 10h
0x140012519  jmp     short loc_140012526
0x14001251b  lea     rsi, [rdx+50h]
0x14001251f  cmp     r8d, 103h
0x140012526  jz      loc_140012712
0x14001252c  or      r14, 0FFFFFFFFFFFFFFFFh
0x140012530  mov     [rbp+57h+var_68], 0
0x140012538  mov     rax, r14
0x14001253b  xchg    rax, [rdx+1A8h]
0x140012542  mov     [rbp+57h+var_68], rax
0x140012546  cmp     rax, r14
0x140012549  jz      loc_1400126E0
0x14001254f  mov     eax, [rbp+57h+var_70]
0x140012552  lea     ecx, [r14+5]
0x140012556  mov     [rdx+1C0h], eax
0x14001255c  xchg    ecx, [rdx+1C8h]
0x140012562  lea     eax, [rcx-1]
0x140012565  test    eax, 0FFFFFFFDh
0x14001256a  jz      short loc_1400125A8
0x14001256c  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140012573  jz      loc_140012712
0x140012579  mov     eax, [rdx+10h]
0x14001257c  lea     r9d, [r14+0Ch]
0x140012580  mov     dword ptr [rsp+130h+var_100], ecx
0x140012584  lea     r8d, [r14+4]
0x140012588  mov     rcx, cs:WPP_GLOBAL_Control
0x14001258f  mov     dl, 4
0x140012591  mov     dword ptr [rsp+130h+var_108], eax
0x140012595  mov     [rsp+130h+var_110], r13
0x14001259a  mov     rcx, [rcx+40h]
0x14001259e  call    WPP_RECORDER_SF_DD
0x1400125a3  jmp     loc_140012712
0x1400125a8  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400125af  jz      short loc_1400125E2
0x1400125b1  mov     eax, [rbp+57h+var_70]
0x1400125b4  mov     r9d, 0Ah
0x1400125ba  mov     dword ptr [rsp+130h+var_F8], eax
0x1400125be  mov     eax, [rdx+10h]
0x1400125c1  mov     dword ptr [rsp+130h+var_100], ecx
0x1400125c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400125cc  mov     dword ptr [rsp+130h+var_108], eax
0x1400125d0  mov     [rsp+130h+var_110], r13
0x1400125d5  mov     rcx, [rcx+40h]
0x1400125d9  call    WPP_RECORDER_SF_DLd
0x1400125de  mov     r11, [rbp+57h+var_60]
0x1400125e2  mov     r9, [rbp+57h+var_68]
0x1400125e6  lea     r12, [r9+20h]
0x1400125ea  mov     ecx, [r12]; unsigned int
0x1400125ee  call    ?GetOidName@@YAPEBDK@Z; GetOidName(ulong)
0x1400125f3  mov     r13, rax
0x1400125f6  inc     r14
0x1400125f9  cmp     byte ptr [r14+rax], 0
0x1400125fe  jnz     short loc_1400125F6
0x140012600  mov     [rsp+130h+var_78], 4
0x14001260c  lea     rax, [r12+18h]
0x140012611  lea     rdx, [r9+4]
0x140012615  add     r11, 20h ; ' '
0x140012619  lea     r8, [r9+18h]
0x14001261d  add     r9, 10h
0x140012621  lea     r10d, [r14+1]
0x140012625  lea     r14, [rbp+57h+var_70]
0x140012629  mov     [rsp+130h+var_80], r14
0x140012631  lea     rcx, [r12+14h]
0x140012636  mov     r14d, 4
0x14001263c  mov     [rsp+130h+var_88], r14
0x140012644  mov     [rsp+130h+var_90], rax
0x14001264c  mov     [rsp+130h+var_98], r14
0x140012654  mov     [rsp+130h+var_A0], rcx
0x14001265c  lea     eax, [r14+4]
0x140012660  mov     [rsp+130h+var_A8], r14
0x140012668  lea     rcx, REQUEST_COMPLETE_EVENT; EventDescriptor
0x14001266f  mov     [rsp+130h+var_B0], rdx
0x140012677  xor     edx, edx; ActivityId
0x140012679  mov     [rsp+130h+var_B8], rax
0x14001267e  mov     [rsp+130h+var_C0], r8
0x140012683  xor     r8d, r8d; RelatedActivityId
0x140012686  mov     [rsp+130h+var_C8], rax
0x14001268b  mov     [rsp+130h+var_D0], r9
0x140012690  lea     r9d, [r14+6]; unsigned __int16
0x140012694  mov     [rsp+130h+var_D8], r10d
0x140012699  mov     [rsp+130h+var_E0], r13
0x14001269e  mov     [rsp+130h+var_E8], r14
0x1400126a3  mov     [rsp+130h+var_F0], r12
0x1400126a8  mov     [rsp+130h+var_F8], rax
0x1400126ad  lea     rax, [rbp+57h+var_68]
0x1400126b1  mov     [rsp+130h+var_100], rax
0x1400126b6  mov     [rsp+130h+var_108], r14
0x1400126bb  mov     [rsp+130h+var_110], r11
0x1400126c0  call    ?MbbWriteEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@1GZZ; MbbWriteEvent(_EVENT_DESCRIPTOR const *,_GUID *,_GUID *,ushort,...)
0x1400126c5  mov     edx, [rbp+57h+var_70]; int
0x1400126c8  mov     rcx, rbx; struct _MBB_REQUEST_CONTEXT *
0x1400126cb  call    ?MbbCompleteRequest@@YAXPEAU_MBB_REQUEST_CONTEXT@@H@Z; MbbCompleteRequest(_MBB_REQUEST_CONTEXT *,int)
0x1400126d0  lea     r12, WPP_RECORDER_INITIALIZED
0x1400126d7  lea     r13, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x1400126de  jmp     short loc_140012712
0x1400126e0  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400126e7  jz      short loc_140012712
0x1400126e9  mov     eax, [rdx+10h]
0x1400126ec  mov     r9d, 0Ch
0x1400126f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400126f9  mov     dword ptr [rsp+130h+var_108], eax
0x1400126fd  mov     [rsp+130h+var_110], r13
0x140012702  lea     r8d, [r9-9]
0x140012706  mov     rcx, [rcx+40h]
0x14001270a  mov     dl, r8b
0x14001270d  call    WPP_RECORDER_SF_d
0x140012712  mov     rax, [rsi]
0x140012715  mov     rax, [rax+50h]
0x140012719  test    rax, rax
0x14001271c  jz      short loc_140012729
0x14001271e  mov     edx, [rbp+57h+var_70]
0x140012721  mov     rcx, rbx
0x140012724  call    _guard_dispatch_icall
0x140012729  mov     rcx, [rbx+230h]; P
0x140012730  test    rcx, rcx
0x140012733  jz      short loc_14001274E
0x140012735  xor     edx, edx; Tag
0x140012737  call    cs:__imp_ExFreePoolWithTag
0x14001273e  nop     dword ptr [rax+rax+00h]
0x140012743  mov     qword ptr [rbx+230h], 0
0x14001274e  test    r15b, r15b
0x140012751  jnz     short loc_140012768
0x140012753  mov     eax, [rbp+57h+var_70]
0x140012756  cmp     eax, 103h
0x14001275b  jz      loc_140012868
0x140012761  cmp     eax, 40230001h
0x140012766  jz      short loc_1400127AA
0x140012768  mov     rcx, [rbx+238h]; P
0x14001276f  test    rcx, rcx
0x140012772  jz      short loc_14001278D
0x140012774  xor     edx, edx; Tag
0x140012776  call    cs:__imp_ExFreePoolWithTag
0x14001277d  nop     dword ptr [rax+rax+00h]
0x140012782  mov     qword ptr [rbx+238h], 0
0x14001278d  lea     rcx, [rbx+38h]; Event
0x140012791  xor     r8d, r8d; Wait
0x140012794  xor     edx, edx; Increment
0x140012796  call    cs:__imp_KeSetEvent
0x14001279d  nop     dword ptr [rax+rax+00h]
0x1400127a2  mov     rcx, rbx; struct _MBB_REQUEST_CONTEXT *
0x1400127a5  call    ?MbbReqMgrDerefRequest@@YAXPEAU_MBB_REQUEST_CONTEXT@@@Z; MbbReqMgrDerefRequest(_MBB_REQUEST_CONTEXT *)
0x1400127aa  mov     eax, [rbp+57h+var_70]
0x1400127ad  cmp     eax, 103h
0x1400127b2  jz      loc_140012868
0x1400127b8  cmp     eax, 40230001h
0x1400127bd  jz      loc_140012868
0x1400127c3  test    eax, eax
0x1400127c5  jz      loc_140012868
0x1400127cb  mov     rax, [rsi]
0x1400127ce  cmp     dword ptr [rax], 0E010103h
0x1400127d4  jnz     loc_140012868
0x1400127da  mov     eax, cs:dword_14005E0C8
0x1400127e0  cmp     eax, 5
0x1400127e3  jbe     short loc_140012837
0x1400127e5  mov     rcx, cs:qword_14005E0E0
0x1400127ec  mov     rdx, 400000000000h
0x1400127f6  mov     rax, cs:qword_14005E0D8
0x1400127fd  test    rdx, rax
0x140012800  jz      short loc_140012837
0x140012802  mov     rax, rcx
0x140012805  and     rax, rdx
0x140012808  cmp     rax, rcx
0x14001280b  jnz     short loc_140012837
0x14001280d  lea     rax, [rbp+57h+var_58]
0x140012811  xor     r9d, r9d
0x140012814  mov     [rsp+130h+var_108], rax
0x140012819  lea     rdx, byte_140058797
0x140012820  xor     r8d, r8d
0x140012823  mov     dword ptr [rsp+130h+var_110], 2
0x14001282b  lea     rcx, dword_14005E0C8
0x140012832  call    _tlgWriteTransfer_EtwWriteTransfer
0x140012837  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14001283e  jz      short loc_140012868
0x140012840  mov     rcx, cs:WPP_GLOBAL_Control
0x140012847  mov     r9d, 0Dh
0x14001284d  mov     eax, [rbp+57h+var_70]
0x140012850  mov     dl, 2
0x140012852  mov     dword ptr [rsp+130h+var_108], eax
0x140012856  mov     [rsp+130h+var_110], r13
0x14001285b  mov     rcx, [rcx+40h]
0x14001285f  lea     r8d, [r9-0Ah]
0x140012863  call    WPP_RECORDER_SF_d
0x140012868  mov     rcx, [rbp+57h+var_38]
0x14001286c  xor     rcx, rsp; StackCookie
0x14001286f  call    __security_check_cookie
0x140012874  add     rsp, 100h
0x14001287b  pop     r15
0x14001287d  pop     r14
0x14001287f  pop     r13
0x140012881  pop     r12
0x140012883  pop     rsi
0x140012884  pop     rbx
0x140012885  pop     rbp
0x140012886  retn
```
