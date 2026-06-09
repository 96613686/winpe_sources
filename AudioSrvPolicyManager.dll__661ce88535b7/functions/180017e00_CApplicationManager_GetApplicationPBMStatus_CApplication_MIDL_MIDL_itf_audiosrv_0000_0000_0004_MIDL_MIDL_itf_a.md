# CApplicationManager::GetApplicationPBMStatus(CApplication *,__MIDL___MIDL_itf_audiosrv_0000_0000_0004 *,__MIDL___MIDL_itf_audiosrv_0000_0000_0004 *,_PLM_EXEMPTION *)

- ea: `0x180017e00`
- end: `0x1800181fb`
- name: `?GetApplicationPBMStatus@CApplicationManager@@QEAAJPEAVCApplication@@PEAW4__MIDL___MIDL_itf_audiosrv_0000_0000_0004@@1PEAW4_PLM_EXEMPTION@@@Z`
- size: `1019`
- prototype: `__int64 __fastcall(CApplicationManager *__hidden this, struct CApplication *, enum __MIDL___MIDL_itf_audiosrv_0000_0000_0004 *, enum __MIDL___MIDL_itf_audiosrv_0000_0000_0004 *, enum _PLM_EXEMPTION *)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800161d0`
- `0x180016a30`
- `0x1800397b4`

## callees

- `0x180017e00`
- `0x18001b100`
- `0x18001b400`
- `0x18001d580`
- `0x18001d6c0`
- `0x180031960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017e4c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017e4c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800181d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800181d0`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800181bd`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800181bd`

## string_xrefs

- `0x180017f7f`: `Not computed`
- `0x180017fde`: `Not computed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CApplicationManager::GetApplicationPBMStatus(
        CApplicationManager *this,
        struct _RTL_CRITICAL_SECTION **a2,
        enum __MIDL___MIDL_itf_audiosrv_0000_0000_0004 *a3,
        enum __MIDL___MIDL_itf_audiosrv_0000_0000_0004 *a4,
        enum _PLM_EXEMPTION *a5)
{
  struct _RTL_CRITICAL_SECTION *v9; // r12
  unsigned int SoundLevel; // eax
  unsigned int v11; // ebx
  __int64 v12; // rcx
  const wchar_t *v13; // r12
  const wchar_t *v14; // r9
  const wchar_t *v15; // rsi
  unsigned int v16; // ebx
  const wchar_t *v17; // r8
  const wchar_t *v18; // r9
  const wchar_t *v19; // r8
  __int64 v20; // r10
  struct _RTL_CRITICAL_SECTION *v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  int v26; // ecx
  _DWORD v28[2]; // [rsp+30h] [rbp-D0h] BYREF
  struct _RTL_CRITICAL_SECTION *v29; // [rsp+38h] [rbp-C8h] BYREF
  struct _RTL_CRITICAL_SECTION *v30; // [rsp+40h] [rbp-C0h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-B8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-A0h] BYREF
  void *v33; // [rsp+70h] [rbp-90h]
  int v34; // [rsp+78h] [rbp-88h]
  int v35; // [rsp+7Ch] [rbp-84h]
  struct _RTL_CRITICAL_SECTION *v36; // [rsp+80h] [rbp-80h]
  int v37; // [rsp+88h] [rbp-78h]
  int v38; // [rsp+8Ch] [rbp-74h]
  struct _RTL_CRITICAL_SECTION **v39; // [rsp+90h] [rbp-70h]
  __int64 v40; // [rsp+98h] [rbp-68h]
  _DWORD *v41; // [rsp+A0h] [rbp-60h]
  __int64 v42; // [rsp+A8h] [rbp-58h]
  _WORD *v43; // [rsp+B0h] [rbp-50h]
  int v44; // [rsp+B8h] [rbp-48h]
  int v45; // [rsp+BCh] [rbp-44h]
  _WORD *v46; // [rsp+C0h] [rbp-40h]
  int v47; // [rsp+C8h] [rbp-38h]
  int v48; // [rsp+CCh] [rbp-34h]
  _WORD *v49; // [rsp+D0h] [rbp-30h]
  int v50; // [rsp+D8h] [rbp-28h]
  int v51; // [rsp+DCh] [rbp-24h]
  _WORD v52[32]; // [rsp+E0h] [rbp-20h] BYREF
  _WORD v53[32]; // [rsp+120h] [rbp+20h] BYREF
  _WORD v54[32]; // [rsp+160h] [rbp+60h] BYREF

  v9 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  v30 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v29 = v9;
  SoundLevel = CApplicationManager::GetSoundLevel(this, a2, 0);
  v11 = SoundLevel;
  if ( a3 )
    *(_DWORD *)a3 = SoundLevel;
  if ( a4 )
  {
    if ( *((_DWORD *)a2 + 156) )
      *(_DWORD *)a4 = *((_DWORD *)a2 + 157);
    else
      *(_DWORD *)a4 = SoundLevel;
  }
  if ( a5 )
    *(_DWORD *)a5 = CApplicationManager::GetPLMExemptionStatus(this, a2, SoundLevel);
  v12 = *((_QWORD *)AudioSrvPolicyManagerTelemetryProvider::Instance() + 1);
  if ( v12
    && *(_DWORD *)v12 > 5u
    && (*(_QWORD *)(v12 + 16) & 0x10000LL) != 0
    && (*(_QWORD *)(v12 + 24) & 0x10000LL) == *(_QWORD *)(v12 + 24) )
  {
    v13 = L"(override)";
    v14 = L"(override)";
    if ( !*((_DWORD *)a2 + 158) )
      v14 = (const wchar_t *)&unk_180053B30;
    v15 = L"Unknown level";
    if ( v11 )
    {
      v16 = v11 - 1;
      if ( v16 )
      {
        if ( v16 == 1 )
          v17 = L"SNDLVL_Full";
        else
          v17 = L"Unknown level";
      }
      else
      {
        v17 = L"SNDLVL_Low";
      }
    }
    else
    {
      v17 = L"SNDLVL_Muted";
    }
    swprintf_s<32>(v54, L"%s%s", v17, v14);
    v18 = L"(override)";
    if ( !*((_DWORD *)a2 + 156) )
      v18 = (const wchar_t *)&unk_180053B30;
    if ( a4 )
    {
      if ( *(_DWORD *)a4 )
      {
        if ( *(_DWORD *)a4 == 1 )
        {
          v15 = L"SNDLVL_Low";
        }
        else if ( *(_DWORD *)a4 == 2 )
        {
          v15 = L"SNDLVL_Full";
        }
      }
      else
      {
        v15 = L"SNDLVL_Muted";
      }
    }
    else
    {
      v15 = L"Not computed";
    }
    swprintf_s<32>(v53, L"%s%s", v15, v18);
    if ( !*((_DWORD *)a2 + 160) )
      v13 = (const wchar_t *)&unk_180053B30;
    if ( a5 )
    {
      if ( *(_DWORD *)a5 )
      {
        if ( *(_DWORD *)a5 == 1 )
        {
          v19 = L"No";
        }
        else if ( *(_DWORD *)a5 == 2 )
        {
          v19 = L"Yes";
        }
        else
        {
          v19 = L"Unknown";
        }
      }
      else
      {
        v19 = L"Invalid";
      }
    }
    else
    {
      v19 = L"Not computed";
    }
    swprintf_s<32>(v52, L"%s%s", v19, v13);
    v20 = *((_QWORD *)AudioSrvPolicyManagerTelemetryProvider::Instance() + 1);
    if ( *(_DWORD *)v20 > 5u
      && (*(_QWORD *)(v20 + 16) & 0x10000LL) != 0
      && (*(_QWORD *)(v20 + 24) & 0x10000LL) == *(_QWORD *)(v20 + 24) )
    {
      v28[0] = *((_DWORD *)a2 + 53);
      v29 = a2[87];
      v21 = a2[3];
      v22 = -1;
      v23 = -1;
      do
        ++v23;
      while ( v52[v23] );
      v49 = v52;
      v50 = 2 * v23 + 2;
      v51 = 0;
      v24 = -1;
      do
        ++v24;
      while ( v53[v24] );
      v46 = v53;
      v47 = 2 * v24 + 2;
      v48 = 0;
      v25 = -1;
      do
        ++v25;
      while ( v54[v25] );
      v43 = v54;
      v44 = 2 * v25 + 2;
      v45 = 0;
      v41 = v28;
      v42 = 4;
      v39 = &v29;
      v40 = 8;
      if ( v21 )
      {
        do
          ++v22;
        while ( *((_WORD *)&v21->DebugInfo + v22) );
        v26 = 2 * v22 + 2;
      }
      else
      {
        v21 = (struct _RTL_CRITICAL_SECTION *)&unk_180053B30;
        v26 = 2;
      }
      v36 = v21;
      v37 = v26;
      v38 = 0;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 5;
      EventDescriptor.Keyword = 0x10000;
      UserData.Ptr = *(_QWORD *)(v20 + 8);
      UserData.Size = *(unsigned __int16 *)UserData.Ptr;
      UserData.Reserved = 2;
      v33 = &unk_180057D11;
      v34 = 108;
      v35 = 1;
      v28[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(*(_QWORD *)(v20 + 32), &EventDescriptor, 0, 0, 8u, &UserData);
    }
    v9 = v30;
  }
  if ( v9 )
    LeaveCriticalSection(v9);
  return 0;
}

```

## disassembly

```asm
0x180017e00  push    rbp
0x180017e02  push    rbx
0x180017e03  push    rsi
0x180017e04  push    rdi
0x180017e05  push    r12
0x180017e07  push    r13
0x180017e09  push    r14
0x180017e0b  push    r15
0x180017e0d  lea     rbp, [rsp-0B8h]
0x180017e15  sub     rsp, 1B8h
0x180017e1c  mov     rax, cs:__security_cookie
0x180017e23  xor     rax, rsp
0x180017e26  mov     [rbp+0F0h+var_50], rax
0x180017e2d  mov     r14, r9
0x180017e30  mov     rsi, r8
0x180017e33  mov     rdi, rdx
0x180017e36  mov     r13, rcx
0x180017e39  mov     r15, [rbp+0F0h+arg_20]
0x180017e40  lea     r12, [rcx+20h]
0x180017e44  mov     [rsp+1F0h+var_1B0], r12
0x180017e49  mov     rcx, r12; lpCriticalSection
0x180017e4c  call    cs:__imp_EnterCriticalSection
0x180017e52  mov     [rsp+1F0h+var_1B8], r12
0x180017e57  xor     r8d, r8d
0x180017e5a  mov     rdx, rdi
0x180017e5d  mov     rcx, r13
0x180017e60  call    ?GetSoundLevel@CApplicationManager@@QEAA?AW4__MIDL___MIDL_itf_audiosrv_0000_0000_0004@@PEAVCApplication@@_N@Z; CApplicationManager::GetSoundLevel(CApplication *,bool)
0x180017e65  mov     ebx, eax
0x180017e67  test    rsi, rsi
0x180017e6a  jz      short loc_180017E6E
0x180017e6c  mov     [rsi], eax
0x180017e6e  test    r14, r14
0x180017e71  jz      short loc_180017E8A
0x180017e73  cmp     dword ptr [rdi+270h], 0
0x180017e7a  jz      short loc_180017E87
0x180017e7c  mov     ecx, [rdi+274h]
0x180017e82  mov     [r14], ecx
0x180017e85  jmp     short loc_180017E8A
0x180017e87  mov     [r14], ebx
0x180017e8a  test    r15, r15
0x180017e8d  jz      short loc_180017EA0
0x180017e8f  mov     r8d, ebx
0x180017e92  mov     rdx, rdi
0x180017e95  mov     rcx, r13
0x180017e98  call    ?GetPLMExemptionStatus@CApplicationManager@@QEAA?AW4_PLM_EXEMPTION@@PEAVCApplication@@W4__MIDL___MIDL_itf_audiosrv_0000_0000_0004@@@Z; CApplicationManager::GetPLMExemptionStatus(CApplication *,__MIDL___MIDL_itf_audiosrv_0000_0000_0004)
0x180017e9d  mov     [r15], eax
0x180017ea0  call    ?Instance@AudioSrvPolicyManagerTelemetryProvider@@KAPEAV1@XZ; AudioSrvPolicyManagerTelemetryProvider::Instance(void)
0x180017ea5  mov     rcx, [rax+8]
0x180017ea9  test    rcx, rcx
0x180017eac  jz      loc_1800181C8
0x180017eb2  mov     eax, [rcx]
0x180017eb4  cmp     eax, 5
0x180017eb7  jbe     loc_1800181C8
0x180017ebd  mov     rdx, [rcx+18h]
0x180017ec1  mov     rax, [rcx+10h]
0x180017ec5  bt      rax, 10h
0x180017eca  jnb     loc_1800181C8
0x180017ed0  mov     rax, rdx
0x180017ed3  and     eax, 10000h
0x180017ed8  cmp     rax, rdx
0x180017edb  jnz     loc_1800181C8
0x180017ee1  lea     r13, unk_180053B30
0x180017ee8  lea     r12, aOverride; "(override)"
0x180017eef  mov     r9, r12
0x180017ef2  cmp     dword ptr [rdi+278h], 0
0x180017ef9  cmovz   r9, r13
0x180017efd  lea     rsi, aUnknownLevel; "Unknown level"
0x180017f04  test    ebx, ebx
0x180017f06  jz      short loc_180017F29
0x180017f08  sub     ebx, 1
0x180017f0b  jz      short loc_180017F20
0x180017f0d  cmp     ebx, 1
0x180017f10  jz      short loc_180017F17
0x180017f12  mov     r8, rsi
0x180017f15  jmp     short loc_180017F30
0x180017f17  lea     r8, aSndlvlFull; "SNDLVL_Full"
0x180017f1e  jmp     short loc_180017F30
0x180017f20  lea     r8, aSndlvlLow; "SNDLVL_Low"
0x180017f27  jmp     short loc_180017F30
0x180017f29  lea     r8, aSndlvlMuted; "SNDLVL_Muted"
0x180017f30  lea     rdx, aSS_0; "%s%s"
0x180017f37  lea     rcx, [rbp+0F0h+var_90]
0x180017f3b  call    ??$swprintf_s@$0CA@@@YAHAEAY0CA@GPEBGZZ; swprintf_s<32>(ushort (&)[32],ushort const *,...)
0x180017f40  mov     r9, r12
0x180017f43  cmp     dword ptr [rdi+270h], 0
0x180017f4a  cmovz   r9, r13
0x180017f4e  test    r14, r14
0x180017f51  jz      short loc_180017F7F
0x180017f53  mov     ecx, [r14]
0x180017f56  test    ecx, ecx
0x180017f58  jz      short loc_180017F76
0x180017f5a  sub     ecx, 1
0x180017f5d  jz      short loc_180017F6D
0x180017f5f  cmp     ecx, 1
0x180017f62  jnz     short loc_180017F86
0x180017f64  lea     rsi, aSndlvlFull; "SNDLVL_Full"
0x180017f6b  jmp     short loc_180017F86
0x180017f6d  lea     rsi, aSndlvlLow; "SNDLVL_Low"
0x180017f74  jmp     short loc_180017F86
0x180017f76  lea     rsi, aSndlvlMuted; "SNDLVL_Muted"
0x180017f7d  jmp     short loc_180017F86
0x180017f7f  lea     rsi, aNotComputed; "Not computed"
0x180017f86  mov     r8, rsi
0x180017f89  lea     rdx, aSS_0; "%s%s"
0x180017f90  lea     rcx, [rbp+0F0h+var_D0]
0x180017f94  call    ??$swprintf_s@$0CA@@@YAHAEAY0CA@GPEBGZZ; swprintf_s<32>(ushort (&)[32],ushort const *,...)
0x180017f99  cmp     dword ptr [rdi+280h], 0
0x180017fa0  cmovz   r12, r13
0x180017fa4  test    r15, r15
0x180017fa7  jz      short loc_180017FDE
0x180017fa9  mov     ecx, [r15]
0x180017fac  test    ecx, ecx
0x180017fae  jz      short loc_180017FD5
0x180017fb0  sub     ecx, 1
0x180017fb3  jz      short loc_180017FCC
0x180017fb5  cmp     ecx, 1
0x180017fb8  jz      short loc_180017FC3
0x180017fba  lea     r8, aUnknown; "Unknown"
0x180017fc1  jmp     short loc_180017FE5
0x180017fc3  lea     r8, aYes; "Yes"
0x180017fca  jmp     short loc_180017FE5
0x180017fcc  lea     r8, aNo; "No"
0x180017fd3  jmp     short loc_180017FE5
0x180017fd5  lea     r8, aInvalid; "Invalid"
0x180017fdc  jmp     short loc_180017FE5
0x180017fde  lea     r8, aNotComputed; "Not computed"
0x180017fe5  mov     r9, r12
0x180017fe8  lea     rdx, aSS_0; "%s%s"
0x180017fef  lea     rcx, [rbp+0F0h+var_110]
0x180017ff3  call    ??$swprintf_s@$0CA@@@YAHAEAY0CA@GPEBGZZ; swprintf_s<32>(ushort (&)[32],ushort const *,...)
0x180017ff8  call    ?Instance@AudioSrvPolicyManagerTelemetryProvider@@KAPEAV1@XZ; AudioSrvPolicyManagerTelemetryProvider::Instance(void)
0x180017ffd  mov     r10, [rax+8]
0x180018001  mov     eax, [r10]
0x180018004  cmp     eax, 5
0x180018007  jbe     loc_1800181C3
0x18001800d  mov     rcx, [r10+18h]
0x180018011  mov     rax, [r10+10h]
0x180018015  bt      rax, 10h
0x18001801a  jnb     loc_1800181C3
0x180018020  mov     rax, rcx
0x180018023  and     eax, 10000h
0x180018028  cmp     rax, rcx
0x18001802b  jnz     loc_1800181C3
0x180018031  mov     eax, [rdi+0D4h]
0x180018037  mov     [rsp+1F0h+var_1C0], eax
0x18001803b  mov     rax, [rdi+2B8h]
0x180018042  mov     [rsp+1F0h+var_1B8], rax
0x180018047  mov     rdx, [rdi+18h]
0x18001804b  lea     r8, [rbp+0F0h+var_110]
0x18001804f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180018056  mov     rax, rcx
0x180018059  nop     dword ptr [rax+00000000h]
0x180018060  lea     rax, [rax+1]
0x180018064  cmp     word ptr [r8+rax*2], 0
0x18001806a  jnz     short loc_180018060
0x18001806c  lea     r8, [rbp+0F0h+var_110]
0x180018070  mov     [rbp+0F0h+var_120], r8
0x180018074  lea     eax, ds:2[rax*2]
0x18001807b  mov     [rbp+0F0h+var_118], eax
0x18001807e  xor     r9d, r9d; RelatedActivityId
0x180018081  mov     [rbp+0F0h+var_114], r9d
0x180018085  lea     r8, [rbp+0F0h+var_D0]
0x180018089  mov     rax, rcx
0x18001808c  nop     dword ptr [rax+00h]
0x180018090  lea     rax, [rax+1]
0x180018094  cmp     [r8+rax*2], r9w
0x180018099  jnz     short loc_180018090
0x18001809b  lea     r8, [rbp+0F0h+var_D0]
0x18001809f  mov     [rbp+0F0h+var_130], r8
0x1800180a3  lea     eax, ds:2[rax*2]
0x1800180aa  mov     [rbp+0F0h+var_128], eax
0x1800180ad  mov     [rbp+0F0h+var_124], r9d
0x1800180b1  lea     r8, [rbp+0F0h+var_90]
0x1800180b5  mov     rax, rcx
0x1800180b8  nop     dword ptr [rax+rax+00000000h]
0x1800180c0  lea     rax, [rax+1]
0x1800180c4  cmp     [r8+rax*2], r9w
0x1800180c9  jnz     short loc_1800180C0
0x1800180cb  lea     r8, [rbp+0F0h+var_90]
0x1800180cf  mov     [rbp+0F0h+var_140], r8
0x1800180d3  lea     eax, ds:2[rax*2]
0x1800180da  mov     [rbp+0F0h+var_138], eax
0x1800180dd  mov     [rbp+0F0h+var_134], r9d
0x1800180e1  lea     rax, [rsp+1F0h+var_1C0]
0x1800180e6  mov     [rbp+0F0h+var_150], rax
0x1800180ea  mov     [rbp+0F0h+var_148], 4
0x1800180f2  lea     rax, [rsp+1F0h+var_1B8]
0x1800180f7  mov     [rbp+0F0h+var_160], rax
0x1800180fb  mov     [rbp+0F0h+var_158], 8
0x180018103  test    rdx, rdx
0x180018106  jz      short loc_180018124
0x180018108  nop     dword ptr [rax+rax+00000000h]
0x180018110  lea     rcx, [rcx+1]
0x180018114  cmp     [rdx+rcx*2], r9w
0x180018119  jnz     short loc_180018110
0x18001811b  lea     ecx, ds:2[rcx*2]
0x180018122  jmp     short loc_18001812C
0x180018124  mov     rdx, r13
0x180018127  mov     ecx, 2
0x18001812c  mov     [rbp+0F0h+var_170], rdx
0x180018130  mov     [rbp+0F0h+var_168], ecx
0x180018133  mov     [rbp+0F0h+var_164], r9d
0x180018137  mov     dword ptr [rsp+1F0h+EventDescriptor.Id], 0B000000h
0x18001813f  movzx   eax, cs:word_180057D07
0x180018146  mov     dword ptr [rsp+1F0h+EventDescriptor.Level], eax
0x18001814a  mov     [rsp+1F0h+EventDescriptor.Keyword], 10000h
0x180018153  mov     rax, [r10+8]
0x180018157  mov     [rsp+1F0h+var_190.Ptr], rax
0x18001815c  movzx   eax, word ptr [rax]
0x18001815f  mov     [rsp+1F0h+var_190.Size], eax
0x180018163  mov     dword ptr [rsp+1F0h+var_190.0Ch], 2
0x18001816b  lea     rax, unk_180057D11
0x180018172  mov     [rsp+1F0h+var_180], rax
0x180018177  mov     [rsp+1F0h+var_178], 6Ch ; 'l'
0x18001817f  mov     [rsp+1F0h+var_174], 1
0x180018187  lea     rax, _TraceLoggingMetadataEnd
0x18001818e  lea     rcx, _TraceLoggingMetadata
0x180018195  sub     eax, ecx
0x180018197  mov     [rsp+1F0h+var_1BC], eax
0x18001819b  mov     eax, [rsp+1F0h+var_1BC]
0x18001819f  lea     rax, [rsp+1F0h+var_190]
0x1800181a4  mov     [rsp+1F0h+UserData], rax; UserData
0x1800181a9  mov     [rsp+1F0h+UserDataCount], 8; UserDataCount
0x1800181b1  xor     r8d, r8d; ActivityId
0x1800181b4  lea     rdx, [rsp+1F0h+EventDescriptor]; EventDescriptor
0x1800181b9  mov     rcx, [r10+20h]; RegHandle
0x1800181bd  call    cs:__imp_EventWriteTransfer
0x1800181c3  mov     r12, [rsp+1F0h+var_1B0]
0x1800181c8  test    r12, r12
0x1800181cb  jz      short loc_1800181D6
0x1800181cd  mov     rcx, r12; lpCriticalSection
0x1800181d0  call    cs:__imp_LeaveCriticalSection
0x1800181d6  xor     eax, eax
0x1800181d8  mov     rcx, [rbp+0F0h+var_50]
0x1800181df  xor     rcx, rsp; StackCookie
0x1800181e2  call    __security_check_cookie
0x1800181e7  add     rsp, 1B8h
0x1800181ee  pop     r15
0x1800181f0  pop     r14
0x1800181f2  pop     r13
0x1800181f4  pop     r12
0x1800181f6  pop     rdi
0x1800181f7  pop     rsi
0x1800181f8  pop     rbx
0x1800181f9  pop     rbp
0x1800181fa  retn
```
