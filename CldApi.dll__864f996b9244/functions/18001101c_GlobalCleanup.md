# GlobalCleanup

- ea: `0x18001101c`
- end: `0x1800111f9`
- name: `GlobalCleanup`
- size: `477`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800025ec`

## callees

- `0x18001101c`
- `0x18001a3a0`
- `0x18001a43c`
- `0x18001a4c4`
- `0x18001b720`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001109f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001109f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800110ed`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800110ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800110ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011129`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800110ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011129`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800110c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001113b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800110c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001113b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001114f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001114f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180011058`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180011058`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011167`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011180`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011199`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800111b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011167`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011180`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011199`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800111b9`

## pseudocode

```c
void GlobalCleanup()
{
  HANDLE ProcessHeap; // rax
  HANDLE v1; // rax

  while ( byte_180028915 )
  {
    if ( _InterlockedIncrement(&dword_180028910) == 1 )
    {
      if ( !byte_180028915 )
      {
        _InterlockedAdd(&dword_180028910, 0xFFFFFFFF);
        return;
      }
      if ( byte_180028914 )
      {
        if ( byte_180028930 )
        {
          TlgUnregisterAggregateProvider();
          byte_180028930 = 0;
        }
        if ( byte_180028938 )
        {
          RtlAcquireSRWLockExclusive(&qword_180028940);
          if ( lpMem )
          {
            ProcessHeap = GetProcessHeap();
            HeapFree(ProcessHeap, 0, lpMem);
            lpMem = 0;
            dword_180028948 = 0;
          }
          qword_180028960 = 0;
          dword_180028958 = 0;
          byte_180028938 = 0;
          RtlReleaseSRWLockExclusive(&qword_180028940);
        }
        if ( byte_1800289B0 )
          TlmiUninitializeRunawayHydrationDetection();
        if ( byte_180028A58 )
          TlmiUninitializeHydrationPerformanceTracking();
        if ( byte_180028968 )
          TlmiUninitializeFirstRunExpStatus();
        if ( String2.Buffer )
        {
          v1 = GetProcessHeap();
          HeapFree(v1, 0, String2.Buffer);
          String2.Buffer = 0;
        }
        DeleteCriticalSection(&_G);
        dword_180028BE8 = 0;
        if ( hPort != (HANDLE)-1LL )
        {
          CloseHandle(hPort);
          hPort = (HANDLE)-1LL;
        }
        if ( *(&hPort + 1) != (HANDLE)-1LL )
        {
          CloseHandle(*(&hPort + 1));
          *(&hPort + 1) = (HANDLE)-1LL;
        }
        if ( CompletionPort )
        {
          CloseHandle(CompletionPort);
          CompletionPort = 0;
        }
        if ( qword_180028D00 != (HANDLE)-1LL )
        {
          CloseHandle(qword_180028D00);
          qword_180028D00 = (HANDLE)-1LL;
        }
        byte_180028914 = 0;
      }
      byte_180028915 = 0;
      _InterlockedAdd(&dword_180028910, 0xFFFFFFFF);
    }
    else
    {
      _InterlockedAdd(&dword_180028910, 0xFFFFFFFF);
      Sleep(0xAu);
    }
  }
}

```

## disassembly

```asm
0x18001101c  mov     [rsp+arg_0], rbx
0x180011021  push    rdi
0x180011022  sub     rsp, 20h
0x180011026  xor     ebx, ebx
0x180011028  cmp     cs:byte_180028915, bl
0x18001102e  jz      loc_1800111EE
0x180011034  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180011038  mov     eax, 1
0x18001103d  lock xadd cs:dword_180028910, eax
0x180011045  inc     eax
0x180011047  cmp     eax, 1
0x18001104a  jz      short loc_180011063
0x18001104c  lock add cs:dword_180028910, edi
0x180011053  mov     ecx, 0Ah; dwMilliseconds
0x180011058  call    cs:__imp_Sleep
0x18001105e  jmp     loc_1800111D9
0x180011063  cmp     cs:byte_180028915, bl
0x180011069  jz      loc_1800111E7
0x18001106f  cmp     cs:byte_180028914, bl
0x180011075  jz      loc_1800111CC
0x18001107b  cmp     cs:byte_180028930, bl
0x180011081  jz      short loc_18001108E
0x180011083  call    TlgUnregisterAggregateProvider
0x180011088  mov     cs:byte_180028930, bl
0x18001108e  mov     al, cs:byte_180028938
0x180011094  test    al, al
0x180011096  jz      short loc_1800110F3
0x180011098  lea     rcx, qword_180028940
0x18001109f  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800110a5  cmp     cs:lpMem, rbx
0x1800110ac  jz      short loc_1800110D3
0x1800110ae  call    cs:__imp_GetProcessHeap
0x1800110b4  mov     r8, cs:lpMem; lpMem
0x1800110bb  xor     edx, edx; dwFlags
0x1800110bd  mov     rcx, rax; hHeap
0x1800110c0  call    cs:__imp_HeapFree
0x1800110c6  mov     cs:lpMem, rbx
0x1800110cd  mov     cs:dword_180028948, ebx
0x1800110d3  mov     cs:qword_180028960, rbx
0x1800110da  lea     rcx, qword_180028940
0x1800110e1  mov     cs:dword_180028958, ebx
0x1800110e7  mov     cs:byte_180028938, bl
0x1800110ed  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800110f3  mov     al, cs:byte_1800289B0
0x1800110f9  test    al, al
0x1800110fb  jz      short loc_180011102
0x1800110fd  call    TlmiUninitializeRunawayHydrationDetection
0x180011102  mov     al, cs:byte_180028A58
0x180011108  test    al, al
0x18001110a  jz      short loc_180011111
0x18001110c  call    TlmiUninitializeHydrationPerformanceTracking
0x180011111  mov     al, cs:byte_180028968
0x180011117  test    al, al
0x180011119  jz      short loc_180011120
0x18001111b  call    TlmiUninitializeFirstRunExpStatus
0x180011120  cmp     cs:String2.Buffer, rbx
0x180011127  jz      short loc_180011148
0x180011129  call    cs:__imp_GetProcessHeap
0x18001112f  mov     r8, cs:String2.Buffer; lpMem
0x180011136  xor     edx, edx; dwFlags
0x180011138  mov     rcx, rax; hHeap
0x18001113b  call    cs:__imp_HeapFree
0x180011141  mov     cs:String2.Buffer, rbx
0x180011148  lea     rcx, __G; lpCriticalSection
0x18001114f  call    cs:__imp_DeleteCriticalSection
0x180011155  mov     rcx, qword ptr cs:hPort; hObject
0x18001115c  mov     cs:dword_180028BE8, ebx
0x180011162  cmp     rcx, rdi
0x180011165  jz      short loc_180011174
0x180011167  call    cs:__imp_CloseHandle
0x18001116d  mov     qword ptr cs:hPort, rdi
0x180011174  mov     rcx, qword ptr cs:hPort+8; hObject
0x18001117b  cmp     rcx, rdi
0x18001117e  jz      short loc_18001118D
0x180011180  call    cs:__imp_CloseHandle
0x180011186  mov     qword ptr cs:hPort+8, rdi
0x18001118d  mov     rcx, cs:CompletionPort; hObject
0x180011194  test    rcx, rcx
0x180011197  jz      short loc_1800111A6
0x180011199  call    cs:__imp_CloseHandle
0x18001119f  mov     cs:CompletionPort, rbx
0x1800111a6  mov     rax, cs:qword_180028D00
0x1800111ad  cmp     rax, rdi
0x1800111b0  jz      short loc_1800111C6
0x1800111b2  mov     rcx, cs:qword_180028D00; hObject
0x1800111b9  call    cs:__imp_CloseHandle
0x1800111bf  mov     cs:qword_180028D00, rdi
0x1800111c6  mov     cs:byte_180028914, bl
0x1800111cc  mov     cs:byte_180028915, bl
0x1800111d2  lock add cs:dword_180028910, edi
0x1800111d9  cmp     cs:byte_180028915, bl
0x1800111df  jnz     loc_180011038
0x1800111e5  jmp     short loc_1800111EE
0x1800111e7  lock add cs:dword_180028910, edi
0x1800111ee  mov     rbx, [rsp+28h+arg_0]
0x1800111f3  add     rsp, 20h
0x1800111f7  pop     rdi
0x1800111f8  retn
```
