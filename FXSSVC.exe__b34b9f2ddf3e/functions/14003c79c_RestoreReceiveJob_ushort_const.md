# RestoreReceiveJob(ushort const *)

- ea: `0x14003c79c`
- end: `0x14003cd6e`
- name: `?RestoreReceiveJob@@YAHPEBG@Z`
- size: `1490`
- prototype: `__int64 __fastcall(WCHAR *lpFileName, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config`

## callers

- `0x14003cd74`

## callees

- `0x140002926`
- `0x140002c43`
- `0x140004b30`
- `0x140004b58`
- `0x140004df0`
- `0x140004e68`
- `0x140035f8c`
- `0x140037b14`
- `0x140037f80`
- `0x14003a3d8`
- `0x14003a754`
- `0x14003c79c`
- `0x14003ebe4`
- `0x140042020`
- `0x140065d14`
- `0x140065dbc`
- `0x140067168`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14003c845`
- `KERNEL32!GetLastError` at `0x14003c8ba`
- `KERNEL32!GetLastError` at `0x14003c934`
- `KERNEL32!GetLastError` at `0x14003cbd7`
- `KERNEL32!GetLastError` at `0x14003cc2d`
- `KERNEL32!GetLastError` at `0x14003cc8a`
- `KERNEL32!GetLastError` at `0x14003ccce`
- `KERNEL32!GetLastError` at `0x14003c845`
- `KERNEL32!GetLastError` at `0x14003c8ba`
- `KERNEL32!GetLastError` at `0x14003c934`
- `KERNEL32!GetLastError` at `0x14003cbd7`
- `KERNEL32!GetLastError` at `0x14003cc2d`
- `KERNEL32!GetLastError` at `0x14003cc8a`
- `KERNEL32!GetLastError` at `0x14003ccce`
- `KERNEL32!EnterCriticalSection` at `0x14003cd19`
- `KERNEL32!EnterCriticalSection` at `0x14003cd19`
- `KERNEL32!LeaveCriticalSection` at `0x14003cd36`
- `KERNEL32!LeaveCriticalSection` at `0x14003cd36`
- `KERNEL32!GetFullPathNameW` at `0x14003cb16`
- `KERNEL32!GetFullPathNameW` at `0x14003cb16`

## pseudocode

```c
__int64 __fastcall RestoreReceiveJob(WCHAR *lpFileName, __int64 a2, __int64 a3, __int64 a4)
{
  int v5; // eax
  struct _JOB_QUEUE_FILE *v6; // rbx
  DWORD LastError; // eax
  _JOB_QUEUE *v8; // rax
  _JOB_QUEUE *v9; // rdi
  char v10; // al
  __int64 v11; // rax
  unsigned int v12; // r15d
  DWORD v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rax
  void *v16; // rax
  CMapDeviceId *v17; // rcx
  __int64 v18; // rdx
  unsigned int v19; // ebp
  __int64 v20; // rax
  __int64 v21; // rsi
  SIZE_T v22; // rcx
  __int64 v23; // r14
  __int64 v24; // rax
  void *v25; // rcx
  __int64 v26; // rax
  struct _FAX_ROUTE *v27; // rax
  int v28; // r12d
  _OWORD *v29; // rbp
  const WCHAR *v30; // r14
  __int64 v31; // rax
  _QWORD *v32; // rsi
  __int64 v33; // rax
  _QWORD *v34; // rax
  DWORD v36; // eax
  DWORD v37; // eax
  char v38; // al
  int v39; // r8d
  struct _JOB_QUEUE_FILE *v41; // [rsp+30h] [rbp-278h] BYREF
  LPWSTR FilePart; // [rsp+38h] [rbp-270h] BYREF
  WCHAR Buffer[264]; // [rsp+40h] [rbp-268h] BYREF

  v41 = 0;
  FilePart = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
  }
  v5 = ReadJobQueueFile(lpFileName, &v41, a3, a4);
  v6 = v41;
  if ( !v5 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, LastError);
    }
    goto LABEL_72;
  }
  if ( !(unsigned int)FixupJobQueueFile(v41) )
    goto LABEL_72;
  v8 = AddReceiveJobQueueEntry(*((const unsigned __int16 **)v6 + 6), 0, 8u, *((_QWORD *)v6 + 1));
  v9 = v8;
  if ( !v8 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = GetLastError();
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        84,
        (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
        (_DWORD)lpFileName,
        v10);
    }
    goto LABEL_72;
  }
  if ( *((_DWORD *)v6 + 10) == 128 )
    _JOB_QUEUE::PutStatus(v8, 0x80u);
  v11 = StringDup(lpFileName);
  *((_QWORD *)v9 + 7) = v11;
  v12 = 1;
  if ( lpFileName && !v11 )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_71;
    }
    v13 = GetLastError();
    v14 = 85;
    goto LABEL_24;
  }
  *((_QWORD *)v9 + 2) = *((_QWORD *)v6 + 1);
  *((_DWORD *)v9 + 148) = *((_DWORD *)v6 + 138);
  *((_DWORD *)v9 + 97) = *((_DWORD *)v6 + 86);
  *((_DWORD *)v9 + 16) = *((_DWORD *)v6 + 11);
  *((_QWORD *)v9 + 145) = *((_QWORD *)v6 + 140);
  *((_QWORD *)v9 + 146) = *((_QWORD *)v6 + 141);
  *((_QWORD *)v9 + 3) = *((_QWORD *)v6 + 2);
  v15 = *((unsigned int *)v6 + 273);
  *((_DWORD *)v9 + 456) = v15;
  if ( (_DWORD)v15 )
  {
    v16 = (void *)pMemAlloc(96 * v15);
    *((_QWORD *)v9 + 229) = v16;
    if ( !v16 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_71;
      }
      v18 = 86;
      goto LABEL_70;
    }
    memset_0(v16, 0, 96LL * *((unsigned int *)v9 + 456));
    memcpy_0(*((void **)v9 + 229), (char *)v6 + *((_QWORD *)v6 + 137), 96LL * *((unsigned int *)v9 + 456));
  }
  v19 = 0;
  if ( !*((_DWORD *)v9 + 456) )
  {
LABEL_38:
    v26 = *((_QWORD *)v6 + 134);
    if ( v26 )
    {
      v27 = DeSerializeFaxRoute((unsigned __int64)v6 + v26);
      *((_QWORD *)v9 + 227) = v27;
      if ( v27 )
      {
        v28 = 0;
        v27->JobId = *((_DWORD *)v9 + 8);
        v29 = (_OWORD *)((char *)v6 + *((unsigned int *)v6 + 271));
        v30 = (const WCHAR *)((char *)v6 + *((unsigned int *)v6 + 272));
        if ( *((_DWORD *)v6 + 270) )
        {
          while ( 1 )
          {
            if ( GetFullPathNameW(v30, 0x104u, Buffer, &FilePart) )
            {
              v31 = pMemAlloc(0x28u);
              v32 = (_QWORD *)v31;
              if ( !v31 )
              {
                if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v38 = GetLastError();
                  WPP_SF_Sll(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, v39, (_DWORD)v30, 40, v38);
                }
                goto LABEL_71;
              }
              *(_OWORD *)v31 = 0;
              *(_OWORD *)(v31 + 16) = 0;
              *(_QWORD *)(v31 + 32) = 0;
              v33 = StringDup(Buffer);
              v32[2] = v33;
              if ( !v33 )
              {
                if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v37 = GetLastError();
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    90,
                    &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
                    v37);
                }
                pMemFree(v32);
                goto LABEL_71;
              }
              *(_OWORD *)(v32 + 3) = *v29;
              v34 = (_QWORD *)*((_QWORD *)v9 + 213);
              *v32 = (char *)v9 + 1696;
              v32[1] = v34;
              *v34 = v32;
              ++*((_DWORD *)v9 + 428);
              *((_QWORD *)v9 + 213) = v32;
            }
            ++v29;
            while ( *v30++ )
              ;
            if ( (unsigned int)++v28 >= *((_DWORD *)v6 + 270) )
              goto LABEL_73;
          }
        }
        goto LABEL_73;
      }
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_71;
      }
      v13 = GetLastError();
      v14 = 88;
LABEL_24:
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v13);
      goto LABEL_71;
    }
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_71;
    }
    v18 = 89;
LABEL_70:
    WPP_SF_(*((_QWORD *)v17 + 2), v18, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
    goto LABEL_71;
  }
  while ( 1 )
  {
    v20 = *((_QWORD *)v9 + 229);
    v21 = 96LL * v19;
    v22 = *(unsigned int *)(v21 + v20 + 88);
    if ( !(_DWORD)v22 )
    {
      *(_QWORD *)(v21 + v20 + 80) = 0;
      goto LABEL_37;
    }
    v23 = *(_QWORD *)(v21 + v20 + 80);
    *(_QWORD *)(v21 + *((_QWORD *)v9 + 229) + 80) = pMemAlloc(v22);
    v24 = *((_QWORD *)v9 + 229);
    v25 = *(void **)(v21 + v24 + 80);
    if ( !v25 )
      break;
    memcpy_0(v25, (char *)v6 + v23, *(unsigned int *)(v21 + v24 + 88));
LABEL_37:
    if ( ++v19 >= *((_DWORD *)v9 + 456) )
      goto LABEL_38;
  }
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v36 = GetLastError();
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      87,
      &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
      *(unsigned int *)(*((_QWORD *)v6 + 137) + v21 + 88),
      v36);
  }
LABEL_71:
  EnterCriticalSection(&g_CsQueue);
  DecreaseJobRefCount(v9, 0, 1, 0);
  LeaveCriticalSection(&g_CsQueue);
LABEL_72:
  v12 = 0;
LABEL_73:
  pMemFree(v6);
  return v12;
}

```

## disassembly

```asm
0x14003c79c  push    rbx
0x14003c79e  push    rbp
0x14003c79f  push    rsi
0x14003c7a0  push    rdi
0x14003c7a1  push    r12
0x14003c7a3  push    r13
0x14003c7a5  push    r14
0x14003c7a7  push    r15
0x14003c7a9  sub     rsp, 268h
0x14003c7b0  mov     rax, cs:__security_cookie
0x14003c7b7  xor     rax, rsp
0x14003c7ba  mov     [rsp+2A8h+var_58], rax
0x14003c7c2  xor     r13d, r13d
0x14003c7c5  mov     rsi, rcx
0x14003c7c8  mov     [rsp+2A8h+var_278], r13
0x14003c7cd  mov     [rsp+2A8h+FilePart], r13
0x14003c7d2  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c7d9  lea     r14, WPP_GLOBAL_Control
0x14003c7e0  lea     rbp, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003c7e7  mov     r12b, 4
0x14003c7ea  cmp     rcx, r14
0x14003c7ed  jz      short loc_14003C80B
0x14003c7ef  test    [rcx+1Ch], r12b
0x14003c7f3  jz      short loc_14003C80B
0x14003c7f5  cmp     byte ptr [rcx+19h], 5
0x14003c7f9  jb      short loc_14003C80B
0x14003c7fb  mov     rcx, [rcx+10h]
0x14003c7ff  lea     edx, [r13+52h]
0x14003c803  mov     r8, rbp
0x14003c806  call    WPP_SF_
0x14003c80b  lea     rdx, [rsp+2A8h+var_278]; struct _JOB_QUEUE_FILE **
0x14003c810  mov     rcx, rsi; lpFileName
0x14003c813  call    ?ReadJobQueueFile@@YAHPEBGPEAPEAU_JOB_QUEUE_FILE@@@Z; ReadJobQueueFile(ushort const *,_JOB_QUEUE_FILE * *)
0x14003c818  mov     rbx, [rsp+2A8h+var_278]
0x14003c81d  test    eax, eax
0x14003c81f  jnz     short loc_14003C86B
0x14003c821  mov     rax, cs:WPP_GLOBAL_Control
0x14003c828  cmp     rax, r14
0x14003c82b  jz      loc_14003CD3C
0x14003c831  test    [rax+1Ch], r12b
0x14003c835  jz      loc_14003CD3C
0x14003c83b  cmp     byte ptr [rax+19h], 2
0x14003c83f  jb      loc_14003CD3C
0x14003c845  call    cs:__imp_GetLastError
0x14003c84b  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c852  mov     edx, 53h ; 'S'
0x14003c857  mov     r9d, eax
0x14003c85a  mov     r8, rbp
0x14003c85d  mov     rcx, [rcx+10h]
0x14003c861  call    WPP_SF_d
0x14003c866  jmp     loc_14003CD3C
0x14003c86b  mov     rcx, rbx; struct _JOB_QUEUE_FILE *
0x14003c86e  call    ?FixupJobQueueFile@@YAHPEAU_JOB_QUEUE_FILE@@@Z; FixupJobQueueFile(_JOB_QUEUE_FILE *)
0x14003c873  test    eax, eax
0x14003c875  jz      loc_14003CD3C
0x14003c87b  mov     r9, [rbx+8]; unsigned __int64
0x14003c87f  xor     edx, edx; struct _JOB_ENTRY *
0x14003c881  mov     rcx, [rbx+30h]; unsigned __int16 *
0x14003c885  lea     r8d, [rdx+8]; unsigned int
0x14003c889  call    ?AddReceiveJobQueueEntry@@YAPEAU_JOB_QUEUE@@PEBGPEAU_JOB_ENTRY@@K_K@Z; AddReceiveJobQueueEntry(ushort const *,_JOB_ENTRY *,ulong,unsigned __int64)
0x14003c88e  mov     rdi, rax
0x14003c891  test    rax, rax
0x14003c894  jnz     short loc_14003C8E2
0x14003c896  mov     rax, cs:WPP_GLOBAL_Control
0x14003c89d  cmp     rax, r14
0x14003c8a0  jz      loc_14003CD3C
0x14003c8a6  test    [rax+1Ch], r12b
0x14003c8aa  jz      loc_14003CD3C
0x14003c8b0  cmp     byte ptr [rax+19h], 2
0x14003c8b4  jb      loc_14003CD3C
0x14003c8ba  call    cs:__imp_GetLastError
0x14003c8c0  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c8c7  lea     edx, [rdi+54h]
0x14003c8ca  mov     r9, rsi
0x14003c8cd  mov     [rsp+2A8h+var_288], eax
0x14003c8d1  mov     r8, rbp
0x14003c8d4  mov     rcx, [rcx+10h]
0x14003c8d8  call    WPP_SF_Sd
0x14003c8dd  jmp     loc_14003CD3C
0x14003c8e2  mov     edx, 80h; unsigned int
0x14003c8e7  cmp     [rbx+28h], edx
0x14003c8ea  jnz     short loc_14003C8F4
0x14003c8ec  mov     rcx, rdi; this
0x14003c8ef  call    ?PutStatus@_JOB_QUEUE@@QEAAXK@Z; _JOB_QUEUE::PutStatus(ulong)
0x14003c8f4  mov     rcx, rsi; unsigned __int16 *
0x14003c8f7  call    StringDup
0x14003c8fc  mov     [rdi+38h], rax
0x14003c900  mov     r15d, 1
0x14003c906  test    rsi, rsi
0x14003c909  jz      short loc_14003C959
0x14003c90b  test    rax, rax
0x14003c90e  jnz     short loc_14003C959
0x14003c910  mov     rax, cs:WPP_GLOBAL_Control
0x14003c917  cmp     rax, r14
0x14003c91a  jz      loc_14003CD12
0x14003c920  test    [rax+1Ch], r12b
0x14003c924  jz      loc_14003CD12
0x14003c92a  cmp     byte ptr [rax+19h], 2
0x14003c92e  jb      loc_14003CD12
0x14003c934  call    cs:__imp_GetLastError
0x14003c93a  lea     edx, [r15+54h]
0x14003c93e  mov     r8, rbp
0x14003c941  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c948  mov     r9d, eax
0x14003c94b  mov     rcx, [rcx+10h]
0x14003c94f  call    WPP_SF_d
0x14003c954  jmp     loc_14003CD12
0x14003c959  mov     rax, [rbx+8]
0x14003c95d  mov     [rdi+10h], rax
0x14003c961  mov     eax, [rbx+228h]
0x14003c967  mov     [rdi+250h], eax
0x14003c96d  mov     eax, [rbx+158h]
0x14003c973  mov     [rdi+184h], eax
0x14003c979  mov     eax, [rbx+2Ch]
0x14003c97c  mov     [rdi+40h], eax
0x14003c97f  mov     rax, [rbx+460h]
0x14003c986  mov     [rdi+488h], rax
0x14003c98d  mov     rax, [rbx+468h]
0x14003c994  mov     [rdi+490h], rax
0x14003c99b  mov     rax, [rbx+10h]
0x14003c99f  mov     [rdi+18h], rax
0x14003c9a3  mov     eax, [rbx+444h]
0x14003c9a9  mov     [rdi+720h], eax
0x14003c9af  test    eax, eax
0x14003c9b1  jz      loc_14003CA3B
0x14003c9b7  lea     rcx, [rax+rax*2]
0x14003c9bb  shl     rcx, 5; dwBytes
0x14003c9bf  call    pMemAlloc
0x14003c9c4  mov     [rdi+728h], rax
0x14003c9cb  mov     rcx, rax; void *
0x14003c9ce  test    rax, rax
0x14003c9d1  jnz     short loc_14003CA02
0x14003c9d3  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c9da  cmp     rcx, r14
0x14003c9dd  jz      loc_14003CD12
0x14003c9e3  test    [rcx+1Ch], r12b
0x14003c9e7  jz      loc_14003CD12
0x14003c9ed  cmp     byte ptr [rcx+19h], 2
0x14003c9f1  jb      loc_14003CD12
0x14003c9f7  lea     edx, [rax+56h]
0x14003c9fa  mov     r8, rbp
0x14003c9fd  jmp     loc_14003CD09
0x14003ca02  mov     eax, [rdi+720h]
0x14003ca08  xor     edx, edx; Val
0x14003ca0a  lea     r8, [rax+rax*2]
0x14003ca0e  shl     r8, 5; Size
0x14003ca12  call    memset_0
0x14003ca17  mov     eax, [rdi+720h]
0x14003ca1d  mov     rdx, [rbx+448h]
0x14003ca24  mov     rcx, [rdi+728h]; void *
0x14003ca2b  add     rdx, rbx; Src
0x14003ca2e  lea     r8, [rax+rax*2]
0x14003ca32  shl     r8, 5; Size
0x14003ca36  call    memcpy_0
0x14003ca3b  mov     ebp, r13d
0x14003ca3e  cmp     [rdi+720h], r13d
0x14003ca45  jbe     short loc_14003CAB2
0x14003ca47  mov     eax, ebp
0x14003ca49  lea     rsi, [rax+rax*2]
0x14003ca4d  mov     rax, [rdi+728h]
0x14003ca54  shl     rsi, 5
0x14003ca58  mov     ecx, [rsi+rax+58h]; dwBytes
0x14003ca5c  test    ecx, ecx
0x14003ca5e  jz      short loc_14003CA9B
0x14003ca60  mov     r14, [rsi+rax+50h]
0x14003ca65  call    pMemAlloc
0x14003ca6a  mov     rcx, [rdi+728h]
0x14003ca71  mov     [rsi+rcx+50h], rax
0x14003ca76  mov     rax, [rdi+728h]
0x14003ca7d  mov     rcx, [rsi+rax+50h]; void *
0x14003ca82  test    rcx, rcx
0x14003ca85  jz      loc_14003CBAC
0x14003ca8b  mov     r8d, [rsi+rax+58h]; Size
0x14003ca90  lea     rdx, [r14+rbx]; Src
0x14003ca94  call    memcpy_0
0x14003ca99  jmp     short loc_14003CAA0
0x14003ca9b  mov     [rsi+rax+50h], r13
0x14003caa0  add     ebp, r15d
0x14003caa3  cmp     ebp, [rdi+720h]
0x14003caa9  jb      short loc_14003CA47
0x14003caab  lea     r14, WPP_GLOBAL_Control
0x14003cab2  mov     rax, [rbx+430h]
0x14003cab9  test    rax, rax
0x14003cabc  jz      loc_14003CCE5
0x14003cac2  lea     rcx, [rax+rbx]; struct _FAX_ROUTE *
0x14003cac6  call    ?DeSerializeFaxRoute@@YAPEAU_FAX_ROUTE@@PEAU1@@Z; DeSerializeFaxRoute(_FAX_ROUTE *)
0x14003cacb  mov     [rdi+718h], rax
0x14003cad2  test    rax, rax
0x14003cad5  jz      loc_14003CCB6
0x14003cadb  mov     ecx, [rdi+20h]
0x14003cade  mov     r12d, r13d
0x14003cae1  mov     [rax+4], ecx
0x14003cae4  mov     ebp, [rbx+43Ch]
0x14003caea  mov     r14d, [rbx+440h]
0x14003caf1  add     rbp, rbx
0x14003caf4  add     r14, rbx
0x14003caf7  cmp     [rbx+438h], r13d
0x14003cafe  jbe     loc_14003CD3F
0x14003cb04  lea     r9, [rsp+2A8h+FilePart]; lpFilePart
0x14003cb09  mov     edx, 104h; nBufferLength
0x14003cb0e  lea     r8, [rsp+2A8h+Buffer]; lpBuffer
0x14003cb13  mov     rcx, r14; lpFileName
0x14003cb16  call    cs:__imp_GetFullPathNameW
0x14003cb1c  test    eax, eax
0x14003cb1e  jz      short loc_14003CB86
0x14003cb20  mov     ecx, 28h ; '('; dwBytes
0x14003cb25  call    pMemAlloc
0x14003cb2a  mov     rsi, rax
0x14003cb2d  test    rax, rax
0x14003cb30  jz      loc_14003CC5F
0x14003cb36  xorps   xmm0, xmm0
0x14003cb39  lea     rcx, [rsp+2A8h+Buffer]; unsigned __int16 *
0x14003cb3e  movups  xmmword ptr [rsi], xmm0
0x14003cb41  xor     eax, eax
0x14003cb43  movups  xmmword ptr [rsi+10h], xmm0
0x14003cb47  mov     [rsi+20h], rax
0x14003cb4b  call    StringDup
0x14003cb50  mov     [rsi+10h], rax
0x14003cb54  test    rax, rax
0x14003cb57  jz      loc_14003CC0E
0x14003cb5d  movups  xmm0, xmmword ptr [rbp+0]
0x14003cb61  lea     rcx, [rdi+6A0h]
0x14003cb68  movdqu  xmmword ptr [rsi+18h], xmm0
0x14003cb6d  mov     rax, [rcx+8]
0x14003cb71  mov     [rsi], rcx
0x14003cb74  mov     [rsi+8], rax
0x14003cb78  mov     [rax], rsi
0x14003cb7b  add     [rdi+6B0h], r15d
0x14003cb82  mov     [rcx+8], rsi
0x14003cb86  add     rbp, 10h
0x14003cb8a  movzx   eax, word ptr [r14]
0x14003cb8e  add     r14, 2
0x14003cb92  test    ax, ax
0x14003cb95  jnz     short loc_14003CB8A
0x14003cb97  add     r12d, r15d
0x14003cb9a  cmp     r12d, [rbx+438h]
0x14003cba1  jb      loc_14003CB04
0x14003cba7  jmp     loc_14003CD3F
0x14003cbac  mov     rax, cs:WPP_GLOBAL_Control
0x14003cbb3  lea     rcx, WPP_GLOBAL_Control
0x14003cbba  cmp     rax, rcx
0x14003cbbd  jz      loc_14003CD12
0x14003cbc3  test    [rax+1Ch], r12b
0x14003cbc7  jz      loc_14003CD12
0x14003cbcd  cmp     byte ptr [rax+19h], 2
0x14003cbd1  jb      loc_14003CD12
0x14003cbd7  call    cs:__imp_GetLastError
0x14003cbdd  mov     r9, [rbx+448h]
0x14003cbe4  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003cbeb  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cbf2  mov     edx, 57h ; 'W'
0x14003cbf7  mov     [rsp+2A8h+var_288], eax
0x14003cbfb  mov     r9d, [r9+rsi+58h]
0x14003cc00  mov     rcx, [rcx+10h]
0x14003cc04  call    WPP_SF_dd
0x14003cc09  jmp     loc_14003CD12
0x14003cc0e  mov     rax, cs:WPP_GLOBAL_Control
0x14003cc15  lea     rcx, WPP_GLOBAL_Control
0x14003cc1c  cmp     rax, rcx
0x14003cc1f  jz      short loc_14003CC52
0x14003cc21  test    byte ptr [rax+1Ch], 4
0x14003cc25  jz      short loc_14003CC52
0x14003cc27  cmp     byte ptr [rax+19h], 2
0x14003cc2b  jb      short loc_14003CC52
0x14003cc2d  call    cs:__imp_GetLastError
0x14003cc33  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cc3a  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003cc41  mov     edx, 5Ah ; 'Z'
0x14003cc46  mov     r9d, eax
0x14003cc49  mov     rcx, [rcx+10h]
0x14003cc4d  call    WPP_SF_d
0x14003cc52  mov     rcx, rsi; lpMem
0x14003cc55  call    pMemFree
0x14003cc5a  jmp     loc_14003CD12
0x14003cc5f  mov     rax, cs:WPP_GLOBAL_Control
0x14003cc66  lea     rcx, WPP_GLOBAL_Control
0x14003cc6d  cmp     rax, rcx
0x14003cc70  jz      loc_14003CD12
0x14003cc76  test    byte ptr [rax+1Ch], 4
0x14003cc7a  jz      loc_14003CD12
0x14003cc80  cmp     byte ptr [rax+19h], 2
0x14003cc84  jb      loc_14003CD12
0x14003cc8a  call    cs:__imp_GetLastError
0x14003cc90  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cc97  mov     edx, 5Bh ; '['
0x14003cc9c  mov     [rsp+2A8h+var_280], eax
0x14003cca0  mov     r9, r14
0x14003cca3  mov     [rsp+2A8h+var_288], 28h ; '('
0x14003ccab  mov     rcx, [rcx+10h]
0x14003ccaf  call    WPP_SF_Sll
0x14003ccb4  jmp     short loc_14003CD12
0x14003ccb6  mov     rax, cs:WPP_GLOBAL_Control
0x14003ccbd  cmp     rax, r14
0x14003ccc0  jz      short loc_14003CD12
0x14003ccc2  test    [rax+1Ch], r12b
0x14003ccc6  jz      short loc_14003CD12
0x14003ccc8  cmp     byte ptr [rax+19h], 2
0x14003cccc  jb      short loc_14003CD12
0x14003ccce  call    cs:__imp_GetLastError
0x14003ccd4  mov     edx, 58h ; 'X'
  ... truncated ...
```
