# CMonitorEvents::TimerCallBack(void *,uchar)

- ea: `0x180004390`
- end: `0x1800048eb`
- name: `?TimerCallBack@CMonitorEvents@@SAXPEAXE@Z`
- size: `1371`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000403c`
- `0x180004390`
- `0x180004bf0`
- `0x180004c30`
- `0x180004ccc`
- `0x180005048`
- `0x18000a18c`
- `0x18000b648`
- `0x18000c744`
- `0x180012c34`
- `0x180016bf0`
- `0x18001d3a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004429`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004429`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004494`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004494`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004470`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004470`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004817`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004817`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180004634`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180004634`
- `wbemcomn!?Enter@CStaticCritSec@@QEAAXXZ` at `0x1800046c7`
- `wbemcomn!?Enter@CStaticCritSec@@QEAAXXZ` at `0x180004712`
- `wbemcomn!?Enter@CStaticCritSec@@QEAAXXZ` at `0x18000476d`
- `wbemcomn!?Enter@CStaticCritSec@@QEAAXXZ` at `0x1800046c7`
- `wbemcomn!?Enter@CStaticCritSec@@QEAAXXZ` at `0x180004712`
- `wbemcomn!?Enter@CStaticCritSec@@QEAAXXZ` at `0x18000476d`
- `wbemcomn!?Leave@CStaticCritSec@@QEAAXXZ` at `0x1800046d8`
- `wbemcomn!?Leave@CStaticCritSec@@QEAAXXZ` at `0x180004742`
- `wbemcomn!?Leave@CStaticCritSec@@QEAAXXZ` at `0x1800046d8`
- `wbemcomn!?Leave@CStaticCritSec@@QEAAXXZ` at `0x180004742`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CMonitorEvents::TimerCallBack(unsigned int *a1, char a2)
{
  __int64 v4; // rsi
  int v5; // r12d
  int v6; // r15d
  int v7; // r14d
  int v8; // r13d
  unsigned __int16 **v9; // rdx
  unsigned __int64 v10; // rcx
  __int64 v11; // rbx
  __int64 v12; // r14
  __int64 v13; // rcx
  const unsigned __int16 *v14; // r8
  __int64 v15; // rdx
  WCHAR *v16; // rax
  unsigned __int16 v17; // r9
  WCHAR *v18; // rcx
  __int64 v19; // rdx
  WCHAR *v20; // rax
  __int64 v21; // r8
  const wchar_t *v22; // rcx
  __int64 v23; // rbx
  WCHAR *v24; // rax
  wchar_t v25; // dx
  WCHAR *v26; // rcx
  unsigned int v27; // eax
  __int64 v28; // rdx
  __int64 v29; // r8
  unsigned int v30; // ebx
  _QWORD *v31; // rcx
  CStaticCritSec *v32; // rcx
  const unsigned __int16 *v33; // r8
  CStaticCritSec *v34; // rbx
  unsigned int i; // eax
  unsigned __int64 v36; // rcx
  HKEY v37; // rcx
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbData[2]; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD v42[4]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v43; // [rsp+60h] [rbp-A0h]
  __int64 v44; // [rsp+68h] [rbp-98h]
  __int64 v45; // [rsp+70h] [rbp-90h]
  int v46; // [rsp+78h] [rbp-88h]
  WCHAR CommandLine[64]; // [rsp+80h] [rbp-80h] BYREF

  if ( (unsigned int)GLOB_Monitor_IsRegistred() && a2 )
  {
    v4 = *((_QWORD *)a1 + 4);
    if ( a1[14] )
    {
      v5 = 1;
      v6 = 0;
      if ( a1[2] != 3 )
      {
        v7 = 1;
        v8 = 0;
        if ( !a1[2] )
        {
          hKey = 0;
          if ( RegOpenKeyExW(
                 HKEY_LOCAL_MACHINE,
                 L"SOFTWARE\\Microsoft\\WBEM\\PROVIDERS\\Performance",
                 0,
                 0x20019u,
                 &hKey) )
          {
            goto LABEL_11;
          }
          Type = 0;
          cbData[0] = 4;
          *(_DWORD *)Data = 0;
          if ( !RegQueryValueExW(hKey, L"Performance Refresh", 0, &Type, Data, cbData) && Type == 4 )
          {
            if ( *(_DWORD *)Data )
            {
              v6 = 1;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  21,
                  WPP_c9be8021473137ba96341d1ad3a34b20_Traceguids,
                  *(unsigned int *)Data);
              }
            }
          }
          RegCloseKey(hKey);
          if ( !v6 )
          {
LABEL_11:
            v45 = 0;
            v44 = 0;
            v43 = 0;
            v42[3] = 1;
            v42[0] = 0;
            v46 = 0;
            if ( (unsigned int)CWMIBinMof::BinaryMofsHaveChanged((CWMIBinMof *)v42) )
            {
              v6 = 1;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_c9be8021473137ba96341d1ad3a34b20_Traceguids);
              }
            }
            CWMIBinMof::~CWMIBinMof((CWMIBinMof *)v42);
          }
          v11 = *(unsigned int *)(v4 + 560);
          if ( (_DWORD)v11 != -1 )
          {
            *(_QWORD *)cbData = *(_QWORD *)(v4 + 568);
            *(_QWORD *)Data = 0;
            GetSystemTimeAsFileTime((LPFILETIME)Data);
            v10 = *(_QWORD *)cbData + 10000000 * v11;
            if ( v10 < *(_QWORD *)Data )
            {
              a1[3] = 0;
              v7 = 0;
            }
          }
          if ( !a1[2] && v7 )
          {
            v27 = DeltaDredge2(v10, v9);
            v30 = v27;
            if ( v27 )
            {
              if ( v27 == 1 )
              {
                a1[3] = 1;
              }
              else if ( v27 == 2 )
              {
                a1[3] = 0;
              }
              v31 = WPP_GLOBAL_Control;
            }
            else
            {
              v31 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_c9be8021473137ba96341d1ad3a34b20_Traceguids);
                v31 = WPP_GLOBAL_Control;
              }
              v5 = 0;
            }
            if ( v31 != &WPP_GLOBAL_Control && (*((_BYTE *)v31 + 28) & 1) != 0 && *((_BYTE *)v31 + 25) >= 5u )
              WPP_SF_dd(v31[2], v28, v29, v30, v5);
            if ( !v5 && !v6 )
            {
              CStaticCritSec::Enter((CStaticCritSec *)(v4 + 24));
              v32 = (CStaticCritSec *)(v4 + 24);
LABEL_50:
              a1[1] = 1;
              CStaticCritSec::Leave(v32);
LABEL_37:
              DeleteTimerQueueTimer(0, *((HANDLE *)a1 + 2), 0);
              *((_QWORD *)a1 + 2) = 0;
              a1[14] = 1;
              return;
            }
          }
        }
LABEL_16:
        v12 = 2147483646;
        v13 = 2147483646;
        v14 = L"wmiadap.exe ";
        v15 = 64;
        v16 = CommandLine;
        do
        {
          if ( !v13 )
            break;
          v17 = *v14;
          if ( !*v14 )
            break;
          ++v14;
          *v16++ = v17;
          --v13;
          --v15;
        }
        while ( v15 );
        v18 = v16 - 1;
        if ( v15 )
          v18 = v16;
        *v18 = 0;
        if ( v8 )
        {
          v33 = (const unsigned __int16 *)(&g_Strings)[a1[3]];
        }
        else
        {
          if ( v5 )
          {
            StringCchCatW(CommandLine, 0x40u, (const unsigned __int16 *)(&g_Strings)[a1[3]]);
            if ( v6 )
            {
              v19 = 64;
              v20 = CommandLine;
              do
              {
                if ( !*v20 )
                  break;
                ++v20;
                --v19;
              }
              while ( v19 );
              v21 = (64 - v19) & -(__int64)(v19 != 0);
              if ( v19 )
              {
                v22 = L" /R";
                v23 = 64 - v21;
                v24 = &CommandLine[v21];
                if ( 64 != v21 )
                {
                  do
                  {
                    if ( !v12 )
                      break;
                    v25 = *v22;
                    if ( !*v22 )
                      break;
                    ++v22;
                    *v24++ = v25;
                    --v12;
                    --v23;
                  }
                  while ( v23 );
                }
                v26 = v24 - 1;
                if ( v23 )
                  v26 = v24;
                *v26 = 0;
              }
            }
            goto LABEL_36;
          }
          if ( !v6 )
          {
LABEL_36:
            CMonitorEvents::CreateProcess_(CommandLine, (struct CMonitorEvents *)v4, (struct ResyncPerfTask *)a1);
            if ( dword_180032A90 )
            {
              if ( !v8 )
                _InterlockedIncrement(&dword_180032A88);
            }
            goto LABEL_37;
          }
          v33 = L"/R /T";
        }
        StringCchCatW(CommandLine, 0x40u, v33);
        goto LABEL_36;
      }
      v34 = (CStaticCritSec *)(v4 + 24);
      CStaticCritSec::Enter((CStaticCritSec *)(v4 + 24));
      for ( i = 0; i < 4; ++i )
      {
        if ( i != 3 )
        {
          v36 = (unsigned __int64)i << 6;
          if ( *(_QWORD *)(v36 + v4 + 312) )
            *(_DWORD *)(v36 + v4 + 352) = 0;
        }
      }
      CStaticCritSec::Leave((CStaticCritSec *)(v4 + 24));
      RegSetDWORD(v37, L"Software\\Microsoft\\WBEM\\CIMOM", L"ThrottleDrege", 0);
      if ( !*(_DWORD *)v4 )
      {
        v8 = 1;
        goto LABEL_16;
      }
      *(_DWORD *)(v4 + 4) = 1;
    }
    else
    {
      v34 = (CStaticCritSec *)(v4 + 24);
    }
    CStaticCritSec::Enter(v34);
    v32 = v34;
    goto LABEL_50;
  }
}

```

## disassembly

```asm
0x180004390  push    rbp
0x180004392  push    rbx
0x180004393  push    rsi
0x180004394  push    rdi
0x180004395  push    r12
0x180004397  push    r13
0x180004399  push    r14
0x18000439b  push    r15
0x18000439d  lea     rbp, [rsp-18h]
0x1800043a2  sub     rsp, 118h
0x1800043a9  mov     rax, cs:__security_cookie
0x1800043b0  xor     rax, rsp
0x1800043b3  mov     [rbp+50h+var_50], rax
0x1800043b7  mov     bl, dl
0x1800043b9  mov     rdi, rcx
0x1800043bc  call    ?GLOB_Monitor_IsRegistred@@YAHXZ; GLOB_Monitor_IsRegistred(void)
0x1800043c1  xor     r10d, r10d
0x1800043c4  test    eax, eax
0x1800043c6  jz      loc_180004645
0x1800043cc  test    bl, bl
0x1800043ce  jz      loc_180004645
0x1800043d4  mov     rsi, [rdi+20h]
0x1800043d8  cmp     [rdi+38h], r10d
0x1800043dc  jz      loc_180004705
0x1800043e2  lea     r12d, [r10+1]
0x1800043e6  mov     r15d, r10d
0x1800043e9  cmp     dword ptr [rdi+8], 3
0x1800043ed  jz      loc_18000470B
0x1800043f3  mov     r14d, r12d
0x1800043f6  mov     r13d, r10d
0x1800043f9  cmp     [rdi+8], r10d
0x1800043fd  jnz     loc_180004519
0x180004403  mov     [rsp+150h+hKey], r10
0x180004408  lea     rax, [rsp+150h+hKey]
0x18000440d  mov     [rsp+150h+phkResult], rax; phkResult
0x180004412  mov     r9d, 20019h; samDesired
0x180004418  xor     r8d, r8d; ulOptions
0x18000441b  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\WBEM\\PROVIDERS\\P"...
0x180004422  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180004429  call    cs:__imp_RegOpenKeyExW
0x18000442f  xor     r10d, r10d
0x180004432  test    eax, eax
0x180004434  jnz     short loc_1800044A2
0x180004436  mov     [rsp+150h+Type], r10d
0x18000443b  mov     [rsp+150h+cbData], 4
0x180004443  mov     dword ptr [rsp+150h+Data], r10d
0x180004448  lea     rax, [rsp+150h+cbData]
0x18000444d  mov     [rsp+150h+lpcbData], rax; lpcbData
0x180004452  lea     rax, [rsp+150h+Data]
0x180004457  mov     [rsp+150h+phkResult], rax; lpData
0x18000445c  lea     r9, [rsp+150h+Type]; lpType
0x180004461  xor     r8d, r8d; lpReserved
0x180004464  lea     rdx, aPerformanceRef; "Performance Refresh"
0x18000446b  mov     rcx, [rsp+150h+hKey]; hKey
0x180004470  call    cs:__imp_RegQueryValueExW
0x180004476  test    eax, eax
0x180004478  jnz     short loc_18000448F
0x18000447a  cmp     [rsp+150h+Type], 4
0x18000447f  jnz     short loc_18000448F
0x180004481  mov     r9d, dword ptr [rsp+150h+Data]
0x180004486  test    r9d, r9d
0x180004489  jnz     loc_180004783
0x18000448f  mov     rcx, [rsp+150h+hKey]; hKey
0x180004494  call    cs:__imp_RegCloseKey
0x18000449a  xor     r10d, r10d
0x18000449d  test    r15d, r15d
0x1800044a0  jnz     short loc_180004500
0x1800044a2  mov     [rsp+150h+var_E0], r10
0x1800044a7  mov     [rsp+150h+var_E8], r10
0x1800044ac  mov     [rsp+150h+var_F4], r10d
0x1800044b1  mov     [rsp+150h+var_F0], r10
0x1800044b6  mov     [rsp+150h+var_F4], 1
0x1800044be  mov     [rsp+150h+var_100], r10d
0x1800044c3  mov     [rsp+150h+var_D8], r10d
0x1800044c8  lea     rcx, [rsp+150h+var_100]; this
0x1800044cd  call    ?BinaryMofsHaveChanged@CWMIBinMof@@QEAAHXZ; CWMIBinMof::BinaryMofsHaveChanged(void)
0x1800044d2  test    eax, eax
0x1800044d4  jz      short loc_1800044F3
0x1800044d6  mov     r15d, 1
0x1800044dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800044e3  lea     rax, WPP_GLOBAL_Control
0x1800044ea  cmp     rcx, rax
0x1800044ed  jnz     loc_1800047CB
0x1800044f3  lea     rcx, [rsp+150h+var_100]; this
0x1800044f8  call    ??1CWMIBinMof@@QEAA@XZ; CWMIBinMof::~CWMIBinMof(void)
0x1800044fd  xor     r10d, r10d
0x180004500  mov     ebx, [rsi+230h]
0x180004506  cmp     ebx, 0FFFFFFFFh
0x180004509  jnz     loc_1800047F9
0x18000450f  cmp     [rdi+8], r10d
0x180004513  jz      loc_180004665
0x180004519  mov     r14d, 7FFFFFFEh
0x18000451f  mov     ecx, r14d
0x180004522  lea     r8, aWmiadapExe; "wmiadap.exe "
0x180004529  mov     ebx, 40h ; '@'
0x18000452e  mov     edx, ebx
0x180004530  lea     rax, [rbp+50h+CommandLine]
0x180004534  test    rcx, rcx
0x180004537  jz      short loc_180004558
0x180004539  movzx   r9d, word ptr [r8]
0x18000453d  test    r9w, r9w
0x180004541  jz      short loc_180004558
0x180004543  add     r8, 2
0x180004547  mov     [rax], r9w
0x18000454b  add     rax, 2
0x18000454f  dec     rcx
0x180004552  sub     rdx, 1
0x180004556  jnz     short loc_180004534
0x180004558  lea     rcx, [rax-2]
0x18000455c  test    rdx, rdx
0x18000455f  cmovnz  rcx, rax
0x180004563  mov     [rcx], r10w
0x180004567  test    r13d, r13d
0x18000456a  jnz     loc_1800046E5
0x180004570  test    r12d, r12d
0x180004573  jz      loc_1800048C1
0x180004579  mov     r8d, [rdi+0Ch]
0x18000457d  lea     rax, ?g_Strings@@3PAPEAGA; ushort * near * g_Strings
0x180004584  mov     rdx, rbx; unsigned __int64
0x180004587  lea     rcx, [rbp+50h+CommandLine]; unsigned __int16 *
0x18000458b  mov     r8, [rax+r8*8]; unsigned __int16 *
0x18000458f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004594  test    r15d, r15d
0x180004597  jz      short loc_18000460E
0x180004599  mov     rdx, rbx
0x18000459c  lea     rax, [rbp+50h+CommandLine]
0x1800045a0  xor     r9d, r9d
0x1800045a3  cmp     [rax], r9w
0x1800045a7  jz      short loc_1800045B3
0x1800045a9  add     rax, 2
0x1800045ad  sub     rdx, 1
0x1800045b1  jnz     short loc_1800045A3
0x1800045b3  mov     rax, rdx
0x1800045b6  mov     rcx, rbx
0x1800045b9  sub     rcx, rdx
0x1800045bc  neg     rax
0x1800045bf  sbb     r8, r8
0x1800045c2  and     r8, rcx
0x1800045c5  test    rdx, rdx
0x1800045c8  jz      short loc_18000460E
0x1800045ca  lea     rcx, aR; " /R"
0x1800045d1  sub     rbx, r8
0x1800045d4  lea     rax, [rbp+50h+CommandLine]
0x1800045d8  lea     rax, [rax+r8*2]
0x1800045dc  jz      short loc_1800045FF
0x1800045de  test    r14, r14
0x1800045e1  jz      short loc_1800045FF
0x1800045e3  movzx   edx, word ptr [rcx]
0x1800045e6  test    dx, dx
0x1800045e9  jz      short loc_1800045FF
0x1800045eb  add     rcx, 2
0x1800045ef  mov     [rax], dx
0x1800045f2  add     rax, 2
0x1800045f6  dec     r14
0x1800045f9  sub     rbx, 1
0x1800045fd  jnz     short loc_1800045DE
0x1800045ff  lea     rcx, [rax-2]
0x180004603  test    rbx, rbx
0x180004606  cmovnz  rcx, rax
0x18000460a  mov     [rcx], r9w
0x18000460e  mov     r8, rdi; struct ResyncPerfTask *
0x180004611  mov     rdx, rsi; struct CMonitorEvents *
0x180004614  lea     rcx, [rbp+50h+CommandLine]; lpCommandLine
0x180004618  call    ?CreateProcess_@CMonitorEvents@@SAHPEAGPEAV1@PEAVResyncPerfTask@@@Z; CMonitorEvents::CreateProcess_(ushort *,CMonitorEvents *,ResyncPerfTask *)
0x18000461d  xor     ebx, ebx
0x18000461f  cmp     cs:dword_180032A90, ebx
0x180004625  jnz     loc_1800048D6
0x18000462b  xor     r8d, r8d; CompletionEvent
0x18000462e  mov     rdx, [rdi+10h]; Timer
0x180004632  xor     ecx, ecx; TimerQueue
0x180004634  call    cs:__imp_DeleteTimerQueueTimer
0x18000463a  mov     [rdi+10h], rbx
0x18000463e  mov     dword ptr [rdi+38h], 1
0x180004645  mov     rcx, [rbp+50h+var_50]
0x180004649  xor     rcx, rsp; StackCookie
0x18000464c  call    __security_check_cookie
0x180004651  add     rsp, 118h
0x180004658  pop     r15
0x18000465a  pop     r14
0x18000465c  pop     r13
0x18000465e  pop     r12
0x180004660  pop     rdi
0x180004661  pop     rsi
0x180004662  pop     rbx
0x180004663  pop     rbp
0x180004664  retn
0x180004665  test    r14d, r14d
0x180004668  jz      loc_180004519
0x18000466e  call    ?DeltaDredge2@@YAKKPEAPEAG@Z; DeltaDredge2(ulong,ushort * *)
0x180004673  mov     ebx, eax
0x180004675  mov     ecx, eax
0x180004677  xor     r10d, r10d
0x18000467a  test    eax, eax
0x18000467c  jz      loc_180004858
0x180004682  sub     ecx, 1
0x180004685  jz      loc_18000484C
0x18000468b  cmp     ecx, 1
0x18000468e  jz      loc_180004843
0x180004694  mov     rcx, cs:WPP_GLOBAL_Control
0x18000469b  lea     rax, WPP_GLOBAL_Control
0x1800046a2  cmp     rcx, rax
0x1800046a5  jz      short loc_1800046B1
0x1800046a7  test    byte ptr [rcx+1Ch], 1
0x1800046ab  jnz     loc_18000489E
0x1800046b1  test    r12d, r12d
0x1800046b4  jnz     loc_180004519
0x1800046ba  test    r15d, r15d
0x1800046bd  jnz     loc_180004519
0x1800046c3  lea     rcx, [rsi+18h]
0x1800046c7  call    cs:__imp_?Enter@CStaticCritSec@@QEAAXXZ; CStaticCritSec::Enter(void)
0x1800046cd  lea     rcx, [rsi+18h]
0x1800046d1  mov     dword ptr [rdi+4], 1
0x1800046d8  call    cs:__imp_?Leave@CStaticCritSec@@QEAAXXZ; CStaticCritSec::Leave(void)
0x1800046de  xor     ebx, ebx
0x1800046e0  jmp     loc_18000462B
0x1800046e5  mov     r8d, [rdi+0Ch]
0x1800046e9  lea     rax, ?g_Strings@@3PAPEAGA; ushort * near * g_Strings
0x1800046f0  mov     r8, [rax+r8*8]; unsigned __int16 *
0x1800046f4  mov     rdx, rbx; unsigned __int64
0x1800046f7  lea     rcx, [rbp+50h+CommandLine]; unsigned __int16 *
0x1800046fb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004700  jmp     loc_18000460E
0x180004705  lea     rbx, [rsi+18h]
0x180004709  jmp     short loc_18000476A
0x18000470b  lea     rbx, [rsi+18h]
0x18000470f  mov     rcx, rbx
0x180004712  call    cs:__imp_?Enter@CStaticCritSec@@QEAAXXZ; CStaticCritSec::Enter(void)
0x180004718  xor     edx, edx
0x18000471a  mov     eax, edx
0x18000471c  cmp     eax, 3
0x18000471f  jz      short loc_180004738
0x180004721  mov     ecx, eax
0x180004723  shl     rcx, 6
0x180004727  cmp     [rcx+rsi+138h], rdx
0x18000472f  jz      short loc_180004738
0x180004731  mov     [rcx+rsi+160h], edx
0x180004738  inc     eax
0x18000473a  cmp     eax, 4
0x18000473d  jb      short loc_18000471C
0x18000473f  mov     rcx, rbx
0x180004742  call    cs:__imp_?Leave@CStaticCritSec@@QEAAXXZ; CStaticCritSec::Leave(void)
0x180004748  xor     r9d, r9d; unsigned int
0x18000474b  lea     r8, aThrottledrege; "ThrottleDrege"
0x180004752  lea     rdx, SubKey; "Software\\Microsoft\\WBEM\\CIMOM"
0x180004759  call    ?RegSetDWORD@@YAKPEAUHKEY__@@PEBG1K@Z; RegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18000475e  xor     r10d, r10d
0x180004761  cmp     [rsi], r10d
0x180004764  jz      short loc_18000477B
0x180004766  mov     [rsi+4], r12d
0x18000476a  mov     rcx, rbx
0x18000476d  call    cs:__imp_?Enter@CStaticCritSec@@QEAAXXZ; CStaticCritSec::Enter(void)
0x180004773  mov     rcx, rbx
0x180004776  jmp     loc_1800046D1
0x18000477b  mov     r13d, r12d
0x18000477e  jmp     loc_180004519
0x180004783  mov     r15d, r12d
0x180004786  mov     rcx, cs:WPP_GLOBAL_Control
0x18000478d  lea     rax, WPP_GLOBAL_Control
0x180004794  cmp     rcx, rax
0x180004797  jz      loc_18000448F
0x18000479d  test    [rcx+1Ch], r12b
0x1800047a1  jz      loc_18000448F
0x1800047a7  cmp     byte ptr [rcx+19h], 5
0x1800047ab  jb      loc_18000448F
0x1800047b1  mov     edx, 15h
0x1800047b6  lea     r8, WPP_c9be8021473137ba96341d1ad3a34b20_Traceguids
0x1800047bd  mov     rcx, [rcx+10h]
0x1800047c1  call    WPP_SF_d
0x1800047c6  jmp     loc_18000448F
0x1800047cb  test    [rcx+1Ch], r15b
0x1800047cf  jz      loc_1800044F3
0x1800047d5  cmp     byte ptr [rcx+19h], 5
0x1800047d9  jb      loc_1800044F3
0x1800047df  mov     edx, 16h
0x1800047e4  lea     r8, WPP_c9be8021473137ba96341d1ad3a34b20_Traceguids
0x1800047eb  mov     rcx, [rcx+10h]
0x1800047ef  call    WPP_SF_
0x1800047f4  jmp     loc_1800044F3
0x1800047f9  mov     eax, [rsi+238h]
0x1800047ff  mov     [rsp+150h+cbData], eax
0x180004803  mov     eax, [rsi+23Ch]
0x180004809  mov     [rsp+150h+cbData+4], eax
0x18000480d  mov     qword ptr [rsp+150h+Data], r10
0x180004812  lea     rcx, [rsp+150h+Data]; lpSystemTimeAsFileTime
0x180004817  call    cs:__imp_GetSystemTimeAsFileTime
0x18000481d  imul    rcx, rbx, 989680h
0x180004824  add     rcx, qword ptr [rsp+150h+cbData]
0x180004829  xor     r10d, r10d
0x18000482c  cmp     rcx, qword ptr [rsp+150h+Data]
0x180004831  jnb     loc_18000450F
0x180004837  mov     [rdi+0Ch], r10d
0x18000483b  mov     r14d, r10d
0x18000483e  jmp     loc_18000450F
0x180004843  mov     [rdi+0Ch], r10d
0x180004847  jmp     loc_180004694
0x18000484c  mov     dword ptr [rdi+0Ch], 1
0x180004853  jmp     loc_180004694
0x180004858  mov     rcx, cs:WPP_GLOBAL_Control
0x18000485f  lea     rax, WPP_GLOBAL_Control
0x180004866  cmp     rcx, rax
  ... truncated ...
```
