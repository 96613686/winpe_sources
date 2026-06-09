# wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)

- ea: `0x1400059c0`
- end: `0x140005b0a`
- name: `?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z`
- size: `330`
- prototype: `__int64 __fastcall(HANDLE hHandle, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140006700`

## callees

- `0x1400059c0`
- `0x1400062f4`
- `0x140006314`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140005a48`
- `KERNEL32!GetLastError` at `0x140005aa2`
- `KERNEL32!GetLastError` at `0x140005a48`
- `KERNEL32!GetLastError` at `0x140005aa2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400059d2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140005ab4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400059d2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140005ab4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x140005a1f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x140005a3e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x140005a6c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x140005a98`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x140005a1f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x140005a3e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x140005a6c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x140005a98`

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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, (unsigned int)"wil", (const char *)0x8000FFFFLL, v11);
  return 2147549183LL;
}

```

## disassembly

```asm
0x1400059c0  mov     [rsp+arg_0], rsi
0x1400059c5  push    rdi; int
0x1400059c6  sub     rsp, 20h
0x1400059ca  mov     rsi, rdx
0x1400059cd  mov     rdi, rcx
0x1400059d0  xor     edx, edx; dwMilliseconds
0x1400059d2  call    cs:__imp_WaitForSingleObject
0x1400059d8  cmp     eax, 0FFFFFFFFh
0x1400059db  jnz     short loc_1400059F1
0x1400059dd  mov     edx, 9Ch; void *
0x1400059e2  mov     rcx, [rsp+28h]; this
0x1400059e7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400059ec  jmp     loc_140005AFF
0x1400059f1  test    eax, eax
0x1400059f3  jz      short loc_140005A06
0x1400059f5  cmp     eax, 102h
0x1400059fa  jz      short loc_140005A06
0x1400059fc  mov     edx, 9Dh
0x140005a01  jmp     loc_140005AE3
0x140005a06  mov     [rsp+28h+PreviousCount], 0
0x140005a0e  mov     edx, 1; lReleaseCount
0x140005a13  mov     rcx, rdi; hSemaphore
0x140005a16  test    eax, eax
0x140005a18  jnz     short loc_140005A5F
0x140005a1a  lea     r8, [rsp+28h+PreviousCount]; lpPreviousCount
0x140005a1f  call    cs:__imp_ReleaseSemaphore
0x140005a25  test    eax, eax
0x140005a27  jnz     short loc_140005A30
0x140005a29  mov     edx, 0A5h
0x140005a2e  jmp     short loc_1400059E2
0x140005a30  inc     [rsp+28h+PreviousCount]
0x140005a34  xor     r8d, r8d; lpPreviousCount
0x140005a37  mov     rcx, rdi; hSemaphore
0x140005a3a  lea     edx, [r8+1]; lReleaseCount
0x140005a3e  call    cs:__imp_ReleaseSemaphore
0x140005a44  test    eax, eax
0x140005a46  jnz     short loc_140005A55
0x140005a48  call    cs:__imp_GetLastError
0x140005a4e  cmp     eax, 12Ah
0x140005a53  jz      short loc_140005AD4
0x140005a55  mov     edx, 0AAh
0x140005a5a  jmp     loc_140005AE3
0x140005a5f  lea     r8, [rsp+28h+arg_18]; lpPreviousCount
0x140005a64  mov     [rsp+28h+arg_18], 0
0x140005a6c  call    cs:__imp_ReleaseSemaphore
0x140005a72  test    eax, eax
0x140005a74  jnz     short loc_140005A80
0x140005a76  mov     edx, 0B4h
0x140005a7b  jmp     loc_1400059E2
0x140005a80  cmp     [rsp+28h+arg_18], 0
0x140005a85  jz      short loc_140005A8E
0x140005a87  mov     edx, 0B5h
0x140005a8c  jmp     short loc_140005AE3
0x140005a8e  xor     r8d, r8d; lpPreviousCount
0x140005a91  mov     rcx, rdi; hSemaphore
0x140005a94  lea     edx, [r8+1]; lReleaseCount
0x140005a98  call    cs:__imp_ReleaseSemaphore
0x140005a9e  test    eax, eax
0x140005aa0  jnz     short loc_140005ADE
0x140005aa2  call    cs:__imp_GetLastError
0x140005aa8  cmp     eax, 12Ah
0x140005aad  jnz     short loc_140005ADE
0x140005aaf  xor     edx, edx; dwMilliseconds
0x140005ab1  mov     rcx, rdi; hHandle
0x140005ab4  call    cs:__imp_WaitForSingleObject
0x140005aba  cmp     eax, 0FFFFFFFFh
0x140005abd  jnz     short loc_140005AC9
0x140005abf  mov     edx, 0BBh
0x140005ac4  jmp     loc_1400059E2
0x140005ac9  test    eax, eax
0x140005acb  jz      short loc_140005AD4
0x140005acd  mov     edx, 0BCh
0x140005ad2  jmp     short loc_140005AE3
0x140005ad4  mov     eax, [rsp+28h+PreviousCount]
0x140005ad8  mov     [rsi], eax
0x140005ada  xor     eax, eax
0x140005adc  jmp     short loc_140005AFF
0x140005ade  mov     edx, 0B8h; void *
0x140005ae3  mov     rcx, [rsp+28h]; this
0x140005ae8  lea     r8, aWil; "wil"
0x140005aef  mov     r9d, 8000FFFFh; char *
0x140005af5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005afa  mov     eax, 8000FFFFh
0x140005aff  mov     rsi, [rsp+28h+arg_0]
0x140005b04  add     rsp, 20h
0x140005b08  pop     rdi
0x140005b09  retn
```
