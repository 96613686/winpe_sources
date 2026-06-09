# HyperVFile::CheckReplayLog(void)

- ea: `0x1401ce034`
- end: `0x1401ce894`
- name: `?CheckReplayLog@HyperVFile@@IEAAXXZ`
- size: `2144`
- prototype: `void __fastcall(HyperVFile *__hidden this)`
- caller_count: `2`
- callee_count: `18`
- tags: ``

## callers

- `0x1401cfe8c`
- `0x1401d2ef8`

## callees

- `0x140023e30`
- `0x1400261dc`
- `0x1400287a8`
- `0x1400535ac`
- `0x140055440`
- `0x1400db600`
- `0x1400e7608`
- `0x140133bec`
- `0x140133c54`
- `0x1401ce034`
- `0x1401d7398`
- `0x1401dacb4`
- `0x1401db358`
- `0x1401db370`
- `0x1401dbd48`
- `0x1401dbf38`
- `0x1401dc340`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1401ce0cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1401ce3cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1401ce667`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1401ce0cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1401ce3cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1401ce667`

## pseudocode

```c
void __fastcall HyperVFile::CheckReplayLog(HyperVFile *this)
{
  __int64 v2; // rcx
  __int64 v3; // rdx
  unsigned int v4; // r9d
  int v5; // ebx
  int IsDebugTraceEnabled; // ebx
  unsigned __int64 v7; // rdx
  unsigned __int8 v8; // cl
  bool IsEnabled; // al
  char v10; // r14
  __int64 v11; // rax
  int v12; // ebx
  unsigned __int64 v13; // rdx
  unsigned __int8 v14; // cl
  bool v15; // al
  char v16; // r14
  __int64 v17; // rax
  int v18; // ebx
  unsigned __int64 v19; // rdx
  unsigned __int8 v20; // cl
  bool v21; // al
  char v22; // r14
  __int64 v23; // rax
  HyperVStorageReplayLog *v24; // rcx
  __int64 v25; // r12
  HyperVStorageReplayLog *v26; // rcx
  int v27; // ebx
  unsigned __int64 v28; // rdx
  unsigned __int8 v29; // cl
  bool v30; // al
  char v31; // r15
  __int64 v32; // rax
  unsigned int v33; // r14d
  unsigned __int64 v34; // rcx
  __int64 v35; // rax
  unsigned int v36; // r8d
  int v37; // ebx
  int v38; // ebx
  unsigned __int64 v39; // rdx
  unsigned __int8 v40; // cl
  bool v41; // al
  char v42; // r14
  __int64 v43; // rax
  int v44; // ebx
  unsigned __int64 v45; // rdx
  unsigned __int8 v46; // cl
  bool v47; // al
  char v48; // r14
  __int64 v49; // rax
  int v50; // ebx
  unsigned __int64 v51; // rdx
  unsigned __int8 v52; // cl
  bool v53; // al
  char v54; // si
  __int64 v55; // rax
  int v56; // ebx
  unsigned __int64 v57; // rdx
  unsigned __int8 v58; // cl
  bool v59; // al
  char v60; // si
  __int64 v61; // rax
  int v62; // ebx
  int v63; // ebx
  unsigned __int64 v64; // rdx
  unsigned __int8 v65; // cl
  bool v66; // al
  char v67; // r14
  __int64 v68; // rax
  int v69; // ebx
  unsigned __int64 v70; // rdx
  unsigned __int8 v71; // cl
  bool v72; // al
  char v73; // r14
  __int64 v74; // rax
  int v75; // ebx
  unsigned __int64 v76; // rdx
  unsigned __int8 v77; // cl
  bool v78; // al
  char v79; // bp
  __int64 v80; // rax
  int v81; // [rsp+70h] [rbp+8h] BYREF
  unsigned int v82; // [rsp+78h] [rbp+10h]
  struct IHyperVStorageReplayLogInterface *v83; // [rsp+80h] [rbp+18h]

  v2 = *(_QWORD *)((char *)this + 50);
  v3 = *(_QWORD *)((char *)this + 58);
  if ( *((_QWORD *)this + 20) < (unsigned __int64)(v3 + v2) )
    *((_QWORD *)this + 20) = v3 + v2;
  v81 = 0;
  *((_QWORD *)this + 83) = v2;
  *((_QWORD *)this + 84) = v3;
  v4 = *(_DWORD *)((char *)this + 34);
  v83 = (struct IHyperVStorageReplayLogInterface *)(((unsigned __int64)this + 584) & -(__int64)(this != 0));
  if ( (unsigned int)HyperVStorageReplayLog::Reload((HyperVFile *)((char *)this + 608), v83, &v81, v4) )
  {
    if ( v81 )
    {
      v5 = *((_DWORD *)this + 44);
      if ( GetCurrentThreadId() != v5 )
      {
        IsDebugTraceEnabled = HvsIsDebugTraceEnabled(0x8040u);
        IsEnabled = HyperVStorageTrace::IsEnabled(v8, v7);
        v10 = IsEnabled;
        if ( IsDebugTraceEnabled || IsEnabled )
        {
          if ( dword_1403C198C > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 2064LL) )
          {
            Init_thread_header(&dword_1403C198C);
            if ( dword_1403C198C == -1 )
            {
              byte_1403A720C = IsDebugTraceEnabled != 0;
              byte_1403A720D = v10;
              Init_thread_footer(&dword_1403C198C);
            }
          }
          v11 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 72LL))(*((_QWORD *)this + 75));
          HvsDebugTraceInternal(0x8040u, (const struct HvsDebugTraceParameters *)&off_1403A71F8, v11);
        }
        goto LABEL_75;
      }
      if ( (unsigned int)IHyperVFileIo::IsOpenedReadOnly(*((IHyperVFileIo **)this + 75)) )
      {
        v12 = HvsIsDebugTraceEnabled(0x8040u);
        v15 = HyperVStorageTrace::IsEnabled(v14, v13);
        v16 = v15;
        if ( v12 || v15 )
        {
          if ( dword_1403C1990 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 2064LL) )
          {
            Init_thread_header(&dword_1403C1990);
            if ( dword_1403C1990 == -1 )
            {
              byte_1403A7224 = v12 != 0;
              byte_1403A7225 = v16;
              Init_thread_footer(&dword_1403C1990);
            }
          }
          v17 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 72LL))(*((_QWORD *)this + 75));
          HvsDebugTraceInternal(0x8040u, (const struct HvsDebugTraceParameters *)&off_1403A7210, v17);
        }
        goto LABEL_83;
      }
      v18 = HvsIsDebugTraceEnabled(0x8040u);
      LOBYTE(v81) = v18 != 0;
      v21 = HyperVStorageTrace::IsEnabled(v20, v19);
      v22 = v21;
      if ( v18 || v21 )
      {
        if ( dword_1403C1994 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 2064LL) )
        {
          Init_thread_header(&dword_1403C1994);
          if ( dword_1403C1994 == -1 )
          {
            byte_1403A71AC = v81;
            byte_1403A71AD = v22;
            Init_thread_footer(&dword_1403C1994);
          }
        }
        v23 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 72LL))(*((_QWORD *)this + 75));
        HvsDebugTraceInternal(0x8040u, (const struct HvsDebugTraceParameters *)&off_1403A7198, v23);
      }
      HyperVStorageReplayLog::ApplyLog(
        (HyperVFile *)((char *)this + 608),
        (struct IHyperVStorageReplayLogInterface *)(((unsigned __int64)this + 584) & -(__int64)(this != 0)));
    }
    if ( (unsigned int)HyperVStorageReplayLog::IsChangeTrackingEnabled((HyperVFile *)((char *)this + 608)) )
    {
      v25 = HyperVStorageReplayLog::GetChangeTrackingBufferOffsetInBytes(v24);
      v82 = HyperVStorageReplayLog::GetChangeTrackingBufferSizeInBytes(v26);
      if ( v82 )
      {
        v27 = HvsIsDebugTraceEnabled(0xC040u);
        LOBYTE(v81) = v27 != 0;
        v30 = HyperVStorageTrace::IsEnabled(v29, v28);
        v31 = v30;
        if ( v27 || v30 )
        {
          if ( dword_1403C1998 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 2064LL) )
          {
            Init_thread_header(&dword_1403C1998);
            if ( dword_1403C1998 == -1 )
            {
              byte_1403A71C4 = v81;
              byte_1403A71C5 = v31;
              Init_thread_footer(&dword_1403C1998);
            }
          }
          v32 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 72LL))(*((_QWORD *)this + 75));
          HvsDebugTraceInternal(0xC040u, (const struct HvsDebugTraceParameters *)&off_1403A71B0, v32);
        }
        v33 = v82;
        v34 = v25 + v82;
        if ( *((_QWORD *)this + 20) < v34 )
          *((_QWORD *)this + 20) = v34;
        v35 = *((_QWORD *)this + 79);
        if ( v35 )
          v36 = *(_DWORD *)(v35 + 30);
        else
          v36 = 0;
        if ( !(unsigned int)HyperVStorageChangeTracking::Load((HyperVFile *)((char *)this + 528), v25, v36) )
        {
          v37 = *((_DWORD *)this + 44);
          if ( GetCurrentThreadId() != v37 )
          {
            v38 = HvsIsDebugTraceEnabled(0x8040u);
            v41 = HyperVStorageTrace::IsEnabled(v40, v39);
            v42 = v41;
            if ( v38 || v41 )
            {
              if ( dword_1403C199C > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 2064LL) )
              {
                Init_thread_header(&dword_1403C199C);
                if ( dword_1403C199C == -1 )
                {
                  byte_1403A71DC = v38 != 0;
                  byte_1403A71DD = v42;
                  Init_thread_footer(&dword_1403C199C);
                }
              }
              v43 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 72LL))(*((_QWORD *)this + 75));
              HvsDebugTraceInternal(0x8040u, (const struct HvsDebugTraceParameters *)&off_1403A71C8, v43);
            }
            goto LABEL_75;
          }
          if ( (unsigned int)IHyperVFileIo::IsOpenedReadOnly(*((IHyperVFileIo **)this + 75)) )
          {
            v44 = HvsIsDebugTraceEnabled(0x8040u);
            v47 = HyperVStorageTrace::IsEnabled(v46, v45);
            v48 = v47;
            if ( v44 || v47 )
            {
              if ( dword_1403C19A0 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 2064LL) )
              {
                Init_thread_header(&dword_1403C19A0);
                if ( dword_1403C19A0 == -1 )
                {
                  byte_1403A714C = v44 != 0;
                  byte_1403A714D = v48;
                  Init_thread_footer(&dword_1403C19A0);
                }
              }
              v49 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 72LL))(*((_QWORD *)this + 75));
              HvsDebugTraceInternal(0x8040u, (const struct HvsDebugTraceParameters *)&off_1403A7138, v49);
            }
            goto LABEL_83;
          }
          HyperVStorageReplayLog::SaveChangeTrackingBufferPosition(
            (HyperVFile *)((char *)this + 608),
            v83,
            1,
            v25,
            v33,
            0);
        }
        return;
      }
      v50 = HvsIsDebugTraceEnabled(0xC040u);
      v53 = HyperVStorageTrace::IsEnabled(v52, v51);
      v54 = v53;
      if ( v50 || v53 )
      {
        if ( dword_1403C19A4 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 2064LL) )
        {
          Init_thread_header(&dword_1403C19A4);
          if ( dword_1403C19A4 == -1 )
          {
            byte_1403A7164 = v50 != 0;
            byte_1403A7165 = v54;
            Init_thread_footer(&dword_1403C19A4);
          }
        }
        v55 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 72LL))(*((_QWORD *)this + 75));
        HvsDebugTraceInternal(0xC040u, (const struct HvsDebugTraceParameters *)&off_1403A7150, v55);
      }
    }
    else
    {
      v56 = HvsIsDebugTraceEnabled(0xC040u);
      v59 = HyperVStorageTrace::IsEnabled(v58, v57);
      v60 = v59;
      if ( v56 || v59 )
      {
        if ( dword_1403C19A8 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 2064LL) )
        {
          Init_thread_header(&dword_1403C19A8);
          if ( dword_1403C19A8 == -1 )
          {
            byte_1403A717C = v56 != 0;
            byte_1403A717D = v60;
            Init_thread_footer(&dword_1403C19A8);
          }
        }
        v61 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 72LL))(*((_QWORD *)this + 75));
        HvsDebugTraceInternal(0xC040u, (const struct HvsDebugTraceParameters *)&off_1403A7168, v61);
      }
    }
    HyperVStorageChangeTracking::Reset((HyperVFile *)((char *)this + 528));
    return;
  }
  v62 = *((_DWORD *)this + 44);
  if ( GetCurrentThreadId() != v62 )
  {
    v63 = HvsIsDebugTraceEnabled(0x8040u);
    v66 = HyperVStorageTrace::IsEnabled(v65, v64);
    v67 = v66;
    if ( v63 || v66 )
    {
      if ( dword_1403C19AC > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 2064LL) )
      {
        Init_thread_header(&dword_1403C19AC);
        if ( dword_1403C19AC == -1 )
        {
          byte_1403A7194 = v63 != 0;
          byte_1403A7195 = v67;
          Init_thread_footer(&dword_1403C19AC);
        }
      }
      v68 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 72LL))(*((_QWORD *)this + 75));
      HvsDebugTraceInternal(0x8040u, (const struct HvsDebugTraceParameters *)&off_1403A7180, v68);
    }
LABEL_75:
    HvsThrowWin32Error(0x21u);
  }
  if ( (unsigned int)IHyperVFileIo::IsOpenedReadOnly(*((IHyperVFileIo **)this + 75)) )
  {
    v69 = HvsIsDebugTraceEnabled(0x8040u);
    v72 = HyperVStorageTrace::IsEnabled(v71, v70);
    v73 = v72;
    if ( v69 || v72 )
    {
      if ( dword_1403C19B0 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 2064LL) )
      {
        Init_thread_header(&dword_1403C19B0);
        if ( dword_1403C19B0 == -1 )
        {
          byte_1403A70EC = v69 != 0;
          byte_1403A70ED = v73;
          Init_thread_footer(&dword_1403C19B0);
        }
      }
      v74 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 72LL))(*((_QWORD *)this + 75));
      HvsDebugTraceInternal(0x8040u, (const struct HvsDebugTraceParameters *)&off_1403A70D8, v74);
    }
LABEL_83:
    HvsThrowWin32Error(0x570u);
  }
  v75 = HvsIsDebugTraceEnabled(0xC040u);
  v78 = HyperVStorageTrace::IsEnabled(v77, v76);
  v79 = v78;
  if ( v75 || v78 )
  {
    if ( dword_1403C19B4 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 2064LL) )
    {
      Init_thread_header(&dword_1403C19B4);
      if ( dword_1403C19B4 == -1 )
      {
        byte_1403A7104 = v75 != 0;
        byte_1403A7105 = v79;
        Init_thread_footer(&dword_1403C19B4);
      }
    }
    v80 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 72LL))(*((_QWORD *)this + 75));
    HvsDebugTraceInternal(0xC040u, (const struct HvsDebugTraceParameters *)&off_1403A70F0, v80);
  }
  HyperVStorageReplayLog::Reinitialize(
    (HyperVFile *)((char *)this + 608),
    (struct IHyperVStorageReplayLogInterface *)(((unsigned __int64)this + 584) & -(__int64)(this != 0)),
    *(_QWORD *)((char *)this + 50),
    *(_QWORD *)((char *)this + 58),
    *(_DWORD *)((char *)this + 66));
}

```

## disassembly

```asm
0x1401ce034  mov     [rsp+arg_18], rbx
0x1401ce039  push    rbp
0x1401ce03a  push    rsi
0x1401ce03b  push    rdi
0x1401ce03c  push    r12
0x1401ce03e  push    r13
0x1401ce040  push    r14
0x1401ce042  push    r15
0x1401ce044  sub     rsp, 30h
0x1401ce048  mov     rdi, rcx
0x1401ce04b  mov     rcx, [rcx+32h]
0x1401ce04f  mov     rdx, [rdi+3Ah]
0x1401ce053  lea     rax, [rdx+rcx]
0x1401ce057  cmp     [rdi+0A0h], rax
0x1401ce05e  jnb     short loc_1401CE067
0x1401ce060  mov     [rdi+0A0h], rax
0x1401ce067  lea     r13, [rdi+260h]
0x1401ce06e  mov     [rsp+68h+arg_0], 0
0x1401ce076  mov     [r13+38h], rcx
0x1401ce07a  lea     r8, [rsp+68h+arg_0]; int *
0x1401ce07f  mov     [r13+40h], rdx
0x1401ce083  lea     rcx, [rdi+248h]
0x1401ce08a  mov     r9d, [rdi+22h]; unsigned int
0x1401ce08e  mov     rax, rdi
0x1401ce091  neg     rax
0x1401ce094  sbb     r12, r12
0x1401ce097  and     r12, rcx
0x1401ce09a  mov     rcx, r13; this
0x1401ce09d  mov     rdx, r12; struct IHyperVStorageReplayLogInterface *
0x1401ce0a0  mov     [rsp+68h+arg_10], r12
0x1401ce0a8  call    ?Reload@HyperVStorageReplayLog@@QEAAHPEAVIHyperVStorageReplayLogInterface@@AEAHI@Z; HyperVStorageReplayLog::Reload(IHyperVStorageReplayLogInterface *,int &,uint)
0x1401ce0ad  test    eax, eax
0x1401ce0af  jz      loc_1401CE661
0x1401ce0b5  cmp     [rsp+68h+arg_0], 0
0x1401ce0ba  mov     ebp, 8040h
0x1401ce0bf  jz      loc_1401CE2B7
0x1401ce0c5  mov     ebx, [rdi+0B0h]
0x1401ce0cb  call    cs:__imp_GetCurrentThreadId
0x1401ce0d2  nop     dword ptr [rax+rax+00h]
0x1401ce0d7  cmp     eax, ebx
0x1401ce0d9  jz      loc_1401CE16C
0x1401ce0df  mov     ecx, ebp; unsigned __int16
0x1401ce0e1  call    ?HvsIsDebugTraceEnabled@@YAHG@Z; HvsIsDebugTraceEnabled(ushort)
0x1401ce0e6  test    eax, eax
0x1401ce0e8  mov     ebx, eax
0x1401ce0ea  setnz   r15b
0x1401ce0ee  call    ?IsEnabled@HyperVStorageTrace@@SA_NE_K@Z; HyperVStorageTrace::IsEnabled(uchar,unsigned __int64)
0x1401ce0f3  mov     r14b, al
0x1401ce0f6  test    ebx, ebx
0x1401ce0f8  jnz     short loc_1401CE102
0x1401ce0fa  test    al, al
0x1401ce0fc  jz      loc_1401CE70E
0x1401ce102  mov     rcx, gs:58h
0x1401ce10b  mov     esi, 810h
0x1401ce110  mov     rcx, [rcx]
0x1401ce113  mov     ecx, [rsi+rcx]
0x1401ce116  cmp     cs:dword_1403C198C, ecx
0x1401ce11c  jle     short loc_1401CE14D
0x1401ce11e  lea     rcx, dword_1403C198C
0x1401ce125  call    _Init_thread_header
0x1401ce12a  cmp     cs:dword_1403C198C, 0FFFFFFFFh
0x1401ce131  jnz     short loc_1401CE14D
0x1401ce133  lea     rcx, dword_1403C198C
0x1401ce13a  mov     cs:byte_1403A720C, r15b
0x1401ce141  mov     cs:byte_1403A720D, r14b
0x1401ce148  call    _Init_thread_footer
0x1401ce14d  mov     rcx, [rdi+258h]
0x1401ce154  mov     rax, [rcx]
0x1401ce157  mov     rax, [rax+48h]
0x1401ce15b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401ce160  lea     rdx, off_1403A71F8; "Cannot apply replay log for file \"%ws"...
0x1401ce167  jmp     loc_1401CE704
0x1401ce16c  mov     rcx, [rdi+258h]; this
0x1401ce173  call    ?IsOpenedReadOnly@IHyperVFileIo@@QEBAHXZ; IHyperVFileIo::IsOpenedReadOnly(void)
0x1401ce178  mov     ecx, ebp; unsigned __int16
0x1401ce17a  test    eax, eax
0x1401ce17c  jz      loc_1401CE20D
0x1401ce182  call    ?HvsIsDebugTraceEnabled@@YAHG@Z; HvsIsDebugTraceEnabled(ushort)
0x1401ce187  test    eax, eax
0x1401ce189  mov     ebx, eax
0x1401ce18b  setnz   r15b
0x1401ce18f  call    ?IsEnabled@HyperVStorageTrace@@SA_NE_K@Z; HyperVStorageTrace::IsEnabled(uchar,unsigned __int64)
0x1401ce194  mov     r14b, al
0x1401ce197  test    ebx, ebx
0x1401ce199  jnz     short loc_1401CE1A3
0x1401ce19b  test    al, al
0x1401ce19d  jz      loc_1401CE7C0
0x1401ce1a3  mov     rcx, gs:58h
0x1401ce1ac  mov     esi, 810h
0x1401ce1b1  mov     rcx, [rcx]
0x1401ce1b4  mov     ecx, [rsi+rcx]
0x1401ce1b7  cmp     cs:dword_1403C1990, ecx
0x1401ce1bd  jle     short loc_1401CE1EE
0x1401ce1bf  lea     rcx, dword_1403C1990
0x1401ce1c6  call    _Init_thread_header
0x1401ce1cb  cmp     cs:dword_1403C1990, 0FFFFFFFFh
0x1401ce1d2  jnz     short loc_1401CE1EE
0x1401ce1d4  lea     rcx, dword_1403C1990
0x1401ce1db  mov     cs:byte_1403A7224, r15b
0x1401ce1e2  mov     cs:byte_1403A7225, r14b
0x1401ce1e9  call    _Init_thread_footer
0x1401ce1ee  mov     rcx, [rdi+258h]
0x1401ce1f5  mov     rax, [rcx]
0x1401ce1f8  mov     rax, [rax+48h]
0x1401ce1fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401ce201  lea     rdx, off_1403A7210; "Cannot apply replay log for file \"%ws"...
0x1401ce208  jmp     loc_1401CE7B6
0x1401ce20d  call    ?HvsIsDebugTraceEnabled@@YAHG@Z; HvsIsDebugTraceEnabled(ushort)
0x1401ce212  test    eax, eax
0x1401ce214  mov     ebx, eax
0x1401ce216  setnz   byte ptr [rsp+68h+arg_0]
0x1401ce21b  call    ?IsEnabled@HyperVStorageTrace@@SA_NE_K@Z; HyperVStorageTrace::IsEnabled(uchar,unsigned __int64)
0x1401ce220  mov     r14b, al
0x1401ce223  test    ebx, ebx
0x1401ce225  jnz     short loc_1401CE235
0x1401ce227  test    al, al
0x1401ce229  jnz     short loc_1401CE235
0x1401ce22b  mov     esi, 810h
0x1401ce230  mov     r15d, esi
0x1401ce233  jmp     short loc_1401CE2AA
0x1401ce235  mov     rax, gs:58h
0x1401ce23e  mov     esi, 810h
0x1401ce243  mov     r15d, esi
0x1401ce246  mov     rcx, [rax]
0x1401ce249  mov     eax, [rsi+rcx]
0x1401ce24c  cmp     cs:dword_1403C1994, eax
0x1401ce252  jle     short loc_1401CE286
0x1401ce254  lea     rcx, dword_1403C1994
0x1401ce25b  call    _Init_thread_header
0x1401ce260  cmp     cs:dword_1403C1994, 0FFFFFFFFh
0x1401ce267  jnz     short loc_1401CE286
0x1401ce269  mov     al, byte ptr [rsp+68h+arg_0]
0x1401ce26d  lea     rcx, dword_1403C1994
0x1401ce274  mov     cs:byte_1403A71AC, al
0x1401ce27a  mov     cs:byte_1403A71AD, r14b
0x1401ce281  call    _Init_thread_footer
0x1401ce286  mov     rcx, [rdi+258h]
0x1401ce28d  mov     rax, [rcx]
0x1401ce290  mov     rax, [rax+48h]
0x1401ce294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401ce299  mov     r8, rax
0x1401ce29c  lea     rdx, off_1403A7198; struct HvsDebugTraceParameters *
0x1401ce2a3  mov     ecx, ebp; unsigned int
0x1401ce2a5  call    ?HvsDebugTraceInternal@@YAXIPEBUHvsDebugTraceParameters@@ZZ; HvsDebugTraceInternal(uint,HvsDebugTraceParameters const *,...)
0x1401ce2aa  mov     rdx, r12; struct IHyperVStorageReplayLogInterface *
0x1401ce2ad  mov     rcx, r13; this
0x1401ce2b0  call    ?ApplyLog@HyperVStorageReplayLog@@QEAAXPEAVIHyperVStorageReplayLogInterface@@@Z; HyperVStorageReplayLog::ApplyLog(IHyperVStorageReplayLogInterface *)
0x1401ce2b5  jmp     short loc_1401CE2BF
0x1401ce2b7  mov     esi, 810h
0x1401ce2bc  mov     r15d, esi
0x1401ce2bf  mov     rcx, r13; this
0x1401ce2c2  call    ?IsChangeTrackingEnabled@HyperVStorageReplayLog@@QEBAHXZ; HyperVStorageReplayLog::IsChangeTrackingEnabled(void)
0x1401ce2c7  test    eax, eax
0x1401ce2c9  jz      loc_1401CE5BE
0x1401ce2cf  call    ?GetChangeTrackingBufferOffsetInBytes@HyperVStorageReplayLog@@QEBA_KXZ; HyperVStorageReplayLog::GetChangeTrackingBufferOffsetInBytes(void)
0x1401ce2d4  mov     r12, rax
0x1401ce2d7  call    ?GetChangeTrackingBufferSizeInBytes@HyperVStorageReplayLog@@QEBAIXZ; HyperVStorageReplayLog::GetChangeTrackingBufferSizeInBytes(void)
0x1401ce2dc  mov     [rsp+68h+arg_8], eax
0x1401ce2e0  mov     r14d, 0C040h
0x1401ce2e6  mov     ecx, r14d; unsigned __int16
0x1401ce2e9  test    eax, eax
0x1401ce2eb  jz      loc_1401CE537
0x1401ce2f1  call    ?HvsIsDebugTraceEnabled@@YAHG@Z; HvsIsDebugTraceEnabled(ushort)
0x1401ce2f6  test    eax, eax
0x1401ce2f8  mov     ebx, eax
0x1401ce2fa  setnz   byte ptr [rsp+68h+arg_0]
0x1401ce2ff  call    ?IsEnabled@HyperVStorageTrace@@SA_NE_K@Z; HyperVStorageTrace::IsEnabled(uchar,unsigned __int64)
0x1401ce304  mov     r15b, al
0x1401ce307  test    ebx, ebx
0x1401ce309  jnz     short loc_1401CE30F
0x1401ce30b  test    al, al
0x1401ce30d  jz      short loc_1401CE381
0x1401ce30f  mov     rcx, gs:58h
0x1401ce318  mov     r8d, esi
0x1401ce31b  mov     rdx, [rcx]
0x1401ce31e  mov     ecx, [r8+rdx]
0x1401ce322  cmp     cs:dword_1403C1998, ecx
0x1401ce328  jle     short loc_1401CE35C
0x1401ce32a  lea     rcx, dword_1403C1998
0x1401ce331  call    _Init_thread_header
0x1401ce336  cmp     cs:dword_1403C1998, 0FFFFFFFFh
0x1401ce33d  jnz     short loc_1401CE35C
0x1401ce33f  mov     al, byte ptr [rsp+68h+arg_0]
0x1401ce343  lea     rcx, dword_1403C1998
0x1401ce34a  mov     cs:byte_1403A71C4, al
0x1401ce350  mov     cs:byte_1403A71C5, r15b
0x1401ce357  call    _Init_thread_footer
0x1401ce35c  mov     rcx, [rdi+258h]
0x1401ce363  mov     rax, [rcx]
0x1401ce366  mov     rax, [rax+48h]
0x1401ce36a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401ce36f  mov     r8, rax
0x1401ce372  lea     rdx, off_1403A71B0; struct HvsDebugTraceParameters *
0x1401ce379  mov     ecx, r14d; unsigned int
0x1401ce37c  call    ?HvsDebugTraceInternal@@YAXIPEBUHvsDebugTraceParameters@@ZZ; HvsDebugTraceInternal(uint,HvsDebugTraceParameters const *,...)
0x1401ce381  mov     r14d, [rsp+68h+arg_8]
0x1401ce386  lea     rcx, [r12+r14]
0x1401ce38a  cmp     [rdi+0A0h], rcx
0x1401ce391  jnb     short loc_1401CE39A
0x1401ce393  mov     [rdi+0A0h], rcx
0x1401ce39a  mov     rax, [rdi+278h]
0x1401ce3a1  test    rax, rax
0x1401ce3a4  jz      short loc_1401CE3AC
0x1401ce3a6  mov     r8d, [rax+1Eh]
0x1401ce3aa  jmp     short loc_1401CE3AF
0x1401ce3ac  xor     r8d, r8d; unsigned int
0x1401ce3af  lea     rcx, [rdi+210h]; this
0x1401ce3b6  mov     rdx, r12; unsigned __int64
0x1401ce3b9  call    ?Load@HyperVStorageChangeTracking@@QEAAH_KI@Z; HyperVStorageChangeTracking::Load(unsigned __int64,uint)
0x1401ce3be  test    eax, eax
0x1401ce3c0  jnz     loc_1401CE87B
0x1401ce3c6  mov     ebx, [rdi+0B0h]
0x1401ce3cc  call    cs:__imp_GetCurrentThreadId
0x1401ce3d3  nop     dword ptr [rax+rax+00h]
0x1401ce3d8  cmp     eax, ebx
0x1401ce3da  jz      loc_1401CE46C
0x1401ce3e0  mov     ecx, ebp; unsigned __int16
0x1401ce3e2  call    ?HvsIsDebugTraceEnabled@@YAHG@Z; HvsIsDebugTraceEnabled(ushort)
0x1401ce3e7  test    eax, eax
0x1401ce3e9  mov     ebx, eax
0x1401ce3eb  setnz   r15b
0x1401ce3ef  call    ?IsEnabled@HyperVStorageTrace@@SA_NE_K@Z; HyperVStorageTrace::IsEnabled(uchar,unsigned __int64)
0x1401ce3f4  mov     r14b, al
0x1401ce3f7  test    ebx, ebx
0x1401ce3f9  jnz     short loc_1401CE403
0x1401ce3fb  test    al, al
0x1401ce3fd  jz      loc_1401CE70E
0x1401ce403  mov     rcx, gs:58h
0x1401ce40c  mov     r8d, esi
0x1401ce40f  mov     rdx, [rcx]
0x1401ce412  mov     ecx, [r8+rdx]
0x1401ce416  cmp     cs:dword_1403C199C, ecx
0x1401ce41c  jle     short loc_1401CE44D
0x1401ce41e  lea     rcx, dword_1403C199C
0x1401ce425  call    _Init_thread_header
0x1401ce42a  cmp     cs:dword_1403C199C, 0FFFFFFFFh
0x1401ce431  jnz     short loc_1401CE44D
0x1401ce433  lea     rcx, dword_1403C199C
0x1401ce43a  mov     cs:byte_1403A71DC, r15b
0x1401ce441  mov     cs:byte_1403A71DD, r14b
0x1401ce448  call    _Init_thread_footer
0x1401ce44d  mov     rcx, [rdi+258h]
0x1401ce454  mov     rax, [rcx]
0x1401ce457  mov     rax, [rax+48h]
0x1401ce45b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401ce460  lea     rdx, off_1403A71C8; "Cannot reinitialize change tracking buf"...
0x1401ce467  jmp     loc_1401CE704
0x1401ce46c  mov     rcx, [rdi+258h]; this
0x1401ce473  call    ?IsOpenedReadOnly@IHyperVFileIo@@QEBAHXZ; IHyperVFileIo::IsOpenedReadOnly(void)
0x1401ce478  test    eax, eax
0x1401ce47a  jz      loc_1401CE50C
0x1401ce480  mov     ecx, ebp; unsigned __int16
0x1401ce482  call    ?HvsIsDebugTraceEnabled@@YAHG@Z; HvsIsDebugTraceEnabled(ushort)
0x1401ce487  test    eax, eax
0x1401ce489  mov     ebx, eax
0x1401ce48b  setnz   r15b
0x1401ce48f  call    ?IsEnabled@HyperVStorageTrace@@SA_NE_K@Z; HyperVStorageTrace::IsEnabled(uchar,unsigned __int64)
0x1401ce494  mov     r14b, al
0x1401ce497  test    ebx, ebx
0x1401ce499  jnz     short loc_1401CE4A3
0x1401ce49b  test    al, al
0x1401ce49d  jz      loc_1401CE7C0
0x1401ce4a3  mov     rcx, gs:58h
0x1401ce4ac  mov     r8d, esi
0x1401ce4af  mov     rdx, [rcx]
0x1401ce4b2  mov     ecx, [r8+rdx]
0x1401ce4b6  cmp     cs:dword_1403C19A0, ecx
0x1401ce4bc  jle     short loc_1401CE4ED
0x1401ce4be  lea     rcx, dword_1403C19A0
0x1401ce4c5  call    _Init_thread_header
0x1401ce4ca  cmp     cs:dword_1403C19A0, 0FFFFFFFFh
0x1401ce4d1  jnz     short loc_1401CE4ED
0x1401ce4d3  lea     rcx, dword_1403C19A0
0x1401ce4da  mov     cs:byte_1403A714C, r15b
0x1401ce4e1  mov     cs:byte_1403A714D, r14b
0x1401ce4e8  call    _Init_thread_footer
0x1401ce4ed  mov     rcx, [rdi+258h]
0x1401ce4f4  mov     rax, [rcx]
0x1401ce4f7  mov     rax, [rax+48h]
0x1401ce4fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401ce500  lea     rdx, off_1403A7138; "Cannot reinitialize change tracking buf"...
0x1401ce507  jmp     loc_1401CE7B6
0x1401ce50c  mov     rdx, [rsp+68h+arg_10]; struct IHyperVStorageReplayLogInterface *
0x1401ce514  mov     r9, r12; unsigned __int64
0x1401ce517  mov     [rsp+68h+var_40], 0; unsigned int
0x1401ce51f  mov     r8d, 1; int
0x1401ce525  mov     rcx, r13; this
0x1401ce528  mov     [rsp+68h+var_48], r14d; unsigned int
0x1401ce52d  call    ?SaveChangeTrackingBufferPosition@HyperVStorageReplayLog@@QEAAXPEAVIHyperVStorageReplayLogInterface@@H_KII@Z; HyperVStorageReplayLog::SaveChangeTrackingBufferPosition(IHyperVStorageReplayLogInterface *,int,unsigned __int64,uint,uint)
0x1401ce532  jmp     loc_1401CE87B
0x1401ce537  call    ?HvsIsDebugTraceEnabled@@YAHG@Z; HvsIsDebugTraceEnabled(ushort)
0x1401ce53c  test    eax, eax
0x1401ce53e  mov     ebx, eax
0x1401ce540  setnz   bpl
0x1401ce544  call    ?IsEnabled@HyperVStorageTrace@@SA_NE_K@Z; HyperVStorageTrace::IsEnabled(uchar,unsigned __int64)
0x1401ce549  mov     sil, al
0x1401ce54c  test    ebx, ebx
0x1401ce54e  jnz     short loc_1401CE558
0x1401ce550  test    al, al
0x1401ce552  jz      loc_1401CE650
  ... truncated ...
```
