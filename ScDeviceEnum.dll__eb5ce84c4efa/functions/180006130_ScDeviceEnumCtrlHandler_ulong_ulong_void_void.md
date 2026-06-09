# ScDeviceEnumCtrlHandler(ulong,ulong,void *,void *)

- ea: `0x180006130`
- end: `0x1800064bb`
- name: `?ScDeviceEnumCtrlHandler@@YAKKKPEAX0@Z`
- size: `907`
- prototype: `__int64 __fastcall(DWORD dwControl, __int64 dwEventType, _DWORD *lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180005e4c`
- `0x180005ebc`
- `0x180006130`
- `0x180006d40`
- `0x180007178`
- `0x1800071d4`
- `0x180007248`
- `0x18000b4a0`
- `0x18000bb00`
- `0x18001e020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180006482`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180006482`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006454`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006454`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180006423`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180006423`

## pseudocode

```c
__int64 __fastcall ScDeviceEnumCtrlHandler(DWORD dwControl, __int64 dwEventType, _DWORD *lpEventData, LPVOID lpContext)
{
  int v5; // ebx
  __int64 v7; // rcx
  DWORD v8; // edi
  DWORD v9; // edi
  DWORD v10; // edi
  __int64 v11; // rcx
  __int64 v12; // rcx
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  unsigned int v15; // edi
  int v16; // ebx
  int v17; // ebx
  int v18; // ebx
  int v19; // ebx
  int v20; // ebx
  __int64 v21; // rcx
  __int64 v22; // rcx
  char LastError; // al
  unsigned int v24; // ebx
  int v26; // [rsp+30h] [rbp-29h] BYREF
  int v27; // [rsp+34h] [rbp-25h] BYREF
  _QWORD *v28; // [rsp+38h] [rbp-21h] BYREF
  _QWORD v29[3]; // [rsp+40h] [rbp-19h] BYREF
  char v30[24]; // [rsp+58h] [rbp-1h] BYREF

  v5 = dwEventType;
  v26 = 0;
  v27 = 0;
  strcpy(v30, "ScDeviceEnumCtrlHandler");
  v29[0] = v30;
  v29[1] = &v27;
  v29[2] = &v26;
  lambda_01ec98b1403357bd946ca82d9f7dc2d4_::operator()(v29, dwEventType, lpEventData, lpContext);
  v27 = 1;
  v28 = v29;
  WppTraceIndent(v7, 2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      (unsigned int)&WPP_cc5e31c4c3a13497f43cc016dcb7f87d_Traceguids,
      (_DWORD)WPP_pszIndent,
      dwControl);
  }
  v8 = dwControl - 1;
  if ( v8 )
  {
    v9 = v8 - 3;
    if ( !v9 )
      goto LABEL_45;
    v10 = v9 - 10;
    if ( v10 )
    {
      if ( v10 == 18 )
      {
        _m_prefetchw(&qword_18002BD40);
        if ( (_InterlockedOr64(&qword_18002BD40, 2u) & 1) != 0 )
        {
          WppTraceIndent(v11, 2);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              24,
              &WPP_cc5e31c4c3a13497f43cc016dcb7f87d_Traceguids,
              WPP_pszIndent);
          }
          v26 = 1115;
        }
      }
      else
      {
        v26 = 120;
      }
      goto LABEL_45;
    }
    _m_prefetchw(&qword_18002BD40);
    if ( (_InterlockedOr64(&qword_18002BD40, 2u) & 1) != 0 )
    {
      WppTraceIndent(v12, 2);
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_45;
      }
      v14 = 22;
      goto LABEL_38;
    }
    v15 = lpEventData[1];
    WppTraceIndent(v12, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_sdd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        (unsigned int)&WPP_cc5e31c4c3a13497f43cc016dcb7f87d_Traceguids,
        (_DWORD)WPP_pszIndent,
        v5,
        v15);
    }
    v16 = v5 - 1;
    if ( v16 )
    {
      v17 = v16 - 1;
      if ( !v17 )
        goto LABEL_31;
      v18 = v17 - 1;
      if ( v18 )
      {
        v19 = v18 - 1;
        if ( !v19 )
          goto LABEL_31;
        v20 = v19 - 1;
        if ( v20 )
        {
          if ( v20 != 1 )
            goto LABEL_45;
LABEL_31:
          CSessionManager::Remove(v15);
          goto LABEL_45;
        }
      }
    }
    CSessionManager::Add(v15);
    goto LABEL_45;
  }
  _m_prefetchw(&qword_18002BD40);
  if ( (_InterlockedOr64(&qword_18002BD40, 3u) & 1) != 0 )
  {
    WppTraceIndent(v21, 2);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      goto LABEL_45;
    }
    v14 = 20;
LABEL_38:
    WPP_SF_s(v13[2], v14, &WPP_cc5e31c4c3a13497f43cc016dcb7f87d_Traceguids, WPP_pszIndent);
    goto LABEL_45;
  }
  *(_QWORD *)&ServiceStatus.dwCurrentState = 3;
  ServiceStatus.dwCheckPoint = 0;
  ServiceStatus.dwWaitHint = 1000;
  ServiceStatus.dwWin32ExitCode = 0;
  if ( !SetServiceStatus(hServiceStatus, &ServiceStatus) )
  {
    WppTraceIndent(v22, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        (unsigned int)&WPP_cc5e31c4c3a13497f43cc016dcb7f87d_Traceguids,
        (_DWORD)WPP_pszIndent,
        LastError);
    }
  }
  SetEvent(hObject);
LABEL_45:
  _InterlockedAnd64(&qword_18002BD40, 0xFFFFFFFFFFFFFFFDuLL);
  v24 = v26;
  WppTraceUnwinder__lambda_01ec98b1403357bd946ca82d9f7dc2d4____::_WppTraceUnwinder__lambda_01ec98b1403357bd946ca82d9f7dc2d4____(&v28);
  return v24;
}

```

## disassembly

```asm
0x180006130  push    rbp
0x180006132  push    rbx
0x180006133  push    rsi
0x180006134  push    rdi
0x180006135  push    r12
0x180006137  push    r15
0x180006139  lea     rbp, [rsp-2Fh]
0x18000613e  sub     rsp, 88h
0x180006145  mov     rax, cs:__security_cookie
0x18000614c  xor     rax, rsp
0x18000614f  mov     [rbp+57h+var_40], rax
0x180006153  mov     rsi, r8
0x180006156  mov     ebx, edx
0x180006158  mov     edi, ecx
0x18000615a  mov     [rbp+57h+var_80], 0
0x180006161  mov     [rbp+57h+var_7C], 0
0x180006168  movups  xmm0, xmmword ptr cs:aScdeviceenumct; "ScDeviceEnumCtrlHandler"
0x18000616f  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x180006173  movsd   xmm1, qword ptr cs:aScdeviceenumct+10h; "Handler"
0x18000617b  movsd   qword ptr [rbp+57h+var_58+10h], xmm1
0x180006180  lea     rax, [rbp+57h+var_58]
0x180006184  mov     [rbp+57h+var_70], rax
0x180006188  lea     rax, [rbp+57h+var_7C]
0x18000618c  mov     [rbp+57h+var_68], rax
0x180006190  lea     rax, [rbp+57h+var_80]
0x180006194  mov     [rbp+57h+var_60], rax
0x180006198  lea     rcx, [rbp+57h+var_70]
0x18000619c  call    _lambda_01ec98b1403357bd946ca82d9f7dc2d4___operator__
0x1800061a1  mov     [rbp+57h+var_7C], 1
0x1800061a8  lea     rax, [rbp+57h+var_70]
0x1800061ac  mov     [rbp+57h+var_78], rax
0x1800061b0  mov     r15d, 2
0x1800061b6  mov     edx, r15d
0x1800061b9  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800061be  lea     rax, WPP_GLOBAL_Control
0x1800061c5  lea     r12, WPP_cc5e31c4c3a13497f43cc016dcb7f87d_Traceguids
0x1800061cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800061d3  cmp     rcx, rax
0x1800061d6  jz      short loc_1800061FF
0x1800061d8  test    byte ptr [rcx+1Ch], 1
0x1800061dc  jz      short loc_1800061FF
0x1800061de  cmp     byte ptr [rcx+19h], 4
0x1800061e2  jb      short loc_1800061FF
0x1800061e4  lea     edx, [r15+11h]
0x1800061e8  mov     [rsp+0B0h+var_90], edi
0x1800061ec  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800061f3  mov     r8, r12
0x1800061f6  mov     rcx, [rcx+10h]
0x1800061fa  call    WPP_SF_sd
0x1800061ff  sub     edi, 1
0x180006202  jz      loc_18000637E
0x180006208  sub     edi, 3
0x18000620b  jz      loc_180006488
0x180006211  sub     edi, 0Ah
0x180006214  jz      loc_18000629D
0x18000621a  cmp     edi, 12h
0x18000621d  jz      short loc_18000622B
0x18000621f  mov     [rbp+57h+var_80], 78h ; 'x'
0x180006226  jmp     loc_180006488
0x18000622b  prefetchw byte ptr cs:qword_18002BD40
0x180006232  mov     rax, cs:qword_18002BD40
0x180006239  mov     rcx, rax
0x18000623c  or      rcx, r15
0x18000623f  lock cmpxchg cs:qword_18002BD40, rcx
0x180006248  jnz     short loc_180006239
0x18000624a  test    al, 1
0x18000624c  jz      loc_180006488
0x180006252  mov     edx, r15d
0x180006255  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000625a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006261  lea     rdx, WPP_GLOBAL_Control
0x180006268  cmp     rcx, rdx
0x18000626b  jz      short loc_180006291
0x18000626d  test    byte ptr [rcx+1Ch], 1
0x180006271  jz      short loc_180006291
0x180006273  cmp     byte ptr [rcx+19h], 4
0x180006277  jb      short loc_180006291
0x180006279  mov     edx, 18h
0x18000627e  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180006285  mov     r8, r12
0x180006288  mov     rcx, [rcx+10h]
0x18000628c  call    WPP_SF_s
0x180006291  mov     [rbp+57h+var_80], 45Bh
0x180006298  jmp     loc_180006488
0x18000629d  prefetchw byte ptr cs:qword_18002BD40
0x1800062a4  mov     rax, cs:qword_18002BD40
0x1800062ab  mov     rcx, rax
0x1800062ae  or      rcx, r15
0x1800062b1  lock cmpxchg cs:qword_18002BD40, rcx
0x1800062ba  jnz     short loc_1800062AB
0x1800062bc  mov     edx, r15d
0x1800062bf  test    al, 1
0x1800062c1  jz      short loc_1800062FD
0x1800062c3  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800062c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800062cf  lea     rdx, WPP_GLOBAL_Control
0x1800062d6  cmp     rcx, rdx
0x1800062d9  jz      loc_180006488
0x1800062df  test    byte ptr [rcx+1Ch], 1
0x1800062e3  jz      loc_180006488
0x1800062e9  cmp     byte ptr [rcx+19h], 4
0x1800062ed  jb      loc_180006488
0x1800062f3  mov     edx, 16h
0x1800062f8  jmp     loc_1800063DA
0x1800062fd  mov     edi, [rsi+4]
0x180006300  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180006305  mov     rcx, cs:WPP_GLOBAL_Control
0x18000630c  lea     rdx, WPP_GLOBAL_Control
0x180006313  cmp     rcx, rdx
0x180006316  jz      short loc_180006344
0x180006318  test    byte ptr [rcx+1Ch], 1
0x18000631c  jz      short loc_180006344
0x18000631e  cmp     byte ptr [rcx+19h], 4
0x180006322  jb      short loc_180006344
0x180006324  mov     edx, 17h
0x180006329  mov     [rsp+0B0h+var_88], edi
0x18000632d  mov     [rsp+0B0h+var_90], ebx
0x180006331  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180006338  mov     r8, r12
0x18000633b  mov     rcx, [rcx+10h]
0x18000633f  call    WPP_SF_sdd
0x180006344  sub     ebx, 1
0x180006347  jz      short loc_180006372
0x180006349  sub     ebx, 1
0x18000634c  jz      short loc_180006366
0x18000634e  sub     ebx, 1
0x180006351  jz      short loc_180006372
0x180006353  sub     ebx, 1
0x180006356  jz      short loc_180006366
0x180006358  sub     ebx, 1
0x18000635b  jz      short loc_180006372
0x18000635d  cmp     ebx, 1
0x180006360  jnz     loc_180006488
0x180006366  mov     ecx, edi; unsigned int
0x180006368  call    ?Remove@CSessionManager@@SAJK@Z; CSessionManager::Remove(ulong)
0x18000636d  jmp     loc_180006488
0x180006372  mov     ecx, edi; unsigned int
0x180006374  call    ?Add@CSessionManager@@SAJK@Z; CSessionManager::Add(ulong)
0x180006379  jmp     loc_180006488
0x18000637e  prefetchw byte ptr cs:qword_18002BD40
0x180006385  mov     rax, cs:qword_18002BD40
0x18000638c  mov     rcx, rax
0x18000638f  or      rcx, 3
0x180006393  lock cmpxchg cs:qword_18002BD40, rcx
0x18000639c  jnz     short loc_18000638C
0x18000639e  test    al, 1
0x1800063a0  jz      short loc_1800063F2
0x1800063a2  mov     edx, r15d
0x1800063a5  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800063aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800063b1  lea     rdx, WPP_GLOBAL_Control
0x1800063b8  cmp     rcx, rdx
0x1800063bb  jz      loc_180006488
0x1800063c1  test    byte ptr [rcx+1Ch], 1
0x1800063c5  jz      loc_180006488
0x1800063cb  cmp     byte ptr [rcx+19h], 4
0x1800063cf  jb      loc_180006488
0x1800063d5  mov     edx, 14h
0x1800063da  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800063e1  mov     r8, r12
0x1800063e4  mov     rcx, [rcx+10h]
0x1800063e8  call    WPP_SF_s
0x1800063ed  jmp     loc_180006488
0x1800063f2  mov     qword ptr cs:ServiceStatus.dwCurrentState, 3
0x1800063fd  xor     ebx, ebx
0x1800063ff  mov     cs:ServiceStatus.dwCheckPoint, ebx
0x180006405  mov     cs:ServiceStatus.dwWaitHint, 3E8h
0x18000640f  mov     cs:ServiceStatus.dwWin32ExitCode, ebx
0x180006415  lea     rdx, ServiceStatus; lpServiceStatus
0x18000641c  mov     rcx, qword ptr cs:hServiceStatus; hServiceStatus
0x180006423  call    cs:__imp_SetServiceStatus
0x180006429  test    eax, eax
0x18000642b  jnz     short loc_18000647B
0x18000642d  mov     edx, r15d
0x180006430  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180006435  mov     rax, cs:WPP_GLOBAL_Control
0x18000643c  lea     rdx, WPP_GLOBAL_Control
0x180006443  cmp     rax, rdx
0x180006446  jz      short loc_18000647B
0x180006448  test    byte ptr [rax+1Ch], 1
0x18000644c  jz      short loc_18000647B
0x18000644e  cmp     [rax+19h], r15b
0x180006452  jb      short loc_18000647B
0x180006454  call    cs:__imp_GetLastError
0x18000645a  lea     edx, [rbx+15h]
0x18000645d  mov     [rsp+0B0h+var_90], eax
0x180006461  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180006468  mov     r8, r12
0x18000646b  mov     rcx, cs:WPP_GLOBAL_Control
0x180006472  mov     rcx, [rcx+10h]
0x180006476  call    WPP_SF_sd
0x18000647b  mov     rcx, cs:hObject; hEvent
0x180006482  call    cs:__imp_SetEvent
0x180006488  lock and cs:qword_18002BD40, 0FFFFFFFFFFFFFFFDh
0x180006491  mov     ebx, [rbp+57h+var_80]
0x180006494  lea     rcx, [rbp+57h+var_78]
0x180006498  call    WppTraceUnwinder__lambda_01ec98b1403357bd946ca82d9f7dc2d4_______WppTraceUnwinder__lambda_01ec98b1403357bd946ca82d9f7dc2d4____
0x18000649d  mov     eax, ebx
0x18000649f  mov     rcx, [rbp+57h+var_40]
0x1800064a3  xor     rcx, rsp; StackCookie
0x1800064a6  call    __security_check_cookie
0x1800064ab  add     rsp, 88h
0x1800064b2  pop     r15
0x1800064b4  pop     r12
0x1800064b6  pop     rdi
0x1800064b7  pop     rsi
0x1800064b8  pop     rbx
0x1800064b9  pop     rbp
0x1800064ba  retn
```
