# BipPdcReferenceAcquire

- ea: `0x180010c70`
- end: `0x180011211`
- name: `BipPdcReferenceAcquire`
- size: `1441`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001079c`
- `0x1800133d4`
- `0x180015aa0`

## callees

- `0x180010c70`
- `0x18003f778`
- `0x18004af00`
- `0x18006a8d4`
- `0x18006d364`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180010ce4`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180010e31`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180011012`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180010ce4`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180010e31`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180011012`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180010ddd`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180010ef7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180011053`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800111c7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180010ddd`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180010ef7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180011053`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800111c7`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800111bb`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800111bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010e37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010e37`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180010e18`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180010e18`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010e75`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010e75`
- `UMPDC!Pdcv2ActivationClientDeactivate` at `0x1800111ef`
- `UMPDC!Pdcv2ActivationClientDeactivate` at `0x1800111ef`
- `UMPDC!Pdcv2ActivationClientActivate` at `0x180010fff`
- `UMPDC!Pdcv2ActivationClientActivate` at `0x180010fff`

## pseudocode

```c
int __fastcall BipPdcReferenceAcquire(__int64 *a1, __int64 a2)
{
  __int64 v4; // rax
  __int64 v5; // rcx
  __int128 v6; // xmm0
  __int64 EntryPoint; // rax
  __int64 v8; // rdx
  DWORD v9; // r15d
  __int64 v10; // rcx
  __int64 v11; // rax
  unsigned __int16 *v12; // rdx
  __int128 *v13; // rax
  __int128 v14; // xmm0
  int v15; // ecx
  _QWORD *ThreadLocalStoragePointer; // rax
  int v17; // ebx
  __int64 v18; // rsi
  _DWORD *v19; // rdx
  char v20; // si
  __int64 v21; // rax
  __int64 v22; // rcx
  struct _FILETIME v23; // rax
  __int64 v24; // rdx
  __int64 v25; // r8
  int v26; // ebx
  _DWORD *v27; // rax
  _DWORD *v28; // r13
  unsigned __int16 *v29; // rsi
  __int64 v30; // r12
  __int64 v31; // rsi
  unsigned int v32; // ebx
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // r8
  int v36; // edx
  int v37; // ecx
  __int64 v38; // rax
  unsigned int v41; // [rsp+40h] [rbp-C0h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v43; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v44; // [rsp+58h] [rbp-A8h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD *v46; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v47; // [rsp+78h] [rbp-88h]
  __int128 v48; // [rsp+80h] [rbp-80h] BYREF
  __int128 v49; // [rsp+90h] [rbp-70h]
  __int128 v50; // [rsp+A0h] [rbp-60h]
  __int64 v51; // [rsp+B0h] [rbp-50h]
  __int128 v52; // [rsp+C0h] [rbp-40h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+D0h] [rbp-30h] BYREF
  __int16 *v54; // [rsp+E0h] [rbp-20h]
  int v55; // [rsp+E8h] [rbp-18h]
  int v56; // [rsp+ECh] [rbp-14h]
  unsigned __int16 *v57; // [rsp+F0h] [rbp-10h]
  int v58; // [rsp+F8h] [rbp-8h]
  int v59; // [rsp+FCh] [rbp-4h]
  __int128 *v60; // [rsp+100h] [rbp+0h]
  __int64 v61; // [rsp+108h] [rbp+8h]
  __int64 v62; // [rsp+110h] [rbp+10h]
  __int64 v63; // [rsp+118h] [rbp+18h]
  _DWORD *v64; // [rsp+120h] [rbp+20h]
  __int64 v65; // [rsp+128h] [rbp+28h]
  __int64 v66; // [rsp+130h] [rbp+30h]
  _DWORD v67[2]; // [rsp+138h] [rbp+38h] BYREF
  _QWORD *v68; // [rsp+140h] [rbp+40h]
  __int64 v69; // [rsp+148h] [rbp+48h]
  struct _FILETIME *p_SystemTimeAsFileTime; // [rsp+150h] [rbp+50h]
  __int64 v71; // [rsp+158h] [rbp+58h]
  unsigned __int16 v72[200]; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int16 v73[128]; // [rsp+310h] [rbp+210h] BYREF

  LODWORD(v4) = (unsigned int)memset_0(v72, 0, 0x182u);
  v52 = 0;
  v43 = 0;
  if ( !*a1 )
    return v4;
  RtlAcquireSRWLockExclusive(a2 + 48);
  if ( (*(_BYTE *)(a2 + 136) & 0x40) != 0 || *(_QWORD *)(a2 + 144) )
    goto LABEL_40;
  v5 = *(_QWORD *)(a2 + 64);
  v6 = 0;
  if ( v5 )
    v6 = *(_OWORD *)(v5 + 32);
  v52 = v6;
  EntryPoint = BipWorkItemGetEntryPoint(v5);
  v8 = *(_QWORD *)(a2 + 64);
  v47 = (unsigned __int16 *)EntryPoint;
  if ( (*(_DWORD *)(v8 + 24) & 0x100) != 0 )
    v9 = 0;
  else
    v9 = 2 - ((*(_DWORD *)(v8 + 24) & 0x800) != 0);
  v10 = 3;
  v41 = *(_DWORD *)(*(_QWORD *)(v8 + 72) + 584LL);
  v44 = *(_DWORD *)(v8 + 404);
  v11 = *(_QWORD *)(v8 + 80);
  v12 = v72;
  v13 = (__int128 *)(v11 + 160);
  do
  {
    v12 += 64;
    v14 = *v13;
    v13 += 8;
    *((_OWORD *)v12 - 8) = v14;
    *((_OWORD *)v12 - 7) = *(v13 - 7);
    *((_OWORD *)v12 - 6) = *(v13 - 6);
    *((_OWORD *)v12 - 5) = *(v13 - 5);
    *((_OWORD *)v12 - 4) = *(v13 - 4);
    *((_OWORD *)v12 - 3) = *(v13 - 3);
    *((_OWORD *)v12 - 2) = *(v13 - 2);
    *((_OWORD *)v12 - 1) = *(v13 - 1);
    --v10;
  }
  while ( v10 );
  *v12 = *(_WORD *)v13;
  RtlReleaseSRWLockExclusive(a2 + 48);
  v15 = *((_DWORD *)a1 + 4);
  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  SystemTimeAsFileTime = 0;
  v17 = 1 << v15;
  v18 = ThreadLocalStoragePointer[(unsigned int)tls_index];
  v46 = (_DWORD *)(v18 + 4);
  if ( *(_DWORD *)(v18 + 4) >= (unsigned int)(1 << v15) && IsDebuggerPresent() )
    BipSyncDebugPrintLockBug((struct _BI_LOCK *)(a1 + 1));
  RtlAcquireSRWLockExclusive(a1 + 1);
  *((_DWORD *)a1 + 5) = GetCurrentThreadId();
  v19 = (_DWORD *)(v18 + 8);
  *(_QWORD *)&EventDescriptor.Id = v18 + 8;
  *(_DWORD *)(v18 + 8) |= v17;
  *(_DWORD *)(v18 + 4) |= v17;
  if ( a1[3] )
  {
    v20 = 0;
    v21 = (__int64)(a1 + 4);
    v22 = 16;
    goto LABEL_23;
  }
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v23 = SystemTimeAsFileTime;
  if ( !a1[5] )
    goto LABEL_21;
  v24 = a1[6];
  if ( v24 )
  {
    if ( (unsigned __int64)(*(_QWORD *)&SystemTimeAsFileTime - v24) < 0x4C4B40 )
    {
      v20 = 0;
      goto LABEL_22;
    }
LABEL_21:
    ++a1[4];
    v20 = 1;
    a1[5] = (__int64)v23;
    goto LABEL_22;
  }
  v20 = 0;
LABEL_22:
  v19 = *(_DWORD **)&EventDescriptor.Id;
  v22 = (__int64)(a1 + 4);
  v21 = 16;
LABEL_23:
  v25 = a1[4];
  ++a1[3];
  *(_QWORD *)&EventDescriptor.Id = v25;
  *(_QWORD *)(v22 + v21) = 0;
  v26 = ~(1 << *((_DWORD *)a1 + 4));
  *((_DWORD *)a1 + 5) = 0;
  *v19 &= v26;
  RtlReleaseSRWLockExclusive(a1 + 1);
  v27 = v46;
  v28 = *(_DWORD **)&EventDescriptor.Id;
  *(_BYTE *)(a2 + 480) = v20;
  v29 = v47;
  *v27 &= v26;
  *(_QWORD *)(a2 + 472) = v28;
  v30 = *a1;
  v31 = *((_QWORD *)v29 + 1);
  v51 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  memset_0(&UserData, 0, 0xA8u);
  SystemTimeAsFileTime.dwLowDateTime = 0;
  if ( v44 )
  {
    v32 = v44 / 0x3E8 + 5;
    if ( v32 > 0x12C )
      v32 = 300;
  }
  else
  {
    v32 = 300;
  }
  if ( (int)RtlStringCchPrintfW(v73, 0x80u, L"%u - %ws", v41, v31) < 0 )
    v73[127] = 0;
  DWORD1(v48) = v32;
  *(_QWORD *)&v49 = v73;
  *((_QWORD *)&v49 + 1) = &UserData;
  LODWORD(v48) = 1;
  if ( (int)Pdcv2ActivationClientActivate(v30, &v48, v32, v9, v72, 0, &v43, &SystemTimeAsFileTime) < 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v34, v33, v35);
  RtlAcquireSRWLockExclusive(a2 + 48);
  v36 = *(_DWORD *)(a2 + 136);
  if ( (v36 & 0x40) == 0 && !*(_QWORD *)(a2 + 144) )
  {
    *(_QWORD *)(a2 + 144) = v43;
    *(_DWORD *)(a2 + 136) = v36 & 0xFFFFFDFF;
    v43 = 0;
    RtlReleaseSRWLockExclusive(a2 + 48);
    LODWORD(v4) = dword_1800C3098;
    if ( (unsigned int)dword_1800C3098 > 4 )
    {
      LODWORD(v4) = qword_1800C30A8;
      if ( (qword_1800C30A8 & 3) != 0 )
      {
        v4 = qword_1800C30B0 & 3;
        if ( v4 == qword_1800C30B0 )
        {
          SystemTimeAsFileTime.dwLowDateTime = v9;
          p_SystemTimeAsFileTime = &SystemTimeAsFileTime;
          v68 = &v46;
          v64 = v67;
          v46 = v28;
          v71 = 4;
          v69 = 8;
          v65 = 2;
          v37 = *v47;
          v66 = *((_QWORD *)v47 + 1);
          v60 = &v52;
          v38 = -1;
          v67[0] = v37;
          v67[1] = 0;
          v62 = a2;
          v63 = 16;
          v61 = 16;
          while ( v72[++v38] != 0 )
            ;
          v59 = 0;
          v58 = 2 * v38 + 2;
          *(_DWORD *)&EventDescriptor.Level = 4;
          UserData.Ptr = (ULONGLONG)off_1800C30A0;
          v57 = v72;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          EventDescriptor.Keyword = 3;
          UserData.Size = *(unsigned __int16 *)off_1800C30A0;
          v54 = word_1800B47C2;
          UserData.Reserved = 2;
          v55 = 94;
          v56 = 1;
          LODWORD(v4) = EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 9u, &UserData);
        }
      }
    }
    goto LABEL_41;
  }
LABEL_40:
  LODWORD(v4) = RtlReleaseSRWLockExclusive(a2 + 48);
LABEL_41:
  if ( v43 )
    LODWORD(v4) = Pdcv2ActivationClientDeactivate();
  return v4;
}

```

## disassembly

```asm
0x180010c70  push    rbp
0x180010c72  push    rbx
0x180010c73  push    rdi
0x180010c74  push    r12
0x180010c76  lea     rbp, [rsp-338h]
0x180010c7e  sub     rsp, 438h
0x180010c85  mov     rax, cs:__security_cookie
0x180010c8c  xor     rax, rsp
0x180010c8f  mov     [rbp+350h+var_40], rax
0x180010c96  mov     rdi, rdx
0x180010c99  mov     r12, rcx
0x180010c9c  xor     edx, edx; Val
0x180010c9e  lea     rcx, [rbp+350h+var_2D0]; void *
0x180010ca5  mov     r8d, 182h; Size
0x180010cab  call    memset_0
0x180010cb0  xor     ebx, ebx
0x180010cb2  xorps   xmm0, xmm0
0x180010cb5  movups  [rbp+350h+var_390], xmm0
0x180010cb9  mov     [rsp+450h+var_400], rbx
0x180010cbe  cmp     [r12], rbx
0x180010cc2  jz      loc_1800111F5
0x180010cc8  mov     [rsp+450h+var_28], r14
0x180010cd0  lea     rcx, [rdi+30h]
0x180010cd4  mov     [rsp+450h+var_20], r13
0x180010cdc  mov     [rsp+450h+var_30], r15
0x180010ce4  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180010cea  test    byte ptr [rdi+88h], 40h
0x180010cf1  jnz     loc_1800111C3
0x180010cf7  cmp     [rdi+90h], rbx
0x180010cfe  jnz     loc_1800111C3
0x180010d04  mov     rcx, [rdi+40h]
0x180010d08  xorps   xmm0, xmm0
0x180010d0b  mov     [rsp+450h+arg_10], rsi
0x180010d13  test    rcx, rcx
0x180010d16  jz      short loc_180010D1C
0x180010d18  movups  xmm0, xmmword ptr [rcx+20h]
0x180010d1c  movdqa  [rbp+350h+var_390], xmm0
0x180010d21  call    BipWorkItemGetEntryPoint
0x180010d26  mov     rdx, [rdi+40h]
0x180010d2a  mov     [rsp+450h+var_3D8], rax
0x180010d2f  mov     ecx, [rdx+18h]
0x180010d32  bt      ecx, 8
0x180010d36  jnb     short loc_180010D3D
0x180010d38  mov     r15d, ebx
0x180010d3b  jmp     short loc_180010D4C
0x180010d3d  and     ecx, 800h
0x180010d43  neg     ecx
0x180010d45  sbb     r15d, r15d
0x180010d48  add     r15d, 2
0x180010d4c  mov     rax, [rdx+48h]
0x180010d50  mov     ecx, 3
0x180010d55  mov     eax, [rax+248h]
0x180010d5b  mov     [rsp+450h+var_410], eax
0x180010d5f  mov     eax, [rdx+194h]
0x180010d65  mov     [rsp+450h+var_3F8], eax
0x180010d69  mov     rax, [rdx+50h]
0x180010d6d  lea     rdx, [rbp+350h+var_2D0]
0x180010d74  add     rax, 0A0h
0x180010d7a  nop     word ptr [rax+rax+00h]
0x180010d80  lea     rdx, [rdx+80h]
0x180010d87  movups  xmm0, xmmword ptr [rax]
0x180010d8a  lea     rax, [rax+80h]
0x180010d91  movups  xmmword ptr [rdx-80h], xmm0
0x180010d95  movups  xmm1, xmmword ptr [rax-70h]
0x180010d99  movups  xmmword ptr [rdx-70h], xmm1
0x180010d9d  movups  xmm0, xmmword ptr [rax-60h]
0x180010da1  movups  xmmword ptr [rdx-60h], xmm0
0x180010da5  movups  xmm1, xmmword ptr [rax-50h]
0x180010da9  movups  xmmword ptr [rdx-50h], xmm1
0x180010dad  movups  xmm0, xmmword ptr [rax-40h]
0x180010db1  movups  xmmword ptr [rdx-40h], xmm0
0x180010db5  movups  xmm1, xmmword ptr [rax-30h]
0x180010db9  movups  xmmword ptr [rdx-30h], xmm1
0x180010dbd  movups  xmm0, xmmword ptr [rax-20h]
0x180010dc1  movups  xmmword ptr [rdx-20h], xmm0
0x180010dc5  movups  xmm1, xmmword ptr [rax-10h]
0x180010dc9  movups  xmmword ptr [rdx-10h], xmm1
0x180010dcd  sub     rcx, 1
0x180010dd1  jnz     short loc_180010D80
0x180010dd3  movzx   ecx, word ptr [rax]
0x180010dd6  mov     [rdx], cx
0x180010dd9  lea     rcx, [rdi+30h]
0x180010ddd  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180010de3  mov     ecx, [r12+10h]
0x180010de8  mov     rax, gs:58h
0x180010df1  mov     qword ptr [rsp+450h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x180010df6  mov     ebx, 1
0x180010dfb  shl     ebx, cl
0x180010dfd  mov     ecx, cs:_tls_index
0x180010e03  mov     rsi, [rax+rcx*8]
0x180010e07  mov     eax, 4
0x180010e0c  add     rax, rsi
0x180010e0f  mov     [rsp+450h+var_3E0], rax
0x180010e14  cmp     [rax], ebx
0x180010e16  jb      short loc_180010E2C
0x180010e18  call    cs:__imp_IsDebuggerPresent
0x180010e1e  test    eax, eax
0x180010e20  jz      short loc_180010E2C
0x180010e22  lea     rcx, [r12+8]; struct _BI_LOCK *
0x180010e27  call    ?BipSyncDebugPrintLockBug@@YAXPEAU_BI_LOCK@@@Z; BipSyncDebugPrintLockBug(_BI_LOCK *)
0x180010e2c  lea     rcx, [r12+8]
0x180010e31  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180010e37  call    cs:__imp_GetCurrentThreadId
0x180010e3d  mov     [r12+14h], eax
0x180010e42  mov     edx, 8
0x180010e47  add     rdx, rsi
0x180010e4a  mov     eax, 4
0x180010e4f  mov     qword ptr [rsp+450h+EventDescriptor.Id], rdx
0x180010e54  or      [rdx], ebx
0x180010e56  or      [rax+rsi], ebx
0x180010e59  cmp     qword ptr [r12+18h], 0
0x180010e5f  jz      short loc_180010E70
0x180010e61  xor     sil, sil
0x180010e64  lea     rax, [r12+20h]
0x180010e69  mov     ecx, 10h
0x180010e6e  jmp     short loc_180010EC7
0x180010e70  lea     rcx, [rsp+450h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180010e75  call    cs:__imp_GetSystemTimeAsFileTime
0x180010e7b  cmp     qword ptr [r12+28h], 0
0x180010e81  mov     rax, qword ptr [rsp+450h+SystemTimeAsFileTime.dwLowDateTime]
0x180010e86  jz      short loc_180010EAB
0x180010e88  mov     rdx, [r12+30h]
0x180010e8d  test    rdx, rdx
0x180010e90  jnz     short loc_180010E97
0x180010e92  xor     sil, sil
0x180010e95  jmp     short loc_180010EB8
0x180010e97  mov     rcx, rax
0x180010e9a  sub     rcx, rdx
0x180010e9d  cmp     rcx, 4C4B40h
0x180010ea4  jnb     short loc_180010EAB
0x180010ea6  xor     sil, sil
0x180010ea9  jmp     short loc_180010EB8
0x180010eab  inc     qword ptr [r12+20h]
0x180010eb0  mov     sil, 1
0x180010eb3  mov     [r12+28h], rax
0x180010eb8  mov     rdx, qword ptr [rsp+450h+EventDescriptor.Id]
0x180010ebd  lea     rcx, [r12+20h]
0x180010ec2  mov     eax, 10h
0x180010ec7  mov     r8, [r12+20h]
0x180010ecc  mov     ebx, 1
0x180010ed1  inc     qword ptr [r12+18h]
0x180010ed6  mov     qword ptr [rsp+450h+EventDescriptor.Id], r8
0x180010edb  xor     r8d, r8d
0x180010ede  mov     [rcx+rax], r8
0x180010ee2  mov     ecx, [r12+10h]
0x180010ee7  shl     ebx, cl
0x180010ee9  lea     rcx, [r12+8]
0x180010eee  not     ebx
0x180010ef0  mov     [r12+14h], r8d
0x180010ef5  and     [rdx], ebx
0x180010ef7  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180010efd  mov     rax, [rsp+450h+var_3E0]
0x180010f02  lea     rcx, [rbp+350h+var_380]; void *
0x180010f06  mov     r13, qword ptr [rsp+450h+EventDescriptor.Id]
0x180010f0b  xorps   xmm0, xmm0
0x180010f0e  mov     [rdi+1E0h], sil
0x180010f15  xor     edx, edx; Val
0x180010f17  mov     rsi, [rsp+450h+var_3D8]
0x180010f1c  mov     r8d, 0A8h; Size
0x180010f22  and     [rax], ebx
0x180010f24  xor     eax, eax
0x180010f26  mov     [rdi+1D8h], r13
0x180010f2d  mov     r12, [r12]
0x180010f31  mov     rsi, [rsi+8]
0x180010f35  mov     [rbp+350h+var_3A0], rax
0x180010f39  movups  [rbp+350h+var_3D0], xmm0
0x180010f3d  movups  [rbp+350h+var_3C0], xmm0
0x180010f41  movups  [rbp+350h+var_3B0], xmm0
0x180010f45  call    memset_0
0x180010f4a  mov     ecx, [rsp+450h+var_3F8]
0x180010f4e  mov     [rsp+450h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180010f56  test    ecx, ecx
0x180010f58  jz      short loc_180010F73
0x180010f5a  mov     eax, 10624DD3h
0x180010f5f  mul     ecx
0x180010f61  mov     eax, 12Ch
0x180010f66  shr     edx, 6
0x180010f69  lea     ebx, [rdx+5]
0x180010f6c  cmp     ebx, eax
0x180010f6e  cmova   ebx, eax
0x180010f71  jmp     short loc_180010F78
0x180010f73  mov     ebx, 12Ch
0x180010f78  mov     r9d, [rsp+450h+var_410]
0x180010f7d  lea     r8, aUWs; "%u - %ws"
0x180010f84  mov     edx, 80h; unsigned __int64
0x180010f89  mov     qword ptr [rsp+450h+UserDataCount], rsi
0x180010f8e  lea     rcx, [rbp+350h+var_140]; unsigned __int16 *
0x180010f95  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010f9a  mov     rsi, [rsp+450h+arg_10]
0x180010fa2  test    eax, eax
0x180010fa4  jns     short loc_180010FAF
0x180010fa6  xor     eax, eax
0x180010fa8  mov     [rbp+350h+var_42], ax
0x180010faf  lea     rax, [rbp+350h+var_140]
0x180010fb6  mov     dword ptr [rbp+350h+var_3D0+4], ebx
0x180010fb9  mov     qword ptr [rbp+350h+var_3C0], rax
0x180010fbd  lea     rdx, [rbp+350h+var_3D0]
0x180010fc1  lea     rax, [rbp+350h+var_380]
0x180010fc5  mov     r8d, ebx
0x180010fc8  mov     qword ptr [rbp+350h+var_3C0+8], rax
0x180010fcc  xor     ebx, ebx
0x180010fce  lea     rax, [rsp+450h+SystemTimeAsFileTime]
0x180010fd3  mov     dword ptr [rbp+350h+var_3D0], 1
0x180010fda  mov     [rsp+450h+var_418], rax
0x180010fdf  mov     r9d, r15d
0x180010fe2  lea     rax, [rsp+450h+var_400]
0x180010fe7  mov     rcx, r12
0x180010fea  mov     [rsp+450h+var_420], rax
0x180010fef  lea     rax, [rbp+350h+var_2D0]
0x180010ff6  mov     dword ptr [rsp+450h+UserData], ebx
0x180010ffa  mov     qword ptr [rsp+450h+UserDataCount], rax
0x180010fff  call    cs:__imp_Pdcv2ActivationClientActivate
0x180011005  test    eax, eax
0x180011007  jns     short loc_18001100E
0x180011009  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001100e  lea     rcx, [rdi+30h]
0x180011012  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180011018  mov     edx, [rdi+88h]
0x18001101e  test    dl, 40h
0x180011021  jnz     loc_1800111C3
0x180011027  cmp     [rdi+90h], rbx
0x18001102e  jnz     loc_1800111C3
0x180011034  mov     rax, [rsp+450h+var_400]
0x180011039  lea     rcx, [rdi+30h]
0x18001103d  btr     edx, 9
0x180011041  mov     [rdi+90h], rax
0x180011048  mov     [rdi+88h], edx
0x18001104e  mov     [rsp+450h+var_400], rbx
0x180011053  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180011059  mov     eax, cs:dword_1800C3098
0x18001105f  cmp     eax, 4
0x180011062  jbe     loc_1800111CD
0x180011068  mov     rcx, cs:qword_1800C30B0
0x18001106f  mov     rax, cs:qword_1800C30A8
0x180011076  test    al, 3
0x180011078  jz      loc_1800111CD
0x18001107e  mov     rax, rcx
0x180011081  and     eax, 3
0x180011084  cmp     rax, rcx
0x180011087  jnz     loc_1800111CD
0x18001108d  lea     rax, [rsp+450h+SystemTimeAsFileTime]
0x180011092  mov     [rsp+450h+SystemTimeAsFileTime.dwLowDateTime], r15d
0x180011097  mov     [rbp+350h+var_300], rax
0x18001109b  lea     rax, [rsp+450h+var_3E0]
0x1800110a0  mov     [rbp+350h+var_310], rax
0x1800110a4  lea     rax, [rbp+350h+var_318]
0x1800110a8  mov     [rbp+350h+var_330], rax
0x1800110ac  mov     rax, [rsp+450h+var_3D8]
0x1800110b1  mov     [rsp+450h+var_3E0], r13
0x1800110b6  mov     [rbp+350h+var_2F8], 4
0x1800110be  mov     [rbp+350h+var_308], 8
0x1800110c6  mov     [rbp+350h+var_328], 2
0x1800110ce  movzx   ecx, word ptr [rax]
0x1800110d1  mov     rax, [rax+8]
0x1800110d5  mov     [rbp+350h+var_320], rax
0x1800110d9  lea     rax, [rbp+350h+var_390]
0x1800110dd  mov     [rbp+350h+var_350], rax
0x1800110e1  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800110e8  mov     [rbp+350h+var_318], ecx
0x1800110eb  lea     rcx, [rbp+350h+var_2D0]
0x1800110f2  mov     [rbp+350h+var_314], ebx
0x1800110f5  mov     [rbp+350h+var_340], rdi
0x1800110f9  mov     [rbp+350h+var_338], 10h
0x180011101  mov     [rbp+350h+var_348], 10h
0x180011109  nop     dword ptr [rax+00000000h]
0x180011110  cmp     [rcx+rax*2+2], bx
0x180011115  lea     rax, [rax+1]
0x180011119  jnz     short loc_180011110
0x18001111b  lea     eax, ds:2[rax*2]
0x180011122  mov     [rbp+350h+var_354], ebx
0x180011125  mov     [rbp+350h+var_358], eax
0x180011128  lea     rcx, [rbp+350h+var_2D0]
0x18001112f  movzx   eax, cs:word_1800B47B8
0x180011136  lea     rdx, [rsp+450h+EventDescriptor]; EventDescriptor
0x18001113b  mov     dword ptr [rsp+450h+EventDescriptor.Level], eax
0x18001113f  xor     r9d, r9d; RelatedActivityId
0x180011142  mov     rax, cs:off_1800C30A0
0x180011149  xor     r8d, r8d; ActivityId
0x18001114c  mov     [rbp+350h+var_380.Ptr], rax
0x180011150  mov     [rbp+350h+var_360], rcx
0x180011154  lea     rcx, _TraceLoggingMetadata
0x18001115b  mov     dword ptr [rsp+450h+EventDescriptor.Id], 0B000000h
0x180011163  mov     [rsp+450h+EventDescriptor.Keyword], 3
0x18001116c  movzx   eax, word ptr [rax]
0x18001116f  mov     [rbp+350h+var_380.Size], eax
0x180011172  lea     rax, word_1800B47C2
0x180011179  mov     [rbp+350h+var_370], rax
0x18001117d  lea     rax, _TraceLoggingMetadataEnd
0x180011184  sub     eax, ecx
0x180011186  mov     dword ptr [rbp+350h+var_380.0Ch], 2
0x18001118d  mov     [rbp+350h+var_368], 5Eh ; '^'
0x180011194  mov     [rbp+350h+var_364], 1
0x18001119b  mov     [rsp+450h+var_410], eax
0x18001119f  mov     eax, [rsp+450h+var_410]
0x1800111a3  mov     rcx, cs:RegHandle; RegHandle
0x1800111aa  lea     rax, [rbp+350h+var_380]
0x1800111ae  mov     [rsp+450h+UserData], rax; UserData
0x1800111b3  mov     [rsp+450h+UserDataCount], 9; UserDataCount
0x1800111bb  call    cs:__imp_EventWriteTransfer
0x1800111c1  jmp     short loc_1800111CD
  ... truncated ...
```
