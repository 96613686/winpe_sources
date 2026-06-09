# UpdateJobStatus(_JOB_ENTRY *,_FSPI_JOB_STATUS const *)

- ea: `0x140036268`
- end: `0x14003673b`
- name: `?UpdateJobStatus@@YAHPEAU_JOB_ENTRY@@PEBU_FSPI_JOB_STATUS@@@Z`
- size: `1235`
- prototype: `int(struct _JOB_ENTRY *, const struct _FSPI_JOB_STATUS *)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x1400311d0`
- `0x1400411a0`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140004fe4`
- `0x1400154a0`
- `0x140023a0c`
- `0x140036268`
- `0x140036b8c`
- `0x140036bf4`
- `0x140037224`
- `0x140053938`
- `0x140058d78`
- `0x14005900c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140036407`
- `KERNEL32!GetLastError` at `0x1400364d2`
- `KERNEL32!GetLastError` at `0x14003652e`
- `KERNEL32!GetLastError` at `0x14003658a`
- `KERNEL32!GetLastError` at `0x140036627`
- `KERNEL32!GetLastError` at `0x140036407`
- `KERNEL32!GetLastError` at `0x1400364d2`
- `KERNEL32!GetLastError` at `0x14003652e`
- `KERNEL32!GetLastError` at `0x14003658a`
- `KERNEL32!GetLastError` at `0x140036627`
- `KERNEL32!SetLastError` at `0x14003671d`
- `KERNEL32!SetLastError` at `0x14003671d`
- `KERNEL32!EnterCriticalSection` at `0x1400362b6`
- `KERNEL32!EnterCriticalSection` at `0x140036695`
- `KERNEL32!EnterCriticalSection` at `0x1400362b6`
- `KERNEL32!EnterCriticalSection` at `0x140036695`
- `KERNEL32!LeaveCriticalSection` at `0x14003633a`
- `KERNEL32!LeaveCriticalSection` at `0x1400366f8`
- `KERNEL32!LeaveCriticalSection` at `0x14003670b`
- `KERNEL32!LeaveCriticalSection` at `0x14003633a`
- `KERNEL32!LeaveCriticalSection` at `0x1400366f8`
- `KERNEL32!LeaveCriticalSection` at `0x14003670b`
- `msvcrt!_wcsicmp` at `0x1400365e3`
- `msvcrt!_wcsicmp` at `0x1400365e3`
- `USER32!LoadStringW` at `0x140036617`
- `USER32!LoadStringW` at `0x140036617`

## pseudocode

```c
_BOOL8 __fastcall UpdateJobStatus(struct _JOB_ENTRY *a1, const struct _FSPI_JOB_STATUS *a2)
{
  CMapDeviceId *v4; // rcx
  DWORD v6; // eax
  __int64 v7; // r8
  DWORD v8; // esi
  __int64 v9; // r9
  DWORD LastError; // eax
  __int64 v11; // r8
  _DWORD *v12; // rsi
  int v13; // eax
  __int128 v14; // xmm0
  __int128 v15; // xmm0
  const unsigned __int16 *v16; // rdx
  DWORD v17; // eax
  const unsigned __int16 *v18; // rdx
  DWORD v19; // eax
  const unsigned __int16 *v20; // rdx
  DWORD v21; // eax
  HINSTANCE v22; // rcx
  DWORD v23; // eax
  int v24; // r8d
  DWORD v25; // edi
  int QueueEvent; // eax
  int v27; // [rsp+20h] [rbp-48h]

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 231, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
  }
  EnterCriticalSection(&g_CsJob);
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v27 = *((_DWORD *)a2 + 3);
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 232, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( *((_DWORD *)a1 + 434) == 1 )
  {
    if ( v4 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 4) != 0 && *((_BYTE *)v4 + 25) >= 3u )
      WPP_SF_d(
        *((_QWORD *)v4 + 2),
        233,
        &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
        *(unsigned int *)(*((_QWORD *)a1 + 138) + 32LL));
    LeaveCriticalSection(&g_CsJob);
    return 1;
  }
  else
  {
    v6 = MapFSPIJobStatusToEventId(a2);
    v7 = *((_QWORD *)a1 + 138);
    v8 = v6;
    if ( *(_DWORD *)(v7 + 36) == 2 )
      v9 = *(_QWORD *)(v7 + 584);
    else
      v9 = *((_QWORD *)a1 + 138);
    if ( !(unsigned int)CreateFaxEvent(
                          *(_DWORD *)(*((_QWORD *)a1 + 2) + 24LL),
                          v6,
                          *(_DWORD *)(v7 + 32),
                          *(void **)(v9 + 408)) )
    {
      if ( g_bServiceIsDown == 1 )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_Dll(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            234,
            *((_QWORD *)a1 + 138),
            v8,
            *(_DWORD *)(*((_QWORD *)a1 + 138) + 32LL),
            *(_DWORD *)(*((_QWORD *)a1 + 2) + 24LL));
        }
      }
      else if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_Dlll(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          *((_QWORD *)a1 + 138),
          v11,
          v8,
          *(_DWORD *)(*((_QWORD *)a1 + 138) + 32LL),
          *(_DWORD *)(*((_QWORD *)a1 + 2) + 24LL),
          LastError);
      }
    }
    v12 = (_DWORD *)((char *)a1 + 1124);
    *((_DWORD *)a1 + 282) = *((_DWORD *)a2 + 2);
    *((_DWORD *)a1 + 283) = *((_DWORD *)a2 + 3);
    *((_DWORD *)a1 + 284) = *((_DWORD *)a2 + 4);
    if ( (*((_BYTE *)a2 + 4) & 1) != 0 )
    {
      v13 = *((_DWORD *)a2 + 12);
      *v12 |= 1u;
      *((_DWORD *)a1 + 292) = v13;
    }
    if ( (*((_BYTE *)a2 + 4) & 2) != 0 )
    {
      v14 = *(_OWORD *)((char *)a2 + 52);
      *v12 |= 2u;
      *(_OWORD *)((char *)a1 + 1172) = v14;
    }
    if ( (*((_BYTE *)a2 + 4) & 4) != 0 )
    {
      v15 = *(_OWORD *)((char *)a2 + 68);
      *v12 |= 4u;
      *(_OWORD *)((char *)a1 + 1188) = v15;
    }
    v16 = (const unsigned __int16 *)*((_QWORD *)a2 + 3);
    if ( v16
      && !ReplaceStringWithCopy((unsigned __int16 **)a1 + 143, v16)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v17 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 236, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, v17);
    }
    v18 = (const unsigned __int16 *)*((_QWORD *)a2 + 4);
    if ( v18
      && !ReplaceStringWithCopy((unsigned __int16 **)a1 + 144, v18)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v19 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 237, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, v19);
    }
    v20 = (const unsigned __int16 *)*((_QWORD *)a2 + 5);
    if ( v20
      && !ReplaceStringWithCopy((unsigned __int16 **)a1 + 145, v20)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v21 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 238, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, v21);
    }
    *((_WORD *)a1 + 608) = 0;
    if ( !*((_DWORD *)a1 + 284)
      || (_wcsicmp(
            (const wchar_t *)(*(_QWORD *)(*((_QWORD *)a1 + 2) + 40LL) + 1624LL),
            L"{2172FD8F-11F6-11d3-90BF-006094EB630B}")
        ? (v22 = *(HINSTANCE *)(*(_QWORD *)(*((_QWORD *)a1 + 2) + 40LL) + 56LL))
        : (v22 = (HINSTANCE)g_hResource),
          LoadStringW(v22, *((_DWORD *)a1 + 284), (LPWSTR)a1 + 608, 256)) )
    {
      v25 = 0;
      EnterCriticalSection(&g_CsQueue);
      QueueEvent = CreateQueueEvent(2u, *((_QWORD *)a1 + 138));
      if ( QueueEvent
        && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LOWORD(v27) = QueueEvent;
        WPP_SF_lh(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          240,
          &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
          *(unsigned int *)(*((_QWORD *)a1 + 138) + 16LL),
          v27);
      }
      LeaveCriticalSection(&g_CsQueue);
    }
    else
    {
      v23 = GetLastError();
      v25 = v23;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_llS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          239,
          v24,
          v23,
          *((_DWORD *)a1 + 284),
          *(_QWORD *)(*((_QWORD *)a1 + 2) + 40LL) + 584LL);
      }
      *v12 &= ~0x10000000u;
      *(_QWORD *)((char *)a1 + 1132) = 0;
    }
    LeaveCriticalSection(&g_CsJob);
    if ( v25 )
      SetLastError(v25);
    return v25 == 0;
  }
}

```

## disassembly

```asm
0x140036268  push    rbx
0x14003626a  push    rsi
0x14003626b  push    rdi
0x14003626c  push    r15
0x14003626e  sub     rsp, 48h
0x140036272  mov     rdi, rdx
0x140036275  mov     rbx, rcx
0x140036278  mov     rcx, cs:WPP_GLOBAL_Control
0x14003627f  lea     r15, WPP_GLOBAL_Control
0x140036286  lea     rsi, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14003628d  cmp     rcx, r15
0x140036290  jz      short loc_1400362AF
0x140036292  test    byte ptr [rcx+1Ch], 4
0x140036296  jz      short loc_1400362AF
0x140036298  cmp     byte ptr [rcx+19h], 5
0x14003629c  jb      short loc_1400362AF
0x14003629e  mov     rcx, [rcx+10h]
0x1400362a2  mov     edx, 0E7h
0x1400362a7  mov     r8, rsi
0x1400362aa  call    WPP_SF_
0x1400362af  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400362b6  call    cs:__imp_EnterCriticalSection
0x1400362bd  nop     dword ptr [rax+rax+00h]
0x1400362c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400362c9  cmp     rcx, r15
0x1400362cc  jz      short loc_1400362FD
0x1400362ce  test    byte ptr [rcx+1Ch], 4
0x1400362d2  jz      short loc_1400362FD
0x1400362d4  cmp     byte ptr [rcx+19h], 5
0x1400362d8  jb      short loc_1400362FD
0x1400362da  mov     eax, [rdi+0Ch]
0x1400362dd  mov     edx, 0E8h
0x1400362e2  mov     r9d, [rdi+8]
0x1400362e6  mov     r8, rsi
0x1400362e9  mov     rcx, [rcx+10h]
0x1400362ed  mov     [rsp+68h+var_48], eax
0x1400362f1  call    WPP_SF_dd
0x1400362f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400362fd  cmp     dword ptr [rbx+6C8h], 1
0x140036304  jnz     short loc_140036350
0x140036306  cmp     rcx, r15
0x140036309  jz      short loc_140036333
0x14003630b  test    byte ptr [rcx+1Ch], 4
0x14003630f  jz      short loc_140036333
0x140036311  cmp     byte ptr [rcx+19h], 3
0x140036315  jb      short loc_140036333
0x140036317  mov     r9, [rbx+450h]
0x14003631e  mov     edx, 0E9h
0x140036323  mov     rcx, [rcx+10h]
0x140036327  mov     r8, rsi
0x14003632a  mov     r9d, [r9+20h]
0x14003632e  call    WPP_SF_d
0x140036333  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003633a  call    cs:__imp_LeaveCriticalSection
0x140036341  nop     dword ptr [rax+rax+00h]
0x140036346  mov     eax, 1
0x14003634b  jmp     loc_140036730
0x140036350  mov     rcx, rdi; struct _FSPI_JOB_STATUS *
0x140036353  call    ?MapFSPIJobStatusToEventId@@YAKPEBU_FSPI_JOB_STATUS@@@Z; MapFSPIJobStatusToEventId(_FSPI_JOB_STATUS const *)
0x140036358  mov     r8, [rbx+450h]
0x14003635f  mov     esi, eax
0x140036361  cmp     dword ptr [r8+24h], 2
0x140036366  jnz     short loc_140036371
0x140036368  mov     r9, [r8+248h]
0x14003636f  jmp     short loc_140036374
0x140036371  mov     r9, r8
0x140036374  mov     rcx, [rbx+10h]
0x140036378  mov     edx, esi; unsigned int
0x14003637a  mov     r9, [r9+198h]; void *
0x140036381  mov     r8d, [r8+20h]; unsigned int
0x140036385  mov     ecx, [rcx+18h]; unsigned int
0x140036388  call    ?CreateFaxEvent@@YAHKKKPEAX@Z; CreateFaxEvent(ulong,ulong,ulong,void *)
0x14003638d  test    eax, eax
0x14003638f  jnz     loc_140036443
0x140036395  cmp     cs:?g_bServiceIsDown@@3HA, 1; int g_bServiceIsDown
0x14003639c  jnz     short loc_1400363EF
0x14003639e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400363a5  cmp     rcx, r15
0x1400363a8  jz      loc_140036443
0x1400363ae  test    byte ptr [rcx+1Ch], 4
0x1400363b2  jz      loc_140036443
0x1400363b8  cmp     byte ptr [rcx+19h], 3
0x1400363bc  jb      loc_140036443
0x1400363c2  mov     rax, [rbx+10h]
0x1400363c6  mov     edx, 0EAh
0x1400363cb  mov     r8, [rbx+450h]
0x1400363d2  mov     r9d, esi
0x1400363d5  mov     rcx, [rcx+10h]
0x1400363d9  mov     eax, [rax+18h]
0x1400363dc  mov     dword ptr [rsp+68h+var_40], eax
0x1400363e0  mov     eax, [r8+20h]
0x1400363e4  mov     [rsp+68h+var_48], eax
0x1400363e8  call    WPP_SF_Dll
0x1400363ed  jmp     short loc_140036443
0x1400363ef  mov     rax, cs:WPP_GLOBAL_Control
0x1400363f6  cmp     rax, r15
0x1400363f9  jz      short loc_140036443
0x1400363fb  test    byte ptr [rax+1Ch], 4
0x1400363ff  jz      short loc_140036443
0x140036401  cmp     byte ptr [rax+19h], 2
0x140036405  jb      short loc_140036443
0x140036407  call    cs:__imp_GetLastError
0x14003640e  nop     dword ptr [rax+rax+00h]
0x140036413  mov     rcx, [rbx+10h]
0x140036417  mov     r9d, esi
0x14003641a  mov     rdx, [rbx+450h]
0x140036421  mov     [rsp+68h+var_38], eax
0x140036425  mov     eax, [rcx+18h]
0x140036428  mov     rcx, cs:WPP_GLOBAL_Control
0x14003642f  mov     dword ptr [rsp+68h+var_40], eax
0x140036433  mov     eax, [rdx+20h]
0x140036436  mov     [rsp+68h+var_48], eax
0x14003643a  mov     rcx, [rcx+10h]
0x14003643e  call    WPP_SF_Dlll
0x140036443  mov     eax, [rdi+8]
0x140036446  lea     rsi, [rbx+464h]
0x14003644d  mov     [rbx+468h], eax
0x140036453  mov     eax, [rdi+0Ch]
0x140036456  mov     [rbx+46Ch], eax
0x14003645c  mov     eax, [rdi+10h]
0x14003645f  mov     [rbx+470h], eax
0x140036465  test    byte ptr [rdi+4], 1
0x140036469  jz      short loc_140036477
0x14003646b  mov     eax, [rdi+30h]
0x14003646e  or      dword ptr [rsi], 1
0x140036471  mov     [rbx+490h], eax
0x140036477  test    byte ptr [rdi+4], 2
0x14003647b  jz      short loc_14003648C
0x14003647d  movups  xmm0, xmmword ptr [rdi+34h]
0x140036481  or      dword ptr [rsi], 2
0x140036484  movdqu  xmmword ptr [rbx+494h], xmm0
0x14003648c  test    byte ptr [rdi+4], 4
0x140036490  jz      short loc_1400364A1
0x140036492  movups  xmm0, xmmword ptr [rdi+44h]
0x140036496  or      dword ptr [rsi], 4
0x140036499  movdqu  xmmword ptr [rbx+4A4h], xmm0
0x1400364a1  mov     rdx, [rdi+18h]; unsigned __int16 *
0x1400364a5  test    rdx, rdx
0x1400364a8  jz      short loc_1400364FD
0x1400364aa  lea     rcx, [rbx+478h]; unsigned __int16 **
0x1400364b1  call    ?ReplaceStringWithCopy@@YAHPEAPEAGPEBG@Z; ReplaceStringWithCopy(ushort * *,ushort const *)
0x1400364b6  test    eax, eax
0x1400364b8  jnz     short loc_1400364FD
0x1400364ba  mov     rax, cs:WPP_GLOBAL_Control
0x1400364c1  cmp     rax, r15
0x1400364c4  jz      short loc_1400364FD
0x1400364c6  test    byte ptr [rax+1Ch], 4
0x1400364ca  jz      short loc_1400364FD
0x1400364cc  cmp     byte ptr [rax+19h], 2
0x1400364d0  jb      short loc_1400364FD
0x1400364d2  call    cs:__imp_GetLastError
0x1400364d9  nop     dword ptr [rax+rax+00h]
0x1400364de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400364e5  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x1400364ec  mov     edx, 0ECh
0x1400364f1  mov     r9d, eax
0x1400364f4  mov     rcx, [rcx+10h]
0x1400364f8  call    WPP_SF_d
0x1400364fd  mov     rdx, [rdi+20h]; unsigned __int16 *
0x140036501  test    rdx, rdx
0x140036504  jz      short loc_140036559
0x140036506  lea     rcx, [rbx+480h]; unsigned __int16 **
0x14003650d  call    ?ReplaceStringWithCopy@@YAHPEAPEAGPEBG@Z; ReplaceStringWithCopy(ushort * *,ushort const *)
0x140036512  test    eax, eax
0x140036514  jnz     short loc_140036559
0x140036516  mov     rax, cs:WPP_GLOBAL_Control
0x14003651d  cmp     rax, r15
0x140036520  jz      short loc_140036559
0x140036522  test    byte ptr [rax+1Ch], 4
0x140036526  jz      short loc_140036559
0x140036528  cmp     byte ptr [rax+19h], 2
0x14003652c  jb      short loc_140036559
0x14003652e  call    cs:__imp_GetLastError
0x140036535  nop     dword ptr [rax+rax+00h]
0x14003653a  mov     rcx, cs:WPP_GLOBAL_Control
0x140036541  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x140036548  mov     edx, 0EDh
0x14003654d  mov     r9d, eax
0x140036550  mov     rcx, [rcx+10h]
0x140036554  call    WPP_SF_d
0x140036559  mov     rdx, [rdi+28h]; unsigned __int16 *
0x14003655d  test    rdx, rdx
0x140036560  jz      short loc_1400365B5
0x140036562  lea     rcx, [rbx+488h]; unsigned __int16 **
0x140036569  call    ?ReplaceStringWithCopy@@YAHPEAPEAGPEBG@Z; ReplaceStringWithCopy(ushort * *,ushort const *)
0x14003656e  test    eax, eax
0x140036570  jnz     short loc_1400365B5
0x140036572  mov     rax, cs:WPP_GLOBAL_Control
0x140036579  cmp     rax, r15
0x14003657c  jz      short loc_1400365B5
0x14003657e  test    byte ptr [rax+1Ch], 4
0x140036582  jz      short loc_1400365B5
0x140036584  cmp     byte ptr [rax+19h], 2
0x140036588  jb      short loc_1400365B5
0x14003658a  call    cs:__imp_GetLastError
0x140036591  nop     dword ptr [rax+rax+00h]
0x140036596  mov     rcx, cs:WPP_GLOBAL_Control
0x14003659d  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x1400365a4  mov     edx, 0EEh
0x1400365a9  mov     r9d, eax
0x1400365ac  mov     rcx, [rcx+10h]
0x1400365b0  call    WPP_SF_d
0x1400365b5  xor     eax, eax
0x1400365b7  lea     rdi, [rbx+4C0h]
0x1400365be  mov     [rdi], ax
0x1400365c1  cmp     [rbx+470h], eax
0x1400365c7  jz      loc_14003668C
0x1400365cd  mov     rax, [rbx+10h]
0x1400365d1  lea     rdx, a2172fd8f11f611; "{2172FD8F-11F6-11d3-90BF-006094EB630B}"
0x1400365d8  mov     rcx, [rax+28h]
0x1400365dc  add     rcx, 658h; String1
0x1400365e3  call    cs:__imp__wcsicmp
0x1400365ea  nop     dword ptr [rax+rax+00h]
0x1400365ef  test    eax, eax
0x1400365f1  jnz     short loc_1400365FC
0x1400365f3  mov     rcx, cs:?g_hResource@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hResource
0x1400365fa  jmp     short loc_140036608
0x1400365fc  mov     rax, [rbx+10h]
0x140036600  mov     rcx, [rax+28h]
0x140036604  mov     rcx, [rcx+38h]; hInstance
0x140036608  mov     edx, [rbx+470h]; uID
0x14003660e  mov     r9d, 100h; cchBufferMax
0x140036614  mov     r8, rdi; lpBuffer
0x140036617  call    cs:__imp_LoadStringW
0x14003661e  nop     dword ptr [rax+rax+00h]
0x140036623  test    eax, eax
0x140036625  jnz     short loc_14003668C
0x140036627  call    cs:__imp_GetLastError
0x14003662e  nop     dword ptr [rax+rax+00h]
0x140036633  mov     edi, eax
0x140036635  mov     rcx, cs:WPP_GLOBAL_Control
0x14003663c  cmp     rcx, r15
0x14003663f  jz      short loc_14003667B
0x140036641  test    byte ptr [rcx+1Ch], 4
0x140036645  jz      short loc_14003667B
0x140036647  cmp     byte ptr [rcx+19h], 2
0x14003664b  jb      short loc_14003667B
0x14003664d  mov     rdx, [rbx+10h]
0x140036651  mov     r9d, edi
0x140036654  mov     rcx, [rcx+10h]
0x140036658  mov     rax, [rdx+28h]
0x14003665c  mov     edx, 0EFh
0x140036661  add     rax, 248h
0x140036667  mov     [rsp+68h+var_40], rax
0x14003666c  mov     eax, [rbx+470h]
0x140036672  mov     [rsp+68h+var_48], eax
0x140036676  call    WPP_SF_llS
0x14003667b  btr     dword ptr [rsi], 1Ch
0x14003667f  mov     qword ptr [rbx+46Ch], 0
0x14003668a  jmp     short loc_140036704
0x14003668c  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140036693  xor     edi, edi
0x140036695  call    cs:__imp_EnterCriticalSection
0x14003669c  nop     dword ptr [rax+rax+00h]
0x1400366a1  mov     rdx, [rbx+450h]
0x1400366a8  lea     ecx, [rdi+2]
0x1400366ab  call    ?CreateQueueEvent@@YAKW4FAX_ENUM_JOB_EVENT_TYPE@@QEAU_JOB_QUEUE@@@Z; CreateQueueEvent(FAX_ENUM_JOB_EVENT_TYPE,_JOB_QUEUE * const)
0x1400366b0  test    eax, eax
0x1400366b2  jz      short loc_1400366F1
0x1400366b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400366bb  cmp     rcx, r15
0x1400366be  jz      short loc_1400366F1
0x1400366c0  test    byte ptr [rcx+1Ch], 4
0x1400366c4  jz      short loc_1400366F1
0x1400366c6  cmp     byte ptr [rcx+19h], 2
0x1400366ca  jb      short loc_1400366F1
0x1400366cc  mov     r9, [rbx+450h]
0x1400366d3  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x1400366da  mov     rcx, [rcx+10h]
0x1400366de  mov     edx, 0F0h
0x1400366e3  mov     word ptr [rsp+68h+var_48], ax
0x1400366e8  mov     r9d, [r9+10h]
0x1400366ec  call    WPP_SF_lh
0x1400366f1  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400366f8  call    cs:__imp_LeaveCriticalSection
0x1400366ff  nop     dword ptr [rax+rax+00h]
0x140036704  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003670b  call    cs:__imp_LeaveCriticalSection
0x140036712  nop     dword ptr [rax+rax+00h]
0x140036717  test    edi, edi
0x140036719  jz      short loc_140036729
0x14003671b  mov     ecx, edi; dwErrCode
0x14003671d  call    cs:__imp_SetLastError
0x140036724  nop     dword ptr [rax+rax+00h]
0x140036729  xor     eax, eax
0x14003672b  test    edi, edi
0x14003672d  setz    al
0x140036730  add     rsp, 48h
0x140036734  pop     r15
0x140036736  pop     rdi
0x140036737  pop     rsi
0x140036738  pop     rbx
0x140036739  retn
```
