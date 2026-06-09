# CUpdateDeploymentJob::ProcessNoopUpdate(ulong)

- ea: `0x18002ac0c`
- end: `0x18002b03c`
- name: `?ProcessNoopUpdate@CUpdateDeploymentJob@@AEAAJK@Z`
- size: `1072`
- prototype: `__int64 __fastcall(CUpdateDeploymentJob *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18002cfc0`
- `0x18002d3d0`

## callees

- `0x180003180`
- `0x1800110fc`
- `0x180011b44`
- `0x180011bf0`
- `0x1800217c8`
- `0x180022790`
- `0x18002a674`
- `0x18002a868`
- `0x18002ac0c`
- `0x180061960`
- `0x180061d54`
- `0x180068ea0`

## string_xrefs

- `0x18002ac4e`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x18002acba`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x18002ad9b`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x18002adf7`: `Deployment job Id %ws : Update %ws is out-of-scope`
- `0x18002afac`: `Deployment job Id %ws : The update %ws is for %ws, installable: %ws, installed: %ws, and present: %ws`
- `0x18002aeb4`: `Deployment job Id %ws : The update %ws is Out of Scope`
- `0x18002af5d`: `Install`
- `0x18002af54`: `Uninstall`
- `0x18002af42`: `Commit`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CUpdateDeploymentJob::ProcessNoopUpdate(struct _GUID *this, unsigned int a2)
{
  __int64 v2; // r15
  __int64 v4; // rdx
  unsigned int v5; // ebx
  __int64 v6; // rdi
  int v7; // r13d
  int v8; // eax
  int v9; // eax
  int v10; // eax
  _DWORD *v11; // r14
  int v12; // edi
  __int64 updated; // rbx
  __int64 v14; // rax
  int v15; // eax
  int v16; // ecx
  __int64 v17; // rbx
  __int64 v18; // rax
  const wchar_t *v19; // r13
  const wchar_t *v20; // rax
  const wchar_t *v21; // rax
  __int64 v22; // rdx
  const wchar_t *v23; // r14
  __int64 v24; // rbx
  __int64 v25; // rax
  unsigned int *v27; // [rsp+20h] [rbp-E0h]
  int v28; // [rsp+20h] [rbp-E0h]
  const wchar_t *v29; // [rsp+70h] [rbp-90h]
  const wchar_t *v30; // [rsp+78h] [rbp-88h]
  _BYTE v31[80]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v32[112]; // [rsp+E0h] [rbp-20h] BYREF
  void *v33; // [rsp+150h] [rbp+50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v2 = a2;
  if ( a2 >= this[43].Data1 )
  {
    v4 = 1483;
LABEL_3:
    v5 = -2145120257;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
      (const char *)0x80240FFFLL,
      (int)v27);
    return v5;
  }
  _mm_lfence();
  if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)this[43].Data4 + 8LL * a2) + 544LL) )
  {
    v4 = 1484;
    goto LABEL_3;
  }
  _mm_lfence();
  v33 = 0;
  v6 = *(_QWORD *)(*(_QWORD *)this[43].Data4 + 8LL * a2);
  v7 = *(_DWORD *)(v6 + 56);
  v8 = WuSmartPtr::XPtrBase<tagDeployableUpdateData,WuSmartPtr::Policies::STPolicy<tagDeployableUpdateData>>::ReleaseAndAlloc(&v33);
  v5 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5D3,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
      (const char *)(unsigned int)v8,
      (int)v27);
    goto LABEL_57;
  }
  switch ( *(_DWORD *)(v6 + 56) )
  {
    case 1:
      v9 = 1;
      break;
    case 2:
      v9 = 2;
      break;
    case 4:
      v9 = 4;
      break;
    case 8:
      v9 = 8;
      break;
    default:
      v9 = 0;
      break;
  }
  v28 = v9;
  v10 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)this[44].Data4 + 24LL))(
          *(_QWORD *)this[44].Data4,
          5,
          this[50].Data1);
  v5 = v10;
  if ( v10 >= 0 )
  {
    v11 = v33;
    if ( *((_DWORD *)v33 + 2) )
    {
      v15 = *((_DWORD *)v33 + 3);
      if ( v7 == 4 )
      {
        if ( v15 == 3 || *((_DWORD *)v33 + 4) )
          v12 = -2145124281;
        else
          v12 = 2359306;
      }
      else if ( v7 == 2 )
      {
        if ( v15 == 3 || *((_DWORD *)v33 + 4) && v15 != 2 )
        {
LABEL_55:
          v5 = 0;
          goto LABEL_56;
        }
        v12 = 2359303;
      }
      else
      {
        v16 = 2359302;
        if ( (unsigned int)(v15 - 3) > 1 )
          v16 = -2145124329;
        v12 = v16;
      }
    }
    else
    {
      v12 = -2145124329;
      updated = Trace::UpdateIdToString::UpdateIdToString(
                  (Trace::UpdateIdToString *)v32,
                  (const struct tagDSGlobalUpdateId *)(*(_QWORD *)(*(_QWORD *)this[43].Data4 + 8 * v2) + 200LL));
      v14 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v31, this + 1);
      LODWORD(v27) = -2145124329;
      WUTrace(0, 0, 0x1000000, 4, v27, L"Deployment job Id %ws : Update %ws is out-of-scope", v14, updated);
    }
    if ( v11[2] )
    {
      _mm_lfence();
      v19 = L"No";
      v20 = L"No";
      if ( v11[4] )
        v20 = L"Yes";
      v29 = v20;
      v21 = L"No";
      if ( v11[3] == 3 )
        v21 = L"Yes";
      v30 = v21;
      if ( v11[3] == 2 )
        v19 = L"Yes";
      v22 = *(_QWORD *)(*(_QWORD *)this[43].Data4 + 8 * v2);
      switch ( *(_DWORD *)(v22 + 56) )
      {
        case 1:
          v23 = L"Install";
          break;
        case 2:
          v23 = L"Uninstall";
          break;
        case 4:
          v23 = L"Revert";
          break;
        case 8:
          v23 = L"Commit";
          break;
        default:
          v23 = L"Unknown";
          break;
      }
      v24 = Trace::UpdateIdToString::UpdateIdToString(
              (Trace::UpdateIdToString *)v32,
              (const struct tagDSGlobalUpdateId *)(v22 + 200));
      v25 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v31, this + 1);
      LODWORD(v27) = v12;
      WUTrace(
        0,
        0,
        0x1000000,
        3,
        v27,
        L"Deployment job Id %ws : The update %ws is for %ws, installable: %ws, installed: %ws, and present: %ws",
        v25,
        v24,
        v23,
        v19,
        v30,
        v29);
    }
    else
    {
      v17 = Trace::UpdateIdToString::UpdateIdToString(
              (Trace::UpdateIdToString *)v32,
              (const struct tagDSGlobalUpdateId *)(*(_QWORD *)(*(_QWORD *)this[43].Data4 + 8 * v2) + 200LL));
      v18 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v31, this + 1);
      LODWORD(v27) = v12;
      WUTrace(0, 0, 0x1000000, 3, v27, L"Deployment job Id %ws : The update %ws is Out of Scope", v18, v17);
    }
    if ( v12 >= 0 )
      CUpdateDeploymentJob::OnUpdateComplete((CUpdateDeploymentJob *)this, v2, v12);
    else
      CUpdateDeploymentJob::OnUpdateFailure((CUpdateDeploymentJob *)this, v2, v12, 0, 0);
    goto LABEL_55;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5E2,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
    (const char *)(unsigned int)v10,
    v28);
LABEL_56:
  DPFreeDeployableUpdateData((char *)v33);
LABEL_57:
  if ( v33 )
    operator delete(v33, (const struct std::nothrow_t *)0x288);
  return v5;
}

```

## disassembly

```asm
0x18002ac0c  mov     [rsp-8+arg_10], rbx
0x18002ac11  push    rbp
0x18002ac12  push    rsi
0x18002ac13  push    rdi
0x18002ac14  push    r12
0x18002ac16  push    r13
0x18002ac18  push    r14
0x18002ac1a  push    r15
0x18002ac1c  lea     rbp, [rsp-60h]
0x18002ac21  sub     rsp, 160h
0x18002ac28  mov     rax, cs:__security_cookie
0x18002ac2f  xor     rax, rsp
0x18002ac32  mov     [rbp+90h+var_38], rax
0x18002ac36  mov     r15d, edx
0x18002ac39  mov     rsi, rcx
0x18002ac3c  cmp     edx, [rcx+2B0h]
0x18002ac42  jb      short loc_18002AC69
0x18002ac44  mov     edx, 5CBh; void *
0x18002ac49  mov     ebx, 80240FFFh
0x18002ac4e  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18002ac55  mov     r9d, ebx; char *
0x18002ac58  mov     rcx, [rbp+98h]; this
0x18002ac5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ac64  jmp     loc_18002B013
0x18002ac69  lfence
0x18002ac6c  mov     rax, [rcx+2B8h]
0x18002ac73  mov     rcx, [rax+r15*8]
0x18002ac77  cmp     dword ptr [rcx+220h], 0
0x18002ac7e  jz      short loc_18002AC87
0x18002ac80  mov     edx, 5CCh
0x18002ac85  jmp     short loc_18002AC49
0x18002ac87  lfence
0x18002ac8a  mov     [rbp+90h+var_40], 0
0x18002ac92  mov     rax, [rsi+2B8h]
0x18002ac99  mov     rdi, [rax+r15*8]
0x18002ac9d  mov     r13d, [rdi+38h]
0x18002aca1  lea     rcx, [rbp+90h+var_40]
0x18002aca5  call    ?ReleaseAndAlloc@?$XPtrBase@UtagDeployableUpdateData@@U?$STPolicy@UtagDeployableUpdateData@@@Policies@WuSmartPtr@@@WuSmartPtr@@QEAAJXZ; WuSmartPtr::XPtrBase<tagDeployableUpdateData,WuSmartPtr::Policies::STPolicy<tagDeployableUpdateData>>::ReleaseAndAlloc(void)
0x18002acaa  mov     ebx, eax
0x18002acac  test    eax, eax
0x18002acae  jns     short loc_18002ACD0
0x18002acb0  mov     rcx, [rbp+98h]; this
0x18002acb7  mov     r9d, eax; char *
0x18002acba  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18002acc1  mov     edx, 5D3h; void *
0x18002acc6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002accb  jmp     loc_18002B000
0x18002acd0  lea     rax, [rbp+90h+var_40]
0x18002acd4  mov     [rbp+90h+var_110], rax
0x18002acd8  mov     [rbp+90h+var_108], 1
0x18002acdc  mov     r10, [rsi+2C8h]
0x18002ace3  mov     rax, [r10]
0x18002ace6  mov     rax, [rax+18h]
0x18002acea  mov     [rsp+190h+var_120], rax
0x18002acef  mov     rdx, [rbp+90h+var_40]
0x18002acf3  mov     r8, [rdi+48h]
0x18002acf7  mov     r9, [rdi+40h]
0x18002acfb  mov     r11d, [rdi+18h]
0x18002acff  mov     rbx, [rdi+10h]
0x18002ad03  mov     r14, [rdi+30h]
0x18002ad07  mov     ecx, [rdi+38h]
0x18002ad0a  mov     edi, 2
0x18002ad0f  sub     ecx, 1
0x18002ad12  jz      short loc_18002AD38
0x18002ad14  sub     ecx, 1
0x18002ad17  jz      short loc_18002AD34
0x18002ad19  sub     ecx, edi
0x18002ad1b  jz      short loc_18002AD2D
0x18002ad1d  cmp     ecx, 4
0x18002ad20  jz      short loc_18002AD26
0x18002ad22  xor     eax, eax
0x18002ad24  jmp     short loc_18002AD3D
0x18002ad26  mov     eax, 8
0x18002ad2b  jmp     short loc_18002AD3D
0x18002ad2d  mov     eax, 4
0x18002ad32  jmp     short loc_18002AD3D
0x18002ad34  mov     eax, edi
0x18002ad36  jmp     short loc_18002AD3D
0x18002ad38  mov     eax, 1
0x18002ad3d  mov     [rsp+190h+var_130], 0
0x18002ad45  mov     [rsp+190h+var_138], rdx
0x18002ad4a  mov     [rsp+190h+var_140], 0
0x18002ad53  mov     [rsp+190h+var_148], r8
0x18002ad58  mov     [rsp+190h+var_150], r9
0x18002ad5d  mov     dword ptr [rsp+190h+var_158], r11d
0x18002ad62  mov     [rsp+190h+var_160], rbx
0x18002ad67  mov     [rsp+190h+var_168], r14
0x18002ad6c  mov     dword ptr [rsp+190h+var_170], eax; int
0x18002ad70  xor     r9d, r9d
0x18002ad73  mov     r8d, [rsi+320h]
0x18002ad7a  lea     edx, [r9+5]
0x18002ad7e  mov     rcx, r10
0x18002ad81  mov     rax, [rsp+190h+var_120]
0x18002ad86  call    _guard_dispatch_icall
0x18002ad8b  mov     ebx, eax
0x18002ad8d  test    eax, eax
0x18002ad8f  jns     short loc_18002ADB1
0x18002ad91  mov     rcx, [rbp+98h]; this
0x18002ad98  mov     r9d, eax; char *
0x18002ad9b  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18002ada2  mov     edx, 5E2h; void *
0x18002ada7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002adac  jmp     loc_18002AFF6
0x18002adb1  mov     r14, [rbp+90h+var_40]
0x18002adb5  xor     edx, edx
0x18002adb7  cmp     [r14+8], edx
0x18002adbb  jnz     short loc_18002AE1E
0x18002adbd  mov     edi, 80240017h
0x18002adc2  mov     rax, [rsi+2B8h]
0x18002adc9  mov     rdx, [rax+r15*8]
0x18002adcd  add     rdx, 0C8h; struct tagDSGlobalUpdateId *
0x18002add4  lea     rcx, [rbp+90h+var_B0]; this
0x18002add8  call    ??0UpdateIdToString@Trace@@QEAA@AEBUtagDSGlobalUpdateId@@@Z; Trace::UpdateIdToString::UpdateIdToString(tagDSGlobalUpdateId const &)
0x18002addd  mov     rbx, rax
0x18002ade0  lea     rdx, [rsi+10h]; struct _GUID *
0x18002ade4  lea     rcx, [rbp+90h+var_100]; this
0x18002ade8  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x18002aded  mov     [rsp+190h+var_158], rbx
0x18002adf2  mov     [rsp+190h+var_160], rax
0x18002adf7  lea     rax, aDeploymentJobI_9; "Deployment job Id %ws : Update %ws is o"...
0x18002adfe  mov     [rsp+190h+var_168], rax
0x18002ae03  mov     dword ptr [rsp+190h+var_170], edi
0x18002ae07  xor     edx, edx
0x18002ae09  xor     ecx, ecx
0x18002ae0b  lea     r9d, [rdx+4]
0x18002ae0f  mov     r8d, 1000000h
0x18002ae15  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18002ae1a  xor     edx, edx
0x18002ae1c  jmp     short loc_18002AE79
0x18002ae1e  mov     eax, [r14+0Ch]
0x18002ae22  cmp     r13d, 4
0x18002ae26  jnz     short loc_18002AE41
0x18002ae28  cmp     eax, 3
0x18002ae2b  jz      short loc_18002AE3A
0x18002ae2d  cmp     [r14+10h], edx
0x18002ae31  jnz     short loc_18002AE3A
0x18002ae33  mov     edi, 24000Ah
0x18002ae38  jmp     short loc_18002AE79
0x18002ae3a  mov     edi, 80240047h
0x18002ae3f  jmp     short loc_18002AE79
0x18002ae41  cmp     r13d, edi
0x18002ae44  jnz     short loc_18002AE64
0x18002ae46  cmp     eax, 3
0x18002ae49  jz      loc_18002AFF4
0x18002ae4f  cmp     [r14+10h], edx
0x18002ae53  jz      short loc_18002AE5D
0x18002ae55  cmp     eax, edi
0x18002ae57  jnz     loc_18002AFF4
0x18002ae5d  mov     edi, 240007h
0x18002ae62  jmp     short loc_18002AE79
0x18002ae64  add     eax, 0FFFFFFFDh
0x18002ae67  mov     ecx, 240006h
0x18002ae6c  mov     edi, 80240017h
0x18002ae71  cmp     eax, 1
0x18002ae74  cmova   ecx, edi
0x18002ae77  mov     edi, ecx
0x18002ae79  cmp     [r14+8], edx
0x18002ae7d  jnz     short loc_18002AEDC
0x18002ae7f  mov     rax, [rsi+2B8h]
0x18002ae86  mov     rdx, [rax+r15*8]
0x18002ae8a  add     rdx, 0C8h; struct tagDSGlobalUpdateId *
0x18002ae91  lea     rcx, [rbp+90h+var_B0]; this
0x18002ae95  call    ??0UpdateIdToString@Trace@@QEAA@AEBUtagDSGlobalUpdateId@@@Z; Trace::UpdateIdToString::UpdateIdToString(tagDSGlobalUpdateId const &)
0x18002ae9a  mov     rbx, rax
0x18002ae9d  lea     rdx, [rsi+10h]; struct _GUID *
0x18002aea1  lea     rcx, [rbp+90h+var_100]; this
0x18002aea5  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x18002aeaa  mov     [rsp+190h+var_158], rbx
0x18002aeaf  mov     [rsp+190h+var_160], rax
0x18002aeb4  lea     rax, aDeploymentJobI_45; "Deployment job Id %ws : The update %ws "...
0x18002aebb  mov     [rsp+190h+var_168], rax
0x18002aec0  mov     dword ptr [rsp+190h+var_170], edi
0x18002aec4  xor     edx, edx
0x18002aec6  xor     ecx, ecx
0x18002aec8  lea     r9d, [rdx+3]
0x18002aecc  mov     r8d, 1000000h
0x18002aed2  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18002aed7  jmp     loc_18002AFCF
0x18002aedc  lfence
0x18002aedf  lea     rcx, aYes_0; "Yes"
0x18002aee6  lea     r13, aNo_1; "No"
0x18002aeed  mov     rax, r13
0x18002aef0  cmp     [r14+10h], edx
0x18002aef4  cmovnz  rax, rcx
0x18002aef8  mov     [rsp+190h+var_120], rax
0x18002aefd  mov     rax, r13
0x18002af00  cmp     dword ptr [r14+0Ch], 3
0x18002af05  cmovz   rax, rcx
0x18002af09  mov     [rsp+190h+var_118], rax
0x18002af0e  cmp     dword ptr [r14+0Ch], 2
0x18002af13  cmovz   r13, rcx
0x18002af17  mov     rax, [rsi+2B8h]
0x18002af1e  mov     rdx, [rax+r15*8]
0x18002af22  mov     ecx, [rdx+38h]
0x18002af25  sub     ecx, 1
0x18002af28  jz      short loc_18002AF5D
0x18002af2a  sub     ecx, 1
0x18002af2d  jz      short loc_18002AF54
0x18002af2f  sub     ecx, 2
0x18002af32  jz      short loc_18002AF4B
0x18002af34  cmp     ecx, 4
0x18002af37  jz      short loc_18002AF42
0x18002af39  lea     r14, aUnknown_0; "Unknown"
0x18002af40  jmp     short loc_18002AF64
0x18002af42  lea     r14, aCommit; "Commit"
0x18002af49  jmp     short loc_18002AF64
0x18002af4b  lea     r14, aRevert_0; "Revert"
0x18002af52  jmp     short loc_18002AF64
0x18002af54  lea     r14, aUninstall; "Uninstall"
0x18002af5b  jmp     short loc_18002AF64
0x18002af5d  lea     r14, aInstall; "Install"
0x18002af64  add     rdx, 0C8h; struct tagDSGlobalUpdateId *
0x18002af6b  lea     rcx, [rbp+90h+var_B0]; this
0x18002af6f  call    ??0UpdateIdToString@Trace@@QEAA@AEBUtagDSGlobalUpdateId@@@Z; Trace::UpdateIdToString::UpdateIdToString(tagDSGlobalUpdateId const &)
0x18002af74  mov     rbx, rax
0x18002af77  lea     rdx, [rsi+10h]; struct _GUID *
0x18002af7b  lea     rcx, [rbp+90h+var_100]; this
0x18002af7f  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x18002af84  mov     rcx, [rsp+190h+var_120]
0x18002af89  mov     [rsp+190h+var_138], rcx
0x18002af8e  mov     rcx, [rsp+190h+var_118]
0x18002af93  mov     [rsp+190h+var_140], rcx
0x18002af98  mov     [rsp+190h+var_148], r13
0x18002af9d  mov     [rsp+190h+var_150], r14
0x18002afa2  mov     [rsp+190h+var_158], rbx
0x18002afa7  mov     [rsp+190h+var_160], rax
0x18002afac  lea     rax, aDeploymentJobI_56; "Deployment job Id %ws : The update %ws "...
0x18002afb3  mov     [rsp+190h+var_168], rax
0x18002afb8  mov     dword ptr [rsp+190h+var_170], edi
0x18002afbc  xor     edx, edx
0x18002afbe  xor     ecx, ecx
0x18002afc0  lea     r9d, [rdx+3]
0x18002afc4  mov     r8d, 1000000h
0x18002afca  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18002afcf  mov     r8d, edi; int
0x18002afd2  mov     edx, r15d; unsigned int
0x18002afd5  mov     rcx, rsi; this
0x18002afd8  test    edi, edi
0x18002afda  jns     short loc_18002AFEF
0x18002afdc  mov     [rsp+190h+var_170], 0; unsigned int *
0x18002afe5  xor     r9d, r9d; unsigned int
0x18002afe8  call    ?OnUpdateFailure@CUpdateDeploymentJob@@AEAAJKJKPEAK@Z; CUpdateDeploymentJob::OnUpdateFailure(ulong,long,ulong,ulong *)
0x18002afed  jmp     short loc_18002AFF4
0x18002afef  call    ?OnUpdateComplete@CUpdateDeploymentJob@@AEAAJKJ@Z; CUpdateDeploymentJob::OnUpdateComplete(ulong,long)
0x18002aff4  xor     ebx, ebx
0x18002aff6  mov     rcx, [rbp+90h+var_40]; void *
0x18002affa  call    ?DPFreeDeployableUpdateData@@YAXPEAX@Z; DPFreeDeployableUpdateData(void *)
0x18002afff  nop
0x18002b000  mov     rcx, [rbp+90h+var_40]; void *
0x18002b004  test    rcx, rcx
0x18002b007  jz      short loc_18002B013
0x18002b009  mov     edx, 288h; struct std::nothrow_t *
0x18002b00e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002b013  mov     eax, ebx
0x18002b015  mov     rcx, [rbp+90h+var_38]
0x18002b019  xor     rcx, rsp; StackCookie
0x18002b01c  call    __security_check_cookie
0x18002b021  mov     rbx, [rsp+190h+arg_10]
0x18002b029  add     rsp, 160h
0x18002b030  pop     r15
0x18002b032  pop     r14
0x18002b034  pop     r13
0x18002b036  pop     r12
0x18002b038  pop     rdi
0x18002b039  pop     rsi
0x18002b03a  pop     rbp
0x18002b03b  retn
```
