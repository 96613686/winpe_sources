# CElevatedDataCollection::CollectDataForServerRequest(void *,void *,void *)

- ea: `0x14005cbac`
- end: `0x14005d00d`
- name: `?CollectDataForServerRequest@CElevatedDataCollection@@QEAAJPEAX00@Z`
- size: `1121`
- prototype: `__int64 __fastcall(CElevatedDataCollection *__hidden this, void *, HANDLE Process, void *)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140023210`
- `0x140026360`

## callees

- `0x140002490`
- `0x140014ee4`
- `0x140014f14`
- `0x140014f58`
- `0x14005afa4`
- `0x14005bf14`
- `0x14005c1b8`
- `0x14005c620`
- `0x14005cbac`
- `0x14005d014`
- `0x14005d808`
- `0x14005de78`
- `0x14005df70`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14005cbf2`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14005cbf2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14005cf44`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14005cf90`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14005cf44`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14005cf90`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14005cdb2`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14005cdb2`

## string_xrefs

- `0x14005ce47`: `ReserveMachineQueueDirectory failed: 0x%x`

## pseudocode

```c
__int64 __fastcall CElevatedDataCollection::CollectDataForServerRequest(
        const wchar_t **this,
        void *a2,
        HANDLE Process,
        const wchar_t *a4)
{
  void *v7; // r15
  DWORD ProcessId; // eax
  DWORD v9; // edi
  int v11; // eax
  unsigned int v12; // edi
  bool v13; // zf
  unsigned int v14; // r15d
  unsigned int i; // ecx
  int v16; // edx
  __int64 v17; // rax
  unsigned int j; // ecx
  int v19; // edx
  __int64 v20; // rax
  HRESULT v21; // eax
  int v22; // eax
  CUserModeHangReport *v23; // rcx
  __int64 v24; // rdx
  int v25; // eax
  unsigned int k; // ebp
  int v27; // eax
  int v28; // eax
  const wchar_t *v29; // rdx
  int v30; // eax
  _OWORD v32[2]; // [rsp+38h] [rbp-70h] BYREF
  int v33; // [rsp+58h] [rbp-50h]

  v33 = 0;
  memset(v32, 0, sizeof(v32));
  v7 = a2;
  ProcessId = GetProcessId(Process);
  v9 = ProcessId;
  if ( !v7 )
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, WPP_b503122a8e753e2116c8130bd5de03da_Traceguids);
    }
    return 2147942487LL;
  }
  if ( *((_DWORD *)this + 118) == 13 )
  {
    v11 = CElevatedDataCollection::AddCrossProcessPid(
            (CElevatedDataCollection *)this,
            ProcessId,
            0,
            0x4000001Fu,
            0,
            ProcessId);
    if ( v11 < 0
      && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        71,
        WPP_b503122a8e753e2116c8130bd5de03da_Traceguids,
        (unsigned int)v11);
    }
  }
  CElevatedDataCollection::FinalizePendingReflectionDumps((CElevatedDataCollection *)this);
  if ( this[2] == this[3]
    && this[6] == this[7]
    && this[10] == this[11]
    && this[14] == this[15]
    && this[18] == this[19]
    && this[22] == this[23]
    && !*((_DWORD *)this + 54)
    && !*((_DWORD *)this + 86)
    && !*((_DWORD *)this + 179) )
  {
    v12 = 0;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, WPP_b503122a8e753e2116c8130bd5de03da_Traceguids);
    }
    goto LABEL_68;
  }
  v13 = *((_DWORD *)this + 118) == 13;
  v14 = 1;
  *this = (const wchar_t *)a2;
  this[1] = a4;
  if ( !v13 )
    LODWORD(v32[0]) = v9;
  for ( i = 0; i < 4; ++i )
  {
    if ( v14 >= 9 )
      break;
    v16 = (int)this[4 * i + 27];
    if ( v16 )
    {
      v17 = v14++;
      *((_DWORD *)v32 + v17) = v16;
    }
  }
  for ( j = 0; j < 4; ++j )
  {
    if ( v14 >= 9 )
      break;
    v19 = (int)this[4 * j + 43];
    if ( v19 )
    {
      v20 = v14++;
      *((_DWORD *)v32 + v20) = v19;
    }
  }
  v21 = CoInitializeEx(0, 0);
  v12 = v21;
  if ( v21 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        73,
        WPP_b503122a8e753e2116c8130bd5de03da_Traceguids,
        (unsigned int)v21);
    }
    goto LABEL_67;
  }
  if ( *((_DWORD *)this + 179)
    || *((_DWORD *)this + 86)
    || this[22] != this[23]
    || this[18] != this[19]
    || this[14] != this[15] )
  {
    v22 = CElevatedDataCollection::ReserveMachineQueueDirectory((CElevatedDataCollection *)this, (void *)*this);
    v12 = v22;
    if ( v22 < 0 )
    {
      CElevatedDataCollection::LogDataCollectionStatus(
        (CElevatedDataCollection *)this,
        L"ReserveMachineQueueDirectory failed: 0x%x",
        (unsigned int)v22);
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_66;
      }
      v24 = 74;
      goto LABEL_48;
    }
  }
  if ( !*((_DWORD *)this + 179)
    || (v25 = CElevatedDataCollection::CollectKernelDump(this, Process, *((unsigned int *)this + 181)),
        v12 = v25,
        v25 >= 0) )
  {
    for ( k = 0; k < 6; ++k )
    {
      v27 = CElevatedDataCollection::CollectCrossProcessModuleDumps(this, v32, v14, k);
      v12 = v27;
      if ( v27 < 0 )
      {
        CElevatedDataCollection::LogDataCollectionStatus(
          (CElevatedDataCollection *)this,
          L"CollectCrossProcessModuleDumps failed: 0x%x",
          (unsigned int)v27);
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, WPP_b503122a8e753e2116c8130bd5de03da_Traceguids);
        }
        goto LABEL_66;
      }
    }
    if ( !*((_DWORD *)this + 118)
      || (v28 = CElevatedDataCollection::CollectCrossProcessDumps((CElevatedDataCollection *)this), v12 = v28, v28 >= 0) )
    {
      CoUninitialize();
      v12 = 0;
      goto LABEL_67;
    }
    CElevatedDataCollection::LogDataCollectionStatus(
      (CElevatedDataCollection *)this,
      L"CollectCrossProcessDumps failed: 0x%x",
      (unsigned int)v28);
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v24 = 77;
      goto LABEL_48;
    }
    goto LABEL_66;
  }
  CElevatedDataCollection::LogDataCollectionStatus(
    (CElevatedDataCollection *)this,
    L"KernelDump failed: 0x%x",
    (unsigned int)v25);
  v23 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v24 = 75;
LABEL_48:
    WPP_SF_d(*((_QWORD *)v23 + 2), v24, WPP_b503122a8e753e2116c8130bd5de03da_Traceguids, v12);
  }
LABEL_66:
  CoUninitialize();
LABEL_67:
  v7 = a2;
LABEL_68:
  v29 = this[100];
  if ( v29 != this[101] )
  {
    v30 = AddStringBufferToReport(v7, v29, L"ElevatedDataCollectionStatus.txt", 0);
    if ( v30 < 0
      && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        78,
        WPP_b503122a8e753e2116c8130bd5de03da_Traceguids,
        (unsigned int)v30);
    }
  }
  return v12;
}

```

## disassembly

```asm
0x14005cbac  push    rbx
0x14005cbae  push    rbp
0x14005cbaf  push    rdi
0x14005cbb0  push    r12
0x14005cbb2  push    r13
0x14005cbb4  push    r14
0x14005cbb6  push    r15
0x14005cbb8  sub     rsp, 70h
0x14005cbbc  mov     rax, cs:__security_cookie
0x14005cbc3  xor     rax, rsp
0x14005cbc6  mov     [rsp+0A8h+var_48], rax
0x14005cbcb  xorps   xmm0, xmm0
0x14005cbce  mov     [rsp+0A8h+var_78], rdx
0x14005cbd3  mov     rbx, rcx
0x14005cbd6  xor     eax, eax
0x14005cbd8  mov     rcx, r8; Process
0x14005cbdb  mov     [rsp+0A8h+var_50], eax
0x14005cbdf  movups  [rsp+0A8h+var_70], xmm0
0x14005cbe4  mov     rbp, r9
0x14005cbe7  mov     r13, r8
0x14005cbea  movups  [rsp+0A8h+var_60], xmm0
0x14005cbef  mov     r15, rdx
0x14005cbf2  call    cs:__imp_GetProcessId
0x14005cbf9  nop     dword ptr [rax+rax+00h]
0x14005cbfe  mov     edi, eax
0x14005cc00  test    r15, r15
0x14005cc03  jnz     short loc_14005CC3C
0x14005cc05  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cc0c  lea     r14, WPP_GLOBAL_Control
0x14005cc13  cmp     rcx, r14
0x14005cc16  jz      short loc_14005CC32
0x14005cc18  test    byte ptr [rcx+1Ch], 1
0x14005cc1c  jz      short loc_14005CC32
0x14005cc1e  mov     rcx, [rcx+10h]
0x14005cc22  lea     edx, [r15+46h]
0x14005cc26  lea     r8, WPP_b503122a8e753e2116c8130bd5de03da_Traceguids
0x14005cc2d  call    WPP_SF_
0x14005cc32  mov     eax, 80070057h
0x14005cc37  jmp     loc_14005CFEF
0x14005cc3c  cmp     dword ptr [rbx+1D8h], 0Dh
0x14005cc43  lea     r12, WPP_b503122a8e753e2116c8130bd5de03da_Traceguids
0x14005cc4a  lea     r14, WPP_GLOBAL_Control
0x14005cc51  jnz     short loc_14005CC9D
0x14005cc53  mov     [rsp+0A8h+var_80], edi; unsigned int
0x14005cc57  mov     r9d, 4000001Fh; unsigned int
0x14005cc5d  xor     r8d, r8d; unsigned int
0x14005cc60  mov     [rsp+0A8h+var_88], 0; wchar_t *
0x14005cc69  mov     edx, edi; dwProcessId
0x14005cc6b  mov     rcx, rbx; this
0x14005cc6e  call    ?AddCrossProcessPid@CElevatedDataCollection@@QEAAJKKKPEB_WK@Z; CElevatedDataCollection::AddCrossProcessPid(ulong,ulong,ulong,wchar_t const *,ulong)
0x14005cc73  test    eax, eax
0x14005cc75  jns     short loc_14005CC9D
0x14005cc77  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cc7e  cmp     rcx, r14
0x14005cc81  jz      short loc_14005CC9D
0x14005cc83  test    byte ptr [rcx+1Ch], 2
0x14005cc87  jz      short loc_14005CC9D
0x14005cc89  mov     rcx, [rcx+10h]
0x14005cc8d  mov     edx, 47h ; 'G'
0x14005cc92  mov     r9d, eax
0x14005cc95  mov     r8, r12
0x14005cc98  call    WPP_SF_d
0x14005cc9d  mov     rcx, rbx; this
0x14005cca0  call    ?FinalizePendingReflectionDumps@CElevatedDataCollection@@IEAAXXZ; CElevatedDataCollection::FinalizePendingReflectionDumps(void)
0x14005cca5  mov     rax, [rbx+18h]
0x14005cca9  cmp     [rbx+10h], rax
0x14005ccad  jnz     loc_14005CD3B
0x14005ccb3  mov     rax, [rbx+38h]
0x14005ccb7  cmp     [rbx+30h], rax
0x14005ccbb  jnz     short loc_14005CD3B
0x14005ccbd  mov     rax, [rbx+58h]
0x14005ccc1  cmp     [rbx+50h], rax
0x14005ccc5  jnz     short loc_14005CD3B
0x14005ccc7  mov     rax, [rbx+78h]
0x14005cccb  cmp     [rbx+70h], rax
0x14005cccf  jnz     short loc_14005CD3B
0x14005ccd1  mov     rax, [rbx+98h]
0x14005ccd8  cmp     [rbx+90h], rax
0x14005ccdf  jnz     short loc_14005CD3B
0x14005cce1  mov     rax, [rbx+0B8h]
0x14005cce8  cmp     [rbx+0B0h], rax
0x14005ccef  jnz     short loc_14005CD3B
0x14005ccf1  xor     eax, eax
0x14005ccf3  cmp     [rbx+0D8h], eax
0x14005ccf9  jnz     short loc_14005CD3B
0x14005ccfb  cmp     [rbx+158h], eax
0x14005cd01  jnz     short loc_14005CD3B
0x14005cd03  cmp     [rbx+2CCh], eax
0x14005cd09  jnz     short loc_14005CD3B
0x14005cd0b  xor     edi, edi
0x14005cd0d  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cd14  cmp     rcx, r14
0x14005cd17  jz      loc_14005CFA1
0x14005cd1d  test    byte ptr [rcx+1Ch], 4
0x14005cd21  jz      loc_14005CFA1
0x14005cd27  mov     rcx, [rcx+10h]
0x14005cd2b  lea     edx, [rax+48h]
0x14005cd2e  mov     r8, r12
0x14005cd31  call    WPP_SF_
0x14005cd36  jmp     loc_14005CFA1
0x14005cd3b  cmp     dword ptr [rbx+1D8h], 0Dh
0x14005cd42  mov     r15d, 1
0x14005cd48  mov     rax, [rsp+0A8h+var_78]
0x14005cd4d  mov     [rbx], rax
0x14005cd50  mov     [rbx+8], rbp
0x14005cd54  jz      short loc_14005CD5A
0x14005cd56  mov     dword ptr [rsp+0A8h+var_70], edi
0x14005cd5a  xor     ecx, ecx
0x14005cd5c  cmp     r15d, 9
0x14005cd60  jnb     short loc_14005CD84
0x14005cd62  mov     eax, ecx
0x14005cd64  shl     rax, 5
0x14005cd68  mov     edx, [rax+rbx+0D8h]
0x14005cd6f  test    edx, edx
0x14005cd71  jz      short loc_14005CD7D
0x14005cd73  mov     eax, r15d
0x14005cd76  inc     r15d
0x14005cd79  mov     dword ptr [rsp+rax*4+0A8h+var_70], edx
0x14005cd7d  inc     ecx
0x14005cd7f  cmp     ecx, 4
0x14005cd82  jb      short loc_14005CD5C
0x14005cd84  xor     ecx, ecx
0x14005cd86  cmp     r15d, 9
0x14005cd8a  jnb     short loc_14005CDAE
0x14005cd8c  mov     eax, ecx
0x14005cd8e  shl     rax, 5
0x14005cd92  mov     edx, [rax+rbx+158h]
0x14005cd99  test    edx, edx
0x14005cd9b  jz      short loc_14005CDA7
0x14005cd9d  mov     eax, r15d
0x14005cda0  inc     r15d
0x14005cda3  mov     dword ptr [rsp+rax*4+0A8h+var_70], edx
0x14005cda7  inc     ecx
0x14005cda9  cmp     ecx, 4
0x14005cdac  jb      short loc_14005CD86
0x14005cdae  xor     edx, edx; dwCoInit
0x14005cdb0  xor     ecx, ecx; pvReserved
0x14005cdb2  call    cs:__imp_CoInitializeEx
0x14005cdb9  nop     dword ptr [rax+rax+00h]
0x14005cdbe  mov     edi, eax
0x14005cdc0  test    eax, eax
0x14005cdc2  jns     short loc_14005CDF7
0x14005cdc4  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cdcb  cmp     rcx, r14
0x14005cdce  jz      loc_14005CF9C
0x14005cdd4  test    byte ptr [rcx+1Ch], 1
0x14005cdd8  jz      loc_14005CF9C
0x14005cdde  mov     rcx, [rcx+10h]
0x14005cde2  mov     edx, 49h ; 'I'
0x14005cde7  mov     r9d, eax
0x14005cdea  mov     r8, r12
0x14005cded  call    WPP_SF_d
0x14005cdf2  jmp     loc_14005CF9C
0x14005cdf7  cmp     dword ptr [rbx+2CCh], 0
0x14005cdfe  jnz     short loc_14005CE33
0x14005ce00  cmp     dword ptr [rbx+158h], 0
0x14005ce07  jnz     short loc_14005CE33
0x14005ce09  mov     rax, [rbx+0B8h]
0x14005ce10  cmp     [rbx+0B0h], rax
0x14005ce17  jnz     short loc_14005CE33
0x14005ce19  mov     rax, [rbx+98h]
0x14005ce20  cmp     [rbx+90h], rax
0x14005ce27  jnz     short loc_14005CE33
0x14005ce29  mov     rax, [rbx+78h]
0x14005ce2d  cmp     [rbx+70h], rax
0x14005ce31  jz      short loc_14005CE89
0x14005ce33  mov     rdx, [rbx]; void *
0x14005ce36  mov     rcx, rbx; this
0x14005ce39  call    ?ReserveMachineQueueDirectory@CElevatedDataCollection@@IEAAJPEAX@Z; CElevatedDataCollection::ReserveMachineQueueDirectory(void *)
0x14005ce3e  mov     edi, eax
0x14005ce40  test    eax, eax
0x14005ce42  jns     short loc_14005CE89
0x14005ce44  mov     r8d, eax
0x14005ce47  lea     rdx, aReservemachine; "ReserveMachineQueueDirectory failed: 0x"...
0x14005ce4e  mov     rcx, rbx; this
0x14005ce51  call    ?LogDataCollectionStatus@CElevatedDataCollection@@IEAAJPEB_WZZ; CElevatedDataCollection::LogDataCollectionStatus(wchar_t const *,...)
0x14005ce56  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ce5d  cmp     rcx, r14
0x14005ce60  jz      loc_14005CF90
0x14005ce66  test    byte ptr [rcx+1Ch], 1
0x14005ce6a  jz      loc_14005CF90
0x14005ce70  mov     edx, 4Ah ; 'J'
0x14005ce75  mov     rcx, [rcx+10h]
0x14005ce79  mov     r9d, edi
0x14005ce7c  mov     r8, r12
0x14005ce7f  call    WPP_SF_d
0x14005ce84  jmp     loc_14005CF90
0x14005ce89  cmp     dword ptr [rbx+2CCh], 0
0x14005ce90  jz      short loc_14005CEDD
0x14005ce92  mov     r8d, [rbx+2D4h]
0x14005ce99  mov     rdx, r13
0x14005ce9c  mov     rcx, rbx
0x14005ce9f  call    ?CollectKernelDump@CElevatedDataCollection@@IEAAJPEAXW4FAULTREP_LIVEKERNEL_DUMPTYPE@@@Z; CElevatedDataCollection::CollectKernelDump(void *,FAULTREP_LIVEKERNEL_DUMPTYPE)
0x14005cea4  mov     edi, eax
0x14005cea6  test    eax, eax
0x14005cea8  jns     short loc_14005CEDD
0x14005ceaa  mov     r8d, eax
0x14005cead  lea     rdx, aKerneldumpFail; "KernelDump failed: 0x%x"
0x14005ceb4  mov     rcx, rbx; this
0x14005ceb7  call    ?LogDataCollectionStatus@CElevatedDataCollection@@IEAAJPEB_WZZ; CElevatedDataCollection::LogDataCollectionStatus(wchar_t const *,...)
0x14005cebc  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cec3  cmp     rcx, r14
0x14005cec6  jz      loc_14005CF90
0x14005cecc  test    byte ptr [rcx+1Ch], 1
0x14005ced0  jz      loc_14005CF90
0x14005ced6  mov     edx, 4Bh ; 'K'
0x14005cedb  jmp     short loc_14005CE75
0x14005cedd  xor     ebp, ebp
0x14005cedf  mov     r9d, ebp
0x14005cee2  lea     rdx, [rsp+0A8h+var_70]
0x14005cee7  mov     r8d, r15d
0x14005ceea  mov     rcx, rbx
0x14005ceed  call    ?CollectCrossProcessModuleDumps@CElevatedDataCollection@@IEAAJPEAKKW4FAULTREP_CROSSPROCESS_DUMPTYPE@@@Z; CElevatedDataCollection::CollectCrossProcessModuleDumps(ulong *,ulong,FAULTREP_CROSSPROCESS_DUMPTYPE)
0x14005cef2  mov     edi, eax
0x14005cef4  test    eax, eax
0x14005cef6  js      short loc_14005CF54
0x14005cef8  inc     ebp
0x14005cefa  cmp     ebp, 6
0x14005cefd  jb      short loc_14005CEDF
0x14005ceff  cmp     dword ptr [rbx+1D8h], 0
0x14005cf06  jz      short loc_14005CF44
0x14005cf08  mov     rcx, rbx; this
0x14005cf0b  call    ?CollectCrossProcessDumps@CElevatedDataCollection@@IEAAJXZ; CElevatedDataCollection::CollectCrossProcessDumps(void)
0x14005cf10  mov     edi, eax
0x14005cf12  test    eax, eax
0x14005cf14  jns     short loc_14005CF44
0x14005cf16  mov     r8d, eax
0x14005cf19  lea     rdx, aCollectcrosspr; "CollectCrossProcessDumps failed: 0x%x"
0x14005cf20  mov     rcx, rbx; this
0x14005cf23  call    ?LogDataCollectionStatus@CElevatedDataCollection@@IEAAJPEB_WZZ; CElevatedDataCollection::LogDataCollectionStatus(wchar_t const *,...)
0x14005cf28  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cf2f  cmp     rcx, r14
0x14005cf32  jz      short loc_14005CF90
0x14005cf34  test    byte ptr [rcx+1Ch], 1
0x14005cf38  jz      short loc_14005CF90
0x14005cf3a  mov     edx, 4Dh ; 'M'
0x14005cf3f  jmp     loc_14005CE75
0x14005cf44  call    cs:__imp_CoUninitialize
0x14005cf4b  nop     dword ptr [rax+rax+00h]
0x14005cf50  xor     edi, edi
0x14005cf52  jmp     short loc_14005CF9C
0x14005cf54  mov     r8d, edi
0x14005cf57  lea     rdx, aCollectcrosspr_0; "CollectCrossProcessModuleDumps failed: "...
0x14005cf5e  mov     rcx, rbx; this
0x14005cf61  call    ?LogDataCollectionStatus@CElevatedDataCollection@@IEAAJPEB_WZZ; CElevatedDataCollection::LogDataCollectionStatus(wchar_t const *,...)
0x14005cf66  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cf6d  cmp     rcx, r14
0x14005cf70  jz      short loc_14005CF90
0x14005cf72  test    byte ptr [rcx+1Ch], 1
0x14005cf76  jz      short loc_14005CF90
0x14005cf78  mov     rcx, [rcx+10h]
0x14005cf7c  mov     edx, 4Ch ; 'L'
0x14005cf81  mov     r9d, ebp
0x14005cf84  mov     dword ptr [rsp+0A8h+var_88], edi
0x14005cf88  mov     r8, r12
0x14005cf8b  call    WPP_SF_Dd
0x14005cf90  call    cs:__imp_CoUninitialize
0x14005cf97  nop     dword ptr [rax+rax+00h]
0x14005cf9c  mov     r15, [rsp+0A8h+var_78]
0x14005cfa1  mov     rdx, [rbx+320h]; wchar_t *
0x14005cfa8  cmp     rdx, [rbx+328h]
0x14005cfaf  jz      short loc_14005CFED
0x14005cfb1  xor     r9d, r9d; wchar_t *
0x14005cfb4  lea     r8, aElevateddataco; "ElevatedDataCollectionStatus.txt"
0x14005cfbb  mov     rcx, r15; void *
0x14005cfbe  call    ?AddStringBufferToReport@@YAJPEAXPEB_W11@Z; AddStringBufferToReport(void *,wchar_t const *,wchar_t const *,wchar_t const *)
0x14005cfc3  test    eax, eax
0x14005cfc5  jns     short loc_14005CFED
0x14005cfc7  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cfce  cmp     rcx, r14
0x14005cfd1  jz      short loc_14005CFED
0x14005cfd3  test    byte ptr [rcx+1Ch], 1
0x14005cfd7  jz      short loc_14005CFED
0x14005cfd9  mov     rcx, [rcx+10h]
0x14005cfdd  mov     edx, 4Eh ; 'N'
0x14005cfe2  mov     r9d, eax
0x14005cfe5  mov     r8, r12
0x14005cfe8  call    WPP_SF_d
0x14005cfed  mov     eax, edi
0x14005cfef  mov     rcx, [rsp+0A8h+var_48]
0x14005cff4  xor     rcx, rsp; StackCookie
0x14005cff7  call    __security_check_cookie
0x14005cffc  add     rsp, 70h
0x14005d000  pop     r15
0x14005d002  pop     r14
0x14005d004  pop     r13
0x14005d006  pop     r12
0x14005d008  pop     rdi
0x14005d009  pop     rbp
0x14005d00a  pop     rbx
0x14005d00b  retn
```
