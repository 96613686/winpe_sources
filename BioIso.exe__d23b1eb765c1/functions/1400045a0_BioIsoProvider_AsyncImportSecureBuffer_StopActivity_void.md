# BioIsoProvider::AsyncImportSecureBuffer::StopActivity(void)

- ea: `0x1400045a0`
- end: `0x140004bfe`
- name: `?StopActivity@AsyncImportSecureBuffer@BioIsoProvider@@MEAAXXZ`
- size: `1630`
- prototype: `void __fastcall(BioIsoProvider::AsyncImportSecureBuffer *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140003eb0`
- `0x1400045a0`
- `0x14000d990`
- `0x14001bd40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140004611`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140004a58`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140004611`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140004a58`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000462f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004650`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004670`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004a76`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004a97`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004ab7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000462f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004650`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004670`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004a76`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004a97`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004ab7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004ae4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004ae4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140004bba`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140004bba`

## pseudocode

```c
void __fastcall BioIsoProvider::AsyncImportSecureBuffer::StopActivity(BioIsoProvider::AsyncImportSecureBuffer *this)
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
  int *v52; // [rsp+90h] [rbp-70h]
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
        v62 = word_1400A1072;
        v63 = 326;
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
    v52 = &dword_1400A11C4;
    v53 = 76;
    v54 = 1;
    v39 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(*(_QWORD *)(v37 + 32), &EventDescriptor, (LPCGUID)(v38 + 8), 0, 5u, &v51);
  }
LABEL_61:
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((BioIsoProvider::AsyncImportSecureBuffer *)((char *)this + 288));
}

```

## disassembly

```asm
0x1400045a0  push    rbp
0x1400045a2  push    rbx
0x1400045a3  push    rsi
0x1400045a4  push    rdi
0x1400045a5  push    r12
0x1400045a7  push    r13
0x1400045a9  push    r14
0x1400045ab  push    r15
0x1400045ad  lea     rbp, [rsp-138h]
0x1400045b5  sub     rsp, 238h
0x1400045bc  mov     rax, cs:__security_cookie
0x1400045c3  xor     rax, rsp
0x1400045c6  mov     [rbp+170h+var_50], rax
0x1400045cd  mov     rsi, rcx
0x1400045d0  xor     r14d, r14d
0x1400045d3  mov     rdi, [rcx+110h]
0x1400045da  mov     eax, [rdi+48h]
0x1400045dd  test    eax, eax
0x1400045df  jns     loc_140004A42
0x1400045e5  add     rdi, 50h ; 'P'
0x1400045e9  cmp     eax, [rdi+8]
0x1400045ec  jnz     loc_140004A42
0x1400045f2  mov     rbx, [rcx+118h]
0x1400045f9  test    rdi, rdi
0x1400045fc  jz      loc_140004A49
0x140004602  test    rbx, rbx
0x140004605  jz      short loc_14000465E
0x140004607  add     rbx, 108h
0x14000460e  mov     rcx, rbx; SRWLock
0x140004611  call    cs:__imp_AcquireSRWLockExclusive
0x140004618  nop     dword ptr [rax+rax+00h]
0x14000461d  lea     rax, [rsp+270h+SRWLock]
0x140004622  mov     [rax], r14
0x140004625  mov     rcx, [rsp+270h+SRWLock]; SRWLock
0x14000462a  test    rcx, rcx
0x14000462d  jz      short loc_14000463B
0x14000462f  call    cs:__imp_ReleaseSRWLockExclusive
0x140004636  nop     dword ptr [rax+rax+00h]
0x14000463b  mov     rax, [rsi+110h]
0x140004642  mov     dword ptr [rax], 2
0x140004648  test    rbx, rbx
0x14000464b  jz      short loc_140004689
0x14000464d  mov     rcx, rbx; SRWLock
0x140004650  call    cs:__imp_ReleaseSRWLockExclusive
0x140004657  nop     dword ptr [rax+rax+00h]
0x14000465c  jmp     short loc_140004689
0x14000465e  lea     rax, [rsp+270h+var_230]
0x140004663  mov     [rax], r14
0x140004666  mov     rcx, [rsp+270h+var_230]; SRWLock
0x14000466b  test    rcx, rcx
0x14000466e  jz      short loc_14000467C
0x140004670  call    cs:__imp_ReleaseSRWLockExclusive
0x140004677  nop     dword ptr [rax+rax+00h]
0x14000467c  mov     rax, [rsi+110h]
0x140004683  mov     dword ptr [rax], 2
0x140004689  call    ?Instance@BioIsoProvider@@KAPEAV1@XZ; BioIsoProvider::Instance(void)
0x14000468e  mov     r13, [rax+8]
0x140004692  mov     eax, [r13+0]
0x140004696  cmp     eax, 5
0x140004699  jbe     loc_140004BC7
0x14000469f  mov     rdx, [rdi+30h]
0x1400046a3  mov     eax, [rdi+44h]
0x1400046a6  mov     [rsp+270h+var_220], eax
0x1400046aa  mov     eax, [rdi+10h]
0x1400046ad  mov     [rsp+270h+var_21C], eax
0x1400046b1  mov     r8, [rdi+78h]
0x1400046b5  mov     r9, [rdi+70h]
0x1400046b9  mov     eax, [rdi+68h]
0x1400046bc  mov     [rsp+270h+var_218], eax
0x1400046c0  mov     r10, [rdi+60h]
0x1400046c4  mov     r11, [rdi+58h]
0x1400046c8  mov     eax, [rdi+50h]
0x1400046cb  mov     [rsp+270h+var_214], eax
0x1400046cf  mov     rbx, [rdi+48h]
0x1400046d3  mov     eax, [rdi+20h]
0x1400046d6  mov     [rsp+270h+var_210], eax
0x1400046da  mov     r14, [rdi+18h]
0x1400046de  mov     eax, [rdi]
0x1400046e0  mov     [rsp+270h+var_20C], eax
0x1400046e4  mov     r15, [rdi+80h]
0x1400046eb  mov     eax, [rdi+40h]
0x1400046ee  mov     [rsp+270h+var_240], eax
0x1400046f2  mov     r12, [rdi+38h]
0x1400046f6  mov     eax, [rdi+8]
0x1400046f9  mov     dword ptr [rsp+270h+var_230], eax
0x1400046fd  mov     [rsp+270h+var_208], 1000000h
0x140004706  mov     [rsp+270h+var_228], 0
0x14000470f  mov     rdi, [rsi+110h]
0x140004716  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14000471d  test    rdx, rdx
0x140004720  jz      short loc_140004732
0x140004722  mov     rax, rcx
0x140004725  inc     rax
0x140004728  cmp     byte ptr [rdx+rax], 0
0x14000472c  jnz     short loc_140004725
0x14000472e  inc     eax
0x140004730  jmp     short loc_14000473E
0x140004732  lea     rdx, word_14008BBFE
0x140004739  mov     eax, 1
0x14000473e  mov     [rbp+170h+var_60], rdx
0x140004745  mov     [rbp+170h+var_58], eax
0x14000474b  xor     edx, edx
0x14000474d  mov     [rbp+170h+var_54], edx
0x140004753  lea     rax, [rsp+270h+var_220]
0x140004758  mov     [rbp+170h+var_70], rax
0x14000475f  mov     [rbp+170h+var_68], 4
0x14000476a  lea     rax, [rsp+270h+var_21C]
0x14000476f  mov     [rbp+170h+var_80], rax
0x140004776  mov     [rbp+170h+var_78], 4
0x140004781  test    r8, r8
0x140004784  jz      short loc_1400047A4
0x140004786  mov     rax, rcx
0x140004789  nop     dword ptr [rax+00000000h]
0x140004790  lea     rax, [rax+1]
0x140004794  cmp     [r8+rax*2], dx
0x140004799  jnz     short loc_140004790
0x14000479b  lea     eax, ds:2[rax*2]
0x1400047a2  jmp     short loc_1400047B0
0x1400047a4  lea     r8, dword_14008BB54
0x1400047ab  mov     eax, 2
0x1400047b0  mov     [rbp+170h+var_90], r8
0x1400047b7  mov     [rbp+170h+var_88], eax
0x1400047bd  mov     [rbp+170h+var_84], edx
0x1400047c3  test    r9, r9
0x1400047c6  jz      short loc_1400047DD
0x1400047c8  mov     rax, rcx
0x1400047cb  nop     dword ptr [rax+rax+00h]
0x1400047d0  inc     rax
0x1400047d3  cmp     [r9+rax], dl
0x1400047d7  jnz     short loc_1400047D0
0x1400047d9  inc     eax
0x1400047db  jmp     short loc_1400047E9
0x1400047dd  lea     r9, word_14008BBFE
0x1400047e4  mov     eax, 1
0x1400047e9  mov     [rbp+170h+var_A0], r9
0x1400047f0  mov     [rbp+170h+var_98], eax
0x1400047f6  mov     [rbp+170h+var_94], edx
0x1400047fc  lea     rax, [rsp+270h+var_218]
0x140004801  mov     [rbp+170h+var_B0], rax
0x140004808  mov     [rbp+170h+var_A8], 4
0x140004813  test    r10, r10
0x140004816  jz      short loc_140004834
0x140004818  mov     rax, rcx
0x14000481b  nop     dword ptr [rax+rax+00h]
0x140004820  lea     rax, [rax+1]
0x140004824  cmp     [r10+rax*2], dx
0x140004829  jnz     short loc_140004820
0x14000482b  lea     eax, ds:2[rax*2]
0x140004832  jmp     short loc_140004840
0x140004834  lea     r10, dword_14008BB54
0x14000483b  mov     eax, 2
0x140004840  mov     [rbp+170h+var_C0], r10
0x140004847  mov     [rbp+170h+var_B8], eax
0x14000484d  mov     [rbp+170h+var_B4], edx
0x140004853  test    r11, r11
0x140004856  jz      short loc_14000486D
0x140004858  mov     rax, rcx
0x14000485b  nop     dword ptr [rax+rax+00h]
0x140004860  inc     rax
0x140004863  cmp     [r11+rax], dl
0x140004867  jnz     short loc_140004860
0x140004869  inc     eax
0x14000486b  jmp     short loc_140004879
0x14000486d  lea     r11, word_14008BBFE
0x140004874  mov     eax, 1
0x140004879  mov     [rbp+170h+var_D0], r11
0x140004880  mov     [rbp+170h+var_C8], eax
0x140004886  mov     [rbp+170h+var_C4], edx
0x14000488c  lea     rax, [rsp+270h+var_214]
0x140004891  mov     [rbp+170h+var_E0], rax
0x140004898  mov     [rbp+170h+var_D8], 4
0x1400048a3  test    rbx, rbx
0x1400048a6  jz      short loc_1400048BC
0x1400048a8  mov     rax, rcx
0x1400048ab  nop     dword ptr [rax+rax+00h]
0x1400048b0  inc     rax
0x1400048b3  cmp     [rbx+rax], dl
0x1400048b6  jnz     short loc_1400048B0
0x1400048b8  inc     eax
0x1400048ba  jmp     short loc_1400048C8
0x1400048bc  lea     rbx, word_14008BBFE
0x1400048c3  mov     eax, 1
0x1400048c8  mov     [rbp+170h+var_F0], rbx
0x1400048cf  mov     [rbp+170h+var_E8], eax
0x1400048d5  mov     [rbp+170h+var_E4], edx
0x1400048db  lea     rax, [rsp+270h+var_210]
0x1400048e0  mov     [rbp+170h+var_100], rax
0x1400048e4  mov     [rbp+170h+var_F8], 4
0x1400048ec  test    r14, r14
0x1400048ef  jz      short loc_140004908
0x1400048f1  mov     rax, rcx
0x1400048f4  lea     rax, [rax+1]
0x1400048f8  cmp     [r14+rax*2], dx
0x1400048fd  jnz     short loc_1400048F4
0x1400048ff  lea     eax, ds:2[rax*2]
0x140004906  jmp     short loc_140004914
0x140004908  lea     r14, dword_14008BB54
0x14000490f  mov     eax, 2
0x140004914  mov     [rbp+170h+var_110], r14
0x140004918  mov     [rbp+170h+var_108], eax
0x14000491b  mov     [rbp+170h+var_104], edx
0x14000491e  lea     rax, [rsp+270h+var_20C]
0x140004923  mov     [rbp+170h+var_120], rax
0x140004927  mov     [rbp+170h+var_118], 4
0x14000492f  test    r15, r15
0x140004932  jz      short loc_140004944
0x140004934  mov     rax, rcx
0x140004937  inc     rax
0x14000493a  cmp     [r15+rax], dl
0x14000493e  jnz     short loc_140004937
0x140004940  inc     eax
0x140004942  jmp     short loc_140004950
0x140004944  lea     r15, word_14008BBFE
0x14000494b  mov     eax, 1
0x140004950  mov     [rbp+170h+var_130], r15
0x140004954  mov     [rbp+170h+var_128], eax
0x140004957  mov     [rbp+170h+var_124], edx
0x14000495a  lea     rax, [rsp+270h+var_240]
0x14000495f  mov     [rbp+170h+var_140], rax
0x140004963  mov     [rbp+170h+var_138], 4
0x14000496b  test    r12, r12
0x14000496e  jz      short loc_14000497D
0x140004970  inc     rcx
0x140004973  cmp     [r12+rcx], dl
0x140004977  jnz     short loc_140004970
0x140004979  inc     ecx
0x14000497b  jmp     short loc_140004989
0x14000497d  lea     r12, word_14008BBFE
0x140004984  mov     ecx, 1
0x140004989  mov     [rbp+170h+var_150], r12
0x14000498d  mov     [rbp+170h+var_148], ecx
0x140004990  mov     [rbp+170h+var_144], edx
0x140004993  lea     rax, [rsp+270h+var_230]
0x140004998  mov     [rbp+170h+var_160], rax
0x14000499c  mov     [rbp+170h+var_158], 4
0x1400049a4  lea     rax, [rsp+270h+var_208]
0x1400049a9  mov     [rbp+170h+var_170], rax
0x1400049ad  mov     [rbp+170h+var_168], 8
0x1400049b5  lea     rax, [rsp+270h+var_228]
0x1400049ba  mov     [rbp+170h+var_180], rax
0x1400049be  mov     [rbp+170h+var_178], 8
0x1400049c6  mov     dword ptr [rsp+270h+EventDescriptor.Id], 0B000000h
0x1400049ce  movzx   eax, cs:word_1400A1068
0x1400049d5  mov     dword ptr [rsp+270h+EventDescriptor.Level], eax
0x1400049d9  mov     [rsp+270h+EventDescriptor.Keyword], rdx
0x1400049de  mov     rax, [r13+8]
0x1400049e2  mov     [rbp+170h+var_1A0], rax
0x1400049e6  movzx   eax, word ptr [rax]
0x1400049e9  mov     [rbp+170h+var_198], eax
0x1400049ec  mov     [rbp+170h+var_194], 2
0x1400049f3  lea     rax, word_1400A1072
0x1400049fa  mov     [rbp+170h+var_190], rax
0x1400049fe  mov     [rbp+170h+var_188], 146h
0x140004a05  mov     [rbp+170h+var_184], 1
0x140004a0c  lea     rax, _TraceLoggingMetadataEnd
0x140004a13  lea     rdx, _TraceLoggingMetadata
0x140004a1a  sub     eax, edx
0x140004a1c  mov     dword ptr [rsp+270h+SRWLock], eax
0x140004a20  mov     eax, dword ptr [rsp+270h+SRWLock]
0x140004a24  lea     rax, [rbp+170h+var_1A0]
0x140004a28  mov     [rsp+270h+UserData], rax
0x140004a2d  mov     [rsp+270h+UserDataCount], 15h
0x140004a35  lea     r8, [rdi+8]
0x140004a39  mov     rcx, [r13+20h]
0x140004a3d  jmp     loc_140004BB2
0x140004a42  mov     rbx, [rcx+118h]
0x140004a49  test    rbx, rbx
0x140004a4c  jz      short loc_140004AA5
0x140004a4e  add     rbx, 108h
0x140004a55  mov     rcx, rbx; SRWLock
0x140004a58  call    cs:__imp_AcquireSRWLockExclusive
0x140004a5f  nop     dword ptr [rax+rax+00h]
0x140004a64  lea     rax, [rsp+270h+var_228]
0x140004a69  mov     [rax], r14
0x140004a6c  mov     rcx, [rsp+270h+var_228]; SRWLock
0x140004a71  test    rcx, rcx
0x140004a74  jz      short loc_140004A82
0x140004a76  call    cs:__imp_ReleaseSRWLockExclusive
0x140004a7d  nop     dword ptr [rax+rax+00h]
0x140004a82  mov     rax, [rsi+110h]
0x140004a89  mov     dword ptr [rax], 2
0x140004a8f  test    rbx, rbx
0x140004a92  jz      short loc_140004AD0
0x140004a94  mov     rcx, rbx; SRWLock
0x140004a97  call    cs:__imp_ReleaseSRWLockExclusive
0x140004a9e  nop     dword ptr [rax+rax+00h]
0x140004aa3  jmp     short loc_140004AD0
0x140004aa5  lea     rax, [rsp+270h+var_208]
0x140004aaa  mov     [rax], r14
0x140004aad  mov     rcx, [rsp+270h+var_208]; SRWLock
0x140004ab2  test    rcx, rcx
0x140004ab5  jz      short loc_140004AC3
0x140004ab7  call    cs:__imp_ReleaseSRWLockExclusive
0x140004abe  nop     dword ptr [rax+rax+00h]
0x140004ac3  mov     rax, [rsi+110h]
0x140004aca  mov     dword ptr [rax], 2
0x140004ad0  call    ?Instance@BioIsoProvider@@KAPEAV1@XZ; BioIsoProvider::Instance(void)
0x140004ad5  mov     rbx, [rax+8]
0x140004ad9  mov     eax, [rbx]
0x140004adb  cmp     eax, 5
  ... truncated ...
```
