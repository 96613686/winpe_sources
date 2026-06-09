# WfpServiceHandlerEx

- ea: `0x180038740`
- end: `0x180038931`
- name: `WfpServiceHandlerEx`
- size: `497`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18001236c`
- `0x180012b54`
- `0x180018b74`
- `0x180038740`
- `0x180038938`
- `0x180038b74`
- `0x18004472c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18008a35f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18008a35f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a36d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a36d`

## string_xrefs

- `0x18003882a`: `WfpComponentsDispatchForward`
- `0x18003886c`: `WfpServiceHandlerEx`
- `0x180038883`: `WfpServiceHandlerEx`

## pseudocode

```c
__int64 __fastcall WfpServiceHandlerEx(__int64 dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)
{
  unsigned int v6; // ebx
  int v7; // ecx
  int v8; // ecx
  __int64 v9; // rcx
  __int64 v10; // rbp
  __int64 v11; // rax
  __int64 result; // rax
  unsigned int v13; // eax
  __int64 LastError; // r8
  const char *v15; // rdx

  if ( !lpContext )
  {
    v13 = WfpReportSysErrorAsNtStatus(dwControl, "WfpServiceHandlerEx", 3221225485LL);
LABEL_22:
    v6 = v13;
    goto LABEL_15;
  }
  v6 = 0;
  v7 = dwControl - 1;
  if ( !v7 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        (unsigned int)WPP_afd810515d1c3db64468bc5743bd872b_Traceguids,
        0,
        *(_QWORD *)lpContext);
    }
    *((_DWORD *)lpContext + 15) = 1;
    goto LABEL_34;
  }
  v8 = v7 - 3;
  if ( !v8 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        (unsigned int)WPP_afd810515d1c3db64468bc5743bd872b_Traceguids,
        0,
        *(_QWORD *)lpContext);
    }
    goto LABEL_15;
  }
  v9 = (unsigned int)(v8 - 1);
  if ( !(_DWORD)v9 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        (unsigned int)WPP_afd810515d1c3db64468bc5743bd872b_Traceguids,
        0,
        *(_QWORD *)lpContext);
    }
    *((_DWORD *)lpContext + 15) = 2;
LABEL_34:
    WfpServiceChangeState(lpContext, 3);
    if ( SetEvent(*((HANDLE *)lpContext + 8)) )
      goto LABEL_15;
    LastError = GetLastError();
    v15 = "SetEvent";
    goto LABEL_36;
  }
  if ( (_DWORD)v9 != 8 )
  {
    LastError = 120;
    v15 = "WfpServiceHandlerEx";
LABEL_36:
    v13 = WfpReportSysErrorAsWinError(v9, v15, LastError);
    goto LABEL_22;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      (unsigned int)WPP_afd810515d1c3db64468bc5743bd872b_Traceguids,
      0,
      *(_QWORD *)lpContext);
  }
  v10 = 0;
  if ( *((_QWORD *)lpContext + 2) )
  {
    while ( 1 )
    {
      v11 = WfpComponentDispatch(*((_QWORD *)lpContext + 1) + 16 * v10, 3, dwEventType);
      v6 = v11;
      if ( v11 )
        break;
      if ( (unsigned __int64)++v10 >= *((_QWORD *)lpContext + 2) )
        goto LABEL_15;
    }
    WfpReportError(v11, "WfpComponentsDispatchForward");
  }
LABEL_15:
  result = (unsigned __int16)v6;
  if ( (v6 & 0x1FFF0000) != 0x70000 )
    return v6;
  return result;
}

```

## disassembly

```asm
0x180038740  push    rbx
0x180038742  push    rbp
0x180038743  push    rdi
0x180038744  push    r14
0x180038746  sub     rsp, 38h
0x18003874a  mov     rdi, r9
0x18003874d  mov     r14d, edx
0x180038750  test    r9, r9
0x180038753  jz      loc_180038866
0x180038759  xor     ebx, ebx
0x18003875b  sub     ecx, 1
0x18003875e  jz      loc_1800388E0
0x180038764  sub     ecx, 3
0x180038767  jnz     short loc_1800387B0
0x180038769  mov     rcx, cs:WPP_GLOBAL_Control
0x180038770  lea     rax, WPP_GLOBAL_Control
0x180038777  cmp     rcx, rax
0x18003877a  jz      loc_18003880C
0x180038780  cmp     byte ptr [rcx+19h], 3
0x180038784  jb      loc_18003880C
0x18003878a  test    byte ptr [rcx+1Ch], 1
0x18003878e  jz      short loc_18003880C
0x180038790  mov     rax, [r9]
0x180038793  lea     edx, [rbx+0Fh]
0x180038796  mov     rcx, [rcx+10h]
0x18003879a  lea     r8, WPP_afd810515d1c3db64468bc5743bd872b_Traceguids
0x1800387a1  xor     r9d, r9d
0x1800387a4  mov     [rsp+58h+var_38], rax
0x1800387a9  call    WPP_SF_SS
0x1800387ae  jmp     short loc_18003880C
0x1800387b0  sub     ecx, 1
0x1800387b3  jz      loc_18003888F
0x1800387b9  cmp     ecx, 8
0x1800387bc  jnz     loc_18003887D
0x1800387c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800387c9  lea     rax, WPP_GLOBAL_Control
0x1800387d0  cmp     rcx, rax
0x1800387d3  jz      short loc_1800387DB
0x1800387d5  cmp     byte ptr [rcx+19h], 3
0x1800387d9  jnb     short loc_18003883B
0x1800387db  xor     ebp, ebp
0x1800387dd  cmp     [rdi+10h], rbx
0x1800387e1  jbe     short loc_18003880C
0x1800387e3  mov     rcx, rbp
0x1800387e6  mov     r8d, r14d
0x1800387e9  shl     rcx, 4
0x1800387ed  mov     edx, 3
0x1800387f2  add     rcx, [rdi+8]
0x1800387f6  call    WfpComponentDispatch
0x1800387fb  mov     rbx, rax
0x1800387fe  test    rax, rax
0x180038801  jnz     short loc_18003882A
0x180038803  inc     rbp
0x180038806  cmp     rbp, [rdi+10h]
0x18003880a  jb      short loc_1800387E3
0x18003880c  mov     ecx, ebx
0x18003880e  movzx   eax, bx
0x180038811  and     ecx, 1FFF0000h
0x180038817  cmp     ecx, 70000h
0x18003881d  cmovnz  eax, ebx
0x180038820  add     rsp, 38h
0x180038824  pop     r14
0x180038826  pop     rdi
0x180038827  pop     rbp
0x180038828  pop     rbx
0x180038829  retn
0x18003882a  lea     rdx, aWfpcomponentsd; "WfpComponentsDispatchForward"
0x180038831  mov     rcx, rax
0x180038834  call    WfpReportError
0x180038839  jmp     short loc_18003880C
0x18003883b  test    byte ptr [rcx+1Ch], 1
0x18003883f  jz      short loc_1800387DB
0x180038841  mov     rax, [r9]
0x180038844  lea     r8, WPP_afd810515d1c3db64468bc5743bd872b_Traceguids
0x18003884b  mov     rcx, [rcx+10h]
0x18003884f  xor     r9d, r9d
0x180038852  mov     edx, 10h
0x180038857  mov     [rsp+58h+var_38], rax
0x18003885c  call    WPP_SF_SS
0x180038861  jmp     loc_1800387DB
0x180038866  mov     r8d, 0C000000Dh
0x18003886c  lea     rdx, aWfpservicehand; "WfpServiceHandlerEx"
0x180038873  call    WfpReportSysErrorAsNtStatus
0x180038878  mov     rbx, rax
0x18003887b  jmp     short loc_18003880C
0x18003887d  mov     r8d, 78h ; 'x'
0x180038883  lea     rdx, aWfpservicehand; "WfpServiceHandlerEx"
0x18003888a  jmp     loc_18008A37D
0x18003888f  mov     rcx, cs:WPP_GLOBAL_Control
0x180038896  lea     rax, WPP_GLOBAL_Control
0x18003889d  cmp     rcx, rax
0x1800388a0  jz      loc_18008A33E
0x1800388a6  cmp     byte ptr [rcx+19h], 3
0x1800388aa  jb      loc_18008A33E
0x1800388b0  test    byte ptr [rcx+1Ch], 1
0x1800388b4  jz      loc_18008A33E
0x1800388ba  mov     rax, [r9]
0x1800388bd  lea     r8, WPP_afd810515d1c3db64468bc5743bd872b_Traceguids
0x1800388c4  mov     rcx, [rcx+10h]
0x1800388c8  xor     r9d, r9d
0x1800388cb  mov     edx, 0Eh
0x1800388d0  mov     [rsp+58h+var_38], rax
0x1800388d5  call    WPP_SF_SS
0x1800388da  nop
0x1800388db  jmp     loc_18008A33E
0x1800388e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800388e7  lea     rax, WPP_GLOBAL_Control
0x1800388ee  cmp     rcx, rax
0x1800388f1  jz      loc_18008A347
0x1800388f7  cmp     byte ptr [rcx+19h], 3
0x1800388fb  jb      loc_18008A347
0x180038901  test    byte ptr [rcx+1Ch], 1
0x180038905  jz      loc_18008A347
0x18003890b  mov     rax, [r9]
0x18003890e  lea     r8, WPP_afd810515d1c3db64468bc5743bd872b_Traceguids
0x180038915  mov     rcx, [rcx+10h]
0x180038919  xor     r9d, r9d
0x18003891c  mov     edx, 0Dh
0x180038921  mov     [rsp+58h+var_38], rax
0x180038926  call    WPP_SF_SS
0x18003892b  nop
0x18003892c  jmp     loc_18008A347
0x18008a33e  mov     dword ptr [rdi+3Ch], 2
0x18008a345  jmp     short loc_18008A34E
0x18008a347  mov     dword ptr [rdi+3Ch], 1
0x18008a34e  mov     edx, 3
0x18008a353  mov     rcx, rdi
0x18008a356  call    WfpServiceChangeState
0x18008a35b  mov     rcx, [rdi+40h]; hEvent
0x18008a35f  call    cs:__imp_SetEvent
0x18008a365  test    eax, eax
0x18008a367  jnz     loc_18003880C
0x18008a36d  call    cs:__imp_GetLastError
0x18008a373  mov     r8d, eax
0x18008a376  lea     rdx, aSetevent; "SetEvent"
0x18008a37d  call    WfpReportSysErrorAsWinError
0x18008a382  nop
0x18008a383  jmp     loc_180038878
```
