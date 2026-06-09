# CBSSEntry::UpdateRSNAInfo(_WFC_BSS_ENTRY_FRAME_TYPE)

- ea: `0x1400287d0`
- end: `0x140028abb`
- name: `?UpdateRSNAInfo@CBSSEntry@@QEAAXW4_WFC_BSS_ENTRY_FRAME_TYPE@@@Z`
- size: `747`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, installer_update`

## callers

- `0x140014bf0`

## callees

- `0x14000d054`
- `0x14000f830`
- `0x14000fa60`
- `0x1400159e0`
- `0x14001de60`
- `0x140024b1c`
- `0x1400287d0`
- `0x1400291fc`
- `0x140029258`
- `0x14002b970`
- `0x1400e0100`

## pseudocode

```c
void __fastcall CBSSEntry::UpdateRSNAInfo(__int64 a1, unsigned int a2)
{
  int v4; // edx
  unsigned int AuthAlgoInfo; // eax
  char v6; // bl
  char v7; // r14
  int v8; // r14d
  unsigned int v9; // r8d
  int v10; // edx
  unsigned __int8 *v11; // [rsp+40h] [rbp-29h] BYREF
  unsigned __int8 *v12; // [rsp+48h] [rbp-21h] BYREF
  unsigned __int8 *v13[14]; // [rsp+50h] [rbp-19h] BYREF
  unsigned __int8 v14; // [rsp+D0h] [rbp+67h] BYREF
  unsigned int v15; // [rsp+E0h] [rbp+77h] BYREF
  unsigned int v16; // [rsp+E8h] [rbp+7Fh] BYREF

  v11 = 0;
  v12 = 0;
  v15 = 0;
  memset(v13, 0, 0x48u);
  v14 = 0;
  *(_DWORD *)(a1 + 452) = 0;
  *(_DWORD *)(a1 + 872) = 0;
  *(_WORD *)(a1 + 876) = 0;
  CBSSEntry::GetIEBlobFromBeaconOrProbeReponse(a1, a2, &v11, &v15);
  if ( !v11 || !v15 )
    return;
  if ( !(unsigned int)Dot11GetInfoElementFromIEBlob(v11, v15, 48, 0, &v14, (void **)&v12) )
  {
    if ( CDRollback_Dot11ParseRSNIE(v12, 1u, v14, (struct RSN_IE_INFO *)v13) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v4) = 2;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v4,
          1,
          69,
          (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids);
      }
      goto LABEL_33;
    }
    v16 = 0;
    AuthAlgoInfo = Dot11GetAuthAlgoInfo((struct RSN_IE_INFO *)v13, &v16);
    v6 = v16;
    v7 = v16;
    *(_DWORD *)(a1 + 872) |= AuthAlgoInfo;
    v8 = v7 & 1;
    if ( v8 && ((__int64)v13[1] & 1) != 0 )
      *(_DWORD *)(a1 + 888) |= 1u;
    if ( (v6 & 0x10) != 0 )
      *(_DWORD *)(a1 + 888) |= 0x10u;
    if ( (unsigned int)Feature_Bugfix_54405666__private_IsEnabledDeviceUsageNoInline() )
    {
      if ( (v6 & 0x30) == 0 && (*(_DWORD *)(a1 + 872) & 0x100) == 0 )
        goto LABEL_16;
    }
    else if ( (v6 & 0x30) == 0 )
    {
      goto LABEL_16;
    }
    if ( Dot11GetVendorElementFromIEBlob(v11, v15, v9) )
      *(_DWORD *)(a1 + 888) |= 0x200u;
LABEL_16:
    if ( ((__int64)v13[1] & 0xC0) != 0 )
      *(_DWORD *)(a1 + 888) |= 4u;
    if ( (v6 & 0xC) != 0 )
      *(_BYTE *)(a1 + 876) = 1;
    if ( (unsigned int)Feature_58744956__private_IsEnabledDeviceUsageNoInline() )
    {
      if ( ((v6 & 8) == 0 || (v6 & 0x12) != 0) && ((v6 & 4) == 0 || (v6 & 1) != 0) )
        goto LABEL_30;
    }
    else if ( (v6 & 0xA) != 8 && ((v6 & 4) == 0 || v8) )
    {
      goto LABEL_30;
    }
    *(_BYTE *)(a1 + 877) = 1;
LABEL_30:
    CBSSEntry::SetRsnAkmsAndCiphers((CBSSEntry *)a1, HIWORD(v13[0]), WORD2(v13[0]), v13[4], v13[3], v13[2], v13[6]);
  }
LABEL_33:
  if ( !(unsigned int)Dot11GetInfoElementFromIEBlob(v11, v15, 221, 32657408, &v14, (void **)&v12) )
  {
    if ( CDRollback_Dot11ParseRSNIE(v12 + 4, 0, v14 - 4, (struct RSN_IE_INFO *)v13) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = 2;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v10,
          1,
          70,
          (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids);
      }
    }
    else if ( LOWORD(v13[0]) == 1 )
    {
      v16 = 0;
      *(_DWORD *)(a1 + 872) |= Dot11GetAuthAlgoInfo((struct RSN_IE_INFO *)v13, &v16);
      CBSSEntry::SetRsnAkmsAndCiphers((CBSSEntry *)a1, HIWORD(v13[0]), WORD2(v13[0]), v13[4], v13[3], v13[2], v13[6]);
    }
  }
}

```

## disassembly

```asm
0x1400287d0  push    rbp
0x1400287d2  push    rbx
0x1400287d3  push    rdi
0x1400287d4  push    r13
0x1400287d6  push    r14
0x1400287d8  lea     rbp, [rsp-37h]
0x1400287dd  sub     rsp, 0A0h
0x1400287e4  mov     ebx, edx
0x1400287e6  mov     [rbp+57h+var_80], 0
0x1400287ee  xor     edx, edx; Val
0x1400287f0  mov     [rbp+57h+var_78], 0
0x1400287f8  mov     rdi, rcx
0x1400287fb  mov     [rbp+57h+arg_10], 0
0x140028802  lea     rcx, [rbp+57h+var_70]; void *
0x140028806  lea     r8d, [rdx+48h]; Size
0x14002880a  call    memset
0x14002880f  xor     eax, eax
0x140028811  mov     [rbp+57h+arg_0], 0
0x140028815  lea     r9, [rbp+57h+arg_10]
0x140028819  mov     [rdi+1C4h], eax
0x14002881f  lea     r8, [rbp+57h+var_80]
0x140028823  mov     dword ptr [rdi+368h], 0
0x14002882d  mov     edx, ebx
0x14002882f  mov     word ptr [rdi+36Ch], 0
0x140028838  mov     rcx, rdi
0x14002883b  call    ?GetIEBlobFromBeaconOrProbeReponse@CBSSEntry@@IEAAXW4_WFC_BSS_ENTRY_FRAME_TYPE@@PEAPEAEPEAK@Z; CBSSEntry::GetIEBlobFromBeaconOrProbeReponse(_WFC_BSS_ENTRY_FRAME_TYPE,uchar * *,ulong *)
0x140028840  cmp     [rbp+57h+var_80], 0
0x140028845  jz      loc_140028AAB
0x14002884b  cmp     [rbp+57h+arg_10], 0
0x14002884f  jz      loc_140028AAB
0x140028855  mov     edx, [rbp+57h+arg_10]; unsigned int
0x140028858  lea     rax, [rbp+57h+var_78]
0x14002885c  mov     rcx, [rbp+57h+var_80]; unsigned __int8 *
0x140028860  xor     r9d, r9d; unsigned int
0x140028863  mov     [rsp+0C0h+var_98], rax; void **
0x140028868  mov     r8b, 30h ; '0'; unsigned __int8
0x14002886b  lea     rax, [rbp+57h+arg_0]
0x14002886f  mov     [rsp+0C0h+var_A0], rax; unsigned __int8 *
0x140028874  call    ?Dot11GetInfoElementFromIEBlob@@YAHPEAEKEK0PEAPEAX@Z; Dot11GetInfoElementFromIEBlob(uchar *,ulong,uchar,ulong,uchar *,void * *)
0x140028879  lea     r14, WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids
0x140028880  mov     r13d, 1
0x140028886  lea     rbx, WPP_RECORDER_INITIALIZED
0x14002888d  test    eax, eax
0x14002888f  jnz     loc_1400289E5
0x140028895  mov     r8b, [rbp+57h+arg_0]; unsigned __int8
0x140028899  lea     r9, [rbp+57h+var_70]; struct RSN_IE_INFO *
0x14002889d  mov     rcx, [rbp+57h+var_78]; unsigned __int8 *
0x1400288a1  mov     dl, r13b; unsigned __int8
0x1400288a4  call    ?CDRollback_Dot11ParseRSNIE@@YAHPEAEEEPEAURSN_IE_INFO@@@Z; CDRollback_Dot11ParseRSNIE(uchar *,uchar,uchar,RSN_IE_INFO *)
0x1400288a9  test    eax, eax
0x1400288ab  jnz     loc_1400289BC
0x1400288b1  lea     rdx, [rbp+57h+arg_18]; unsigned int *
0x1400288b5  mov     [rbp+57h+arg_18], eax
0x1400288b8  lea     rcx, [rbp+57h+var_70]; struct RSN_IE_INFO *
0x1400288bc  call    ?Dot11GetAuthAlgoInfo@@YAKPEAURSN_IE_INFO@@PEAK@Z; Dot11GetAuthAlgoInfo(RSN_IE_INFO *,ulong *)
0x1400288c1  mov     ebx, [rbp+57h+arg_18]
0x1400288c4  mov     r14d, ebx
0x1400288c7  or      [rdi+368h], eax
0x1400288cd  and     r14d, r13d
0x1400288d0  jz      short loc_1400288DF
0x1400288d2  test    [rbp+57h+var_68], r13b
0x1400288d6  jz      short loc_1400288DF
0x1400288d8  or      [rdi+378h], r13d
0x1400288df  test    bl, 10h
0x1400288e2  jz      short loc_1400288EB
0x1400288e4  or      dword ptr [rdi+378h], 10h
0x1400288eb  call    Feature_Bugfix_54405666__private_IsEnabledDeviceUsageNoInline
0x1400288f0  test    eax, eax
0x1400288f2  jz      short loc_14002890D
0x1400288f4  test    bl, 30h
0x1400288f7  setz    cl
0x1400288fa  test    dword ptr [rdi+368h], 100h
0x140028904  setz    al
0x140028907  test    al, cl
0x140028909  jnz     short loc_14002892B
0x14002890b  jmp     short loc_140028912
0x14002890d  test    bl, 30h
0x140028910  jz      short loc_14002892B
0x140028912  mov     edx, [rbp+57h+arg_10]; unsigned int
0x140028915  mov     rcx, [rbp+57h+var_80]; unsigned __int8 *
0x140028919  call    ?Dot11GetVendorElementFromIEBlob@@YAPEAUDOT11_INFO_ELEMENT@@PEAEKK@Z; Dot11GetVendorElementFromIEBlob(uchar *,ulong,ulong)
0x14002891e  test    rax, rax
0x140028921  jz      short loc_14002892B
0x140028923  bts     dword ptr [rdi+378h], 9
0x14002892b  test    [rbp+57h+var_68], 0C0h
0x14002892f  jz      short loc_140028938
0x140028931  or      dword ptr [rdi+378h], 4
0x140028938  test    bl, 0Ch
0x14002893b  jz      short loc_140028944
0x14002893d  mov     [rdi+36Ch], r13b
0x140028944  call    Feature_58744956__private_IsEnabledDeviceUsageNoInline
0x140028949  test    eax, eax
0x14002894b  jz      short loc_140028963
0x14002894d  test    bl, 8
0x140028950  jz      short loc_140028957
0x140028952  test    bl, 12h
0x140028955  jz      short loc_140028975
0x140028957  test    bl, 4
0x14002895a  jz      short loc_14002897C
0x14002895c  test    r13b, bl
0x14002895f  jz      short loc_140028975
0x140028961  jmp     short loc_14002897C
0x140028963  mov     eax, ebx
0x140028965  and     al, 0Ah
0x140028967  cmp     al, 8
0x140028969  jz      short loc_140028975
0x14002896b  test    bl, 4
0x14002896e  jz      short loc_14002897C
0x140028970  test    r14d, r14d
0x140028973  jnz     short loc_14002897C
0x140028975  mov     [rdi+36Dh], r13b
0x14002897c  mov     rax, [rbp+57h+var_40]
0x140028980  mov     rcx, rdi; this
0x140028983  mov     r9, [rbp+57h+var_50]; unsigned __int8 *
0x140028987  movzx   r8d, [rbp+57h+var_6C]; unsigned __int16
0x14002898c  movzx   edx, [rbp+57h+var_6A]; unsigned __int16
0x140028990  mov     [rsp+0C0h+var_90], rax; unsigned __int8 *
0x140028995  mov     rax, [rbp+57h+var_60]
0x140028999  mov     [rsp+0C0h+var_98], rax; unsigned __int8 *
0x14002899e  mov     rax, [rbp+57h+var_58]
0x1400289a2  mov     [rsp+0C0h+var_A0], rax; unsigned __int8 *
0x1400289a7  call    ?SetRsnAkmsAndCiphers@CBSSEntry@@QEAAXGGPEAE000@Z; CBSSEntry::SetRsnAkmsAndCiphers(ushort,ushort,uchar *,uchar *,uchar *,uchar *)
0x1400289ac  lea     rbx, WPP_RECORDER_INITIALIZED
0x1400289b3  lea     r14, WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids
0x1400289ba  jmp     short loc_1400289E5
0x1400289bc  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400289c3  jz      short loc_1400289E5
0x1400289c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400289cc  mov     r9d, 45h ; 'E'
0x1400289d2  mov     r8d, r13d
0x1400289d5  mov     [rsp+0C0h+var_A0], r14
0x1400289da  mov     dl, 2
0x1400289dc  mov     rcx, [rcx+40h]
0x1400289e0  call    WPP_RECORDER_SF_
0x1400289e5  mov     edx, [rbp+57h+arg_10]; unsigned int
0x1400289e8  lea     rax, [rbp+57h+var_78]
0x1400289ec  mov     rcx, [rbp+57h+var_80]; unsigned __int8 *
0x1400289f0  mov     r9d, 1F25000h; unsigned int
0x1400289f6  mov     [rsp+0C0h+var_98], rax; void **
0x1400289fb  mov     r8b, 0DDh; unsigned __int8
0x1400289fe  lea     rax, [rbp+57h+arg_0]
0x140028a02  mov     [rsp+0C0h+var_A0], rax; unsigned __int8 *
0x140028a07  call    ?Dot11GetInfoElementFromIEBlob@@YAHPEAEKEK0PEAPEAX@Z; Dot11GetInfoElementFromIEBlob(uchar *,ulong,uchar,ulong,uchar *,void * *)
0x140028a0c  test    eax, eax
0x140028a0e  jnz     loc_140028AAB
0x140028a14  mov     r8b, [rbp+57h+arg_0]
0x140028a18  lea     r9, [rbp+57h+var_70]; struct RSN_IE_INFO *
0x140028a1c  mov     rcx, [rbp+57h+var_78]
0x140028a20  sub     r8b, 4; unsigned __int8
0x140028a24  add     rcx, 4; unsigned __int8 *
0x140028a28  xor     edx, edx; unsigned __int8
0x140028a2a  call    ?CDRollback_Dot11ParseRSNIE@@YAHPEAEEEPEAURSN_IE_INFO@@@Z; CDRollback_Dot11ParseRSNIE(uchar *,uchar,uchar,RSN_IE_INFO *)
0x140028a2f  test    eax, eax
0x140028a31  jnz     short loc_140028A82
0x140028a33  cmp     r13w, [rbp+57h+var_70]
0x140028a38  jnz     short loc_140028AAB
0x140028a3a  lea     rdx, [rbp+57h+arg_18]; unsigned int *
0x140028a3e  mov     [rbp+57h+arg_18], eax
0x140028a41  lea     rcx, [rbp+57h+var_70]; struct RSN_IE_INFO *
0x140028a45  call    ?Dot11GetAuthAlgoInfo@@YAKPEAURSN_IE_INFO@@PEAK@Z; Dot11GetAuthAlgoInfo(RSN_IE_INFO *,ulong *)
0x140028a4a  or      [rdi+368h], eax
0x140028a50  mov     rcx, rdi; this
0x140028a53  mov     rax, [rbp+57h+var_40]
0x140028a57  mov     r9, [rbp+57h+var_50]; unsigned __int8 *
0x140028a5b  movzx   r8d, [rbp+57h+var_6C]; unsigned __int16
0x140028a60  movzx   edx, [rbp+57h+var_6A]; unsigned __int16
0x140028a64  mov     [rsp+0C0h+var_90], rax; unsigned __int8 *
0x140028a69  mov     rax, [rbp+57h+var_60]
0x140028a6d  mov     [rsp+0C0h+var_98], rax; unsigned __int8 *
0x140028a72  mov     rax, [rbp+57h+var_58]
0x140028a76  mov     [rsp+0C0h+var_A0], rax; unsigned __int8 *
0x140028a7b  call    ?SetRsnAkmsAndCiphers@CBSSEntry@@QEAAXGGPEAE000@Z; CBSSEntry::SetRsnAkmsAndCiphers(ushort,ushort,uchar *,uchar *,uchar *,uchar *)
0x140028a80  jmp     short loc_140028AAB
0x140028a82  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140028a89  jz      short loc_140028AAB
0x140028a8b  mov     rcx, cs:WPP_GLOBAL_Control
0x140028a92  mov     r9d, 46h ; 'F'
0x140028a98  mov     r8d, r13d
0x140028a9b  mov     [rsp+0C0h+var_A0], r14
0x140028aa0  mov     dl, 2
0x140028aa2  mov     rcx, [rcx+40h]
0x140028aa6  call    WPP_RECORDER_SF_
0x140028aab  add     rsp, 0A0h
0x140028ab2  pop     r14
0x140028ab4  pop     r13
0x140028ab6  pop     rdi
0x140028ab7  pop     rbx
0x140028ab8  pop     rbp
0x140028ab9  retn
```
