# PrintConfig::CPrinterExtensionManager::StartPrinterQueueEnumerationThread(void)

- ea: `0x18008cb6c`
- end: `0x18008cd72`
- name: `?StartPrinterQueueEnumerationThread@CPrinterExtensionManager@PrintConfig@@AEAAXXZ`
- size: `518`
- prototype: `void __fastcall(PrintConfig::CPrinterExtensionManager *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180087be0`
- `0x1800890f0`

## callees

- `0x180004564`
- `0x18000f830`
- `0x1800197b4`
- `0x18008cb6c`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18008cbbd`
- `KERNEL32!CloseHandle` at `0x18008cc2a`
- `KERNEL32!CloseHandle` at `0x18008cbbd`
- `KERNEL32!CloseHandle` at `0x18008cc2a`
- `KERNEL32!GetLastError` at `0x18008cc77`
- `KERNEL32!GetLastError` at `0x18008ccab`
- `KERNEL32!GetLastError` at `0x18008cd0b`
- `KERNEL32!GetLastError` at `0x18008cd3f`
- `KERNEL32!GetLastError` at `0x18008cc77`
- `KERNEL32!GetLastError` at `0x18008ccab`
- `KERNEL32!GetLastError` at `0x18008cd0b`
- `KERNEL32!GetLastError` at `0x18008cd3f`
- `KERNEL32!CreateEventW` at `0x18008cb9d`
- `KERNEL32!CreateEventW` at `0x18008cb9d`
- `KERNEL32!CreateThread` at `0x18008cc0a`
- `KERNEL32!CreateThread` at `0x18008cc0a`

## pseudocode

```c
void __fastcall PrintConfig::CPrinterExtensionManager::StartPrinterQueueEnumerationThread(
        PrintConfig::CPrinterExtensionManager *this)
{
  HANDLE EventW; // rax
  char *v3; // rcx
  HANDLE v4; // rdi
  HANDLE Thread; // rax
  char *v6; // rcx
  HANDLE v7; // rdi
  signed int LastError; // eax
  signed int v9; // eax
  signed int v10; // eax
  signed int v11; // eax
  _BYTE pExceptionObject[40]; // [rsp+30h] [rbp-28h] BYREF

  if ( *((_DWORD *)this + 67) && *((_BYTE *)this + 272) )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    v3 = (char *)*((_QWORD *)this + 30);
    v4 = EventW;
    if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v3);
    *((_QWORD *)this + 30) = v4;
    if ( (((unsigned __int64)v4 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          0x43u,
          &WPP_f0578d27b884356b8893b94b89c0652f_Traceguids,
          LastError);
      }
      v9 = GetLastError();
      if ( v9 > 0 )
        v9 = (unsigned __int16)v9 | 0x80070000;
      hr_error::hr_error((hr_error *)pExceptionObject, v9);
      throw (hr_error *)pExceptionObject;
    }
    (*(void (__fastcall **)(PrintConfig::CPrinterExtensionManager *))(*(_QWORD *)this + 8LL))(this);
    Thread = CreateThread(
               0,
               0,
               (LPTHREAD_START_ROUTINE)PrintConfig::CPrinterExtensionManager::GetPrinterQueuesThreadProc,
               this,
               0,
               0);
    v6 = (char *)*((_QWORD *)this + 29);
    v7 = Thread;
    if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v6);
    *((_QWORD *)this + 29) = v7;
    if ( (((unsigned __int64)v7 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      (*(void (__fastcall **)(PrintConfig::CPrinterExtensionManager *))(*(_QWORD *)this + 16LL))(this);
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        v10 = GetLastError();
        if ( v10 > 0 )
          v10 = (unsigned __int16)v10 | 0x80070000;
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 0x44u, &WPP_f0578d27b884356b8893b94b89c0652f_Traceguids, v10);
      }
      v11 = GetLastError();
      if ( v11 > 0 )
        v11 = (unsigned __int16)v11 | 0x80070000;
      hr_error::hr_error((hr_error *)pExceptionObject, v11);
      throw (hr_error *)pExceptionObject;
    }
  }
}

```

## disassembly

```asm
0x18008cb6c  mov     [rsp+arg_0], rbx
0x18008cb71  push    rdi
0x18008cb72  sub     rsp, 50h
0x18008cb76  cmp     dword ptr [rcx+10Ch], 0
0x18008cb7d  mov     rbx, rcx
0x18008cb80  jz      loc_18008CC4D
0x18008cb86  cmp     byte ptr [rcx+110h], 0
0x18008cb8d  jz      loc_18008CC4D
0x18008cb93  xor     r9d, r9d; lpName
0x18008cb96  xor     r8d, r8d; bInitialState
0x18008cb99  xor     edx, edx; bManualReset
0x18008cb9b  xor     ecx, ecx; lpEventAttributes
0x18008cb9d  call    cs:__imp_CreateEventW
0x18008cba4  nop     dword ptr [rax+rax+00h]
0x18008cba9  mov     rcx, [rbx+0F0h]; hObject
0x18008cbb0  mov     rdi, rax
0x18008cbb3  lea     rdx, [rcx-1]
0x18008cbb7  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18008cbbb  ja      short loc_18008CBC9
0x18008cbbd  call    cs:__imp_CloseHandle
0x18008cbc4  nop     dword ptr [rax+rax+00h]
0x18008cbc9  lea     rax, [rdi+1]
0x18008cbcd  mov     [rbx+0F0h], rdi
0x18008cbd4  test    rax, 0FFFFFFFFFFFFFFFEh
0x18008cbda  jz      short loc_18008CC59
0x18008cbdc  mov     rax, [rbx]
0x18008cbdf  mov     rcx, rbx
0x18008cbe2  mov     rax, [rax+8]
0x18008cbe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008cbeb  mov     r9, rbx; lpParameter
0x18008cbee  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x18008cbf7  lea     r8, ?GetPrinterQueuesThreadProc@CPrinterExtensionManager@PrintConfig@@CAKPEAX@Z; lpStartAddress
0x18008cbfe  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x18008cc06  xor     edx, edx; dwStackSize
0x18008cc08  xor     ecx, ecx; lpThreadAttributes
0x18008cc0a  call    cs:__imp_CreateThread
0x18008cc11  nop     dword ptr [rax+rax+00h]
0x18008cc16  mov     rcx, [rbx+0E8h]; hObject
0x18008cc1d  mov     rdi, rax
0x18008cc20  lea     rdx, [rcx-1]
0x18008cc24  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18008cc28  ja      short loc_18008CC36
0x18008cc2a  call    cs:__imp_CloseHandle
0x18008cc31  nop     dword ptr [rax+rax+00h]
0x18008cc36  lea     rax, [rdi+1]
0x18008cc3a  mov     [rbx+0E8h], rdi
0x18008cc41  test    rax, 0FFFFFFFFFFFFFFFEh
0x18008cc47  jz      loc_18008CCDE
0x18008cc4d  mov     rbx, [rsp+58h+arg_0]
0x18008cc52  add     rsp, 50h
0x18008cc56  pop     rdi
0x18008cc57  retn
0x18008cc59  mov     rcx, cs:WPP_GLOBAL_Control
0x18008cc60  lea     rax, WPP_GLOBAL_Control
0x18008cc67  mov     ebx, 80070000h
0x18008cc6c  cmp     rcx, rax
0x18008cc6f  jz      short loc_18008CCAB
0x18008cc71  test    byte ptr [rcx+44h], 1
0x18008cc75  jz      short loc_18008CCAB
0x18008cc77  call    cs:__imp_GetLastError
0x18008cc7e  nop     dword ptr [rax+rax+00h]
0x18008cc83  test    eax, eax
0x18008cc85  jle     short loc_18008CC8C
0x18008cc87  movzx   eax, ax
0x18008cc8a  or      eax, ebx
0x18008cc8c  mov     rcx, cs:WPP_GLOBAL_Control
0x18008cc93  lea     r8, WPP_f0578d27b884356b8893b94b89c0652f_Traceguids
0x18008cc9a  mov     edx, 43h ; 'C'
0x18008cc9f  mov     r9d, eax
0x18008cca2  mov     rcx, [rcx+38h]
0x18008cca6  call    WPP_SF_d
0x18008ccab  call    cs:__imp_GetLastError
0x18008ccb2  nop     dword ptr [rax+rax+00h]
0x18008ccb7  test    eax, eax
0x18008ccb9  jle     short loc_18008CCC0
0x18008ccbb  movzx   eax, ax
0x18008ccbe  or      eax, ebx
0x18008ccc0  mov     edx, eax; int
0x18008ccc2  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18008ccc7  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18008cccc  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18008ccd3  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18008ccd8  call    _CxxThrowException_0
0x18008ccde  mov     rax, [rbx]
0x18008cce1  mov     rcx, rbx
0x18008cce4  mov     rax, [rax+10h]
0x18008cce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008cced  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ccf4  lea     rax, WPP_GLOBAL_Control
0x18008ccfb  mov     ebx, 80070000h
0x18008cd00  cmp     rcx, rax
0x18008cd03  jz      short loc_18008CD3F
0x18008cd05  test    byte ptr [rcx+44h], 1
0x18008cd09  jz      short loc_18008CD3F
0x18008cd0b  call    cs:__imp_GetLastError
0x18008cd12  nop     dword ptr [rax+rax+00h]
0x18008cd17  test    eax, eax
0x18008cd19  jle     short loc_18008CD20
0x18008cd1b  movzx   eax, ax
0x18008cd1e  or      eax, ebx
0x18008cd20  mov     rcx, cs:WPP_GLOBAL_Control
0x18008cd27  lea     r8, WPP_f0578d27b884356b8893b94b89c0652f_Traceguids
0x18008cd2e  mov     edx, 44h ; 'D'
0x18008cd33  mov     r9d, eax
0x18008cd36  mov     rcx, [rcx+38h]
0x18008cd3a  call    WPP_SF_d
0x18008cd3f  call    cs:__imp_GetLastError
0x18008cd46  nop     dword ptr [rax+rax+00h]
0x18008cd4b  test    eax, eax
0x18008cd4d  jle     short loc_18008CD54
0x18008cd4f  movzx   eax, ax
0x18008cd52  or      eax, ebx
0x18008cd54  mov     edx, eax; int
0x18008cd56  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18008cd5b  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18008cd60  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18008cd67  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18008cd6c  call    _CxxThrowException_0
```
