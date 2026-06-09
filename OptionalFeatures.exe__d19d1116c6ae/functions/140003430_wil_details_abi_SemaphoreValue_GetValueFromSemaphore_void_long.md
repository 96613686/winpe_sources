# wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)

- ea: `0x140003430`
- end: `0x140003573`
- name: `?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z`
- size: `323`
- prototype: `__int64 __fastcall(HANDLE hHandle, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140004570`

## callees

- `0x140003430`
- `0x140003e74`
- `0x140003e94`

## import_xrefs

- `KERNEL32!ReleaseSemaphore` at `0x14000348f`
- `KERNEL32!ReleaseSemaphore` at `0x1400034ae`
- `KERNEL32!ReleaseSemaphore` at `0x1400034dc`
- `KERNEL32!ReleaseSemaphore` at `0x140003508`
- `KERNEL32!ReleaseSemaphore` at `0x14000348f`
- `KERNEL32!ReleaseSemaphore` at `0x1400034ae`
- `KERNEL32!ReleaseSemaphore` at `0x1400034dc`
- `KERNEL32!ReleaseSemaphore` at `0x140003508`
- `KERNEL32!WaitForSingleObject` at `0x140003442`
- `KERNEL32!WaitForSingleObject` at `0x140003524`
- `KERNEL32!WaitForSingleObject` at `0x140003442`
- `KERNEL32!WaitForSingleObject` at `0x140003524`
- `KERNEL32!GetLastError` at `0x1400034b8`
- `KERNEL32!GetLastError` at `0x140003512`
- `KERNEL32!GetLastError` at `0x1400034b8`
- `KERNEL32!GetLastError` at `0x140003512`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::GetValueFromSemaphore(HANDLE hHandle, int *a2)
{
  DWORD v4; // eax
  unsigned int v5; // r8d
  const char *v6; // r9
  __int64 v7; // rdx
  __int64 v9; // rdx
  DWORD v10; // eax
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int PreviousCount; // [rsp+40h] [rbp+18h] BYREF
  int v14; // [rsp+48h] [rbp+20h] BYREF

  v4 = WaitForSingleObject(hHandle, 0);
  if ( v4 == -1 )
  {
    v7 = 156;
    return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)v7, v5, v6);
  }
  if ( !v4 || v4 == 258 )
  {
    PreviousCount = 0;
    if ( v4 )
    {
      v14 = 0;
      if ( !ReleaseSemaphore(hHandle, 1, &v14) )
      {
        v7 = 180;
        return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)v7, v5, v6);
      }
      if ( v14 )
      {
        v9 = 181;
        goto LABEL_25;
      }
      if ( ReleaseSemaphore(hHandle, 1, 0) || GetLastError() != 298 )
      {
        v9 = 184;
        goto LABEL_25;
      }
      v10 = WaitForSingleObject(hHandle, 0);
      if ( v10 == -1 )
      {
        v7 = 187;
        return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)v7, v5, v6);
      }
      if ( v10 )
      {
        v9 = 188;
        goto LABEL_25;
      }
    }
    else
    {
      if ( !ReleaseSemaphore(hHandle, 1, &PreviousCount) )
      {
        v7 = 165;
        return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)v7, v5, v6);
      }
      ++PreviousCount;
      if ( ReleaseSemaphore(hHandle, 1, 0) || GetLastError() != 298 )
      {
        v9 = 170;
        goto LABEL_25;
      }
    }
    *a2 = PreviousCount;
    return 0;
  }
  v9 = 157;
LABEL_25:
  wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v5, (const char *)0x8000FFFFLL, v11);
  return 2147549183LL;
}

```

## disassembly

```asm
0x140003430  mov     [rsp+arg_0], rsi
0x140003435  push    rdi; int
0x140003436  sub     rsp, 20h
0x14000343a  mov     rsi, rdx
0x14000343d  mov     rdi, rcx
0x140003440  xor     edx, edx; dwMilliseconds
0x140003442  call    cs:__imp_WaitForSingleObject
0x140003448  cmp     eax, 0FFFFFFFFh
0x14000344b  jnz     short loc_140003461
0x14000344d  mov     edx, 9Ch; void *
0x140003452  mov     rcx, [rsp+28h]; this
0x140003457  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000345c  jmp     loc_140003568
0x140003461  test    eax, eax
0x140003463  jz      short loc_140003476
0x140003465  cmp     eax, 102h
0x14000346a  jz      short loc_140003476
0x14000346c  mov     edx, 9Dh
0x140003471  jmp     loc_140003553
0x140003476  mov     [rsp+28h+PreviousCount], 0
0x14000347e  mov     edx, 1; lReleaseCount
0x140003483  mov     rcx, rdi; hSemaphore
0x140003486  test    eax, eax
0x140003488  jnz     short loc_1400034CF
0x14000348a  lea     r8, [rsp+28h+PreviousCount]; lpPreviousCount
0x14000348f  call    cs:__imp_ReleaseSemaphore
0x140003495  test    eax, eax
0x140003497  jnz     short loc_1400034A0
0x140003499  mov     edx, 0A5h
0x14000349e  jmp     short loc_140003452
0x1400034a0  inc     [rsp+28h+PreviousCount]
0x1400034a4  xor     r8d, r8d; lpPreviousCount
0x1400034a7  mov     rcx, rdi; hSemaphore
0x1400034aa  lea     edx, [r8+1]; lReleaseCount
0x1400034ae  call    cs:__imp_ReleaseSemaphore
0x1400034b4  test    eax, eax
0x1400034b6  jnz     short loc_1400034C5
0x1400034b8  call    cs:__imp_GetLastError
0x1400034be  cmp     eax, 12Ah
0x1400034c3  jz      short loc_140003544
0x1400034c5  mov     edx, 0AAh
0x1400034ca  jmp     loc_140003553
0x1400034cf  lea     r8, [rsp+28h+arg_18]; lpPreviousCount
0x1400034d4  mov     [rsp+28h+arg_18], 0
0x1400034dc  call    cs:__imp_ReleaseSemaphore
0x1400034e2  test    eax, eax
0x1400034e4  jnz     short loc_1400034F0
0x1400034e6  mov     edx, 0B4h
0x1400034eb  jmp     loc_140003452
0x1400034f0  cmp     [rsp+28h+arg_18], 0
0x1400034f5  jz      short loc_1400034FE
0x1400034f7  mov     edx, 0B5h
0x1400034fc  jmp     short loc_140003553
0x1400034fe  xor     r8d, r8d; lpPreviousCount
0x140003501  mov     rcx, rdi; hSemaphore
0x140003504  lea     edx, [r8+1]; lReleaseCount
0x140003508  call    cs:__imp_ReleaseSemaphore
0x14000350e  test    eax, eax
0x140003510  jnz     short loc_14000354E
0x140003512  call    cs:__imp_GetLastError
0x140003518  cmp     eax, 12Ah
0x14000351d  jnz     short loc_14000354E
0x14000351f  xor     edx, edx; dwMilliseconds
0x140003521  mov     rcx, rdi; hHandle
0x140003524  call    cs:__imp_WaitForSingleObject
0x14000352a  cmp     eax, 0FFFFFFFFh
0x14000352d  jnz     short loc_140003539
0x14000352f  mov     edx, 0BBh
0x140003534  jmp     loc_140003452
0x140003539  test    eax, eax
0x14000353b  jz      short loc_140003544
0x14000353d  mov     edx, 0BCh
0x140003542  jmp     short loc_140003553
0x140003544  mov     eax, [rsp+28h+PreviousCount]
0x140003548  mov     [rsi], eax
0x14000354a  xor     eax, eax
0x14000354c  jmp     short loc_140003568
0x14000354e  mov     edx, 0B8h; void *
0x140003553  mov     rcx, [rsp+28h]; this
0x140003558  mov     r9d, 8000FFFFh; char *
0x14000355e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003563  mov     eax, 8000FFFFh
0x140003568  mov     rsi, [rsp+28h+arg_0]
0x14000356d  add     rsp, 20h
0x140003571  pop     rdi
0x140003572  retn
```
