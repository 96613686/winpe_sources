# LoadActivityLoggingSettings

- ea: `0x140082538`
- end: `0x140082828`
- name: `LoadActivityLoggingSettings`
- size: `752`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14004a944`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x14006998c`
- `0x140073d5c`
- `0x140074cb4`
- `0x140074f18`
- `0x140082538`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14008280c`
- `ADVAPI32!RegCloseKey` at `0x14008280c`
- `KERNEL32!GetLastError` at `0x1400825a6`
- `KERNEL32!GetLastError` at `0x1400825a6`
- `KERNEL32!lstrcmpW` at `0x1400827bc`
- `KERNEL32!lstrcmpW` at `0x1400827bc`

## string_xrefs

- `0x1400825fa`: `LogIncoming`

## pseudocode

```c
__int64 __fastcall LoadActivityLoggingSettings(__int64 a1)
{
  HKEY v2; // rax
  HKEY v3; // rdi
  DWORD LastError; // eax
  DWORD v5; // ebx
  unsigned int v7; // esi
  int RegistryDwordDefault; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  BYTE *RegistryStringValue; // rax
  DWORD v15; // [rsp+20h] [rbp-18h]
  int Data; // [rsp+78h] [rbp+40h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids);
  }
  v2 = OpenRegistryKey(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax\\ActivityLogging", 0, 0x2001Fu);
  v3 = v2;
  if ( v2 )
  {
    v7 = 0;
    *(_DWORD *)a1 = 24;
    Data = 0;
    RegistryDwordDefault = GetRegistryDwordDefault(v2, L"LogIncoming", (BYTE *)&Data, 0);
    *(_DWORD *)(a1 + 4) = RegistryDwordDefault != 0 ? Data : 0;
    Data = 0;
    v9 = GetRegistryDwordDefault(v3, L"LogOutgoing", (BYTE *)&Data, 0);
    *(_DWORD *)(a1 + 8) = v9 != 0 ? Data : 0;
    Data = 0;
    v10 = GetRegistryDwordDefault(v3, L"LogLimitCriteria", (BYTE *)&Data, 0);
    *(_DWORD *)(a1 + 24) = v10 != 0 ? Data : 0;
    Data = 0;
    v11 = GetRegistryDwordDefault(v3, L"LogSizeLimit", (BYTE *)&Data, 0);
    *(_DWORD *)(a1 + 28) = v11 != 0 ? Data : 0;
    Data = 0;
    v12 = GetRegistryDwordDefault(v3, L"LogAgeLimit", (BYTE *)&Data, 0);
    *(_DWORD *)(a1 + 32) = v12 != 0 ? Data : 0;
    Data = 0;
    v13 = GetRegistryDwordDefault(v3, L"LogLimitReachedAction", (BYTE *)&Data, 0);
    *(_DWORD *)(a1 + 36) = v13 != 0 ? Data : 0;
    if ( !*(_DWORD *)(a1 + 28) )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, 50);
      }
      *(_DWORD *)(a1 + 28) = 50;
    }
    if ( !*(_DWORD *)(a1 + 32) )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, 1);
      }
      *(_DWORD *)(a1 + 32) = 1;
    }
    if ( *(_DWORD *)(a1 + 24) >= 3u )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids);
      }
      *(_DWORD *)(a1 + 24) = 0;
    }
    if ( *(_DWORD *)(a1 + 36) >= 2u )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids);
      }
      *(_DWORD *)(a1 + 36) = 0;
    }
    RegistryStringValue = GetRegistryStringValue(v3, 1u, L"DBFile", L"\\\\\\", v15);
    *(_QWORD *)(a1 + 16) = RegistryStringValue;
    if ( !lstrcmpW(L"\\\\\\", (LPCWSTR)RegistryStringValue) )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids);
      }
      v7 = 13;
      pMemFree(*(LPVOID *)(a1 + 16));
      *(_QWORD *)(a1 + 16) = 0;
    }
    RegCloseKey(v3);
    return v7;
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, LastError);
    }
    return v5;
  }
}

```

## disassembly

```asm
0x140082538  push    rbp
0x14008253a  push    rbx
0x14008253b  push    rsi
0x14008253c  push    rdi
0x14008253d  push    r12
0x14008253f  push    r15
0x140082541  mov     rbp, rsp
0x140082544  sub     rsp, 38h
0x140082548  mov     rbx, rcx
0x14008254b  mov     rcx, cs:WPP_GLOBAL_Control
0x140082552  lea     r15, WPP_GLOBAL_Control
0x140082559  lea     r12, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x140082560  cmp     rcx, r15
0x140082563  jz      short loc_140082582
0x140082565  test    byte ptr [rcx+1Ch], 2
0x140082569  jz      short loc_140082582
0x14008256b  cmp     byte ptr [rcx+19h], 5
0x14008256f  jb      short loc_140082582
0x140082571  mov     rcx, [rcx+10h]
0x140082575  mov     edx, 3Ah ; ':'
0x14008257a  mov     r8, r12
0x14008257d  call    WPP_SF_
0x140082582  mov     r9d, 2001Fh
0x140082588  lea     rdx, aSoftwareMicros_9; "Software\\Microsoft\\Fax\\ActivityLoggi"...
0x14008258f  xor     r8d, r8d
0x140082592  mov     rcx, 0FFFFFFFF80000002h
0x140082599  call    OpenRegistryKey
0x14008259e  mov     rdi, rax
0x1400825a1  test    rax, rax
0x1400825a4  jnz     short loc_1400825E5
0x1400825a6  call    cs:__imp_GetLastError
0x1400825ad  nop     dword ptr [rax+rax+00h]
0x1400825b2  mov     ebx, eax
0x1400825b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400825bb  cmp     rcx, r15
0x1400825be  jz      short loc_1400825DE
0x1400825c0  test    byte ptr [rcx+1Ch], 2
0x1400825c4  jz      short loc_1400825DE
0x1400825c6  cmp     byte ptr [rcx+19h], 2
0x1400825ca  jb      short loc_1400825DE
0x1400825cc  mov     rcx, [rcx+10h]
0x1400825d0  lea     edx, [rdi+3Bh]
0x1400825d3  mov     r9d, eax
0x1400825d6  mov     r8, r12
0x1400825d9  call    WPP_SF_d
0x1400825de  mov     eax, ebx
0x1400825e0  jmp     loc_14008281A
0x1400825e5  xor     esi, esi
0x1400825e7  mov     dword ptr [rbx], 18h
0x1400825ed  xor     r9d, r9d
0x1400825f0  mov     [rbp+Data], esi
0x1400825f3  lea     r8, [rbp+Data]; lpData
0x1400825f7  mov     rcx, rdi; hKey
0x1400825fa  lea     rdx, aLogincoming; "LogIncoming"
0x140082601  call    GetRegistryDwordDefault
0x140082606  neg     eax
0x140082608  lea     r8, [rbp+Data]; lpData
0x14008260c  lea     rdx, aLogoutgoing; "LogOutgoing"
0x140082613  sbb     ecx, ecx
0x140082615  xor     r9d, r9d
0x140082618  and     ecx, [rbp+Data]
0x14008261b  mov     [rbx+4], ecx
0x14008261e  mov     rcx, rdi; hKey
0x140082621  mov     [rbp+Data], esi
0x140082624  call    GetRegistryDwordDefault
0x140082629  neg     eax
0x14008262b  lea     r8, [rbp+Data]; lpData
0x14008262f  lea     rdx, aLoglimitcriter; "LogLimitCriteria"
0x140082636  sbb     ecx, ecx
0x140082638  xor     r9d, r9d
0x14008263b  and     ecx, [rbp+Data]
0x14008263e  mov     [rbx+8], ecx
0x140082641  mov     rcx, rdi; hKey
0x140082644  mov     [rbp+Data], esi
0x140082647  call    GetRegistryDwordDefault
0x14008264c  neg     eax
0x14008264e  lea     r8, [rbp+Data]; lpData
0x140082652  lea     rdx, aLogsizelimit; "LogSizeLimit"
0x140082659  sbb     ecx, ecx
0x14008265b  xor     r9d, r9d
0x14008265e  and     ecx, [rbp+Data]
0x140082661  mov     [rbx+18h], ecx
0x140082664  mov     rcx, rdi; hKey
0x140082667  mov     [rbp+Data], esi
0x14008266a  call    GetRegistryDwordDefault
0x14008266f  neg     eax
0x140082671  lea     r8, [rbp+Data]; lpData
0x140082675  lea     rdx, aLogagelimit; "LogAgeLimit"
0x14008267c  sbb     ecx, ecx
0x14008267e  xor     r9d, r9d
0x140082681  and     ecx, [rbp+Data]
0x140082684  mov     [rbx+1Ch], ecx
0x140082687  mov     rcx, rdi; hKey
0x14008268a  mov     [rbp+Data], esi
0x14008268d  call    GetRegistryDwordDefault
0x140082692  neg     eax
0x140082694  lea     r8, [rbp+Data]; lpData
0x140082698  lea     rdx, aLoglimitreache; "LogLimitReachedAction"
0x14008269f  sbb     ecx, ecx
0x1400826a1  xor     r9d, r9d
0x1400826a4  and     ecx, [rbp+Data]
0x1400826a7  mov     [rbx+20h], ecx
0x1400826aa  mov     rcx, rdi; hKey
0x1400826ad  mov     [rbp+Data], esi
0x1400826b0  call    GetRegistryDwordDefault
0x1400826b5  neg     eax
0x1400826b7  sbb     ecx, ecx
0x1400826b9  and     ecx, [rbp+Data]
0x1400826bc  mov     [rbx+24h], ecx
0x1400826bf  cmp     [rbx+1Ch], esi
0x1400826c2  jnz     short loc_1400826F6
0x1400826c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400826cb  cmp     rcx, r15
0x1400826ce  jz      short loc_1400826EF
0x1400826d0  test    byte ptr [rcx+1Ch], 2
0x1400826d4  jz      short loc_1400826EF
0x1400826d6  cmp     byte ptr [rcx+19h], 2
0x1400826da  jb      short loc_1400826EF
0x1400826dc  mov     rcx, [rcx+10h]
0x1400826e0  lea     edx, [rsi+3Ch]
0x1400826e3  lea     r9d, [rsi+32h]
0x1400826e7  mov     r8, r12
0x1400826ea  call    WPP_SF_d
0x1400826ef  mov     dword ptr [rbx+1Ch], 32h ; '2'
0x1400826f6  cmp     [rbx+20h], esi
0x1400826f9  jnz     short loc_14008272F
0x1400826fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140082702  cmp     rcx, r15
0x140082705  jz      short loc_140082728
0x140082707  test    byte ptr [rcx+1Ch], 2
0x14008270b  jz      short loc_140082728
0x14008270d  cmp     byte ptr [rcx+19h], 2
0x140082711  jb      short loc_140082728
0x140082713  mov     rcx, [rcx+10h]
0x140082717  mov     edx, 3Dh ; '='
0x14008271c  mov     r8, r12
0x14008271f  lea     r9d, [rdx-3Ch]
0x140082723  call    WPP_SF_d
0x140082728  mov     dword ptr [rbx+20h], 1
0x14008272f  cmp     dword ptr [rbx+18h], 3
0x140082733  jb      short loc_140082761
0x140082735  mov     rcx, cs:WPP_GLOBAL_Control
0x14008273c  cmp     rcx, r15
0x14008273f  jz      short loc_14008275E
0x140082741  test    byte ptr [rcx+1Ch], 2
0x140082745  jz      short loc_14008275E
0x140082747  cmp     byte ptr [rcx+19h], 2
0x14008274b  jb      short loc_14008275E
0x14008274d  mov     rcx, [rcx+10h]
0x140082751  mov     edx, 3Eh ; '>'
0x140082756  mov     r8, r12
0x140082759  call    WPP_SF_
0x14008275e  mov     [rbx+18h], esi
0x140082761  cmp     dword ptr [rbx+24h], 2
0x140082765  jb      short loc_140082793
0x140082767  mov     rcx, cs:WPP_GLOBAL_Control
0x14008276e  cmp     rcx, r15
0x140082771  jz      short loc_140082790
0x140082773  test    byte ptr [rcx+1Ch], 2
0x140082777  jz      short loc_140082790
0x140082779  cmp     byte ptr [rcx+19h], 2
0x14008277d  jb      short loc_140082790
0x14008277f  mov     rcx, [rcx+10h]
0x140082783  mov     edx, 3Fh ; '?'
0x140082788  mov     r8, r12
0x14008278b  call    WPP_SF_
0x140082790  mov     [rbx+24h], esi
0x140082793  lea     r9, asc_1400945F8; "\\\\\\"
0x14008279a  mov     edx, 1; dwType
0x14008279f  lea     r8, aDbfile; "DBFile"
0x1400827a6  mov     rcx, rdi; hKey
0x1400827a9  call    ?GetRegistryStringValue@@YAPEAGPEAUHKEY__@@KPEBG1PEAK@Z; GetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,ulong *)
0x1400827ae  mov     rdx, rax; lpString2
0x1400827b1  mov     [rbx+10h], rax
0x1400827b5  lea     rcx, asc_1400945F8; "\\\\\\"
0x1400827bc  call    cs:__imp_lstrcmpW
0x1400827c3  nop     dword ptr [rax+rax+00h]
0x1400827c8  test    eax, eax
0x1400827ca  jnz     short loc_140082809
0x1400827cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400827d3  cmp     rcx, r15
0x1400827d6  jz      short loc_1400827F3
0x1400827d8  test    byte ptr [rcx+1Ch], 2
0x1400827dc  jz      short loc_1400827F3
0x1400827de  cmp     byte ptr [rcx+19h], 2
0x1400827e2  jb      short loc_1400827F3
0x1400827e4  mov     rcx, [rcx+10h]
0x1400827e8  lea     edx, [rax+40h]
0x1400827eb  mov     r8, r12
0x1400827ee  call    WPP_SF_
0x1400827f3  mov     rcx, [rbx+10h]; lpMem
0x1400827f7  mov     esi, 0Dh
0x1400827fc  call    pMemFree
0x140082801  mov     qword ptr [rbx+10h], 0
0x140082809  mov     rcx, rdi; hKey
0x14008280c  call    cs:__imp_RegCloseKey
0x140082813  nop     dword ptr [rax+rax+00h]
0x140082818  mov     eax, esi
0x14008281a  add     rsp, 38h
0x14008281e  pop     r15
0x140082820  pop     r12
0x140082822  pop     rdi
0x140082823  pop     rsi
0x140082824  pop     rbx
0x140082825  pop     rbp
0x140082826  retn
```
