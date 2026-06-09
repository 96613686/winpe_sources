# HangUpThread

- ea: `0x18001efc0`
- end: `0x18001f237`
- name: `HangUpThread`
- size: `631`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x18001efc0`
- `0x1800552a4`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f1c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f1ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f1c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f1ef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f040`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f040`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f132`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f22c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f132`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f22c`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18001f030`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18001f030`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001f156`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001f156`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001f057`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001f057`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001f0b3`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001f0ed`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001f0b3`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001f0ed`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasHangUpW` at `0x18001f142`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasHangUpW` at `0x18001f142`

## pseudocode

```c
void __fastcall HangUpThread(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)
{
  __int64 v4; // rdi
  HRASCONN *v5; // rsi
  unsigned int v6; // ecx
  __int64 v7; // rbx
  __int64 v8; // r8
  DWORD LastError; // eax
  __int64 i; // rbx
  struct _LIST_ENTRY *v11; // rcx
  __int64 v12; // rdx
  WCHAR lpWideCharStr[264]; // [rsp+30h] [rbp-468h] BYREF
  WCHAR WideCharStr[264]; // [rsp+240h] [rbp-258h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 178, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
  }
  v4 = 0;
  v5 = (HRASCONN *)GlobalAlloc(0x40u, 8LL * (unsigned int)MaxPorts);
  EnterCriticalSection(&g_csSubmitRequest);
  SetThreadpoolWait(g_hangUpThreadPool, g_hangUpEvent, 0);
  v6 = MaxPorts;
  v7 = 0;
  if ( !MaxPorts )
  {
LABEL_13:
    LeaveCriticalSection(&g_csSubmitRequest);
    for ( i = 0; (unsigned int)i < (unsigned int)v4; i = (unsigned int)(i + 1) )
      RasHangUpW(v5[i]);
    goto LABEL_15;
  }
  while ( 1 )
  {
    v8 = *((_QWORD *)Pcb + v7);
    if ( !v8 || !*(_DWORD *)(v8 + 1376) )
      goto LABEL_12;
    if ( !MultiByteToWideChar(0, 0, *(LPCCH *)(v8 + 1200), -1, WideCharStr, 261) )
    {
      LastError = GetLastError();
      if ( LastError )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          v12 = 179;
          goto LABEL_36;
        }
      }
      goto LABEL_37;
    }
    if ( !MultiByteToWideChar(0, 0, *(LPCCH *)(*((_QWORD *)Pcb + v7) + 1208LL), -1, lpWideCharStr, 257) )
      break;
    LastError = RasGetEntryHrasconnW(WideCharStr, lpWideCharStr, &v5[v4]);
    if ( LastError )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v12 = 181;
LABEL_36:
        WPP_SF_d(v11[1].Flink, v12, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, LastError);
        goto LABEL_37;
      }
      goto LABEL_37;
    }
    v6 = MaxPorts;
    v4 = (unsigned int)(v4 + 1);
LABEL_12:
    v7 = (unsigned int)(v7 + 1);
    if ( (unsigned int)v7 >= v6 )
      goto LABEL_13;
  }
  LastError = GetLastError();
  if ( LastError )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v12 = 180;
      goto LABEL_36;
    }
  }
LABEL_37:
  LeaveCriticalSection(&g_csSubmitRequest);
LABEL_15:
  if ( v5 )
    GlobalFree(v5);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 182, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
  }
}

```

## disassembly

```asm
0x18001efc0  push    rbx
0x18001efc2  push    rbp
0x18001efc3  push    rsi
0x18001efc4  push    rdi
0x18001efc5  push    r12
0x18001efc7  push    r14
0x18001efc9  push    r15
0x18001efcb  sub     rsp, 460h
0x18001efd2  mov     rax, cs:__security_cookie
0x18001efd9  xor     rax, rsp
0x18001efdc  mov     [rsp+498h+var_48], rax
0x18001efe4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001efeb  lea     r15, WPP_GLOBAL_Control
0x18001eff2  lea     r12, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x18001eff9  mov     r14d, 2000h
0x18001efff  cmp     rcx, r15
0x18001f002  jz      short loc_18001F021
0x18001f004  test    [rcx+1Ch], r14d
0x18001f008  jz      short loc_18001F021
0x18001f00a  cmp     byte ptr [rcx+19h], 6
0x18001f00e  jb      short loc_18001F021
0x18001f010  mov     rcx, [rcx+10h]
0x18001f014  mov     edx, 0B2h
0x18001f019  mov     r8, r12
0x18001f01c  call    WPP_SF_
0x18001f021  mov     edx, cs:MaxPorts
0x18001f027  xor     edi, edi
0x18001f029  shl     rdx, 3; dwBytes
0x18001f02d  lea     ecx, [rdi+40h]; uFlags
0x18001f030  call    cs:__imp_GlobalAlloc
0x18001f036  lea     rcx, g_csSubmitRequest; lpCriticalSection
0x18001f03d  mov     rsi, rax
0x18001f040  call    cs:__imp_EnterCriticalSection
0x18001f046  mov     rdx, cs:g_hangUpEvent; h
0x18001f04d  xor     r8d, r8d; pftTimeout
0x18001f050  mov     rcx, cs:g_hangUpThreadPool; pwa
0x18001f057  call    cs:__imp_SetThreadpoolWait
0x18001f05d  mov     ecx, cs:MaxPorts
0x18001f063  xor     ebx, ebx
0x18001f065  test    ecx, ecx
0x18001f067  jz      loc_18001F12B
0x18001f06d  mov     rax, cs:Pcb
0x18001f074  mov     r8, [rax+rbx*8]
0x18001f078  test    r8, r8
0x18001f07b  jz      loc_18001F121
0x18001f081  cmp     dword ptr [r8+560h], 0
0x18001f089  jz      loc_18001F121
0x18001f08f  mov     r8, [r8+4B0h]; lpMultiByteStr
0x18001f096  lea     rax, [rsp+498h+WideCharStr]
0x18001f09e  mov     [rsp+498h+cchWideChar], 105h; cchWideChar
0x18001f0a6  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18001f0aa  xor     edx, edx; dwFlags
0x18001f0ac  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x18001f0b1  xor     ecx, ecx; CodePage
0x18001f0b3  call    cs:__imp_MultiByteToWideChar
0x18001f0b9  test    eax, eax
0x18001f0bb  jz      loc_18001F1EF
0x18001f0c1  mov     rax, cs:Pcb
0x18001f0c8  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18001f0cc  mov     [rsp+498h+cchWideChar], 101h; cchWideChar
0x18001f0d4  xor     edx, edx; dwFlags
0x18001f0d6  xor     ecx, ecx; CodePage
0x18001f0d8  mov     r8, [rax+rbx*8]
0x18001f0dc  lea     rax, [rsp+498h+var_468]
0x18001f0e1  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x18001f0e6  mov     r8, [r8+4B8h]; lpMultiByteStr
0x18001f0ed  call    cs:__imp_MultiByteToWideChar
0x18001f0f3  test    eax, eax
0x18001f0f5  jz      loc_18001F1C6
0x18001f0fb  lea     r8, [rsi+rdi*8]
0x18001f0ff  lea     rdx, [rsp+498h+var_468]
0x18001f104  lea     rcx, [rsp+498h+WideCharStr]
0x18001f10c  call    RasGetEntryHrasconnW
0x18001f111  test    eax, eax
0x18001f113  jnz     loc_18001F1A7
0x18001f119  mov     ecx, cs:MaxPorts
0x18001f11f  inc     edi
0x18001f121  inc     ebx
0x18001f123  cmp     ebx, ecx
0x18001f125  jb      loc_18001F06D
0x18001f12b  lea     rcx, g_csSubmitRequest; lpCriticalSection
0x18001f132  call    cs:__imp_LeaveCriticalSection
0x18001f138  xor     ebx, ebx
0x18001f13a  test    edi, edi
0x18001f13c  jz      short loc_18001F14E
0x18001f13e  mov     rcx, [rsi+rbx*8]; HRASCONN
0x18001f142  call    cs:__imp_RasHangUpW
0x18001f148  inc     ebx
0x18001f14a  cmp     ebx, edi
0x18001f14c  jb      short loc_18001F13E
0x18001f14e  test    rsi, rsi
0x18001f151  jz      short loc_18001F15C
0x18001f153  mov     rcx, rsi; hMem
0x18001f156  call    cs:__imp_GlobalFree
0x18001f15c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f163  cmp     rcx, r15
0x18001f166  jz      short loc_18001F185
0x18001f168  test    [rcx+1Ch], r14d
0x18001f16c  jz      short loc_18001F185
0x18001f16e  cmp     byte ptr [rcx+19h], 6
0x18001f172  jb      short loc_18001F185
0x18001f174  mov     rcx, [rcx+10h]
0x18001f178  mov     edx, 0B6h
0x18001f17d  mov     r8, r12
0x18001f180  call    WPP_SF_
0x18001f185  mov     rcx, [rsp+498h+var_48]
0x18001f18d  xor     rcx, rsp; StackCookie
0x18001f190  call    __security_check_cookie
0x18001f195  add     rsp, 460h
0x18001f19c  pop     r15
0x18001f19e  pop     r14
0x18001f1a0  pop     r12
0x18001f1a2  pop     rdi
0x18001f1a3  pop     rsi
0x18001f1a4  pop     rbp
0x18001f1a5  pop     rbx
0x18001f1a6  retn
0x18001f1a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f1ae  cmp     rcx, r15
0x18001f1b1  jz      short loc_18001F225
0x18001f1b3  test    [rcx+1Ch], r14d
0x18001f1b7  jz      short loc_18001F225
0x18001f1b9  cmp     byte ptr [rcx+19h], 2
0x18001f1bd  jb      short loc_18001F225
0x18001f1bf  mov     edx, 0B5h
0x18001f1c4  jmp     short loc_18001F216
0x18001f1c6  call    cs:__imp_GetLastError
0x18001f1cc  test    eax, eax
0x18001f1ce  jz      short loc_18001F225
0x18001f1d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f1d7  cmp     rcx, r15
0x18001f1da  jz      short loc_18001F225
0x18001f1dc  test    [rcx+1Ch], r14d
0x18001f1e0  jz      short loc_18001F225
0x18001f1e2  cmp     byte ptr [rcx+19h], 2
0x18001f1e6  jb      short loc_18001F225
0x18001f1e8  mov     edx, 0B4h
0x18001f1ed  jmp     short loc_18001F216
0x18001f1ef  call    cs:__imp_GetLastError
0x18001f1f5  test    eax, eax
0x18001f1f7  jz      short loc_18001F225
0x18001f1f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f200  cmp     rcx, r15
0x18001f203  jz      short loc_18001F225
0x18001f205  test    [rcx+1Ch], r14d
0x18001f209  jz      short loc_18001F225
0x18001f20b  cmp     byte ptr [rcx+19h], 2
0x18001f20f  jb      short loc_18001F225
0x18001f211  mov     edx, 0B3h
0x18001f216  mov     rcx, [rcx+10h]
0x18001f21a  mov     r9d, eax
0x18001f21d  mov     r8, r12
0x18001f220  call    WPP_SF_d
0x18001f225  lea     rcx, g_csSubmitRequest; lpCriticalSection
0x18001f22c  call    cs:__imp_LeaveCriticalSection
0x18001f232  jmp     loc_18001F14E
```
