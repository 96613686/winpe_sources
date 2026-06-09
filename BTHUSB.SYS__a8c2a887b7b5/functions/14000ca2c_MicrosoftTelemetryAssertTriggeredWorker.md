# MicrosoftTelemetryAssertTriggeredWorker

- ea: `0x14000ca2c`
- end: `0x14000d332`
- name: `MicrosoftTelemetryAssertTriggeredWorker`
- size: `2310`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000c9c0`
- `0x14000c9fc`

## callees

- `0x1400010b8`
- `0x14000ca2c`
- `0x14000ddc0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000cc33`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d305`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000cc33`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d305`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000ca85`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d2bf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000ca85`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d2bf`
- `ntoskrnl!ExAllocatePool2` at `0x14000cae8`
- `ntoskrnl!ExAllocatePool2` at `0x14000cae8`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000cd5b`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000cf06`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000cf98`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000cd5b`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000cf06`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000cf98`
- `ntoskrnl!DbgkWerCaptureLiveKernelDump` at `0x14000cfe2`
- `ntoskrnl!DbgkWerCaptureLiveKernelDump` at `0x14000cfe2`
- `ntoskrnl!KeQueryTimeIncrement` at `0x14000cb06`
- `ntoskrnl!KeQueryTimeIncrement` at `0x14000cb83`
- `ntoskrnl!KeQueryTimeIncrement` at `0x14000cb06`
- `ntoskrnl!KeQueryTimeIncrement` at `0x14000cb83`

## pseudocode

```c
void __fastcall MicrosoftTelemetryAssertTriggeredWorker(
        unsigned __int64 a1,
        int a2,
        __int64 *a3,
        unsigned int a4,
        int a5,
        const char *a6)
{
  unsigned int v6; // r15d
  KIRQL v9; // al
  __int64 *v10; // rcx
  KIRQL v11; // si
  __int64 *v12; // rdi
  unsigned __int64 *Pool2; // rax
  __int64 v14; // rbx
  ULONG TimeIncrement; // eax
  __int64 v16; // rax
  __int64 v17; // rbx
  __int64 v18; // rdx
  __int16 v19; // cx
  unsigned int v20; // r12d
  unsigned __int64 v21; // rcx
  unsigned int v22; // r14d
  int v23; // eax
  unsigned int v24; // eax
  int v25; // edi
  __int64 v26; // rbx
  const char *v27; // rax
  __int64 v28; // rcx
  KIRQL CurrentIrql; // al
  __int64 *v30; // rcx
  __int64 v31; // rax
  int v32; // eax
  const char *v33; // rcx
  __int64 v34; // rax
  const char *v35; // rax
  __int64 v36; // rcx
  KIRQL v37; // al
  const char *v38; // rcx
  __int64 v39; // rax
  int v40; // edi
  const char *v41; // rax
  __int64 v42; // rcx
  int v43; // ebx
  const char *v44; // rax
  KIRQL v45; // al
  __int64 *v46; // rcx
  int v47; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v48; // [rsp+54h] [rbp-ACh] BYREF
  int v49; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v50; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v51; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v52; // [rsp+64h] [rbp-9Ch] BYREF
  int v53; // [rsp+68h] [rbp-98h] BYREF
  int v54; // [rsp+6Ch] [rbp-94h]
  unsigned int v55; // [rsp+70h] [rbp-90h]
  int v56; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v57; // [rsp+78h] [rbp-88h] BYREF
  int v58; // [rsp+7Ch] [rbp-84h]
  unsigned int v59; // [rsp+80h] [rbp-80h]
  unsigned __int64 v60; // [rsp+88h] [rbp-78h]
  struct _EVENT_DATA_DESCRIPTOR v61[2]; // [rsp+90h] [rbp-70h] BYREF
  int *v62; // [rsp+B0h] [rbp-50h]
  __int64 v63; // [rsp+B8h] [rbp-48h]
  int *v64; // [rsp+C0h] [rbp-40h]
  __int64 v65; // [rsp+C8h] [rbp-38h]
  int *v66; // [rsp+D0h] [rbp-30h]
  __int64 v67; // [rsp+D8h] [rbp-28h]
  int *v68; // [rsp+E0h] [rbp-20h]
  __int64 v69; // [rsp+E8h] [rbp-18h]
  const char *v70; // [rsp+F0h] [rbp-10h]
  int v71; // [rsp+F8h] [rbp-8h]
  int v72; // [rsp+FCh] [rbp-4h]
  int *v73; // [rsp+100h] [rbp+0h]
  __int64 v74; // [rsp+108h] [rbp+8h]
  int *v75; // [rsp+110h] [rbp+10h]
  __int64 v76; // [rsp+118h] [rbp+18h]
  int *v77; // [rsp+120h] [rbp+20h]
  __int64 v78; // [rsp+128h] [rbp+28h]
  void *v79; // [rsp+130h] [rbp+30h]
  int v80; // [rsp+138h] [rbp+38h]
  int v81; // [rsp+13Ch] [rbp+3Ch]
  int *v82; // [rsp+140h] [rbp+40h]
  __int64 v83; // [rsp+148h] [rbp+48h]
  int *v84; // [rsp+150h] [rbp+50h]
  __int64 v85; // [rsp+158h] [rbp+58h]
  const char *v86; // [rsp+160h] [rbp+60h]
  int v87; // [rsp+168h] [rbp+68h]
  int v88; // [rsp+16Ch] [rbp+6Ch]

  v6 = 0;
  v59 = a4;
  v58 = a2;
  v60 = a1;
  if ( !_InterlockedExchangeAdd(&g_AssertsOperational, 0) )
    return;
  v9 = KeAcquireSpinLockRaiseToDpc(&g_AssertSpinLock);
  v10 = (__int64 *)g_MicrosoftTelemetryAssertsTriggeredList;
  v11 = v9;
  if ( &g_MicrosoftTelemetryAssertsTriggeredList == (__int64 *)g_MicrosoftTelemetryAssertsTriggeredList )
    goto LABEL_7;
  while ( 1 )
  {
    v12 = v10 - 4;
    if ( *(v10 - 4) == a1 )
      break;
    v10 = (__int64 *)*v10;
    if ( &g_MicrosoftTelemetryAssertsTriggeredList == v10 )
      goto LABEL_7;
  }
  if ( v10 == (__int64 *)32 )
  {
LABEL_7:
    Pool2 = (unsigned __int64 *)ExAllocatePool2(66, 48, 1953657665);
    v12 = (__int64 *)Pool2;
    if ( !Pool2 )
    {
LABEL_82:
      KeReleaseSpinLock(&g_AssertSpinLock, v11);
      return;
    }
    v14 = MEMORY[0xFFFFF78000000320];
    *Pool2 = a1;
    TimeIncrement = KeQueryTimeIncrement();
    v12[2] = 0;
    *((_DWORD *)v12 + 6) = 0;
    v12[1] = ((__int64)((unsigned __int128)(v14 * TimeIncrement * (__int128)0x346DC5D63886594BLL) >> 64) >> 11)
           - 60001
           + ((unsigned __int64)((unsigned __int128)(v14 * TimeIncrement * (__int128)0x346DC5D63886594BLL) >> 64) >> 63);
    v16 = g_MicrosoftTelemetryAssertsTriggeredList;
    if ( *(__int64 **)(g_MicrosoftTelemetryAssertsTriggeredList + 8) != &g_MicrosoftTelemetryAssertsTriggeredList )
      __fastfail(3u);
    v12[4] = g_MicrosoftTelemetryAssertsTriggeredList;
    v12[5] = (__int64)&g_MicrosoftTelemetryAssertsTriggeredList;
    *(_QWORD *)(v16 + 8) = v12 + 4;
    g_MicrosoftTelemetryAssertsTriggeredList = (__int64)(v12 + 4);
  }
  ++*((_DWORD *)v12 + 4);
  ++*((_DWORD *)v12 + 5);
  v17 = MEMORY[0xFFFFF78000000320];
  v18 = v17 * KeQueryTimeIncrement() / 10000;
  if ( (unsigned __int64)(v18 - v12[1]) <= 0xEA60 )
    goto LABEL_82;
  v19 = *(_WORD *)(MEMORY[0x14000003C] + 0x140000018LL);
  if ( v19 == 267 || v19 == 523 )
  {
    v20 = *(_DWORD *)(MEMORY[0x14000003C] + 0x140000008LL);
    v6 = *(_DWORD *)(MEMORY[0x14000003C] + 0x140000050LL);
  }
  else
  {
    v20 = 0;
  }
  if ( a1 < 0x140000000LL || (v21 = 0x140000000LL + v6, v21 <= 0x140000000LL) || a1 > v21 )
    v22 = 0;
  else
    v22 = a1 - 0x40000000;
  v23 = *((_DWORD *)v12 + 4);
  v12[1] = v18;
  v54 = v23;
  v24 = *((_DWORD *)v12 + 5);
  v25 = *((_DWORD *)v12 + 6);
  v55 = v24;
  KeReleaseSpinLock(&g_AssertSpinLock, v11);
  if ( !a3 )
    a3 = (__int64 *)g_ModuleName;
  v26 = -1;
  if ( v58 )
  {
    if ( (unsigned int)dword_140016040 > 5
      && (qword_140016050 & 0x400000000000LL) != 0
      && (qword_140016058 & 0x400000000000LL) == qword_140016058 )
    {
      v56 = 10;
      v62 = &v56;
      v64 = (int *)&v57;
      v66 = &v47;
      v68 = (int *)&v48;
      v27 = (const char *)g_ModuleName;
      v63 = 4;
      v57 = v22;
      v65 = 4;
      v47 = v20;
      v67 = 4;
      v48 = v6;
      v69 = 4;
      if ( !g_ModuleName )
        v27 = "<unknown>";
      v28 = -1;
      do
        ++v28;
      while ( v27[v28] );
      v70 = v27;
      v49 = v54;
      v73 = &v49;
      v50 = v55;
      v75 = (int *)&v50;
      v71 = v28 + 1;
      v72 = 0;
      v74 = 4;
      v76 = 4;
      CurrentIrql = KeGetCurrentIrql();
      v78 = 4;
      v51 = CurrentIrql;
      v77 = (int *)&v51;
      if ( a3 )
      {
        v30 = a3;
        v31 = -1;
        do
          ++v31;
        while ( *((_BYTE *)a3 + v31) );
        v32 = v31 + 1;
      }
      else
      {
        v30 = &qword_140010B60;
        v32 = 1;
      }
      v80 = v32;
      v52 = v59;
      v82 = (int *)&v52;
      v53 = a5;
      v79 = v30;
      v33 = a6;
      v84 = &v53;
      v81 = 0;
      if ( !a6 )
        v33 = "<unknown>";
      v83 = 4;
      v34 = -1;
      v85 = 4;
      do
        ++v34;
      while ( v33[v34] );
      v88 = 0;
      v87 = v34 + 1;
      v86 = v33;
      tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140016040, (unsigned __int8 *)&unk_140011320, 0, 0, 0xEu, v61);
    }
  }
  else if ( (unsigned int)dword_140016040 > 5
         && (qword_140016050 & 0x400000000000LL) != 0
         && (qword_140016058 & 0x400000000000LL) == qword_140016058 )
  {
    v53 = 10;
    v62 = &v53;
    v64 = (int *)&v52;
    v66 = (int *)&v51;
    v68 = (int *)&v50;
    v35 = (const char *)g_ModuleName;
    v63 = 4;
    v52 = v22;
    v65 = 4;
    v51 = v20;
    v67 = 4;
    v50 = v6;
    v69 = 4;
    if ( !g_ModuleName )
      v35 = "<unknown>";
    v36 = -1;
    do
      ++v36;
    while ( v35[v36] );
    v70 = v35;
    v49 = v54;
    v73 = &v49;
    v48 = v55;
    v75 = (int *)&v48;
    v71 = v36 + 1;
    v72 = 0;
    v74 = 4;
    v76 = 4;
    v37 = KeGetCurrentIrql();
    v38 = a6;
    v47 = v37;
    v77 = &v47;
    if ( !a6 )
      v38 = "<unknown>";
    v78 = 4;
    v39 = -1;
    do
      ++v39;
    while ( v38[v39] );
    v81 = 0;
    v80 = v39 + 1;
    v79 = (void *)v38;
    tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140016040, (unsigned __int8 *)qword_140011470, 0, 0, 0xBu, v61);
  }
  if ( dword_140016078 && !v25 && !KeGetCurrentIrql() )
  {
    v40 = DbgkWerCaptureLiveKernelDump(L"TELASSERT", 465, v22, g_ModuleName, v20, v6, 0, 0, 0);
    if ( v58 )
    {
      if ( (unsigned int)dword_140016040 > 5
        && (qword_140016050 & 0x400000000000LL) != 0
        && (qword_140016058 & 0x400000000000LL) == qword_140016058 )
      {
        v53 = 10;
        v62 = &v53;
        v64 = (int *)&v52;
        v66 = (int *)&v51;
        v68 = (int *)&v50;
        v41 = (const char *)g_ModuleName;
        v63 = 4;
        v52 = v22;
        v65 = 4;
        v51 = v20;
        v67 = 4;
        v50 = v6;
        v69 = 4;
        if ( !g_ModuleName )
          v41 = "<unknown>";
        v42 = -1;
        do
          ++v42;
        while ( v41[v42] );
        v70 = v41;
        v49 = v54;
        v73 = &v49;
        v48 = v55;
        v75 = (int *)&v48;
        v77 = &v47;
        v71 = v42 + 1;
        v72 = 0;
        v74 = 4;
        v76 = 4;
        v47 = v40;
        v78 = 4;
        if ( a3 )
        {
          do
            ++v26;
          while ( *((_BYTE *)a3 + v26) );
          v43 = v26 + 1;
        }
        else
        {
          a3 = &qword_140010B60;
          v43 = 1;
        }
        v57 = v59;
        v82 = (int *)&v57;
        v56 = a5;
        v84 = &v56;
        v79 = a3;
        v80 = v43;
        v81 = 0;
        v83 = 4;
        v85 = 4;
        tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140016040, (unsigned __int8 *)word_1400113CA, 0, 0, 0xDu, v61);
      }
    }
    else if ( (unsigned int)dword_140016040 > 5
           && (qword_140016050 & 0x400000000000LL) != 0
           && (qword_140016058 & 0x400000000000LL) == qword_140016058 )
    {
      v53 = 10;
      v62 = &v53;
      v64 = (int *)&v52;
      v66 = (int *)&v51;
      v68 = (int *)&v50;
      v44 = (const char *)g_ModuleName;
      v63 = 4;
      v52 = v22;
      v65 = 4;
      v51 = v20;
      v67 = 4;
      v50 = v6;
      v69 = 4;
      if ( !g_ModuleName )
        v44 = "<unknown>";
      do
        ++v26;
      while ( v44[v26] );
      v49 = v54;
      v70 = v44;
      v73 = &v49;
      v48 = v55;
      v75 = (int *)&v48;
      v77 = &v47;
      v71 = v26 + 1;
      v72 = 0;
      v74 = 4;
      v76 = 4;
      v47 = v40;
      v78 = 4;
      tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140016040, (unsigned __int8 *)byte_1400114DD, 0, 0, 0xAu, v61);
    }
    if ( !v40 )
    {
      v45 = KeAcquireSpinLockRaiseToDpc(&g_AssertSpinLock);
      v46 = (__int64 *)g_MicrosoftTelemetryAssertsTriggeredList;
      v11 = v45;
      if ( &g_MicrosoftTelemetryAssertsTriggeredList != (__int64 *)g_MicrosoftTelemetryAssertsTriggeredList )
      {
        while ( *(v46 - 4) != v60 )
        {
          v46 = (__int64 *)*v46;
          if ( &g_MicrosoftTelemetryAssertsTriggeredList == v46 )
            goto LABEL_82;
        }
        ++*((_DWORD *)v46 - 2);
      }
      goto LABEL_82;
    }
  }
}

```

## disassembly

```asm
0x14000ca2c  push    rbp
0x14000ca2e  push    rbx
0x14000ca2f  push    rsi
0x14000ca30  push    rdi
0x14000ca31  push    r12
0x14000ca33  push    r13
0x14000ca35  push    r14
0x14000ca37  push    r15
0x14000ca39  lea     rbp, [rsp-88h]
0x14000ca41  sub     rsp, 188h
0x14000ca48  mov     rax, cs:__security_cookie
0x14000ca4f  xor     rax, rsp
0x14000ca52  mov     [rbp+0C0h+var_50], rax
0x14000ca56  xor     r15d, r15d
0x14000ca59  mov     [rbp+0C0h+var_140], r9d
0x14000ca5d  mov     eax, r15d
0x14000ca60  mov     [rsp+1C0h+var_144], edx
0x14000ca64  mov     r13, r8
0x14000ca67  mov     [rbp+0C0h+var_138], rcx
0x14000ca6b  mov     r14, rcx
0x14000ca6e  lock xadd cs:g_AssertsOperational, eax
0x14000ca76  test    eax, eax
0x14000ca78  jz      loc_14000D311
0x14000ca7e  lea     rcx, g_AssertSpinLock; SpinLock
0x14000ca85  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000ca8c  nop     dword ptr [rax+rax+00h]
0x14000ca91  mov     rcx, cs:g_MicrosoftTelemetryAssertsTriggeredList
0x14000ca98  lea     rdx, g_MicrosoftTelemetryAssertsTriggeredList
0x14000ca9f  mov     sil, al
0x14000caa2  mov     rbx, 0FFFFF78000000320h
0x14000caac  mov     r12, 346DC5D63886594Bh
0x14000cab6  cmp     rdx, rcx
0x14000cab9  jz      short loc_14000CADA
0x14000cabb  lea     rdi, [rcx-20h]
0x14000cabf  cmp     [rdi], r14
0x14000cac2  jz      short loc_14000CAD1
0x14000cac4  mov     rax, [rcx]
0x14000cac7  mov     rcx, rax
0x14000caca  cmp     rdx, rax
0x14000cacd  jnz     short loc_14000CABB
0x14000cacf  jmp     short loc_14000CADA
0x14000cad1  test    rdi, rdi
0x14000cad4  jnz     loc_14000CB7A
0x14000cada  mov     edx, 30h ; '0'
0x14000cadf  mov     r8d, 74727341h
0x14000cae5  lea     ecx, [rdx+12h]
0x14000cae8  call    cs:__imp_ExAllocatePool2
0x14000caef  nop     dword ptr [rax+rax+00h]
0x14000caf4  mov     rdi, rax
0x14000caf7  test    rax, rax
0x14000cafa  jz      loc_14000D2FB
0x14000cb00  mov     rbx, [rbx]
0x14000cb03  mov     [rax], r14
0x14000cb06  call    cs:__imp_KeQueryTimeIncrement
0x14000cb0d  nop     dword ptr [rax+rax+00h]
0x14000cb12  mov     ecx, eax
0x14000cb14  mov     rax, r12
0x14000cb17  imul    rcx, rbx
0x14000cb1b  mov     [rdi+10h], r15
0x14000cb1f  imul    rcx
0x14000cb22  mov     [rdi+18h], r15d
0x14000cb26  sar     rdx, 0Bh
0x14000cb2a  mov     rax, rdx
0x14000cb2d  add     rdx, 0FFFFFFFFFFFF159Fh
0x14000cb34  shr     rax, 3Fh
0x14000cb38  add     rax, rdx
0x14000cb3b  lea     rdx, g_MicrosoftTelemetryAssertsTriggeredList
0x14000cb42  mov     [rdi+8], rax
0x14000cb46  mov     rax, cs:g_MicrosoftTelemetryAssertsTriggeredList
0x14000cb4d  cmp     [rax+8], rdx
0x14000cb51  jz      short loc_14000CB5A
0x14000cb53  mov     ecx, 3
0x14000cb58  int     29h; Win8: RtlFailFast(ecx)
0x14000cb5a  lea     rcx, [rdi+20h]
0x14000cb5e  mov     rbx, 0FFFFF78000000320h
0x14000cb68  mov     [rcx], rax
0x14000cb6b  mov     [rcx+8], rdx
0x14000cb6f  mov     [rax+8], rcx
0x14000cb73  mov     cs:g_MicrosoftTelemetryAssertsTriggeredList, rcx
0x14000cb7a  inc     dword ptr [rdi+10h]
0x14000cb7d  inc     dword ptr [rdi+14h]
0x14000cb80  mov     rbx, [rbx]
0x14000cb83  call    cs:__imp_KeQueryTimeIncrement
0x14000cb8a  nop     dword ptr [rax+rax+00h]
0x14000cb8f  mov     ecx, eax
0x14000cb91  mov     rax, r12
0x14000cb94  imul    rcx, rbx
0x14000cb98  imul    rcx
0x14000cb9b  sar     rdx, 0Bh
0x14000cb9f  mov     rax, rdx
0x14000cba2  shr     rax, 3Fh
0x14000cba6  add     rdx, rax
0x14000cba9  mov     rax, rdx
0x14000cbac  sub     rax, [rdi+8]
0x14000cbb0  cmp     rax, 0EA60h
0x14000cbb6  jbe     loc_14000D2FB
0x14000cbbc  movsxd  rax, dword ptr cs:14000003Ch
0x14000cbc3  lea     r9, cs:140000000h
0x14000cbca  mov     r8d, 10Bh
0x14000cbd0  movzx   ecx, word ptr [rax+r9+18h]
0x14000cbd6  cmp     cx, r8w
0x14000cbda  jz      short loc_14000CBE8
0x14000cbdc  mov     r8d, 20Bh
0x14000cbe2  cmp     cx, r8w
0x14000cbe6  jnz     short loc_14000CBF4
0x14000cbe8  mov     r12d, [rax+r9+8]
0x14000cbed  mov     r15d, [rax+r9+50h]
0x14000cbf2  jmp     short loc_14000CBF7
0x14000cbf4  mov     r12d, r15d
0x14000cbf7  cmp     r14, r9
0x14000cbfa  jb      short loc_14000CC11
0x14000cbfc  mov     ecx, r15d
0x14000cbff  add     rcx, r9
0x14000cc02  cmp     rcx, r9
0x14000cc05  jbe     short loc_14000CC11
0x14000cc07  cmp     r14, rcx
0x14000cc0a  ja      short loc_14000CC11
0x14000cc0c  sub     r14d, r9d
0x14000cc0f  jmp     short loc_14000CC14
0x14000cc11  xor     r14d, r14d
0x14000cc14  mov     eax, [rdi+10h]
0x14000cc17  lea     rcx, g_AssertSpinLock; SpinLock
0x14000cc1e  mov     [rdi+8], rdx
0x14000cc22  mov     dl, sil; NewIrql
0x14000cc25  mov     [rsp+1C0h+var_154], eax
0x14000cc29  mov     eax, [rdi+14h]
0x14000cc2c  mov     edi, [rdi+18h]
0x14000cc2f  mov     [rsp+1C0h+var_150], eax
0x14000cc33  call    cs:__imp_KeReleaseSpinLock
0x14000cc3a  nop     dword ptr [rax+rax+00h]
0x14000cc3f  mov     eax, cs:dword_140016040
0x14000cc45  lea     rsi, qword_140010B60
0x14000cc4c  xor     edx, edx
0x14000cc4e  lea     r10, aUnknown; "<unknown>"
0x14000cc55  test    r13, r13
0x14000cc58  mov     r9, 400000000000h
0x14000cc62  cmovz   r13, cs:g_ModuleName
0x14000cc6a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000cc6e  lea     r11d, [rdx+0Ah]
0x14000cc72  cmp     [rsp+1C0h+var_144], edx
0x14000cc76  jz      loc_14000CE27
0x14000cc7c  cmp     eax, 5
0x14000cc7f  jbe     loc_14000CF82
0x14000cc85  mov     rcx, cs:qword_140016058
0x14000cc8c  mov     rax, cs:qword_140016050
0x14000cc93  test    r9, rax
0x14000cc96  jz      loc_14000CF82
0x14000cc9c  mov     rax, rcx
0x14000cc9f  and     rax, r9
0x14000cca2  cmp     rax, rcx
0x14000cca5  jnz     loc_14000CF82
0x14000ccab  lea     rax, [rsp+1C0h+var_14C]
0x14000ccb0  mov     [rsp+1C0h+var_14C], r11d
0x14000ccb5  mov     [rbp+0C0h+var_110], rax
0x14000ccb9  lea     rax, [rsp+1C0h+var_148]
0x14000ccbe  mov     [rbp+0C0h+var_100], rax
0x14000ccc2  lea     rax, [rsp+1C0h+var_170]
0x14000ccc7  mov     [rbp+0C0h+var_F0], rax
0x14000cccb  lea     rax, [rsp+1C0h+var_16C]
0x14000ccd0  mov     [rbp+0C0h+var_E0], rax
0x14000ccd4  mov     rax, cs:g_ModuleName
0x14000ccdb  mov     [rbp+0C0h+var_108], 4
0x14000cce3  mov     [rsp+1C0h+var_148], r14d
0x14000cce8  mov     [rbp+0C0h+var_F8], 4
0x14000ccf0  mov     [rsp+1C0h+var_170], r12d
0x14000ccf5  mov     [rbp+0C0h+var_E8], 4
0x14000ccfd  mov     [rsp+1C0h+var_16C], r15d
0x14000cd02  mov     [rbp+0C0h+var_D8], 4
0x14000cd0a  test    rax, rax
0x14000cd0d  jnz     short loc_14000CD12
0x14000cd0f  mov     rax, r10
0x14000cd12  mov     rcx, rbx
0x14000cd15  inc     rcx
0x14000cd18  cmp     [rax+rcx], dl
0x14000cd1b  jnz     short loc_14000CD15
0x14000cd1d  mov     [rbp+0C0h+var_D0], rax
0x14000cd21  inc     ecx
0x14000cd23  mov     eax, [rsp+1C0h+var_154]
0x14000cd27  mov     [rsp+1C0h+var_168], eax
0x14000cd2b  lea     rax, [rsp+1C0h+var_168]
0x14000cd30  mov     [rbp+0C0h+var_C0], rax
0x14000cd34  mov     eax, [rsp+1C0h+var_150]
0x14000cd38  mov     [rsp+1C0h+var_164], eax
0x14000cd3c  lea     rax, [rsp+1C0h+var_164]
0x14000cd41  mov     [rbp+0C0h+var_B0], rax
0x14000cd45  mov     [rbp+0C0h+var_C8], ecx
0x14000cd48  mov     [rbp+0C0h+var_C4], edx
0x14000cd4b  mov     [rbp+0C0h+var_B8], 4
0x14000cd53  mov     [rbp+0C0h+var_A8], 4
0x14000cd5b  call    cs:__imp_KeGetCurrentIrql
0x14000cd62  nop     dword ptr [rax+rax+00h]
0x14000cd67  xor     edx, edx
0x14000cd69  mov     [rbp+0C0h+var_98], 4
0x14000cd71  movzx   eax, al
0x14000cd74  mov     [rsp+1C0h+var_160], eax
0x14000cd78  lea     rax, [rsp+1C0h+var_160]
0x14000cd7d  mov     [rbp+0C0h+var_A0], rax
0x14000cd81  test    r13, r13
0x14000cd84  jz      short loc_14000CD99
0x14000cd86  mov     rcx, r13
0x14000cd89  mov     rax, rbx
0x14000cd8c  inc     rax
0x14000cd8f  cmp     [rax+r13], dl
0x14000cd93  jnz     short loc_14000CD8C
0x14000cd95  inc     eax
0x14000cd97  jmp     short loc_14000CDA1
0x14000cd99  mov     rcx, rsi
0x14000cd9c  mov     eax, 1
0x14000cda1  mov     [rbp+0C0h+var_88], eax
0x14000cda4  mov     eax, [rbp+0C0h+var_140]
0x14000cda7  mov     [rsp+1C0h+var_15C], eax
0x14000cdab  lea     rax, [rsp+1C0h+var_15C]
0x14000cdb0  mov     [rbp+0C0h+var_80], rax
0x14000cdb4  mov     eax, [rbp+0C0h+arg_20]
0x14000cdba  mov     [rsp+1C0h+var_158], eax
0x14000cdbe  lea     rax, [rsp+1C0h+var_158]
0x14000cdc3  mov     [rbp+0C0h+var_90], rcx
0x14000cdc7  mov     rcx, [rbp+0C0h+arg_28]
0x14000cdce  mov     [rbp+0C0h+var_70], rax
0x14000cdd2  test    rcx, rcx
0x14000cdd5  lea     rax, aUnknown; "<unknown>"
0x14000cddc  mov     [rbp+0C0h+var_84], edx
0x14000cddf  cmovz   rcx, rax
0x14000cde3  mov     [rbp+0C0h+var_78], 4
0x14000cdeb  mov     rax, rbx
0x14000cdee  mov     [rbp+0C0h+var_68], 4
0x14000cdf6  inc     rax
0x14000cdf9  cmp     [rcx+rax], dl
0x14000cdfc  jnz     short loc_14000CDF6
0x14000cdfe  inc     eax
0x14000ce00  mov     [rbp+0C0h+var_54], edx
0x14000ce03  mov     [rbp+0C0h+var_58], eax
0x14000ce06  lea     rdx, unk_140011320
0x14000ce0d  lea     rax, [rbp+0C0h+var_130]
0x14000ce11  mov     [rbp+0C0h+var_60], rcx
0x14000ce15  mov     [rsp+1C0h+var_198], rax
0x14000ce1a  mov     dword ptr [rsp+1C0h+var_1A0], 0Eh
0x14000ce22  jmp     loc_14000CF70
0x14000ce27  cmp     eax, 5
0x14000ce2a  jbe     loc_14000CF82
0x14000ce30  mov     rcx, cs:qword_140016058
0x14000ce37  mov     rax, cs:qword_140016050
0x14000ce3e  test    r9, rax
0x14000ce41  jz      loc_14000CF82
0x14000ce47  mov     rax, rcx
0x14000ce4a  and     rax, r9
0x14000ce4d  cmp     rax, rcx
0x14000ce50  jnz     loc_14000CF82
0x14000ce56  lea     rax, [rsp+1C0h+var_158]
0x14000ce5b  mov     [rsp+1C0h+var_158], r11d
0x14000ce60  mov     [rbp+0C0h+var_110], rax
0x14000ce64  lea     rax, [rsp+1C0h+var_15C]
0x14000ce69  mov     [rbp+0C0h+var_100], rax
0x14000ce6d  lea     rax, [rsp+1C0h+var_160]
0x14000ce72  mov     [rbp+0C0h+var_F0], rax
0x14000ce76  lea     rax, [rsp+1C0h+var_164]
0x14000ce7b  mov     [rbp+0C0h+var_E0], rax
0x14000ce7f  mov     rax, cs:g_ModuleName
0x14000ce86  mov     [rbp+0C0h+var_108], 4
0x14000ce8e  mov     [rsp+1C0h+var_15C], r14d
0x14000ce93  mov     [rbp+0C0h+var_F8], 4
0x14000ce9b  mov     [rsp+1C0h+var_160], r12d
0x14000cea0  mov     [rbp+0C0h+var_E8], 4
0x14000cea8  mov     [rsp+1C0h+var_164], r15d
0x14000cead  mov     [rbp+0C0h+var_D8], 4
0x14000ceb5  test    rax, rax
0x14000ceb8  jnz     short loc_14000CEBD
0x14000ceba  mov     rax, r10
0x14000cebd  mov     rcx, rbx
0x14000cec0  inc     rcx
0x14000cec3  cmp     [rax+rcx], dl
0x14000cec6  jnz     short loc_14000CEC0
0x14000cec8  mov     [rbp+0C0h+var_D0], rax
0x14000cecc  inc     ecx
0x14000cece  mov     eax, [rsp+1C0h+var_154]
0x14000ced2  mov     [rsp+1C0h+var_168], eax
0x14000ced6  lea     rax, [rsp+1C0h+var_168]
0x14000cedb  mov     [rbp+0C0h+var_C0], rax
0x14000cedf  mov     eax, [rsp+1C0h+var_150]
0x14000cee3  mov     [rsp+1C0h+var_16C], eax
0x14000cee7  lea     rax, [rsp+1C0h+var_16C]
0x14000ceec  mov     [rbp+0C0h+var_B0], rax
0x14000cef0  mov     [rbp+0C0h+var_C8], ecx
0x14000cef3  mov     [rbp+0C0h+var_C4], edx
0x14000cef6  mov     [rbp+0C0h+var_B8], 4
0x14000cefe  mov     [rbp+0C0h+var_A8], 4
0x14000cf06  call    cs:__imp_KeGetCurrentIrql
0x14000cf0d  nop     dword ptr [rax+rax+00h]
0x14000cf12  mov     rcx, [rbp+0C0h+arg_28]
0x14000cf19  xor     edx, edx
0x14000cf1b  movzx   eax, al
0x14000cf1e  test    rcx, rcx
0x14000cf21  mov     [rsp+1C0h+var_170], eax
0x14000cf25  lea     rax, [rsp+1C0h+var_170]
0x14000cf2a  mov     [rbp+0C0h+var_A0], rax
0x14000cf2e  lea     rax, aUnknown; "<unknown>"
0x14000cf35  cmovz   rcx, rax
0x14000cf39  mov     [rbp+0C0h+var_98], 4
0x14000cf41  mov     rax, rbx
0x14000cf44  inc     rax
  ... truncated ...
```
