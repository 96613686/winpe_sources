# DpspShutdownServiceThreads(void * *,ulong,ulong *)

- ea: `0x18000f2f4`
- end: `0x18000f3c7`
- name: `?DpspShutdownServiceThreads@@YAXPEAPEAXKPEAK@Z`
- size: `211`
- prototype: `void __fastcall(void **, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000f774`

## callees

- `0x180001768`
- `0x180009090`
- `0x18000f2f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000f369`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000f369`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f3a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f3a9`

## string_xrefs

- `0x18000f382`: `DpspShutdownServiceThreads`

## pseudocode

```c
void __fastcall DpspShutdownServiceThreads(void **a1, __int64 a2, unsigned int *a3)
{
  __int64 v4; // rbx
  DWORD v5; // eax
  __int64 v6; // rdi
  char *v7; // rcx

  v4 = 0;
  do
  {
    if ( !*(&g_WorkerThreadHandles + v4) )
      break;
    v4 = (unsigned int)(v4 + 1);
  }
  while ( (unsigned int)v4 < 2 );
  if ( (_DWORD)v4 )
  {
    while ( 1 )
    {
      v5 = WaitForMultipleObjectsEx(v4, &g_WorkerThreadHandles, 1, 0x3E8u, 0);
      if ( !v5 )
        break;
      if ( v5 == -1 || v5 == 128 )
      {
        WdipTraceError(
          (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsstate.cpp",
          (__int64)L"DpspShutdownServiceThreads",
          2894,
          (const wchar_t *)L"WaitForMultipleObjects failed");
        break;
      }
      DpsNotifySvc(15, 3u, *a3, 0xBB8u, 0);
      ++*a3;
    }
    v6 = 0;
    do
    {
      v7 = (char *)*(&g_WorkerThreadHandles + v6);
      if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        CloseHandle(v7);
        *(&g_WorkerThreadHandles + v6) = 0;
      }
      v6 = (unsigned int)(v6 + 1);
    }
    while ( (unsigned int)v6 < (unsigned int)v4 );
  }
}

```

## disassembly

```asm
0x18000f2f4  push    rbx
0x18000f2f6  push    rsi
0x18000f2f7  push    rdi
0x18000f2f8  push    r14
0x18000f2fa  sub     rsp, 38h
0x18000f2fe  mov     rdi, r8
0x18000f301  lea     r14, g_WorkerThreadHandles
0x18000f308  xor     ebx, ebx
0x18000f30a  cmp     qword ptr [r14+rbx*8], 0
0x18000f30f  jz      short loc_18000F318
0x18000f311  inc     ebx
0x18000f313  cmp     ebx, 2
0x18000f316  jb      short loc_18000F30A
0x18000f318  test    ebx, ebx
0x18000f31a  jz      loc_18000F3BD
0x18000f320  mov     esi, 3E8h
0x18000f325  jmp     short loc_18000F353
0x18000f327  cmp     eax, 0FFFFFFFFh
0x18000f32a  jz      short loc_18000F375
0x18000f32c  cmp     eax, 80h
0x18000f331  jz      short loc_18000F375
0x18000f333  mov     r8d, [rdi]
0x18000f336  mov     edx, 3
0x18000f33b  mov     r9d, 0BB8h
0x18000f341  mov     [rsp+58h+bAlertable], 0
0x18000f349  lea     ecx, [rdx+0Ch]
0x18000f34c  call    DpsNotifySvc
0x18000f351  inc     dword ptr [rdi]
0x18000f353  mov     r9d, esi; dwMilliseconds
0x18000f356  mov     [rsp+58h+bAlertable], 0; Args
0x18000f35e  mov     r8d, 1; bWaitAll
0x18000f364  mov     rdx, r14; lpHandles
0x18000f367  mov     ecx, ebx; nCount
0x18000f369  call    cs:__imp_WaitForMultipleObjectsEx
0x18000f36f  test    eax, eax
0x18000f371  jnz     short loc_18000F327
0x18000f373  jmp     short loc_18000F395
0x18000f375  lea     r9, aWaitformultipl; "WaitForMultipleObjects failed"
0x18000f37c  mov     r8d, 0B4Eh; int
0x18000f382  lea     rdx, aDpspshutdownse; "DpspShutdownServiceThreads"
0x18000f389  lea     rcx, aClientcoreBase_8; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000f390  call    WdipTraceError
0x18000f395  xor     edi, edi
0x18000f397  test    ebx, ebx
0x18000f399  jz      short loc_18000F3BD
0x18000f39b  mov     rcx, [r14+rdi*8]; hObject
0x18000f39f  lea     rax, [rcx-1]
0x18000f3a3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000f3a7  ja      short loc_18000F3B7
0x18000f3a9  call    cs:__imp_CloseHandle
0x18000f3af  mov     qword ptr [r14+rdi*8], 0
0x18000f3b7  inc     edi
0x18000f3b9  cmp     edi, ebx
0x18000f3bb  jb      short loc_18000F39B
0x18000f3bd  add     rsp, 38h
0x18000f3c1  pop     r14
0x18000f3c3  pop     rdi
0x18000f3c4  pop     rsi
0x18000f3c5  pop     rbx
0x18000f3c6  retn
```
