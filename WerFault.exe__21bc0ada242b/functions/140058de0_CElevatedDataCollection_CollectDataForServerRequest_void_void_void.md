# CElevatedDataCollection::CollectDataForServerRequest(void *,void *,void *)

- ea: `0x140058de0`
- end: `0x140059228`
- name: `?CollectDataForServerRequest@CElevatedDataCollection@@QEAAJPEAX00@Z`
- size: `1096`
- prototype: `__int64 __fastcall(const wchar_t **this, void *, HANDLE Process, const wchar_t *)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140021bc0`
- `0x140024af0`

## callees

- `0x140002470`
- `0x14001444c`
- `0x140014474`
- `0x1400144b4`
- `0x140057238`
- `0x140058160`
- `0x1400583f8`
- `0x140058860`
- `0x140058de0`
- `0x140059230`
- `0x140059a10`
- `0x14005a074`
- `0x14005a16c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x140058e26`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x140058e26`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14005916c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400591b2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14005916c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400591b2`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140058fe0`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140058fe0`

## string_xrefs

- `0x14005906f`: `ReserveMachineQueueDirectory failed: 0x%x`

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
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, WPP_b503122a8e753e2116c8130bd5de03da_Traceguids, k, v12);
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
0x140058de0  push    rbx
0x140058de2  push    rbp
0x140058de3  push    rdi
0x140058de4  push    r12
0x140058de6  push    r13
0x140058de8  push    r14
0x140058dea  push    r15
0x140058dec  sub     rsp, 70h
0x140058df0  mov     rax, cs:__security_cookie
0x140058df7  xor     rax, rsp
0x140058dfa  mov     [rsp+0A8h+var_48], rax
0x140058dff  xorps   xmm0, xmm0
0x140058e02  mov     [rsp+0A8h+var_78], rdx
0x140058e07  mov     rbx, rcx
0x140058e0a  xor     eax, eax
0x140058e0c  mov     rcx, r8; Process
0x140058e0f  mov     [rsp+0A8h+var_50], eax
0x140058e13  movups  [rsp+0A8h+var_70], xmm0
0x140058e18  mov     rbp, r9
0x140058e1b  mov     r13, r8
0x140058e1e  movups  [rsp+0A8h+var_60], xmm0
0x140058e23  mov     r15, rdx
0x140058e26  call    cs:__imp_GetProcessId
0x140058e2c  mov     edi, eax
0x140058e2e  test    r15, r15
0x140058e31  jnz     short loc_140058E6A
0x140058e33  mov     rcx, cs:WPP_GLOBAL_Control
0x140058e3a  lea     r14, WPP_GLOBAL_Control
0x140058e41  cmp     rcx, r14
0x140058e44  jz      short loc_140058E60
0x140058e46  test    byte ptr [rcx+1Ch], 1
0x140058e4a  jz      short loc_140058E60
0x140058e4c  mov     rcx, [rcx+10h]
0x140058e50  lea     edx, [r15+46h]
0x140058e54  lea     r8, WPP_b503122a8e753e2116c8130bd5de03da_Traceguids
0x140058e5b  call    WPP_SF_
0x140058e60  mov     eax, 80070057h
0x140058e65  jmp     loc_14005920B
0x140058e6a  cmp     dword ptr [rbx+1D8h], 0Dh
0x140058e71  lea     r12, WPP_b503122a8e753e2116c8130bd5de03da_Traceguids
0x140058e78  lea     r14, WPP_GLOBAL_Control
0x140058e7f  jnz     short loc_140058ECB
0x140058e81  mov     [rsp+0A8h+var_80], edi; unsigned int
0x140058e85  mov     r9d, 4000001Fh; unsigned int
0x140058e8b  xor     r8d, r8d; unsigned int
0x140058e8e  mov     [rsp+0A8h+var_88], 0; wchar_t *
0x140058e97  mov     edx, edi; dwProcessId
0x140058e99  mov     rcx, rbx; this
0x140058e9c  call    ?AddCrossProcessPid@CElevatedDataCollection@@QEAAJKKKPEB_WK@Z; CElevatedDataCollection::AddCrossProcessPid(ulong,ulong,ulong,wchar_t const *,ulong)
0x140058ea1  test    eax, eax
0x140058ea3  jns     short loc_140058ECB
0x140058ea5  mov     rcx, cs:WPP_GLOBAL_Control
0x140058eac  cmp     rcx, r14
0x140058eaf  jz      short loc_140058ECB
0x140058eb1  test    byte ptr [rcx+1Ch], 2
0x140058eb5  jz      short loc_140058ECB
0x140058eb7  mov     rcx, [rcx+10h]
0x140058ebb  mov     edx, 47h ; 'G'
0x140058ec0  mov     r9d, eax
0x140058ec3  mov     r8, r12
0x140058ec6  call    WPP_SF_d
0x140058ecb  mov     rcx, rbx; this
0x140058ece  call    ?FinalizePendingReflectionDumps@CElevatedDataCollection@@IEAAXXZ; CElevatedDataCollection::FinalizePendingReflectionDumps(void)
0x140058ed3  mov     rax, [rbx+18h]
0x140058ed7  cmp     [rbx+10h], rax
0x140058edb  jnz     loc_140058F69
0x140058ee1  mov     rax, [rbx+38h]
0x140058ee5  cmp     [rbx+30h], rax
0x140058ee9  jnz     short loc_140058F69
0x140058eeb  mov     rax, [rbx+58h]
0x140058eef  cmp     [rbx+50h], rax
0x140058ef3  jnz     short loc_140058F69
0x140058ef5  mov     rax, [rbx+78h]
0x140058ef9  cmp     [rbx+70h], rax
0x140058efd  jnz     short loc_140058F69
0x140058eff  mov     rax, [rbx+98h]
0x140058f06  cmp     [rbx+90h], rax
0x140058f0d  jnz     short loc_140058F69
0x140058f0f  mov     rax, [rbx+0B8h]
0x140058f16  cmp     [rbx+0B0h], rax
0x140058f1d  jnz     short loc_140058F69
0x140058f1f  xor     eax, eax
0x140058f21  cmp     [rbx+0D8h], eax
0x140058f27  jnz     short loc_140058F69
0x140058f29  cmp     [rbx+158h], eax
0x140058f2f  jnz     short loc_140058F69
0x140058f31  cmp     [rbx+2CCh], eax
0x140058f37  jnz     short loc_140058F69
0x140058f39  xor     edi, edi
0x140058f3b  mov     rcx, cs:WPP_GLOBAL_Control
0x140058f42  cmp     rcx, r14
0x140058f45  jz      loc_1400591BD
0x140058f4b  test    byte ptr [rcx+1Ch], 4
0x140058f4f  jz      loc_1400591BD
0x140058f55  mov     rcx, [rcx+10h]
0x140058f59  lea     edx, [rax+48h]
0x140058f5c  mov     r8, r12
0x140058f5f  call    WPP_SF_
0x140058f64  jmp     loc_1400591BD
0x140058f69  cmp     dword ptr [rbx+1D8h], 0Dh
0x140058f70  mov     r15d, 1
0x140058f76  mov     rax, [rsp+0A8h+var_78]
0x140058f7b  mov     [rbx], rax
0x140058f7e  mov     [rbx+8], rbp
0x140058f82  jz      short loc_140058F88
0x140058f84  mov     dword ptr [rsp+0A8h+var_70], edi
0x140058f88  xor     ecx, ecx
0x140058f8a  cmp     r15d, 9
0x140058f8e  jnb     short loc_140058FB2
0x140058f90  mov     eax, ecx
0x140058f92  shl     rax, 5
0x140058f96  mov     edx, [rax+rbx+0D8h]
0x140058f9d  test    edx, edx
0x140058f9f  jz      short loc_140058FAB
0x140058fa1  mov     eax, r15d
0x140058fa4  inc     r15d
0x140058fa7  mov     dword ptr [rsp+rax*4+0A8h+var_70], edx
0x140058fab  inc     ecx
0x140058fad  cmp     ecx, 4
0x140058fb0  jb      short loc_140058F8A
0x140058fb2  xor     ecx, ecx
0x140058fb4  cmp     r15d, 9
0x140058fb8  jnb     short loc_140058FDC
0x140058fba  mov     eax, ecx
0x140058fbc  shl     rax, 5
0x140058fc0  mov     edx, [rax+rbx+158h]
0x140058fc7  test    edx, edx
0x140058fc9  jz      short loc_140058FD5
0x140058fcb  mov     eax, r15d
0x140058fce  inc     r15d
0x140058fd1  mov     dword ptr [rsp+rax*4+0A8h+var_70], edx
0x140058fd5  inc     ecx
0x140058fd7  cmp     ecx, 4
0x140058fda  jb      short loc_140058FB4
0x140058fdc  xor     edx, edx; dwCoInit
0x140058fde  xor     ecx, ecx; pvReserved
0x140058fe0  call    cs:__imp_CoInitializeEx
0x140058fe6  mov     edi, eax
0x140058fe8  test    eax, eax
0x140058fea  jns     short loc_14005901F
0x140058fec  mov     rcx, cs:WPP_GLOBAL_Control
0x140058ff3  cmp     rcx, r14
0x140058ff6  jz      loc_1400591B8
0x140058ffc  test    byte ptr [rcx+1Ch], 1
0x140059000  jz      loc_1400591B8
0x140059006  mov     rcx, [rcx+10h]
0x14005900a  mov     edx, 49h ; 'I'
0x14005900f  mov     r9d, eax
0x140059012  mov     r8, r12
0x140059015  call    WPP_SF_d
0x14005901a  jmp     loc_1400591B8
0x14005901f  cmp     dword ptr [rbx+2CCh], 0
0x140059026  jnz     short loc_14005905B
0x140059028  cmp     dword ptr [rbx+158h], 0
0x14005902f  jnz     short loc_14005905B
0x140059031  mov     rax, [rbx+0B8h]
0x140059038  cmp     [rbx+0B0h], rax
0x14005903f  jnz     short loc_14005905B
0x140059041  mov     rax, [rbx+98h]
0x140059048  cmp     [rbx+90h], rax
0x14005904f  jnz     short loc_14005905B
0x140059051  mov     rax, [rbx+78h]
0x140059055  cmp     [rbx+70h], rax
0x140059059  jz      short loc_1400590B1
0x14005905b  mov     rdx, [rbx]; void *
0x14005905e  mov     rcx, rbx; this
0x140059061  call    ?ReserveMachineQueueDirectory@CElevatedDataCollection@@IEAAJPEAX@Z; CElevatedDataCollection::ReserveMachineQueueDirectory(void *)
0x140059066  mov     edi, eax
0x140059068  test    eax, eax
0x14005906a  jns     short loc_1400590B1
0x14005906c  mov     r8d, eax
0x14005906f  lea     rdx, aReservemachine; "ReserveMachineQueueDirectory failed: 0x"...
0x140059076  mov     rcx, rbx; this
0x140059079  call    ?LogDataCollectionStatus@CElevatedDataCollection@@IEAAJPEB_WZZ; CElevatedDataCollection::LogDataCollectionStatus(wchar_t const *,...)
0x14005907e  mov     rcx, cs:WPP_GLOBAL_Control
0x140059085  cmp     rcx, r14
0x140059088  jz      loc_1400591B2
0x14005908e  test    byte ptr [rcx+1Ch], 1
0x140059092  jz      loc_1400591B2
0x140059098  mov     edx, 4Ah ; 'J'
0x14005909d  mov     rcx, [rcx+10h]
0x1400590a1  mov     r9d, edi
0x1400590a4  mov     r8, r12
0x1400590a7  call    WPP_SF_d
0x1400590ac  jmp     loc_1400591B2
0x1400590b1  cmp     dword ptr [rbx+2CCh], 0
0x1400590b8  jz      short loc_140059105
0x1400590ba  mov     r8d, [rbx+2D4h]
0x1400590c1  mov     rdx, r13
0x1400590c4  mov     rcx, rbx
0x1400590c7  call    ?CollectKernelDump@CElevatedDataCollection@@IEAAJPEAXW4FAULTREP_LIVEKERNEL_DUMPTYPE@@@Z; CElevatedDataCollection::CollectKernelDump(void *,FAULTREP_LIVEKERNEL_DUMPTYPE)
0x1400590cc  mov     edi, eax
0x1400590ce  test    eax, eax
0x1400590d0  jns     short loc_140059105
0x1400590d2  mov     r8d, eax
0x1400590d5  lea     rdx, aKerneldumpFail; "KernelDump failed: 0x%x"
0x1400590dc  mov     rcx, rbx; this
0x1400590df  call    ?LogDataCollectionStatus@CElevatedDataCollection@@IEAAJPEB_WZZ; CElevatedDataCollection::LogDataCollectionStatus(wchar_t const *,...)
0x1400590e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400590eb  cmp     rcx, r14
0x1400590ee  jz      loc_1400591B2
0x1400590f4  test    byte ptr [rcx+1Ch], 1
0x1400590f8  jz      loc_1400591B2
0x1400590fe  mov     edx, 4Bh ; 'K'
0x140059103  jmp     short loc_14005909D
0x140059105  xor     ebp, ebp
0x140059107  mov     r9d, ebp
0x14005910a  lea     rdx, [rsp+0A8h+var_70]
0x14005910f  mov     r8d, r15d
0x140059112  mov     rcx, rbx
0x140059115  call    ?CollectCrossProcessModuleDumps@CElevatedDataCollection@@IEAAJPEAKKW4FAULTREP_CROSSPROCESS_DUMPTYPE@@@Z; CElevatedDataCollection::CollectCrossProcessModuleDumps(ulong *,ulong,FAULTREP_CROSSPROCESS_DUMPTYPE)
0x14005911a  mov     edi, eax
0x14005911c  test    eax, eax
0x14005911e  js      short loc_140059176
0x140059120  inc     ebp
0x140059122  cmp     ebp, 6
0x140059125  jb      short loc_140059107
0x140059127  cmp     dword ptr [rbx+1D8h], 0
0x14005912e  jz      short loc_14005916C
0x140059130  mov     rcx, rbx; this
0x140059133  call    ?CollectCrossProcessDumps@CElevatedDataCollection@@IEAAJXZ; CElevatedDataCollection::CollectCrossProcessDumps(void)
0x140059138  mov     edi, eax
0x14005913a  test    eax, eax
0x14005913c  jns     short loc_14005916C
0x14005913e  mov     r8d, eax
0x140059141  lea     rdx, aCollectcrosspr; "CollectCrossProcessDumps failed: 0x%x"
0x140059148  mov     rcx, rbx; this
0x14005914b  call    ?LogDataCollectionStatus@CElevatedDataCollection@@IEAAJPEB_WZZ; CElevatedDataCollection::LogDataCollectionStatus(wchar_t const *,...)
0x140059150  mov     rcx, cs:WPP_GLOBAL_Control
0x140059157  cmp     rcx, r14
0x14005915a  jz      short loc_1400591B2
0x14005915c  test    byte ptr [rcx+1Ch], 1
0x140059160  jz      short loc_1400591B2
0x140059162  mov     edx, 4Dh ; 'M'
0x140059167  jmp     loc_14005909D
0x14005916c  call    cs:__imp_CoUninitialize
0x140059172  xor     edi, edi
0x140059174  jmp     short loc_1400591B8
0x140059176  mov     r8d, edi
0x140059179  lea     rdx, aCollectcrosspr_0; "CollectCrossProcessModuleDumps failed: "...
0x140059180  mov     rcx, rbx; this
0x140059183  call    ?LogDataCollectionStatus@CElevatedDataCollection@@IEAAJPEB_WZZ; CElevatedDataCollection::LogDataCollectionStatus(wchar_t const *,...)
0x140059188  mov     rcx, cs:WPP_GLOBAL_Control
0x14005918f  cmp     rcx, r14
0x140059192  jz      short loc_1400591B2
0x140059194  test    byte ptr [rcx+1Ch], 1
0x140059198  jz      short loc_1400591B2
0x14005919a  mov     rcx, [rcx+10h]
0x14005919e  mov     edx, 4Ch ; 'L'
0x1400591a3  mov     r9d, ebp
0x1400591a6  mov     dword ptr [rsp+0A8h+var_88], edi
0x1400591aa  mov     r8, r12
0x1400591ad  call    WPP_SF_Dd
0x1400591b2  call    cs:__imp_CoUninitialize
0x1400591b8  mov     r15, [rsp+0A8h+var_78]
0x1400591bd  mov     rdx, [rbx+320h]; wchar_t *
0x1400591c4  cmp     rdx, [rbx+328h]
0x1400591cb  jz      short loc_140059209
0x1400591cd  xor     r9d, r9d; wchar_t *
0x1400591d0  lea     r8, aElevateddataco; "ElevatedDataCollectionStatus.txt"
0x1400591d7  mov     rcx, r15; void *
0x1400591da  call    ?AddStringBufferToReport@@YAJPEAXPEB_W11@Z; AddStringBufferToReport(void *,wchar_t const *,wchar_t const *,wchar_t const *)
0x1400591df  test    eax, eax
0x1400591e1  jns     short loc_140059209
0x1400591e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400591ea  cmp     rcx, r14
0x1400591ed  jz      short loc_140059209
0x1400591ef  test    byte ptr [rcx+1Ch], 1
0x1400591f3  jz      short loc_140059209
0x1400591f5  mov     rcx, [rcx+10h]
0x1400591f9  mov     edx, 4Eh ; 'N'
0x1400591fe  mov     r9d, eax
0x140059201  mov     r8, r12
0x140059204  call    WPP_SF_d
0x140059209  mov     eax, edi
0x14005920b  mov     rcx, [rsp+0A8h+var_48]
0x140059210  xor     rcx, rsp; StackCookie
0x140059213  call    __security_check_cookie
0x140059218  add     rsp, 70h
0x14005921c  pop     r15
0x14005921e  pop     r14
0x140059220  pop     r13
0x140059222  pop     r12
0x140059224  pop     rdi
0x140059225  pop     rbp
0x140059226  pop     rbx
0x140059227  retn
```
