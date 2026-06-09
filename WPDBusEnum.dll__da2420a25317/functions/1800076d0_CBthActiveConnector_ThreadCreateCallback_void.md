# CBthActiveConnector::_ThreadCreateCallback(void *)

- ea: `0x1800076d0`
- end: `0x180007789`
- name: `?_ThreadCreateCallback@CBthActiveConnector@@CAKPEAX@Z`
- size: `185`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800076d0`
- `0x180007f28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007726`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007726`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800076e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800076f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800076e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800076f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800076f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800076f0`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000771c`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000771c`

## pseudocode

```c
__int64 __fastcall CBthActiveConnector::_ThreadCreateCallback(HANDLE *Parameter)
{
  unsigned int v1; // esi
  HANDLE CurrentProcess; // rdi
  HANDLE CurrentThread; // rbx
  HANDLE v5; // rax
  signed int LastError; // eax
  bool v7; // sf
  __int64 v8; // r9

  v1 = 0;
  if ( Parameter )
  {
    CurrentProcess = GetCurrentProcess();
    CurrentThread = GetCurrentThread();
    v5 = GetCurrentProcess();
    if ( !DuplicateHandle(v5, CurrentThread, CurrentProcess, Parameter + 4, 0, 0, 2u) )
    {
      LastError = GetLastError();
      v1 = LastError;
      v7 = LastError < 0;
      if ( LastError > 0 )
        v7 = 1;
      if ( v7
        && WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        if ( LastError > 0 )
          v8 = (unsigned __int16)LastError | 0x80070000;
        else
          v8 = (unsigned int)LastError;
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids, v8);
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x1800076d0  push    rbx
0x1800076d2  push    rbp
0x1800076d3  push    rsi
0x1800076d4  push    rdi
0x1800076d5  sub     rsp, 48h
0x1800076d9  xor     esi, esi
0x1800076db  mov     rbp, rcx
0x1800076de  test    rcx, rcx
0x1800076e1  jz      loc_18000777E
0x1800076e7  call    cs:__imp_GetCurrentProcess
0x1800076ed  mov     rdi, rax
0x1800076f0  call    cs:__imp_GetCurrentThread
0x1800076f6  mov     rbx, rax
0x1800076f9  call    cs:__imp_GetCurrentProcess
0x1800076ff  mov     [rsp+68h+dwOptions], 2; dwOptions
0x180007707  lea     r9, [rbp+20h]; lpTargetHandle
0x18000770b  mov     rcx, rax; hSourceProcessHandle
0x18000770e  mov     [rsp+68h+bInheritHandle], esi; bInheritHandle
0x180007712  mov     r8, rdi; hTargetProcessHandle
0x180007715  mov     [rsp+68h+dwDesiredAccess], esi; dwDesiredAccess
0x180007719  mov     rdx, rbx; hSourceHandle
0x18000771c  call    cs:__imp_DuplicateHandle
0x180007722  test    eax, eax
0x180007724  jnz     short loc_18000777E
0x180007726  call    cs:__imp_GetLastError
0x18000772c  movzx   r9d, ax
0x180007730  mov     esi, eax
0x180007732  mov     edx, 80070000h
0x180007737  test    eax, eax
0x180007739  jle     short loc_180007742
0x18000773b  mov     eax, r9d
0x18000773e  or      eax, edx
0x180007740  test    eax, eax
0x180007742  jns     short loc_18000777E
0x180007744  mov     rcx, cs:WPP_GLOBAL_Control
0x18000774b  lea     rax, WPP_GLOBAL_Control
0x180007752  cmp     rcx, rax
0x180007755  jz      short loc_18000777E
0x180007757  test    byte ptr [rcx+1Ch], 2
0x18000775b  jz      short loc_18000777E
0x18000775d  test    esi, esi
0x18000775f  jg      short loc_180007766
0x180007761  mov     r9d, esi
0x180007764  jmp     short loc_180007769
0x180007766  or      r9d, edx
0x180007769  mov     rcx, [rcx+10h]
0x18000776d  lea     r8, WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids
0x180007774  mov     edx, 1Ch
0x180007779  call    WPP_SF_d
0x18000777e  mov     eax, esi
0x180007780  add     rsp, 48h
0x180007784  pop     rdi
0x180007785  pop     rsi
0x180007786  pop     rbp
0x180007787  pop     rbx
0x180007788  retn
```
