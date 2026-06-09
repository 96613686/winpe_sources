# KspDebugProvider::KspDebugActivity::Stop(char const *)

- ea: `0x18001f2f0`
- end: `0x18001fa01`
- name: `?Stop@KspDebugActivity@KspDebugProvider@@QEAAXPEBD@Z`
- size: `1809`
- prototype: `void __fastcall(KspDebugProvider::KspDebugActivity *__hidden this, const char *)`
- caller_count: `21`
- callee_count: `4`
- tags: ``

## callers

- `0x180018b00`
- `0x18001c410`
- `0x18001c980`
- `0x18001cf60`
- `0x18001d110`
- `0x18001d590`
- `0x18001dbd0`
- `0x18001fa10`
- `0x18001ffe0`
- `0x1800204a0`
- `0x180027cf0`
- `0x180037b20`
- `0x1800388a0`
- `0x180038aa0`
- `0x18003a340`
- `0x180057b60`
- `0x180057d38`
- `0x1800749b4`
- `0x18007bde0`
- `0x18007d980`
- `0x18007db80`

## callees

- `0x18001f2f0`
- `0x18003cf80`
- `0x18004d1ac`
- `0x1800764d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f381`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f3a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f3c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f84c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f86d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f88d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f381`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f3a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f3c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f84c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f86d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f88d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001f363`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001f82e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001f363`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001f82e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f8ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f8ba`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001f7ff`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001f9c6`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001f7ff`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001f9c6`

## pseudocode

```c
void __fastcall KspDebugProvider::KspDebugActivity::Stop(KspDebugProvider::KspDebugActivity *this, const char *a2)
{
  __int64 v2; // rdi
  int v5; // eax
  int *v6; // rdi
  RTL_SRWLOCK *v7; // rbx
  RTL_SRWLOCK *v8; // rbx
  const unsigned __int16 *v9; // rdx
  int *v10; // r8
  const unsigned __int16 *v11; // r9
  int *v12; // r10
  const unsigned __int16 *v13; // r11
  const unsigned __int16 *v14; // rbx
  int *v15; // r15
  const unsigned __int16 *v16; // r12
  const unsigned __int16 *v17; // r13
  int v18; // eax
  __int64 v19; // rdi
  __int64 v20; // rax
  __int64 v21; // rcx
  int v22; // ecx
  __int64 v23; // rcx
  int v24; // ecx
  __int64 v25; // rcx
  bool v26; // zf
  int v27; // ecx
  __int64 v28; // rcx
  int v29; // ecx
  __int64 v30; // rcx
  int v31; // ecx
  __int64 v32; // rcx
  int v33; // ecx
  __int64 v34; // rcx
  int v35; // ecx
  __int64 v36; // rcx
  int v37; // ecx
  __int64 v38; // rcx
  int v39; // ecx
  int v40; // eax
  PSRWLOCK v41; // rcx
  RTL_SRWLOCK *v42; // rbx
  __int64 v43; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v45; // r8
  __int64 v46; // rax
  int v47; // eax
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v49; // [rsp+38h] [rbp-C8h] BYREF
  PSRWLOCK v50; // [rsp+40h] [rbp-C0h] BYREF
  PSRWLOCK v51; // [rsp+48h] [rbp-B8h] BYREF
  int v52; // [rsp+50h] [rbp-B0h] BYREF
  int v53; // [rsp+54h] [rbp-ACh] BYREF
  int v54; // [rsp+58h] [rbp-A8h] BYREF
  int v55; // [rsp+5Ch] [rbp-A4h] BYREF
  int v56; // [rsp+60h] [rbp-A0h] BYREF
  int v57; // [rsp+64h] [rbp-9Ch] BYREF
  PSRWLOCK v58; // [rsp+68h] [rbp-98h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+70h] [rbp-90h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v60; // [rsp+80h] [rbp-80h] BYREF
  __int16 *v61; // [rsp+90h] [rbp-70h]
  int v62; // [rsp+98h] [rbp-68h]
  int v63; // [rsp+9Ch] [rbp-64h]
  PSRWLOCK *v64; // [rsp+A0h] [rbp-60h]
  __int64 v65; // [rsp+A8h] [rbp-58h]
  PSRWLOCK *v66; // [rsp+B0h] [rbp-50h]
  __int64 v67; // [rsp+B8h] [rbp-48h]
  PSRWLOCK *p_SRWLock; // [rsp+C0h] [rbp-40h]
  __int64 v69; // [rsp+C8h] [rbp-38h]
  const char *v70; // [rsp+D0h] [rbp-30h]
  int v71; // [rsp+D8h] [rbp-28h]
  int v72; // [rsp+DCh] [rbp-24h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+E0h] [rbp-20h] BYREF
  char *v74; // [rsp+F0h] [rbp-10h]
  int v75; // [rsp+F8h] [rbp-8h]
  int v76; // [rsp+FCh] [rbp-4h]
  PSRWLOCK *v77; // [rsp+100h] [rbp+0h]
  __int64 v78; // [rsp+108h] [rbp+8h]
  PSRWLOCK *v79; // [rsp+110h] [rbp+10h]
  __int64 v80; // [rsp+118h] [rbp+18h]
  PSRWLOCK *v81; // [rsp+120h] [rbp+20h]
  __int64 v82; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v83; // [rsp+130h] [rbp+30h]
  int v84; // [rsp+138h] [rbp+38h]
  int v85; // [rsp+13Ch] [rbp+3Ch]
  unsigned int *v86; // [rsp+140h] [rbp+40h]
  __int64 v87; // [rsp+148h] [rbp+48h]
  const unsigned __int16 *v88; // [rsp+150h] [rbp+50h]
  int v89; // [rsp+158h] [rbp+58h]
  int v90; // [rsp+15Ch] [rbp+5Ch]
  int *v91; // [rsp+160h] [rbp+60h]
  __int64 v92; // [rsp+168h] [rbp+68h]
  int *v93; // [rsp+170h] [rbp+70h]
  int v94; // [rsp+178h] [rbp+78h]
  int v95; // [rsp+17Ch] [rbp+7Ch]
  int *v96; // [rsp+180h] [rbp+80h]
  __int64 v97; // [rsp+188h] [rbp+88h]
  const unsigned __int16 *v98; // [rsp+190h] [rbp+90h]
  int v99; // [rsp+198h] [rbp+98h]
  int v100; // [rsp+19Ch] [rbp+9Ch]
  int *v101; // [rsp+1A0h] [rbp+A0h]
  __int64 v102; // [rsp+1A8h] [rbp+A8h]
  const unsigned __int16 *v103; // [rsp+1B0h] [rbp+B0h]
  int v104; // [rsp+1B8h] [rbp+B8h]
  int v105; // [rsp+1BCh] [rbp+BCh]
  int *v106; // [rsp+1C0h] [rbp+C0h]
  int v107; // [rsp+1C8h] [rbp+C8h]
  int v108; // [rsp+1CCh] [rbp+CCh]
  int *v109; // [rsp+1D0h] [rbp+D0h]
  __int64 v110; // [rsp+1D8h] [rbp+D8h]
  const unsigned __int16 *v111; // [rsp+1E0h] [rbp+E0h]
  int v112; // [rsp+1E8h] [rbp+E8h]
  int v113; // [rsp+1ECh] [rbp+ECh]
  int *v114; // [rsp+1F0h] [rbp+F0h]
  int v115; // [rsp+1F8h] [rbp+F8h]
  int v116; // [rsp+1FCh] [rbp+FCh]
  int *v117; // [rsp+200h] [rbp+100h]
  __int64 v118; // [rsp+208h] [rbp+108h]
  int *v119; // [rsp+210h] [rbp+110h]
  __int64 v120; // [rsp+218h] [rbp+118h]
  const unsigned __int16 *v121; // [rsp+220h] [rbp+120h]
  int v122; // [rsp+228h] [rbp+128h]
  int v123; // [rsp+22Ch] [rbp+12Ch]
  const char *v124; // [rsp+230h] [rbp+130h]
  int v125; // [rsp+238h] [rbp+138h]
  int v126; // [rsp+23Ch] [rbp+13Ch]

  v2 = *((_QWORD *)this + 34);
  v5 = *(_DWORD *)(v2 + 72);
  if ( v5 < 0 && (v6 = (int *)(v2 + 80), v5 == v6[2]) )
  {
    v7 = (RTL_SRWLOCK *)*((_QWORD *)this + 35);
    if ( v6 )
    {
      if ( v7 )
      {
        v8 = v7 + 33;
        AcquireSRWLockExclusive(v8);
        SRWLock = 0;
        **((_DWORD **)this + 34) = 2;
        if ( v8 )
          ReleaseSRWLockExclusive(v8);
      }
      else
      {
        v50 = 0;
        **((_DWORD **)this + 34) = 2;
      }
      SRWLock = (PSRWLOCK)*((_QWORD *)KspDebugProvider::Instance() + 1);
      if ( LODWORD(SRWLock->Ptr) > 5 )
      {
        v9 = (const unsigned __int16 *)*((_QWORD *)v6 + 6);
        v10 = (int *)*((_QWORD *)v6 + 15);
        v11 = (const unsigned __int16 *)*((_QWORD *)v6 + 14);
        v12 = (int *)*((_QWORD *)v6 + 12);
        v13 = (const unsigned __int16 *)*((_QWORD *)v6 + 11);
        v14 = (const unsigned __int16 *)*((_QWORD *)v6 + 9);
        v15 = (int *)*((_QWORD *)v6 + 3);
        v16 = (const unsigned __int16 *)*((_QWORD *)v6 + 16);
        v17 = (const unsigned __int16 *)*((_QWORD *)v6 + 7);
        v52 = v6[17];
        v53 = v6[4];
        v54 = v6[26];
        v55 = v6[20];
        v56 = v6[8];
        v57 = *v6;
        v49 = v6[16];
        v18 = v6[2];
        v19 = *((_QWORD *)this + 34);
        LODWORD(v50) = v18;
        v20 = -1;
        v58 = (PSRWLOCK)0x1000000;
        v51 = 0;
        if ( a2 )
        {
          v21 = -1;
          do
            ++v21;
          while ( a2[v21] );
          v22 = v21 + 1;
        }
        else
        {
          a2 = (const char *)&word_1800DBB72;
          v22 = 1;
        }
        v124 = a2;
        v125 = v22;
        v126 = 0;
        if ( v9 )
        {
          v23 = -1;
          do
            ++v23;
          while ( *((_BYTE *)v9 + v23) );
          v24 = v23 + 1;
        }
        else
        {
          v9 = &word_1800DBB72;
          v24 = 1;
        }
        v122 = v24;
        v119 = &v52;
        v117 = &v53;
        v121 = v9;
        v123 = 0;
        v120 = 4;
        v118 = 4;
        if ( v10 )
        {
          v25 = -1;
          do
            v26 = *((_WORD *)v10 + ++v25) == 0;
          while ( !v26 );
          v27 = 2 * v25 + 2;
        }
        else
        {
          v10 = &dword_1800DB714;
          v27 = 2;
        }
        v114 = v10;
        v115 = v27;
        v116 = 0;
        if ( v11 )
        {
          v28 = -1;
          do
            ++v28;
          while ( *((_BYTE *)v11 + v28) );
          v29 = v28 + 1;
        }
        else
        {
          v11 = &word_1800DBB72;
          v29 = 1;
        }
        v112 = v29;
        v109 = &v54;
        v111 = v11;
        v113 = 0;
        v110 = 4;
        if ( v12 )
        {
          v30 = -1;
          do
            v26 = *((_WORD *)v12 + ++v30) == 0;
          while ( !v26 );
          v31 = 2 * v30 + 2;
        }
        else
        {
          v12 = &dword_1800DB714;
          v31 = 2;
        }
        v106 = v12;
        v107 = v31;
        v108 = 0;
        if ( v13 )
        {
          v32 = -1;
          do
            ++v32;
          while ( *((_BYTE *)v13 + v32) );
          v33 = v32 + 1;
        }
        else
        {
          v13 = &word_1800DBB72;
          v33 = 1;
        }
        v104 = v33;
        v101 = &v55;
        v103 = v13;
        v105 = 0;
        v102 = 4;
        if ( v14 )
        {
          v34 = -1;
          do
            ++v34;
          while ( *((_BYTE *)v14 + v34) );
          v35 = v34 + 1;
        }
        else
        {
          v14 = &word_1800DBB72;
          v35 = 1;
        }
        v99 = v35;
        v96 = &v56;
        v98 = v14;
        v100 = 0;
        v97 = 4;
        if ( v15 )
        {
          v36 = -1;
          do
            v26 = *((_WORD *)v15 + ++v36) == 0;
          while ( !v26 );
          v37 = 2 * v36 + 2;
        }
        else
        {
          v15 = &dword_1800DB714;
          v37 = 2;
        }
        v94 = v37;
        v91 = &v57;
        v93 = v15;
        v95 = 0;
        v92 = 4;
        if ( v16 )
        {
          v38 = -1;
          do
            ++v38;
          while ( *((_BYTE *)v16 + v38) );
          v39 = v38 + 1;
        }
        else
        {
          v16 = &word_1800DBB72;
          v39 = 1;
        }
        v89 = v39;
        v88 = v16;
        v86 = &v49;
        v90 = 0;
        v87 = 4;
        if ( v17 )
        {
          do
            ++v20;
          while ( *((_BYTE *)v17 + v20) );
          v40 = v20 + 1;
        }
        else
        {
          v17 = &word_1800DBB72;
          v40 = 1;
        }
        v41 = SRWLock;
        v84 = v40;
        v83 = v17;
        v81 = &v50;
        v85 = 0;
        v79 = &v58;
        v77 = &v51;
        *(_DWORD *)&EventDescriptor.Level = 517;
        UserData.Ptr = (ULONGLONG)SRWLock[1].Ptr;
        v82 = 4;
        v80 = 8;
        v78 = 8;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 0;
        UserData.Size = *(unsigned __int16 *)UserData.Ptr;
        v74 = byte_1800F622D;
        UserData.Reserved = 2;
        v75 = 329;
        v76 = 1;
        LODWORD(SRWLock) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer((REGHANDLE)v41[4].Ptr, &EventDescriptor, (LPCGUID)(v19 + 8), 0, 0x16u, &UserData);
      }
      goto LABEL_71;
    }
  }
  else
  {
    v7 = (RTL_SRWLOCK *)*((_QWORD *)this + 35);
  }
  if ( v7 )
  {
    v42 = v7 + 33;
    AcquireSRWLockExclusive(v42);
    v51 = 0;
    **((_DWORD **)this + 34) = 2;
    if ( v42 )
      ReleaseSRWLockExclusive(v42);
  }
  else
  {
    v58 = 0;
    **((_DWORD **)this + 34) = 2;
  }
  v43 = *((_QWORD *)KspDebugProvider::Instance() + 1);
  if ( *(_DWORD *)v43 > 5u )
  {
    CurrentThreadId = GetCurrentThreadId();
    v45 = *((_QWORD *)this + 34);
    LODWORD(SRWLock) = CurrentThreadId;
    LODWORD(v50) = *(_DWORD *)(v45 + 72);
    v51 = 0;
    if ( a2 )
    {
      v46 = -1;
      do
        ++v46;
      while ( a2[v46] );
      v47 = v46 + 1;
    }
    else
    {
      a2 = (const char *)&word_1800DBB72;
      v47 = 1;
    }
    v71 = v47;
    v70 = a2;
    p_SRWLock = &SRWLock;
    v72 = 0;
    v66 = &v50;
    v69 = 4;
    v64 = &v51;
    *(_DWORD *)&EventDescriptor.Level = 517;
    v60.Ptr = *(_QWORD *)(v43 + 8);
    v67 = 4;
    v65 = 8;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    v60.Size = *(unsigned __int16 *)v60.Ptr;
    v61 = word_1800F6382;
    v60.Reserved = 2;
    v62 = 79;
    v63 = 1;
    v49 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(*(_QWORD *)(v43 + 32), &EventDescriptor, (LPCGUID)(v45 + 8), 0, 6u, &v60);
  }
LABEL_71:
  wil::ActivityBase<KspDebugProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x18001f2f0  mov     [rsp-8+arg_18], rbx
0x18001f2f5  push    rbp
0x18001f2f6  push    rsi
0x18001f2f7  push    rdi
0x18001f2f8  push    r14
0x18001f2fa  push    r15
0x18001f2fc  lea     rbp, [rsp-150h]
0x18001f304  sub     rsp, 250h
0x18001f30b  mov     rax, cs:__security_cookie
0x18001f312  xor     rax, rsp
0x18001f315  mov     [rbp+170h+var_30], rax
0x18001f31c  mov     rdi, [rcx+110h]
0x18001f323  xor     r15d, r15d
0x18001f326  mov     rsi, rdx
0x18001f329  mov     r14, rcx
0x18001f32c  mov     eax, [rdi+48h]
0x18001f32f  test    eax, eax
0x18001f331  jns     loc_18001F818
0x18001f337  add     rdi, 50h ; 'P'
0x18001f33b  cmp     eax, [rdi+8]
0x18001f33e  jnz     loc_18001F818
0x18001f344  mov     rbx, [rcx+118h]
0x18001f34b  test    rdi, rdi
0x18001f34e  jz      loc_18001F81F
0x18001f354  test    rbx, rbx
0x18001f357  jz      short loc_18001F3B0
0x18001f359  add     rbx, 108h
0x18001f360  mov     rcx, rbx; SRWLock
0x18001f363  call    cs:__imp_AcquireSRWLockExclusive
0x18001f36a  nop     dword ptr [rax+rax+00h]
0x18001f36f  lea     rax, [rsp+270h+SRWLock]
0x18001f374  mov     [rax], r15
0x18001f377  mov     rcx, [rsp+270h+SRWLock]; SRWLock
0x18001f37c  test    rcx, rcx
0x18001f37f  jz      short loc_18001F38D
0x18001f381  call    cs:__imp_ReleaseSRWLockExclusive
0x18001f388  nop     dword ptr [rax+rax+00h]
0x18001f38d  mov     rax, [r14+110h]
0x18001f394  mov     dword ptr [rax], 2
0x18001f39a  test    rbx, rbx
0x18001f39d  jz      short loc_18001F3DB
0x18001f39f  mov     rcx, rbx; SRWLock
0x18001f3a2  call    cs:__imp_ReleaseSRWLockExclusive
0x18001f3a9  nop     dword ptr [rax+rax+00h]
0x18001f3ae  jmp     short loc_18001F3DB
0x18001f3b0  lea     rax, [rsp+270h+var_230]
0x18001f3b5  mov     [rax], r15
0x18001f3b8  mov     rcx, [rsp+270h+var_230]; SRWLock
0x18001f3bd  test    rcx, rcx
0x18001f3c0  jz      short loc_18001F3CE
0x18001f3c2  call    cs:__imp_ReleaseSRWLockExclusive
0x18001f3c9  nop     dword ptr [rax+rax+00h]
0x18001f3ce  mov     rax, [r14+110h]
0x18001f3d5  mov     dword ptr [rax], 2
0x18001f3db  call    ?Instance@KspDebugProvider@@KAPEAV1@XZ; KspDebugProvider::Instance(void)
0x18001f3e0  mov     rax, [rax+8]
0x18001f3e4  mov     [rsp+270h+SRWLock], rax
0x18001f3e9  mov     eax, [rax]
0x18001f3eb  cmp     eax, 5
0x18001f3ee  jbe     loc_18001F9D2
0x18001f3f4  mov     [rsp+270h+arg_8], r12
0x18001f3fc  mov     [rsp+270h+arg_10], r13
0x18001f404  mov     eax, [rdi+44h]
0x18001f407  mov     rdx, [rdi+30h]
0x18001f40b  mov     r8, [rdi+78h]
0x18001f40f  mov     r9, [rdi+70h]
0x18001f413  mov     r10, [rdi+60h]
0x18001f417  mov     r11, [rdi+58h]
0x18001f41b  mov     rbx, [rdi+48h]
0x18001f41f  mov     r15, [rdi+18h]
0x18001f423  mov     r12, [rdi+80h]
0x18001f42a  mov     r13, [rdi+38h]
0x18001f42e  mov     [rsp+270h+var_220], eax
0x18001f432  mov     eax, [rdi+10h]
0x18001f435  mov     [rsp+270h+var_21C], eax
0x18001f439  mov     eax, [rdi+68h]
0x18001f43c  mov     [rsp+270h+var_218], eax
0x18001f440  mov     eax, [rdi+50h]
0x18001f443  mov     [rsp+270h+var_214], eax
0x18001f447  mov     eax, [rdi+20h]
0x18001f44a  mov     [rsp+270h+var_210], eax
0x18001f44e  mov     eax, [rdi]
0x18001f450  mov     [rsp+270h+var_20C], eax
0x18001f454  mov     eax, [rdi+40h]
0x18001f457  mov     [rsp+270h+var_238], eax
0x18001f45b  mov     eax, [rdi+8]
0x18001f45e  mov     rdi, [r14+110h]
0x18001f465  mov     dword ptr [rsp+270h+var_230], eax
0x18001f469  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001f470  mov     [rsp+270h+var_208], 1000000h
0x18001f479  mov     [rsp+270h+var_228], 0
0x18001f482  test    rsi, rsi
0x18001f485  jz      short loc_18001F49D
0x18001f487  mov     rcx, rax
0x18001f48a  nop     word ptr [rax+rax+00h]
0x18001f490  inc     rcx
0x18001f493  cmp     byte ptr [rsi+rcx], 0
0x18001f497  jnz     short loc_18001F490
0x18001f499  inc     ecx
0x18001f49b  jmp     short loc_18001F4A9
0x18001f49d  lea     rsi, word_1800DBB72
0x18001f4a4  mov     ecx, 1
0x18001f4a9  mov     [rbp+170h+var_40], rsi
0x18001f4b0  xor     esi, esi
0x18001f4b2  mov     [rbp+170h+var_38], ecx
0x18001f4b8  mov     [rbp+170h+var_34], esi
0x18001f4be  test    rdx, rdx
0x18001f4c1  jz      short loc_18001F4D3
0x18001f4c3  mov     rcx, rax
0x18001f4c6  inc     rcx
0x18001f4c9  cmp     [rdx+rcx], sil
0x18001f4cd  jnz     short loc_18001F4C6
0x18001f4cf  inc     ecx
0x18001f4d1  jmp     short loc_18001F4DF
0x18001f4d3  lea     rdx, word_1800DBB72
0x18001f4da  mov     ecx, 1
0x18001f4df  mov     [rbp+170h+var_48], ecx
0x18001f4e5  lea     rcx, [rsp+270h+var_220]
0x18001f4ea  mov     [rbp+170h+var_60], rcx
0x18001f4f1  lea     rcx, [rsp+270h+var_21C]
0x18001f4f6  mov     [rbp+170h+var_70], rcx
0x18001f4fd  mov     [rbp+170h+var_50], rdx
0x18001f504  mov     [rbp+170h+var_44], esi
0x18001f50a  mov     [rbp+170h+var_58], 4
0x18001f515  mov     [rbp+170h+var_68], 4
0x18001f520  test    r8, r8
0x18001f523  jz      short loc_18001F545
0x18001f525  mov     rcx, rax
0x18001f528  nop     dword ptr [rax+rax+00000000h]
0x18001f530  cmp     [r8+rcx*2+2], si
0x18001f536  lea     rcx, [rcx+1]
0x18001f53a  jnz     short loc_18001F530
0x18001f53c  lea     ecx, ds:2[rcx*2]
0x18001f543  jmp     short loc_18001F551
0x18001f545  lea     r8, dword_1800DB714
0x18001f54c  mov     ecx, 2
0x18001f551  mov     [rbp+170h+var_80], r8
0x18001f558  mov     [rbp+170h+var_78], ecx
0x18001f55e  mov     [rbp+170h+var_74], esi
0x18001f564  test    r9, r9
0x18001f567  jz      short loc_18001F57D
0x18001f569  mov     rcx, rax
0x18001f56c  nop     dword ptr [rax+00h]
0x18001f570  inc     rcx
0x18001f573  cmp     [r9+rcx], sil
0x18001f577  jnz     short loc_18001F570
0x18001f579  inc     ecx
0x18001f57b  jmp     short loc_18001F589
0x18001f57d  lea     r9, word_1800DBB72
0x18001f584  mov     ecx, 1
0x18001f589  mov     [rbp+170h+var_88], ecx
0x18001f58f  lea     rcx, [rsp+270h+var_218]
0x18001f594  mov     [rbp+170h+var_A0], rcx
0x18001f59b  mov     [rbp+170h+var_90], r9
0x18001f5a2  mov     [rbp+170h+var_84], esi
0x18001f5a8  mov     [rbp+170h+var_98], 4
0x18001f5b3  test    r10, r10
0x18001f5b6  jz      short loc_18001F5D5
0x18001f5b8  mov     rcx, rax
0x18001f5bb  nop     dword ptr [rax+rax+00h]
0x18001f5c0  cmp     [r10+rcx*2+2], si
0x18001f5c6  lea     rcx, [rcx+1]
0x18001f5ca  jnz     short loc_18001F5C0
0x18001f5cc  lea     ecx, ds:2[rcx*2]
0x18001f5d3  jmp     short loc_18001F5E1
0x18001f5d5  lea     r10, dword_1800DB714
0x18001f5dc  mov     ecx, 2
0x18001f5e1  mov     [rbp+170h+var_B0], r10
0x18001f5e8  mov     [rbp+170h+var_A8], ecx
0x18001f5ee  mov     [rbp+170h+var_A4], esi
0x18001f5f4  test    r11, r11
0x18001f5f7  jz      short loc_18001F60D
0x18001f5f9  mov     rcx, rax
0x18001f5fc  nop     dword ptr [rax+00h]
0x18001f600  inc     rcx
0x18001f603  cmp     [r11+rcx], sil
0x18001f607  jnz     short loc_18001F600
0x18001f609  inc     ecx
0x18001f60b  jmp     short loc_18001F619
0x18001f60d  lea     r11, word_1800DBB72
0x18001f614  mov     ecx, 1
0x18001f619  mov     [rbp+170h+var_B8], ecx
0x18001f61f  lea     rcx, [rsp+270h+var_214]
0x18001f624  mov     [rbp+170h+var_D0], rcx
0x18001f62b  mov     [rbp+170h+var_C0], r11
0x18001f632  mov     [rbp+170h+var_B4], esi
0x18001f638  mov     [rbp+170h+var_C8], 4
0x18001f643  test    rbx, rbx
0x18001f646  jz      short loc_18001F65D
0x18001f648  mov     rcx, rax
0x18001f64b  nop     dword ptr [rax+rax+00h]
0x18001f650  inc     rcx
0x18001f653  cmp     [rbx+rcx], sil
0x18001f657  jnz     short loc_18001F650
0x18001f659  inc     ecx
0x18001f65b  jmp     short loc_18001F669
0x18001f65d  lea     rbx, word_1800DBB72
0x18001f664  mov     ecx, 1
0x18001f669  mov     [rbp+170h+var_D8], ecx
0x18001f66f  lea     rcx, [rsp+270h+var_210]
0x18001f674  mov     [rbp+170h+var_F0], rcx
0x18001f67b  mov     [rbp+170h+var_E0], rbx
0x18001f682  mov     [rbp+170h+var_D4], esi
0x18001f688  mov     [rbp+170h+var_E8], 4
0x18001f693  test    r15, r15
0x18001f696  jz      short loc_18001F6B5
0x18001f698  mov     rcx, rax
0x18001f69b  nop     dword ptr [rax+rax+00h]
0x18001f6a0  cmp     [r15+rcx*2+2], si
0x18001f6a6  lea     rcx, [rcx+1]
0x18001f6aa  jnz     short loc_18001F6A0
0x18001f6ac  lea     ecx, ds:2[rcx*2]
0x18001f6b3  jmp     short loc_18001F6C1
0x18001f6b5  lea     r15, dword_1800DB714
0x18001f6bc  mov     ecx, 2
0x18001f6c1  mov     [rbp+170h+var_F8], ecx
0x18001f6c4  lea     rcx, [rsp+270h+var_20C]
0x18001f6c9  mov     [rbp+170h+var_110], rcx
0x18001f6cd  mov     [rbp+170h+var_100], r15
0x18001f6d1  mov     [rbp+170h+var_F4], esi
0x18001f6d4  mov     [rbp+170h+var_108], 4
0x18001f6dc  test    r12, r12
0x18001f6df  jz      short loc_18001F6F1
0x18001f6e1  mov     rcx, rax
0x18001f6e4  inc     rcx
0x18001f6e7  cmp     [r12+rcx], sil
0x18001f6eb  jnz     short loc_18001F6E4
0x18001f6ed  inc     ecx
0x18001f6ef  jmp     short loc_18001F6FD
0x18001f6f1  lea     r12, word_1800DBB72
0x18001f6f8  mov     ecx, 1
0x18001f6fd  mov     [rbp+170h+var_118], ecx
0x18001f700  lea     rcx, [rsp+270h+var_238]
0x18001f705  mov     [rbp+170h+var_120], r12
0x18001f709  mov     r12, [rsp+270h+arg_8]
0x18001f711  mov     [rbp+170h+var_130], rcx
0x18001f715  mov     [rbp+170h+var_114], esi
0x18001f718  mov     [rbp+170h+var_128], 4
0x18001f720  test    r13, r13
0x18001f723  jz      short loc_18001F732
0x18001f725  inc     rax
0x18001f728  cmp     [rax+r13], sil
0x18001f72c  jnz     short loc_18001F725
0x18001f72e  inc     eax
0x18001f730  jmp     short loc_18001F73E
0x18001f732  lea     r13, word_1800DBB72
0x18001f739  mov     eax, 1
0x18001f73e  mov     rcx, [rsp+270h+SRWLock]
0x18001f743  lea     rdx, _TraceLoggingMetadata
0x18001f74a  mov     [rbp+170h+var_138], eax
0x18001f74d  lea     r8, [rdi+8]; ActivityId
0x18001f751  mov     [rbp+170h+var_140], r13
0x18001f755  lea     rax, [rsp+270h+var_230]
0x18001f75a  mov     [rbp+170h+var_150], rax
0x18001f75e  xor     r9d, r9d; RelatedActivityId
0x18001f761  mov     [rbp+170h+var_134], esi
0x18001f764  lea     rax, [rsp+270h+var_208]
0x18001f769  mov     [rbp+170h+var_160], rax
0x18001f76d  lea     rax, [rsp+270h+var_228]
0x18001f772  mov     [rbp+170h+var_170], rax
0x18001f776  movzx   eax, cs:word_1800F6223
0x18001f77d  mov     dword ptr [rsp+270h+EventDescriptor.Level], eax
0x18001f781  mov     rax, [rcx+8]
0x18001f785  mov     [rbp+170h+var_190.Ptr], rax
0x18001f789  mov     [rbp+170h+var_148], 4
0x18001f791  mov     [rbp+170h+var_158], 8
0x18001f799  mov     [rbp+170h+var_168], 8
0x18001f7a1  mov     dword ptr [rsp+270h+EventDescriptor.Id], 0B000000h
0x18001f7a9  mov     [rsp+270h+EventDescriptor.Keyword], rsi
0x18001f7ae  movzx   eax, word ptr [rax]
0x18001f7b1  mov     [rbp+170h+var_190.Size], eax
0x18001f7b4  lea     rax, byte_1800F622D
0x18001f7bb  mov     [rbp+170h+var_180], rax
0x18001f7bf  lea     rax, _TraceLoggingMetadataEnd
0x18001f7c6  sub     eax, edx
0x18001f7c8  mov     dword ptr [rbp+170h+var_190.0Ch], 2
0x18001f7cf  mov     [rbp+170h+var_178], 149h
0x18001f7d6  lea     rdx, [rsp+270h+EventDescriptor]; EventDescriptor
0x18001f7db  mov     [rbp+170h+var_174], 1
0x18001f7e2  mov     dword ptr [rsp+270h+SRWLock], eax
0x18001f7e6  mov     eax, dword ptr [rsp+270h+SRWLock]
0x18001f7ea  mov     rcx, [rcx+20h]; RegHandle
0x18001f7ee  lea     rax, [rbp+170h+var_190]
0x18001f7f2  mov     [rsp+270h+UserData], rax; UserData
0x18001f7f7  mov     [rsp+270h+UserDataCount], 16h; UserDataCount
0x18001f7ff  call    cs:__imp_EventWriteTransfer
0x18001f806  nop     dword ptr [rax+rax+00h]
0x18001f80b  mov     r13, [rsp+270h+arg_10]
0x18001f813  jmp     loc_18001F9D2
0x18001f818  mov     rbx, [rcx+118h]
0x18001f81f  test    rbx, rbx
0x18001f822  jz      short loc_18001F87B
0x18001f824  add     rbx, 108h
0x18001f82b  mov     rcx, rbx; SRWLock
0x18001f82e  call    cs:__imp_AcquireSRWLockExclusive
0x18001f835  nop     dword ptr [rax+rax+00h]
0x18001f83a  lea     rax, [rsp+270h+var_228]
0x18001f83f  mov     [rax], r15
0x18001f842  mov     rcx, [rsp+270h+var_228]; SRWLock
0x18001f847  test    rcx, rcx
  ... truncated ...
```
