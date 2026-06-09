# CDsmTask::_StartThread(CDsmTask::DSM_PROGRESS_STATE)

- ea: `0x18000b490`
- end: `0x18000b72c`
- name: `?_StartThread@CDsmTask@@AEAAJW4DSM_PROGRESS_STATE@1@@Z`
- size: `668`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x18000fc90`

## callees

- `0x18000b490`
- `0x18000b740`
- `0x180021790`
- `0x180025294`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000b619`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000b619`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000b6b9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000b6b9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000b505`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000b505`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000b58c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000b69d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000b58c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000b69d`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000b6aa`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000b6aa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b4cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b717`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b4cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b717`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b4af`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b539`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b4af`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b539`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b64d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b6f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b64d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b6f6`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000b63f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000b63f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b690`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b690`

## pseudocode

```c
__int64 __fastcall CDsmTask::_StartThread(__int64 a1, int a2)
{
  signed int v3; // edi
  int v5; // eax
  void *v6; // rcx
  unsigned int ContainerUINT; // eax
  HANDLE Thread; // rbp
  signed int LastError; // eax
  signed int v10; // eax

  v3 = 0;
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 360));
  if ( *(_DWORD *)(a1 + 372) == 3 )
  {
    ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 360));
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_29059859b8ae329ea4a673d999cc36a2_Traceguids);
    WaitForSingleObject(*(HANDLE *)(a1 + 392), 0xFFFFFFFF);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_29059859b8ae329ea4a673d999cc36a2_Traceguids);
    AcquireSRWLockExclusive((PSRWLOCK)(a1 + 360));
  }
  v5 = *(_DWORD *)(a1 + 372);
  if ( v5 && v5 != a2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        &WPP_29059859b8ae329ea4a673d999cc36a2_Traceguids,
        *(unsigned int *)(a1 + 368),
        a2);
    v6 = *(void **)(a1 + 384);
    *(_DWORD *)(a1 + 368) = a2;
    SetEvent(v6);
  }
  if ( !*(_DWORD *)(a1 + 372) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_29059859b8ae329ea4a673d999cc36a2_Traceguids);
    ContainerUINT = GetContainerUINT((const unsigned __int16 *)(a1 + 24), &DEVPKEY_DeviceSetup_DeviceState);
    *(_QWORD *)(a1 + 420) = 0;
    *(_DWORD *)(a1 + 368) = a2;
    *(_DWORD *)(a1 + 372) = a2;
    *(_BYTE *)(a1 + 349) = ContainerUINT == 0;
    *(_QWORD *)(a1 + 376) = 0;
    *(_BYTE *)(a1 + 429) = 0;
    if ( GetModuleHandleExW(4u, (LPCWSTR)CDsmTask::_SetupUXProgressThreadEntry, (HMODULE *)(a1 + 400)) )
    {
      Thread = CreateThread(0, 0, CDsmTask::_SetupUXProgressThreadEntry, (LPVOID)a1, 0, 0);
      if ( Thread )
        goto LABEL_25;
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      if ( v3 >= 0 )
      {
LABEL_25:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_29059859b8ae329ea4a673d999cc36a2_Traceguids);
        CloseHandle(Thread);
        SetEvent(*(HANDLE *)(a1 + 384));
        ResetEvent(*(HANDLE *)(a1 + 392));
      }
      else
      {
        FreeLibrary(*(HMODULE *)(a1 + 400));
        *(_QWORD *)(a1 + 400) = 0;
        *(_DWORD *)(a1 + 372) = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_29059859b8ae329ea4a673d999cc36a2_Traceguids);
      }
    }
    else
    {
      v10 = GetLastError();
      v3 = v10;
      if ( v10 > 0 )
        v3 = (unsigned __int16)v10 | 0x80070000;
    }
  }
  ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 360));
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000b490  push    rbx
0x18000b492  push    rbp
0x18000b493  push    rsi
0x18000b494  push    rdi
0x18000b495  push    r12
0x18000b497  push    r15
0x18000b499  sub     rsp, 38h
0x18000b49d  mov     rbx, rcx
0x18000b4a0  xor     r15d, r15d
0x18000b4a3  add     rcx, 168h; SRWLock
0x18000b4aa  mov     edi, r15d
0x18000b4ad  mov     ebp, edx
0x18000b4af  call    cs:__imp_AcquireSRWLockExclusive
0x18000b4b5  cmp     dword ptr [rbx+174h], 3
0x18000b4bc  lea     r12, WPP_GLOBAL_Control
0x18000b4c3  jnz     short loc_18000B53F
0x18000b4c5  lea     rcx, [rbx+168h]; SRWLock
0x18000b4cc  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b4d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b4d9  cmp     rcx, r12
0x18000b4dc  jz      short loc_18000B4F9
0x18000b4de  test    byte ptr [rcx+1Ch], 10h
0x18000b4e2  jz      short loc_18000B4F9
0x18000b4e4  mov     rcx, [rcx+10h]
0x18000b4e8  lea     r8, WPP_29059859b8ae329ea4a673d999cc36a2_Traceguids
0x18000b4ef  mov     edx, 10h
0x18000b4f4  call    WPP_SF_
0x18000b4f9  mov     rcx, [rbx+188h]; hHandle
0x18000b500  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18000b505  call    cs:__imp_WaitForSingleObject
0x18000b50b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b512  cmp     rcx, r12
0x18000b515  jz      short loc_18000B532
0x18000b517  test    byte ptr [rcx+1Ch], 10h
0x18000b51b  jz      short loc_18000B532
0x18000b51d  mov     rcx, [rcx+10h]
0x18000b521  lea     r8, WPP_29059859b8ae329ea4a673d999cc36a2_Traceguids
0x18000b528  mov     edx, 11h
0x18000b52d  call    WPP_SF_
0x18000b532  lea     rcx, [rbx+168h]; SRWLock
0x18000b539  call    cs:__imp_AcquireSRWLockExclusive
0x18000b53f  mov     eax, [rbx+174h]
0x18000b545  test    eax, eax
0x18000b547  jz      short loc_18000B592
0x18000b549  cmp     eax, ebp
0x18000b54b  jz      short loc_18000B592
0x18000b54d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b554  cmp     rcx, r12
0x18000b557  jz      short loc_18000B57F
0x18000b559  test    byte ptr [rcx+1Ch], 10h
0x18000b55d  jz      short loc_18000B57F
0x18000b55f  mov     r9d, [rbx+170h]
0x18000b566  lea     r8, WPP_29059859b8ae329ea4a673d999cc36a2_Traceguids
0x18000b56d  mov     rcx, [rcx+10h]
0x18000b571  mov     edx, 12h
0x18000b576  mov     [rsp+68h+dwCreationFlags], ebp
0x18000b57a  call    WPP_SF_Dd
0x18000b57f  mov     rcx, [rbx+180h]; hEvent
0x18000b586  mov     [rbx+170h], ebp
0x18000b58c  call    cs:__imp_SetEvent
0x18000b592  cmp     [rbx+174h], edi
0x18000b598  jnz     loc_18000B710
0x18000b59e  mov     [rsp+68h+arg_0], r14
0x18000b5a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b5aa  cmp     rcx, r12
0x18000b5ad  jz      short loc_18000B5CA
0x18000b5af  test    byte ptr [rcx+1Ch], 10h
0x18000b5b3  jz      short loc_18000B5CA
0x18000b5b5  mov     rcx, [rcx+10h]
0x18000b5b9  lea     r8, WPP_29059859b8ae329ea4a673d999cc36a2_Traceguids
0x18000b5c0  mov     edx, 13h
0x18000b5c5  call    WPP_SF_
0x18000b5ca  lea     rcx, [rbx+18h]; unsigned __int16 *
0x18000b5ce  lea     rdx, DEVPKEY_DeviceSetup_DeviceState; struct _DEVPROPKEY *
0x18000b5d5  call    ?GetContainerUINT@@YAIPEBGAEBU_DEVPROPKEY@@@Z; GetContainerUINT(ushort const *,_DEVPROPKEY const &)
0x18000b5da  test    eax, eax
0x18000b5dc  mov     [rbx+1A4h], r15
0x18000b5e3  lea     r8, [rbx+190h]; phModule
0x18000b5ea  mov     [rbx+170h], ebp
0x18000b5f0  setz    al
0x18000b5f3  mov     [rbx+174h], ebp
0x18000b5f9  lea     rdx, ?_SetupUXProgressThreadEntry@CDsmTask@@CAKPEAX@Z; lpModuleName
0x18000b600  mov     [rbx+15Dh], al
0x18000b606  mov     ecx, 4; dwFlags
0x18000b60b  mov     [rbx+178h], r15
0x18000b612  mov     [rbx+1ADh], dil
0x18000b619  call    cs:__imp_GetModuleHandleExW
0x18000b61f  test    eax, eax
0x18000b621  jz      loc_18000B6F6
0x18000b627  mov     [rsp+68h+lpThreadId], r15; lpThreadId
0x18000b62c  lea     r8, ?_SetupUXProgressThreadEntry@CDsmTask@@CAKPEAX@Z; lpStartAddress
0x18000b633  mov     r9, rbx; lpParameter
0x18000b636  mov     [rsp+68h+dwCreationFlags], r15d; dwCreationFlags
0x18000b63b  xor     edx, edx; dwStackSize
0x18000b63d  xor     ecx, ecx; lpThreadAttributes
0x18000b63f  call    cs:__imp_CreateThread
0x18000b645  mov     rbp, rax
0x18000b648  test    rax, rax
0x18000b64b  jnz     short loc_18000B666
0x18000b64d  call    cs:__imp_GetLastError
0x18000b653  mov     edi, eax
0x18000b655  test    eax, eax
0x18000b657  jle     short loc_18000B662
0x18000b659  movzx   edi, ax
0x18000b65c  or      edi, 80070000h
0x18000b662  test    edi, edi
0x18000b664  js      short loc_18000B6B2
0x18000b666  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b66d  cmp     rcx, r12
0x18000b670  jz      short loc_18000B68D
0x18000b672  test    byte ptr [rcx+1Ch], 10h
0x18000b676  jz      short loc_18000B68D
0x18000b678  mov     rcx, [rcx+10h]
0x18000b67c  lea     r8, WPP_29059859b8ae329ea4a673d999cc36a2_Traceguids
0x18000b683  mov     edx, 14h
0x18000b688  call    WPP_SF_
0x18000b68d  mov     rcx, rbp; hObject
0x18000b690  call    cs:__imp_CloseHandle
0x18000b696  mov     rcx, [rbx+180h]; hEvent
0x18000b69d  call    cs:__imp_SetEvent
0x18000b6a3  mov     rcx, [rbx+188h]; hEvent
0x18000b6aa  call    cs:__imp_ResetEvent
0x18000b6b0  jmp     short loc_18000B70B
0x18000b6b2  mov     rcx, [rbx+190h]; hLibModule
0x18000b6b9  call    cs:__imp_FreeLibrary
0x18000b6bf  mov     [rbx+190h], r15
0x18000b6c6  mov     [rbx+174h], r15d
0x18000b6cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b6d4  cmp     rcx, r12
0x18000b6d7  jz      short loc_18000B70B
0x18000b6d9  test    byte ptr [rcx+1Ch], 4
0x18000b6dd  jz      short loc_18000B70B
0x18000b6df  mov     rcx, [rcx+10h]
0x18000b6e3  lea     r8, WPP_29059859b8ae329ea4a673d999cc36a2_Traceguids
0x18000b6ea  mov     edx, 15h
0x18000b6ef  call    WPP_SF_
0x18000b6f4  jmp     short loc_18000B70B
0x18000b6f6  call    cs:__imp_GetLastError
0x18000b6fc  mov     edi, eax
0x18000b6fe  test    eax, eax
0x18000b700  jle     short loc_18000B70B
0x18000b702  movzx   edi, ax
0x18000b705  or      edi, 80070000h
0x18000b70b  mov     r14, [rsp+68h+arg_0]
0x18000b710  lea     rcx, [rbx+168h]; SRWLock
0x18000b717  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b71d  mov     eax, edi
0x18000b71f  add     rsp, 38h
0x18000b723  pop     r15
0x18000b725  pop     r12
0x18000b727  pop     rdi
0x18000b728  pop     rsi
0x18000b729  pop     rbp
0x18000b72a  pop     rbx
0x18000b72b  retn
```
