# _WlanSyncTaskWlanToCDS::DoWork_::_1_::catch$14

- ea: `0x18003ee84`
- end: `0x18003f072`
- name: `_WlanSyncTaskWlanToCDS::DoWork_::_1_::catch$14`
- size: `494`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x1800118a0`
- `0x18002543c`
- `0x1800310a8`
- `0x180034144`
- `0x18003d4d8`
- `0x18003ee84`

## string_xrefs

- `0x18003ee99`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskwlantocds.cpp`

## pseudocode

```c
__int64 __fastcall WlanSyncTaskWlanToCDS::DoWork_::_1_::catch_14(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  unsigned int v5; // eax
  unsigned int *v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rax

  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 504),
    (void *)0xC4,
    (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskwlantocds.cpp",
    a4);
  v5 = *(_DWORD *)(a2 + 384);
  v6 = *(unsigned int **)(a2 + 120);
  if ( v5 < 3 )
  {
    *(_DWORD *)(a2 + 432) = v5 + 1;
    *(_QWORD *)(a2 + 436) = *(_QWORD *)(a2 + 192);
    Windows::Internal::WiFiCloudStore::SetRetryCountForProfile(
      a2 + 400,
      (void *)(532LL * *(unsigned int *)(a2 + 80) + *(_QWORD *)(a2 + 112) + 8LL),
      v6[10],
      v6[11],
      (BYTE *)(a2 + 432));
    *(_DWORD *)(a2 + 104) = 16;
    *(_DWORD *)(a2 + 100) = 0;
    *(_DWORD *)(a2 + 96) = 0;
    *(_DWORD *)(a2 + 92) = 0;
    *(_DWORD *)(a2 + 84) = 0;
    v8 = a2 + 400;
    if ( *(_QWORD *)(a2 + 424) > 7u )
      v8 = *(_QWORD *)(a2 + 400);
    *(_QWORD *)(a2 + 128) = v8;
    WiFiCloudStoreTelemetry::WlanTriggeredSync::ActionTakenOnWiFiProfile<unsigned short const *,enum Windows::Internal::WiFiCloudStore::ProfileGeneration const &,int,int,int,int,unsigned long &,enum WiFiSyncAction>(
      *(_QWORD *)(a2 + 216),
      a2 + 128,
      (_DWORD)v6 + 44,
      a2 + 84,
      a2 + 92,
      a2 + 96,
      a2 + 100,
      a2 + 384,
      a2 + 104);
  }
  else
  {
    *(_DWORD *)(a2 + 104) = 15;
    *(_DWORD *)(a2 + 100) = 0;
    *(_DWORD *)(a2 + 96) = 0;
    *(_DWORD *)(a2 + 92) = 0;
    *(_DWORD *)(a2 + 84) = 0;
    v7 = a2 + 400;
    if ( *(_QWORD *)(a2 + 424) > 7u )
      v7 = *(_QWORD *)(a2 + 400);
    *(_QWORD *)(a2 + 128) = v7;
    WiFiCloudStoreTelemetry::WlanTriggeredSync::ActionTakenOnWiFiProfile<unsigned short const *,enum Windows::Internal::WiFiCloudStore::ProfileGeneration const &,int,int,int,int,unsigned long &,enum WiFiSyncAction>(
      *(_QWORD *)(a2 + 216),
      a2 + 128,
      (_DWORD)v6 + 44,
      a2 + 84,
      a2 + 92,
      a2 + 96,
      a2 + 100,
      a2 + 384,
      a2 + 104);
    if ( *(_QWORD *)(a2 + 152) == *(_QWORD *)(a2 + 160) )
    {
      std::vector<Windows::Internal::WiFiCloudStore::SyncNeededProfile>::_Emplace_reallocate<Windows::Internal::WiFiCloudStore::SyncNeededProfile const &>(
        a2 + 144,
        *(_QWORD *)(a2 + 152),
        v6);
    }
    else
    {
      Windows::Internal::WiFiCloudStore::SyncNeededProfile::SyncNeededProfile(
        *(Windows::Internal::WiFiCloudStore::SyncNeededProfile **)(a2 + 152),
        (const struct Windows::Internal::WiFiCloudStore::SyncNeededProfile *)v6);
      *(_QWORD *)(a2 + 152) += 48LL;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18003ee84  mov     [rsp+arg_8], rdx
0x18003ee89  push    rbx
0x18003ee8a  push    rbp
0x18003ee8b  sub     rsp, 58h
0x18003ee8f  mov     rbp, rdx
0x18003ee92  mov     rcx, [rbp+1F8h]; this
0x18003ee99  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x18003eea0  mov     edx, 0C4h; void *
0x18003eea5  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x18003eeaa  mov     eax, [rbp+180h]
0x18003eeb0  mov     rbx, [rbp+78h]
0x18003eeb4  cmp     eax, 3
0x18003eeb7  jb      loc_18003EF88
0x18003eebd  mov     dword ptr [rbp+68h], 0Fh
0x18003eec4  mov     dword ptr [rbp+64h], 0
0x18003eecb  mov     dword ptr [rbp+60h], 0
0x18003eed2  mov     dword ptr [rbp+5Ch], 0
0x18003eed9  mov     dword ptr [rbp+54h], 0
0x18003eee0  lea     rax, [rbp+190h]
0x18003eee7  cmp     qword ptr [rbp+1A8h], 7
0x18003eeef  cmova   rax, [rbp+190h]
0x18003eef7  mov     [rbp+80h], rax
0x18003eefe  lea     r8, [rbx+2Ch]
0x18003ef02  lea     rax, [rbp+68h]
0x18003ef06  mov     [rsp+68h+var_28], rax
0x18003ef0b  lea     rax, [rbp+180h]
0x18003ef12  mov     [rsp+68h+var_30], rax
0x18003ef17  lea     rax, [rbp+64h]
0x18003ef1b  mov     [rsp+68h+var_38], rax
0x18003ef20  lea     rax, [rbp+60h]
0x18003ef24  mov     [rsp+68h+var_40], rax
0x18003ef29  lea     rax, [rbp+5Ch]
0x18003ef2d  mov     [rsp+68h+var_48], rax
0x18003ef32  lea     r9, [rbp+54h]
0x18003ef36  lea     rdx, [rbp+80h]
0x18003ef3d  mov     rcx, [rbp+0D8h]
0x18003ef44  call    ??$ActionTakenOnWiFiProfile@PEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@HHHHAEAKW4WiFiSyncAction@@@WlanTriggeredSync@WiFiCloudStoreTelemetry@@QEAAX$$QEAPEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@$$QEAH222AEAK$$QEAW4WiFiSyncAction@@@Z; WiFiCloudStoreTelemetry::WlanTriggeredSync::ActionTakenOnWiFiProfile<ushort const *,Windows::Internal::WiFiCloudStore::ProfileGeneration const &,int,int,int,int,ulong &,WiFiSyncAction>(ushort const * &&,Windows::Internal::WiFiCloudStore::ProfileGeneration const &,int &&,int &&,int &&,int &&,ulong &,WiFiSyncAction &&)
0x18003ef49  mov     rax, [rbp+98h]
0x18003ef50  cmp     rax, [rbp+0A0h]
0x18003ef57  jz      short loc_18003EF71
0x18003ef59  mov     rdx, rbx; struct Windows::Internal::WiFiCloudStore::SyncNeededProfile *
0x18003ef5c  mov     rcx, rax; this
0x18003ef5f  call    ??0SyncNeededProfile@WiFiCloudStore@Internal@Windows@@QEAA@AEBU0123@@Z; Windows::Internal::WiFiCloudStore::SyncNeededProfile::SyncNeededProfile(Windows::Internal::WiFiCloudStore::SyncNeededProfile const &)
0x18003ef64  add     qword ptr [rbp+98h], 30h ; '0'
0x18003ef6c  jmp     loc_18003F060
0x18003ef71  mov     r8, rbx
0x18003ef74  mov     rdx, rax
0x18003ef77  lea     rcx, [rbp+90h]
0x18003ef7e  call    ??$_Emplace_reallocate@AEBUSyncNeededProfile@WiFiCloudStore@Internal@Windows@@@?$vector@USyncNeededProfile@WiFiCloudStore@Internal@Windows@@V?$allocator@USyncNeededProfile@WiFiCloudStore@Internal@Windows@@@std@@@std@@AEAAPEAUSyncNeededProfile@WiFiCloudStore@Internal@Windows@@QEAU2345@AEBU2345@@Z; std::vector<Windows::Internal::WiFiCloudStore::SyncNeededProfile>::_Emplace_reallocate<Windows::Internal::WiFiCloudStore::SyncNeededProfile const &>(Windows::Internal::WiFiCloudStore::SyncNeededProfile * const,Windows::Internal::WiFiCloudStore::SyncNeededProfile const &)
0x18003ef83  jmp     loc_18003F060
0x18003ef88  inc     eax
0x18003ef8a  mov     [rbp+1B0h], eax
0x18003ef90  mov     rax, [rbp+0C0h]
0x18003ef97  mov     [rbp+1B4h], rax
0x18003ef9e  mov     eax, [rbp+50h]
0x18003efa1  imul    rcx, rax, 214h
0x18003efa8  mov     rdx, [rbp+70h]
0x18003efac  add     rdx, 8
0x18003efb0  add     rdx, rcx; int
0x18003efb3  lea     rax, [rbp+1B0h]
0x18003efba  mov     [rsp+68h+var_48], rax; BYTE *
0x18003efbf  mov     r9d, [rbx+2Ch]; int
0x18003efc3  mov     r8d, [rbx+28h]; int
0x18003efc7  lea     rcx, [rbp+190h]; int
0x18003efce  call    ?SetRetryCountForProfile@WiFiCloudStore@Internal@Windows@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@W4ProfileModificationType@123@W4ProfileGeneration@123@AEBURetryStatistics@123@@Z; Windows::Internal::WiFiCloudStore::SetRetryCountForProfile(std::wstring const &,_GUID const &,Windows::Internal::WiFiCloudStore::ProfileModificationType,Windows::Internal::WiFiCloudStore::ProfileGeneration,Windows::Internal::WiFiCloudStore::RetryStatistics const &)
0x18003efd3  mov     dword ptr [rbp+68h], 10h
0x18003efda  mov     dword ptr [rbp+64h], 0
0x18003efe1  mov     dword ptr [rbp+60h], 0
0x18003efe8  mov     dword ptr [rbp+5Ch], 0
0x18003efef  mov     dword ptr [rbp+54h], 0
0x18003eff6  lea     rax, [rbp+190h]
0x18003effd  cmp     qword ptr [rbp+1A8h], 7
0x18003f005  cmova   rax, [rbp+190h]
0x18003f00d  mov     [rbp+80h], rax
0x18003f014  lea     r8, [rbx+2Ch]
0x18003f018  lea     rax, [rbp+68h]
0x18003f01c  mov     [rsp+68h+var_28], rax
0x18003f021  lea     rax, [rbp+180h]
0x18003f028  mov     [rsp+68h+var_30], rax
0x18003f02d  lea     rax, [rbp+64h]
0x18003f031  mov     [rsp+68h+var_38], rax
0x18003f036  lea     rax, [rbp+60h]
0x18003f03a  mov     [rsp+68h+var_40], rax
0x18003f03f  lea     rax, [rbp+5Ch]
0x18003f043  mov     [rsp+68h+var_48], rax
0x18003f048  lea     r9, [rbp+54h]
0x18003f04c  lea     rdx, [rbp+80h]
0x18003f053  mov     rcx, [rbp+0D8h]
0x18003f05a  call    ??$ActionTakenOnWiFiProfile@PEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@HHHHAEAKW4WiFiSyncAction@@@WlanTriggeredSync@WiFiCloudStoreTelemetry@@QEAAX$$QEAPEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@$$QEAH222AEAK$$QEAW4WiFiSyncAction@@@Z; WiFiCloudStoreTelemetry::WlanTriggeredSync::ActionTakenOnWiFiProfile<ushort const *,Windows::Internal::WiFiCloudStore::ProfileGeneration const &,int,int,int,int,ulong &,WiFiSyncAction>(ushort const * &&,Windows::Internal::WiFiCloudStore::ProfileGeneration const &,int &&,int &&,int &&,int &&,ulong &,WiFiSyncAction &&)
0x18003f05f  nop
0x18003f060  mov     rax, 0
0x18003f06a  add     rsp, 58h
0x18003f06e  pop     rbp
0x18003f06f  pop     rbx
0x18003f070  retn
```
