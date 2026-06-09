# CStorageWMIOperationTracker::FinalConstruct(void)

- ea: `0x1801310f8`
- end: `0x18013123e`
- name: `?FinalConstruct@CStorageWMIOperationTracker@@QEAAJXZ`
- size: `326`
- prototype: `__int64 __fastcall(CStorageWMIOperationTracker *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180130e28`

## callees

- `0x1801310f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180131191`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801311ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013120f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013121c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180131191`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801311ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013120f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013121c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180131167`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801311a8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801311e7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180131167`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801311a8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801311e7`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180131155`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180131155`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18013117e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801311bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801311fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18013117e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801311bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801311fe`

## pseudocode

```c
__int64 __fastcall CStorageWMIOperationTracker::FinalConstruct(CStorageWMIOperationTracker *this)
{
  char *v1; // rax
  __int64 v3; // rcx
  __int64 v4; // rdx
  char *v5; // rax
  __int64 v6; // rdx
  char *v7; // rax
  HANDLE EventW; // rax
  char *v9; // rcx
  HANDLE v10; // rdi
  HANDLE v11; // rax
  char *v12; // rcx
  HANDLE v13; // rdi
  HANDLE v14; // rax
  char *v15; // rcx
  HANDLE v16; // rdi
  unsigned int v17; // ebx
  signed int LastError; // eax

  v1 = (char *)this + 64;
  v3 = 16;
  if ( v1 )
  {
    v4 = 16;
    do
    {
      *v1++ = 0;
      --v4;
    }
    while ( v4 );
  }
  v5 = (char *)this + 48;
  if ( this != (CStorageWMIOperationTracker *)-48LL )
  {
    v6 = 16;
    do
    {
      *v5++ = 0;
      --v6;
    }
    while ( v6 );
  }
  v7 = (char *)this + 80;
  if ( this != (CStorageWMIOperationTracker *)-80LL )
  {
    do
    {
      *v7++ = 0;
      --v3;
    }
    while ( v3 );
  }
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
  EventW = CreateEventW(0, 1, 0, 0);
  v9 = (char *)*((_QWORD *)this + 12);
  v10 = EventW;
  if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v9);
  *((_QWORD *)this + 12) = v10;
  if ( !v10 || GetLastError() == 183 )
    goto LABEL_21;
  v11 = CreateEventW(0, 0, 0, 0);
  v12 = (char *)*((_QWORD *)this + 13);
  v13 = v11;
  if ( (unsigned __int64)(v12 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v12);
  *((_QWORD *)this + 13) = v13;
  if ( !v13 || GetLastError() == 183 )
    goto LABEL_21;
  v14 = CreateEventW(0, 1, 0, 0);
  v15 = (char *)*((_QWORD *)this + 14);
  v16 = v14;
  if ( (unsigned __int64)(v15 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v15);
  *((_QWORD *)this + 14) = v16;
  if ( !v16 || (v17 = 0, GetLastError() == 183) )
  {
LABEL_21:
    LastError = GetLastError();
    v17 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v17;
}

```

## disassembly

```asm
0x1801310f8  mov     [rsp+arg_0], rbx
0x1801310fd  push    rdi
0x1801310fe  sub     rsp, 20h
0x180131102  lea     rax, [rcx+40h]
0x180131106  mov     rbx, rcx
0x180131109  mov     ecx, 10h
0x18013110e  test    rax, rax
0x180131111  jz      short loc_180131121
0x180131113  mov     edx, ecx
0x180131115  mov     byte ptr [rax], 0
0x180131118  inc     rax
0x18013111b  sub     rdx, 1
0x18013111f  jnz     short loc_180131115
0x180131121  lea     rax, [rbx+30h]
0x180131125  test    rax, rax
0x180131128  jz      short loc_180131139
0x18013112a  mov     rdx, rcx
0x18013112d  mov     byte ptr [rax], 0
0x180131130  inc     rax
0x180131133  sub     rdx, 1
0x180131137  jnz     short loc_18013112D
0x180131139  lea     rax, [rbx+50h]
0x18013113d  test    rax, rax
0x180131140  jz      short loc_18013114E
0x180131142  mov     byte ptr [rax], 0
0x180131145  inc     rax
0x180131148  sub     rcx, 1
0x18013114c  jnz     short loc_180131142
0x18013114e  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x180131155  call    cs:__imp_InitializeCriticalSection
0x18013115b  xor     r9d, r9d; lpName
0x18013115e  xor     r8d, r8d; bInitialState
0x180131161  xor     ecx, ecx; lpEventAttributes
0x180131163  lea     edx, [r9+1]; bManualReset
0x180131167  call    cs:__imp_CreateEventW
0x18013116d  mov     rcx, [rbx+60h]; hObject
0x180131171  mov     rdi, rax
0x180131174  lea     rdx, [rcx-1]
0x180131178  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18013117c  ja      short loc_180131184
0x18013117e  call    cs:__imp_CloseHandle
0x180131184  mov     [rbx+60h], rdi
0x180131188  test    rdi, rdi
0x18013118b  jz      loc_18013121C
0x180131191  call    cs:__imp_GetLastError
0x180131197  cmp     eax, 0B7h
0x18013119c  jz      short loc_18013121C
0x18013119e  xor     r9d, r9d; lpName
0x1801311a1  xor     r8d, r8d; bInitialState
0x1801311a4  xor     edx, edx; bManualReset
0x1801311a6  xor     ecx, ecx; lpEventAttributes
0x1801311a8  call    cs:__imp_CreateEventW
0x1801311ae  mov     rcx, [rbx+68h]; hObject
0x1801311b2  mov     rdi, rax
0x1801311b5  lea     rdx, [rcx-1]
0x1801311b9  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1801311bd  ja      short loc_1801311C5
0x1801311bf  call    cs:__imp_CloseHandle
0x1801311c5  mov     [rbx+68h], rdi
0x1801311c9  test    rdi, rdi
0x1801311cc  jz      short loc_18013121C
0x1801311ce  call    cs:__imp_GetLastError
0x1801311d4  cmp     eax, 0B7h
0x1801311d9  jz      short loc_18013121C
0x1801311db  xor     r9d, r9d; lpName
0x1801311de  xor     r8d, r8d; bInitialState
0x1801311e1  xor     ecx, ecx; lpEventAttributes
0x1801311e3  lea     edx, [r9+1]; bManualReset
0x1801311e7  call    cs:__imp_CreateEventW
0x1801311ed  mov     rcx, [rbx+70h]; hObject
0x1801311f1  mov     rdi, rax
0x1801311f4  lea     rdx, [rcx-1]
0x1801311f8  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1801311fc  ja      short loc_180131204
0x1801311fe  call    cs:__imp_CloseHandle
0x180131204  mov     [rbx+70h], rdi
0x180131208  test    rdi, rdi
0x18013120b  jz      short loc_18013121C
0x18013120d  xor     ebx, ebx
0x18013120f  call    cs:__imp_GetLastError
0x180131215  cmp     eax, 0B7h
0x18013121a  jnz     short loc_180131231
0x18013121c  call    cs:__imp_GetLastError
0x180131222  mov     ebx, eax
0x180131224  test    eax, eax
0x180131226  jle     short loc_180131231
0x180131228  movzx   ebx, ax
0x18013122b  or      ebx, 80070000h
0x180131231  mov     eax, ebx
0x180131233  mov     rbx, [rsp+28h+arg_0]
0x180131238  add     rsp, 20h
0x18013123c  pop     rdi
0x18013123d  retn
```
