# Wd1dsListener::Start(bool)

- ea: `0x1400e6070`
- end: `0x1400e655e`
- name: `?Start@Wd1dsListener@@QEAAJ_N@Z`
- size: `1262`
- prototype: `__int64 __fastcall(Wd1dsListener *__hidden this, bool)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1400b1108`

## callees

- `0x140013cdc`
- `0x140017738`
- `0x14003a5c0`
- `0x14003aab0`
- `0x140059d40`
- `0x14007d210`
- `0x140085d94`
- `0x1400e5e48`
- `0x1400e6070`
- `0x140166990`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1400e6509`
- `KERNEL32!CloseHandle` at `0x1400e6509`
- `ADVAPI32!EnableTraceEx` at `0x1400e6462`
- `ADVAPI32!EnableTraceEx` at `0x1400e6462`
- `ADVAPI32!OpenTraceW` at `0x1400e64e7`
- `ADVAPI32!OpenTraceW` at `0x1400e64e7`
- `ADVAPI32!StartTraceW` at `0x1400e63d8`
- `ADVAPI32!StartTraceW` at `0x1400e63d8`
- `ADVAPI32!ControlTraceW` at `0x1400e61ce`
- `ADVAPI32!ControlTraceW` at `0x1400e630c`
- `ADVAPI32!ControlTraceW` at `0x1400e61ce`
- `ADVAPI32!ControlTraceW` at `0x1400e630c`
- `RPCRT4!UuidCreate` at `0x1400e60ff`
- `RPCRT4!UuidCreate` at `0x1400e615a`
- `RPCRT4!UuidCreate` at `0x1400e62b6`
- `RPCRT4!UuidCreate` at `0x1400e6386`
- `RPCRT4!UuidCreate` at `0x1400e60ff`
- `RPCRT4!UuidCreate` at `0x1400e615a`
- `RPCRT4!UuidCreate` at `0x1400e62b6`
- `RPCRT4!UuidCreate` at `0x1400e6386`

## pseudocode

```c
__int64 __fastcall Wd1dsListener::Start(Wd1dsListener *this, bool a2)
{
  Wd1dsListener *v2; // r14
  unsigned int v4; // edi
  int v5; // ebx
  const WCHAR *v6; // rbx
  bool v7; // cc
  const wchar_t *v8; // r8
  unsigned __int16 *v9; // rax
  int v10; // edx
  int v11; // ecx
  unsigned __int16 *v12; // rax
  int v13; // edx
  int v14; // ecx
  const WCHAR **v15; // rsi
  const WCHAR *v16; // rdx
  signed int v17; // eax
  ULONG v18; // ebx
  const WCHAR *v19; // rdx
  signed int started; // eax
  unsigned int v21; // ebx
  ULONG v23; // eax
  WCHAR *v24; // rax
  TRACEHANDLE v25; // rax
  HANDLE *v26; // rbx
  int Thread; // eax
  unsigned int *Level; // [rsp+20h] [rbp-E0h]
  struct _EVENT_TRACE_LOGFILEW Logfile; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE Properties[2336]; // [rsp+210h] [rbp+110h] BYREF
  struct _EVENT_TRACE_PROPERTIES v31; // [rsp+B30h] [rbp+A30h] BYREF
  struct _EVENT_TRACE_PROPERTIES v32; // [rsp+FC0h] [rbp+EC0h] BYREF

  v2 = qword_1401E7480;
  Wd1dsListener::Shutdown(qword_1401E7480, a2);
  v4 = 0;
  if ( !a2 )
  {
    memset(Properties, 0, 0x488u);
    *(_DWORD *)Properties = 1160;
    *(_DWORD *)&Properties[44] = 0x20000;
    UuidCreate((UUID *)&Properties[24]);
    v5 = *((_DWORD *)v2 + 8);
    *(_DWORD *)&Properties[48] = 64;
    *(_DWORD *)&Properties[56] = 64;
    *(_QWORD *)&Properties[64] = 134218112;
    *(_DWORD *)&Properties[116] = 120;
    *(_DWORD *)&Properties[112] = 640;
    memset(&Properties[1168], 0, 0x488u);
    *(_DWORD *)&Properties[1168] = 1160;
    *(_DWORD *)&Properties[1212] = 0x20000;
    UuidCreate((UUID *)&Properties[1192]);
    *(_DWORD *)&Properties[1236] = v5;
    v6 = (const WCHAR *)((char *)v2 + 40);
    v7 = *((_QWORD *)v2 + 8) <= 7u;
    v8 = (const wchar_t *)((char *)v2 + 40);
    *(_DWORD *)&Properties[1216] = 64;
    *(_DWORD *)&Properties[1224] = 64;
    *(_DWORD *)&Properties[1232] = 134218112;
    *(_DWORD *)&Properties[1284] = 120;
    *(_DWORD *)&Properties[1280] = 640;
    if ( !v7 )
      v8 = *(const wchar_t **)v6;
    wcsncpy_s((wchar_t *)&Properties[1288], 0x104u, v8, 0xFFFFFFFFFFFFFFFFuLL);
    if ( *((_QWORD *)v2 + 8) > 7u )
      v6 = *(const WCHAR **)v6;
    if ( !ControlTraceW(0, v6, (PEVENT_TRACE_PROPERTIES)Properties, 0)
      && *(_DWORD *)&Properties[48] == *(_DWORD *)&Properties[1216]
      && *(_DWORD *)&Properties[56] == *(_DWORD *)&Properties[1224]
      && *(_DWORD *)&Properties[68] == *(_DWORD *)&Properties[1236]
      && ((*(_WORD *)&Properties[64] ^ *(_WORD *)&Properties[1232]) & 0x180) == 0 )
    {
      v9 = (unsigned __int16 *)&Properties[120];
      do
      {
        v10 = v9[584];
        v11 = *v9 - v10;
        if ( v11 )
          break;
        ++v9;
      }
      while ( v10 );
      if ( !v11 )
      {
        v12 = (unsigned __int16 *)&Properties[640];
        do
        {
          v13 = v12[584];
          v14 = *v12 - v13;
          if ( v14 )
            break;
          ++v12;
        }
        while ( v13 );
        if ( !v14 )
          *((_QWORD *)v2 + 1) = *(_QWORD *)&Properties[8];
      }
    }
  }
  if ( !*((_QWORD *)v2 + 1) )
  {
    memset(&v31, 0, 0x488u);
    v31.Wnode.BufferSize = 1160;
    v31.Wnode.Flags = 0x20000;
    UuidCreate(&v31.Wnode.Guid);
    v15 = (const WCHAR **)((char *)v2 + 40);
    *(_QWORD *)&v31.LogFileMode = 134218112;
    v7 = *((_QWORD *)v2 + 8) <= 7u;
    v31.BufferSize = 64;
    v16 = (const WCHAR *)((char *)v2 + 40);
    v31.MaximumBuffers = 64;
    v31.LoggerNameOffset = 120;
    v31.LogFileNameOffset = 640;
    if ( !v7 )
      v16 = *v15;
    v17 = ControlTraceW(0, v16, &v31, 1u);
    if ( v17
      && v17 != 4201
      && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
    {
      if ( v17 > 0 )
        v17 = (unsigned __int16)v17 | 0x80070000;
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        47,
        &WPP_3446203f0eb23a99ce68b6ff1fda97d5_Traceguids,
        (unsigned int)v17);
    }
    v18 = *((_DWORD *)v2 + 8);
    memset(&v32, 0, 0x488u);
    v32.Wnode.BufferSize = 1160;
    v32.Wnode.Flags = 0x20000;
    UuidCreate(&v32.Wnode.Guid);
    v7 = *((_QWORD *)v2 + 8) <= 7u;
    v32.BufferSize = 64;
    v19 = (const WCHAR *)((char *)v2 + 40);
    v32.MaximumBuffers = 64;
    v32.LogFileMode = 134218112;
    v32.FlushTimer = v18;
    v32.LoggerNameOffset = 120;
    v32.LogFileNameOffset = 640;
    if ( !v7 )
      v19 = *v15;
    started = StartTraceW((PTRACEHANDLE)v2 + 1, v19, &v32);
    v21 = started;
    if ( started )
    {
      if ( started > 0 )
        v21 = (unsigned __int16)started | 0x80070000;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        if ( *((_QWORD *)v2 + 8) > 7u )
          v15 = (const WCHAR **)*v15;
        WPP_SF_Sd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          48,
          (unsigned int)&WPP_3446203f0eb23a99ce68b6ff1fda97d5_Traceguids,
          (_DWORD)v15,
          v21);
      }
      return v21;
    }
  }
  v23 = EnableTraceEx(&stru_14019DD08, 0, *((_QWORD *)v2 + 1), 1u, 0xFu, 0xE00000000000uLL, 0, 0, 0);
  v21 = v23;
  if ( v23 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 49, &WPP_3446203f0eb23a99ce68b6ff1fda97d5_Traceguids, v23);
    if ( (int)v21 > 0 )
      return (unsigned __int16)v21 | 0x80070000;
    return v21;
  }
  memset(&Logfile, 0, sizeof(Logfile));
  v24 = (WCHAR *)((char *)v2 + 40);
  if ( *((_QWORD *)v2 + 8) > 7u )
    v24 = *(WCHAR **)v24;
  Logfile.LoggerName = v24;
  Logfile.LogFileMode = 268435712;
  Logfile.EventCallback = (PEVENT_CALLBACK)EventRecordCallback;
  v25 = OpenTraceW(&Logfile);
  *(_QWORD *)v2 = v25;
  if ( v25 == -1 )
    return HrGetLastFailure();
  v26 = (HANDLE *)((char *)v2 + 16);
  if ( *((_QWORD *)v2 + 2) )
  {
    CloseHandle(*v26);
    *v26 = 0;
  }
  Thread = CommonUtil::UtilSimpleCreateThread(
             (Wd1dsListener *)((char *)v2 + 16),
             (void **)Wd1dsListener::RealtimeConsumerThreadProc,
             (unsigned int (*)(void *))v2,
             0,
             Level);
  if ( Thread < 0 )
    return (unsigned int)Thread;
  return v4;
}

```

## disassembly

```asm
0x1400e6070  mov     rax, rsp
0x1400e6073  mov     [rax+8], rbx
0x1400e6077  mov     [rax+10h], rsi
0x1400e607b  mov     [rax+18h], rdi
0x1400e607f  mov     [rax+20h], r13
0x1400e6083  push    rbp
0x1400e6084  push    r14
0x1400e6086  push    r15
0x1400e6088  lea     rbp, [rax-1378h]
0x1400e608f  mov     eax, 1460h
0x1400e6094  call    _alloca_probe
0x1400e6099  sub     rsp, rax
0x1400e609c  mov     rax, cs:__security_cookie
0x1400e60a3  xor     rax, rsp
0x1400e60a6  mov     [rbp+1370h+var_20], rax
0x1400e60ad  mov     r14, cs:qword_1401E7480
0x1400e60b4  mov     bl, dl
0x1400e60b6  mov     rcx, r14; this
0x1400e60b9  call    ?Shutdown@Wd1dsListener@@QEAAX_N@Z; Wd1dsListener::Shutdown(bool)
0x1400e60be  xor     edi, edi
0x1400e60c0  mov     esi, 488h
0x1400e60c5  mov     r13d, 8000180h
0x1400e60cb  lea     r15d, [rdi+40h]
0x1400e60cf  test    bl, bl
0x1400e60d1  jnz     loc_1400E627A
0x1400e60d7  mov     r8d, esi; Size
0x1400e60da  lea     rcx, [rbp+1370h+Properties]; void *
0x1400e60e1  xor     edx, edx; Val
0x1400e60e3  call    memset
0x1400e60e8  lea     rcx, [rbp+1370h+Properties.Wnode.Guid]; Uuid
0x1400e60ef  mov     [rbp+1370h+Properties.Wnode.BufferSize], esi
0x1400e60f5  mov     [rbp+1370h+Properties.Wnode.Flags], 20000h
0x1400e60ff  call    cs:__imp_UuidCreate
0x1400e6105  mov     ebx, [r14+20h]
0x1400e6109  lea     rcx, [rbp+1370h+var_DD0]; void *
0x1400e6110  mov     r8d, esi; Size
0x1400e6113  mov     [rbp+1370h+Properties.BufferSize], r15d
0x1400e611a  xor     edx, edx; Val
0x1400e611c  mov     [rbp+1370h+Properties.MaximumBuffers], r15d
0x1400e6123  mov     qword ptr [rbp+1370h+Properties.LogFileMode], r13
0x1400e612a  mov     [rbp+1370h+Properties.LoggerNameOffset], 78h ; 'x'
0x1400e6134  mov     [rbp+1370h+Properties.LogFileNameOffset], 280h
0x1400e613e  call    memset
0x1400e6143  lea     rcx, [rbp+1370h+var_DB8]; Uuid
0x1400e614a  mov     [rbp+1370h+var_DD0], esi
0x1400e6150  mov     [rbp+1370h+var_DA4], 20000h
0x1400e615a  call    cs:__imp_UuidCreate
0x1400e6160  mov     [rbp+1370h+var_D8C], ebx
0x1400e6166  lea     rbx, [r14+28h]
0x1400e616a  cmp     qword ptr [rbx+18h], 7
0x1400e616f  mov     r8, rbx
0x1400e6172  mov     [rbp+1370h+var_DA0], r15d
0x1400e6179  mov     [rbp+1370h+var_D98], r15d
0x1400e6180  mov     [rbp+1370h+var_D90], r13d
0x1400e6187  mov     [rbp+1370h+var_D5C], 78h ; 'x'
0x1400e6191  mov     [rbp+1370h+var_D60], 280h
0x1400e619b  jbe     short loc_1400E61A0
0x1400e619d  mov     r8, [rbx]; Source
0x1400e61a0  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1400e61a4  lea     rcx, [rbp+1370h+Destination]; Destination
0x1400e61ab  mov     edx, 104h; SizeInWords
0x1400e61b0  call    wcsncpy_s
0x1400e61b5  cmp     qword ptr [rbx+18h], 7
0x1400e61ba  jbe     short loc_1400E61BF
0x1400e61bc  mov     rbx, [rbx]
0x1400e61bf  xor     r9d, r9d; ControlCode
0x1400e61c2  lea     r8, [rbp+1370h+Properties]; Properties
0x1400e61c9  mov     rdx, rbx; InstanceName
0x1400e61cc  xor     ecx, ecx; TraceHandle
0x1400e61ce  call    cs:__imp_ControlTraceW
0x1400e61d4  test    eax, eax
0x1400e61d6  jnz     loc_1400E627A
0x1400e61dc  mov     eax, [rbp+1370h+var_DA0]
0x1400e61e2  cmp     [rbp+1370h+Properties.BufferSize], eax
0x1400e61e8  jnz     loc_1400E627A
0x1400e61ee  mov     eax, [rbp+1370h+var_D98]
0x1400e61f4  cmp     [rbp+1370h+Properties.MaximumBuffers], eax
0x1400e61fa  jnz     short loc_1400E627A
0x1400e61fc  mov     eax, [rbp+1370h+var_D8C]
0x1400e6202  cmp     [rbp+1370h+Properties.FlushTimer], eax
0x1400e6208  jnz     short loc_1400E627A
0x1400e620a  mov     eax, [rbp+1370h+var_D90]
0x1400e6210  xor     eax, [rbp+1370h+Properties.LogFileMode]
0x1400e6216  test    eax, 180h
0x1400e621b  jnz     short loc_1400E627A
0x1400e621d  lea     rax, [rbp+1370h+var_11E8]
0x1400e6224  lea     r8, [rbp+1370h+Destination]
0x1400e622b  sub     r8, rax
0x1400e622e  movzx   ecx, word ptr [rax]
0x1400e6231  movzx   edx, word ptr [rax+r8]
0x1400e6236  sub     ecx, edx
0x1400e6238  jnz     short loc_1400E6242
0x1400e623a  add     rax, 2
0x1400e623e  test    edx, edx
0x1400e6240  jnz     short loc_1400E622E
0x1400e6242  test    ecx, ecx
0x1400e6244  jnz     short loc_1400E627A
0x1400e6246  lea     rax, [rbp+1370h+var_FE0]
0x1400e624d  lea     r8, [rbp+1370h+var_B50]
0x1400e6254  sub     r8, rax
0x1400e6257  movzx   ecx, word ptr [rax]
0x1400e625a  movzx   edx, word ptr [rax+r8]
0x1400e625f  sub     ecx, edx
0x1400e6261  jnz     short loc_1400E626B
0x1400e6263  add     rax, 2
0x1400e6267  test    edx, edx
0x1400e6269  jnz     short loc_1400E6257
0x1400e626b  test    ecx, ecx
0x1400e626d  jnz     short loc_1400E627A
0x1400e626f  mov     rax, qword ptr [rbp+1370h+Properties.Wnode.8]
0x1400e6276  mov     [r14+8], rax
0x1400e627a  lea     r15, [r14+8]
0x1400e627e  lea     r13, WPP_GLOBAL_Control
0x1400e6285  cmp     [r15], rdi
0x1400e6288  jnz     loc_1400E642E
0x1400e628e  mov     r8, rsi; Size
0x1400e6291  lea     rcx, [rbp+1370h+var_940]; void *
0x1400e6298  xor     edx, edx; Val
0x1400e629a  call    memset
0x1400e629f  lea     rcx, [rbp+1370h+var_940.Wnode.Guid]; Uuid
0x1400e62a6  mov     [rbp+1370h+var_940.Wnode.BufferSize], esi
0x1400e62ac  mov     [rbp+1370h+var_940.Wnode.Flags], 20000h
0x1400e62b6  call    cs:__imp_UuidCreate
0x1400e62bc  lea     rsi, [r14+28h]
0x1400e62c0  mov     qword ptr [rbp+1370h+var_940.LogFileMode], 8000180h
0x1400e62cb  cmp     qword ptr [rsi+18h], 7
0x1400e62d0  mov     eax, 40h ; '@'
0x1400e62d5  mov     [rbp+1370h+var_940.BufferSize], eax
0x1400e62db  mov     rdx, rsi
0x1400e62de  mov     [rbp+1370h+var_940.MaximumBuffers], eax
0x1400e62e4  mov     [rbp+1370h+var_940.LoggerNameOffset], 78h ; 'x'
0x1400e62ee  mov     [rbp+1370h+var_940.LogFileNameOffset], 280h
0x1400e62f8  jbe     short loc_1400E62FD
0x1400e62fa  mov     rdx, [rsi]; InstanceName
0x1400e62fd  mov     r9d, 1; ControlCode
0x1400e6303  lea     r8, [rbp+1370h+var_940]; Properties
0x1400e630a  xor     ecx, ecx; TraceHandle
0x1400e630c  call    cs:__imp_ControlTraceW
0x1400e6312  test    eax, eax
0x1400e6314  jz      short loc_1400E6353
0x1400e6316  cmp     eax, 1069h
0x1400e631b  jz      short loc_1400E6353
0x1400e631d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e6324  cmp     rcx, r13
0x1400e6327  jz      short loc_1400E6353
0x1400e6329  test    byte ptr [rcx+1Ch], 2
0x1400e632d  jz      short loc_1400E6353
0x1400e632f  test    eax, eax
0x1400e6331  jle     short loc_1400E633B
0x1400e6333  movzx   eax, ax
0x1400e6336  or      eax, 80070000h
0x1400e633b  mov     rcx, [rcx+10h]
0x1400e633f  lea     r8, WPP_3446203f0eb23a99ce68b6ff1fda97d5_Traceguids
0x1400e6346  mov     edx, 2Fh ; '/'
0x1400e634b  mov     r9d, eax
0x1400e634e  call    WPP_SF_d
0x1400e6353  mov     ebx, [r14+20h]
0x1400e6357  lea     rcx, [rbp+1370h+var_4B0]; void *
0x1400e635e  xor     edx, edx; Val
0x1400e6360  mov     r8d, 488h; Size
0x1400e6366  call    memset
0x1400e636b  lea     rcx, [rbp+1370h+var_4B0.Wnode.Guid]; Uuid
0x1400e6372  mov     [rbp+1370h+var_4B0.Wnode.BufferSize], 488h
0x1400e637c  mov     [rbp+1370h+var_4B0.Wnode.Flags], 20000h
0x1400e6386  call    cs:__imp_UuidCreate
0x1400e638c  cmp     qword ptr [rsi+18h], 7
0x1400e6391  mov     eax, 40h ; '@'
0x1400e6396  mov     [rbp+1370h+var_4B0.BufferSize], eax
0x1400e639c  mov     rdx, rsi
0x1400e639f  mov     [rbp+1370h+var_4B0.MaximumBuffers], eax
0x1400e63a5  mov     [rbp+1370h+var_4B0.LogFileMode], 8000180h
0x1400e63af  mov     [rbp+1370h+var_4B0.FlushTimer], ebx
0x1400e63b5  mov     [rbp+1370h+var_4B0.LoggerNameOffset], 78h ; 'x'
0x1400e63bf  mov     [rbp+1370h+var_4B0.LogFileNameOffset], 280h
0x1400e63c9  jbe     short loc_1400E63CE
0x1400e63cb  mov     rdx, [rsi]; InstanceName
0x1400e63ce  lea     r8, [rbp+1370h+var_4B0]; Properties
0x1400e63d5  mov     rcx, r15; TraceHandle
0x1400e63d8  call    cs:__imp_StartTraceW
0x1400e63de  mov     ebx, eax
0x1400e63e0  test    eax, eax
0x1400e63e2  jz      short loc_1400E642E
0x1400e63e4  jle     short loc_1400E63EF
0x1400e63e6  movzx   ebx, ax
0x1400e63e9  or      ebx, 80070000h
0x1400e63ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e63f6  cmp     rcx, r13
0x1400e63f9  jz      short loc_1400E6427
0x1400e63fb  test    byte ptr [rcx+1Ch], 1
0x1400e63ff  jz      short loc_1400E6427
0x1400e6401  cmp     qword ptr [rsi+18h], 7
0x1400e6406  jbe     short loc_1400E640B
0x1400e6408  mov     rsi, [rsi]
0x1400e640b  mov     rcx, [rcx+10h]
0x1400e640f  lea     r8, WPP_3446203f0eb23a99ce68b6ff1fda97d5_Traceguids
0x1400e6416  mov     edx, 30h ; '0'
0x1400e641b  mov     dword ptr [rsp+1470h+Level], ebx
0x1400e641f  mov     r9, rsi
0x1400e6422  call    WPP_SF_Sd
0x1400e6427  mov     eax, ebx
0x1400e6429  jmp     loc_1400E652E
0x1400e642e  mov     r8, [r15]; TraceHandle
0x1400e6431  lea     rcx, stru_14019DD08; ProviderId
0x1400e6438  mov     [rsp+1470h+EnableFilterDesc], rdi; EnableFilterDesc
0x1400e643d  mov     rax, 0E00000000000h
0x1400e6447  mov     [rsp+1470h+EnableProperty], edi; EnableProperty
0x1400e644b  mov     r9d, 1; IsEnabled
0x1400e6451  mov     [rsp+1470h+MatchAllKeyword], rdi; MatchAllKeyword
0x1400e6456  xor     edx, edx; SourceId
0x1400e6458  mov     [rsp+1470h+MatchAnyKeyword], rax; MatchAnyKeyword
0x1400e645d  mov     [rsp+1470h+Level], 0Fh; unsigned int *
0x1400e6462  call    cs:__imp_EnableTraceEx
0x1400e6468  mov     ebx, eax
0x1400e646a  test    eax, eax
0x1400e646c  jz      short loc_1400E64A7
0x1400e646e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e6475  cmp     rcx, r13
0x1400e6478  jz      short loc_1400E6498
0x1400e647a  test    byte ptr [rcx+1Ch], 1
0x1400e647e  jz      short loc_1400E6498
0x1400e6480  mov     rcx, [rcx+10h]
0x1400e6484  lea     r8, WPP_3446203f0eb23a99ce68b6ff1fda97d5_Traceguids
0x1400e648b  mov     edx, 31h ; '1'
0x1400e6490  mov     r9d, eax
0x1400e6493  call    WPP_SF_d
0x1400e6498  test    ebx, ebx
0x1400e649a  jle     short loc_1400E6427
0x1400e649c  movzx   ebx, bx
0x1400e649f  or      ebx, 80070000h
0x1400e64a5  jmp     short loc_1400E6427
0x1400e64a7  xor     edx, edx; Val
0x1400e64a9  lea     rcx, [rsp+1470h+Logfile]; void *
0x1400e64ae  mov     r8d, 1C0h; Size
0x1400e64b4  call    memset
0x1400e64b9  lea     rax, [r14+28h]
0x1400e64bd  cmp     qword ptr [rax+18h], 7
0x1400e64c2  jbe     short loc_1400E64C7
0x1400e64c4  mov     rax, [rax]
0x1400e64c7  mov     [rsp+1470h+Logfile.LoggerName], rax
0x1400e64cc  lea     rcx, [rsp+1470h+Logfile]; Logfile
0x1400e64d1  lea     rax, EventRecordCallback
0x1400e64d8  mov     dword ptr [rsp+1470h+Logfile.1Ch], 10000100h
0x1400e64e0  mov     qword ptr [rbp+1370h+Logfile.1A8h], rax
0x1400e64e7  call    cs:__imp_OpenTraceW
0x1400e64ed  mov     [r14], rax
0x1400e64f0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400e64f4  jnz     short loc_1400E64FD
0x1400e64f6  call    HrGetLastFailure
0x1400e64fb  jmp     short loc_1400E652E
0x1400e64fd  lea     rbx, [r14+10h]
0x1400e6501  cmp     [rbx], rdi
0x1400e6504  jz      short loc_1400E6512
0x1400e6506  mov     rcx, [rbx]; hObject
0x1400e6509  call    cs:__imp_CloseHandle
0x1400e650f  mov     [rbx], rdi
0x1400e6512  xor     r9d, r9d; void *
0x1400e6515  lea     rdx, ?RealtimeConsumerThreadProc@Wd1dsListener@@CAIPEAX@Z; void **
0x1400e651c  mov     r8, r14; unsigned int (*)(void *)
0x1400e651f  mov     rcx, rbx; this
0x1400e6522  call    ?UtilSimpleCreateThread@CommonUtil@@YAJPEAPEAXP6AIPEAX@Z1PEAK@Z; CommonUtil::UtilSimpleCreateThread(void * *,uint (*)(void *),void *,ulong *)
0x1400e6527  test    eax, eax
0x1400e6529  cmovs   edi, eax
0x1400e652c  mov     eax, edi
0x1400e652e  mov     rcx, [rbp+1370h+var_20]
0x1400e6535  xor     rcx, rsp; StackCookie
0x1400e6538  call    __security_check_cookie
0x1400e653d  lea     r11, [rsp+1470h+var_10]
0x1400e6545  mov     rbx, [r11+20h]
0x1400e6549  mov     rsi, [r11+28h]
0x1400e654d  mov     rdi, [r11+30h]
0x1400e6551  mov     r13, [r11+38h]
0x1400e6555  mov     rsp, r11
0x1400e6558  pop     r15
0x1400e655a  pop     r14
0x1400e655c  pop     rbp
0x1400e655d  retn
```
