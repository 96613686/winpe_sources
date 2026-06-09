# UpdateJobStatus(_JOB_ENTRY *,_FSPI_JOB_STATUS const *)

- ea: `0x14003465c`
- end: `0x140034adc`
- name: `?UpdateJobStatus@@YAHPEAU_JOB_ENTRY@@PEBU_FSPI_JOB_STATUS@@@Z`
- size: `1152`
- prototype: `int(struct _JOB_ENTRY *, const struct _FSPI_JOB_STATUS *)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x14002f9f0`
- `0x14003ed20`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x140004e68`
- `0x140014c24`
- `0x140022a4c`
- `0x14003465c`
- `0x140034ef8`
- `0x140034f58`
- `0x140035554`
- `0x1400505e8`
- `0x14005584c`
- `0x140055acc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400347eb`
- `KERNEL32!GetLastError` at `0x1400348b0`
- `KERNEL32!GetLastError` at `0x140034906`
- `KERNEL32!GetLastError` at `0x14003495c`
- `KERNEL32!GetLastError` at `0x1400349e7`
- `KERNEL32!GetLastError` at `0x1400347eb`
- `KERNEL32!GetLastError` at `0x1400348b0`
- `KERNEL32!GetLastError` at `0x140034906`
- `KERNEL32!GetLastError` at `0x14003495c`
- `KERNEL32!GetLastError` at `0x1400349e7`
- `KERNEL32!SetLastError` at `0x140034ac5`
- `KERNEL32!SetLastError` at `0x140034ac5`
- `KERNEL32!EnterCriticalSection` at `0x1400346aa`
- `KERNEL32!EnterCriticalSection` at `0x140034a4f`
- `KERNEL32!EnterCriticalSection` at `0x1400346aa`
- `KERNEL32!EnterCriticalSection` at `0x140034a4f`
- `KERNEL32!LeaveCriticalSection` at `0x140034728`
- `KERNEL32!LeaveCriticalSection` at `0x140034aac`
- `KERNEL32!LeaveCriticalSection` at `0x140034ab9`
- `KERNEL32!LeaveCriticalSection` at `0x140034728`
- `KERNEL32!LeaveCriticalSection` at `0x140034aac`
- `KERNEL32!LeaveCriticalSection` at `0x140034ab9`
- `msvcrt!_wcsicmp` at `0x1400349af`
- `msvcrt!_wcsicmp` at `0x1400349af`
- `USER32!LoadStringW` at `0x1400349dd`
- `USER32!LoadStringW` at `0x1400349dd`

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
  unsigned __int16 *v16; // rdx
  DWORD v17; // eax
  unsigned __int16 *v18; // rdx
  DWORD v19; // eax
  unsigned __int16 *v20; // rdx
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
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      232,
      &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
      *((unsigned int *)a2 + 2),
      *((_DWORD *)a2 + 3));
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
    v16 = (unsigned __int16 *)*((_QWORD *)a2 + 3);
    if ( v16
      && !ReplaceStringWithCopy((LPVOID *)a1 + 143, v16)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v17 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 236, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, v17);
    }
    v18 = (unsigned __int16 *)*((_QWORD *)a2 + 4);
    if ( v18
      && !ReplaceStringWithCopy((LPVOID *)a1 + 144, v18)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v19 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 237, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, v19);
    }
    v20 = (unsigned __int16 *)*((_QWORD *)a2 + 5);
    if ( v20
      && !ReplaceStringWithCopy((LPVOID *)a1 + 145, v20)
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
0x14003465c  push    rbx
0x14003465e  push    rsi
0x14003465f  push    rdi
0x140034660  push    r15
0x140034662  sub     rsp, 48h
0x140034666  mov     rdi, rdx
0x140034669  mov     rbx, rcx
0x14003466c  mov     rcx, cs:WPP_GLOBAL_Control
0x140034673  lea     r15, WPP_GLOBAL_Control
0x14003467a  lea     rsi, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x140034681  cmp     rcx, r15
0x140034684  jz      short loc_1400346A3
0x140034686  test    byte ptr [rcx+1Ch], 4
0x14003468a  jz      short loc_1400346A3
0x14003468c  cmp     byte ptr [rcx+19h], 5
0x140034690  jb      short loc_1400346A3
0x140034692  mov     rcx, [rcx+10h]
0x140034696  mov     edx, 0E7h
0x14003469b  mov     r8, rsi
0x14003469e  call    WPP_SF_
0x1400346a3  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400346aa  call    cs:__imp_EnterCriticalSection
0x1400346b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400346b7  cmp     rcx, r15
0x1400346ba  jz      short loc_1400346EB
0x1400346bc  test    byte ptr [rcx+1Ch], 4
0x1400346c0  jz      short loc_1400346EB
0x1400346c2  cmp     byte ptr [rcx+19h], 5
0x1400346c6  jb      short loc_1400346EB
0x1400346c8  mov     eax, [rdi+0Ch]
0x1400346cb  mov     edx, 0E8h
0x1400346d0  mov     r9d, [rdi+8]
0x1400346d4  mov     r8, rsi
0x1400346d7  mov     rcx, [rcx+10h]
0x1400346db  mov     [rsp+68h+var_48], eax
0x1400346df  call    WPP_SF_dd
0x1400346e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400346eb  cmp     dword ptr [rbx+6C8h], 1
0x1400346f2  jnz     short loc_140034738
0x1400346f4  cmp     rcx, r15
0x1400346f7  jz      short loc_140034721
0x1400346f9  test    byte ptr [rcx+1Ch], 4
0x1400346fd  jz      short loc_140034721
0x1400346ff  cmp     byte ptr [rcx+19h], 3
0x140034703  jb      short loc_140034721
0x140034705  mov     r9, [rbx+450h]
0x14003470c  mov     edx, 0E9h
0x140034711  mov     rcx, [rcx+10h]
0x140034715  mov     r8, rsi
0x140034718  mov     r9d, [r9+20h]
0x14003471c  call    WPP_SF_d
0x140034721  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140034728  call    cs:__imp_LeaveCriticalSection
0x14003472e  mov     eax, 1
0x140034733  jmp     loc_140034AD2
0x140034738  mov     rcx, rdi; struct _FSPI_JOB_STATUS *
0x14003473b  call    ?MapFSPIJobStatusToEventId@@YAKPEBU_FSPI_JOB_STATUS@@@Z; MapFSPIJobStatusToEventId(_FSPI_JOB_STATUS const *)
0x140034740  mov     r8, [rbx+450h]
0x140034747  mov     esi, eax
0x140034749  cmp     dword ptr [r8+24h], 2
0x14003474e  jnz     short loc_140034759
0x140034750  mov     r9, [r8+248h]
0x140034757  jmp     short loc_14003475C
0x140034759  mov     r9, r8
0x14003475c  mov     rcx, [rbx+10h]
0x140034760  mov     edx, esi; unsigned int
0x140034762  mov     r9, [r9+198h]; void *
0x140034769  mov     r8d, [r8+20h]; unsigned int
0x14003476d  mov     ecx, [rcx+18h]; unsigned int
0x140034770  call    ?CreateFaxEvent@@YAHKKKPEAX@Z; CreateFaxEvent(ulong,ulong,ulong,void *)
0x140034775  test    eax, eax
0x140034777  jnz     loc_140034821
0x14003477d  cmp     cs:?g_bServiceIsDown@@3HA, 1; int g_bServiceIsDown
0x140034784  jnz     short loc_1400347D3
0x140034786  mov     rcx, cs:WPP_GLOBAL_Control
0x14003478d  cmp     rcx, r15
0x140034790  jz      loc_140034821
0x140034796  test    byte ptr [rcx+1Ch], 4
0x14003479a  jz      loc_140034821
0x1400347a0  cmp     byte ptr [rcx+19h], 3
0x1400347a4  jb      short loc_140034821
0x1400347a6  mov     rax, [rbx+10h]
0x1400347aa  mov     edx, 0EAh
0x1400347af  mov     r8, [rbx+450h]
0x1400347b6  mov     r9d, esi
0x1400347b9  mov     rcx, [rcx+10h]
0x1400347bd  mov     eax, [rax+18h]
0x1400347c0  mov     dword ptr [rsp+68h+var_40], eax
0x1400347c4  mov     eax, [r8+20h]
0x1400347c8  mov     [rsp+68h+var_48], eax
0x1400347cc  call    WPP_SF_Dll
0x1400347d1  jmp     short loc_140034821
0x1400347d3  mov     rax, cs:WPP_GLOBAL_Control
0x1400347da  cmp     rax, r15
0x1400347dd  jz      short loc_140034821
0x1400347df  test    byte ptr [rax+1Ch], 4
0x1400347e3  jz      short loc_140034821
0x1400347e5  cmp     byte ptr [rax+19h], 2
0x1400347e9  jb      short loc_140034821
0x1400347eb  call    cs:__imp_GetLastError
0x1400347f1  mov     rcx, [rbx+10h]
0x1400347f5  mov     r9d, esi
0x1400347f8  mov     rdx, [rbx+450h]
0x1400347ff  mov     [rsp+68h+var_38], eax
0x140034803  mov     eax, [rcx+18h]
0x140034806  mov     rcx, cs:WPP_GLOBAL_Control
0x14003480d  mov     dword ptr [rsp+68h+var_40], eax
0x140034811  mov     eax, [rdx+20h]
0x140034814  mov     [rsp+68h+var_48], eax
0x140034818  mov     rcx, [rcx+10h]
0x14003481c  call    WPP_SF_Dlll
0x140034821  mov     eax, [rdi+8]
0x140034824  lea     rsi, [rbx+464h]
0x14003482b  mov     [rbx+468h], eax
0x140034831  mov     eax, [rdi+0Ch]
0x140034834  mov     [rbx+46Ch], eax
0x14003483a  mov     eax, [rdi+10h]
0x14003483d  mov     [rbx+470h], eax
0x140034843  test    byte ptr [rdi+4], 1
0x140034847  jz      short loc_140034855
0x140034849  mov     eax, [rdi+30h]
0x14003484c  or      dword ptr [rsi], 1
0x14003484f  mov     [rbx+490h], eax
0x140034855  test    byte ptr [rdi+4], 2
0x140034859  jz      short loc_14003486A
0x14003485b  movups  xmm0, xmmword ptr [rdi+34h]
0x14003485f  or      dword ptr [rsi], 2
0x140034862  movdqu  xmmword ptr [rbx+494h], xmm0
0x14003486a  test    byte ptr [rdi+4], 4
0x14003486e  jz      short loc_14003487F
0x140034870  movups  xmm0, xmmword ptr [rdi+44h]
0x140034874  or      dword ptr [rsi], 4
0x140034877  movdqu  xmmword ptr [rbx+4A4h], xmm0
0x14003487f  mov     rdx, [rdi+18h]; unsigned __int16 *
0x140034883  test    rdx, rdx
0x140034886  jz      short loc_1400348D5
0x140034888  lea     rcx, [rbx+478h]; unsigned __int16 **
0x14003488f  call    ?ReplaceStringWithCopy@@YAHPEAPEAGPEBG@Z; ReplaceStringWithCopy(ushort * *,ushort const *)
0x140034894  test    eax, eax
0x140034896  jnz     short loc_1400348D5
0x140034898  mov     rax, cs:WPP_GLOBAL_Control
0x14003489f  cmp     rax, r15
0x1400348a2  jz      short loc_1400348D5
0x1400348a4  test    byte ptr [rax+1Ch], 4
0x1400348a8  jz      short loc_1400348D5
0x1400348aa  cmp     byte ptr [rax+19h], 2
0x1400348ae  jb      short loc_1400348D5
0x1400348b0  call    cs:__imp_GetLastError
0x1400348b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400348bd  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x1400348c4  mov     edx, 0ECh
0x1400348c9  mov     r9d, eax
0x1400348cc  mov     rcx, [rcx+10h]
0x1400348d0  call    WPP_SF_d
0x1400348d5  mov     rdx, [rdi+20h]; unsigned __int16 *
0x1400348d9  test    rdx, rdx
0x1400348dc  jz      short loc_14003492B
0x1400348de  lea     rcx, [rbx+480h]; unsigned __int16 **
0x1400348e5  call    ?ReplaceStringWithCopy@@YAHPEAPEAGPEBG@Z; ReplaceStringWithCopy(ushort * *,ushort const *)
0x1400348ea  test    eax, eax
0x1400348ec  jnz     short loc_14003492B
0x1400348ee  mov     rax, cs:WPP_GLOBAL_Control
0x1400348f5  cmp     rax, r15
0x1400348f8  jz      short loc_14003492B
0x1400348fa  test    byte ptr [rax+1Ch], 4
0x1400348fe  jz      short loc_14003492B
0x140034900  cmp     byte ptr [rax+19h], 2
0x140034904  jb      short loc_14003492B
0x140034906  call    cs:__imp_GetLastError
0x14003490c  mov     rcx, cs:WPP_GLOBAL_Control
0x140034913  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14003491a  mov     edx, 0EDh
0x14003491f  mov     r9d, eax
0x140034922  mov     rcx, [rcx+10h]
0x140034926  call    WPP_SF_d
0x14003492b  mov     rdx, [rdi+28h]; unsigned __int16 *
0x14003492f  test    rdx, rdx
0x140034932  jz      short loc_140034981
0x140034934  lea     rcx, [rbx+488h]; unsigned __int16 **
0x14003493b  call    ?ReplaceStringWithCopy@@YAHPEAPEAGPEBG@Z; ReplaceStringWithCopy(ushort * *,ushort const *)
0x140034940  test    eax, eax
0x140034942  jnz     short loc_140034981
0x140034944  mov     rax, cs:WPP_GLOBAL_Control
0x14003494b  cmp     rax, r15
0x14003494e  jz      short loc_140034981
0x140034950  test    byte ptr [rax+1Ch], 4
0x140034954  jz      short loc_140034981
0x140034956  cmp     byte ptr [rax+19h], 2
0x14003495a  jb      short loc_140034981
0x14003495c  call    cs:__imp_GetLastError
0x140034962  mov     rcx, cs:WPP_GLOBAL_Control
0x140034969  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x140034970  mov     edx, 0EEh
0x140034975  mov     r9d, eax
0x140034978  mov     rcx, [rcx+10h]
0x14003497c  call    WPP_SF_d
0x140034981  xor     eax, eax
0x140034983  lea     rdi, [rbx+4C0h]
0x14003498a  mov     [rdi], ax
0x14003498d  cmp     [rbx+470h], eax
0x140034993  jz      loc_140034A46
0x140034999  mov     rax, [rbx+10h]
0x14003499d  lea     rdx, a2172fd8f11f611; "{2172FD8F-11F6-11d3-90BF-006094EB630B}"
0x1400349a4  mov     rcx, [rax+28h]
0x1400349a8  add     rcx, 658h; String1
0x1400349af  call    cs:__imp__wcsicmp
0x1400349b5  test    eax, eax
0x1400349b7  jnz     short loc_1400349C2
0x1400349b9  mov     rcx, cs:?g_hResource@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hResource
0x1400349c0  jmp     short loc_1400349CE
0x1400349c2  mov     rax, [rbx+10h]
0x1400349c6  mov     rcx, [rax+28h]
0x1400349ca  mov     rcx, [rcx+38h]; hInstance
0x1400349ce  mov     edx, [rbx+470h]; uID
0x1400349d4  mov     r9d, 100h; cchBufferMax
0x1400349da  mov     r8, rdi; lpBuffer
0x1400349dd  call    cs:__imp_LoadStringW
0x1400349e3  test    eax, eax
0x1400349e5  jnz     short loc_140034A46
0x1400349e7  call    cs:__imp_GetLastError
0x1400349ed  mov     edi, eax
0x1400349ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400349f6  cmp     rcx, r15
0x1400349f9  jz      short loc_140034A35
0x1400349fb  test    byte ptr [rcx+1Ch], 4
0x1400349ff  jz      short loc_140034A35
0x140034a01  cmp     byte ptr [rcx+19h], 2
0x140034a05  jb      short loc_140034A35
0x140034a07  mov     rdx, [rbx+10h]
0x140034a0b  mov     r9d, edi
0x140034a0e  mov     rcx, [rcx+10h]
0x140034a12  mov     rax, [rdx+28h]
0x140034a16  mov     edx, 0EFh
0x140034a1b  add     rax, 248h
0x140034a21  mov     [rsp+68h+var_40], rax
0x140034a26  mov     eax, [rbx+470h]
0x140034a2c  mov     [rsp+68h+var_48], eax
0x140034a30  call    WPP_SF_llS
0x140034a35  btr     dword ptr [rsi], 1Ch
0x140034a39  mov     qword ptr [rbx+46Ch], 0
0x140034a44  jmp     short loc_140034AB2
0x140034a46  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140034a4d  xor     edi, edi
0x140034a4f  call    cs:__imp_EnterCriticalSection
0x140034a55  mov     rdx, [rbx+450h]
0x140034a5c  lea     ecx, [rdi+2]
0x140034a5f  call    ?CreateQueueEvent@@YAKW4FAX_ENUM_JOB_EVENT_TYPE@@QEAU_JOB_QUEUE@@@Z; CreateQueueEvent(FAX_ENUM_JOB_EVENT_TYPE,_JOB_QUEUE * const)
0x140034a64  test    eax, eax
0x140034a66  jz      short loc_140034AA5
0x140034a68  mov     rcx, cs:WPP_GLOBAL_Control
0x140034a6f  cmp     rcx, r15
0x140034a72  jz      short loc_140034AA5
0x140034a74  test    byte ptr [rcx+1Ch], 4
0x140034a78  jz      short loc_140034AA5
0x140034a7a  cmp     byte ptr [rcx+19h], 2
0x140034a7e  jb      short loc_140034AA5
0x140034a80  mov     r9, [rbx+450h]
0x140034a87  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x140034a8e  mov     rcx, [rcx+10h]
0x140034a92  mov     edx, 0F0h
0x140034a97  mov     word ptr [rsp+68h+var_48], ax
0x140034a9c  mov     r9d, [r9+10h]
0x140034aa0  call    WPP_SF_lh
0x140034aa5  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140034aac  call    cs:__imp_LeaveCriticalSection
0x140034ab2  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140034ab9  call    cs:__imp_LeaveCriticalSection
0x140034abf  test    edi, edi
0x140034ac1  jz      short loc_140034ACB
0x140034ac3  mov     ecx, edi; dwErrCode
0x140034ac5  call    cs:__imp_SetLastError
0x140034acb  xor     eax, eax
0x140034acd  test    edi, edi
0x140034acf  setz    al
0x140034ad2  add     rsp, 48h
0x140034ad6  pop     r15
0x140034ad8  pop     rdi
0x140034ad9  pop     rsi
0x140034ada  pop     rbx
0x140034adb  retn
```
