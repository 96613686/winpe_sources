# RestoreReceiveJob(ushort const *)

- ea: `0x14003ea34`
- end: `0x14003f043`
- name: `?RestoreReceiveJob@@YAHPEBG@Z`
- size: `1551`
- prototype: `__int64 __fastcall(WCHAR *lpFileName, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config`

## callers

- `0x14003f04c`

## callees

- `0x140002946`
- `0x140002c73`
- `0x140004c78`
- `0x140004ca8`
- `0x140004f64`
- `0x140004fe4`
- `0x140037d3c`
- `0x1400399f0`
- `0x140039e88`
- `0x14003c4ac`
- `0x14003c834`
- `0x14003ea34`
- `0x140041054`
- `0x140044738`
- `0x1400698ec`
- `0x14006998c`
- `0x14006af2c`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14003eadd`
- `KERNEL32!GetLastError` at `0x14003eb58`
- `KERNEL32!GetLastError` at `0x14003ebd8`
- `KERNEL32!GetLastError` at `0x14003ee87`
- `KERNEL32!GetLastError` at `0x14003eee3`
- `KERNEL32!GetLastError` at `0x14003ef46`
- `KERNEL32!GetLastError` at `0x14003ef90`
- `KERNEL32!GetLastError` at `0x14003eadd`
- `KERNEL32!GetLastError` at `0x14003eb58`
- `KERNEL32!GetLastError` at `0x14003ebd8`
- `KERNEL32!GetLastError` at `0x14003ee87`
- `KERNEL32!GetLastError` at `0x14003eee3`
- `KERNEL32!GetLastError` at `0x14003ef46`
- `KERNEL32!GetLastError` at `0x14003ef90`
- `KERNEL32!EnterCriticalSection` at `0x14003efe1`
- `KERNEL32!EnterCriticalSection` at `0x14003efe1`
- `KERNEL32!LeaveCriticalSection` at `0x14003f004`
- `KERNEL32!LeaveCriticalSection` at `0x14003f004`
- `KERNEL32!GetFullPathNameW` at `0x14003edc0`
- `KERNEL32!GetFullPathNameW` at `0x14003edc0`

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
  unsigned __int16 *v11; // rax
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
  unsigned __int16 *v33; // rax
  _QWORD *v34; // rax
  DWORD v36; // eax
  char v37; // al
  int v38; // r8d
  struct _JOB_QUEUE_FILE *v40; // [rsp+30h] [rbp-278h] BYREF
  LPWSTR FilePart; // [rsp+38h] [rbp-270h] BYREF
  WCHAR Buffer[264]; // [rsp+40h] [rbp-268h] BYREF

  v40 = 0;
  FilePart = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
  }
  v5 = ReadJobQueueFile(lpFileName, &v40, a3, a4);
  v6 = v40;
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
  if ( !(unsigned int)FixupJobQueueFile(v40) )
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
                  v37 = GetLastError();
                  WPP_SF_Sll(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, v38, (_DWORD)v30, 40, v37);
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
                  v36 = GetLastError();
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    90,
                    &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
                    v36);
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
    GetLastError();
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
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
0x14003ea34  push    rbx
0x14003ea36  push    rbp
0x14003ea37  push    rsi
0x14003ea38  push    rdi
0x14003ea39  push    r12
0x14003ea3b  push    r13
0x14003ea3d  push    r14
0x14003ea3f  push    r15
0x14003ea41  sub     rsp, 268h
0x14003ea48  mov     rax, cs:__security_cookie
0x14003ea4f  xor     rax, rsp
0x14003ea52  mov     [rsp+2A8h+var_58], rax
0x14003ea5a  xor     r13d, r13d
0x14003ea5d  mov     rsi, rcx
0x14003ea60  mov     [rsp+2A8h+var_278], r13
0x14003ea65  mov     [rsp+2A8h+FilePart], r13
0x14003ea6a  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ea71  lea     r14, WPP_GLOBAL_Control
0x14003ea78  lea     rbp, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003ea7f  mov     r12b, 4
0x14003ea82  cmp     rcx, r14
0x14003ea85  jz      short loc_14003EAA3
0x14003ea87  test    [rcx+1Ch], r12b
0x14003ea8b  jz      short loc_14003EAA3
0x14003ea8d  cmp     byte ptr [rcx+19h], 5
0x14003ea91  jb      short loc_14003EAA3
0x14003ea93  mov     rcx, [rcx+10h]
0x14003ea97  lea     edx, [r13+52h]
0x14003ea9b  mov     r8, rbp
0x14003ea9e  call    WPP_SF_
0x14003eaa3  lea     rdx, [rsp+2A8h+var_278]; struct _JOB_QUEUE_FILE **
0x14003eaa8  mov     rcx, rsi; lpFileName
0x14003eaab  call    ?ReadJobQueueFile@@YAHPEBGPEAPEAU_JOB_QUEUE_FILE@@@Z; ReadJobQueueFile(ushort const *,_JOB_QUEUE_FILE * *)
0x14003eab0  mov     rbx, [rsp+2A8h+var_278]
0x14003eab5  test    eax, eax
0x14003eab7  jnz     short loc_14003EB09
0x14003eab9  mov     rax, cs:WPP_GLOBAL_Control
0x14003eac0  cmp     rax, r14
0x14003eac3  jz      loc_14003F010
0x14003eac9  test    [rax+1Ch], r12b
0x14003eacd  jz      loc_14003F010
0x14003ead3  cmp     byte ptr [rax+19h], 2
0x14003ead7  jb      loc_14003F010
0x14003eadd  call    cs:__imp_GetLastError
0x14003eae4  nop     dword ptr [rax+rax+00h]
0x14003eae9  mov     rcx, cs:WPP_GLOBAL_Control
0x14003eaf0  mov     edx, 53h ; 'S'
0x14003eaf5  mov     r9d, eax
0x14003eaf8  mov     r8, rbp
0x14003eafb  mov     rcx, [rcx+10h]
0x14003eaff  call    WPP_SF_d
0x14003eb04  jmp     loc_14003F010
0x14003eb09  mov     rcx, rbx; struct _JOB_QUEUE_FILE *
0x14003eb0c  call    ?FixupJobQueueFile@@YAHPEAU_JOB_QUEUE_FILE@@@Z; FixupJobQueueFile(_JOB_QUEUE_FILE *)
0x14003eb11  test    eax, eax
0x14003eb13  jz      loc_14003F010
0x14003eb19  mov     r9, [rbx+8]; unsigned __int64
0x14003eb1d  xor     edx, edx; struct _JOB_ENTRY *
0x14003eb1f  mov     rcx, [rbx+30h]; unsigned __int16 *
0x14003eb23  lea     r8d, [rdx+8]; unsigned int
0x14003eb27  call    ?AddReceiveJobQueueEntry@@YAPEAU_JOB_QUEUE@@PEBGPEAU_JOB_ENTRY@@K_K@Z; AddReceiveJobQueueEntry(ushort const *,_JOB_ENTRY *,ulong,unsigned __int64)
0x14003eb2c  mov     rdi, rax
0x14003eb2f  test    rax, rax
0x14003eb32  jnz     short loc_14003EB86
0x14003eb34  mov     rax, cs:WPP_GLOBAL_Control
0x14003eb3b  cmp     rax, r14
0x14003eb3e  jz      loc_14003F010
0x14003eb44  test    [rax+1Ch], r12b
0x14003eb48  jz      loc_14003F010
0x14003eb4e  cmp     byte ptr [rax+19h], 2
0x14003eb52  jb      loc_14003F010
0x14003eb58  call    cs:__imp_GetLastError
0x14003eb5f  nop     dword ptr [rax+rax+00h]
0x14003eb64  mov     rcx, cs:WPP_GLOBAL_Control
0x14003eb6b  lea     edx, [rdi+54h]
0x14003eb6e  mov     r9, rsi
0x14003eb71  mov     [rsp+2A8h+var_288], eax
0x14003eb75  mov     r8, rbp
0x14003eb78  mov     rcx, [rcx+10h]
0x14003eb7c  call    WPP_SF_Sd
0x14003eb81  jmp     loc_14003F010
0x14003eb86  mov     edx, 80h; unsigned int
0x14003eb8b  cmp     [rbx+28h], edx
0x14003eb8e  jnz     short loc_14003EB98
0x14003eb90  mov     rcx, rdi; this
0x14003eb93  call    ?PutStatus@_JOB_QUEUE@@QEAAXK@Z; _JOB_QUEUE::PutStatus(ulong)
0x14003eb98  mov     rcx, rsi; unsigned __int16 *
0x14003eb9b  call    StringDup
0x14003eba0  mov     [rdi+38h], rax
0x14003eba4  mov     r15d, 1
0x14003ebaa  test    rsi, rsi
0x14003ebad  jz      short loc_14003EC03
0x14003ebaf  test    rax, rax
0x14003ebb2  jnz     short loc_14003EC03
0x14003ebb4  mov     rax, cs:WPP_GLOBAL_Control
0x14003ebbb  cmp     rax, r14
0x14003ebbe  jz      loc_14003EFDA
0x14003ebc4  test    [rax+1Ch], r12b
0x14003ebc8  jz      loc_14003EFDA
0x14003ebce  cmp     byte ptr [rax+19h], 2
0x14003ebd2  jb      loc_14003EFDA
0x14003ebd8  call    cs:__imp_GetLastError
0x14003ebdf  nop     dword ptr [rax+rax+00h]
0x14003ebe4  lea     edx, [r15+54h]
0x14003ebe8  mov     r8, rbp
0x14003ebeb  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ebf2  mov     r9d, eax
0x14003ebf5  mov     rcx, [rcx+10h]
0x14003ebf9  call    WPP_SF_d
0x14003ebfe  jmp     loc_14003EFDA
0x14003ec03  mov     rax, [rbx+8]
0x14003ec07  mov     [rdi+10h], rax
0x14003ec0b  mov     eax, [rbx+228h]
0x14003ec11  mov     [rdi+250h], eax
0x14003ec17  mov     eax, [rbx+158h]
0x14003ec1d  mov     [rdi+184h], eax
0x14003ec23  mov     eax, [rbx+2Ch]
0x14003ec26  mov     [rdi+40h], eax
0x14003ec29  mov     rax, [rbx+460h]
0x14003ec30  mov     [rdi+488h], rax
0x14003ec37  mov     rax, [rbx+468h]
0x14003ec3e  mov     [rdi+490h], rax
0x14003ec45  mov     rax, [rbx+10h]
0x14003ec49  mov     [rdi+18h], rax
0x14003ec4d  mov     eax, [rbx+444h]
0x14003ec53  mov     [rdi+720h], eax
0x14003ec59  test    eax, eax
0x14003ec5b  jz      loc_14003ECE5
0x14003ec61  lea     rcx, [rax+rax*2]
0x14003ec65  shl     rcx, 5; dwBytes
0x14003ec69  call    pMemAlloc
0x14003ec6e  mov     [rdi+728h], rax
0x14003ec75  mov     rcx, rax; void *
0x14003ec78  test    rax, rax
0x14003ec7b  jnz     short loc_14003ECAC
0x14003ec7d  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ec84  cmp     rcx, r14
0x14003ec87  jz      loc_14003EFDA
0x14003ec8d  test    [rcx+1Ch], r12b
0x14003ec91  jz      loc_14003EFDA
0x14003ec97  cmp     byte ptr [rcx+19h], 2
0x14003ec9b  jb      loc_14003EFDA
0x14003eca1  lea     edx, [rax+56h]
0x14003eca4  mov     r8, rbp
0x14003eca7  jmp     loc_14003EFD1
0x14003ecac  mov     eax, [rdi+720h]
0x14003ecb2  xor     edx, edx; Val
0x14003ecb4  lea     r8, [rax+rax*2]
0x14003ecb8  shl     r8, 5; Size
0x14003ecbc  call    memset_0
0x14003ecc1  mov     eax, [rdi+720h]
0x14003ecc7  mov     rdx, [rbx+448h]
0x14003ecce  mov     rcx, [rdi+728h]; void *
0x14003ecd5  add     rdx, rbx; Src
0x14003ecd8  lea     r8, [rax+rax*2]
0x14003ecdc  shl     r8, 5; Size
0x14003ece0  call    memcpy_0
0x14003ece5  mov     ebp, r13d
0x14003ece8  cmp     [rdi+720h], r13d
0x14003ecef  jbe     short loc_14003ED5C
0x14003ecf1  mov     eax, ebp
0x14003ecf3  lea     rsi, [rax+rax*2]
0x14003ecf7  mov     rax, [rdi+728h]
0x14003ecfe  shl     rsi, 5
0x14003ed02  mov     ecx, [rsi+rax+58h]; dwBytes
0x14003ed06  test    ecx, ecx
0x14003ed08  jz      short loc_14003ED45
0x14003ed0a  mov     r14, [rsi+rax+50h]
0x14003ed0f  call    pMemAlloc
0x14003ed14  mov     rcx, [rdi+728h]
0x14003ed1b  mov     [rsi+rcx+50h], rax
0x14003ed20  mov     rax, [rdi+728h]
0x14003ed27  mov     rcx, [rsi+rax+50h]; void *
0x14003ed2c  test    rcx, rcx
0x14003ed2f  jz      loc_14003EE5C
0x14003ed35  mov     r8d, [rsi+rax+58h]; Size
0x14003ed3a  lea     rdx, [r14+rbx]; Src
0x14003ed3e  call    memcpy_0
0x14003ed43  jmp     short loc_14003ED4A
0x14003ed45  mov     [rsi+rax+50h], r13
0x14003ed4a  add     ebp, r15d
0x14003ed4d  cmp     ebp, [rdi+720h]
0x14003ed53  jb      short loc_14003ECF1
0x14003ed55  lea     r14, WPP_GLOBAL_Control
0x14003ed5c  mov     rax, [rbx+430h]
0x14003ed63  test    rax, rax
0x14003ed66  jz      loc_14003EFAD
0x14003ed6c  lea     rcx, [rax+rbx]; struct _FAX_ROUTE *
0x14003ed70  call    ?DeSerializeFaxRoute@@YAPEAU_FAX_ROUTE@@PEAU1@@Z; DeSerializeFaxRoute(_FAX_ROUTE *)
0x14003ed75  mov     [rdi+718h], rax
0x14003ed7c  test    rax, rax
0x14003ed7f  jz      loc_14003EF78
0x14003ed85  mov     ecx, [rdi+20h]
0x14003ed88  mov     r12d, r13d
0x14003ed8b  mov     [rax+4], ecx
0x14003ed8e  mov     ebp, [rbx+43Ch]
0x14003ed94  mov     r14d, [rbx+440h]
0x14003ed9b  add     rbp, rbx
0x14003ed9e  add     r14, rbx
0x14003eda1  cmp     [rbx+438h], r13d
0x14003eda8  jbe     loc_14003F013
0x14003edae  lea     r9, [rsp+2A8h+FilePart]; lpFilePart
0x14003edb3  mov     edx, 104h; nBufferLength
0x14003edb8  lea     r8, [rsp+2A8h+Buffer]; lpBuffer
0x14003edbd  mov     rcx, r14; lpFileName
0x14003edc0  call    cs:__imp_GetFullPathNameW
0x14003edc7  nop     dword ptr [rax+rax+00h]
0x14003edcc  test    eax, eax
0x14003edce  jz      short loc_14003EE36
0x14003edd0  mov     ecx, 28h ; '('; dwBytes
0x14003edd5  call    pMemAlloc
0x14003edda  mov     rsi, rax
0x14003eddd  test    rax, rax
0x14003ede0  jz      loc_14003EF1B
0x14003ede6  xorps   xmm0, xmm0
0x14003ede9  lea     rcx, [rsp+2A8h+Buffer]; unsigned __int16 *
0x14003edee  movups  xmmword ptr [rsi], xmm0
0x14003edf1  xor     eax, eax
0x14003edf3  movups  xmmword ptr [rsi+10h], xmm0
0x14003edf7  mov     [rsi+20h], rax
0x14003edfb  call    StringDup
0x14003ee00  mov     [rsi+10h], rax
0x14003ee04  test    rax, rax
0x14003ee07  jz      loc_14003EEC4
0x14003ee0d  movups  xmm0, xmmword ptr [rbp+0]
0x14003ee11  lea     rcx, [rdi+6A0h]
0x14003ee18  movdqu  xmmword ptr [rsi+18h], xmm0
0x14003ee1d  mov     rax, [rcx+8]
0x14003ee21  mov     [rsi], rcx
0x14003ee24  mov     [rsi+8], rax
0x14003ee28  mov     [rax], rsi
0x14003ee2b  add     [rdi+6B0h], r15d
0x14003ee32  mov     [rcx+8], rsi
0x14003ee36  add     rbp, 10h
0x14003ee3a  movzx   eax, word ptr [r14]
0x14003ee3e  add     r14, 2
0x14003ee42  test    ax, ax
0x14003ee45  jnz     short loc_14003EE3A
0x14003ee47  add     r12d, r15d
0x14003ee4a  cmp     r12d, [rbx+438h]
0x14003ee51  jb      loc_14003EDAE
0x14003ee57  jmp     loc_14003F013
0x14003ee5c  mov     rax, cs:WPP_GLOBAL_Control
0x14003ee63  lea     rcx, WPP_GLOBAL_Control
0x14003ee6a  cmp     rax, rcx
0x14003ee6d  jz      loc_14003EFDA
0x14003ee73  test    [rax+1Ch], r12b
0x14003ee77  jz      loc_14003EFDA
0x14003ee7d  cmp     byte ptr [rax+19h], 2
0x14003ee81  jb      loc_14003EFDA
0x14003ee87  call    cs:__imp_GetLastError
0x14003ee8e  nop     dword ptr [rax+rax+00h]
0x14003ee93  mov     r9, [rbx+448h]
0x14003ee9a  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003eea1  mov     rcx, cs:WPP_GLOBAL_Control
0x14003eea8  mov     edx, 57h ; 'W'
0x14003eead  mov     [rsp+2A8h+var_288], eax
0x14003eeb1  mov     r9d, [r9+rsi+58h]
0x14003eeb6  mov     rcx, [rcx+10h]
0x14003eeba  call    WPP_SF_dd
0x14003eebf  jmp     loc_14003EFDA
0x14003eec4  mov     rax, cs:WPP_GLOBAL_Control
0x14003eecb  lea     rcx, WPP_GLOBAL_Control
0x14003eed2  cmp     rax, rcx
0x14003eed5  jz      short loc_14003EF0E
0x14003eed7  test    byte ptr [rax+1Ch], 4
0x14003eedb  jz      short loc_14003EF0E
0x14003eedd  cmp     byte ptr [rax+19h], 2
0x14003eee1  jb      short loc_14003EF0E
0x14003eee3  call    cs:__imp_GetLastError
0x14003eeea  nop     dword ptr [rax+rax+00h]
0x14003eeef  mov     rcx, cs:WPP_GLOBAL_Control
0x14003eef6  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003eefd  mov     edx, 5Ah ; 'Z'
0x14003ef02  mov     r9d, eax
0x14003ef05  mov     rcx, [rcx+10h]
0x14003ef09  call    WPP_SF_d
0x14003ef0e  mov     rcx, rsi; lpMem
0x14003ef11  call    pMemFree
0x14003ef16  jmp     loc_14003EFDA
0x14003ef1b  mov     rax, cs:WPP_GLOBAL_Control
0x14003ef22  lea     rcx, WPP_GLOBAL_Control
0x14003ef29  cmp     rax, rcx
0x14003ef2c  jz      loc_14003EFDA
0x14003ef32  test    byte ptr [rax+1Ch], 4
0x14003ef36  jz      loc_14003EFDA
0x14003ef3c  cmp     byte ptr [rax+19h], 2
0x14003ef40  jb      loc_14003EFDA
0x14003ef46  call    cs:__imp_GetLastError
0x14003ef4d  nop     dword ptr [rax+rax+00h]
0x14003ef52  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ef59  mov     edx, 5Bh ; '['
0x14003ef5e  mov     [rsp+2A8h+var_280], eax
0x14003ef62  mov     r9, r14
0x14003ef65  mov     [rsp+2A8h+var_288], 28h ; '('
0x14003ef6d  mov     rcx, [rcx+10h]
0x14003ef71  call    WPP_SF_Sll
0x14003ef76  jmp     short loc_14003EFDA
0x14003ef78  mov     rax, cs:WPP_GLOBAL_Control
0x14003ef7f  cmp     rax, r14
  ... truncated ...
```
