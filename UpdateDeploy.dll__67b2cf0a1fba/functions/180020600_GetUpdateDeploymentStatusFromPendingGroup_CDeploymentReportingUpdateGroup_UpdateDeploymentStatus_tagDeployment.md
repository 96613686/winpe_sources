# GetUpdateDeploymentStatusFromPendingGroup(CDeploymentReportingUpdateGroup *,UpdateDeploymentStatus * *,tagDeploymentReportingUpdateGroup *)

- ea: `0x180020600`
- end: `0x180020950`
- name: `?GetUpdateDeploymentStatusFromPendingGroup@@YAJPEAVCDeploymentReportingUpdateGroup@@PEAPEAVUpdateDeploymentStatus@@PEAUtagDeploymentReportingUpdateGroup@@@Z`
- size: `848`
- prototype: `__int64 __fastcall(struct CDeploymentReportingUpdateGroup *, struct UpdateDeploymentStatus **, struct tagDeploymentReportingUpdateGroup *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update`

## callers

- `0x180013494`

## callees

- `0x180003180`
- `0x180008b30`
- `0x18000c640`
- `0x18000dce4`
- `0x1800110fc`
- `0x180014888`
- `0x18001feb8`
- `0x180020460`
- `0x180020600`
- `0x180021584`
- `0x180061960`
- `0x180068ea0`

## import_xrefs

- `RPCRT4!UuidToStringW` at `0x18002073b`
- `RPCRT4!UuidToStringW` at `0x18002073b`

## string_xrefs

- `0x180020646`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\DPReportingData.cpp`
- `0x180020695`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\DPReportingData.cpp`
- `0x1800208a4`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\DPReportingData.cpp`
- `0x1800208e2`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\DPReportingData.cpp`
- `0x1800208f5`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\DPReportingData.cpp`
- `0x180020707`: `Deserialized Reporting Event doesn't contain valid Reporting Data.`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall GetUpdateDeploymentStatusFromPendingGroup(
        struct CDeploymentReportingUpdateGroup *a1,
        struct UpdateDeploymentStatus **a2,
        struct tagDeploymentReportingUpdateGroup *a3)
{
  struct UpdateDeploymentStatus **v4; // r14
  __int64 v6; // rdx
  int v8; // eax
  RPC_WSTR v9; // rcx
  int fixed; // edi
  struct UpdateDeploymentStatus *v11; // rbx
  char *v12; // rsi
  _OWORD *v13; // rax
  unsigned int v14; // r12d
  unsigned int v15; // eax
  struct tagUpdateDeploymentReportingData *v16; // r14
  __int64 v17; // rsi
  RPC_STATUS v18; // eax
  void *v19; // rcx
  int v20; // edx
  int updated; // eax
  __int64 v22; // rcx
  __int64 v23; // rdx
  unsigned __int64 v24; // r9
  __int64 v25; // rdx
  struct UpdateDeploymentStatus *v26; // rax
  int v27; // [rsp+20h] [rbp-49h]
  int v28; // [rsp+20h] [rbp-49h]
  struct UpdateDeploymentStatus *v29; // [rsp+30h] [rbp-39h] BYREF
  struct UpdateDeploymentStatus **v30; // [rsp+38h] [rbp-31h]
  struct tagUpdateDeploymentReportingData *v31[2]; // [rsp+40h] [rbp-29h] BYREF
  __int128 v32; // [rsp+50h] [rbp-19h]
  RPC_WSTR StringUuid; // [rsp+80h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v4 = a2;
  v30 = a2;
  if ( !a2 )
  {
    v6 = 1193;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\DPReportingData.cpp",
      (const char *)0x80004003LL,
      v27);
    return 2147500035LL;
  }
  if ( !a3 )
  {
    v6 = 1194;
    goto LABEL_3;
  }
  *(_OWORD *)v31 = 0;
  v32 = 0;
  v29 = 0;
  v8 = UpdateDeploymentStatus::CreateInstance(&v29);
  fixed = v8;
  if ( v8 >= 0 )
  {
    v12 = (char *)a1 + 24;
    if ( *((_DWORD *)a1 + 11) == 1 )
    {
      v13 = (_OWORD *)*((_QWORD *)a1 + 4);
      *(_OWORD *)v31 = *v13;
      v32 = v13[1];
    }
    v14 = 0;
    v15 = *((_DWORD *)a1 + 5);
    v11 = v29;
    if ( v15 )
    {
      v16 = v31[0];
      while ( 1 )
      {
        StringUuid = 0;
        if ( v14 >= v15 )
          break;
        v17 = *(_QWORD *)(*((_QWORD *)a1 + 1) + 32LL * v14);
        if ( v17 )
        {
          v18 = UuidToStringW((const UUID *)(v17 + 236), &StringUuid);
          fixed = v18;
          if ( v18 >= 1 )
            fixed = (unsigned __int16)v18 | 0x80010000;
          if ( fixed < 0 )
          {
            v25 = 1222;
            goto LABEL_43;
          }
          v19 = (void *)*((_QWORD *)v11 + 2);
          if ( v19 )
          {
            SusFree(v19);
            *((_QWORD *)v11 + 2) = 0;
          }
          fixed = DuplicateString<wchar_t *,wchar_t *>(StringUuid, (_QWORD *)v11 + 2);
          if ( fixed < 0 )
          {
            v25 = 1224;
            goto LABEL_43;
          }
          *((_DWORD *)v11 + 6) = *(_DWORD *)(v17 + 252);
          *((_DWORD *)v11 + 23) = *(_DWORD *)(v17 + 96);
          *((_DWORD *)v11 + 24) = *(_DWORD *)(v17 + 100);
          *((_DWORD *)v11 + 22) = ((*((int *)v11 + 23) >> 31) & 2) + 6;
          if ( *(_DWORD *)(v17 + 96) == 2367509 )
            *((_DWORD *)v11 + 26) = 1;
          if ( *(_DWORD *)(v17 + 476) && v16 )
          {
            *((_DWORD *)v16 + 10) = *(_DWORD *)(v17 + 40);
            v20 = *(_DWORD *)(v17 + 96);
            if ( *(_DWORD *)(v17 + 152) )
              v20 = *(_DWORD *)(v17 + 156) != 0 ? v20 : 0;
            *((_DWORD *)v16 + 24) = v20;
            if ( v20 < 0 )
            {
              if ( (unsigned int)(v20 + 2145116140) <= 1 )
                *((_DWORD *)v16 + 118) = 1;
              *((_DWORD *)v16 + 25) = *(_DWORD *)(v17 + 100);
              FixReplacementStringsForFailure(v16);
              if ( *((_DWORD *)v16 + 38) )
                *((_DWORD *)v16 + 39) = 1;
              fixed = FixRepeatFailCountAndFirmwareStatus((struct tagDeploymentReportingUpdateEvent *)v31);
              if ( fixed < 0 )
              {
                v25 = 1296;
                goto LABEL_43;
              }
            }
          }
        }
        else
        {
          v27 = 0;
          WUTrace(0, 0, 0x1000000, 4);
        }
        v9 = StringUuid;
        if ( StringUuid )
          XPtrRpcStringFree(StringUuid);
        ++v14;
        v15 = *((_DWORD *)a1 + 5);
        if ( v14 >= v15 )
        {
          v12 = (char *)a1 + 24;
          v4 = v30;
          goto LABEL_37;
        }
      }
      fixed = -2145124345;
      v25 = 1211;
LABEL_43:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v25,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\DPReportingData.cpp",
        (const char *)(unsigned int)fixed,
        v27);
      if ( StringUuid )
        XPtrRpcStringFree(StringUuid);
      goto LABEL_49;
    }
LABEL_37:
    updated = CDeploymentReportingUpdateGroup::CloneReportingUpdateEventFromEventList(
                (__int64)v9,
                (__int64)a1,
                a3,
                (_QWORD *)a3 + 1);
    fixed = updated;
    if ( updated >= 0 )
    {
      fixed = CDeploymentReportingUpdateGroup::CloneReportingUpdateEventFromEventList(
                v22,
                (__int64)v12,
                (_DWORD *)a3 + 4,
                (_QWORD *)a3 + 3);
      v24 = (unsigned int)fixed;
      if ( fixed >= 0 )
      {
        v26 = v11;
        v11 = 0;
        *v4 = v26;
        fixed = 0;
        goto LABEL_49;
      }
      v23 = 1772;
    }
    else
    {
      v23 = 1768;
      v24 = (unsigned int)updated;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\DPReportingData.cpp",
      (const char *)v24,
      v27);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x516,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\DPReportingData.cpp",
      (const char *)(unsigned int)fixed,
      v28);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4AF,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\DPReportingData.cpp",
      (const char *)(unsigned int)v8,
      v27);
    v11 = v29;
  }
LABEL_49:
  if ( v11 )
    (*(void (__fastcall **)(struct UpdateDeploymentStatus *))(*(_QWORD *)v11 + 16LL))(v11);
  return (unsigned int)fixed;
}

```

## disassembly

```asm
0x180020600  mov     [rsp-8+arg_18], rbx
0x180020605  push    rbp
0x180020606  push    rsi
0x180020607  push    rdi
0x180020608  push    r12
0x18002060a  push    r13
0x18002060c  push    r14
0x18002060e  push    r15
0x180020610  lea     rbp, [rsp-27h]
0x180020615  sub     rsp, 90h
0x18002061c  mov     rax, cs:__security_cookie
0x180020623  xor     rax, rsp
0x180020626  mov     [rbp+57h+var_38], rax
0x18002062a  mov     r13, r8
0x18002062d  mov     r14, rdx
0x180020630  mov     [rbp+57h+var_88], rdx
0x180020634  mov     r15, rcx
0x180020637  test    rdx, rdx
0x18002063a  jnz     short loc_180020660
0x18002063c  mov     edx, 4A9h; void *
0x180020641  mov     ebx, 80004003h
0x180020646  lea     r8, aCW1SSrcClientU_11; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18002064d  mov     r9d, ebx; char *
0x180020650  mov     rcx, [rbp+5Fh]; this
0x180020654  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020659  mov     eax, ebx
0x18002065b  jmp     loc_180020929
0x180020660  test    r13, r13
0x180020663  jnz     short loc_18002066C
0x180020665  mov     edx, 4AAh
0x18002066a  jmp     short loc_180020641
0x18002066c  xorps   xmm0, xmm0
0x18002066f  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x180020673  movups  [rbp+57h+var_70], xmm0
0x180020677  mov     [rbp+57h+var_90], 0
0x18002067f  lea     rcx, [rbp+57h+var_90]; struct UpdateDeploymentStatus **
0x180020683  call    ?CreateInstance@UpdateDeploymentStatus@@SAJPEAPEAV1@@Z; UpdateDeploymentStatus::CreateInstance(UpdateDeploymentStatus * *)
0x180020688  mov     edi, eax
0x18002068a  test    eax, eax
0x18002068c  jns     short loc_1800206AF
0x18002068e  mov     rcx, [rbp+5Fh]; this
0x180020692  mov     r9d, eax; char *
0x180020695  lea     r8, aCW1SSrcClientU_11; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18002069c  mov     edx, 4AFh; void *
0x1800206a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800206a6  mov     rbx, [rbp+57h+var_90]
0x1800206aa  jmp     loc_180020912
0x1800206af  lea     rsi, [r15+18h]
0x1800206b3  cmp     dword ptr [rsi+14h], 1
0x1800206b7  jnz     short loc_1800206CC
0x1800206b9  mov     rax, [r15+20h]
0x1800206bd  movups  xmm0, xmmword ptr [rax]
0x1800206c0  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x1800206c4  movups  xmm1, xmmword ptr [rax+10h]
0x1800206c8  movups  [rbp+57h+var_70], xmm1
0x1800206cc  xor     r12d, r12d
0x1800206cf  mov     eax, [r15+14h]
0x1800206d3  mov     rbx, [rbp+57h+var_90]
0x1800206d7  test    eax, eax
0x1800206d9  jz      loc_18002085F
0x1800206df  mov     r14, [rbp+57h+var_80]
0x1800206e3  mov     [rbp+57h+StringUuid], 0
0x1800206eb  cmp     r12d, eax
0x1800206ee  jnb     loc_180020893
0x1800206f4  mov     eax, r12d
0x1800206f7  shl     rax, 5
0x1800206fb  add     rax, [r15+8]
0x1800206ff  mov     rsi, [rax]
0x180020702  test    rsi, rsi
0x180020705  jnz     short loc_180020730
0x180020707  lea     rax, aDeserializedRe; "Deserialized Reporting Event doesn't co"...
0x18002070e  mov     [rsp+0C0h+var_98], rax
0x180020713  mov     [rsp+0C0h+var_A0], rsi
0x180020718  xor     edx, edx
0x18002071a  xor     ecx, ecx
0x18002071c  lea     r9d, [rsi+4]
0x180020720  mov     r8d, 1000000h
0x180020726  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18002072b  jmp     loc_180020839
0x180020730  lea     rcx, [rsi+0ECh]; Uuid
0x180020737  lea     rdx, [rbp+57h+StringUuid]; StringUuid
0x18002073b  call    cs:__imp_UuidToStringW
0x180020741  mov     edi, eax
0x180020743  cmp     eax, 1
0x180020746  jl      short loc_180020751
0x180020748  movzx   edi, ax
0x18002074b  or      edi, 80010000h
0x180020751  test    edi, edi
0x180020753  js      loc_18002088C
0x180020759  lea     rdi, [rbx+10h]
0x18002075d  mov     rcx, [rdi]; lpMem
0x180020760  test    rcx, rcx
0x180020763  jz      short loc_180020771
0x180020765  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18002076a  mov     qword ptr [rdi], 0
0x180020771  mov     rdx, rdi
0x180020774  mov     rcx, [rbp+57h+StringUuid]
0x180020778  call    ??$DuplicateString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x18002077d  mov     edi, eax
0x18002077f  test    eax, eax
0x180020781  js      loc_180020885
0x180020787  mov     eax, [rsi+0FCh]
0x18002078d  mov     [rbx+18h], eax
0x180020790  mov     eax, [rsi+60h]
0x180020793  mov     [rbx+5Ch], eax
0x180020796  mov     eax, [rsi+64h]
0x180020799  mov     [rbx+60h], eax
0x18002079c  mov     eax, [rbx+5Ch]
0x18002079f  sar     eax, 1Fh
0x1800207a2  and     eax, 2
0x1800207a5  add     eax, 6
0x1800207a8  mov     [rbx+58h], eax
0x1800207ab  cmp     dword ptr [rsi+60h], 242015h
0x1800207b2  jnz     short loc_1800207BB
0x1800207b4  mov     dword ptr [rbx+68h], 1
0x1800207bb  cmp     dword ptr [rsi+1DCh], 0
0x1800207c2  jz      short loc_180020839
0x1800207c4  test    r14, r14
0x1800207c7  jz      short loc_180020839
0x1800207c9  mov     eax, [rsi+28h]
0x1800207cc  mov     [r14+28h], eax
0x1800207d0  mov     edx, [rsi+60h]
0x1800207d3  cmp     dword ptr [rsi+98h], 0
0x1800207da  jz      short loc_1800207E8
0x1800207dc  mov     eax, [rsi+9Ch]
0x1800207e2  neg     eax
0x1800207e4  sbb     ecx, ecx
0x1800207e6  and     edx, ecx
0x1800207e8  mov     [r14+60h], edx
0x1800207ec  test    edx, edx
0x1800207ee  jns     short loc_180020839
0x1800207f0  lea     eax, [rdx+7FDBDFECh]
0x1800207f6  cmp     eax, 1
0x1800207f9  ja      short loc_180020806
0x1800207fb  mov     dword ptr [r14+1D8h], 1
0x180020806  mov     eax, [rsi+64h]
0x180020809  mov     [r14+64h], eax
0x18002080d  mov     rcx, r14; struct tagUpdateDeploymentReportingData *
0x180020810  call    ?FixReplacementStringsForFailure@@YAJPEAUtagUpdateDeploymentReportingData@@@Z; FixReplacementStringsForFailure(tagUpdateDeploymentReportingData *)
0x180020815  cmp     dword ptr [r14+98h], 0
0x18002081d  jz      short loc_18002082A
0x18002081f  mov     dword ptr [r14+9Ch], 1
0x18002082a  lea     rcx, [rbp+57h+var_80]; struct tagDeploymentReportingUpdateEvent *
0x18002082e  call    ?FixRepeatFailCountAndFirmwareStatus@@YAJPEAUtagDeploymentReportingUpdateEvent@@@Z; FixRepeatFailCountAndFirmwareStatus(tagDeploymentReportingUpdateEvent *)
0x180020833  mov     edi, eax
0x180020835  test    eax, eax
0x180020837  js      short loc_18002087E
0x180020839  mov     rcx, [rbp+57h+StringUuid]; void *
0x18002083d  test    rcx, rcx
0x180020840  jz      short loc_180020847
0x180020842  call    ?XPtrRpcStringFree@@YAXPEAX@Z; XPtrRpcStringFree(void *)
0x180020847  inc     r12d
0x18002084a  mov     eax, [r15+14h]
0x18002084e  cmp     r12d, eax
0x180020851  jb      loc_1800206E3
0x180020857  lea     rsi, [r15+18h]
0x18002085b  mov     r14, [rbp+57h+var_88]
0x18002085f  lea     r9, [r13+8]
0x180020863  mov     r8, r13
0x180020866  mov     rdx, r15
0x180020869  call    ?CloneReportingUpdateEventFromEventList@CDeploymentReportingUpdateGroup@@QEAAJAEBV?$CSusArrayList@UtagDeploymentReportingUpdateEvent@@VCSusArrayListItemOpDeploymentReportingUpdateEvent@@@@PEAKPEAPEAUtagDeploymentReportingUpdateEvent@@@Z; CDeploymentReportingUpdateGroup::CloneReportingUpdateEventFromEventList(CSusArrayList<tagDeploymentReportingUpdateEvent,CSusArrayListItemOpDeploymentReportingUpdateEvent> const &,ulong *,tagDeploymentReportingUpdateEvent * *)
0x18002086e  mov     edi, eax
0x180020870  test    eax, eax
0x180020872  jns     short loc_1800208C0
0x180020874  mov     edx, 6E8h
0x180020879  mov     r9d, eax
0x18002087c  jmp     short loc_1800208DE
0x18002087e  mov     edx, 510h
0x180020883  jmp     short loc_18002089D
0x180020885  mov     edx, 4C8h
0x18002088a  jmp     short loc_18002089D
0x18002088c  mov     edx, 4C6h
0x180020891  jmp     short loc_18002089D
0x180020893  mov     edi, 80240007h
0x180020898  mov     edx, 4BBh; void *
0x18002089d  mov     rcx, [rbp+5Fh]; this
0x1800208a1  mov     r9d, edi; char *
0x1800208a4  lea     r8, aCW1SSrcClientU_11; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x1800208ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800208b0  mov     rcx, [rbp+57h+StringUuid]; void *
0x1800208b4  test    rcx, rcx
0x1800208b7  jz      short loc_180020912
0x1800208b9  call    ?XPtrRpcStringFree@@YAXPEAX@Z; XPtrRpcStringFree(void *)
0x1800208be  jmp     short loc_180020912
0x1800208c0  lea     r9, [r13+18h]
0x1800208c4  lea     r8, [r13+10h]
0x1800208c8  mov     rdx, rsi
0x1800208cb  call    ?CloneReportingUpdateEventFromEventList@CDeploymentReportingUpdateGroup@@QEAAJAEBV?$CSusArrayList@UtagDeploymentReportingUpdateEvent@@VCSusArrayListItemOpDeploymentReportingUpdateEvent@@@@PEAKPEAPEAUtagDeploymentReportingUpdateEvent@@@Z; CDeploymentReportingUpdateGroup::CloneReportingUpdateEventFromEventList(CSusArrayList<tagDeploymentReportingUpdateEvent,CSusArrayListItemOpDeploymentReportingUpdateEvent> const &,ulong *,tagDeploymentReportingUpdateEvent * *)
0x1800208d0  mov     edi, eax
0x1800208d2  mov     r9d, eax; char *
0x1800208d5  test    eax, eax
0x1800208d7  jns     short loc_180020908
0x1800208d9  mov     edx, 6ECh; void *
0x1800208de  mov     rcx, [rbp+5Fh]; this
0x1800208e2  lea     r8, aCW1SSrcClientU_11; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x1800208e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800208ee  mov     rcx, [rbp+5Fh]; this
0x1800208f2  mov     r9d, edi; char *
0x1800208f5  lea     r8, aCW1SSrcClientU_11; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x1800208fc  mov     edx, 516h; void *
0x180020901  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020906  jmp     short loc_180020912
0x180020908  mov     rax, rbx
0x18002090b  xor     ebx, ebx
0x18002090d  mov     [r14], rax
0x180020910  xor     edi, edi
0x180020912  test    rbx, rbx
0x180020915  jz      short loc_180020927
0x180020917  mov     rcx, [rbx]
0x18002091a  mov     rax, [rcx+10h]
0x18002091e  mov     rcx, rbx
0x180020921  call    _guard_dispatch_icall
0x180020926  nop
0x180020927  mov     eax, edi
0x180020929  mov     rcx, [rbp+57h+var_38]
0x18002092d  xor     rcx, rsp; StackCookie
0x180020930  call    __security_check_cookie
0x180020935  mov     rbx, [rsp+0C0h+arg_18]
0x18002093d  add     rsp, 90h
0x180020944  pop     r15
0x180020946  pop     r14
0x180020948  pop     r13
0x18002094a  pop     r12
0x18002094c  pop     rdi
0x18002094d  pop     rsi
0x18002094e  pop     rbp
0x18002094f  retn
```
