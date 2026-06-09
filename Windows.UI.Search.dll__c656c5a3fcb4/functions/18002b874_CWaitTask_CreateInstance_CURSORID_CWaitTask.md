# CWaitTask::CreateInstance(CURSORID,CWaitTask * *)

- ea: `0x18002b874`
- end: `0x18002b94a`
- name: `?CreateInstance@CWaitTask@@SAJW4CURSORID@@PEAPEAV1@@Z`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18002dd90`

## callees

- `0x180003d70`
- `0x18002b874`
- `0x18002d188`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002b8f3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002b8f3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002b8e1`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002b8e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b8c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b8c9`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18002b923`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18002b923`

## pseudocode

```c
__int64 __fastcall CWaitTask::CreateInstance(int a1, _QWORD *a2)
{
  unsigned int v4; // edi
  char *v5; // rax
  char *v6; // rbx
  DWORD CurrentThreadId; // eax
  HANDLE EventW; // rax

  *a2 = 0;
  v4 = -2147024882;
  v5 = (char *)operator new(0x60u, (const struct std::nothrow_t *)std::nothrow);
  v6 = v5;
  if ( v5 )
  {
    *(_DWORD *)v5 = 1;
    *((_QWORD *)v5 + 1) = 0;
    *((_QWORD *)v5 + 2) = 0;
    *((_QWORD *)v5 + 3) = 0;
    CurrentThreadId = GetCurrentThreadId();
    v6[36] = 0;
    *((_DWORD *)v6 + 8) = CurrentThreadId;
    *((_DWORD *)v6 + 10) = a1;
    v6[88] = 0;
    InitializeCriticalSection((LPCRITICAL_SECTION)(v6 + 48));
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)v6 + 2) = EventW;
    if ( EventW
      && RegisterWaitForSingleObject((PHANDLE)v6 + 1, EventW, CWaitTask::s_WaitBeforeCursing, v6, 0xC8u, 0x18u) )
    {
      _InterlockedIncrement((volatile signed __int32 *)v6);
      *a2 = v6;
      return 0;
    }
    else
    {
      CWaitTask::Release((CWaitTask *)v6);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18002b874  push    rbx
0x18002b876  push    rbp
0x18002b877  push    rsi
0x18002b878  push    rdi
0x18002b879  sub     rsp, 38h
0x18002b87d  mov     rsi, rdx
0x18002b880  mov     qword ptr [rdx], 0
0x18002b887  mov     ebp, ecx
0x18002b889  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002b890  mov     ecx, 60h ; '`'; unsigned __int64
0x18002b895  mov     edi, 8007000Eh
0x18002b89a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002b89f  mov     rbx, rax
0x18002b8a2  test    rax, rax
0x18002b8a5  jz      loc_18002B93F
0x18002b8ab  mov     dword ptr [rax], 1
0x18002b8b1  mov     qword ptr [rax+8], 0
0x18002b8b9  mov     qword ptr [rax+10h], 0
0x18002b8c1  mov     qword ptr [rax+18h], 0
0x18002b8c9  call    cs:__imp_GetCurrentThreadId
0x18002b8cf  lea     rcx, [rbx+30h]; lpCriticalSection
0x18002b8d3  mov     byte ptr [rbx+24h], 0
0x18002b8d7  mov     [rbx+20h], eax
0x18002b8da  mov     [rbx+28h], ebp
0x18002b8dd  mov     byte ptr [rbx+58h], 0
0x18002b8e1  call    cs:__imp_InitializeCriticalSection
0x18002b8e7  xor     r9d, r9d; lpName
0x18002b8ea  xor     r8d, r8d; bInitialState
0x18002b8ed  xor     ecx, ecx; lpEventAttributes
0x18002b8ef  lea     edx, [r9+1]; bManualReset
0x18002b8f3  call    cs:__imp_CreateEventW
0x18002b8f9  mov     [rbx+10h], rax
0x18002b8fd  test    rax, rax
0x18002b900  jz      short loc_18002B937
0x18002b902  lea     rcx, [rbx+8]; phNewWaitObject
0x18002b906  mov     [rsp+58h+dwFlags], 18h; dwFlags
0x18002b90e  mov     r9, rbx; Context
0x18002b911  mov     [rsp+58h+dwMilliseconds], 0C8h; dwMilliseconds
0x18002b919  lea     r8, ?s_WaitBeforeCursing@CWaitTask@@CAXPEAXE@Z; Callback
0x18002b920  mov     rdx, rax; hObject
0x18002b923  call    cs:__imp_RegisterWaitForSingleObject
0x18002b929  test    eax, eax
0x18002b92b  jz      short loc_18002B937
0x18002b92d  lock inc dword ptr [rbx]
0x18002b930  mov     [rsi], rbx
0x18002b933  xor     edi, edi
0x18002b935  jmp     short loc_18002B93F
0x18002b937  mov     rcx, rbx; this
0x18002b93a  call    ?Release@CWaitTask@@QEAAKXZ; CWaitTask::Release(void)
0x18002b93f  mov     eax, edi
0x18002b941  add     rsp, 38h
0x18002b945  pop     rdi
0x18002b946  pop     rsi
0x18002b947  pop     rbp
0x18002b948  pop     rbx
0x18002b949  retn
```
