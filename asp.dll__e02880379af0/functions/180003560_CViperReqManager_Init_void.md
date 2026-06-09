# CViperReqManager::Init(void)

- ea: `0x180003560`
- end: `0x1800036d5`
- name: `?Init@CViperReqManager@@QEAAJXZ`
- size: `373`
- prototype: `__int64 __fastcall(CViperReqManager *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180002ae8`

## callees

- `0x180003560`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180025476`
- `KERNEL32!CloseHandle` at `0x180025476`
- `KERNEL32!CreateThread` at `0x18000369e`
- `KERNEL32!CreateThread` at `0x18000369e`
- `KERNEL32!CreateEventA` at `0x18000365f`
- `KERNEL32!CreateEventA` at `0x18000365f`
- `KERNEL32!GetTickCount` at `0x180003593`
- `KERNEL32!GetTickCount` at `0x180003593`
- `KERNEL32!GetLastError` at `0x1800035da`
- `KERNEL32!GetLastError` at `0x180003620`
- `KERNEL32!GetLastError` at `0x180025448`
- `KERNEL32!GetLastError` at `0x1800035da`
- `KERNEL32!GetLastError` at `0x180003620`
- `KERNEL32!GetLastError` at `0x180025448`
- `iisutil!IISInitializeCriticalSection` at `0x1800035d0`
- `iisutil!IISInitializeCriticalSection` at `0x180003616`
- `iisutil!IISInitializeCriticalSection` at `0x1800035d0`
- `iisutil!IISInitializeCriticalSection` at `0x180003616`

## pseudocode

```c
__int64 __fastcall CViperReqManager::Init(CViperReqManager *this)
{
  signed int v1; // ebx
  signed int LastError; // eax
  signed int v3; // eax
  signed int v5; // eax

  if ( (dword_18007D2BC & 8) != 0 )
    return 0;
  dword_18007D310 = dword_180079FA4 / (unsigned int)(g_fOOP != 0 ? 5 : 10);
  dword_18007D328 = GetTickCount() / 0x3E8;
  dword_18007D32C = 80 * dword_180079FA4 / 0x64u;
  v1 = 0;
  if ( !(unsigned int)IISInitializeCriticalSection(&stru_18007D2C0) )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( v1 < 0 )
    goto LABEL_21;
  dword_18007D2BC |= 1u;
  v1 = 0;
  if ( !(unsigned int)IISInitializeCriticalSection(&stru_18007D2E8) )
  {
    v3 = GetLastError();
    v1 = v3;
    if ( v3 > 0 )
      v1 = (unsigned __int16)v3 | 0x80070000;
  }
  if ( v1 < 0 )
    goto LABEL_21;
  dword_18007D2BC |= 2u;
  hEvent = CreateEventA(0, 1, 0, 0);
  if ( !hEvent )
    v1 = -2147024882;
  if ( v1 < 0 )
    goto LABEL_21;
  qword_18007D320 = CreateThread(0, 0, CViperReqManager::WatchThread, 0, 0, 0);
  if ( !qword_18007D320 )
  {
    v5 = GetLastError();
    v1 = v5;
    if ( v5 > 0 )
      v1 = (unsigned __int16)v5 | 0x80070000;
  }
  if ( v1 < 0 )
  {
LABEL_21:
    if ( hEvent )
      CloseHandle(hEvent);
  }
  if ( (g_AspRegistryParams & 1) != 0 )
    dword_18007D2BC = dword_18007D2BC & 0xFFFFFFF7 | (*(_DWORD *)&Data == 0 ? 8 : 0);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180003560  push    rbx
0x180003562  sub     rsp, 40h
0x180003566  test    byte ptr cs:dword_18007D2BC, 8
0x18000356d  jnz     loc_1800036D1
0x180003573  mov     eax, cs:?g_fOOP@@3HA; int g_fOOP
0x180003579  neg     eax
0x18000357b  sbb     ecx, ecx
0x18000357d  and     ecx, 0FFFFFFFBh
0x180003580  add     ecx, 0Ah
0x180003583  xor     edx, edx
0x180003585  mov     eax, cs:dword_180079FA4
0x18000358b  div     ecx
0x18000358d  mov     cs:dword_18007D310, eax
0x180003593  call    cs:__imp_GetTickCount
0x180003599  mov     ecx, eax
0x18000359b  mov     eax, 10624DD3h
0x1800035a0  mul     ecx
0x1800035a2  shr     edx, 6
0x1800035a5  mov     cs:dword_18007D328, edx
0x1800035ab  mov     eax, cs:dword_180079FA4
0x1800035b1  lea     ecx, [rax+rax*4]
0x1800035b4  shl     ecx, 4
0x1800035b7  mov     eax, 51EB851Fh
0x1800035bc  mul     ecx
0x1800035be  shr     edx, 5
0x1800035c1  mov     cs:dword_18007D32C, edx
0x1800035c7  xor     ebx, ebx
0x1800035c9  lea     rcx, stru_18007D2C0
0x1800035d0  call    cs:__imp_IISInitializeCriticalSection
0x1800035d6  test    eax, eax
0x1800035d8  jnz     short loc_1800035F3
0x1800035da  call    cs:__imp_GetLastError
0x1800035e0  mov     ebx, eax
0x1800035e2  test    eax, eax
0x1800035e4  jle     short loc_1800035EF
0x1800035e6  movzx   ebx, ax
0x1800035e9  or      ebx, 80070000h
0x1800035ef  mov     [rsp+48h+var_18], ebx
0x1800035f3  jmp     short loc_1800035FE
0x1800035f5  mov     ebx, 8000FFFFh
0x1800035fa  mov     [rsp+48h+var_18], ebx
0x1800035fe  test    ebx, ebx
0x180003600  js      loc_180025466
0x180003606  or      cs:dword_18007D2BC, 1
0x18000360d  xor     ebx, ebx
0x18000360f  lea     rcx, stru_18007D2E8
0x180003616  call    cs:__imp_IISInitializeCriticalSection
0x18000361c  test    eax, eax
0x18000361e  jnz     short loc_180003639
0x180003620  call    cs:__imp_GetLastError
0x180003626  mov     ebx, eax
0x180003628  test    eax, eax
0x18000362a  jle     short loc_180003635
0x18000362c  movzx   ebx, ax
0x18000362f  or      ebx, 80070000h
0x180003635  mov     [rsp+48h+var_18], ebx
0x180003639  jmp     short loc_180003644
0x18000363b  mov     ebx, 8000FFFFh
0x180003640  mov     [rsp+48h+var_18], ebx
0x180003644  test    ebx, ebx
0x180003646  js      loc_180025466
0x18000364c  or      cs:dword_18007D2BC, 2
0x180003653  xor     r9d, r9d; lpName
0x180003656  xor     r8d, r8d; bInitialState
0x180003659  lea     edx, [r9+1]; bManualReset
0x18000365d  xor     ecx, ecx; lpEventAttributes
0x18000365f  call    cs:__imp_CreateEventA
0x180003665  mov     cs:hEvent, rax
0x18000366c  mov     ecx, 8007000Eh
0x180003671  test    rax, rax
0x180003674  cmovz   ebx, ecx
0x180003677  test    ebx, ebx
0x180003679  js      loc_180025466
0x18000367f  mov     [rsp+48h+lpThreadId], 0; lpThreadId
0x180003688  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x180003690  xor     r9d, r9d; lpParameter
0x180003693  lea     r8, ?WatchThread@CViperReqManager@@CAKPEAX@Z; lpStartAddress
0x18000369a  xor     edx, edx; dwStackSize
0x18000369c  xor     ecx, ecx; lpThreadAttributes
0x18000369e  call    cs:__imp_CreateThread
0x1800036a4  mov     cs:qword_18007D320, rax
0x1800036ab  test    rax, rax
0x1800036ae  jz      loc_180025448
0x1800036b4  test    ebx, ebx
0x1800036b6  js      loc_180025466
0x1800036bc  test    byte ptr cs:?g_AspRegistryParams@@3VCAspRegistryParams@@A, 1; CAspRegistryParams g_AspRegistryParams
0x1800036c3  jnz     loc_180025482
0x1800036c9  mov     eax, ebx
0x1800036cb  add     rsp, 40h
0x1800036cf  pop     rbx
0x1800036d0  retn
0x1800036d1  xor     eax, eax
0x1800036d3  jmp     short loc_1800036CB
0x180025448  call    cs:__imp_GetLastError
0x18002544e  mov     ebx, eax
0x180025450  test    eax, eax
0x180025452  jle     loc_1800036B4
0x180025458  movzx   ebx, ax
0x18002545b  or      ebx, 80070000h
0x180025461  jmp     loc_1800036B4
0x180025466  mov     rcx, cs:hEvent; hObject
0x18002546d  test    rcx, rcx
0x180025470  jz      loc_1800036BC
0x180025476  call    cs:__imp_CloseHandle
0x18002547c  nop
0x18002547d  jmp     loc_1800036BC
0x180025482  mov     ecx, cs:Data
0x180025488  neg     ecx
0x18002548a  sbb     edx, edx
0x18002548c  not     edx
0x18002548e  and     edx, 8
0x180025491  mov     ecx, cs:dword_18007D2BC
0x180025497  and     ecx, 0FFFFFFF7h
0x18002549a  or      edx, ecx
0x18002549c  mov     cs:dword_18007D2BC, edx
0x1800254a2  jmp     loc_1800036C9
```
