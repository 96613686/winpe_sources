# CSimpleRegistryWatcher::StartUpdateWatcher(void)

- ea: `0x180089380`
- end: `0x1800896aa`
- name: `?StartUpdateWatcher@CSimpleRegistryWatcher@@IEAAJXZ`
- size: `810`
- prototype: `__int64 __fastcall(CSimpleRegistryWatcher *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x180089a20`

## callees

- `0x1800105a4`
- `0x180089380`
- `0x180089b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800893a4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180089424`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180089486`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800894e5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800893a4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180089424`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180089486`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800894e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800893d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089400`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008945c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800894bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008951a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008957f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800895ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800893d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089400`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008945c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800894bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008951a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008957f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800895ae`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18008954e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18008954e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800895d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008960a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008963e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180089672`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800895d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008960a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008963e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180089672`

## string_xrefs

- `0x1800893e7`: `Update event handle creation failed`
- `0x180089593`: `Update watcher thread creation failed`

## pseudocode

```c
__int64 __fastcall CSimpleRegistryWatcher::StartUpdateWatcher(CSimpleRegistryWatcher *this)
{
  unsigned int v1; // ebx
  HANDLE EventW; // rax
  char v4; // al
  int v5; // r8d
  signed int v6; // eax
  HANDLE *v7; // r14
  HANDLE v8; // rax
  char LastError; // al
  int v10; // r8d
  int v11; // edx
  const wchar_t *v12; // r9
  HANDLE v13; // rax
  HANDLE v14; // rax
  HANDLE Thread; // rax
  signed int v16; // eax
  void *v17; // rcx
  void *v18; // rcx
  void *v19; // rcx

  v1 = 0;
  if ( *((_QWORD *)this + 1) )
    return v1;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 2) = EventW;
  if ( EventW )
  {
    v8 = CreateEventW(0, 0, 0, 0);
    v7 = (HANDLE *)((char *)this + 24);
    *((_QWORD *)this + 3) = v8;
    if ( v8 )
    {
      v13 = CreateEventW(0, 0, 0, 0);
      *((_QWORD *)this + 4) = v13;
      if ( v13 )
      {
        v14 = CreateEventW(0, 0, 0, 0);
        *((_QWORD *)this + 5) = v14;
        if ( v14 )
        {
          Thread = CreateThread(0, 0, CSimpleRegistryWatcher::UpdateWatcherThreadProc, this, 0, 0);
          *((_QWORD *)this + 1) = Thread;
          if ( Thread )
            return v1;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            goto LABEL_26;
          LastError = GetLastError();
          v11 = 16;
          v12 = L"Update watcher thread creation failed";
          goto LABEL_25;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          LastError = GetLastError();
          v11 = 15;
          v12 = L"Resume event handle creation failed";
          goto LABEL_25;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        v11 = 14;
        v12 = L"Suspend event handle creation failed";
        goto LABEL_25;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      v11 = 13;
      v12 = L"Shutdown event handle creation failed";
LABEL_25:
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, v10, (_DWORD)v12, LastError);
    }
LABEL_26:
    v16 = GetLastError();
    v1 = v16;
    if ( v16 > 0 )
      v1 = (unsigned __int16)v16 | 0x80070000;
    goto LABEL_28;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v4 = GetLastError();
    WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, v5, (unsigned int)L"Update event handle creation failed", v4);
  }
  v6 = GetLastError();
  v1 = v6;
  if ( v6 > 0 )
    v1 = (unsigned __int16)v6 | 0x80070000;
  v7 = (HANDLE *)((char *)this + 24);
LABEL_28:
  if ( (v1 & 0x80000000) != 0 )
  {
    v17 = (void *)*((_QWORD *)this + 2);
    if ( v17
      && !CloseHandle(v17)
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_4d6757e87b913ee9b8f01e6dd23dcef1_Traceguids);
    }
    if ( *v7
      && !CloseHandle(*v7)
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_4d6757e87b913ee9b8f01e6dd23dcef1_Traceguids);
    }
    v18 = (void *)*((_QWORD *)this + 4);
    if ( v18
      && !CloseHandle(v18)
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_4d6757e87b913ee9b8f01e6dd23dcef1_Traceguids);
    }
    v19 = (void *)*((_QWORD *)this + 5);
    if ( v19
      && !CloseHandle(v19)
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_4d6757e87b913ee9b8f01e6dd23dcef1_Traceguids);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180089380  push    rbx
0x180089382  push    rbp
0x180089383  push    rsi
0x180089384  push    rdi
0x180089385  push    r14
0x180089387  sub     rsp, 30h
0x18008938b  xor     ebx, ebx
0x18008938d  mov     rbp, rcx
0x180089390  cmp     [rcx+8], rbx
0x180089394  jnz     loc_18008969D
0x18008939a  xor     r9d, r9d; lpName
0x18008939d  xor     r8d, r8d; bInitialState
0x1800893a0  xor     edx, edx; bManualReset
0x1800893a2  xor     ecx, ecx; lpEventAttributes
0x1800893a4  call    cs:__imp_CreateEventW
0x1800893aa  mov     [rbp+10h], rax
0x1800893ae  test    rax, rax
0x1800893b1  jnz     short loc_18008941A
0x1800893b3  mov     rax, cs:WPP_GLOBAL_Control
0x1800893ba  lea     rsi, WPP_GLOBAL_Control
0x1800893c1  mov     edi, 80070000h
0x1800893c6  cmp     rax, rsi
0x1800893c9  jz      short loc_180089400
0x1800893cb  cmp     byte ptr [rax+19h], 2
0x1800893cf  jb      short loc_180089400
0x1800893d1  call    cs:__imp_GetLastError
0x1800893d7  test    eax, eax
0x1800893d9  jle     short loc_1800893E0
0x1800893db  movzx   eax, ax
0x1800893de  or      eax, edi
0x1800893e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800893e7  lea     r9, aUpdateEventHan; "Update event handle creation failed"
0x1800893ee  mov     edx, 0Ch
0x1800893f3  mov     [rsp+58h+dwCreationFlags], eax
0x1800893f7  mov     rcx, [rcx+10h]
0x1800893fb  call    WPP_SF_Sd
0x180089400  call    cs:__imp_GetLastError
0x180089406  mov     ebx, eax
0x180089408  test    eax, eax
0x18008940a  jle     short loc_180089411
0x18008940c  movzx   ebx, ax
0x18008940f  or      ebx, edi
0x180089411  lea     r14, [rbp+18h]
0x180089415  jmp     loc_1800895BF
0x18008941a  xor     r9d, r9d; lpName
0x18008941d  xor     r8d, r8d; bInitialState
0x180089420  xor     edx, edx; bManualReset
0x180089422  xor     ecx, ecx; lpEventAttributes
0x180089424  call    cs:__imp_CreateEventW
0x18008942a  lea     r14, [rbp+18h]
0x18008942e  mov     [r14], rax
0x180089431  test    rax, rax
0x180089434  jnz     short loc_18008947C
0x180089436  mov     rax, cs:WPP_GLOBAL_Control
0x18008943d  lea     rsi, WPP_GLOBAL_Control
0x180089444  mov     edi, 80070000h
0x180089449  cmp     rax, rsi
0x18008944c  jz      loc_1800895AE
0x180089452  cmp     byte ptr [rax+19h], 2
0x180089456  jb      loc_1800895AE
0x18008945c  call    cs:__imp_GetLastError
0x180089462  test    eax, eax
0x180089464  jle     short loc_18008946B
0x180089466  movzx   eax, ax
0x180089469  or      eax, edi
0x18008946b  mov     edx, 0Dh
0x180089470  lea     r9, aShutdownEventH; "Shutdown event handle creation failed"
0x180089477  jmp     loc_18008959A
0x18008947c  xor     r9d, r9d; lpName
0x18008947f  xor     r8d, r8d; bInitialState
0x180089482  xor     edx, edx; bManualReset
0x180089484  xor     ecx, ecx; lpEventAttributes
0x180089486  call    cs:__imp_CreateEventW
0x18008948c  mov     [rbp+20h], rax
0x180089490  test    rax, rax
0x180089493  jnz     short loc_1800894DB
0x180089495  mov     rax, cs:WPP_GLOBAL_Control
0x18008949c  lea     rsi, WPP_GLOBAL_Control
0x1800894a3  mov     edi, 80070000h
0x1800894a8  cmp     rax, rsi
0x1800894ab  jz      loc_1800895AE
0x1800894b1  cmp     byte ptr [rax+19h], 2
0x1800894b5  jb      loc_1800895AE
0x1800894bb  call    cs:__imp_GetLastError
0x1800894c1  test    eax, eax
0x1800894c3  jle     short loc_1800894CA
0x1800894c5  movzx   eax, ax
0x1800894c8  or      eax, edi
0x1800894ca  mov     edx, 0Eh
0x1800894cf  lea     r9, aSuspendEventHa; "Suspend event handle creation failed"
0x1800894d6  jmp     loc_18008959A
0x1800894db  xor     r9d, r9d; lpName
0x1800894de  xor     r8d, r8d; bInitialState
0x1800894e1  xor     edx, edx; bManualReset
0x1800894e3  xor     ecx, ecx; lpEventAttributes
0x1800894e5  call    cs:__imp_CreateEventW
0x1800894eb  mov     [rbp+28h], rax
0x1800894ef  test    rax, rax
0x1800894f2  jnz     short loc_180089537
0x1800894f4  mov     rax, cs:WPP_GLOBAL_Control
0x1800894fb  lea     rsi, WPP_GLOBAL_Control
0x180089502  mov     edi, 80070000h
0x180089507  cmp     rax, rsi
0x18008950a  jz      loc_1800895AE
0x180089510  cmp     byte ptr [rax+19h], 2
0x180089514  jb      loc_1800895AE
0x18008951a  call    cs:__imp_GetLastError
0x180089520  test    eax, eax
0x180089522  jle     short loc_180089529
0x180089524  movzx   eax, ax
0x180089527  or      eax, edi
0x180089529  mov     edx, 0Fh
0x18008952e  lea     r9, aResumeEventHan; "Resume event handle creation failed"
0x180089535  jmp     short loc_18008959A
0x180089537  mov     [rsp+58h+lpThreadId], rbx; lpThreadId
0x18008953c  lea     r8, ?UpdateWatcherThreadProc@CSimpleRegistryWatcher@@CAKPEAX@Z; lpStartAddress
0x180089543  mov     r9, rbp; lpParameter
0x180089546  mov     [rsp+58h+dwCreationFlags], ebx; dwCreationFlags
0x18008954a  xor     edx, edx; dwStackSize
0x18008954c  xor     ecx, ecx; lpThreadAttributes
0x18008954e  call    cs:__imp_CreateThread
0x180089554  mov     [rbp+8], rax
0x180089558  test    rax, rax
0x18008955b  jnz     loc_18008969D
0x180089561  mov     rax, cs:WPP_GLOBAL_Control
0x180089568  lea     rsi, WPP_GLOBAL_Control
0x18008956f  mov     edi, 80070000h
0x180089574  cmp     rax, rsi
0x180089577  jz      short loc_1800895AE
0x180089579  cmp     byte ptr [rax+19h], 2
0x18008957d  jb      short loc_1800895AE
0x18008957f  call    cs:__imp_GetLastError
0x180089585  test    eax, eax
0x180089587  jle     short loc_18008958E
0x180089589  movzx   eax, ax
0x18008958c  or      eax, edi
0x18008958e  mov     edx, 10h
0x180089593  lea     r9, aUpdateWatcherT; "Update watcher thread creation failed"
0x18008959a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800895a1  mov     [rsp+58h+dwCreationFlags], eax
0x1800895a5  mov     rcx, [rcx+10h]
0x1800895a9  call    WPP_SF_Sd
0x1800895ae  call    cs:__imp_GetLastError
0x1800895b4  mov     ebx, eax
0x1800895b6  test    eax, eax
0x1800895b8  jle     short loc_1800895BF
0x1800895ba  movzx   ebx, ax
0x1800895bd  or      ebx, edi
0x1800895bf  test    ebx, ebx
0x1800895c1  jns     loc_18008969D
0x1800895c7  mov     rcx, [rbp+10h]; hObject
0x1800895cb  lea     rdi, WPP_4d6757e87b913ee9b8f01e6dd23dcef1_Traceguids
0x1800895d2  test    rcx, rcx
0x1800895d5  jz      short loc_180089602
0x1800895d7  call    cs:__imp_CloseHandle
0x1800895dd  test    eax, eax
0x1800895df  jnz     short loc_180089602
0x1800895e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800895e8  cmp     rcx, rsi
0x1800895eb  jz      short loc_180089602
0x1800895ed  cmp     byte ptr [rcx+19h], 2
0x1800895f1  jb      short loc_180089602
0x1800895f3  mov     rcx, [rcx+10h]
0x1800895f7  lea     edx, [rax+11h]
0x1800895fa  mov     r8, rdi
0x1800895fd  call    WPP_SF_
0x180089602  mov     rcx, [r14]; hObject
0x180089605  test    rcx, rcx
0x180089608  jz      short loc_180089635
0x18008960a  call    cs:__imp_CloseHandle
0x180089610  test    eax, eax
0x180089612  jnz     short loc_180089635
0x180089614  mov     rcx, cs:WPP_GLOBAL_Control
0x18008961b  cmp     rcx, rsi
0x18008961e  jz      short loc_180089635
0x180089620  cmp     byte ptr [rcx+19h], 2
0x180089624  jb      short loc_180089635
0x180089626  mov     rcx, [rcx+10h]
0x18008962a  lea     edx, [rax+12h]
0x18008962d  mov     r8, rdi
0x180089630  call    WPP_SF_
0x180089635  mov     rcx, [rbp+20h]; hObject
0x180089639  test    rcx, rcx
0x18008963c  jz      short loc_180089669
0x18008963e  call    cs:__imp_CloseHandle
0x180089644  test    eax, eax
0x180089646  jnz     short loc_180089669
0x180089648  mov     rcx, cs:WPP_GLOBAL_Control
0x18008964f  cmp     rcx, rsi
0x180089652  jz      short loc_180089669
0x180089654  cmp     byte ptr [rcx+19h], 2
0x180089658  jb      short loc_180089669
0x18008965a  mov     rcx, [rcx+10h]
0x18008965e  lea     edx, [rax+13h]
0x180089661  mov     r8, rdi
0x180089664  call    WPP_SF_
0x180089669  mov     rcx, [rbp+28h]; hObject
0x18008966d  test    rcx, rcx
0x180089670  jz      short loc_18008969D
0x180089672  call    cs:__imp_CloseHandle
0x180089678  test    eax, eax
0x18008967a  jnz     short loc_18008969D
0x18008967c  mov     rcx, cs:WPP_GLOBAL_Control
0x180089683  cmp     rcx, rsi
0x180089686  jz      short loc_18008969D
0x180089688  cmp     byte ptr [rcx+19h], 2
0x18008968c  jb      short loc_18008969D
0x18008968e  mov     rcx, [rcx+10h]
0x180089692  lea     edx, [rax+14h]
0x180089695  mov     r8, rdi
0x180089698  call    WPP_SF_
0x18008969d  mov     eax, ebx
0x18008969f  add     rsp, 30h
0x1800896a3  pop     r14
0x1800896a5  pop     rdi
0x1800896a6  pop     rsi
0x1800896a7  pop     rbp
0x1800896a8  pop     rbx
0x1800896a9  retn
```
