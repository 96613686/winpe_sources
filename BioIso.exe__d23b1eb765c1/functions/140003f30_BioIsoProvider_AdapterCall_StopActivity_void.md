# BioIsoProvider::AdapterCall::StopActivity(void)

- ea: `0x140003f30`
- end: `0x14000458e`
- name: `?StopActivity@AdapterCall@BioIsoProvider@@MEAAXXZ`
- size: `1630`
- prototype: `void __fastcall(BioIsoProvider::AdapterCall *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140003eb0`
- `0x140003f30`
- `0x14000d990`
- `0x14001bd40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140003fa1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400043e8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140003fa1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400043e8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140003fbf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140003fe0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004000`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004406`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004427`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004447`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140003fbf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140003fe0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004000`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004406`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004427`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140004447`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004474`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004474`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x14000454a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x14000454a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall BioIsoProvider::AdapterCall::StopActivity(BioIsoProvider::AdapterCall *this)
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
  __int64 *v52; // [rsp+90h] [rbp-70h]
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
        v62 = word_140095D92;
        v63 = 314;
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
    v52 = qword_140095ED8;
    v53 = 64;
    v54 = 1;
    v39 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(*(_QWORD *)(v37 + 32), &EventDescriptor, (LPCGUID)(v38 + 8), 0, 5u, &v51);
  }
LABEL_61:
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((BioIsoProvider::AdapterCall *)((char *)this + 288));
}

```

## disassembly

```asm
0x140003f30  push    rbp
0x140003f32  push    rbx
0x140003f33  push    rsi
0x140003f34  push    rdi
0x140003f35  push    r12
0x140003f37  push    r13
0x140003f39  push    r14
0x140003f3b  push    r15
0x140003f3d  lea     rbp, [rsp-138h]
0x140003f45  sub     rsp, 238h
0x140003f4c  mov     rax, cs:__security_cookie
0x140003f53  xor     rax, rsp
0x140003f56  mov     [rbp+170h+var_50], rax
0x140003f5d  mov     rsi, rcx
0x140003f60  xor     r14d, r14d
0x140003f63  mov     rdi, [rcx+110h]
0x140003f6a  mov     eax, [rdi+48h]
0x140003f6d  test    eax, eax
0x140003f6f  jns     loc_1400043D2
0x140003f75  add     rdi, 50h ; 'P'
0x140003f79  cmp     eax, [rdi+8]
0x140003f7c  jnz     loc_1400043D2
0x140003f82  mov     rbx, [rcx+118h]
0x140003f89  test    rdi, rdi
0x140003f8c  jz      loc_1400043D9
0x140003f92  test    rbx, rbx
0x140003f95  jz      short loc_140003FEE
0x140003f97  add     rbx, 108h
0x140003f9e  mov     rcx, rbx; SRWLock
0x140003fa1  call    cs:__imp_AcquireSRWLockExclusive
0x140003fa8  nop     dword ptr [rax+rax+00h]
0x140003fad  lea     rax, [rsp+270h+SRWLock]
0x140003fb2  mov     [rax], r14
0x140003fb5  mov     rcx, [rsp+270h+SRWLock]; SRWLock
0x140003fba  test    rcx, rcx
0x140003fbd  jz      short loc_140003FCB
0x140003fbf  call    cs:__imp_ReleaseSRWLockExclusive
0x140003fc6  nop     dword ptr [rax+rax+00h]
0x140003fcb  mov     rax, [rsi+110h]
0x140003fd2  mov     dword ptr [rax], 2
0x140003fd8  test    rbx, rbx
0x140003fdb  jz      short loc_140004019
0x140003fdd  mov     rcx, rbx; SRWLock
0x140003fe0  call    cs:__imp_ReleaseSRWLockExclusive
0x140003fe7  nop     dword ptr [rax+rax+00h]
0x140003fec  jmp     short loc_140004019
0x140003fee  lea     rax, [rsp+270h+var_230]
0x140003ff3  mov     [rax], r14
0x140003ff6  mov     rcx, [rsp+270h+var_230]; SRWLock
0x140003ffb  test    rcx, rcx
0x140003ffe  jz      short loc_14000400C
0x140004000  call    cs:__imp_ReleaseSRWLockExclusive
0x140004007  nop     dword ptr [rax+rax+00h]
0x14000400c  mov     rax, [rsi+110h]
0x140004013  mov     dword ptr [rax], 2
0x140004019  call    ?Instance@BioIsoProvider@@KAPEAV1@XZ; BioIsoProvider::Instance(void)
0x14000401e  mov     r13, [rax+8]
0x140004022  mov     eax, [r13+0]
0x140004026  cmp     eax, 5
0x140004029  jbe     loc_140004557
0x14000402f  mov     rdx, [rdi+30h]
0x140004033  mov     eax, [rdi+44h]
0x140004036  mov     [rsp+270h+var_220], eax
0x14000403a  mov     eax, [rdi+10h]
0x14000403d  mov     [rsp+270h+var_21C], eax
0x140004041  mov     r8, [rdi+78h]
0x140004045  mov     r9, [rdi+70h]
0x140004049  mov     eax, [rdi+68h]
0x14000404c  mov     [rsp+270h+var_218], eax
0x140004050  mov     r10, [rdi+60h]
0x140004054  mov     r11, [rdi+58h]
0x140004058  mov     eax, [rdi+50h]
0x14000405b  mov     [rsp+270h+var_214], eax
0x14000405f  mov     rbx, [rdi+48h]
0x140004063  mov     eax, [rdi+20h]
0x140004066  mov     [rsp+270h+var_210], eax
0x14000406a  mov     r14, [rdi+18h]
0x14000406e  mov     eax, [rdi]
0x140004070  mov     [rsp+270h+var_20C], eax
0x140004074  mov     r15, [rdi+80h]
0x14000407b  mov     eax, [rdi+40h]
0x14000407e  mov     [rsp+270h+var_240], eax
0x140004082  mov     r12, [rdi+38h]
0x140004086  mov     eax, [rdi+8]
0x140004089  mov     dword ptr [rsp+270h+var_230], eax
0x14000408d  mov     [rsp+270h+var_208], 1000000h
0x140004096  mov     [rsp+270h+var_228], 0
0x14000409f  mov     rdi, [rsi+110h]
0x1400040a6  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1400040ad  test    rdx, rdx
0x1400040b0  jz      short loc_1400040C2
0x1400040b2  mov     rax, rcx
0x1400040b5  inc     rax
0x1400040b8  cmp     byte ptr [rdx+rax], 0
0x1400040bc  jnz     short loc_1400040B5
0x1400040be  inc     eax
0x1400040c0  jmp     short loc_1400040CE
0x1400040c2  lea     rdx, word_14008BBFE
0x1400040c9  mov     eax, 1
0x1400040ce  mov     [rbp+170h+var_60], rdx
0x1400040d5  mov     [rbp+170h+var_58], eax
0x1400040db  xor     edx, edx
0x1400040dd  mov     [rbp+170h+var_54], edx
0x1400040e3  lea     rax, [rsp+270h+var_220]
0x1400040e8  mov     [rbp+170h+var_70], rax
0x1400040ef  mov     [rbp+170h+var_68], 4
0x1400040fa  lea     rax, [rsp+270h+var_21C]
0x1400040ff  mov     [rbp+170h+var_80], rax
0x140004106  mov     [rbp+170h+var_78], 4
0x140004111  test    r8, r8
0x140004114  jz      short loc_140004134
0x140004116  mov     rax, rcx
0x140004119  nop     dword ptr [rax+00000000h]
0x140004120  lea     rax, [rax+1]
0x140004124  cmp     [r8+rax*2], dx
0x140004129  jnz     short loc_140004120
0x14000412b  lea     eax, ds:2[rax*2]
0x140004132  jmp     short loc_140004140
0x140004134  lea     r8, dword_14008BB54
0x14000413b  mov     eax, 2
0x140004140  mov     [rbp+170h+var_90], r8
0x140004147  mov     [rbp+170h+var_88], eax
0x14000414d  mov     [rbp+170h+var_84], edx
0x140004153  test    r9, r9
0x140004156  jz      short loc_14000416D
0x140004158  mov     rax, rcx
0x14000415b  nop     dword ptr [rax+rax+00h]
0x140004160  inc     rax
0x140004163  cmp     [r9+rax], dl
0x140004167  jnz     short loc_140004160
0x140004169  inc     eax
0x14000416b  jmp     short loc_140004179
0x14000416d  lea     r9, word_14008BBFE
0x140004174  mov     eax, 1
0x140004179  mov     [rbp+170h+var_A0], r9
0x140004180  mov     [rbp+170h+var_98], eax
0x140004186  mov     [rbp+170h+var_94], edx
0x14000418c  lea     rax, [rsp+270h+var_218]
0x140004191  mov     [rbp+170h+var_B0], rax
0x140004198  mov     [rbp+170h+var_A8], 4
0x1400041a3  test    r10, r10
0x1400041a6  jz      short loc_1400041C4
0x1400041a8  mov     rax, rcx
0x1400041ab  nop     dword ptr [rax+rax+00h]
0x1400041b0  lea     rax, [rax+1]
0x1400041b4  cmp     [r10+rax*2], dx
0x1400041b9  jnz     short loc_1400041B0
0x1400041bb  lea     eax, ds:2[rax*2]
0x1400041c2  jmp     short loc_1400041D0
0x1400041c4  lea     r10, dword_14008BB54
0x1400041cb  mov     eax, 2
0x1400041d0  mov     [rbp+170h+var_C0], r10
0x1400041d7  mov     [rbp+170h+var_B8], eax
0x1400041dd  mov     [rbp+170h+var_B4], edx
0x1400041e3  test    r11, r11
0x1400041e6  jz      short loc_1400041FD
0x1400041e8  mov     rax, rcx
0x1400041eb  nop     dword ptr [rax+rax+00h]
0x1400041f0  inc     rax
0x1400041f3  cmp     [r11+rax], dl
0x1400041f7  jnz     short loc_1400041F0
0x1400041f9  inc     eax
0x1400041fb  jmp     short loc_140004209
0x1400041fd  lea     r11, word_14008BBFE
0x140004204  mov     eax, 1
0x140004209  mov     [rbp+170h+var_D0], r11
0x140004210  mov     [rbp+170h+var_C8], eax
0x140004216  mov     [rbp+170h+var_C4], edx
0x14000421c  lea     rax, [rsp+270h+var_214]
0x140004221  mov     [rbp+170h+var_E0], rax
0x140004228  mov     [rbp+170h+var_D8], 4
0x140004233  test    rbx, rbx
0x140004236  jz      short loc_14000424C
0x140004238  mov     rax, rcx
0x14000423b  nop     dword ptr [rax+rax+00h]
0x140004240  inc     rax
0x140004243  cmp     [rbx+rax], dl
0x140004246  jnz     short loc_140004240
0x140004248  inc     eax
0x14000424a  jmp     short loc_140004258
0x14000424c  lea     rbx, word_14008BBFE
0x140004253  mov     eax, 1
0x140004258  mov     [rbp+170h+var_F0], rbx
0x14000425f  mov     [rbp+170h+var_E8], eax
0x140004265  mov     [rbp+170h+var_E4], edx
0x14000426b  lea     rax, [rsp+270h+var_210]
0x140004270  mov     [rbp+170h+var_100], rax
0x140004274  mov     [rbp+170h+var_F8], 4
0x14000427c  test    r14, r14
0x14000427f  jz      short loc_140004298
0x140004281  mov     rax, rcx
0x140004284  lea     rax, [rax+1]
0x140004288  cmp     [r14+rax*2], dx
0x14000428d  jnz     short loc_140004284
0x14000428f  lea     eax, ds:2[rax*2]
0x140004296  jmp     short loc_1400042A4
0x140004298  lea     r14, dword_14008BB54
0x14000429f  mov     eax, 2
0x1400042a4  mov     [rbp+170h+var_110], r14
0x1400042a8  mov     [rbp+170h+var_108], eax
0x1400042ab  mov     [rbp+170h+var_104], edx
0x1400042ae  lea     rax, [rsp+270h+var_20C]
0x1400042b3  mov     [rbp+170h+var_120], rax
0x1400042b7  mov     [rbp+170h+var_118], 4
0x1400042bf  test    r15, r15
0x1400042c2  jz      short loc_1400042D4
0x1400042c4  mov     rax, rcx
0x1400042c7  inc     rax
0x1400042ca  cmp     [r15+rax], dl
0x1400042ce  jnz     short loc_1400042C7
0x1400042d0  inc     eax
0x1400042d2  jmp     short loc_1400042E0
0x1400042d4  lea     r15, word_14008BBFE
0x1400042db  mov     eax, 1
0x1400042e0  mov     [rbp+170h+var_130], r15
0x1400042e4  mov     [rbp+170h+var_128], eax
0x1400042e7  mov     [rbp+170h+var_124], edx
0x1400042ea  lea     rax, [rsp+270h+var_240]
0x1400042ef  mov     [rbp+170h+var_140], rax
0x1400042f3  mov     [rbp+170h+var_138], 4
0x1400042fb  test    r12, r12
0x1400042fe  jz      short loc_14000430D
0x140004300  inc     rcx
0x140004303  cmp     [r12+rcx], dl
0x140004307  jnz     short loc_140004300
0x140004309  inc     ecx
0x14000430b  jmp     short loc_140004319
0x14000430d  lea     r12, word_14008BBFE
0x140004314  mov     ecx, 1
0x140004319  mov     [rbp+170h+var_150], r12
0x14000431d  mov     [rbp+170h+var_148], ecx
0x140004320  mov     [rbp+170h+var_144], edx
0x140004323  lea     rax, [rsp+270h+var_230]
0x140004328  mov     [rbp+170h+var_160], rax
0x14000432c  mov     [rbp+170h+var_158], 4
0x140004334  lea     rax, [rsp+270h+var_208]
0x140004339  mov     [rbp+170h+var_170], rax
0x14000433d  mov     [rbp+170h+var_168], 8
0x140004345  lea     rax, [rsp+270h+var_228]
0x14000434a  mov     [rbp+170h+var_180], rax
0x14000434e  mov     [rbp+170h+var_178], 8
0x140004356  mov     dword ptr [rsp+270h+EventDescriptor.Id], 0B000000h
0x14000435e  movzx   eax, cs:word_140095D88
0x140004365  mov     dword ptr [rsp+270h+EventDescriptor.Level], eax
0x140004369  mov     [rsp+270h+EventDescriptor.Keyword], rdx
0x14000436e  mov     rax, [r13+8]
0x140004372  mov     [rbp+170h+var_1A0], rax
0x140004376  movzx   eax, word ptr [rax]
0x140004379  mov     [rbp+170h+var_198], eax
0x14000437c  mov     [rbp+170h+var_194], 2
0x140004383  lea     rax, word_140095D92
0x14000438a  mov     [rbp+170h+var_190], rax
0x14000438e  mov     [rbp+170h+var_188], 13Ah
0x140004395  mov     [rbp+170h+var_184], 1
0x14000439c  lea     rax, _TraceLoggingMetadataEnd
0x1400043a3  lea     rdx, _TraceLoggingMetadata
0x1400043aa  sub     eax, edx
0x1400043ac  mov     dword ptr [rsp+270h+SRWLock], eax
0x1400043b0  mov     eax, dword ptr [rsp+270h+SRWLock]
0x1400043b4  lea     rax, [rbp+170h+var_1A0]
0x1400043b8  mov     [rsp+270h+UserData], rax
0x1400043bd  mov     [rsp+270h+UserDataCount], 15h
0x1400043c5  lea     r8, [rdi+8]
0x1400043c9  mov     rcx, [r13+20h]
0x1400043cd  jmp     loc_140004542
0x1400043d2  mov     rbx, [rcx+118h]
0x1400043d9  test    rbx, rbx
0x1400043dc  jz      short loc_140004435
0x1400043de  add     rbx, 108h
0x1400043e5  mov     rcx, rbx; SRWLock
0x1400043e8  call    cs:__imp_AcquireSRWLockExclusive
0x1400043ef  nop     dword ptr [rax+rax+00h]
0x1400043f4  lea     rax, [rsp+270h+var_228]
0x1400043f9  mov     [rax], r14
0x1400043fc  mov     rcx, [rsp+270h+var_228]; SRWLock
0x140004401  test    rcx, rcx
0x140004404  jz      short loc_140004412
0x140004406  call    cs:__imp_ReleaseSRWLockExclusive
0x14000440d  nop     dword ptr [rax+rax+00h]
0x140004412  mov     rax, [rsi+110h]
0x140004419  mov     dword ptr [rax], 2
0x14000441f  test    rbx, rbx
0x140004422  jz      short loc_140004460
0x140004424  mov     rcx, rbx; SRWLock
0x140004427  call    cs:__imp_ReleaseSRWLockExclusive
0x14000442e  nop     dword ptr [rax+rax+00h]
0x140004433  jmp     short loc_140004460
0x140004435  lea     rax, [rsp+270h+var_208]
0x14000443a  mov     [rax], r14
0x14000443d  mov     rcx, [rsp+270h+var_208]; SRWLock
0x140004442  test    rcx, rcx
0x140004445  jz      short loc_140004453
0x140004447  call    cs:__imp_ReleaseSRWLockExclusive
0x14000444e  nop     dword ptr [rax+rax+00h]
0x140004453  mov     rax, [rsi+110h]
0x14000445a  mov     dword ptr [rax], 2
0x140004460  call    ?Instance@BioIsoProvider@@KAPEAV1@XZ; BioIsoProvider::Instance(void)
0x140004465  mov     rbx, [rax+8]
0x140004469  mov     eax, [rbx]
0x14000446b  cmp     eax, 5
  ... truncated ...
```
