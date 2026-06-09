# MsInitializeThunk(void)

- ea: `0x1400ab2ac`
- end: `0x1400ab3b0`
- name: `?MsInitializeThunk@@YAXXZ`
- size: `260`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140087ec0`

## callees

- `0x1400ab2ac`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1400ab2da`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1400ab2da`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x1400ab2ef`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x1400ab2ef`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x1400ab309`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x1400ab309`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1400ab2c1`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1400ab2c1`

## pseudocode

```c
void MsInitializeThunk(void)
{
  __int64 v0; // rdi
  __int64 v1; // rbx
  struct MS_THREADPOOL *Threadpool; // rax
  struct MS_THREADPOOL *ThreadpoolCleanupGroup; // rax
  LARGE_INTEGER Frequency; // [rsp+50h] [rbp+8h] BYREF

  Frequency.QuadPart = 0;
  QueryPerformanceFrequency(&Frequency);
  v0 = 0;
  v1 = 0;
  do
  {
    Threadpool = CreateThreadpool(0);
    *(struct MS_THREADPOOL near **)((char *)&MspThunkThreadpool + v1) = Threadpool;
    if ( Threadpool )
    {
      ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
      *(struct MS_THREADPOOL near **)((char *)&MspThunkThreadpool + v1 + 8) = ThreadpoolCleanupGroup;
      if ( ThreadpoolCleanupGroup )
      {
        *(_DWORD *)((char *)&MspThunkThreadpool + v1 + 16) = 3;
        *(struct MS_THREADPOOL near **)((char *)&MspThunkThreadpool + v1 + 24) = 0;
        *(struct MS_THREADPOOL near **)((char *)&MspThunkThreadpool + v1 + 48) = 0;
        *(struct MS_THREADPOOL near **)((char *)&MspThunkThreadpool + v1 + 56) = 0;
        *(struct MS_THREADPOOL near **)((char *)&MspThunkThreadpool + v1 + 64) = 0;
        *(_DWORD *)((char *)&MspThunkThreadpool + v1 + 76) = 1;
        *(_DWORD *)((char *)&MspThunkThreadpool + v1 + 80) = 72;
        *(struct MS_THREADPOOL near **)((char *)&MspThunkThreadpool + v1 + 32) = ThreadpoolCleanupGroup;
        *(struct MS_THREADPOOL near **)((char *)&MspThunkThreadpool + v1 + 40) = 0;
        *(_DWORD *)((char *)&MspThunkThreadpool + v1 + 72) = 1;
      }
      else
      {
        CloseThreadpool(*(struct MS_THREADPOOL near **)((char *)&MspThunkThreadpool + v1));
        *(struct MS_THREADPOOL near **)((char *)&MspThunkThreadpool + v1) = 0;
      }
    }
    ++v0;
    v1 += 88;
  }
  while ( v0 != 4 );
  dword_140243B5C = 2;
  dword_140243BB4 = 1;
  dword_140243C0C = 0;
  dword_140243C64 = 0;
  MsQpcFrequency = Frequency.QuadPart;
  if ( !Frequency.QuadPart )
    MsQpcFrequency = 1;
}

```

## disassembly

```asm
0x1400ab2ac  push    rbx
0x1400ab2ae  push    rbp
0x1400ab2af  push    rsi
0x1400ab2b0  push    rdi
0x1400ab2b1  sub     rsp, 28h
0x1400ab2b5  xor     esi, esi
0x1400ab2b7  lea     rcx, [rsp+48h+Frequency]; lpFrequency
0x1400ab2bc  mov     qword ptr [rsp+48h+Frequency], rsi
0x1400ab2c1  call    cs:__imp_QueryPerformanceFrequency
0x1400ab2c8  nop     dword ptr [rax+rax+00h]
0x1400ab2cd  mov     edi, esi
0x1400ab2cf  lea     rbp, ?MspThunkThreadpool@@3PAUMS_THREADPOOL@@A; MS_THREADPOOL near * MspThunkThreadpool
0x1400ab2d6  mov     ebx, esi
0x1400ab2d8  xor     ecx, ecx; reserved
0x1400ab2da  call    cs:__imp_CreateThreadpool
0x1400ab2e1  nop     dword ptr [rax+rax+00h]
0x1400ab2e6  mov     [rbx+rbp], rax
0x1400ab2ea  test    rax, rax
0x1400ab2ed  jz      short loc_1400AB359
0x1400ab2ef  call    cs:__imp_CreateThreadpoolCleanupGroup
0x1400ab2f6  nop     dword ptr [rax+rax+00h]
0x1400ab2fb  mov     [rbx+rbp+8], rax
0x1400ab300  test    rax, rax
0x1400ab303  jnz     short loc_1400AB31B
0x1400ab305  mov     rcx, [rbx+rbp]; ptpp
0x1400ab309  call    cs:__imp_CloseThreadpool
0x1400ab310  nop     dword ptr [rax+rax+00h]
0x1400ab315  mov     [rbx+rbp], rsi
0x1400ab319  jmp     short loc_1400AB359
0x1400ab31b  mov     dword ptr [rbx+rbp+10h], 3
0x1400ab323  mov     [rbx+rbp+18h], rsi
0x1400ab328  mov     [rbx+rbp+30h], rsi
0x1400ab32d  mov     [rbx+rbp+38h], rsi
0x1400ab332  mov     [rbx+rbp+40h], rsi
0x1400ab337  mov     dword ptr [rbx+rbp+4Ch], 1
0x1400ab33f  mov     dword ptr [rbx+rbp+50h], 48h ; 'H'
0x1400ab347  mov     [rbx+rbp+20h], rax
0x1400ab34c  mov     [rbx+rbp+28h], rsi
0x1400ab351  mov     dword ptr [rbx+rbp+48h], 1
0x1400ab359  inc     rdi
0x1400ab35c  add     rbx, 58h ; 'X'
0x1400ab360  cmp     rdi, 4
0x1400ab364  jnz     loc_1400AB2D8
0x1400ab36a  mov     rax, qword ptr [rsp+48h+Frequency]
0x1400ab36f  mov     cs:dword_140243B5C, 2
0x1400ab379  mov     cs:dword_140243BB4, 1
0x1400ab383  mov     cs:dword_140243C0C, esi
0x1400ab389  mov     cs:dword_140243C64, esi
0x1400ab38f  mov     cs:?MsQpcFrequency@@3_KA, rax; unsigned __int64 MsQpcFrequency
0x1400ab396  test    rax, rax
0x1400ab399  jnz     short loc_1400AB3A6
0x1400ab39b  mov     cs:?MsQpcFrequency@@3_KA, 1; unsigned __int64 MsQpcFrequency
0x1400ab3a6  add     rsp, 28h
0x1400ab3aa  pop     rdi
0x1400ab3ab  pop     rsi
0x1400ab3ac  pop     rbp
0x1400ab3ad  pop     rbx
0x1400ab3ae  retn
```
