# CFolderItemCache::_EnsureBackgroundThreadExists(void)

- ea: `0x18004a914`
- end: `0x18004aa0c`
- name: `?_EnsureBackgroundThreadExists@CFolderItemCache@@AEAAJXZ`
- size: `248`
- prototype: `__int64 __fastcall(CFolderItemCache *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180049dd0`
- `0x18004a7fc`

## callees

- `0x180005360`
- `0x180012e54`
- `0x18004a914`

## import_xrefs

- `SHLWAPI!__imp_SHCreateThreadWithHandle` at `0x18004a9c7`
- `SHLWAPI!__imp_SHCreateThreadWithHandle` at `0x18004a9c7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004a961`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004a998`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004a961`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004a998`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a9fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a9fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a924`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a924`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a9e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a9e9`

## pseudocode

```c
__int64 __fastcall CFolderItemCache::_EnsureBackgroundThreadExists(CFolderItemCache *this)
{
  HDPA v2; // rax
  int Error; // ebx
  HANDLE v4; // rax
  HANDLE EventW; // rax
  void *v6; // rcx

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( *((_QWORD *)this + 7) || (v2 = DPA_Create(4), (*((_QWORD *)this + 7) = v2) != 0) )
  {
    Error = 0;
    if ( *((_QWORD *)this + 5)
      || (v4 = CreateEventW(0, 1, 0, 0), (*((_QWORD *)this + 5) = v4) != 0)
      || (Error = ResultFromKnownLastError(), Error >= 0) )
    {
      if ( !*((_QWORD *)this + 3) )
      {
        if ( !*((_QWORD *)this + 4) )
        {
          EventW = CreateEventW(0, 1, 0, 0);
          *((_QWORD *)this + 4) = EventW;
          if ( !EventW )
            Error = ResultFromKnownLastError();
        }
        if ( Error >= 0 )
        {
          if ( SHCreateThreadWithHandle((WCHAR)CFolderItemCache::s_StaticWorkerThreadProc) )
          {
            Error = 0;
            goto LABEL_17;
          }
          Error = ResultFromKnownLastError();
          if ( Error >= 0 )
            goto LABEL_17;
        }
        v6 = (void *)*((_QWORD *)this + 4);
        if ( v6 )
        {
          CloseHandle(v6);
          *((_QWORD *)this + 4) = 0;
        }
      }
    }
  }
  else
  {
    Error = -2147024882;
  }
LABEL_17:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18004a914  push    rbx
0x18004a916  push    rbp
0x18004a917  push    rsi
0x18004a918  push    rdi
0x18004a919  sub     rsp, 38h
0x18004a91d  mov     rdi, rcx
0x18004a920  add     rcx, 40h ; '@'; lpCriticalSection
0x18004a924  call    cs:__imp_EnterCriticalSection
0x18004a92a  cmp     qword ptr [rdi+38h], 0
0x18004a92f  jnz     short loc_18004A94E
0x18004a931  mov     ecx, 4; cItemGrow
0x18004a936  call    DPA_Create
0x18004a93b  mov     [rdi+38h], rax
0x18004a93f  test    rax, rax
0x18004a942  jnz     short loc_18004A94E
0x18004a944  mov     ebx, 8007000Eh
0x18004a949  jmp     loc_18004A9F7
0x18004a94e  xor     ebx, ebx
0x18004a950  cmp     [rdi+28h], rbx
0x18004a954  jnz     short loc_18004A97B
0x18004a956  xor     r9d, r9d; lpName
0x18004a959  lea     edx, [rbx+1]; bManualReset
0x18004a95c  xor     r8d, r8d; bInitialState
0x18004a95f  xor     ecx, ecx; lpEventAttributes
0x18004a961  call    cs:__imp_CreateEventW
0x18004a967  mov     [rdi+28h], rax
0x18004a96b  test    rax, rax
0x18004a96e  jnz     short loc_18004A97B
0x18004a970  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18004a975  mov     ebx, eax
0x18004a977  test    eax, eax
0x18004a979  js      short loc_18004A9F7
0x18004a97b  lea     rsi, [rdi+18h]
0x18004a97f  cmp     qword ptr [rsi], 0
0x18004a983  jnz     short loc_18004A9F7
0x18004a985  cmp     qword ptr [rdi+20h], 0
0x18004a98a  jnz     short loc_18004A9AE
0x18004a98c  xor     r9d, r9d; lpName
0x18004a98f  xor     r8d, r8d; bInitialState
0x18004a992  xor     ecx, ecx; lpEventAttributes
0x18004a994  lea     edx, [r9+1]; bManualReset
0x18004a998  call    cs:__imp_CreateEventW
0x18004a99e  mov     [rdi+20h], rax
0x18004a9a2  test    rax, rax
0x18004a9a5  jnz     short loc_18004A9AE
0x18004a9a7  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18004a9ac  mov     ebx, eax
0x18004a9ae  test    ebx, ebx
0x18004a9b0  js      short loc_18004A9E0
0x18004a9b2  xor     r9d, r9d
0x18004a9b5  mov     [rsp+58h+var_38], rsi
0x18004a9ba  xor     edx, edx
0x18004a9bc  lea     rcx, ?s_StaticWorkerThreadProc@CFolderItemCache@@CAKPEAX@Z; ch
0x18004a9c3  lea     r8d, [r9+8]
0x18004a9c7  call    cs:__imp_SHCreateThreadWithHandle
0x18004a9cd  test    eax, eax
0x18004a9cf  jz      short loc_18004A9D5
0x18004a9d1  xor     ebx, ebx
0x18004a9d3  jmp     short loc_18004A9F7
0x18004a9d5  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18004a9da  mov     ebx, eax
0x18004a9dc  test    eax, eax
0x18004a9de  jns     short loc_18004A9F7
0x18004a9e0  mov     rcx, [rdi+20h]; hObject
0x18004a9e4  test    rcx, rcx
0x18004a9e7  jz      short loc_18004A9F7
0x18004a9e9  call    cs:__imp_CloseHandle
0x18004a9ef  mov     qword ptr [rdi+20h], 0
0x18004a9f7  lea     rcx, [rdi+40h]; lpCriticalSection
0x18004a9fb  call    cs:__imp_LeaveCriticalSection
0x18004aa01  mov     eax, ebx
0x18004aa03  add     rsp, 38h
0x18004aa07  pop     rdi
0x18004aa08  pop     rsi
0x18004aa09  pop     rbp
0x18004aa0a  pop     rbx
0x18004aa0b  retn
```
