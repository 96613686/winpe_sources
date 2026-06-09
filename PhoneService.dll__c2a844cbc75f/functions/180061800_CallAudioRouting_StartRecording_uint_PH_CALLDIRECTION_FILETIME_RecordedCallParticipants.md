# CallAudioRouting::StartRecording(uint,PH_CALLDIRECTION,_FILETIME *,RecordedCallParticipants *)

- ea: `0x180061800`
- end: `0x180061b7e`
- name: `?StartRecording@CallAudioRouting@@UEAAJIW4PH_CALLDIRECTION@@PEAU_FILETIME@@PEAURecordedCallParticipants@@@Z`
- size: `894`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *, unsigned int, unsigned int, __int64, BackTraceCollection *)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180006e94`
- `0x180058bdc`
- `0x18005f9c0`
- `0x180061800`
- `0x180063a78`
- `0x180064dac`
- `0x18006950c`
- `0x18006bb78`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061a6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061b4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061a6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061b4a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180061846`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180061846`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180061b56`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180061b56`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180061922`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180061922`
- `ext-ms-win-winrt-storage-l1-1-0!CreateStorageItemFromPath_FullTrustCaller` at `0x180061968`
- `ext-ms-win-winrt-storage-l1-1-0!CreateStorageItemFromPath_FullTrustCaller` at `0x180061968`

## string_xrefs

- `0x1800618a1`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x18006193b`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180061a38`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180061aef`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`

## pseudocode

```c
__int64 __fastcall CallAudioRouting::StartRecording(
        struct _RTL_CRITICAL_SECTION *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4,
        BackTraceCollection *a5)
{
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  CallAudioRouting *p_SpinCount; // rsi
  int v10; // eax
  BackTraceCollection *v11; // rcx
  unsigned int v12; // edi
  __int64 v13; // r9
  __int64 v14; // rdx
  BackTraceCollection *v15; // rcx
  struct CallAudioRouting::CellularAudioState *v16; // r14
  unsigned int v17; // r15d
  int v18; // eax
  BackTraceCollection *v19; // rcx
  HRESULT v20; // eax
  BackTraceCollection *v21; // rcx
  int v22; // eax
  BackTraceCollection *v23; // rcx
  __int64 v24; // r9
  __int64 v25; // rdi
  __int64 v26; // rcx
  __int64 v27; // rax
  PWSTR v28; // rcx
  BackTraceCollection *v29; // r14
  __int64 v30; // rdx
  BackTraceCollection *v31; // rcx
  int updated; // eax
  BackTraceCollection *v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // rcx
  unsigned int started; // eax
  BackTraceCollection *v38; // rcx
  int v39; // eax
  __int64 v40; // rcx
  char v42[8]; // [rsp+30h] [rbp-41h] BYREF
  struct CallAudioRouting::CellularAudioState *v43; // [rsp+38h] [rbp-39h] BYREF
  BackTraceCollection *v44; // [rsp+40h] [rbp-31h] BYREF
  void *v45; // [rsp+48h] [rbp-29h] BYREF
  int v46; // [rsp+50h] [rbp-21h]
  struct _RTL_CRITICAL_SECTION *v47; // [rsp+58h] [rbp-19h]
  __int64 v48; // [rsp+60h] [rbp-11h] BYREF
  unsigned int v49; // [rsp+68h] [rbp-9h] BYREF
  PWSTR ppszPath; // [rsp+70h] [rbp-1h] BYREF

  v5 = a1 + 2;
  v47 = a1;
  v49 = a2;
  v44 = a5;
  EnterCriticalSection(a1 + 2);
  p_SpinCount = (CallAudioRouting *)&a1[-1].SpinCount;
  v10 = CallAudioRouting::_CheckShutdown((CallAudioRouting *)&a1[-1].SpinCount);
  v12 = v10;
  if ( v10 < 0 )
  {
    BackTraceCollection::Capture(v11, v10);
    v13 = 1677;
LABEL_3:
    v14 = 1;
LABEL_6:
    Log_HREvent_17(v12, v14, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", v13);
    goto LABEL_45;
  }
  v43 = 0;
  if ( !(unsigned int)CallAudioRouting::_FindCellularState(p_SpinCount, v49, &v43) )
  {
    v12 = -2147023728;
    BackTraceCollection::Capture(v15, -2147023728);
    v13 = 1680;
    v14 = 0;
    goto LABEL_6;
  }
  v16 = v43;
  v17 = 3;
  v42[0] = 0;
  LODWORD(v43) = *((_DWORD *)v43 + 8);
  if ( (_DWORD)v43 == 6 )
  {
    v42[0] = 4;
    v17 = 7;
  }
  v18 = CallAudioRouting::_SaveCallMetadataForRecording(p_SpinCount, v16, a3, a4, v44);
  v12 = v18;
  if ( v18 < 0 )
  {
    BackTraceCollection::Capture(v19, v18);
    v13 = 1693;
    goto LABEL_3;
  }
  ppszPath = 0;
  v20 = SHGetKnownFolderPath(&FOLDERID_RecordedCalls, 0x8000u, 0, &ppszPath);
  v12 = v20;
  if ( v20 < 0 )
  {
    BackTraceCollection::Capture(v21, v20);
    Log_HREvent_17(v12, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 1696);
LABEL_31:
    if ( ppszPath )
      CoTaskMemFree(ppszPath);
    goto LABEL_45;
  }
  v48 = 0;
  v22 = CreateStorageItemFromPath_FullTrustCaller(ppszPath, 0, &GUID_72d1cb78_b3ef_4f75_a80b_6fd9dae2944b, &v48);
  v12 = v22;
  if ( v22 < 0 )
  {
    BackTraceCollection::Capture(v23, v22);
    v24 = 1702;
LABEL_27:
    v34 = 1;
    v35 = v12;
    goto LABEL_28;
  }
  v25 = v48;
  v48 = 0;
  v26 = *((_QWORD *)v16 + 6);
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  *((_QWORD *)v16 + 6) = v25;
  v27 = 2147483646;
  v28 = ppszPath;
  v29 = (struct CallAudioRouting::CellularAudioState *)((char *)v16 + 144);
  v30 = 260;
  do
  {
    if ( !v27 )
      break;
    if ( !*v28 )
      break;
    *(_WORD *)v29 = *v28++;
    v29 = (BackTraceCollection *)((char *)v29 + 2);
    --v27;
    --v30;
  }
  while ( v30 );
  v31 = (BackTraceCollection *)((char *)v29 - 2);
  v12 = v30 == 0 ? 0x8007007A : 0;
  if ( v30 )
    v31 = v29;
  *(_WORD *)v31 = 0;
  if ( !v30 )
  {
    BackTraceCollection::Capture(v31, v12);
    v24 = 1707;
    goto LABEL_27;
  }
  updated = CallAudioRouting::_UpdateRecordingState(p_SpinCount, v49, v17);
  v12 = updated;
  if ( updated < 0 )
  {
    BackTraceCollection::Capture(v33, updated);
    v24 = 1709;
    goto LABEL_27;
  }
  v46 = 0;
  v45 = &CallAudioRouting::_StartRecording;
  v44 = p_SpinCount;
  if ( p_SpinCount )
    (*(void (__fastcall **)(CallAudioRouting *))(*(_QWORD *)p_SpinCount + 8LL))(p_SpinCount);
  started = QueueAsyncWorkItem_ATL::CComPtr_CallAudioRouting__void____cdecl_CallAudioRouting::___unsigned_int_enum_CallAudioRouting::StartRecordingAction__unsigned_int___enum_CallAudioRouting::StartRecordingAction___(
              *(_QWORD *)&v47[5].LockCount,
              (unsigned int)&v44,
              (unsigned int)&v45,
              (unsigned int)&v49,
              (__int64)v42);
  v38 = v44;
  v12 = started;
  if ( v44 )
    (*(void (__fastcall **)(BackTraceCollection *))(*(_QWORD *)v44 + 16LL))(v44);
  if ( (v12 & 0x80000000) != 0 )
  {
    BackTraceCollection::Capture(v38, v12);
    Log_HREvent_17(v12, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 1717);
    v39 = CallAudioRouting::_UpdateRecordingState(p_SpinCount, v49, (unsigned int)v43);
    if ( v39 >= 0 )
    {
LABEL_29:
      v36 = v48;
      if ( v48 )
      {
        v48 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
      }
      goto LABEL_31;
    }
    v24 = 1712;
    v34 = 0;
    v35 = (unsigned int)v39;
LABEL_28:
    Log_HREvent_17(v35, v34, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", v24);
    goto LABEL_29;
  }
  v40 = v48;
  if ( v48 )
  {
    v48 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
  }
  if ( ppszPath )
    CoTaskMemFree(ppszPath);
  v12 = 0;
LABEL_45:
  LeaveCriticalSection(v5);
  return v12;
}

```

## disassembly

```asm
0x180061800  push    rbp
0x180061802  push    rbx
0x180061803  push    rsi
0x180061804  push    rdi
0x180061805  push    r12
0x180061807  push    r13
0x180061809  push    r14
0x18006180b  push    r15
0x18006180d  lea     rbp, [rsp-17h]
0x180061812  sub     rsp, 88h
0x180061819  mov     rax, cs:__security_cookie
0x180061820  xor     rax, rsp
0x180061823  mov     [rbp+4Fh+var_48], rax
0x180061827  mov     rax, [rbp+4Fh+arg_20]
0x18006182b  lea     rbx, [rcx+50h]
0x18006182f  mov     rdi, rcx
0x180061832  mov     [rbp+4Fh+var_68], rcx
0x180061836  mov     rcx, rbx; lpCriticalSection
0x180061839  mov     [rbp+4Fh+var_58], edx
0x18006183c  mov     r13, r9
0x18006183f  mov     [rbp+4Fh+var_80], rax
0x180061843  mov     r12d, r8d
0x180061846  call    cs:__imp_EnterCriticalSection
0x18006184c  lea     rsi, [rdi-8]
0x180061850  mov     rcx, rsi; this
0x180061853  call    ?_CheckShutdown@CallAudioRouting@@AEAAJXZ; CallAudioRouting::_CheckShutdown(void)
0x180061858  mov     edi, eax
0x18006185a  test    eax, eax
0x18006185c  jns     short loc_180061872
0x18006185e  mov     edx, eax; int
0x180061860  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180061865  mov     r9d, 68Dh
0x18006186b  mov     edx, 1
0x180061870  jmp     short loc_1800618A1
0x180061872  mov     edx, [rbp+4Fh+var_58]; unsigned int
0x180061875  lea     r8, [rbp+4Fh+var_88]; struct CallAudioRouting::CellularAudioState **
0x180061879  mov     rcx, rsi; this
0x18006187c  mov     [rbp+4Fh+var_88], 0
0x180061884  call    ?_FindCellularState@CallAudioRouting@@AEAAHIPEAPEAUCellularAudioState@1@@Z; CallAudioRouting::_FindCellularState(uint,CallAudioRouting::CellularAudioState * *)
0x180061889  test    eax, eax
0x18006188b  jnz     short loc_1800618B4
0x18006188d  mov     edi, 80070490h
0x180061892  mov     edx, edi; int
0x180061894  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180061899  mov     r9d, 690h
0x18006189f  xor     edx, edx
0x1800618a1  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800618a8  mov     ecx, edi
0x1800618aa  call    Log_HREvent_17
0x1800618af  jmp     loc_180061B53
0x1800618b4  mov     r14, [rbp+4Fh+var_88]
0x1800618b8  mov     r15d, 3
0x1800618be  mov     [rbp+4Fh+var_90], 0
0x1800618c2  mov     eax, [r14+20h]
0x1800618c6  mov     dword ptr [rbp+4Fh+var_88], eax
0x1800618c9  cmp     eax, 6
0x1800618cc  jnz     short loc_1800618D6
0x1800618ce  mov     [rbp+4Fh+var_90], 4
0x1800618d2  lea     r15d, [rax+1]
0x1800618d6  mov     rax, [rbp+4Fh+var_80]
0x1800618da  mov     r9, r13
0x1800618dd  mov     r8d, r12d
0x1800618e0  mov     [rsp+0C0h+var_A0], rax
0x1800618e5  mov     rdx, r14
0x1800618e8  mov     rcx, rsi
0x1800618eb  call    ?_SaveCallMetadataForRecording@CallAudioRouting@@AEAAJPEAUCellularAudioState@1@W4PH_CALLDIRECTION@@PEBU_FILETIME@@PEAURecordedCallParticipants@@@Z; CallAudioRouting::_SaveCallMetadataForRecording(CallAudioRouting::CellularAudioState *,PH_CALLDIRECTION,_FILETIME const *,RecordedCallParticipants *)
0x1800618f0  xor     r12d, r12d
0x1800618f3  mov     edi, eax
0x1800618f5  test    eax, eax
0x1800618f7  jns     short loc_18006190B
0x1800618f9  mov     edx, eax; int
0x1800618fb  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180061900  mov     r9d, 69Dh
0x180061906  jmp     loc_18006186B
0x18006190b  lea     r9, [rbp+4Fh+ppszPath]; ppszPath
0x18006190f  mov     [rbp+4Fh+ppszPath], r12
0x180061913  xor     r8d, r8d; hToken
0x180061916  lea     rcx, FOLDERID_RecordedCalls; rfid
0x18006191d  mov     edx, 8000h; dwFlags
0x180061922  call    cs:__imp_SHGetKnownFolderPath
0x180061928  mov     edi, eax
0x18006192a  test    eax, eax
0x18006192c  jns     short loc_180061953
0x18006192e  mov     edx, eax; int
0x180061930  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180061935  mov     r9d, 6A0h
0x18006193b  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180061942  mov     edx, 1
0x180061947  mov     ecx, edi
0x180061949  call    Log_HREvent_17
0x18006194e  jmp     loc_180061A5D
0x180061953  mov     rcx, [rbp+4Fh+ppszPath]
0x180061957  lea     r9, [rbp+4Fh+var_60]
0x18006195b  lea     r8, _GUID_72d1cb78_b3ef_4f75_a80b_6fd9dae2944b
0x180061962  mov     [rbp+4Fh+var_60], r12
0x180061966  xor     edx, edx
0x180061968  call    cs:__imp_CreateStorageItemFromPath_FullTrustCaller
0x18006196e  mov     edi, eax
0x180061970  test    eax, eax
0x180061972  jns     short loc_180061986
0x180061974  mov     edx, eax; int
0x180061976  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18006197b  mov     r9d, 6A6h
0x180061981  jmp     loc_180061A31
0x180061986  mov     rdi, [rbp+4Fh+var_60]
0x18006198a  mov     [rbp+4Fh+var_60], r12
0x18006198e  mov     rcx, [r14+30h]
0x180061992  test    rcx, rcx
0x180061995  jz      short loc_1800619A3
0x180061997  mov     rax, [rcx]
0x18006199a  mov     rax, [rax+10h]
0x18006199e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800619a3  mov     [r14+30h], rdi
0x1800619a7  mov     eax, 7FFFFFFEh
0x1800619ac  mov     rcx, [rbp+4Fh+ppszPath]
0x1800619b0  add     r14, 90h
0x1800619b7  mov     edx, 104h
0x1800619bc  test    rax, rax
0x1800619bf  jz      short loc_1800619E0
0x1800619c1  movzx   r8d, word ptr [rcx]
0x1800619c5  test    r8w, r8w
0x1800619c9  jz      short loc_1800619E0
0x1800619cb  mov     [r14], r8w
0x1800619cf  add     rcx, 2
0x1800619d3  add     r14, 2
0x1800619d7  dec     rax
0x1800619da  sub     rdx, 1
0x1800619de  jnz     short loc_1800619BC
0x1800619e0  mov     rax, rdx
0x1800619e3  lea     rcx, [r14-2]
0x1800619e7  neg     rax
0x1800619ea  sbb     edi, edi
0x1800619ec  not     edi
0x1800619ee  and     edi, 8007007Ah
0x1800619f4  test    rdx, rdx
0x1800619f7  cmovnz  rcx, r14; this
0x1800619fb  mov     [rcx], r12w
0x1800619ff  jnz     short loc_180061A10
0x180061a01  mov     edx, edi; int
0x180061a03  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180061a08  mov     r9d, 6ABh
0x180061a0e  jmp     short loc_180061A31
0x180061a10  mov     edx, [rbp+4Fh+var_58]
0x180061a13  mov     r8d, r15d
0x180061a16  mov     rcx, rsi
0x180061a19  call    ?_UpdateRecordingState@CallAudioRouting@@AEAAJIW4CallRecordingState@@@Z; CallAudioRouting::_UpdateRecordingState(uint,CallRecordingState)
0x180061a1e  mov     edi, eax
0x180061a20  test    eax, eax
0x180061a22  jns     short loc_180061A75
0x180061a24  mov     edx, eax; int
0x180061a26  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180061a2b  mov     r9d, 6ADh
0x180061a31  mov     edx, 1
0x180061a36  mov     ecx, edi
0x180061a38  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180061a3f  call    Log_HREvent_17
0x180061a44  mov     rcx, [rbp+4Fh+var_60]
0x180061a48  test    rcx, rcx
0x180061a4b  jz      short loc_180061A5D
0x180061a4d  mov     [rbp+4Fh+var_60], r12
0x180061a51  mov     rax, [rcx]
0x180061a54  mov     rax, [rax+10h]
0x180061a58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061a5d  mov     rcx, [rbp+4Fh+ppszPath]; pv
0x180061a61  test    rcx, rcx
0x180061a64  jz      loc_180061B53
0x180061a6a  call    cs:__imp_CoTaskMemFree
0x180061a70  jmp     loc_180061B53
0x180061a75  mov     [rbp+4Fh+var_70], r12d
0x180061a79  lea     rax, ?_StartRecording@CallAudioRouting@@AEAAXIW4StartRecordingAction@1@@Z; CallAudioRouting::_StartRecording(uint,CallAudioRouting::StartRecordingAction)
0x180061a80  mov     [rbp+4Fh+var_78], rax
0x180061a84  mov     eax, [rbp+4Fh+var_6C]
0x180061a87  mov     [rbp+4Fh+var_6C], eax
0x180061a8a  mov     [rbp+4Fh+var_80], rsi
0x180061a8e  test    rsi, rsi
0x180061a91  jz      short loc_180061AA2
0x180061a93  mov     rax, [rsi]
0x180061a96  mov     rcx, rsi
0x180061a99  mov     rax, [rax+8]
0x180061a9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061aa2  mov     rcx, [rbp+4Fh+var_68]
0x180061aa6  lea     rax, [rbp+4Fh+var_90]
0x180061aaa  lea     r9, [rbp+4Fh+var_58]
0x180061aae  mov     [rsp+0C0h+var_A0], rax
0x180061ab3  lea     r8, [rbp+4Fh+var_78]
0x180061ab7  lea     rdx, [rbp+4Fh+var_80]
0x180061abb  mov     rcx, [rcx+0D0h]
0x180061ac2  call    QueueAsyncWorkItem_ATL__CComPtr_CallAudioRouting__void____cdecl_CallAudioRouting_____unsigned_int_enum_CallAudioRouting__StartRecordingAction__unsigned_int___enum_CallAudioRouting__StartRecordingAction___
0x180061ac7  mov     rcx, [rbp+4Fh+var_80]
0x180061acb  mov     edi, eax
0x180061acd  test    rcx, rcx
0x180061ad0  jz      short loc_180061ADE
0x180061ad2  mov     rax, [rcx]
0x180061ad5  mov     rax, [rax+10h]
0x180061ad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061ade  test    edi, edi
0x180061ae0  jns     short loc_180061B28
0x180061ae2  mov     edx, edi; int
0x180061ae4  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180061ae9  mov     r9d, 6B5h
0x180061aef  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180061af6  mov     edx, 1
0x180061afb  mov     ecx, edi
0x180061afd  call    Log_HREvent_17
0x180061b02  mov     r8d, dword ptr [rbp+4Fh+var_88]
0x180061b06  mov     rcx, rsi
0x180061b09  mov     edx, [rbp+4Fh+var_58]
0x180061b0c  call    ?_UpdateRecordingState@CallAudioRouting@@AEAAJIW4CallRecordingState@@@Z; CallAudioRouting::_UpdateRecordingState(uint,CallRecordingState)
0x180061b11  test    eax, eax
0x180061b13  jns     loc_180061A44
0x180061b19  mov     r9d, 6B0h
0x180061b1f  xor     edx, edx
0x180061b21  mov     ecx, eax
0x180061b23  jmp     loc_180061A38
0x180061b28  mov     rcx, [rbp+4Fh+var_60]
0x180061b2c  test    rcx, rcx
0x180061b2f  jz      short loc_180061B41
0x180061b31  mov     [rbp+4Fh+var_60], r12
0x180061b35  mov     rax, [rcx]
0x180061b38  mov     rax, [rax+10h]
0x180061b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061b41  mov     rcx, [rbp+4Fh+ppszPath]; pv
0x180061b45  test    rcx, rcx
0x180061b48  jz      short loc_180061B50
0x180061b4a  call    cs:__imp_CoTaskMemFree
0x180061b50  mov     edi, r12d
0x180061b53  mov     rcx, rbx; lpCriticalSection
0x180061b56  call    cs:__imp_LeaveCriticalSection
0x180061b5c  mov     eax, edi
0x180061b5e  mov     rcx, [rbp+4Fh+var_48]
0x180061b62  xor     rcx, rsp; StackCookie
0x180061b65  call    __security_check_cookie
0x180061b6a  add     rsp, 88h
0x180061b71  pop     r15
0x180061b73  pop     r14
0x180061b75  pop     r13
0x180061b77  pop     r12
0x180061b79  pop     rdi
0x180061b7a  pop     rsi
0x180061b7b  pop     rbx
0x180061b7c  pop     rbp
0x180061b7d  retn
```
