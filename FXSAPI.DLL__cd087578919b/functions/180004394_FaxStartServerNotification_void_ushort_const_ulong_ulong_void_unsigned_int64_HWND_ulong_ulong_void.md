# FaxStartServerNotification(void *,ushort const *,ulong,ulong,void *,unsigned __int64,HWND__ *,ulong,ulong,void * *)

- ea: `0x180004394`
- end: `0x180004c35`
- name: `?FaxStartServerNotification@@YAHPEAXPEBGKK0_KPEAUHWND__@@KKPEAPEAX@Z`
- size: `2209`
- prototype: `__int64 __fastcall(_DWORD *, const unsigned __int16 *, int, unsigned int, void *, unsigned __int64, HWND, unsigned int, unsigned int, void **)`
- caller_count: `3`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18000a710`
- `0x18000a770`
- `0x18000a7d0`

## callees

- `0x180004394`
- `0x180004c3c`
- `0x18000abe4`
- `0x18000ac14`
- `0x18000ac58`
- `0x180027248`
- `0x180027740`
- `0x18002bab8`
- `0x18002bb58`
- `0x18002c1e0`
- `0x18003d510`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180004a03`
- `RPCRT4!NdrClientCall3` at `0x180004a9b`
- `RPCRT4!NdrClientCall3` at `0x180004a03`
- `RPCRT4!NdrClientCall3` at `0x180004a9b`
- `KERNEL32!GetComputerNameW` at `0x18000459d`
- `KERNEL32!GetComputerNameW` at `0x18000459d`
- `KERNEL32!EnterCriticalSection` at `0x1800047cb`
- `KERNEL32!EnterCriticalSection` at `0x180004b7a`
- `KERNEL32!EnterCriticalSection` at `0x1800047cb`
- `KERNEL32!EnterCriticalSection` at `0x180004b7a`
- `KERNEL32!SetLastError` at `0x1800044a5`
- `KERNEL32!SetLastError` at `0x18000451b`
- `KERNEL32!SetLastError` at `0x180004540`
- `KERNEL32!SetLastError` at `0x180004688`
- `KERNEL32!SetLastError` at `0x180004bdb`
- `KERNEL32!SetLastError` at `0x1800044a5`
- `KERNEL32!SetLastError` at `0x18000451b`
- `KERNEL32!SetLastError` at `0x180004540`
- `KERNEL32!SetLastError` at `0x180004688`
- `KERNEL32!SetLastError` at `0x180004bdb`
- `KERNEL32!GetLastError` at `0x1800045d0`
- `KERNEL32!GetLastError` at `0x1800045d0`
- `KERNEL32!LeaveCriticalSection` at `0x180004805`
- `KERNEL32!LeaveCriticalSection` at `0x180004b95`
- `KERNEL32!LeaveCriticalSection` at `0x180004805`
- `KERNEL32!LeaveCriticalSection` at `0x180004b95`

## pseudocode

```c
__int64 __fastcall FaxStartServerNotification(
        _DWORD *a1,
        const unsigned __int16 *a2,
        int a3,
        unsigned int a4,
        void *a5,
        unsigned __int64 a6,
        HWND a7,
        unsigned int a8,
        unsigned int a9,
        void **a10)
{
  _QWORD *v12; // rcx
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  DWORD v15; // ecx
  DWORD LastError; // eax
  __int64 v17; // r13
  __int64 v18; // rax
  __int64 v19; // rax
  const wchar_t *v20; // r8
  __int64 v21; // rcx
  wchar_t *v22; // rdx
  wchar_t v23; // r9
  unsigned int v24; // ebx
  wchar_t *v25; // rax
  _QWORD *v26; // rcx
  __int64 v27; // rdx
  _DWORD *v28; // rbx
  int v29; // eax
  struct _LIST_ENTRY *v30; // rax
  struct _LIST_ENTRY *v31; // rcx
  int v32; // eax
  unsigned int started; // eax
  _QWORD *v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // r9
  unsigned __int16 near **v37; // rax
  __int64 v38; // rcx
  _WORD *v39; // rdx
  __int64 v40; // r9
  __int16 v41; // r8
  _WORD *v42; // rax
  const unsigned __int16 *v43; // rcx
  _QWORD *v44; // rax
  CLIENT_CALL_RETURN v45; // rax
  const unsigned __int16 *v46; // rcx
  _QWORD *v47; // rax
  struct _LIST_ENTRY *v48; // rcx
  int v50; // [rsp+60h] [rbp-D8h]
  int v51; // [rsp+68h] [rbp-D0h]
  DWORD nSize; // [rsp+6Ch] [rbp-CCh] BYREF
  int v53; // [rsp+70h] [rbp-C8h]
  int v54; // [rsp+74h] [rbp-C4h]
  BOOL v55; // [rsp+78h] [rbp-C0h]
  _DWORD *Simple; // [rsp+80h] [rbp-B8h]
  struct _LIST_ENTRY *v57; // [rsp+88h] [rbp-B0h]
  void *v58; // [rsp+90h] [rbp-A8h] BYREF
  const unsigned __int16 *Pointer; // [rsp+98h] [rbp-A0h]
  void **v60; // [rsp+A0h] [rbp-98h]
  __int64 v61; // [rsp+A8h] [rbp-90h]
  void **v62; // [rsp+B0h] [rbp-88h]
  _BYTE v63[24]; // [rsp+B8h] [rbp-80h] BYREF
  WCHAR Buffer[16]; // [rsp+D0h] [rbp-68h] BYREF

  v53 = a4;
  v54 = a3;
  Pointer = a2;
  Simple = a1;
  v60 = a10;
  v62 = a10;
  nSize = 0;
  v58 = 0;
  v55 = a9 > 0x10000;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_152912f6797533292abcfca723f93957_Traceguids);
    v12 = WPP_GLOBAL_Control;
  }
  if ( !a1 || !*a1 || a1[4] )
  {
    SetLastError(6u);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v14 = 14;
LABEL_114:
    WPP_SF_(v13[2], v14, &WPP_152912f6797533292abcfca723f93957_Traceguids);
    return 0;
  }
  if ( a5 )
  {
    if ( !a7 )
      goto LABEL_23;
    goto LABEL_12;
  }
  if ( !a7 )
  {
LABEL_12:
    SetLastError(0x57u);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v14 = 15;
    goto LABEL_114;
  }
  if ( a8 < 0x400 )
  {
    if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 7) & 0x1000) != 0 && *((_BYTE *)v12 + 25) >= 2u )
      WPP_SF_(v12[2], 17, &WPP_152912f6797533292abcfca723f93957_Traceguids);
    v15 = 87;
    goto LABEL_22;
  }
LABEL_23:
  if ( a9 == 196608 && a4 != 1 )
  {
    SetLastError(0x57u);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_152912f6797533292abcfca723f93957_Traceguids, a4);
    }
    return 0;
  }
  nSize = 16;
  if ( !GetComputerNameW(Buffer, &nSize) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_152912f6797533292abcfca723f93957_Traceguids, LastError);
    }
    return 0;
  }
  v17 = pMemAlloc(0x58u);
  v61 = v17;
  if ( !v17 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_152912f6797533292abcfca723f93957_Traceguids);
    }
    v15 = 8;
LABEL_22:
    SetLastError(v15);
    return 0;
  }
  v18 = pMemAlloc(0x18u);
  v57 = (struct _LIST_ENTRY *)v18;
  if ( !v18 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_152912f6797533292abcfca723f93957_Traceguids);
    }
    SetLastError(8u);
    pMemFree((LPVOID)v17);
    return 0;
  }
  v51 = 0;
  *(_QWORD *)(v18 + 16) = v17;
  v19 = 2147483646;
  v20 = L"KukiMuki";
  v21 = 10;
  v22 = (wchar_t *)v17;
  do
  {
    if ( !v19 )
      break;
    v23 = *v20;
    if ( !*v20 )
      break;
    ++v20;
    *v22++ = v23;
    --v19;
    --v21;
  }
  while ( v21 );
  v24 = v21 == 0 ? 0x8007007A : 0;
  v25 = v22 - 1;
  if ( v21 )
    v25 = v22;
  *v25 = 0;
  if ( !v21 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v27 = 22;
LABEL_57:
      WPP_SF_d(v26[2], v27, &WPP_152912f6797533292abcfca723f93957_Traceguids, v24);
      goto LABEL_58;
    }
    goto LABEL_58;
  }
  *(_DWORD *)(v17 + 52) = v55;
  *(_QWORD *)(v17 + 24) = 0;
  *(_QWORD *)(v17 + 40) = 0;
  *(_QWORD *)(v17 + 64) = 0;
  v28 = Simple;
  *(_DWORD *)(v17 + 56) = *(_DWORD *)(*((_QWORD *)Simple + 4) + 88LL);
  *(_DWORD *)(v17 + 72) = 0;
  *(_DWORD *)(v17 + 76) = *(_DWORD *)(*((_QWORD *)v28 + 4) + 80LL);
  v29 = v53;
  if ( a9 != 196608 )
    v29 = 0;
  *(_DWORD *)(v17 + 80) = v29;
  if ( a5 )
  {
    *(_QWORD *)(v17 + 24) = a5;
    *(_QWORD *)(v17 + 32) = a6;
  }
  else
  {
    *(_QWORD *)(v17 + 40) = a7;
    *(_DWORD *)(v17 + 48) = a8;
  }
  EnterCriticalSection(&g_CsFaxAssyncInfo);
  v30 = off_18004E008;
  v31 = v57;
  v57->Flink = &g_contextListHead;
  v31->Blink = v30;
  v30->Flink = v31;
  off_18004E008 = v31;
  LeaveCriticalSection(&g_CsFaxAssyncInfo);
  if ( a8 == 1324 && (unsigned int)IsLocalMachineNameW(*(wchar_t **)(*((_QWORD *)v28 + 4) + 72LL)) )
  {
    v32 = 1;
    *(_DWORD *)(v17 + 56) = 0;
  }
  else
  {
    v32 = 0;
  }
  v50 = v32;
  started = StartFaxClientRpcServer(v32);
  v24 = started;
  if ( started )
  {
    v34 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_104;
    }
    v35 = 23;
    v36 = started;
LABEL_103:
    WPP_SF_d(v34[2], v35, &WPP_152912f6797533292abcfca723f93957_Traceguids, v36);
LABEL_104:
    EnterCriticalSection(&g_CsFaxAssyncInfo);
    FindAndRemoveContext(v48, (struct _ASYNC_EVENT_INFO *)v17);
    LeaveCriticalSection(&g_CsFaxAssyncInfo);
    pMemFree((LPVOID)v17);
    if ( v51 )
      StopFaxClientRpcServer();
    v15 = v24;
    goto LABEL_22;
  }
  v51 = 1;
  LODWORD(v57) = 1;
  v37 = &g_tszEndPoint;
  v38 = 11;
  v39 = v63;
  v40 = 2147483646;
  do
  {
    if ( !v40 )
      break;
    v41 = *(_WORD *)v37;
    if ( !*(_WORD *)v37 )
      break;
    v37 = (unsigned __int16 near **)((char *)v37 + 2);
    *v39++ = v41;
    --v40;
    --v38;
  }
  while ( v38 );
  v24 = v38 == 0 ? 0x8007007A : 0;
  v42 = v39 - 1;
  if ( v38 )
    v42 = v39;
  *v42 = 0;
  if ( !v38 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v27 = 24;
      goto LABEL_57;
    }
LABEL_58:
    if ( (v24 & 0x1FFF0000) == 0x70000 )
      v24 = (unsigned __int16)v24;
    goto LABEL_104;
  }
  if ( ((a9 - 0x10000) & 0xFFFEFFFF) == 0 )
  {
    v46 = L"ncalrpc";
    if ( !v50 )
      v46 = L"ncacn_ip_tcp";
    v47 = (_QWORD *)*((_QWORD *)Simple + 4);
    Pointer = 0;
    Pointer = (const unsigned __int16 *)NdrClientCall3(
                                          (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                                          0x4Au,
                                          0,
                                          *v47,
                                          Buffer,
                                          v63,
                                          v17,
                                          v46,
                                          v55,
                                          v54,
                                          &v58).Pointer;
    v24 = (unsigned int)Pointer;
    goto LABEL_97;
  }
  if ( a9 == 196608 )
  {
    v43 = L"ncalrpc";
    if ( !v50 )
      v43 = L"ncacn_ip_tcp";
    v44 = (_QWORD *)*((_QWORD *)Simple + 4);
    Simple = 0;
    v45.Pointer = NdrClientCall3(
                    (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                    0x5Cu,
                    0,
                    *v44,
                    Pointer,
                    Buffer,
                    v63,
                    v17,
                    v43,
                    v54,
                    v53,
                    &v58).Pointer;
    v24 = (unsigned int)v45.Pointer;
    Simple = (_DWORD *)v45.Simple;
    goto LABEL_97;
  }
  v24 = 1359;
  v34 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_152912f6797533292abcfca723f93957_Traceguids, a9);
LABEL_97:
    v34 = WPP_GLOBAL_Control;
  }
  if ( v24 )
  {
    if ( v34 == &WPP_GLOBAL_Control || (*((_DWORD *)v34 + 7) & 0x1000) == 0 || *((_BYTE *)v34 + 25) < 2u )
      goto LABEL_104;
    v35 = 27;
    v36 = v24;
    goto LABEL_103;
  }
  if ( a9 > 0x10000 )
    *v60 = v58;
  return 1;
}

```

## disassembly

```asm
0x180004394  push    rbx
0x180004396  push    rsi
0x180004397  push    rdi
0x180004398  push    r12
0x18000439a  push    r13
0x18000439c  push    r14
0x18000439e  push    r15
0x1800043a0  sub     rsp, 100h
0x1800043a7  mov     rax, cs:__security_cookie
0x1800043ae  xor     rax, rsp
0x1800043b1  mov     [rsp+138h+var_48], rax
0x1800043b9  mov     r13d, r9d
0x1800043bc  mov     [rsp+138h+var_C8], r9d
0x1800043c1  mov     [rsp+138h+var_C4], r8d
0x1800043c6  mov     [rsp+138h+var_A0], rdx
0x1800043ce  mov     rbx, rcx
0x1800043d1  mov     [rsp+138h+var_B8], rcx
0x1800043d9  mov     rax, [rsp+138h+arg_48]
0x1800043e1  mov     [rsp+138h+var_98], rax
0x1800043e9  mov     [rsp+138h+var_88], rax
0x1800043f1  xor     edi, edi
0x1800043f3  mov     [rsp+138h+nSize], edi
0x1800043f7  mov     [rsp+138h+var_A8], rdi
0x1800043ff  mov     eax, edi
0x180004401  mov     r12d, [rsp+138h+arg_40]
0x180004409  cmp     r12d, 10000h
0x180004410  setnbe  al
0x180004413  mov     [rsp+138h+var_C0], eax
0x180004417  lea     r15, WPP_GLOBAL_Control
0x18000441e  mov     rcx, cs:WPP_GLOBAL_Control
0x180004425  mov     esi, 1000h
0x18000442a  cmp     rcx, r15
0x18000442d  jz      short loc_180004459
0x18000442f  test    [rcx+1Ch], esi
0x180004432  jz      short loc_180004459
0x180004434  cmp     byte ptr [rcx+19h], 5
0x180004438  jb      short loc_180004459
0x18000443a  lea     edx, [rdi+0Dh]
0x18000443d  lea     r14, WPP_152912f6797533292abcfca723f93957_Traceguids
0x180004444  mov     r8, r14
0x180004447  mov     rcx, [rcx+10h]
0x18000444b  call    WPP_SF_
0x180004450  mov     rcx, cs:WPP_GLOBAL_Control
0x180004457  jmp     short loc_180004460
0x180004459  lea     r14, WPP_152912f6797533292abcfca723f93957_Traceguids
0x180004460  test    rbx, rbx
0x180004463  jz      loc_180004BD6
0x180004469  cmp     [rbx], edi
0x18000446b  jz      loc_180004BD6
0x180004471  cmp     [rbx+10h], edi
0x180004474  jnz     loc_180004BD6
0x18000447a  mov     rax, [rsp+138h+arg_20]
0x180004482  test    rax, rax
0x180004485  jz      short loc_180004496
0x180004487  cmp     [rsp+138h+arg_30], rdi
0x18000448f  jnz     short loc_1800044A0
0x180004491  test    rax, rax
0x180004494  jnz     short loc_1800044DE
0x180004496  cmp     [rsp+138h+arg_30], rdi
0x18000449e  jnz     short loc_1800044E8
0x1800044a0  mov     ecx, 57h ; 'W'; dwErrCode
0x1800044a5  call    cs:__imp_SetLastError
0x1800044ac  nop     dword ptr [rax+rax+00h]
0x1800044b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800044b8  cmp     rcx, r15
0x1800044bb  jz      loc_180004C0F
0x1800044c1  test    [rcx+1Ch], esi
0x1800044c4  jz      loc_180004C0F
0x1800044ca  cmp     byte ptr [rcx+19h], 2
0x1800044ce  jb      loc_180004C0F
0x1800044d4  mov     edx, 0Fh
0x1800044d9  jmp     loc_180004C03
0x1800044de  cmp     [rsp+138h+arg_30], rdi
0x1800044e6  jz      short loc_18000452C
0x1800044e8  cmp     [rsp+138h+arg_38], 400h
0x1800044f3  jnb     short loc_18000452C
0x1800044f5  cmp     rcx, r15
0x1800044f8  jz      short loc_180004516
0x1800044fa  test    [rcx+1Ch], esi
0x1800044fd  jz      short loc_180004516
0x1800044ff  cmp     byte ptr [rcx+19h], 2
0x180004503  jb      short loc_180004516
0x180004505  mov     edx, 11h
0x18000450a  mov     r8, r14
0x18000450d  mov     rcx, [rcx+10h]
0x180004511  call    WPP_SF_
0x180004516  mov     ecx, 57h ; 'W'; dwErrCode
0x18000451b  call    cs:__imp_SetLastError
0x180004522  nop     dword ptr [rax+rax+00h]
0x180004527  jmp     loc_180004C0F
0x18000452c  cmp     r12d, 30000h
0x180004533  jnz     short loc_180004588
0x180004535  cmp     r13d, 1
0x180004539  jz      short loc_180004588
0x18000453b  mov     ecx, 57h ; 'W'; dwErrCode
0x180004540  call    cs:__imp_SetLastError
0x180004547  nop     dword ptr [rax+rax+00h]
0x18000454c  mov     rcx, cs:WPP_GLOBAL_Control
0x180004553  cmp     rcx, r15
0x180004556  jz      loc_180004C0F
0x18000455c  test    [rcx+1Ch], esi
0x18000455f  jz      loc_180004C0F
0x180004565  cmp     byte ptr [rcx+19h], 2
0x180004569  jb      loc_180004C0F
0x18000456f  mov     edx, 12h
0x180004574  mov     r9d, r13d
0x180004577  mov     r8, r14
0x18000457a  mov     rcx, [rcx+10h]
0x18000457e  call    WPP_SF_d
0x180004583  jmp     loc_180004C0F
0x180004588  mov     [rsp+138h+nSize], 10h
0x180004590  lea     rdx, [rsp+138h+nSize]; nSize
0x180004595  lea     rcx, [rsp+138h+Buffer]; lpBuffer
0x18000459d  call    cs:__imp_GetComputerNameW
0x1800045a4  nop     dword ptr [rax+rax+00h]
0x1800045a9  test    eax, eax
0x1800045ab  jnz     short loc_1800045FC
0x1800045ad  mov     rax, cs:WPP_GLOBAL_Control
0x1800045b4  cmp     rax, r15
0x1800045b7  jz      loc_180004C0F
0x1800045bd  test    [rax+1Ch], esi
0x1800045c0  jz      loc_180004C0F
0x1800045c6  cmp     byte ptr [rax+19h], 2
0x1800045ca  jb      loc_180004C0F
0x1800045d0  call    cs:__imp_GetLastError
0x1800045d7  nop     dword ptr [rax+rax+00h]
0x1800045dc  mov     edx, 13h
0x1800045e1  mov     r9d, eax
0x1800045e4  mov     r8, r14
0x1800045e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800045ee  mov     rcx, [rcx+10h]
0x1800045f2  call    WPP_SF_d
0x1800045f7  jmp     loc_180004C0F
0x1800045fc  mov     ecx, 58h ; 'X'; dwBytes
0x180004601  call    pMemAlloc
0x180004606  mov     r13, rax
0x180004609  mov     [rsp+138h+var_90], rax
0x180004611  test    rax, rax
0x180004614  jnz     short loc_180004646
0x180004616  mov     rcx, cs:WPP_GLOBAL_Control
0x18000461d  cmp     rcx, r15
0x180004620  jz      short loc_18000463C
0x180004622  test    [rcx+1Ch], esi
0x180004625  jz      short loc_18000463C
0x180004627  cmp     byte ptr [rcx+19h], 2
0x18000462b  jb      short loc_18000463C
0x18000462d  lea     edx, [rax+14h]
0x180004630  mov     r8, r14
0x180004633  mov     rcx, [rcx+10h]
0x180004637  call    WPP_SF_
0x18000463c  mov     ecx, 8
0x180004641  jmp     loc_18000451B
0x180004646  mov     ecx, 18h; dwBytes
0x18000464b  call    pMemAlloc
0x180004650  mov     [rsp+138h+var_B0], rax
0x180004658  test    rax, rax
0x18000465b  jnz     short loc_1800046A1
0x18000465d  mov     rcx, cs:WPP_GLOBAL_Control
0x180004664  cmp     rcx, r15
0x180004667  jz      short loc_180004683
0x180004669  test    [rcx+1Ch], esi
0x18000466c  jz      short loc_180004683
0x18000466e  cmp     byte ptr [rcx+19h], 2
0x180004672  jb      short loc_180004683
0x180004674  lea     edx, [rax+15h]
0x180004677  mov     r8, r14
0x18000467a  mov     rcx, [rcx+10h]
0x18000467e  call    WPP_SF_
0x180004683  mov     ecx, 8; dwErrCode
0x180004688  call    cs:__imp_SetLastError
0x18000468f  nop     dword ptr [rax+rax+00h]
0x180004694  mov     rcx, r13; lpMem
0x180004697  call    pMemFree
0x18000469c  jmp     loc_180004C0F
0x1800046a1  mov     [rsp+138h+var_D0], edi
0x1800046a5  mov     [rax+10h], r13
0x1800046a9  mov     eax, 7FFFFFFEh
0x1800046ae  lea     r8, aKukimuki; "KukiMuki"
0x1800046b5  mov     ecx, 0Ah
0x1800046ba  mov     rdx, r13
0x1800046bd  test    rax, rax
0x1800046c0  jz      short loc_1800046E1
0x1800046c2  movzx   r9d, word ptr [r8]
0x1800046c6  test    r9w, r9w
0x1800046ca  jz      short loc_1800046E1
0x1800046cc  add     r8, 2
0x1800046d0  mov     [rdx], r9w
0x1800046d4  add     rdx, 2
0x1800046d8  dec     rax
0x1800046db  sub     rcx, 1
0x1800046df  jnz     short loc_1800046BD
0x1800046e1  mov     rax, rcx
0x1800046e4  neg     rax
0x1800046e7  sbb     ebx, ebx
0x1800046e9  not     ebx
0x1800046eb  and     ebx, 8007007Ah
0x1800046f1  lea     rax, [rdx-2]
0x1800046f5  test    rcx, rcx
0x1800046f8  cmovnz  rax, rdx
0x1800046fc  mov     [rax], di
0x1800046ff  jnz     short loc_180004746
0x180004701  mov     rcx, cs:WPP_GLOBAL_Control
0x180004708  cmp     rcx, r15
0x18000470b  jz      short loc_18000472C
0x18000470d  test    [rcx+1Ch], esi
0x180004710  jz      short loc_18000472C
0x180004712  cmp     byte ptr [rcx+19h], 2
0x180004716  jb      short loc_18000472C
0x180004718  mov     edx, 16h
0x18000471d  mov     r9d, ebx
0x180004720  mov     r8, r14
0x180004723  mov     rcx, [rcx+10h]
0x180004727  call    WPP_SF_d
0x18000472c  mov     eax, ebx
0x18000472e  and     eax, 1FFF0000h
0x180004733  cmp     eax, 70000h
0x180004738  jnz     loc_180004B73
0x18000473e  movzx   ebx, bx
0x180004741  jmp     loc_180004B73
0x180004746  mov     eax, [rsp+138h+var_C0]
0x18000474a  mov     [r13+34h], eax
0x18000474e  mov     [r13+18h], rdi
0x180004752  mov     [r13+28h], rdi
0x180004756  mov     [r13+40h], rdi
0x18000475a  mov     rbx, [rsp+138h+var_B8]
0x180004762  mov     rax, [rbx+20h]
0x180004766  mov     ecx, [rax+58h]
0x180004769  mov     [r13+38h], ecx
0x18000476d  mov     [r13+48h], edi
0x180004771  mov     rax, [rbx+20h]
0x180004775  mov     ecx, [rax+50h]
0x180004778  mov     [r13+4Ch], ecx
0x18000477c  mov     eax, [rsp+138h+var_C8]
0x180004780  cmp     r12d, 30000h
0x180004787  cmovnz  eax, edi
0x18000478a  mov     [r13+50h], eax
0x18000478e  mov     rax, [rsp+138h+arg_20]
0x180004796  test    rax, rax
0x180004799  jz      short loc_1800047AD
0x18000479b  mov     [r13+18h], rax
0x18000479f  mov     rax, [rsp+138h+arg_28]
0x1800047a7  mov     [r13+20h], rax
0x1800047ab  jmp     short loc_1800047C4
0x1800047ad  mov     rax, [rsp+138h+arg_30]
0x1800047b5  mov     [r13+28h], rax
0x1800047b9  mov     eax, [rsp+138h+arg_38]
0x1800047c0  mov     [r13+30h], eax
0x1800047c4  lea     rcx, ?g_CsFaxAssyncInfo@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800047cb  call    cs:__imp_EnterCriticalSection
0x1800047d2  nop     dword ptr [rax+rax+00h]
0x1800047d7  mov     rax, cs:off_18004E008
0x1800047de  lea     rdx, ?g_contextListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_contextListHead
0x1800047e5  mov     rcx, [rsp+138h+var_B0]
0x1800047ed  mov     [rcx], rdx
0x1800047f0  mov     [rcx+8], rax
0x1800047f4  mov     [rax], rcx
0x1800047f7  mov     cs:off_18004E008, rcx
0x1800047fe  lea     rcx, ?g_CsFaxAssyncInfo@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180004805  call    cs:__imp_LeaveCriticalSection
0x18000480c  nop     dword ptr [rax+rax+00h]
0x180004811  cmp     [rsp+138h+arg_38], 52Ch
0x18000481c  jnz     short loc_18000483A
0x18000481e  mov     rcx, [rbx+20h]
0x180004822  mov     rcx, [rcx+48h]; String2
0x180004826  call    IsLocalMachineNameW
0x18000482b  test    eax, eax
0x18000482d  jz      short loc_18000483A
0x18000482f  mov     eax, 1
0x180004834  mov     [r13+38h], edi
0x180004838  jmp     short loc_18000483C
0x18000483a  mov     eax, edi
0x18000483c  mov     [rsp+138h+var_D8], eax
0x180004840  mov     ecx, eax; int
0x180004842  call    ?StartFaxClientRpcServer@@YAKH@Z; StartFaxClientRpcServer(int)
0x180004847  mov     ebx, eax
0x180004849  test    eax, eax
0x18000484b  jz      short loc_18000487D
0x18000484d  mov     rcx, cs:WPP_GLOBAL_Control
0x180004854  cmp     rcx, r15
0x180004857  jz      loc_180004B73
0x18000485d  test    [rcx+1Ch], esi
0x180004860  jz      loc_180004B73
0x180004866  cmp     byte ptr [rcx+19h], 2
0x18000486a  jb      loc_180004B73
0x180004870  mov     edx, 17h
0x180004875  mov     r9d, eax
0x180004878  jmp     loc_180004B67
0x18000487d  mov     r10d, 1
0x180004883  mov     [rsp+138h+var_D0], r10d
0x180004888  mov     dword ptr [rsp+138h+var_B0], r10d
0x180004890  lea     rax, ?g_tszEndPoint@@3PAGA; ushort near * g_tszEndPoint
0x180004897  lea     ecx, [r10+0Ah]
0x18000489b  lea     rdx, [rsp+138h+var_80]
0x1800048a3  mov     r9d, 7FFFFFFEh
0x1800048a9  test    r9, r9
0x1800048ac  jz      short loc_1800048CC
0x1800048ae  movzx   r8d, word ptr [rax]
0x1800048b2  test    r8w, r8w
0x1800048b6  jz      short loc_1800048CC
0x1800048b8  add     rax, 2
  ... truncated ...
```
