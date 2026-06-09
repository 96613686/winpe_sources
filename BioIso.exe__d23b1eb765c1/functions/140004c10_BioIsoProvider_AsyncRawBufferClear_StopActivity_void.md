# BioIsoProvider::AsyncRawBufferClear::StopActivity(void)

- ea: `0x140004c10`
- end: `0x14000526e`
- name: `?StopActivity@AsyncRawBufferClear@BioIsoProvider@@MEAAXXZ`
- size: `1630`
- prototype: `void __fastcall(BioIsoProvider::AsyncRawBufferClear *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140003eb0`
- `0x140004c10`
- `0x14000d990`
- `0x14001bd40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140004c81`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400050c8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140004c81`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400050c8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004c9f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004cc0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004ce0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400050e6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140005107`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140005127`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004c9f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004cc0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004ce0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400050e6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140005107`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140005127`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005154`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005154`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x14000522a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x14000522a`

## pseudocode

```c
void __fastcall BioIsoProvider::AsyncRawBufferClear::StopActivity(BioIsoProvider::AsyncRawBufferClear *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  RTL_SRWLOCK *v5; // rbx
  RTL_SRWLOCK *v6; // rbx
  __int64 v7; // r13
  const unsigned __int16 *v8; // rdx
  int *v9; // r8
  const unsigned __int16 *v10; // r9
  int *v11; // r10
  const unsigned __int16 *v12; // r11
  const unsigned __int16 *v13; // rbx
  int *v14; // r14
  const unsigned __int16 *v15; // r15
  const unsigned __int16 *v16; // r12
  __int64 v17; // rdi
  __int64 v18; // rcx
  __int64 v19; // rax
  int v20; // eax
  __int64 v21; // rax
  int v22; // eax
  __int64 v23; // rax
  int v24; // eax
  __int64 v25; // rax
  int v26; // eax
  __int64 v27; // rax
  int v28; // eax
  __int64 v29; // rax
  int v30; // eax
  __int64 v31; // rax
  int v32; // eax
  __int64 v33; // rax
  int v34; // eax
  int v35; // ecx
  RTL_SRWLOCK *v36; // rbx
  __int64 v37; // rbx
  __int64 v38; // r8
  unsigned int v39; // [rsp+30h] [rbp-D0h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-C8h] BYREF
  PSRWLOCK v41; // [rsp+40h] [rbp-C0h] BYREF
  PSRWLOCK v42; // [rsp+48h] [rbp-B8h] BYREF
  int v43; // [rsp+50h] [rbp-B0h] BYREF
  int v44; // [rsp+54h] [rbp-ACh] BYREF
  int v45; // [rsp+58h] [rbp-A8h] BYREF
  int v46; // [rsp+5Ch] [rbp-A4h] BYREF
  int v47; // [rsp+60h] [rbp-A0h] BYREF
  int v48; // [rsp+64h] [rbp-9Ch] BYREF
  PSRWLOCK v49; // [rsp+68h] [rbp-98h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+70h] [rbp-90h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v51; // [rsp+80h] [rbp-80h] BYREF
  __int16 *v52; // [rsp+90h] [rbp-70h]
  int v53; // [rsp+98h] [rbp-68h]
  int v54; // [rsp+9Ch] [rbp-64h]
  PSRWLOCK *v55; // [rsp+A0h] [rbp-60h]
  __int64 v56; // [rsp+A8h] [rbp-58h]
  PSRWLOCK *v57; // [rsp+B0h] [rbp-50h]
  __int64 v58; // [rsp+B8h] [rbp-48h]
  PSRWLOCK *p_SRWLock; // [rsp+C0h] [rbp-40h]
  __int64 v60; // [rsp+C8h] [rbp-38h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+D0h] [rbp-30h] BYREF
  void *v62; // [rsp+E0h] [rbp-20h]
  int v63; // [rsp+E8h] [rbp-18h]
  int v64; // [rsp+ECh] [rbp-14h]
  PSRWLOCK *v65; // [rsp+F0h] [rbp-10h]
  __int64 v66; // [rsp+F8h] [rbp-8h]
  PSRWLOCK *v67; // [rsp+100h] [rbp+0h]
  __int64 v68; // [rsp+108h] [rbp+8h]
  PSRWLOCK *v69; // [rsp+110h] [rbp+10h]
  __int64 v70; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v71; // [rsp+120h] [rbp+20h]
  int v72; // [rsp+128h] [rbp+28h]
  int v73; // [rsp+12Ch] [rbp+2Ch]
  unsigned int *v74; // [rsp+130h] [rbp+30h]
  __int64 v75; // [rsp+138h] [rbp+38h]
  const unsigned __int16 *v76; // [rsp+140h] [rbp+40h]
  int v77; // [rsp+148h] [rbp+48h]
  int v78; // [rsp+14Ch] [rbp+4Ch]
  int *v79; // [rsp+150h] [rbp+50h]
  __int64 v80; // [rsp+158h] [rbp+58h]
  int *v81; // [rsp+160h] [rbp+60h]
  int v82; // [rsp+168h] [rbp+68h]
  int v83; // [rsp+16Ch] [rbp+6Ch]
  int *v84; // [rsp+170h] [rbp+70h]
  __int64 v85; // [rsp+178h] [rbp+78h]
  const unsigned __int16 *v86; // [rsp+180h] [rbp+80h]
  int v87; // [rsp+188h] [rbp+88h]
  int v88; // [rsp+18Ch] [rbp+8Ch]
  int *v89; // [rsp+190h] [rbp+90h]
  __int64 v90; // [rsp+198h] [rbp+98h]
  const unsigned __int16 *v91; // [rsp+1A0h] [rbp+A0h]
  int v92; // [rsp+1A8h] [rbp+A8h]
  int v93; // [rsp+1ACh] [rbp+ACh]
  int *v94; // [rsp+1B0h] [rbp+B0h]
  int v95; // [rsp+1B8h] [rbp+B8h]
  int v96; // [rsp+1BCh] [rbp+BCh]
  int *v97; // [rsp+1C0h] [rbp+C0h]
  __int64 v98; // [rsp+1C8h] [rbp+C8h]
  const unsigned __int16 *v99; // [rsp+1D0h] [rbp+D0h]
  int v100; // [rsp+1D8h] [rbp+D8h]
  int v101; // [rsp+1DCh] [rbp+DCh]
  int *v102; // [rsp+1E0h] [rbp+E0h]
  int v103; // [rsp+1E8h] [rbp+E8h]
  int v104; // [rsp+1ECh] [rbp+ECh]
  int *v105; // [rsp+1F0h] [rbp+F0h]
  __int64 v106; // [rsp+1F8h] [rbp+F8h]
  int *v107; // [rsp+200h] [rbp+100h]
  __int64 v108; // [rsp+208h] [rbp+108h]
  const unsigned __int16 *v109; // [rsp+210h] [rbp+110h]
  int v110; // [rsp+218h] [rbp+118h]
  int v111; // [rsp+21Ch] [rbp+11Ch]

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) )
  {
    v5 = (RTL_SRWLOCK *)*((_QWORD *)this + 35);
    if ( v4 )
    {
      if ( v5 )
      {
        v6 = v5 + 33;
        AcquireSRWLockExclusive(v6);
        SRWLock = 0;
        **((_DWORD **)this + 34) = 2;
        if ( v6 )
          ReleaseSRWLockExclusive(v6);
      }
      else
      {
        v41 = 0;
        **((_DWORD **)this + 34) = 2;
      }
      v7 = *((_QWORD *)BioIsoProvider::Instance() + 1);
      if ( *(_DWORD *)v7 > 5u )
      {
        v8 = (const unsigned __int16 *)*((_QWORD *)v4 + 6);
        v43 = v4[17];
        v44 = v4[4];
        v9 = (int *)*((_QWORD *)v4 + 15);
        v10 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
        v45 = v4[26];
        v11 = (int *)*((_QWORD *)v4 + 12);
        v12 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
        v46 = v4[20];
        v13 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
        v47 = v4[8];
        v14 = (int *)*((_QWORD *)v4 + 3);
        v48 = *v4;
        v15 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
        v39 = v4[16];
        v16 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
        LODWORD(v41) = v4[2];
        v49 = (PSRWLOCK)0x1000000;
        v42 = 0;
        v17 = *((_QWORD *)this + 34);
        v18 = -1;
        if ( v8 )
        {
          v19 = -1;
          do
            ++v19;
          while ( *((_BYTE *)v8 + v19) );
          v20 = v19 + 1;
        }
        else
        {
          v8 = &word_14008BBFE;
          v20 = 1;
        }
        v109 = v8;
        v110 = v20;
        v111 = 0;
        v107 = &v43;
        v108 = 4;
        v105 = &v44;
        v106 = 4;
        if ( v9 )
        {
          v21 = -1;
          do
            ++v21;
          while ( *((_WORD *)v9 + v21) );
          v22 = 2 * v21 + 2;
        }
        else
        {
          v9 = &dword_14008BB54;
          v22 = 2;
        }
        v102 = v9;
        v103 = v22;
        v104 = 0;
        if ( v10 )
        {
          v23 = -1;
          do
            ++v23;
          while ( *((_BYTE *)v10 + v23) );
          v24 = v23 + 1;
        }
        else
        {
          v10 = &word_14008BBFE;
          v24 = 1;
        }
        v99 = v10;
        v100 = v24;
        v101 = 0;
        v97 = &v45;
        v98 = 4;
        if ( v11 )
        {
          v25 = -1;
          do
            ++v25;
          while ( *((_WORD *)v11 + v25) );
          v26 = 2 * v25 + 2;
        }
        else
        {
          v11 = &dword_14008BB54;
          v26 = 2;
        }
        v94 = v11;
        v95 = v26;
        v96 = 0;
        if ( v12 )
        {
          v27 = -1;
          do
            ++v27;
          while ( *((_BYTE *)v12 + v27) );
          v28 = v27 + 1;
        }
        else
        {
          v12 = &word_14008BBFE;
          v28 = 1;
        }
        v91 = v12;
        v92 = v28;
        v93 = 0;
        v89 = &v46;
        v90 = 4;
        if ( v13 )
        {
          v29 = -1;
          do
            ++v29;
          while ( *((_BYTE *)v13 + v29) );
          v30 = v29 + 1;
        }
        else
        {
          v13 = &word_14008BBFE;
          v30 = 1;
        }
        v86 = v13;
        v87 = v30;
        v88 = 0;
        v84 = &v47;
        v85 = 4;
        if ( v14 )
        {
          v31 = -1;
          do
            ++v31;
          while ( *((_WORD *)v14 + v31) );
          v32 = 2 * v31 + 2;
        }
        else
        {
          v14 = &dword_14008BB54;
          v32 = 2;
        }
        v81 = v14;
        v82 = v32;
        v83 = 0;
        v79 = &v48;
        v80 = 4;
        if ( v15 )
        {
          v33 = -1;
          do
            ++v33;
          while ( *((_BYTE *)v15 + v33) );
          v34 = v33 + 1;
        }
        else
        {
          v15 = &word_14008BBFE;
          v34 = 1;
        }
        v76 = v15;
        v77 = v34;
        v78 = 0;
        v74 = &v39;
        v75 = 4;
        if ( v16 )
        {
          do
            ++v18;
          while ( *((_BYTE *)v16 + v18) );
          v35 = v18 + 1;
        }
        else
        {
          v16 = &word_14008BBFE;
          v35 = 1;
        }
        v71 = v16;
        v72 = v35;
        v73 = 0;
        v69 = &v41;
        v70 = 4;
        v67 = &v49;
        v68 = 8;
        v65 = &v42;
        v66 = 8;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        *(_DWORD *)&EventDescriptor.Level = 517;
        EventDescriptor.Keyword = 0;
        UserData.Ptr = *(_QWORD *)(v7 + 8);
        UserData.Size = *(unsigned __int16 *)UserData.Ptr;
        UserData.Reserved = 2;
        v62 = &unk_1400A1720;
        v63 = 322;
        v64 = 1;
        LODWORD(SRWLock) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(*(_QWORD *)(v7 + 32), &EventDescriptor, (LPCGUID)(v17 + 8), 0, 0x15u, &UserData);
      }
      goto LABEL_61;
    }
  }
  else
  {
    v5 = (RTL_SRWLOCK *)*((_QWORD *)this + 35);
  }
  if ( v5 )
  {
    v36 = v5 + 33;
    AcquireSRWLockExclusive(v36);
    v42 = 0;
    **((_DWORD **)this + 34) = 2;
    if ( v36 )
      ReleaseSRWLockExclusive(v36);
  }
  else
  {
    v49 = 0;
    **((_DWORD **)this + 34) = 2;
  }
  v37 = *((_QWORD *)BioIsoProvider::Instance() + 1);
  if ( *(_DWORD *)v37 > 5u )
  {
    LODWORD(SRWLock) = GetCurrentThreadId();
    v38 = *((_QWORD *)this + 34);
    LODWORD(v41) = *(_DWORD *)(v38 + 72);
    v42 = 0;
    p_SRWLock = &SRWLock;
    v60 = 4;
    v57 = &v41;
    v58 = 4;
    v55 = &v42;
    v56 = 8;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 517;
    EventDescriptor.Keyword = 0;
    v51.Ptr = *(_QWORD *)(v37 + 8);
    v51.Size = *(unsigned __int16 *)v51.Ptr;
    v51.Reserved = 2;
    v52 = &word_1400A186E;
    v53 = 72;
    v54 = 1;
    v39 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(*(_QWORD *)(v37 + 32), &EventDescriptor, (LPCGUID)(v38 + 8), 0, 5u, &v51);
  }
LABEL_61:
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((BioIsoProvider::AsyncRawBufferClear *)((char *)this + 288));
}

```

## disassembly

```asm
0x140004c10  push    rbp
0x140004c12  push    rbx
0x140004c13  push    rsi
0x140004c14  push    rdi
0x140004c15  push    r12
0x140004c17  push    r13
0x140004c19  push    r14
0x140004c1b  push    r15
0x140004c1d  lea     rbp, [rsp-138h]
0x140004c25  sub     rsp, 238h
0x140004c2c  mov     rax, cs:__security_cookie
0x140004c33  xor     rax, rsp
0x140004c36  mov     [rbp+170h+var_50], rax
0x140004c3d  mov     rsi, rcx
0x140004c40  xor     r14d, r14d
0x140004c43  mov     rdi, [rcx+110h]
0x140004c4a  mov     eax, [rdi+48h]
0x140004c4d  test    eax, eax
0x140004c4f  jns     loc_1400050B2
0x140004c55  add     rdi, 50h ; 'P'
0x140004c59  cmp     eax, [rdi+8]
0x140004c5c  jnz     loc_1400050B2
0x140004c62  mov     rbx, [rcx+118h]
0x140004c69  test    rdi, rdi
0x140004c6c  jz      loc_1400050B9
0x140004c72  test    rbx, rbx
0x140004c75  jz      short loc_140004CCE
0x140004c77  add     rbx, 108h
0x140004c7e  mov     rcx, rbx; SRWLock
0x140004c81  call    cs:__imp_AcquireSRWLockExclusive
0x140004c88  nop     dword ptr [rax+rax+00h]
0x140004c8d  lea     rax, [rsp+270h+SRWLock]
0x140004c92  mov     [rax], r14
0x140004c95  mov     rcx, [rsp+270h+SRWLock]; SRWLock
0x140004c9a  test    rcx, rcx
0x140004c9d  jz      short loc_140004CAB
0x140004c9f  call    cs:__imp_ReleaseSRWLockExclusive
0x140004ca6  nop     dword ptr [rax+rax+00h]
0x140004cab  mov     rax, [rsi+110h]
0x140004cb2  mov     dword ptr [rax], 2
0x140004cb8  test    rbx, rbx
0x140004cbb  jz      short loc_140004CF9
0x140004cbd  mov     rcx, rbx; SRWLock
0x140004cc0  call    cs:__imp_ReleaseSRWLockExclusive
0x140004cc7  nop     dword ptr [rax+rax+00h]
0x140004ccc  jmp     short loc_140004CF9
0x140004cce  lea     rax, [rsp+270h+var_230]
0x140004cd3  mov     [rax], r14
0x140004cd6  mov     rcx, [rsp+270h+var_230]; SRWLock
0x140004cdb  test    rcx, rcx
0x140004cde  jz      short loc_140004CEC
0x140004ce0  call    cs:__imp_ReleaseSRWLockExclusive
0x140004ce7  nop     dword ptr [rax+rax+00h]
0x140004cec  mov     rax, [rsi+110h]
0x140004cf3  mov     dword ptr [rax], 2
0x140004cf9  call    ?Instance@BioIsoProvider@@KAPEAV1@XZ; BioIsoProvider::Instance(void)
0x140004cfe  mov     r13, [rax+8]
0x140004d02  mov     eax, [r13+0]
0x140004d06  cmp     eax, 5
0x140004d09  jbe     loc_140005237
0x140004d0f  mov     rdx, [rdi+30h]
0x140004d13  mov     eax, [rdi+44h]
0x140004d16  mov     [rsp+270h+var_220], eax
0x140004d1a  mov     eax, [rdi+10h]
0x140004d1d  mov     [rsp+270h+var_21C], eax
0x140004d21  mov     r8, [rdi+78h]
0x140004d25  mov     r9, [rdi+70h]
0x140004d29  mov     eax, [rdi+68h]
0x140004d2c  mov     [rsp+270h+var_218], eax
0x140004d30  mov     r10, [rdi+60h]
0x140004d34  mov     r11, [rdi+58h]
0x140004d38  mov     eax, [rdi+50h]
0x140004d3b  mov     [rsp+270h+var_214], eax
0x140004d3f  mov     rbx, [rdi+48h]
0x140004d43  mov     eax, [rdi+20h]
0x140004d46  mov     [rsp+270h+var_210], eax
0x140004d4a  mov     r14, [rdi+18h]
0x140004d4e  mov     eax, [rdi]
0x140004d50  mov     [rsp+270h+var_20C], eax
0x140004d54  mov     r15, [rdi+80h]
0x140004d5b  mov     eax, [rdi+40h]
0x140004d5e  mov     [rsp+270h+var_240], eax
0x140004d62  mov     r12, [rdi+38h]
0x140004d66  mov     eax, [rdi+8]
0x140004d69  mov     dword ptr [rsp+270h+var_230], eax
0x140004d6d  mov     [rsp+270h+var_208], 1000000h
0x140004d76  mov     [rsp+270h+var_228], 0
0x140004d7f  mov     rdi, [rsi+110h]
0x140004d86  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140004d8d  test    rdx, rdx
0x140004d90  jz      short loc_140004DA2
0x140004d92  mov     rax, rcx
0x140004d95  inc     rax
0x140004d98  cmp     byte ptr [rdx+rax], 0
0x140004d9c  jnz     short loc_140004D95
0x140004d9e  inc     eax
0x140004da0  jmp     short loc_140004DAE
0x140004da2  lea     rdx, word_14008BBFE
0x140004da9  mov     eax, 1
0x140004dae  mov     [rbp+170h+var_60], rdx
0x140004db5  mov     [rbp+170h+var_58], eax
0x140004dbb  xor     edx, edx
0x140004dbd  mov     [rbp+170h+var_54], edx
0x140004dc3  lea     rax, [rsp+270h+var_220]
0x140004dc8  mov     [rbp+170h+var_70], rax
0x140004dcf  mov     [rbp+170h+var_68], 4
0x140004dda  lea     rax, [rsp+270h+var_21C]
0x140004ddf  mov     [rbp+170h+var_80], rax
0x140004de6  mov     [rbp+170h+var_78], 4
0x140004df1  test    r8, r8
0x140004df4  jz      short loc_140004E14
0x140004df6  mov     rax, rcx
0x140004df9  nop     dword ptr [rax+00000000h]
0x140004e00  lea     rax, [rax+1]
0x140004e04  cmp     [r8+rax*2], dx
0x140004e09  jnz     short loc_140004E00
0x140004e0b  lea     eax, ds:2[rax*2]
0x140004e12  jmp     short loc_140004E20
0x140004e14  lea     r8, dword_14008BB54
0x140004e1b  mov     eax, 2
0x140004e20  mov     [rbp+170h+var_90], r8
0x140004e27  mov     [rbp+170h+var_88], eax
0x140004e2d  mov     [rbp+170h+var_84], edx
0x140004e33  test    r9, r9
0x140004e36  jz      short loc_140004E4D
0x140004e38  mov     rax, rcx
0x140004e3b  nop     dword ptr [rax+rax+00h]
0x140004e40  inc     rax
0x140004e43  cmp     [r9+rax], dl
0x140004e47  jnz     short loc_140004E40
0x140004e49  inc     eax
0x140004e4b  jmp     short loc_140004E59
0x140004e4d  lea     r9, word_14008BBFE
0x140004e54  mov     eax, 1
0x140004e59  mov     [rbp+170h+var_A0], r9
0x140004e60  mov     [rbp+170h+var_98], eax
0x140004e66  mov     [rbp+170h+var_94], edx
0x140004e6c  lea     rax, [rsp+270h+var_218]
0x140004e71  mov     [rbp+170h+var_B0], rax
0x140004e78  mov     [rbp+170h+var_A8], 4
0x140004e83  test    r10, r10
0x140004e86  jz      short loc_140004EA4
0x140004e88  mov     rax, rcx
0x140004e8b  nop     dword ptr [rax+rax+00h]
0x140004e90  lea     rax, [rax+1]
0x140004e94  cmp     [r10+rax*2], dx
0x140004e99  jnz     short loc_140004E90
0x140004e9b  lea     eax, ds:2[rax*2]
0x140004ea2  jmp     short loc_140004EB0
0x140004ea4  lea     r10, dword_14008BB54
0x140004eab  mov     eax, 2
0x140004eb0  mov     [rbp+170h+var_C0], r10
0x140004eb7  mov     [rbp+170h+var_B8], eax
0x140004ebd  mov     [rbp+170h+var_B4], edx
0x140004ec3  test    r11, r11
0x140004ec6  jz      short loc_140004EDD
0x140004ec8  mov     rax, rcx
0x140004ecb  nop     dword ptr [rax+rax+00h]
0x140004ed0  inc     rax
0x140004ed3  cmp     [r11+rax], dl
0x140004ed7  jnz     short loc_140004ED0
0x140004ed9  inc     eax
0x140004edb  jmp     short loc_140004EE9
0x140004edd  lea     r11, word_14008BBFE
0x140004ee4  mov     eax, 1
0x140004ee9  mov     [rbp+170h+var_D0], r11
0x140004ef0  mov     [rbp+170h+var_C8], eax
0x140004ef6  mov     [rbp+170h+var_C4], edx
0x140004efc  lea     rax, [rsp+270h+var_214]
0x140004f01  mov     [rbp+170h+var_E0], rax
0x140004f08  mov     [rbp+170h+var_D8], 4
0x140004f13  test    rbx, rbx
0x140004f16  jz      short loc_140004F2C
0x140004f18  mov     rax, rcx
0x140004f1b  nop     dword ptr [rax+rax+00h]
0x140004f20  inc     rax
0x140004f23  cmp     [rbx+rax], dl
0x140004f26  jnz     short loc_140004F20
0x140004f28  inc     eax
0x140004f2a  jmp     short loc_140004F38
0x140004f2c  lea     rbx, word_14008BBFE
0x140004f33  mov     eax, 1
0x140004f38  mov     [rbp+170h+var_F0], rbx
0x140004f3f  mov     [rbp+170h+var_E8], eax
0x140004f45  mov     [rbp+170h+var_E4], edx
0x140004f4b  lea     rax, [rsp+270h+var_210]
0x140004f50  mov     [rbp+170h+var_100], rax
0x140004f54  mov     [rbp+170h+var_F8], 4
0x140004f5c  test    r14, r14
0x140004f5f  jz      short loc_140004F78
0x140004f61  mov     rax, rcx
0x140004f64  lea     rax, [rax+1]
0x140004f68  cmp     [r14+rax*2], dx
0x140004f6d  jnz     short loc_140004F64
0x140004f6f  lea     eax, ds:2[rax*2]
0x140004f76  jmp     short loc_140004F84
0x140004f78  lea     r14, dword_14008BB54
0x140004f7f  mov     eax, 2
0x140004f84  mov     [rbp+170h+var_110], r14
0x140004f88  mov     [rbp+170h+var_108], eax
0x140004f8b  mov     [rbp+170h+var_104], edx
0x140004f8e  lea     rax, [rsp+270h+var_20C]
0x140004f93  mov     [rbp+170h+var_120], rax
0x140004f97  mov     [rbp+170h+var_118], 4
0x140004f9f  test    r15, r15
0x140004fa2  jz      short loc_140004FB4
0x140004fa4  mov     rax, rcx
0x140004fa7  inc     rax
0x140004faa  cmp     [r15+rax], dl
0x140004fae  jnz     short loc_140004FA7
0x140004fb0  inc     eax
0x140004fb2  jmp     short loc_140004FC0
0x140004fb4  lea     r15, word_14008BBFE
0x140004fbb  mov     eax, 1
0x140004fc0  mov     [rbp+170h+var_130], r15
0x140004fc4  mov     [rbp+170h+var_128], eax
0x140004fc7  mov     [rbp+170h+var_124], edx
0x140004fca  lea     rax, [rsp+270h+var_240]
0x140004fcf  mov     [rbp+170h+var_140], rax
0x140004fd3  mov     [rbp+170h+var_138], 4
0x140004fdb  test    r12, r12
0x140004fde  jz      short loc_140004FED
0x140004fe0  inc     rcx
0x140004fe3  cmp     [r12+rcx], dl
0x140004fe7  jnz     short loc_140004FE0
0x140004fe9  inc     ecx
0x140004feb  jmp     short loc_140004FF9
0x140004fed  lea     r12, word_14008BBFE
0x140004ff4  mov     ecx, 1
0x140004ff9  mov     [rbp+170h+var_150], r12
0x140004ffd  mov     [rbp+170h+var_148], ecx
0x140005000  mov     [rbp+170h+var_144], edx
0x140005003  lea     rax, [rsp+270h+var_230]
0x140005008  mov     [rbp+170h+var_160], rax
0x14000500c  mov     [rbp+170h+var_158], 4
0x140005014  lea     rax, [rsp+270h+var_208]
0x140005019  mov     [rbp+170h+var_170], rax
0x14000501d  mov     [rbp+170h+var_168], 8
0x140005025  lea     rax, [rsp+270h+var_228]
0x14000502a  mov     [rbp+170h+var_180], rax
0x14000502e  mov     [rbp+170h+var_178], 8
0x140005036  mov     dword ptr [rsp+270h+EventDescriptor.Id], 0B000000h
0x14000503e  movzx   eax, cs:word_1400A1716
0x140005045  mov     dword ptr [rsp+270h+EventDescriptor.Level], eax
0x140005049  mov     [rsp+270h+EventDescriptor.Keyword], rdx
0x14000504e  mov     rax, [r13+8]
0x140005052  mov     [rbp+170h+var_1A0], rax
0x140005056  movzx   eax, word ptr [rax]
0x140005059  mov     [rbp+170h+var_198], eax
0x14000505c  mov     [rbp+170h+var_194], 2
0x140005063  lea     rax, unk_1400A1720
0x14000506a  mov     [rbp+170h+var_190], rax
0x14000506e  mov     [rbp+170h+var_188], 142h
0x140005075  mov     [rbp+170h+var_184], 1
0x14000507c  lea     rax, _TraceLoggingMetadataEnd
0x140005083  lea     rdx, _TraceLoggingMetadata
0x14000508a  sub     eax, edx
0x14000508c  mov     dword ptr [rsp+270h+SRWLock], eax
0x140005090  mov     eax, dword ptr [rsp+270h+SRWLock]
0x140005094  lea     rax, [rbp+170h+var_1A0]
0x140005098  mov     [rsp+270h+UserData], rax
0x14000509d  mov     [rsp+270h+UserDataCount], 15h
0x1400050a5  lea     r8, [rdi+8]
0x1400050a9  mov     rcx, [r13+20h]
0x1400050ad  jmp     loc_140005222
0x1400050b2  mov     rbx, [rcx+118h]
0x1400050b9  test    rbx, rbx
0x1400050bc  jz      short loc_140005115
0x1400050be  add     rbx, 108h
0x1400050c5  mov     rcx, rbx; SRWLock
0x1400050c8  call    cs:__imp_AcquireSRWLockExclusive
0x1400050cf  nop     dword ptr [rax+rax+00h]
0x1400050d4  lea     rax, [rsp+270h+var_228]
0x1400050d9  mov     [rax], r14
0x1400050dc  mov     rcx, [rsp+270h+var_228]; SRWLock
0x1400050e1  test    rcx, rcx
0x1400050e4  jz      short loc_1400050F2
0x1400050e6  call    cs:__imp_ReleaseSRWLockExclusive
0x1400050ed  nop     dword ptr [rax+rax+00h]
0x1400050f2  mov     rax, [rsi+110h]
0x1400050f9  mov     dword ptr [rax], 2
0x1400050ff  test    rbx, rbx
0x140005102  jz      short loc_140005140
0x140005104  mov     rcx, rbx; SRWLock
0x140005107  call    cs:__imp_ReleaseSRWLockExclusive
0x14000510e  nop     dword ptr [rax+rax+00h]
0x140005113  jmp     short loc_140005140
0x140005115  lea     rax, [rsp+270h+var_208]
0x14000511a  mov     [rax], r14
0x14000511d  mov     rcx, [rsp+270h+var_208]; SRWLock
0x140005122  test    rcx, rcx
0x140005125  jz      short loc_140005133
0x140005127  call    cs:__imp_ReleaseSRWLockExclusive
0x14000512e  nop     dword ptr [rax+rax+00h]
0x140005133  mov     rax, [rsi+110h]
0x14000513a  mov     dword ptr [rax], 2
0x140005140  call    ?Instance@BioIsoProvider@@KAPEAV1@XZ; BioIsoProvider::Instance(void)
0x140005145  mov     rbx, [rax+8]
0x140005149  mov     eax, [rbx]
0x14000514b  cmp     eax, 5
  ... truncated ...
```
