# CDeploymentReportingUpdateGroup::DeserializeInternal(CSerializationHelper &,tagDeploymentReportingUpdateEvent *,CSusArrayList<tagDeploymentReportingUpdateEvent,CSusArrayListItemOpDeploymentReportingUpdateEvent> &)

- ea: `0x1800213a0`
- end: `0x18002157c`
- name: `?DeserializeInternal@CDeploymentReportingUpdateGroup@@AEAAJAEAVCSerializationHelper@@PEAUtagDeploymentReportingUpdateEvent@@AEAV?$CSusArrayList@UtagDeploymentReportingUpdateEvent@@VCSusArrayListItemOpDeploymentReportingUpdateEvent@@@@@Z`
- size: `476`
- prototype: `__int64 __fastcall(__int64, CSerializationHelper *, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800211a4`

## callees

- `0x180003180`
- `0x18001ede0`
- `0x1800213a0`
- `0x1800217c8`
- `0x180047cec`
- `0x180047dbc`
- `0x180047e84`
- `0x180061d54`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002147f`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002147f`

## string_xrefs

- `0x1800213ca`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\DPReportingData.cpp`
- `0x18002149b`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\DPReportingData.cpp`
- `0x1800214c6`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\DPReportingData.cpp`
- `0x180021501`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\DPReportingData.cpp`
- `0x18002152c`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\DPReportingData.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDeploymentReportingUpdateGroup::DeserializeInternal(
        __int64 a1,
        CSerializationHelper *a2,
        __int64 a3,
        __int64 a4)
{
  int v7; // ebx
  __int64 v8; // rdx
  int v10; // eax
  unsigned int v11; // edi
  __int64 v12; // r9
  __int64 v13; // rdx
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  wchar_t **v18; // rcx
  struct CSerializationHelper *v19; // rdx
  wchar_t **v20; // rbx
  int updated; // eax
  unsigned int v22; // [rsp+20h] [rbp-28h] BYREF
  wchar_t **v23; // [rsp+28h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( !a3 )
  {
    v7 = -2147467261;
    v8 = 1754;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\DPReportingData.cpp",
      (const char *)(unsigned int)v7,
      v22);
    return (unsigned int)v7;
  }
  v22 = 0;
  v23 = 0;
  v10 = CSerializationHelper::RawDeserializeData(a2, (char *)(a3 + 8), 4u);
  v11 = v10;
  if ( v10 < 0 )
  {
    v12 = (unsigned int)v10;
    v13 = 1636;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\DPReportingData.cpp",
      (const char *)v12,
      v22);
LABEL_24:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6DC,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\DPReportingData.cpp",
      (const char *)v11,
      v22);
    return v11;
  }
  v14 = CSerializationHelper::RawDeserializeString(a2, (wchar_t **)(a3 + 16), 0x400u);
  v11 = v14;
  if ( v14 < 0 )
  {
    v12 = (unsigned int)v14;
    v13 = 1642;
    goto LABEL_15;
  }
  v15 = CSerializationHelper::RawDeserializeArrayCount(a2, &v22);
  v11 = v15;
  if ( v15 < 0 )
  {
    v12 = (unsigned int)v15;
    v13 = 1647;
    goto LABEL_15;
  }
  if ( v22 )
  {
    v16 = CSerializationHelper::RawDeserializeData(a2, *(char **)(a3 + 24), v22);
    v11 = v16;
    if ( v16 < 0 )
    {
      v12 = (unsigned int)v16;
      v13 = 1651;
      goto LABEL_15;
    }
    if ( !IsValidSid(*(PSID *)(a3 + 24)) )
    {
      v11 = -2147024883;
      v13 = 1655;
      v12 = 2147942413LL;
      goto LABEL_15;
    }
  }
  else
  {
    *(_QWORD *)(a3 + 24) = 0;
  }
  v17 = WuSmartPtr::XPtrBase<tagDeployableUpdateData,WuSmartPtr::Policies::STPolicy<tagDeployableUpdateData>>::ReleaseAndAlloc(&v23);
  v11 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x682,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\DPReportingData.cpp",
      (const char *)(unsigned int)v17,
      v22);
    v18 = v23;
    if ( !v23 )
      goto LABEL_24;
LABEL_23:
    operator delete(v18, (const struct std::nothrow_t *)0x288);
    goto LABEL_24;
  }
  v19 = a2;
  v20 = v23;
  updated = DeserializeUpdateDeploymentReportingData(v23, v19);
  v11 = updated;
  if ( updated < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x684,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\DPReportingData.cpp",
      (const char *)(unsigned int)updated,
      v22);
    if ( !v20 )
      goto LABEL_24;
    v18 = v20;
    goto LABEL_23;
  }
  *(_QWORD *)a3 = v20;
  v7 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)a4 + 8LL))(a4, a3, 0);
  if ( v7 < 0 )
  {
    v8 = 1758;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x1800213a0  mov     [rsp+arg_0], rbx
0x1800213a5  push    rsi
0x1800213a6  push    rdi
0x1800213a7  push    r14
0x1800213a9  sub     rsp, 30h
0x1800213ad  mov     r14, r9
0x1800213b0  mov     rsi, r8
0x1800213b3  mov     rbx, rdx
0x1800213b6  test    r8, r8
0x1800213b9  jnz     short loc_1800213E0
0x1800213bb  mov     ebx, 80004003h
0x1800213c0  mov     edx, 6DAh; void *
0x1800213c5  mov     rcx, [rsp+48h]; this
0x1800213ca  lea     r8, aCW1SSrcClientU_11; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x1800213d1  mov     r9d, ebx; char *
0x1800213d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800213d9  mov     eax, ebx
0x1800213db  jmp     loc_18002156E
0x1800213e0  lea     rdx, [r8+8]; void *
0x1800213e4  mov     [rsp+48h+var_28], 0; int
0x1800213ec  mov     r8d, 4; unsigned int
0x1800213f2  mov     [rsp+48h+var_20], 0
0x1800213fb  mov     rcx, rbx; this
0x1800213fe  call    ?RawDeserializeData@CSerializationHelper@@QEAAJPEAXK@Z; CSerializationHelper::RawDeserializeData(void *,ulong)
0x180021403  mov     edi, eax
0x180021405  test    eax, eax
0x180021407  jns     short loc_180021416
0x180021409  mov     r9d, eax
0x18002140c  mov     edx, 664h
0x180021411  jmp     loc_180021496
0x180021416  lea     rdx, [rsi+10h]; wchar_t **
0x18002141a  mov     r8d, 400h; unsigned int
0x180021420  mov     rcx, rbx; this
0x180021423  call    ?RawDeserializeString@CSerializationHelper@@QEAAJPEAPEA_WK@Z; CSerializationHelper::RawDeserializeString(wchar_t * *,ulong)
0x180021428  mov     edi, eax
0x18002142a  test    eax, eax
0x18002142c  jns     short loc_180021438
0x18002142e  mov     r9d, eax
0x180021431  mov     edx, 66Ah
0x180021436  jmp     short loc_180021496
0x180021438  lea     rdx, [rsp+48h+var_28]; unsigned int *
0x18002143d  mov     rcx, rbx; this
0x180021440  call    ?RawDeserializeArrayCount@CSerializationHelper@@QEAAJPEAK@Z; CSerializationHelper::RawDeserializeArrayCount(ulong *)
0x180021445  mov     edi, eax
0x180021447  test    eax, eax
0x180021449  jns     short loc_180021455
0x18002144b  mov     r9d, eax
0x18002144e  mov     edx, 66Fh
0x180021453  jmp     short loc_180021496
0x180021455  mov     r8d, [rsp+48h+var_28]; unsigned int
0x18002145a  test    r8d, r8d
0x18002145d  jz      short loc_1800214A9
0x18002145f  mov     rdx, [rsi+18h]; void *
0x180021463  mov     rcx, rbx; this
0x180021466  call    ?RawDeserializeData@CSerializationHelper@@QEAAJPEAXK@Z; CSerializationHelper::RawDeserializeData(void *,ulong)
0x18002146b  mov     edi, eax
0x18002146d  test    eax, eax
0x18002146f  jns     short loc_18002147B
0x180021471  mov     r9d, eax
0x180021474  mov     edx, 673h
0x180021479  jmp     short loc_180021496
0x18002147b  mov     rcx, [rsi+18h]; pSid
0x18002147f  call    cs:__imp_IsValidSid
0x180021485  test    eax, eax
0x180021487  jnz     short loc_1800214B1
0x180021489  mov     edi, 8007000Dh
0x18002148e  mov     edx, 677h; void *
0x180021493  mov     r9d, edi; char *
0x180021496  mov     rcx, [rsp+48h]; this
0x18002149b  lea     r8, aCW1SSrcClientU_11; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x1800214a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800214a7  jmp     short loc_180021527
0x1800214a9  mov     qword ptr [rsi+18h], 0
0x1800214b1  lea     rcx, [rsp+48h+var_20]
0x1800214b6  call    ?ReleaseAndAlloc@?$XPtrBase@UtagDeployableUpdateData@@U?$STPolicy@UtagDeployableUpdateData@@@Policies@WuSmartPtr@@@WuSmartPtr@@QEAAJXZ; WuSmartPtr::XPtrBase<tagDeployableUpdateData,WuSmartPtr::Policies::STPolicy<tagDeployableUpdateData>>::ReleaseAndAlloc(void)
0x1800214bb  mov     edi, eax
0x1800214bd  test    eax, eax
0x1800214bf  jns     short loc_1800214E6
0x1800214c1  mov     rcx, [rsp+48h]; this
0x1800214c6  lea     r8, aCW1SSrcClientU_11; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x1800214cd  mov     r9d, eax; char *
0x1800214d0  mov     edx, 682h; void *
0x1800214d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800214da  mov     rcx, [rsp+48h+var_20]
0x1800214df  test    rcx, rcx
0x1800214e2  jz      short loc_180021527
0x1800214e4  jmp     short loc_18002151D
0x1800214e6  mov     rdx, rbx; this
0x1800214e9  mov     rbx, [rsp+48h+var_20]
0x1800214ee  mov     rcx, rbx; wchar_t **
0x1800214f1  call    ?DeserializeUpdateDeploymentReportingData@@YAJAEAUtagUpdateDeploymentReportingData@@AEAVCSerializationHelper@@@Z; DeserializeUpdateDeploymentReportingData(tagUpdateDeploymentReportingData &,CSerializationHelper &)
0x1800214f6  mov     edi, eax
0x1800214f8  test    eax, eax
0x1800214fa  jns     short loc_180021544
0x1800214fc  mov     rcx, [rsp+48h]; this
0x180021501  lea     r8, aCW1SSrcClientU_11; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180021508  mov     r9d, eax; char *
0x18002150b  mov     edx, 684h; void *
0x180021510  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021515  test    rbx, rbx
0x180021518  jz      short loc_180021527
0x18002151a  mov     rcx, rbx; void *
0x18002151d  mov     edx, 288h; struct std::nothrow_t *
0x180021522  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180021527  mov     rcx, [rsp+48h]; this
0x18002152c  lea     r8, aCW1SSrcClientU_11; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180021533  mov     r9d, edi; char *
0x180021536  mov     edx, 6DCh; void *
0x18002153b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021540  mov     eax, edi
0x180021542  jmp     short loc_18002156E
0x180021544  mov     [rsi], rbx
0x180021547  xor     r8d, r8d
0x18002154a  mov     rax, [r14]
0x18002154d  mov     rdx, rsi
0x180021550  mov     rcx, r14
0x180021553  mov     rax, [rax+8]
0x180021557  call    _guard_dispatch_icall
0x18002155c  mov     ebx, eax
0x18002155e  test    eax, eax
0x180021560  jns     short loc_18002156C
0x180021562  mov     edx, 6DEh
0x180021567  jmp     loc_1800213C5
0x18002156c  xor     eax, eax
0x18002156e  mov     rbx, [rsp+48h+arg_0]
0x180021573  add     rsp, 30h
0x180021577  pop     r14
0x180021579  pop     rdi
0x18002157a  pop     rsi
0x18002157b  retn
```
