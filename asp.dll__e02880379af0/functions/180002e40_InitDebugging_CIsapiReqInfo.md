# InitDebugging(CIsapiReqInfo *)

- ea: `0x180002e40`
- end: `0x180002eb7`
- name: `?InitDebugging@@YAJPEAVCIsapiReqInfo@@@Z`
- size: `119`
- prototype: `__int64 __fastcall(struct CIsapiReqInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180002ae8`

## callees

- `0x180002e40`
- `0x180002ec0`
- `0x180023d86`
- `0x180023dd0`
- `0x180064010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x1800251cf`
- `msvcrt!wcscpy_s` at `0x1800251cf`
- `KERNEL32!CloseHandle` at `0x1800252e9`
- `KERNEL32!CloseHandle` at `0x1800252e9`
- `KERNEL32!SetEvent` at `0x1800252c5`
- `KERNEL32!SetEvent` at `0x1800252c5`
- `KERNEL32!Sleep` at `0x1800252d2`
- `KERNEL32!Sleep` at `0x1800252d2`
- `KERNEL32!DeleteCriticalSection` at `0x180025301`
- `KERNEL32!DeleteCriticalSection` at `0x180025301`
- `KERNEL32!GetLastError` at `0x180025157`
- `KERNEL32!GetLastError` at `0x180025157`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x1800251ba`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x1800251ba`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800251ac`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800251ac`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x180002e7c`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x180002e7c`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180002e96`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002525d`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180002e96`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002525d`
- `iisutil!IISInitializeCriticalSection` at `0x18002514d`
- `iisutil!IISInitializeCriticalSection` at `0x18002514d`

## pseudocode

```c
__int64 __fastcall InitDebugging(struct CIsapiReqInfo *a1)
{
  signed int started; // ebx
  signed int LastError; // eax
  wchar_t *Ptr; // rbx
  unsigned int Size; // eax
  _BYTE v6[56]; // [rsp+28h] [rbp-D0h] BYREF
  unsigned __int8 v7[128]; // [rsp+60h] [rbp-98h] BYREF

  memset_0(v7, 0, sizeof(v7));
  BUFFER::BUFFER((BUFFER *)v6, v7, 0x80u);
  started = StartPDM();
  if ( started < 0 )
    goto LABEL_2;
  started = 0;
  if ( !(unsigned int)IISInitializeCriticalSection(&stru_18007E430) )
  {
    LastError = GetLastError();
    started = LastError;
    if ( LastError > 0 )
      started = (unsigned __int16)LastError | 0x80070000;
  }
  if ( started < 0 )
    goto LABEL_2;
  started = (*(__int64 (__fastcall **)(LPVOID, struct IDebugApplication64 **))(*(_QWORD *)g_pPDM + 24LL))(
              g_pPDM,
              &g_pDebugApp);
  if ( started < 0
    || (Ptr = (wchar_t *)BUFFER::QueryPtr((BUFFER *)v6),
        Size = BUFFER::QuerySize((BUFFER *)v6),
        wcscpy_s(Ptr, (unsigned __int64)Size >> 1, L"Microsoft Active Server Pages"),
        started = ((__int64 (__fastcall *)(struct IDebugApplication64 *, wchar_t *))g_pDebugApp->lpVtbl->SetName)(
                    g_pDebugApp,
                    Ptr),
        started < 0)
    || (started = (*(__int64 (__fastcall **)(LPVOID, struct IDebugApplication64 *, int *))(*(_QWORD *)g_pPDM + 40LL))(
                    g_pPDM,
                    g_pDebugApp,
                    &dword_18007E428),
        started < 0)
    || (started = ((__int64 (__fastcall *)(struct IDebugApplication64 *, struct IDebugApplicationNode **))g_pDebugApp->lpVtbl->GetRootNode)(
                    g_pDebugApp,
                    &g_pDebugAppRoot),
        started < 0) )
  {
    if ( g_pDebugAppRoot )
    {
      ((void (__fastcall *)(struct IDebugApplicationNode *))g_pDebugAppRoot->lpVtbl->Release)(g_pDebugAppRoot);
      g_pDebugAppRoot = 0;
    }
    if ( g_pDebugApp )
    {
      ((void (__fastcall *)(struct IDebugApplication64 *))g_pDebugApp->lpVtbl->Release)(g_pDebugApp);
      g_pDebugApp = 0;
    }
    if ( g_pPDM )
    {
      SetEvent(hObject);
      while ( g_pPDM )
        Sleep(0x64u);
      CloseHandle(hObject);
      g_pPDM = 0;
      DeleteCriticalSection(&stru_18007E430);
    }
LABEL_2:
    BUFFER::~BUFFER((BUFFER *)v6);
    return (unsigned int)started;
  }
  qword_180078030 = 11;
  qword_180078020 = 0;
  dword_180078008 |= 1u;
  BUFFER::~BUFFER((BUFFER *)v6);
  return 0;
}

```

## disassembly

```asm
0x180002e40  push    rbx
0x180002e42  sub     rsp, 0F0h
0x180002e49  mov     rax, cs:__security_cookie
0x180002e50  xor     rax, rsp
0x180002e53  mov     [rsp+0F8h+var_18], rax
0x180002e5b  mov     ebx, 80h
0x180002e60  mov     r8d, ebx; Size
0x180002e63  xor     edx, edx; Val
0x180002e65  lea     rcx, [rsp+0F8h+var_98]; void *
0x180002e6a  call    memset_0
0x180002e6f  mov     r8d, ebx
0x180002e72  lea     rdx, [rsp+0F8h+var_98]
0x180002e77  lea     rcx, [rsp+0F8h+var_D0]
0x180002e7c  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x180002e82  call    ?StartPDM@@YAJXZ; StartPDM(void)
0x180002e87  mov     ebx, eax
0x180002e89  test    eax, eax
0x180002e8b  jns     loc_180025144
0x180002e91  lea     rcx, [rsp+0F8h+var_D0]
0x180002e96  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180002e9c  mov     eax, ebx
0x180002e9e  mov     rcx, [rsp+0F8h+var_18]
0x180002ea6  xor     rcx, rsp; StackCookie
0x180002ea9  call    __security_check_cookie
0x180002eae  add     rsp, 0F0h
0x180002eb5  pop     rbx
0x180002eb6  retn
0x180025144  xor     ebx, ebx
0x180025146  lea     rcx, stru_18007E430
0x18002514d  call    cs:__imp_IISInitializeCriticalSection
0x180025153  test    eax, eax
0x180025155  jnz     short loc_180025170
0x180025157  call    cs:__imp_GetLastError
0x18002515d  mov     ebx, eax
0x18002515f  test    eax, eax
0x180025161  jle     short loc_18002516C
0x180025163  movzx   ebx, ax
0x180025166  or      ebx, 80070000h
0x18002516c  mov     [rsp+0F8h+var_D8], ebx
0x180025170  jmp     short loc_18002517B
0x180025172  mov     ebx, 8000FFFFh
0x180025177  mov     [rsp+0F8h+var_D8], ebx
0x18002517b  test    ebx, ebx
0x18002517d  js      loc_180002E91
0x180025183  mov     rcx, cs:?g_pPDM@@3PEAUIProcessDebugManager64@@EA; IProcessDebugManager64 * g_pPDM
0x18002518a  mov     rax, [rcx]
0x18002518d  lea     rdx, ?g_pDebugApp@@3PEAUIDebugApplication64@@EA; IDebugApplication64 * g_pDebugApp
0x180025194  mov     rax, [rax+18h]
0x180025198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002519d  mov     ebx, eax
0x18002519f  test    eax, eax
0x1800251a1  js      loc_18002526A
0x1800251a7  lea     rcx, [rsp+0F8h+var_D0]
0x1800251ac  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800251b2  mov     rbx, rax
0x1800251b5  lea     rcx, [rsp+0F8h+var_D0]
0x1800251ba  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x1800251c0  mov     edx, eax
0x1800251c2  shr     rdx, 1; SizeInWords
0x1800251c5  lea     r8, aMicrosoftActiv; "Microsoft Active Server Pages"
0x1800251cc  mov     rcx, rbx; Destination
0x1800251cf  call    cs:__imp_wcscpy_s
0x1800251d5  mov     r8, cs:?g_pDebugApp@@3PEAUIDebugApplication64@@EA; IDebugApplication64 * g_pDebugApp
0x1800251dc  mov     rcx, [r8]
0x1800251df  mov     rax, [rcx+70h]
0x1800251e3  mov     rdx, rbx
0x1800251e6  mov     rcx, r8
0x1800251e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800251ee  mov     ebx, eax
0x1800251f0  test    eax, eax
0x1800251f2  js      short loc_18002526A
0x1800251f4  mov     rcx, cs:?g_pPDM@@3PEAUIProcessDebugManager64@@EA; IProcessDebugManager64 * g_pPDM
0x1800251fb  mov     rax, [rcx]
0x1800251fe  lea     r8, dword_18007E428
0x180025205  mov     rdx, cs:?g_pDebugApp@@3PEAUIDebugApplication64@@EA; IDebugApplication64 * g_pDebugApp
0x18002520c  mov     rax, [rax+28h]
0x180025210  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025215  mov     ebx, eax
0x180025217  test    eax, eax
0x180025219  js      short loc_18002526A
0x18002521b  mov     rcx, cs:?g_pDebugApp@@3PEAUIDebugApplication64@@EA; IDebugApplication64 * g_pDebugApp
0x180025222  mov     rax, [rcx]
0x180025225  lea     rdx, ?g_pDebugAppRoot@@3PEAUIDebugApplicationNode@@EA; IDebugApplicationNode * g_pDebugAppRoot
0x18002522c  mov     rax, [rax+60h]
0x180025230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025235  mov     ebx, eax
0x180025237  test    eax, eax
0x180025239  js      short loc_18002526A
0x18002523b  mov     cs:qword_180078030, 0Bh
0x180025246  mov     cs:qword_180078020, 0
0x180025251  or      cs:dword_180078008, 1
0x180025258  lea     rcx, [rsp+0F8h+var_D0]
0x18002525d  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180025263  xor     eax, eax
0x180025265  jmp     loc_180002E9E
0x18002526a  mov     rcx, cs:?g_pDebugAppRoot@@3PEAUIDebugApplicationNode@@EA; IDebugApplicationNode * g_pDebugAppRoot
0x180025271  test    rcx, rcx
0x180025274  jz      short loc_18002528D
0x180025276  mov     rax, [rcx]
0x180025279  mov     rax, [rax+10h]
0x18002527d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025282  mov     cs:?g_pDebugAppRoot@@3PEAUIDebugApplicationNode@@EA, 0; IDebugApplicationNode * g_pDebugAppRoot
0x18002528d  mov     rcx, cs:?g_pDebugApp@@3PEAUIDebugApplication64@@EA; IDebugApplication64 * g_pDebugApp
0x180025294  test    rcx, rcx
0x180025297  jz      short loc_1800252B0
0x180025299  mov     rax, [rcx]
0x18002529c  mov     rax, [rax+10h]
0x1800252a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800252a5  mov     cs:?g_pDebugApp@@3PEAUIDebugApplication64@@EA, 0; IDebugApplication64 * g_pDebugApp
0x1800252b0  cmp     cs:?g_pPDM@@3PEAUIProcessDebugManager64@@EA, 0; IProcessDebugManager64 * g_pPDM
0x1800252b8  jz      loc_180002E91
0x1800252be  mov     rcx, cs:hObject; hEvent
0x1800252c5  call    cs:__imp_SetEvent
0x1800252cb  jmp     short loc_1800252D8
0x1800252cd  mov     ecx, 64h ; 'd'; dwMilliseconds
0x1800252d2  call    cs:__imp_Sleep
0x1800252d8  cmp     cs:?g_pPDM@@3PEAUIProcessDebugManager64@@EA, 0; IProcessDebugManager64 * g_pPDM
0x1800252e0  jnz     short loc_1800252CD
0x1800252e2  mov     rcx, cs:hObject; hObject
0x1800252e9  call    cs:__imp_CloseHandle
0x1800252ef  mov     cs:?g_pPDM@@3PEAUIProcessDebugManager64@@EA, 0; IProcessDebugManager64 * g_pPDM
0x1800252fa  lea     rcx, stru_18007E430; lpCriticalSection
0x180025301  call    cs:__imp_DeleteCriticalSection
0x180025307  nop
0x180025308  jmp     loc_180002E91
```
