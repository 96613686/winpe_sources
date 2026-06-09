# Broker::SebPublishWnfEventCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)

- ea: `0x180017f40`
- end: `0x180018623`
- name: `?SebPublishWnfEventCallback@Broker@@YAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z`
- size: `1763`
- prototype: `int(Broker *__hidden this, struct _WNF_STATE_NAME, unsigned int, struct _WNF_TYPE_ID *, void *, const void *, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180005b0c`
- `0x180017cd0`
- `0x180017f40`
- `0x18001cf50`
- `0x180022230`
- `0x180022434`
- `0x180027010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180018025`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180018501`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800185f6`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180018025`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180018501`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800185f6`

## pseudocode

```c
__int64 __fastcall Broker::SebPublishWnfEventCallback(
        Broker *this,
        struct _WNF_STATE_NAME a2,
        __int64 a3,
        struct _WNF_TYPE_ID *a4,
        char *a5,
        const void *a6)
{
  ULONG v6; // ebx
  unsigned __int64 v8; // rdx
  __int64 v9; // r10
  __int64 v10; // r14
  unsigned int v11; // ebx
  int v12; // esi
  unsigned int v13; // r8d
  int v14; // eax
  int v15; // r8d
  __int64 *SessionInfo; // rax
  __int64 v17; // rsi
  volatile signed __int32 *v18; // rdi
  volatile signed __int32 *v19; // rbx
  bool v20; // cc
  __int64 v21; // rax
  const WCHAR *v22; // rcx
  __int64 v23; // rdx
  int v25; // r14d
  int v26; // esi
  char *v27; // r9
  __int64 v28; // r15
  unsigned int v29; // edi
  __int64 v30; // rdi
  __int64 v31; // r12
  __int64 v32; // rbx
  const void *v33; // rcx
  const struct _GUID *UserDataCount; // [rsp+20h] [rbp-E0h]
  Broker *v36; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v37; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v38; // [rsp+3Ch] [rbp-C4h] BYREF
  void *v39; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v40; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int128 Buf2; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v42; // [rsp+60h] [rbp-A0h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+68h] [rbp-98h] BYREF
  __int64 v44; // [rsp+78h] [rbp-88h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+80h] [rbp-80h] BYREF
  __int16 *v46; // [rsp+90h] [rbp-70h]
  int v47; // [rsp+98h] [rbp-68h]
  int v48; // [rsp+9Ch] [rbp-64h]
  Broker **v49; // [rsp+A0h] [rbp-60h]
  __int64 v50; // [rsp+A8h] [rbp-58h]
  void **v51; // [rsp+B0h] [rbp-50h]
  __int64 v52; // [rsp+B8h] [rbp-48h]
  Broker **v53; // [rsp+C0h] [rbp-40h]
  __int64 v54; // [rsp+C8h] [rbp-38h]
  struct _EVENT_DATA_DESCRIPTOR v55; // [rsp+D0h] [rbp-30h] BYREF
  __int16 *v56; // [rsp+E0h] [rbp-20h]
  int v57; // [rsp+E8h] [rbp-18h]
  int v58; // [rsp+ECh] [rbp-14h]
  EVENT_DESCRIPTOR *p_EventDescriptor; // [rsp+F0h] [rbp-10h]
  __int64 v60; // [rsp+F8h] [rbp-8h]
  __int64 v61; // [rsp+100h] [rbp+0h]
  __int64 v62; // [rsp+108h] [rbp+8h]
  void **v63; // [rsp+110h] [rbp+10h]
  __int64 v64; // [rsp+118h] [rbp+18h]
  __int64 *v65; // [rsp+120h] [rbp+20h]
  __int64 v66; // [rsp+128h] [rbp+28h]
  const WCHAR *v67; // [rsp+130h] [rbp+30h]
  int v68; // [rsp+138h] [rbp+38h]
  int v69; // [rsp+13Ch] [rbp+3Ch]
  __int64 *v70; // [rsp+140h] [rbp+40h]
  __int64 v71; // [rsp+148h] [rbp+48h]
  unsigned int *v72; // [rsp+150h] [rbp+50h]
  __int64 v73; // [rsp+158h] [rbp+58h]
  unsigned int *v74; // [rsp+160h] [rbp+60h]
  __int64 v75; // [rsp+168h] [rbp+68h]
  unsigned int *v76; // [rsp+170h] [rbp+70h]
  __int64 v77; // [rsp+178h] [rbp+78h]

  v6 = a2.Data[0];
  v8 = (unsigned __int64)&TraceLoggingMetadata;
  if ( (unsigned int)dword_180035050 > 4 )
  {
    v36 = this;
    v49 = &v36;
    *(_DWORD *)&EventDescriptor.Level = 260;
    UserData.Ptr = (ULONGLONG)off_180035058;
    v50 = 8;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)off_180035058;
    v46 = &word_18002E09E;
    UserData.Reserved = 2;
    v47 = 30;
    v48 = 1;
    v37 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    v8 = (unsigned __int64)&TraceLoggingMetadata;
  }
  v40 = 0;
  if ( !v6 )
  {
    if ( (unsigned int)dword_180035050 > 4 )
    {
      LODWORD(v40) = (_DWORD)a6;
      LODWORD(v36) = 4096;
      v53 = &v36;
      LODWORD(v39) = 303;
      v51 = &v39;
      v54 = 4;
      v49 = (Broker **)&v40;
      UserData.Ptr = (ULONGLONG)off_180035058;
      v52 = 4;
      v50 = 4;
      Buf2 = 0x2040B000000uLL;
      UserData.Size = *(unsigned __int16 *)off_180035058;
      v46 = &word_18002E05E;
      UserData.Reserved = 2;
      v47 = 52;
      v48 = 1;
      v38 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)&Buf2, 0, 0, 5u, &UserData);
    }
    goto LABEL_64;
  }
  v9 = *((_QWORD *)a4 + 24);
  this = (Broker *)&v40;
  v10 = -1;
  if ( !v9 )
  {
    v11 = 1168;
    v12 = 0x2000;
LABEL_31:
    v13 = (unsigned int)a6;
    goto LABEL_32;
  }
  v13 = (unsigned int)a6;
  if ( (unsigned int)a6 < 8 )
  {
    v11 = 122;
    v12 = 12288;
    goto LABEL_32;
  }
  v8 = *(unsigned int *)a5;
  this = (Broker *)a5;
  v36 = (Broker *)a5;
  if ( (v8 & 0x1000000) != 0 )
  {
    v11 = 87;
    v12 = 0x4000;
    goto LABEL_32;
  }
  if ( (unsigned int)a6 < ((v8 >> 2) & 0xFFF) + 8 )
  {
    v11 = 122;
    v12 = 20480;
    this = (Broker *)a5;
    goto LABEL_32;
  }
  if ( (v8 & 0x3FFC) - 1 <= 0x4E )
  {
    v11 = 122;
    v12 = 24576;
    this = (Broker *)a5;
    goto LABEL_32;
  }
  v14 = *((_DWORD *)a4 + 25);
  if ( v14 )
  {
    if ( v14 >= 1 && (v8 & 1) == 0 )
    {
      v11 = 87;
      v12 = 0x8000;
      this = (Broker *)a5;
      goto LABEL_32;
    }
  }
  else if ( (v8 & 1) != 0 )
  {
    v11 = 87;
    v12 = 28672;
    this = (Broker *)a5;
    goto LABEL_32;
  }
  v15 = *((_DWORD *)a5 + 1);
  if ( v15 != -1 )
  {
    LOBYTE(UserDataCount) = 1;
    SessionInfo = Broker::SebBroker::GetSessionInfo(v9, &Buf2, v15, *((_QWORD *)a4 + 1));
    v17 = *SessionInfo;
    v18 = (volatile signed __int32 *)SessionInfo[1];
    *SessionInfo = 0;
    SessionInfo[1] = 0;
    v19 = (volatile signed __int32 *)*((_QWORD *)&Buf2 + 1);
    if ( *((_QWORD *)&Buf2 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&Buf2 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
        if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
      }
    }
    if ( !v17 )
    {
      v11 = 1312;
      v12 = 36864;
      if ( v18 )
      {
        if ( _InterlockedExchangeAdd(v18 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
          if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
        }
      }
      this = (Broker *)a5;
      goto LABEL_31;
    }
    if ( v18 )
    {
      if ( _InterlockedExchangeAdd(v18 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
        if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
      }
    }
  }
  v26 = *(_DWORD *)a5;
  v27 = a5 + 8;
  v28 = *((_QWORD *)a4 + 13);
  v29 = (*(_DWORD *)a5 >> 2) & 0xFFF;
  v39 = a5 + 8;
  if ( v28 )
  {
    if ( (v26 & 0x400000) == 0 )
    {
      this = v36;
      v11 = 87;
      v12 = 49152;
      goto LABEL_31;
    }
    Buf2 = 0;
    if ( v29 < 0x14 || (v30 = v29 - 4, v31 = *(unsigned int *)&v27[v30], v31 + 16 > (unsigned __int64)(unsigned int)v30) )
    {
      this = v36;
      v11 = 87;
      v12 = 40960;
      goto LABEL_31;
    }
    v29 = v30 - v31;
    v32 = v29;
    if ( !memcmp_0(v27, &Buf2, 0x10u) )
      v29 = 0;
    v8 = (unsigned __int64)v39 + v32;
    if ( !((char *)v39 + v32)
      || (v33 = *(const void **)(v28 + 8), v31 != *(_QWORD *)(v28 + 16) - (_QWORD)v33)
      || *(_DWORD *)v28 != 1
      || memcmp_0(v33, (const void *)v8, (unsigned int)v31) )
    {
      this = v36;
      v11 = 0;
      v12 = 45056;
      goto LABEL_31;
    }
  }
  v11 = Broker::SebEvent::OnSignaled(a4, (v26 & 2) != 0, v39, v29, UserDataCount);
  v13 = (unsigned int)a6;
  this = v36;
  if ( v11 )
  {
    v12 = 53248;
  }
  else
  {
    v11 = 0;
    v12 = 0;
  }
LABEL_32:
  if ( (unsigned int)dword_180035050 > 4 )
  {
    v20 = *((_QWORD *)a4 + 11) <= 7u;
    v21 = *(_QWORD *)this;
    v22 = (const WCHAR *)((char *)a4 + 64);
    v37 = v12;
    v42 = v11;
    v38 = v13;
    v44 = v21;
    if ( !v20 )
      v22 = *(const WCHAR **)v22;
    v23 = *((_QWORD *)a4 + 28);
    LODWORD(v40) = *((_DWORD *)a4 + 33);
    LODWORD(v39) = *((_DWORD *)a4 + 24);
    *(_QWORD *)&EventDescriptor.Id = *(_QWORD *)((char *)a4 + 124);
    v76 = &v37;
    v74 = &v42;
    v72 = &v38;
    v70 = &v44;
    v77 = 4;
    v75 = 4;
    v73 = 4;
    v71 = 8;
    if ( v22 )
    {
      while ( v22[++v10] != 0 )
        ;
      v25 = 2 * v10 + 2;
    }
    else
    {
      v22 = &LocaleName;
      v25 = 2;
    }
    v67 = v22;
    v65 = &v40;
    v61 = v23;
    v63 = &v39;
    v68 = v25;
    p_EventDescriptor = &EventDescriptor;
    v55.Ptr = (ULONGLONG)off_180035058;
    v69 = 0;
    v66 = 4;
    v64 = 4;
    v62 = 16;
    v60 = 8;
    Buf2 = 0x2040B000000uLL;
    v55.Size = *(unsigned __int16 *)off_180035058;
    v56 = &word_18002DF46;
    v55.Reserved = 2;
    v57 = 112;
    v58 = 1;
    LODWORD(v36) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)&Buf2, 0, 0, 0xBu, &v55);
  }
  if ( v11 )
LABEL_64:
    MicrosoftTelemetryAssertTriggeredNoArgs(this, v8);
  return 0;
}

```

## disassembly

```asm
0x180017f40  push    rbp
0x180017f42  push    rbx
0x180017f43  push    rdi
0x180017f44  push    r12
0x180017f46  push    r13
0x180017f48  push    r15
0x180017f4a  lea     rbp, [rsp-98h]
0x180017f52  sub     rsp, 198h
0x180017f59  mov     rax, cs:__security_cookie
0x180017f60  xor     rax, rsp
0x180017f63  mov     [rbp+0C0h+var_40], rax
0x180017f6a  mov     eax, cs:dword_180035050
0x180017f70  lea     rdi, _TraceLoggingMetadataEnd
0x180017f77  mov     r15, [rbp+0C0h+arg_20]
0x180017f7e  xor     r12d, r12d
0x180017f81  mov     ebx, edx
0x180017f83  mov     r13, r9
0x180017f86  lea     rdx, _TraceLoggingMetadata
0x180017f8d  cmp     eax, 4
0x180017f90  jbe     loc_180018032
0x180017f96  mov     [rsp+1C0h+var_190], rcx
0x180017f9b  lea     rax, [rsp+1C0h+var_190]
0x180017fa0  mov     [rbp+0C0h+var_120], rax
0x180017fa4  xor     r9d, r9d; RelatedActivityId
0x180017fa7  movzx   eax, cs:word_18002E094
0x180017fae  xor     r8d, r8d; ActivityId
0x180017fb1  mov     dword ptr [rsp+1C0h+EventDescriptor.Level], eax
0x180017fb5  mov     rax, cs:off_180035058
0x180017fbc  mov     [rbp+0C0h+var_140.Ptr], rax
0x180017fc0  mov     [rbp+0C0h+var_118], 8
0x180017fc8  mov     dword ptr [rsp+1C0h+EventDescriptor.Id], 0B000000h
0x180017fd0  mov     [rsp+1C0h+EventDescriptor.Keyword], r12
0x180017fd5  movzx   eax, word ptr [rax]
0x180017fd8  mov     [rbp+0C0h+var_140.Size], eax
0x180017fdb  lea     rax, word_18002E09E
0x180017fe2  mov     [rbp+0C0h+var_130], rax
0x180017fe6  mov     rax, rdi
0x180017fe9  sub     eax, edx
0x180017feb  mov     dword ptr [rbp+0C0h+var_140.0Ch], 2
0x180017ff2  mov     [rbp+0C0h+var_128], 1Eh
0x180017ff9  lea     rdx, [rsp+1C0h+EventDescriptor]; EventDescriptor
0x180017ffe  mov     [rbp+0C0h+var_124], 1
0x180018005  mov     [rsp+1C0h+var_188], eax
0x180018009  mov     eax, [rsp+1C0h+var_188]
0x18001800d  mov     rcx, cs:RegHandle; RegHandle
0x180018014  lea     rax, [rbp+0C0h+var_140]
0x180018018  mov     [rsp+1C0h+UserData], rax; UserData
0x18001801d  mov     dword ptr [rsp+1C0h+UserDataCount], 3; UserDataCount
0x180018025  call    cs:__imp_EventWriteTransfer
0x18001802b  lea     rdx, _TraceLoggingMetadata
0x180018032  mov     [rsp+1C0h+var_178], r12
0x180018037  test    ebx, ebx
0x180018039  jz      loc_180018524
0x18001803f  mov     r10, [r13+0C0h]
0x180018046  lea     rcx, [rsp+1C0h+var_178]
0x18001804b  mov     [rsp+1C0h+var_30], r14
0x180018053  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18001805a  mov     [rsp+1C0h+arg_8], rsi
0x180018062  test    r10, r10
0x180018065  jnz     short loc_180018076
0x180018067  mov     ebx, 490h
0x18001806c  mov     esi, 2000h
0x180018071  jmp     loc_180018201
0x180018076  mov     r8d, dword ptr [rbp+0C0h+arg_28]
0x18001807d  cmp     r8d, 8
0x180018081  jnb     short loc_180018092
0x180018083  mov     ebx, 7Ah ; 'z'
0x180018088  mov     esi, 3000h
0x18001808d  jmp     loc_180018208
0x180018092  mov     edx, [r15]
0x180018095  mov     rcx, r15
0x180018098  mov     [rsp+1C0h+var_190], rcx
0x18001809d  bt      edx, 18h
0x1800180a1  jnb     short loc_1800180B2
0x1800180a3  mov     ebx, 57h ; 'W'
0x1800180a8  mov     esi, 4000h
0x1800180ad  jmp     loc_180018208
0x1800180b2  mov     rcx, rdx
0x1800180b5  shr     rcx, 2
0x1800180b9  and     ecx, 0FFFh
0x1800180bf  add     rcx, 8
0x1800180c3  cmp     r8, rcx
0x1800180c6  jnb     short loc_1800180DA
0x1800180c8  mov     ebx, 7Ah ; 'z'
0x1800180cd  mov     esi, 5000h
0x1800180d2  mov     rcx, r15
0x1800180d5  jmp     loc_180018208
0x1800180da  mov     eax, edx
0x1800180dc  and     eax, 3FFCh
0x1800180e1  dec     eax
0x1800180e3  cmp     eax, 4Eh ; 'N'
0x1800180e6  ja      short loc_1800180FA
0x1800180e8  mov     ebx, 7Ah ; 'z'
0x1800180ed  mov     esi, 6000h
0x1800180f2  mov     rcx, r15
0x1800180f5  jmp     loc_180018208
0x1800180fa  mov     eax, [r13+64h]
0x1800180fe  test    eax, eax
0x180018100  jnz     short loc_180018119
0x180018102  test    dl, 1
0x180018105  jz      short loc_180018135
0x180018107  mov     ebx, 57h ; 'W'
0x18001810c  mov     esi, 7000h
0x180018111  mov     rcx, r15
0x180018114  jmp     loc_180018208
0x180018119  cmp     eax, 1
0x18001811c  jl      short loc_180018135
0x18001811e  test    dl, 1
0x180018121  jnz     short loc_180018135
0x180018123  mov     ebx, 57h ; 'W'
0x180018128  mov     esi, 8000h
0x18001812d  mov     rcx, r15
0x180018130  jmp     loc_180018208
0x180018135  mov     r8d, [r15+4]
0x180018139  cmp     r8d, 0FFFFFFFFh
0x18001813d  jz      loc_180018306
0x180018143  mov     r9, [r13+8]
0x180018147  lea     rdx, [rsp+1C0h+Buf2]
0x18001814c  mov     rcx, r10
0x18001814f  mov     byte ptr [rsp+1C0h+UserDataCount], 1; struct _GUID *
0x180018154  call    ?GetSessionInfo@SebBroker@Broker@@QEAA?AV?$shared_ptr@U_SessionInfo@Broker@@@std@@KQEAX_N@Z; Broker::SebBroker::GetSessionInfo(ulong,void * const,bool)
0x180018159  mov     rsi, [rax]
0x18001815c  mov     rdi, [rax+8]
0x180018160  mov     [rax], r12
0x180018163  mov     [rax+8], r12
0x180018167  mov     rbx, qword ptr [rsp+1C0h+Buf2+8]
0x18001816c  test    rbx, rbx
0x18001816f  jz      short loc_1800181A8
0x180018171  mov     eax, r14d
0x180018174  lock xadd [rbx+8], eax
0x180018179  cmp     eax, 1
0x18001817c  jnz     short loc_1800181A8
0x18001817e  mov     rax, [rbx]
0x180018181  mov     rcx, rbx
0x180018184  mov     rax, [rax]
0x180018187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001818c  mov     eax, r14d
0x18001818f  lock xadd [rbx+0Ch], eax
0x180018194  cmp     eax, 1
0x180018197  jnz     short loc_1800181A8
0x180018199  mov     rax, [rbx]
0x18001819c  mov     rcx, rbx
0x18001819f  mov     rax, [rax+8]
0x1800181a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800181a8  test    rsi, rsi
0x1800181ab  jnz     loc_1800182CA
0x1800181b1  mov     ebx, 520h
0x1800181b6  mov     esi, 9000h
0x1800181bb  test    rdi, rdi
0x1800181be  jz      short loc_1800181F7
0x1800181c0  mov     eax, r14d
0x1800181c3  lock xadd [rdi+8], eax
0x1800181c8  cmp     eax, 1
0x1800181cb  jnz     short loc_1800181F7
0x1800181cd  mov     rax, [rdi]
0x1800181d0  mov     rcx, rdi
0x1800181d3  mov     rax, [rax]
0x1800181d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800181db  mov     eax, r14d
0x1800181de  lock xadd [rdi+0Ch], eax
0x1800181e3  cmp     eax, 1
0x1800181e6  jnz     short loc_1800181F7
0x1800181e8  mov     rax, [rdi]
0x1800181eb  mov     rcx, rdi
0x1800181ee  mov     rax, [rax+8]
0x1800181f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800181f7  mov     rcx, r15
0x1800181fa  lea     rdi, _TraceLoggingMetadataEnd
0x180018201  mov     r8d, dword ptr [rbp+0C0h+arg_28]
0x180018208  mov     eax, cs:dword_180035050
0x18001820e  cmp     eax, 4
0x180018211  jbe     loc_180018507
0x180018217  cmp     qword ptr [r13+58h], 7
0x18001821c  mov     rax, [rcx]
0x18001821f  lea     rcx, [r13+40h]
0x180018223  mov     [rsp+1C0h+var_188], esi
0x180018227  mov     [rsp+1C0h+var_160], ebx
0x18001822b  mov     [rsp+1C0h+var_184], r8d
0x180018230  mov     [rsp+1C0h+var_148], rax
0x180018235  jbe     short loc_18001823A
0x180018237  mov     rcx, [rcx]
0x18001823a  mov     eax, [r13+84h]
0x180018241  mov     rdx, [r13+0E0h]
0x180018248  mov     dword ptr [rsp+1C0h+var_178], eax
0x18001824c  mov     eax, [r13+60h]
0x180018250  mov     dword ptr [rsp+1C0h+var_180], eax
0x180018254  mov     rax, [r13+7Ch]
0x180018258  mov     qword ptr [rsp+1C0h+EventDescriptor.Id], rax
0x18001825d  lea     rax, [rsp+1C0h+var_188]
0x180018262  mov     [rbp+0C0h+var_50], rax
0x180018266  lea     rax, [rsp+1C0h+var_160]
0x18001826b  mov     [rbp+0C0h+var_60], rax
0x18001826f  lea     rax, [rsp+1C0h+var_184]
0x180018274  mov     [rbp+0C0h+var_70], rax
0x180018278  lea     rax, [rsp+1C0h+var_148]
0x18001827d  mov     [rbp+0C0h+var_80], rax
0x180018281  mov     [rbp+0C0h+var_48], 4
0x180018289  mov     [rbp+0C0h+var_58], 4
0x180018291  mov     [rbp+0C0h+var_68], 4
0x180018299  mov     [rbp+0C0h+var_78], 8
0x1800182a1  test    rcx, rcx
0x1800182a4  jz      loc_18001842C
0x1800182aa  nop     word ptr [rax+rax+00h]
0x1800182b0  cmp     word ptr [rcx+r14*2+2], 0
0x1800182b7  lea     r14, [r14+1]
0x1800182bb  jnz     short loc_1800182B0
0x1800182bd  lea     r14d, ds:2[r14*2]
0x1800182c5  jmp     loc_180018439
0x1800182ca  test    rdi, rdi
0x1800182cd  jz      short loc_180018306
0x1800182cf  mov     eax, r14d
0x1800182d2  lock xadd [rdi+8], eax
0x1800182d7  cmp     eax, 1
0x1800182da  jnz     short loc_180018306
0x1800182dc  mov     rax, [rdi]
0x1800182df  mov     rcx, rdi
0x1800182e2  mov     rax, [rax]
0x1800182e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182ea  mov     eax, r14d
0x1800182ed  lock xadd [rdi+0Ch], eax
0x1800182f2  cmp     eax, 1
0x1800182f5  jnz     short loc_180018306
0x1800182f7  mov     rax, [rdi]
0x1800182fa  mov     rcx, rdi
0x1800182fd  mov     rax, [rax+8]
0x180018301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018306  mov     esi, [r15]
0x180018309  lea     r9, [r15+8]
0x18001830d  mov     r15, [r13+68h]
0x180018311  mov     edi, esi
0x180018313  shr     edi, 2
0x180018316  and     edi, 0FFFh
0x18001831c  mov     [rsp+1C0h+var_180], r9
0x180018321  test    r15, r15
0x180018324  jz      loc_1800183E4
0x18001832a  bt      esi, 16h
0x18001832e  jnb     loc_1800183CD
0x180018334  xorps   xmm0, xmm0
0x180018337  movups  [rsp+1C0h+Buf2], xmm0
0x18001833c  cmp     edi, 14h
0x18001833f  jb      short loc_1800183B9
0x180018341  add     edi, 0FFFFFFFCh
0x180018344  mov     ecx, edi
0x180018346  mov     r12d, [rdi+r9]
0x18001834a  lea     rax, [r12+10h]
0x18001834f  cmp     rax, rcx
0x180018352  ja      short loc_1800183B6
0x180018354  sub     edi, r12d
0x180018357  lea     rdx, [rsp+1C0h+Buf2]; Buf2
0x18001835c  mov     r8d, 10h; Size
0x180018362  mov     ebx, edi
0x180018364  mov     rcx, r9; Buf1
0x180018367  call    memcmp_0
0x18001836c  mov     rdx, [rsp+1C0h+var_180]
0x180018371  mov     ecx, eax
0x180018373  xor     eax, eax
0x180018375  test    ecx, ecx
0x180018377  cmovz   edi, eax
0x18001837a  add     rdx, rbx; Buf2
0x18001837d  jz      short loc_1800183A1
0x18001837f  mov     rcx, [r15+8]; Buf1
0x180018383  mov     rax, [r15+10h]
0x180018387  sub     rax, rcx
0x18001838a  cmp     r12, rax
0x18001838d  jnz     short loc_1800183A1
0x18001838f  cmp     dword ptr [r15], 1
0x180018393  jnz     short loc_1800183A1
0x180018395  mov     r8d, r12d; Size
0x180018398  call    memcmp_0
0x18001839d  test    eax, eax
0x18001839f  jz      short loc_1800183E1
0x1800183a1  mov     rcx, [rsp+1C0h+var_190]
0x1800183a6  xor     r12d, r12d
0x1800183a9  mov     ebx, r12d
0x1800183ac  mov     esi, 0B000h
0x1800183b1  jmp     loc_1800181FA
0x1800183b6  xor     r12d, r12d
0x1800183b9  mov     rcx, [rsp+1C0h+var_190]
0x1800183be  mov     ebx, 57h ; 'W'
0x1800183c3  mov     esi, 0A000h
0x1800183c8  jmp     loc_1800181FA
0x1800183cd  mov     rcx, [rsp+1C0h+var_190]
0x1800183d2  mov     ebx, 57h ; 'W'
0x1800183d7  mov     esi, 0C000h
0x1800183dc  jmp     loc_1800181FA
0x1800183e1  xor     r12d, r12d
0x1800183e4  mov     r8, [rsp+1C0h+var_180]; void *
0x1800183e9  mov     r9d, edi; unsigned int
0x1800183ec  shr     esi, 1
0x1800183ee  mov     rcx, r13; this
0x1800183f1  and     sil, 1
0x1800183f5  movzx   edx, sil; unsigned __int8
0x1800183f9  call    ?OnSignaled@SebEvent@Broker@@QEAAKEPEBXIPEBU_GUID@@@Z; Broker::SebEvent::OnSignaled(uchar,void const *,uint,_GUID const *)
0x1800183fe  mov     ebx, eax
0x180018400  mov     r8d, dword ptr [rbp+0C0h+arg_28]
0x180018407  lea     rdi, _TraceLoggingMetadataEnd
0x18001840e  mov     rcx, [rsp+1C0h+var_190]
0x180018413  test    eax, eax
0x180018415  jz      short loc_180018421
0x180018417  mov     esi, 0D000h
  ... truncated ...
```
