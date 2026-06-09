# PrintConfig::CPrinterExtensionManager::StartPrinterQueueEnumerationThread(void)

- ea: `0x1800896dc`
- end: `0x1800898b1`
- name: `?StartPrinterQueueEnumerationThread@CPrinterExtensionManager@PrintConfig@@AEAAXXZ`
- size: `469`
- prototype: `void __fastcall(PrintConfig::CPrinterExtensionManager *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180084960`
- `0x180085d50`

## callees

- `0x180004424`
- `0x18000f380`
- `0x180018bbc`
- `0x1800896dc`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180089727`
- `KERNEL32!CloseHandle` at `0x180089788`
- `KERNEL32!CloseHandle` at `0x180089727`
- `KERNEL32!CloseHandle` at `0x180089788`
- `KERNEL32!GetLastError` at `0x1800897ce`
- `KERNEL32!GetLastError` at `0x1800897fc`
- `KERNEL32!GetLastError` at `0x180089856`
- `KERNEL32!GetLastError` at `0x180089884`
- `KERNEL32!GetLastError` at `0x1800897ce`
- `KERNEL32!GetLastError` at `0x1800897fc`
- `KERNEL32!GetLastError` at `0x180089856`
- `KERNEL32!GetLastError` at `0x180089884`
- `KERNEL32!CreateEventW` at `0x18008970d`
- `KERNEL32!CreateEventW` at `0x18008970d`
- `KERNEL32!CreateThread` at `0x18008976e`
- `KERNEL32!CreateThread` at `0x18008976e`

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
          67,
          &WPP_f0578d27b884356b8893b94b89c0652f_Traceguids,
          (unsigned int)LastError);
      }
      v9 = GetLastError();
      if ( v9 > 0 )
        v9 = (unsigned __int16)v9 | 0x80070000;
      hr_error::hr_error((hr_error *)pExceptionObject, v9);
      throw (hr_error *)pExceptionObject;
    }
    (*(void (__fastcall **)(PrintConfig::CPrinterExtensionManager *))(*(_QWORD *)this + 8LL))(this);
    Thread = CreateThread(0, 0, PrintConfig::CPrinterExtensionManager::GetPrinterQueuesThreadProc, this, 0, 0);
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
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          68,
          &WPP_f0578d27b884356b8893b94b89c0652f_Traceguids,
          (unsigned int)v10);
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
0x1800896dc  mov     [rsp+arg_0], rbx
0x1800896e1  push    rdi
0x1800896e2  sub     rsp, 50h
0x1800896e6  cmp     dword ptr [rcx+10Ch], 0
0x1800896ed  mov     rbx, rcx
0x1800896f0  jz      loc_1800897A5
0x1800896f6  cmp     byte ptr [rcx+110h], 0
0x1800896fd  jz      loc_1800897A5
0x180089703  xor     r9d, r9d; lpName
0x180089706  xor     r8d, r8d; bInitialState
0x180089709  xor     edx, edx; bManualReset
0x18008970b  xor     ecx, ecx; lpEventAttributes
0x18008970d  call    cs:__imp_CreateEventW
0x180089713  mov     rcx, [rbx+0F0h]; hObject
0x18008971a  mov     rdi, rax
0x18008971d  lea     rdx, [rcx-1]
0x180089721  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180089725  ja      short loc_18008972D
0x180089727  call    cs:__imp_CloseHandle
0x18008972d  lea     rax, [rdi+1]
0x180089731  mov     [rbx+0F0h], rdi
0x180089738  test    rax, 0FFFFFFFFFFFFFFFEh
0x18008973e  jz      short loc_1800897B0
0x180089740  mov     rax, [rbx]
0x180089743  mov     rcx, rbx
0x180089746  mov     rax, [rax+8]
0x18008974a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008974f  mov     r9, rbx; lpParameter
0x180089752  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x18008975b  lea     r8, ?GetPrinterQueuesThreadProc@CPrinterExtensionManager@PrintConfig@@CAKPEAX@Z; lpStartAddress
0x180089762  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x18008976a  xor     edx, edx; dwStackSize
0x18008976c  xor     ecx, ecx; lpThreadAttributes
0x18008976e  call    cs:__imp_CreateThread
0x180089774  mov     rcx, [rbx+0E8h]; hObject
0x18008977b  mov     rdi, rax
0x18008977e  lea     rdx, [rcx-1]
0x180089782  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180089786  ja      short loc_18008978E
0x180089788  call    cs:__imp_CloseHandle
0x18008978e  lea     rax, [rdi+1]
0x180089792  mov     [rbx+0E8h], rdi
0x180089799  test    rax, 0FFFFFFFFFFFFFFFEh
0x18008979f  jz      loc_180089829
0x1800897a5  mov     rbx, [rsp+58h+arg_0]
0x1800897aa  add     rsp, 50h
0x1800897ae  pop     rdi
0x1800897af  retn
0x1800897b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800897b7  lea     rax, WPP_GLOBAL_Control
0x1800897be  mov     ebx, 80070000h
0x1800897c3  cmp     rcx, rax
0x1800897c6  jz      short loc_1800897FC
0x1800897c8  test    byte ptr [rcx+44h], 1
0x1800897cc  jz      short loc_1800897FC
0x1800897ce  call    cs:__imp_GetLastError
0x1800897d4  test    eax, eax
0x1800897d6  jle     short loc_1800897DD
0x1800897d8  movzx   eax, ax
0x1800897db  or      eax, ebx
0x1800897dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800897e4  lea     r8, WPP_f0578d27b884356b8893b94b89c0652f_Traceguids
0x1800897eb  mov     edx, 43h ; 'C'
0x1800897f0  mov     r9d, eax
0x1800897f3  mov     rcx, [rcx+38h]
0x1800897f7  call    WPP_SF_d
0x1800897fc  call    cs:__imp_GetLastError
0x180089802  test    eax, eax
0x180089804  jle     short loc_18008980B
0x180089806  movzx   eax, ax
0x180089809  or      eax, ebx
0x18008980b  mov     edx, eax; int
0x18008980d  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180089812  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180089817  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18008981e  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180089823  call    _CxxThrowException_0
0x180089829  mov     rax, [rbx]
0x18008982c  mov     rcx, rbx
0x18008982f  mov     rax, [rax+10h]
0x180089833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089838  mov     rcx, cs:WPP_GLOBAL_Control
0x18008983f  lea     rax, WPP_GLOBAL_Control
0x180089846  mov     ebx, 80070000h
0x18008984b  cmp     rcx, rax
0x18008984e  jz      short loc_180089884
0x180089850  test    byte ptr [rcx+44h], 1
0x180089854  jz      short loc_180089884
0x180089856  call    cs:__imp_GetLastError
0x18008985c  test    eax, eax
0x18008985e  jle     short loc_180089865
0x180089860  movzx   eax, ax
0x180089863  or      eax, ebx
0x180089865  mov     rcx, cs:WPP_GLOBAL_Control
0x18008986c  lea     r8, WPP_f0578d27b884356b8893b94b89c0652f_Traceguids
0x180089873  mov     edx, 44h ; 'D'
0x180089878  mov     r9d, eax
0x18008987b  mov     rcx, [rcx+38h]
0x18008987f  call    WPP_SF_d
0x180089884  call    cs:__imp_GetLastError
0x18008988a  test    eax, eax
0x18008988c  jle     short loc_180089893
0x18008988e  movzx   eax, ax
0x180089891  or      eax, ebx
0x180089893  mov     edx, eax; int
0x180089895  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18008989a  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18008989f  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800898a6  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x1800898ab  call    _CxxThrowException_0
```
