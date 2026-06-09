# CDataReaderCoordinator::StreamReaderThread(void *)

- ea: `0x1800055b0`
- end: `0x1800056be`
- name: `?StreamReaderThread@CDataReaderCoordinator@@KAKPEAX@Z`
- size: `270`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800055b0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800055dc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180005606`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800055dc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180005606`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x180005668`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x180005668`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005698`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005698`

## pseudocode

```c
__int64 __fastcall CDataReaderCoordinator::StreamReaderThread(int *Parameter)
{
  __int64 v2; // rsi
  void *v3; // rcx
  __int64 v4; // rax
  __int64 v5; // rdx
  __int64 v6; // r8
  signed int LastError; // eax
  int v9; // ecx
  int v10; // [rsp+40h] [rbp+8h] BYREF

  if ( Parameter[20] )
    return 0;
LABEL_2:
  if ( !WaitForSingleObject(*(HANDLE *)Parameter, 0xFFFFFFFF) )
  {
    v2 = *((_QWORD *)Parameter + 9);
    while ( 1 )
    {
      if ( Parameter[20] )
        return 0;
      v3 = (void *)*((_QWORD *)Parameter + 3);
      v10 = 0;
      if ( WaitForSingleObject(v3, 0xFFFFFFFF) )
        break;
      v4 = Parameter[8];
      v5 = *(_QWORD *)&Parameter[2 * v4 + 10];
      if ( !v5 )
        break;
      v6 = (unsigned int)Parameter[v4 + 16];
      if ( (_DWORD)v6 )
      {
        LastError = (*(__int64 (__fastcall **)(__int64, __int64, __int64, int *))(*(_QWORD *)v2 + 24LL))(
                      v2,
                      v5,
                      v6,
                      &v10);
        if ( LastError < 0 )
        {
          LastError = (unsigned __int16)LastError;
          v10 = 0;
          goto LABEL_15;
        }
      }
LABEL_9:
      Parameter[Parameter[8]++ + 14] = v10;
      if ( Parameter[8] >= 2 )
        Parameter[8] = 0;
      ReleaseSemaphore(*((HANDLE *)Parameter + 2), 1, 0);
      if ( !v10 )
      {
        if ( !Parameter[20] )
          goto LABEL_2;
        return 0;
      }
    }
    LastError = GetLastError();
LABEL_15:
    v9 = 1;
    if ( LastError )
      v9 = LastError;
    Parameter[20] = v9;
    goto LABEL_9;
  }
  return 0;
}

```

## disassembly

```asm
0x1800055b0  push    rdi
0x1800055b2  sub     rsp, 30h
0x1800055b6  cmp     dword ptr [rcx+50h], 0
0x1800055ba  mov     rdi, rcx
0x1800055bd  jnz     loc_1800056AD
0x1800055c3  mov     [rsp+38h+arg_8], rbx
0x1800055c8  mov     [rsp+38h+arg_10], rbp
0x1800055cd  xor     ebp, ebp
0x1800055cf  mov     [rsp+38h+arg_18], rsi
0x1800055d4  mov     rcx, [rdi]; hHandle
0x1800055d7  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x1800055dc  call    cs:__imp_WaitForSingleObject
0x1800055e2  test    eax, eax
0x1800055e4  jnz     loc_180005681
0x1800055ea  mov     rsi, [rdi+48h]
0x1800055ee  xchg    ax, ax
0x1800055f0  cmp     [rdi+50h], ebp
0x1800055f3  jnz     loc_180005681
0x1800055f9  mov     rcx, [rdi+18h]; hHandle
0x1800055fd  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180005602  mov     [rsp+38h+arg_0], ebp
0x180005606  call    cs:__imp_WaitForSingleObject
0x18000560c  test    eax, eax
0x18000560e  jnz     loc_180005698
0x180005614  movsxd  rax, dword ptr [rdi+20h]
0x180005618  mov     rdx, [rdi+rax*8+28h]
0x18000561d  test    rdx, rdx
0x180005620  jz      short loc_180005698
0x180005622  mov     r8d, [rdi+rax*4+40h]
0x180005627  test    r8d, r8d
0x18000562a  jz      short loc_180005644
0x18000562c  mov     rax, [rsi]
0x18000562f  lea     r9, [rsp+38h+arg_0]
0x180005634  mov     rcx, rsi
0x180005637  mov     rax, [rax+18h]
0x18000563b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005640  test    eax, eax
0x180005642  js      short loc_1800056B5
0x180005644  movsxd  rcx, dword ptr [rdi+20h]
0x180005648  mov     eax, [rsp+38h+arg_0]
0x18000564c  mov     [rdi+rcx*4+38h], eax
0x180005650  inc     dword ptr [rdi+20h]
0x180005653  cmp     dword ptr [rdi+20h], 2
0x180005657  jl      short loc_18000565C
0x180005659  mov     [rdi+20h], ebp
0x18000565c  mov     rcx, [rdi+10h]; hSemaphore
0x180005660  xor     r8d, r8d; lpPreviousCount
0x180005663  mov     edx, 1; lReleaseCount
0x180005668  call    cs:__imp_ReleaseSemaphore
0x18000566e  cmp     [rsp+38h+arg_0], ebp
0x180005672  jnz     loc_1800055F0
0x180005678  cmp     [rdi+50h], ebp
0x18000567b  jz      loc_1800055D4
0x180005681  mov     rbp, [rsp+38h+arg_10]
0x180005686  xor     eax, eax
0x180005688  mov     rbx, [rsp+38h+arg_8]
0x18000568d  mov     rsi, [rsp+38h+arg_18]
0x180005692  add     rsp, 30h
0x180005696  pop     rdi
0x180005697  retn
0x180005698  call    cs:__imp_GetLastError
0x18000569e  test    eax, eax
0x1800056a0  mov     ecx, 1
0x1800056a5  cmovnz  ecx, eax
0x1800056a8  mov     [rdi+50h], ecx
0x1800056ab  jmp     short loc_180005644
0x1800056ad  xor     eax, eax
0x1800056af  add     rsp, 30h
0x1800056b3  pop     rdi
0x1800056b4  retn
0x1800056b5  movzx   eax, ax
0x1800056b8  mov     [rsp+38h+arg_0], ebp
0x1800056bc  jmp     short loc_18000569E
```
