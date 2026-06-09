# vt::CVTSingleton<CTaskManager>::SingletonOp(vt::CVTSingleton<CTaskManager>::eSingletonOp)

- ea: `0x1800b87a0`
- end: `0x1800b88f7`
- name: `?SingletonOp@?$CVTSingleton@VCTaskManager@@@vt@@KAJW4eSingletonOp@12@@Z`
- size: `343`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180032f34`

## callees

- `0x18000290c`
- `0x1800b6be4`
- `0x1800b80b8`
- `0x1800b87a0`
- `0x1800b8900`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800b88d6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800b88d6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800b87f0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800b87f0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800b87bc`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800b87bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b87ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b88b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b87ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b88b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b88df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b88df`

## pseudocode

```c
signed int __fastcall vt::CVTSingleton<CTaskManager>::SingletonOp(int a1)
{
  HANDLE MutexW; // rax
  void *v3; // rsi
  signed int result; // eax
  DWORD v5; // eax
  signed int v6; // ebx
  int v7; // eax
  char *v8; // rax
  unsigned int v9; // edx
  vt::CCritSection *v10; // rdi
  int v11; // edx
  signed int LastError; // eax

  MutexW = CreateMutexW(0, 0, L"Local\\Microsoft:VisionTools:GlobalsMutex");
  v3 = MutexW;
  if ( MutexW )
  {
    v5 = WaitForSingleObjectEx(MutexW, 0xFFFFFFFF, 0);
    if ( v5 )
    {
      if ( v5 == -1 )
      {
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_24;
      }
    }
    else
    {
      v6 = 0;
      if ( a1 != 1 )
      {
        if ( vt::CVTSingleton<CTaskManager>::m_singletonInstance )
        {
          ++vt::CVTSingleton<CTaskManager>::m_uRefCount;
        }
        else
        {
          v8 = (char *)operator new(0x40u, (const struct std::nothrow_t *)&byte_18014FFA5);
          v10 = (vt::CCritSection *)v8;
          if ( v8 )
          {
            *v8 = 0;
            *((_QWORD *)v8 + 6) = 0;
            *((_QWORD *)v8 + 7) = 0;
            v6 = vt::CSystem::CThreadPool::Startup((vt::CSystem::CThreadPool *)(v8 + 48), v9);
            if ( v6 >= 0 )
              v6 = vt::CCritSection::Startup(v10, v11);
            if ( v6 )
            {
              vt::CVTSingleton<CTaskManager>::`scalar deleting destructor'(v10);
            }
            else
            {
              vt::CVTSingleton<CTaskManager>::m_singletonInstance = v10;
              vt::CVTSingleton<CTaskManager>::m_uRefCount = 1;
            }
          }
          else
          {
            v6 = -2147024882;
          }
        }
        goto LABEL_24;
      }
      v7 = vt::CVTSingleton<CTaskManager>::m_uRefCount;
      if ( vt::CVTSingleton<CTaskManager>::m_uRefCount )
      {
        --vt::CVTSingleton<CTaskManager>::m_uRefCount;
        if ( v7 == 1 )
        {
          if ( vt::CVTSingleton<CTaskManager>::m_singletonInstance )
            vt::CVTSingleton<CTaskManager>::`scalar deleting destructor'(vt::CVTSingleton<CTaskManager>::m_singletonInstance);
          vt::CVTSingleton<CTaskManager>::m_singletonInstance = 0;
        }
        goto LABEL_24;
      }
    }
    v6 = -2147418113;
LABEL_24:
    ReleaseMutex(v3);
    CloseHandle(v3);
    return v6;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800b87a0  mov     [rsp+arg_0], rbx
0x1800b87a5  mov     [rsp+arg_10], rsi
0x1800b87aa  push    rdi
0x1800b87ab  sub     rsp, 20h
0x1800b87af  mov     edi, ecx
0x1800b87b1  lea     r8, Name; "Local\\Microsoft:VisionTools:GlobalsMut"...
0x1800b87b8  xor     ecx, ecx; lpMutexAttributes
0x1800b87ba  xor     edx, edx; bInitialOwner
0x1800b87bc  call    cs:__imp_CreateMutexW
0x1800b87c2  mov     rsi, rax
0x1800b87c5  test    rax, rax
0x1800b87c8  jnz     short loc_1800B87E5
0x1800b87ca  call    cs:__imp_GetLastError
0x1800b87d0  test    eax, eax
0x1800b87d2  jle     loc_1800B88E7
0x1800b87d8  movzx   eax, ax
0x1800b87db  or      eax, 80070000h
0x1800b87e0  jmp     loc_1800B88E7
0x1800b87e5  or      ebx, 0FFFFFFFFh
0x1800b87e8  xor     r8d, r8d; bAlertable
0x1800b87eb  mov     edx, ebx; dwMilliseconds
0x1800b87ed  mov     rcx, rsi; hHandle
0x1800b87f0  call    cs:__imp_WaitForSingleObjectEx
0x1800b87f6  test    eax, eax
0x1800b87f8  jnz     loc_1800B88B3
0x1800b87fe  xor     ebx, ebx
0x1800b8800  cmp     edi, 1
0x1800b8803  jnz     short loc_1800B883E
0x1800b8805  mov     eax, cs:?m_uRefCount@?$CVTSingleton@VCTaskManager@@@vt@@1JA; long vt::CVTSingleton<CTaskManager>::m_uRefCount
0x1800b880b  test    eax, eax
0x1800b880d  jz      loc_1800B88CE
0x1800b8813  sub     eax, edi
0x1800b8815  mov     cs:?m_uRefCount@?$CVTSingleton@VCTaskManager@@@vt@@1JA, eax; long vt::CVTSingleton<CTaskManager>::m_uRefCount
0x1800b881b  jnz     loc_1800B88D3
0x1800b8821  mov     rcx, cs:?m_singletonInstance@?$CVTSingleton@VCTaskManager@@@vt@@1PEAV12@EA; void *
0x1800b8828  test    rcx, rcx
0x1800b882b  jz      short loc_1800B8832
0x1800b882d  call    ??_G?$CVTSingleton@VCTaskManager@@@vt@@QEAAPEAXI@Z; vt::CVTSingleton<CTaskManager>::`scalar deleting destructor'(uint)
0x1800b8832  mov     cs:?m_singletonInstance@?$CVTSingleton@VCTaskManager@@@vt@@1PEAV12@EA, rbx; vt::CVTSingleton<CTaskManager> * vt::CVTSingleton<CTaskManager>::m_singletonInstance
0x1800b8839  jmp     loc_1800B88D3
0x1800b883e  cmp     cs:?m_singletonInstance@?$CVTSingleton@VCTaskManager@@@vt@@1PEAV12@EA, rbx; vt::CVTSingleton<CTaskManager> * vt::CVTSingleton<CTaskManager>::m_singletonInstance
0x1800b8845  jnz     short loc_1800B88AB
0x1800b8847  lea     rdx, byte_18014FFA5; struct std::nothrow_t *
0x1800b884e  mov     ecx, 40h ; '@'; unsigned __int64
0x1800b8853  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800b8858  mov     rdi, rax
0x1800b885b  test    rax, rax
0x1800b885e  jz      short loc_1800B88A4
0x1800b8860  mov     [rax], bl
0x1800b8862  lea     rcx, [rax+30h]; this
0x1800b8866  mov     [rax+30h], rbx
0x1800b886a  mov     [rax+38h], rbx
0x1800b886e  call    ?Startup@CThreadPool@CSystem@vt@@QEAAJK@Z; vt::CSystem::CThreadPool::Startup(ulong)
0x1800b8873  mov     ebx, eax
0x1800b8875  test    eax, eax
0x1800b8877  js      short loc_1800B8883
0x1800b8879  mov     rcx, rdi; this
0x1800b887c  call    ?Startup@CCritSection@vt@@QEAAJH@Z; vt::CCritSection::Startup(int)
0x1800b8881  mov     ebx, eax
0x1800b8883  test    ebx, ebx
0x1800b8885  jnz     short loc_1800B889A
0x1800b8887  mov     cs:?m_singletonInstance@?$CVTSingleton@VCTaskManager@@@vt@@1PEAV12@EA, rdi; vt::CVTSingleton<CTaskManager> * vt::CVTSingleton<CTaskManager>::m_singletonInstance
0x1800b888e  mov     cs:?m_uRefCount@?$CVTSingleton@VCTaskManager@@@vt@@1JA, 1; long vt::CVTSingleton<CTaskManager>::m_uRefCount
0x1800b8898  jmp     short loc_1800B88D3
0x1800b889a  mov     rcx, rdi; void *
0x1800b889d  call    ??_G?$CVTSingleton@VCTaskManager@@@vt@@QEAAPEAXI@Z; vt::CVTSingleton<CTaskManager>::`scalar deleting destructor'(uint)
0x1800b88a2  jmp     short loc_1800B88D3
0x1800b88a4  mov     ebx, 8007000Eh
0x1800b88a9  jmp     short loc_1800B88D3
0x1800b88ab  inc     cs:?m_uRefCount@?$CVTSingleton@VCTaskManager@@@vt@@1JA; long vt::CVTSingleton<CTaskManager>::m_uRefCount
0x1800b88b1  jmp     short loc_1800B88D3
0x1800b88b3  cmp     eax, ebx
0x1800b88b5  jnz     short loc_1800B88CE
0x1800b88b7  call    cs:__imp_GetLastError
0x1800b88bd  mov     ebx, eax
0x1800b88bf  test    eax, eax
0x1800b88c1  jle     short loc_1800B88D3
0x1800b88c3  movzx   ebx, ax
0x1800b88c6  or      ebx, 80070000h
0x1800b88cc  jmp     short loc_1800B88D3
0x1800b88ce  mov     ebx, 8000FFFFh
0x1800b88d3  mov     rcx, rsi; hMutex
0x1800b88d6  call    cs:__imp_ReleaseMutex
0x1800b88dc  mov     rcx, rsi; hObject
0x1800b88df  call    cs:__imp_CloseHandle
0x1800b88e5  mov     eax, ebx
0x1800b88e7  mov     rbx, [rsp+28h+arg_0]
0x1800b88ec  mov     rsi, [rsp+28h+arg_10]
0x1800b88f1  add     rsp, 20h
0x1800b88f5  pop     rdi
0x1800b88f6  retn
```
