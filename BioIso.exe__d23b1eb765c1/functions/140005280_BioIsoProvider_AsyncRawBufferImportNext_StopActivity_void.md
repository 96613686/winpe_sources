# BioIsoProvider::AsyncRawBufferImportNext::StopActivity(void)

- ea: `0x140005280`
- end: `0x1400058de`
- name: `?StopActivity@AsyncRawBufferImportNext@BioIsoProvider@@MEAAXXZ`
- size: `1630`
- prototype: `void __fastcall(BioIsoProvider::AsyncRawBufferImportNext *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140003eb0`
- `0x140005280`
- `0x14000d990`
- `0x14001bd40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400052f1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140005738`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400052f1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140005738`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000530f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140005330`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140005350`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140005756`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140005777`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140005797`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000530f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140005330`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140005350`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140005756`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140005777`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140005797`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400057c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400057c4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x14000589a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x14000589a`

## pseudocode

```c
void __fastcall BioIsoProvider::AsyncRawBufferImportNext::StopActivity(BioIsoProvider::AsyncRawBufferImportNext *this)
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
  char *v52; // [rsp+90h] [rbp-70h]
  int v53; // [rsp+98h] [rbp-68h]
  int v54; // [rsp+9Ch] [rbp-64h]
  PSRWLOCK *v55; // [rsp+A0h] [rbp-60h]
  __int64 v56; // [rsp+A8h] [rbp-58h]
  PSRWLOCK *v57; // [rsp+B0h] [rbp-50h]
  __int64 v58; // [rsp+B8h] [rbp-48h]
  PSRWLOCK *p_SRWLock; // [rsp+C0h] [rbp-40h]
  __int64 v60; // [rsp+C8h] [rbp-38h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+D0h] [rbp-30h] BYREF
  __int16 *v62; // [rsp+E0h] [rbp-20h]
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
        v62 = &word_1400A13C6;
        v63 = 327;
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
    v52 = byte_1400A1519;
    v53 = 77;
    v54 = 1;
    v39 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(*(_QWORD *)(v37 + 32), &EventDescriptor, (LPCGUID)(v38 + 8), 0, 5u, &v51);
  }
LABEL_61:
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((BioIsoProvider::AsyncRawBufferImportNext *)((char *)this + 288));
}

```

## disassembly

```asm
0x140005280  push    rbp
0x140005282  push    rbx
0x140005283  push    rsi
0x140005284  push    rdi
0x140005285  push    r12
0x140005287  push    r13
0x140005289  push    r14
0x14000528b  push    r15
0x14000528d  lea     rbp, [rsp-138h]
0x140005295  sub     rsp, 238h
0x14000529c  mov     rax, cs:__security_cookie
0x1400052a3  xor     rax, rsp
0x1400052a6  mov     [rbp+170h+var_50], rax
0x1400052ad  mov     rsi, rcx
0x1400052b0  xor     r14d, r14d
0x1400052b3  mov     rdi, [rcx+110h]
0x1400052ba  mov     eax, [rdi+48h]
0x1400052bd  test    eax, eax
0x1400052bf  jns     loc_140005722
0x1400052c5  add     rdi, 50h ; 'P'
0x1400052c9  cmp     eax, [rdi+8]
0x1400052cc  jnz     loc_140005722
0x1400052d2  mov     rbx, [rcx+118h]
0x1400052d9  test    rdi, rdi
0x1400052dc  jz      loc_140005729
0x1400052e2  test    rbx, rbx
0x1400052e5  jz      short loc_14000533E
0x1400052e7  add     rbx, 108h
0x1400052ee  mov     rcx, rbx; SRWLock
0x1400052f1  call    cs:__imp_AcquireSRWLockExclusive
0x1400052f8  nop     dword ptr [rax+rax+00h]
0x1400052fd  lea     rax, [rsp+270h+SRWLock]
0x140005302  mov     [rax], r14
0x140005305  mov     rcx, [rsp+270h+SRWLock]; SRWLock
0x14000530a  test    rcx, rcx
0x14000530d  jz      short loc_14000531B
0x14000530f  call    cs:__imp_ReleaseSRWLockExclusive
0x140005316  nop     dword ptr [rax+rax+00h]
0x14000531b  mov     rax, [rsi+110h]
0x140005322  mov     dword ptr [rax], 2
0x140005328  test    rbx, rbx
0x14000532b  jz      short loc_140005369
0x14000532d  mov     rcx, rbx; SRWLock
0x140005330  call    cs:__imp_ReleaseSRWLockExclusive
0x140005337  nop     dword ptr [rax+rax+00h]
0x14000533c  jmp     short loc_140005369
0x14000533e  lea     rax, [rsp+270h+var_230]
0x140005343  mov     [rax], r14
0x140005346  mov     rcx, [rsp+270h+var_230]; SRWLock
0x14000534b  test    rcx, rcx
0x14000534e  jz      short loc_14000535C
0x140005350  call    cs:__imp_ReleaseSRWLockExclusive
0x140005357  nop     dword ptr [rax+rax+00h]
0x14000535c  mov     rax, [rsi+110h]
0x140005363  mov     dword ptr [rax], 2
0x140005369  call    ?Instance@BioIsoProvider@@KAPEAV1@XZ; BioIsoProvider::Instance(void)
0x14000536e  mov     r13, [rax+8]
0x140005372  mov     eax, [r13+0]
0x140005376  cmp     eax, 5
0x140005379  jbe     loc_1400058A7
0x14000537f  mov     rdx, [rdi+30h]
0x140005383  mov     eax, [rdi+44h]
0x140005386  mov     [rsp+270h+var_220], eax
0x14000538a  mov     eax, [rdi+10h]
0x14000538d  mov     [rsp+270h+var_21C], eax
0x140005391  mov     r8, [rdi+78h]
0x140005395  mov     r9, [rdi+70h]
0x140005399  mov     eax, [rdi+68h]
0x14000539c  mov     [rsp+270h+var_218], eax
0x1400053a0  mov     r10, [rdi+60h]
0x1400053a4  mov     r11, [rdi+58h]
0x1400053a8  mov     eax, [rdi+50h]
0x1400053ab  mov     [rsp+270h+var_214], eax
0x1400053af  mov     rbx, [rdi+48h]
0x1400053b3  mov     eax, [rdi+20h]
0x1400053b6  mov     [rsp+270h+var_210], eax
0x1400053ba  mov     r14, [rdi+18h]
0x1400053be  mov     eax, [rdi]
0x1400053c0  mov     [rsp+270h+var_20C], eax
0x1400053c4  mov     r15, [rdi+80h]
0x1400053cb  mov     eax, [rdi+40h]
0x1400053ce  mov     [rsp+270h+var_240], eax
0x1400053d2  mov     r12, [rdi+38h]
0x1400053d6  mov     eax, [rdi+8]
0x1400053d9  mov     dword ptr [rsp+270h+var_230], eax
0x1400053dd  mov     [rsp+270h+var_208], 1000000h
0x1400053e6  mov     [rsp+270h+var_228], 0
0x1400053ef  mov     rdi, [rsi+110h]
0x1400053f6  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1400053fd  test    rdx, rdx
0x140005400  jz      short loc_140005412
0x140005402  mov     rax, rcx
0x140005405  inc     rax
0x140005408  cmp     byte ptr [rdx+rax], 0
0x14000540c  jnz     short loc_140005405
0x14000540e  inc     eax
0x140005410  jmp     short loc_14000541E
0x140005412  lea     rdx, word_14008BBFE
0x140005419  mov     eax, 1
0x14000541e  mov     [rbp+170h+var_60], rdx
0x140005425  mov     [rbp+170h+var_58], eax
0x14000542b  xor     edx, edx
0x14000542d  mov     [rbp+170h+var_54], edx
0x140005433  lea     rax, [rsp+270h+var_220]
0x140005438  mov     [rbp+170h+var_70], rax
0x14000543f  mov     [rbp+170h+var_68], 4
0x14000544a  lea     rax, [rsp+270h+var_21C]
0x14000544f  mov     [rbp+170h+var_80], rax
0x140005456  mov     [rbp+170h+var_78], 4
0x140005461  test    r8, r8
0x140005464  jz      short loc_140005484
0x140005466  mov     rax, rcx
0x140005469  nop     dword ptr [rax+00000000h]
0x140005470  lea     rax, [rax+1]
0x140005474  cmp     [r8+rax*2], dx
0x140005479  jnz     short loc_140005470
0x14000547b  lea     eax, ds:2[rax*2]
0x140005482  jmp     short loc_140005490
0x140005484  lea     r8, dword_14008BB54
0x14000548b  mov     eax, 2
0x140005490  mov     [rbp+170h+var_90], r8
0x140005497  mov     [rbp+170h+var_88], eax
0x14000549d  mov     [rbp+170h+var_84], edx
0x1400054a3  test    r9, r9
0x1400054a6  jz      short loc_1400054BD
0x1400054a8  mov     rax, rcx
0x1400054ab  nop     dword ptr [rax+rax+00h]
0x1400054b0  inc     rax
0x1400054b3  cmp     [r9+rax], dl
0x1400054b7  jnz     short loc_1400054B0
0x1400054b9  inc     eax
0x1400054bb  jmp     short loc_1400054C9
0x1400054bd  lea     r9, word_14008BBFE
0x1400054c4  mov     eax, 1
0x1400054c9  mov     [rbp+170h+var_A0], r9
0x1400054d0  mov     [rbp+170h+var_98], eax
0x1400054d6  mov     [rbp+170h+var_94], edx
0x1400054dc  lea     rax, [rsp+270h+var_218]
0x1400054e1  mov     [rbp+170h+var_B0], rax
0x1400054e8  mov     [rbp+170h+var_A8], 4
0x1400054f3  test    r10, r10
0x1400054f6  jz      short loc_140005514
0x1400054f8  mov     rax, rcx
0x1400054fb  nop     dword ptr [rax+rax+00h]
0x140005500  lea     rax, [rax+1]
0x140005504  cmp     [r10+rax*2], dx
0x140005509  jnz     short loc_140005500
0x14000550b  lea     eax, ds:2[rax*2]
0x140005512  jmp     short loc_140005520
0x140005514  lea     r10, dword_14008BB54
0x14000551b  mov     eax, 2
0x140005520  mov     [rbp+170h+var_C0], r10
0x140005527  mov     [rbp+170h+var_B8], eax
0x14000552d  mov     [rbp+170h+var_B4], edx
0x140005533  test    r11, r11
0x140005536  jz      short loc_14000554D
0x140005538  mov     rax, rcx
0x14000553b  nop     dword ptr [rax+rax+00h]
0x140005540  inc     rax
0x140005543  cmp     [r11+rax], dl
0x140005547  jnz     short loc_140005540
0x140005549  inc     eax
0x14000554b  jmp     short loc_140005559
0x14000554d  lea     r11, word_14008BBFE
0x140005554  mov     eax, 1
0x140005559  mov     [rbp+170h+var_D0], r11
0x140005560  mov     [rbp+170h+var_C8], eax
0x140005566  mov     [rbp+170h+var_C4], edx
0x14000556c  lea     rax, [rsp+270h+var_214]
0x140005571  mov     [rbp+170h+var_E0], rax
0x140005578  mov     [rbp+170h+var_D8], 4
0x140005583  test    rbx, rbx
0x140005586  jz      short loc_14000559C
0x140005588  mov     rax, rcx
0x14000558b  nop     dword ptr [rax+rax+00h]
0x140005590  inc     rax
0x140005593  cmp     [rbx+rax], dl
0x140005596  jnz     short loc_140005590
0x140005598  inc     eax
0x14000559a  jmp     short loc_1400055A8
0x14000559c  lea     rbx, word_14008BBFE
0x1400055a3  mov     eax, 1
0x1400055a8  mov     [rbp+170h+var_F0], rbx
0x1400055af  mov     [rbp+170h+var_E8], eax
0x1400055b5  mov     [rbp+170h+var_E4], edx
0x1400055bb  lea     rax, [rsp+270h+var_210]
0x1400055c0  mov     [rbp+170h+var_100], rax
0x1400055c4  mov     [rbp+170h+var_F8], 4
0x1400055cc  test    r14, r14
0x1400055cf  jz      short loc_1400055E8
0x1400055d1  mov     rax, rcx
0x1400055d4  lea     rax, [rax+1]
0x1400055d8  cmp     [r14+rax*2], dx
0x1400055dd  jnz     short loc_1400055D4
0x1400055df  lea     eax, ds:2[rax*2]
0x1400055e6  jmp     short loc_1400055F4
0x1400055e8  lea     r14, dword_14008BB54
0x1400055ef  mov     eax, 2
0x1400055f4  mov     [rbp+170h+var_110], r14
0x1400055f8  mov     [rbp+170h+var_108], eax
0x1400055fb  mov     [rbp+170h+var_104], edx
0x1400055fe  lea     rax, [rsp+270h+var_20C]
0x140005603  mov     [rbp+170h+var_120], rax
0x140005607  mov     [rbp+170h+var_118], 4
0x14000560f  test    r15, r15
0x140005612  jz      short loc_140005624
0x140005614  mov     rax, rcx
0x140005617  inc     rax
0x14000561a  cmp     [r15+rax], dl
0x14000561e  jnz     short loc_140005617
0x140005620  inc     eax
0x140005622  jmp     short loc_140005630
0x140005624  lea     r15, word_14008BBFE
0x14000562b  mov     eax, 1
0x140005630  mov     [rbp+170h+var_130], r15
0x140005634  mov     [rbp+170h+var_128], eax
0x140005637  mov     [rbp+170h+var_124], edx
0x14000563a  lea     rax, [rsp+270h+var_240]
0x14000563f  mov     [rbp+170h+var_140], rax
0x140005643  mov     [rbp+170h+var_138], 4
0x14000564b  test    r12, r12
0x14000564e  jz      short loc_14000565D
0x140005650  inc     rcx
0x140005653  cmp     [r12+rcx], dl
0x140005657  jnz     short loc_140005650
0x140005659  inc     ecx
0x14000565b  jmp     short loc_140005669
0x14000565d  lea     r12, word_14008BBFE
0x140005664  mov     ecx, 1
0x140005669  mov     [rbp+170h+var_150], r12
0x14000566d  mov     [rbp+170h+var_148], ecx
0x140005670  mov     [rbp+170h+var_144], edx
0x140005673  lea     rax, [rsp+270h+var_230]
0x140005678  mov     [rbp+170h+var_160], rax
0x14000567c  mov     [rbp+170h+var_158], 4
0x140005684  lea     rax, [rsp+270h+var_208]
0x140005689  mov     [rbp+170h+var_170], rax
0x14000568d  mov     [rbp+170h+var_168], 8
0x140005695  lea     rax, [rsp+270h+var_228]
0x14000569a  mov     [rbp+170h+var_180], rax
0x14000569e  mov     [rbp+170h+var_178], 8
0x1400056a6  mov     dword ptr [rsp+270h+EventDescriptor.Id], 0B000000h
0x1400056ae  movzx   eax, cs:word_1400A13BC
0x1400056b5  mov     dword ptr [rsp+270h+EventDescriptor.Level], eax
0x1400056b9  mov     [rsp+270h+EventDescriptor.Keyword], rdx
0x1400056be  mov     rax, [r13+8]
0x1400056c2  mov     [rbp+170h+var_1A0], rax
0x1400056c6  movzx   eax, word ptr [rax]
0x1400056c9  mov     [rbp+170h+var_198], eax
0x1400056cc  mov     [rbp+170h+var_194], 2
0x1400056d3  lea     rax, word_1400A13C6
0x1400056da  mov     [rbp+170h+var_190], rax
0x1400056de  mov     [rbp+170h+var_188], 147h
0x1400056e5  mov     [rbp+170h+var_184], 1
0x1400056ec  lea     rax, _TraceLoggingMetadataEnd
0x1400056f3  lea     rdx, _TraceLoggingMetadata
0x1400056fa  sub     eax, edx
0x1400056fc  mov     dword ptr [rsp+270h+SRWLock], eax
0x140005700  mov     eax, dword ptr [rsp+270h+SRWLock]
0x140005704  lea     rax, [rbp+170h+var_1A0]
0x140005708  mov     [rsp+270h+UserData], rax
0x14000570d  mov     [rsp+270h+UserDataCount], 15h
0x140005715  lea     r8, [rdi+8]
0x140005719  mov     rcx, [r13+20h]
0x14000571d  jmp     loc_140005892
0x140005722  mov     rbx, [rcx+118h]
0x140005729  test    rbx, rbx
0x14000572c  jz      short loc_140005785
0x14000572e  add     rbx, 108h
0x140005735  mov     rcx, rbx; SRWLock
0x140005738  call    cs:__imp_AcquireSRWLockExclusive
0x14000573f  nop     dword ptr [rax+rax+00h]
0x140005744  lea     rax, [rsp+270h+var_228]
0x140005749  mov     [rax], r14
0x14000574c  mov     rcx, [rsp+270h+var_228]; SRWLock
0x140005751  test    rcx, rcx
0x140005754  jz      short loc_140005762
0x140005756  call    cs:__imp_ReleaseSRWLockExclusive
0x14000575d  nop     dword ptr [rax+rax+00h]
0x140005762  mov     rax, [rsi+110h]
0x140005769  mov     dword ptr [rax], 2
0x14000576f  test    rbx, rbx
0x140005772  jz      short loc_1400057B0
0x140005774  mov     rcx, rbx; SRWLock
0x140005777  call    cs:__imp_ReleaseSRWLockExclusive
0x14000577e  nop     dword ptr [rax+rax+00h]
0x140005783  jmp     short loc_1400057B0
0x140005785  lea     rax, [rsp+270h+var_208]
0x14000578a  mov     [rax], r14
0x14000578d  mov     rcx, [rsp+270h+var_208]; SRWLock
0x140005792  test    rcx, rcx
0x140005795  jz      short loc_1400057A3
0x140005797  call    cs:__imp_ReleaseSRWLockExclusive
0x14000579e  nop     dword ptr [rax+rax+00h]
0x1400057a3  mov     rax, [rsi+110h]
0x1400057aa  mov     dword ptr [rax], 2
0x1400057b0  call    ?Instance@BioIsoProvider@@KAPEAV1@XZ; BioIsoProvider::Instance(void)
0x1400057b5  mov     rbx, [rax+8]
0x1400057b9  mov     eax, [rbx]
0x1400057bb  cmp     eax, 5
  ... truncated ...
```
