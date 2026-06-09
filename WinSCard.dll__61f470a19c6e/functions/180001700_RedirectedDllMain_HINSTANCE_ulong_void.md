# RedirectedDllMain(HINSTANCE__ *,ulong,void *)

- ea: `0x180001700`
- end: `0x180001881`
- name: `?RedirectedDllMain@@YAHPEAUHINSTANCE__@@KPEAX@Z`
- size: `385`
- prototype: `__int64 __fastcall(HINSTANCE, unsigned int, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001210`

## callees

- `0x180001700`
- `0x18000ff10`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000183c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000183c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000172e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180001745`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000172e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180001745`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180001769`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180001789`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800017d6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800017f6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180001769`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180001789`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800017d6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800017f6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180001807`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180001807`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000179b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000179b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000182a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000182a`

## pseudocode

```c
__int64 __fastcall RedirectedDllMain(HINSTANCE a1, int a2, void *a3)
{
  void **i; // rdi
  HANDLE v5; // rcx
  unsigned int v6; // edi

  if ( a2 )
  {
    if ( a2 == 1 )
    {
      InitializeCriticalSection(&g_ProcessDetachEventCreateCS);
      g_fProcessDetachEventCreateCSInitialized = 1;
      InitializeCriticalSection(&g_BufferListCS);
      g_fBufferListCSInitialized = 1;
    }
  }
  else
  {
    if ( g_hProcessDetachEvent )
    {
      SetEvent(g_hProcessDetachEvent);
      v5 = g_hProcessDetachEvent;
      if ( g_hProcessDetachEvent )
      {
        v6 = 0;
        if ( g_lProcessDetachEventClients > 0 )
        {
          do
          {
            if ( v6 >= 0x32 )
              break;
            Sleep(0xAu);
            ++v6;
          }
          while ( g_lProcessDetachEventClients > 0 );
          v5 = g_hProcessDetachEvent;
        }
        if ( v6 < 0x32 )
          CloseHandle(v5);
      }
    }
    for ( i = (void **)g_pBufferList; g_pBufferList; i = (void **)g_pBufferList )
    {
      g_pBufferList = *i;
      MIDL_user_free(i[2]);
      MIDL_user_free(i);
    }
    if ( g_fProcessDetachEventCreateCSInitialized )
    {
      DeleteCriticalSection(&g_ProcessDetachEventCreateCS);
      g_fProcessDetachEventCreateCSInitialized = 0;
    }
    if ( g_fBufferListCSInitialized )
    {
      DeleteCriticalSection(&g_BufferListCS);
      g_fBufferListCSInitialized = 0;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180001700  mov     [rsp+arg_0], rbx
0x180001705  push    rdi
0x180001706  sub     rsp, 20h
0x18000170a  test    edx, edx
0x18000170c  jz      loc_1800017A8
0x180001712  cmp     edx, 1
0x180001715  jz      short loc_180001727
0x180001717  mov     eax, 1
0x18000171c  mov     rbx, [rsp+28h+arg_0]
0x180001721  add     rsp, 20h
0x180001725  pop     rdi
0x180001726  retn
0x180001727  lea     rcx, ?g_ProcessDetachEventCreateCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000172e  call    cs:__imp_InitializeCriticalSection
0x180001734  mov     cs:?g_fProcessDetachEventCreateCSInitialized@@3HA, 1; int g_fProcessDetachEventCreateCSInitialized
0x18000173e  lea     rcx, ?g_BufferListCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180001745  call    cs:__imp_InitializeCriticalSection
0x18000174b  mov     cs:?g_fBufferListCSInitialized@@3HA, 1; int g_fBufferListCSInitialized
0x180001755  jmp     short loc_180001717
0x180001757  mov     ebx, eax
0x180001759  cmp     cs:?g_fProcessDetachEventCreateCSInitialized@@3HA, 0; int g_fProcessDetachEventCreateCSInitialized
0x180001760  jz      short loc_180001779
0x180001762  lea     rcx, ?g_ProcessDetachEventCreateCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180001769  call    cs:__imp_DeleteCriticalSection
0x18000176f  mov     cs:?g_fProcessDetachEventCreateCSInitialized@@3HA, 0; int g_fProcessDetachEventCreateCSInitialized
0x180001779  cmp     cs:?g_fBufferListCSInitialized@@3HA, 0; int g_fBufferListCSInitialized
0x180001780  jz      short loc_180001799
0x180001782  lea     rcx, ?g_BufferListCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180001789  call    cs:__imp_DeleteCriticalSection
0x18000178f  mov     cs:?g_fBufferListCSInitialized@@3HA, 0; int g_fBufferListCSInitialized
0x180001799  mov     ecx, ebx; dwErrCode
0x18000179b  call    cs:__imp_SetLastError
0x1800017a1  xor     eax, eax
0x1800017a3  jmp     loc_18000171C
0x1800017a8  mov     rcx, cs:?g_hProcessDetachEvent@@3PEAXEA; hEvent
0x1800017af  test    rcx, rcx
0x1800017b2  jnz     short loc_180001807
0x1800017b4  xor     ebx, ebx
0x1800017b6  mov     rdi, cs:?g_pBufferList@@3PEAU_BUFFER_LIST_STRUCT@@EA; _BUFFER_LIST_STRUCT * g_pBufferList
0x1800017bd  test    rdi, rdi
0x1800017c0  jnz     loc_180001855
0x1800017c6  cmp     cs:?g_fProcessDetachEventCreateCSInitialized@@3HA, 0; int g_fProcessDetachEventCreateCSInitialized
0x1800017cd  jz      short loc_1800017E2
0x1800017cf  lea     rcx, ?g_ProcessDetachEventCreateCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800017d6  call    cs:__imp_DeleteCriticalSection
0x1800017dc  mov     cs:?g_fProcessDetachEventCreateCSInitialized@@3HA, ebx; int g_fProcessDetachEventCreateCSInitialized
0x1800017e2  cmp     cs:?g_fBufferListCSInitialized@@3HA, 0; int g_fBufferListCSInitialized
0x1800017e9  jz      loc_180001717
0x1800017ef  lea     rcx, ?g_BufferListCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800017f6  call    cs:__imp_DeleteCriticalSection
0x1800017fc  mov     cs:?g_fBufferListCSInitialized@@3HA, ebx; int g_fBufferListCSInitialized
0x180001802  jmp     loc_180001717
0x180001807  call    cs:__imp_SetEvent
0x18000180d  mov     rcx, cs:?g_hProcessDetachEvent@@3PEAXEA; hObject
0x180001814  test    rcx, rcx
0x180001817  jz      short loc_1800017B4
0x180001819  xor     ebx, ebx
0x18000181b  mov     edi, ebx
0x18000181d  cmp     cs:?g_lProcessDetachEventClients@@3JA, ebx; long g_lProcessDetachEventClients
0x180001823  jg      short loc_180001832
0x180001825  cmp     edi, 32h ; '2'
0x180001828  jnb     short loc_1800017B6
0x18000182a  call    cs:__imp_CloseHandle
0x180001830  jmp     short loc_1800017B6
0x180001832  cmp     edi, 32h ; '2'
0x180001835  jnb     short loc_18000184C
0x180001837  mov     ecx, 0Ah; dwMilliseconds
0x18000183c  call    cs:__imp_Sleep
0x180001842  inc     edi
0x180001844  cmp     cs:?g_lProcessDetachEventClients@@3JA, ebx; long g_lProcessDetachEventClients
0x18000184a  jg      short loc_180001832
0x18000184c  mov     rcx, cs:?g_hProcessDetachEvent@@3PEAXEA; void * g_hProcessDetachEvent
0x180001853  jmp     short loc_180001825
0x180001855  mov     rax, [rdi]
0x180001858  mov     cs:?g_pBufferList@@3PEAU_BUFFER_LIST_STRUCT@@EA, rax; _BUFFER_LIST_STRUCT * g_pBufferList
0x18000185f  mov     rcx, [rdi+10h]; void *
0x180001863  call    MIDL_user_free
0x180001868  mov     rcx, rdi; void *
0x18000186b  call    MIDL_user_free
0x180001870  mov     rdi, cs:?g_pBufferList@@3PEAU_BUFFER_LIST_STRUCT@@EA; _BUFFER_LIST_STRUCT * g_pBufferList
0x180001877  test    rdi, rdi
0x18000187a  jnz     short loc_180001855
0x18000187c  jmp     loc_1800017C6
```
