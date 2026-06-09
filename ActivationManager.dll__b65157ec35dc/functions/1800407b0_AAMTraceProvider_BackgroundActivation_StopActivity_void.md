# AAMTraceProvider::BackgroundActivation::StopActivity(void)

- ea: `0x1800407b0`
- end: `0x180040e10`
- name: `?StopActivity@BackgroundActivation@AAMTraceProvider@@MEAAXXZ`
- size: `1632`
- prototype: `void __fastcall(AAMTraceProvider::BackgroundActivation *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180024840`
- `0x180035e10`
- `0x1800407b0`
- `0x18005ae90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180040839`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180040854`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004086e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180040c84`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180040c9f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180040cb9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180040839`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180040854`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004086e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180040c84`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180040c9f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180040cb9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180040821`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180040c6c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180040821`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180040c6c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180040cff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180040cff`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180040dd3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180040dd3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall AAMTraceProvider::BackgroundActivation::StopActivity(AAMTraceProvider::BackgroundActivation *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  RTL_SRWLOCK *v5; // rbx
  RTL_SRWLOCK *v6; // rbx
  __int64 v7; // r13
  const unsigned __int16 *v8; // rdx
  const WCHAR *v9; // r8
  const unsigned __int16 *v10; // r9
  const WCHAR *v11; // r10
  const unsigned __int16 *v12; // r11
  const unsigned __int16 *v13; // rbx
  const WCHAR *v14; // r14
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
  char *v62; // [rsp+E0h] [rbp-20h]
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
  const WCHAR *v81; // [rsp+160h] [rbp+60h]
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
  const WCHAR *v94; // [rsp+1B0h] [rbp+B0h]
  int v95; // [rsp+1B8h] [rbp+B8h]
  int v96; // [rsp+1BCh] [rbp+BCh]
  int *v97; // [rsp+1C0h] [rbp+C0h]
  __int64 v98; // [rsp+1C8h] [rbp+C8h]
  const unsigned __int16 *v99; // [rsp+1D0h] [rbp+D0h]
  int v100; // [rsp+1D8h] [rbp+D8h]
  int v101; // [rsp+1DCh] [rbp+DCh]
  const WCHAR *v102; // [rsp+1E0h] [rbp+E0h]
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
      v7 = *((_QWORD *)AAMTraceProvider::Instance() + 1);
      if ( *(_DWORD *)v7 > 5u && (*(_QWORD *)(v7 + 16) & 1) != 0 && (*(_QWORD *)(v7 + 24) & 1LL) == *(_QWORD *)(v7 + 24) )
      {
        v8 = (const unsigned __int16 *)*((_QWORD *)v4 + 6);
        v43 = v4[17];
        v44 = v4[4];
        v9 = (const WCHAR *)*((_QWORD *)v4 + 15);
        v10 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
        v45 = v4[26];
        v11 = (const WCHAR *)*((_QWORD *)v4 + 12);
        v12 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
        v46 = v4[20];
        v13 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
        v47 = v4[8];
        v14 = (const WCHAR *)*((_QWORD *)v4 + 3);
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
          v8 = &word_1800AD9E6;
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
          while ( v9[v21] );
          v22 = 2 * v21 + 2;
        }
        else
        {
          v9 = &Src;
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
          v10 = &word_1800AD9E6;
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
          while ( v11[v25] );
          v26 = 2 * v25 + 2;
        }
        else
        {
          v11 = &Src;
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
          v12 = &word_1800AD9E6;
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
          v13 = &word_1800AD9E6;
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
          while ( v14[v31] );
          v32 = 2 * v31 + 2;
        }
        else
        {
          v14 = &Src;
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
          v15 = &word_1800AD9E6;
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
          v16 = &word_1800AD9E6;
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
        EventDescriptor.Keyword = 1;
        UserData.Ptr = *(_QWORD *)(v7 + 8);
        UserData.Size = *(unsigned __int16 *)UserData.Ptr;
        UserData.Reserved = 2;
        v62 = &byte_1800B7D77;
        v63 = 323;
        v64 = 1;
        LODWORD(SRWLock) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(*(_QWORD *)(v7 + 32), &EventDescriptor, (LPCGUID)(v17 + 8), 0, 0x15u, &UserData);
      }
      goto LABEL_65;
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
  v37 = *((_QWORD *)AAMTraceProvider::Instance() + 1);
  if ( *(_DWORD *)v37 > 5u && (*(_QWORD *)(v37 + 16) & 1) != 0 && (*(_QWORD *)(v37 + 24) & 1LL) == *(_QWORD *)(v37 + 24) )
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
    EventDescriptor.Keyword = 1;
    v51.Ptr = *(_QWORD *)(v37 + 8);
    v51.Size = *(unsigned __int16 *)v51.Ptr;
    v51.Reserved = 2;
    v52 = &word_1800B7EC6;
    v53 = 73;
    v54 = 1;
    v39 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(*(_QWORD *)(v37 + 32), &EventDescriptor, (LPCGUID)(v38 + 8), 0, 5u, &v51);
  }
LABEL_65:
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((AAMTraceProvider::BackgroundActivation *)((char *)this + 288));
}

```

## disassembly

```asm
0x1800407b0  push    rbp
0x1800407b2  push    rbx
0x1800407b3  push    rsi
0x1800407b4  push    rdi
0x1800407b5  push    r12
0x1800407b7  push    r13
0x1800407b9  push    r14
0x1800407bb  push    r15
0x1800407bd  lea     rbp, [rsp-138h]
0x1800407c5  sub     rsp, 238h
0x1800407cc  mov     rax, cs:__security_cookie
0x1800407d3  xor     rax, rsp
0x1800407d6  mov     [rbp+170h+var_50], rax
0x1800407dd  mov     rsi, rcx
0x1800407e0  xor     r14d, r14d
0x1800407e3  mov     rdi, [rcx+110h]
0x1800407ea  mov     eax, [rdi+48h]
0x1800407ed  test    eax, eax
0x1800407ef  jns     loc_180040C56
0x1800407f5  add     rdi, 50h ; 'P'
0x1800407f9  cmp     eax, [rdi+8]
0x1800407fc  jnz     loc_180040C56
0x180040802  mov     rbx, [rcx+118h]
0x180040809  test    rdi, rdi
0x18004080c  jz      loc_180040C5D
0x180040812  test    rbx, rbx
0x180040815  jz      short loc_18004085C
0x180040817  add     rbx, 108h
0x18004081e  mov     rcx, rbx; SRWLock
0x180040821  call    cs:__imp_AcquireSRWLockExclusive
0x180040827  lea     rax, [rsp+270h+SRWLock]
0x18004082c  mov     [rax], r14
0x18004082f  mov     rcx, [rsp+270h+SRWLock]; SRWLock
0x180040834  test    rcx, rcx
0x180040837  jz      short loc_18004083F
0x180040839  call    cs:__imp_ReleaseSRWLockExclusive
0x18004083f  mov     rax, [rsi+110h]
0x180040846  mov     dword ptr [rax], 2
0x18004084c  test    rbx, rbx
0x18004084f  jz      short loc_180040881
0x180040851  mov     rcx, rbx; SRWLock
0x180040854  call    cs:__imp_ReleaseSRWLockExclusive
0x18004085a  jmp     short loc_180040881
0x18004085c  lea     rax, [rsp+270h+var_230]
0x180040861  mov     [rax], r14
0x180040864  mov     rcx, [rsp+270h+var_230]; SRWLock
0x180040869  test    rcx, rcx
0x18004086c  jz      short loc_180040874
0x18004086e  call    cs:__imp_ReleaseSRWLockExclusive
0x180040874  mov     rax, [rsi+110h]
0x18004087b  mov     dword ptr [rax], 2
0x180040881  call    ?Instance@AAMTraceProvider@@KAPEAV1@XZ; AAMTraceProvider::Instance(void)
0x180040886  mov     r13, [rax+8]
0x18004088a  mov     eax, [r13+0]
0x18004088e  cmp     eax, 5
0x180040891  jbe     loc_180040DDA
0x180040897  mov     rcx, [r13+18h]
0x18004089b  mov     rax, [r13+10h]
0x18004089f  test    al, 1
0x1800408a1  jz      loc_180040DDA
0x1800408a7  mov     rax, rcx
0x1800408aa  and     eax, 1
0x1800408ad  cmp     rax, rcx
0x1800408b0  jnz     loc_180040DDA
0x1800408b6  mov     rdx, [rdi+30h]
0x1800408ba  mov     eax, [rdi+44h]
0x1800408bd  mov     [rsp+270h+var_220], eax
0x1800408c1  mov     eax, [rdi+10h]
0x1800408c4  mov     [rsp+270h+var_21C], eax
0x1800408c8  mov     r8, [rdi+78h]
0x1800408cc  mov     r9, [rdi+70h]
0x1800408d0  mov     eax, [rdi+68h]
0x1800408d3  mov     [rsp+270h+var_218], eax
0x1800408d7  mov     r10, [rdi+60h]
0x1800408db  mov     r11, [rdi+58h]
0x1800408df  mov     eax, [rdi+50h]
0x1800408e2  mov     [rsp+270h+var_214], eax
0x1800408e6  mov     rbx, [rdi+48h]
0x1800408ea  mov     eax, [rdi+20h]
0x1800408ed  mov     [rsp+270h+var_210], eax
0x1800408f1  mov     r14, [rdi+18h]
0x1800408f5  mov     eax, [rdi]
0x1800408f7  mov     [rsp+270h+var_20C], eax
0x1800408fb  mov     r15, [rdi+80h]
0x180040902  mov     eax, [rdi+40h]
0x180040905  mov     [rsp+270h+var_240], eax
0x180040909  mov     r12, [rdi+38h]
0x18004090d  mov     eax, [rdi+8]
0x180040910  mov     dword ptr [rsp+270h+var_230], eax
0x180040914  mov     [rsp+270h+var_208], 1000000h
0x18004091d  mov     [rsp+270h+var_228], 0
0x180040926  mov     rdi, [rsi+110h]
0x18004092d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180040934  test    rdx, rdx
0x180040937  jz      short loc_18004094D
0x180040939  mov     rax, rcx
0x18004093c  nop     dword ptr [rax+00h]
0x180040940  inc     rax
0x180040943  cmp     byte ptr [rdx+rax], 0
0x180040947  jnz     short loc_180040940
0x180040949  inc     eax
0x18004094b  jmp     short loc_180040959
0x18004094d  lea     rdx, word_1800AD9E6
0x180040954  mov     eax, 1
0x180040959  mov     [rbp+170h+var_60], rdx
0x180040960  mov     [rbp+170h+var_58], eax
0x180040966  xor     edx, edx
0x180040968  mov     [rbp+170h+var_54], edx
0x18004096e  lea     rax, [rsp+270h+var_220]
0x180040973  mov     [rbp+170h+var_70], rax
0x18004097a  mov     [rbp+170h+var_68], 4
0x180040985  lea     rax, [rsp+270h+var_21C]
0x18004098a  mov     [rbp+170h+var_80], rax
0x180040991  mov     [rbp+170h+var_78], 4
0x18004099c  test    r8, r8
0x18004099f  jz      short loc_1800409B8
0x1800409a1  mov     rax, rcx
0x1800409a4  lea     rax, [rax+1]
0x1800409a8  cmp     [r8+rax*2], dx
0x1800409ad  jnz     short loc_1800409A4
0x1800409af  lea     eax, ds:2[rax*2]
0x1800409b6  jmp     short loc_1800409C4
0x1800409b8  lea     r8, Src
0x1800409bf  mov     eax, 2
0x1800409c4  mov     [rbp+170h+var_90], r8
0x1800409cb  mov     [rbp+170h+var_88], eax
0x1800409d1  mov     [rbp+170h+var_84], edx
0x1800409d7  test    r9, r9
0x1800409da  jz      short loc_1800409ED
0x1800409dc  mov     rax, rcx
0x1800409df  nop
0x1800409e0  inc     rax
0x1800409e3  cmp     [r9+rax], dl
0x1800409e7  jnz     short loc_1800409E0
0x1800409e9  inc     eax
0x1800409eb  jmp     short loc_1800409F9
0x1800409ed  lea     r9, word_1800AD9E6
0x1800409f4  mov     eax, 1
0x1800409f9  mov     [rbp+170h+var_A0], r9
0x180040a00  mov     [rbp+170h+var_98], eax
0x180040a06  mov     [rbp+170h+var_94], edx
0x180040a0c  lea     rax, [rsp+270h+var_218]
0x180040a11  mov     [rbp+170h+var_B0], rax
0x180040a18  mov     [rbp+170h+var_A8], 4
0x180040a23  test    r10, r10
0x180040a26  jz      short loc_180040A44
0x180040a28  mov     rax, rcx
0x180040a2b  nop     dword ptr [rax+rax+00h]
0x180040a30  lea     rax, [rax+1]
0x180040a34  cmp     [r10+rax*2], dx
0x180040a39  jnz     short loc_180040A30
0x180040a3b  lea     eax, ds:2[rax*2]
0x180040a42  jmp     short loc_180040A50
0x180040a44  lea     r10, Src
0x180040a4b  mov     eax, 2
0x180040a50  mov     [rbp+170h+var_C0], r10
0x180040a57  mov     [rbp+170h+var_B8], eax
0x180040a5d  mov     [rbp+170h+var_B4], edx
0x180040a63  test    r11, r11
0x180040a66  jz      short loc_180040A7D
0x180040a68  mov     rax, rcx
0x180040a6b  nop     dword ptr [rax+rax+00h]
0x180040a70  inc     rax
0x180040a73  cmp     [r11+rax], dl
0x180040a77  jnz     short loc_180040A70
0x180040a79  inc     eax
0x180040a7b  jmp     short loc_180040A89
0x180040a7d  lea     r11, word_1800AD9E6
0x180040a84  mov     eax, 1
0x180040a89  mov     [rbp+170h+var_D0], r11
0x180040a90  mov     [rbp+170h+var_C8], eax
0x180040a96  mov     [rbp+170h+var_C4], edx
0x180040a9c  lea     rax, [rsp+270h+var_214]
0x180040aa1  mov     [rbp+170h+var_E0], rax
0x180040aa8  mov     [rbp+170h+var_D8], 4
0x180040ab3  test    rbx, rbx
0x180040ab6  jz      short loc_180040ACC
0x180040ab8  mov     rax, rcx
0x180040abb  nop     dword ptr [rax+rax+00h]
0x180040ac0  inc     rax
0x180040ac3  cmp     [rbx+rax], dl
0x180040ac6  jnz     short loc_180040AC0
0x180040ac8  inc     eax
0x180040aca  jmp     short loc_180040AD8
0x180040acc  lea     rbx, word_1800AD9E6
0x180040ad3  mov     eax, 1
0x180040ad8  mov     [rbp+170h+var_F0], rbx
0x180040adf  mov     [rbp+170h+var_E8], eax
0x180040ae5  mov     [rbp+170h+var_E4], edx
0x180040aeb  lea     rax, [rsp+270h+var_210]
0x180040af0  mov     [rbp+170h+var_100], rax
0x180040af4  mov     [rbp+170h+var_F8], 4
0x180040afc  test    r14, r14
0x180040aff  jz      short loc_180040B18
0x180040b01  mov     rax, rcx
0x180040b04  lea     rax, [rax+1]
0x180040b08  cmp     [r14+rax*2], dx
0x180040b0d  jnz     short loc_180040B04
0x180040b0f  lea     eax, ds:2[rax*2]
0x180040b16  jmp     short loc_180040B24
0x180040b18  lea     r14, Src
0x180040b1f  mov     eax, 2
0x180040b24  mov     [rbp+170h+var_110], r14
0x180040b28  mov     [rbp+170h+var_108], eax
0x180040b2b  mov     [rbp+170h+var_104], edx
0x180040b2e  lea     rax, [rsp+270h+var_20C]
0x180040b33  mov     [rbp+170h+var_120], rax
0x180040b37  mov     [rbp+170h+var_118], 4
0x180040b3f  test    r15, r15
0x180040b42  jz      short loc_180040B54
0x180040b44  mov     rax, rcx
0x180040b47  inc     rax
0x180040b4a  cmp     [r15+rax], dl
0x180040b4e  jnz     short loc_180040B47
0x180040b50  inc     eax
0x180040b52  jmp     short loc_180040B60
0x180040b54  lea     r15, word_1800AD9E6
0x180040b5b  mov     eax, 1
0x180040b60  mov     [rbp+170h+var_130], r15
0x180040b64  mov     [rbp+170h+var_128], eax
0x180040b67  mov     [rbp+170h+var_124], edx
0x180040b6a  lea     rax, [rsp+270h+var_240]
0x180040b6f  mov     [rbp+170h+var_140], rax
0x180040b73  mov     [rbp+170h+var_138], 4
0x180040b7b  test    r12, r12
0x180040b7e  jz      short loc_180040B8D
0x180040b80  inc     rcx
0x180040b83  cmp     [r12+rcx], dl
0x180040b87  jnz     short loc_180040B80
0x180040b89  inc     ecx
0x180040b8b  jmp     short loc_180040B99
0x180040b8d  lea     r12, word_1800AD9E6
0x180040b94  mov     ecx, 1
0x180040b99  mov     [rbp+170h+var_150], r12
0x180040b9d  mov     [rbp+170h+var_148], ecx
0x180040ba0  mov     [rbp+170h+var_144], edx
0x180040ba3  lea     rax, [rsp+270h+var_230]
0x180040ba8  mov     [rbp+170h+var_160], rax
0x180040bac  mov     [rbp+170h+var_158], 4
0x180040bb4  lea     rax, [rsp+270h+var_208]
0x180040bb9  mov     [rbp+170h+var_170], rax
0x180040bbd  mov     [rbp+170h+var_168], 8
0x180040bc5  lea     rax, [rsp+270h+var_228]
0x180040bca  mov     [rbp+170h+var_180], rax
0x180040bce  mov     [rbp+170h+var_178], 8
0x180040bd6  mov     dword ptr [rsp+270h+EventDescriptor.Id], 0B000000h
0x180040bde  movzx   eax, cs:word_1800B7D6D
0x180040be5  mov     dword ptr [rsp+270h+EventDescriptor.Level], eax
0x180040be9  mov     [rsp+270h+EventDescriptor.Keyword], 1
0x180040bf2  mov     rax, [r13+8]
0x180040bf6  mov     [rbp+170h+var_1A0], rax
0x180040bfa  movzx   eax, word ptr [rax]
0x180040bfd  mov     [rbp+170h+var_198], eax
0x180040c00  mov     [rbp+170h+var_194], 2
0x180040c07  lea     rax, byte_1800B7D77
0x180040c0e  mov     [rbp+170h+var_190], rax
0x180040c12  mov     [rbp+170h+var_188], 143h
0x180040c19  mov     [rbp+170h+var_184], 1
0x180040c20  lea     rax, _TraceLoggingMetadataEnd
0x180040c27  lea     rdx, _TraceLoggingMetadata
0x180040c2e  sub     eax, edx
0x180040c30  mov     dword ptr [rsp+270h+SRWLock], eax
0x180040c34  mov     eax, dword ptr [rsp+270h+SRWLock]
0x180040c38  lea     rax, [rbp+170h+var_1A0]
0x180040c3c  mov     [rsp+270h+UserData], rax
0x180040c41  mov     [rsp+270h+UserDataCount], 15h
0x180040c49  lea     r8, [rdi+8]
0x180040c4d  mov     rcx, [r13+20h]
0x180040c51  jmp     loc_180040DCB
0x180040c56  mov     rbx, [rcx+118h]
0x180040c5d  test    rbx, rbx
0x180040c60  jz      short loc_180040CA7
0x180040c62  add     rbx, 108h
0x180040c69  mov     rcx, rbx; SRWLock
0x180040c6c  call    cs:__imp_AcquireSRWLockExclusive
0x180040c72  lea     rax, [rsp+270h+var_228]
0x180040c77  mov     [rax], r14
0x180040c7a  mov     rcx, [rsp+270h+var_228]; SRWLock
0x180040c7f  test    rcx, rcx
0x180040c82  jz      short loc_180040C8A
0x180040c84  call    cs:__imp_ReleaseSRWLockExclusive
0x180040c8a  mov     rax, [rsi+110h]
0x180040c91  mov     dword ptr [rax], 2
0x180040c97  test    rbx, rbx
0x180040c9a  jz      short loc_180040CCC
0x180040c9c  mov     rcx, rbx; SRWLock
0x180040c9f  call    cs:__imp_ReleaseSRWLockExclusive
0x180040ca5  jmp     short loc_180040CCC
0x180040ca7  lea     rax, [rsp+270h+var_208]
0x180040cac  mov     [rax], r14
0x180040caf  mov     rcx, [rsp+270h+var_208]; SRWLock
0x180040cb4  test    rcx, rcx
0x180040cb7  jz      short loc_180040CBF
0x180040cb9  call    cs:__imp_ReleaseSRWLockExclusive
0x180040cbf  mov     rax, [rsi+110h]
0x180040cc6  mov     dword ptr [rax], 2
0x180040ccc  call    ?Instance@AAMTraceProvider@@KAPEAV1@XZ; AAMTraceProvider::Instance(void)
0x180040cd1  mov     rbx, [rax+8]
0x180040cd5  mov     eax, [rbx]
0x180040cd7  cmp     eax, 5
  ... truncated ...
```
