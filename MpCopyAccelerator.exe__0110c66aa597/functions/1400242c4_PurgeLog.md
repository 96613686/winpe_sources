# PurgeLog

- ea: `0x1400242c4`
- end: `0x140024413`
- name: `PurgeLog`
- size: `335`
- prototype: `__int64 __fastcall(wchar_t *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14002380c`

## callees

- `0x140003254`
- `0x14000493c`
- `0x140005c20`
- `0x140005c40`
- `0x14001da70`
- `0x140024148`
- `0x1400242c4`
- `0x1400246d0`
- `0x140024984`

## import_xrefs

- `KERNEL32!MoveFileExW` at `0x14002434a`
- `KERNEL32!MoveFileExW` at `0x14002434a`

## string_xrefs

- `0x1400243db`: `ERROR: UtilDeletePathSafe() failed (%X)\n`

## pseudocode

```c
__int64 __fastcall PurgeLog(wchar_t *a1)
{
  const wchar_t *v2; // rdx
  int v3; // ebx
  WCHAR *v5; // rbx
  int v6; // eax
  unsigned int LastFailure; // edi
  unsigned __int64 v8; // rdx
  LPCWSTR lpNewFileName; // [rsp+30h] [rbp-18h] BYREF

  lpNewFileName = 0;
  v3 = CommonUtil::NewSprintfW((CommonUtil *)&lpNewFileName, (wchar_t **)L"%ls.bak", a1);
  if ( v3 < 0 )
  {
    if ( lpNewFileName )
      operator delete((void *)lpNewFileName, (unsigned __int64)v2);
    return (unsigned int)v3;
  }
  v5 = (WCHAR *)lpNewFileName;
  v6 = MpCmdUtils::UtilDeletePathSafe((void **)lpNewFileName, v2);
  LastFailure = v6;
  if ( v6 <= -2147024895 || (unsigned int)(v6 + 2147024892) <= 0x7FF8FFFB )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v5);
    MpCmdLogPrintf(L"ERROR: UtilDeletePathSafe() failed (%X)\n", LastFailure);
    goto LABEL_19;
  }
  if ( !MoveFileExW(a1, v5, 0) )
  {
    LastFailure = HrGetLastFailure();
    if ( (LastFailure & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_4c401faab9b1388d1fa6583bd2a81a5a_Traceguids, LastFailure);
LABEL_19:
      if ( v5 )
        operator delete(v5, v8);
      return LastFailure;
    }
  }
  if ( v5 )
    operator delete(v5, v8);
  return 0;
}

```

## disassembly

```asm
0x1400242c4  mov     r11, rsp
0x1400242c7  mov     [r11+10h], rbx
0x1400242cb  mov     [r11+18h], rsi
0x1400242cf  push    rdi
0x1400242d0  sub     rsp, 40h
0x1400242d4  mov     rax, cs:__security_cookie
0x1400242db  xor     rax, rsp
0x1400242de  mov     [rsp+48h+var_10], rax
0x1400242e3  mov     rsi, rcx
0x1400242e6  mov     qword ptr [r11-18h], 0
0x1400242ee  mov     r8, rcx; wchar_t *
0x1400242f1  lea     rdx, aLsBak; "%ls.bak"
0x1400242f8  lea     rcx, [r11-18h]; this
0x1400242fc  call    ?NewSprintfW@CommonUtil@@YAJPEAPEA_WPEB_WZZ; CommonUtil::NewSprintfW(wchar_t * *,wchar_t const *,...)
0x140024301  mov     ebx, eax
0x140024303  test    eax, eax
0x140024305  jns     short loc_14002431D
0x140024307  mov     rcx, [rsp+48h+lpNewFileName]; void *
0x14002430c  test    rcx, rcx
0x14002430f  jz      short loc_140024316
0x140024311  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140024316  mov     eax, ebx
0x140024318  jmp     loc_1400243F6
0x14002431d  mov     rbx, [rsp+48h+lpNewFileName]
0x140024322  mov     rcx, rbx; this
0x140024325  call    ?UtilDeletePathSafe@MpCmdUtils@@YAJPEB_W@Z; MpCmdUtils::UtilDeletePathSafe(wchar_t const *)
0x14002432a  mov     edi, eax
0x14002432c  cmp     eax, 80070001h
0x140024331  jle     short loc_1400243A3
0x140024333  lea     edx, [rax+7FF8FFFCh]
0x140024339  cmp     edx, 7FF8FFFBh
0x14002433f  jbe     short loc_1400243A3
0x140024341  xor     r8d, r8d; dwFlags
0x140024344  mov     rdx, rbx; lpNewFileName
0x140024347  mov     rcx, rsi; lpExistingFileName
0x14002434a  call    cs:__imp_MoveFileExW
0x140024350  test    eax, eax
0x140024352  jnz     short loc_140024392
0x140024354  call    HrGetLastFailure
0x140024359  mov     edi, eax
0x14002435b  test    eax, eax
0x14002435d  jns     short loc_140024392
0x14002435f  lea     rax, WPP_GLOBAL_Control
0x140024366  mov     rcx, cs:WPP_GLOBAL_Control
0x14002436d  cmp     rcx, rax
0x140024370  jz      short loc_1400243E7
0x140024372  test    byte ptr [rcx+1Ch], 1
0x140024376  jz      short loc_1400243E7
0x140024378  mov     edx, 1Dh
0x14002437d  mov     r9d, edi
0x140024380  lea     r8, WPP_4c401faab9b1388d1fa6583bd2a81a5a_Traceguids
0x140024387  mov     rcx, [rcx+10h]
0x14002438b  call    WPP_SF_d
0x140024390  jmp     short loc_1400243E7
0x140024392  test    rbx, rbx
0x140024395  jz      short loc_14002439F
0x140024397  mov     rcx, rbx; void *
0x14002439a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14002439f  xor     eax, eax
0x1400243a1  jmp     short loc_1400243F6
0x1400243a3  lea     rax, WPP_GLOBAL_Control
0x1400243aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400243b1  cmp     rcx, rax
0x1400243b4  jz      short loc_1400243D9
0x1400243b6  test    byte ptr [rcx+1Ch], 1
0x1400243ba  jz      short loc_1400243D9
0x1400243bc  mov     edx, 1Ch
0x1400243c1  mov     [rsp+48h+var_28], rbx; __int64
0x1400243c6  mov     r9d, edi
0x1400243c9  lea     r8, WPP_4c401faab9b1388d1fa6583bd2a81a5a_Traceguids
0x1400243d0  mov     rcx, [rcx+10h]; LoggerHandle
0x1400243d4  call    WPP_SF_dS
0x1400243d9  mov     edx, edi
0x1400243db  lea     rcx, aErrorUtildelet; "ERROR: UtilDeletePathSafe() failed (%X)"...
0x1400243e2  call    ?MpCmdLogPrintf@@YAXPEB_WZZ; MpCmdLogPrintf(wchar_t const *,...)
0x1400243e7  test    rbx, rbx
0x1400243ea  jz      short loc_1400243F4
0x1400243ec  mov     rcx, rbx; void *
0x1400243ef  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400243f4  mov     eax, edi
0x1400243f6  mov     rcx, [rsp+48h+var_10]
0x1400243fb  xor     rcx, rsp; StackCookie
0x1400243fe  call    __security_check_cookie
0x140024403  mov     rbx, [rsp+48h+arg_8]
0x140024408  mov     rsi, [rsp+48h+arg_10]
0x14002440d  add     rsp, 40h
0x140024411  pop     rdi
0x140024412  retn
```
