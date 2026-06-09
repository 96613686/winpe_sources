# BfeNotifyCancel

- ea: `0x18001e8fc`
- end: `0x18001ea34`
- name: `BfeNotifyCancel`
- size: `312`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18001f45c`
- `0x1800594dc`
- `0x1800735c4`

## callees

- `0x18000e7e0`
- `0x18001e8fc`
- `0x18005aa60`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x18008bbc5`
- `ntdll!RtlRemoveEntryHashTable` at `0x18008bbc5`
- `ntdll!RtlInitEnumerationHashTable` at `0x18001e953`
- `ntdll!RtlInitEnumerationHashTable` at `0x18001e953`
- `ntdll!RtlEnumerateEntryHashTable` at `0x18001e96e`
- `ntdll!RtlEnumerateEntryHashTable` at `0x18001e96e`
- `ntdll!RtlEndEnumerationHashTable` at `0x18001e990`
- `ntdll!RtlEndEnumerationHashTable` at `0x18001e990`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18008bbb0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18008bbb0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e92c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e92c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e99f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e99f`

## pseudocode

```c
void __fastcall BfeNotifyCancel(LPCRITICAL_SECTION lpCriticalSection, __int64 a2)
{
  HANDLE *LockSemaphore; // rcx
  __int64 v5; // rax
  __int64 v6; // rbx
  HANDLE **v7; // rbx
  HANDLE *v8; // rax
  _QWORD v9[7]; // [rsp+20h] [rbp-68h] BYREF

  memset(&v9[1], 0, 48);
  EnterCriticalSection(lpCriticalSection);
  LockSemaphore = (HANDLE *)lpCriticalSection[1].LockSemaphore;
  if ( LockSemaphore != &lpCriticalSection[1].LockSemaphore )
  {
    do
    {
      v7 = (HANDLE **)*LockSemaphore;
      v9[0] = LockSemaphore;
      if ( !a2 || a2 == *((_QWORD *)LockSemaphore[2] + 1) )
      {
        if ( v7[1] != LockSemaphore || (v8 = (HANDLE *)LockSemaphore[1], *v8 != LockSemaphore) )
          __fastfail(3u);
        *v8 = v7;
        v7[1] = v8;
        --LODWORD(lpCriticalSection[1].OwningThread);
        WfpMemFree(LockSemaphore + 2);
        WfpMemFree(v9);
      }
      LockSemaphore = (HANDLE *)v7;
    }
    while ( v7 != (HANDLE **)&lpCriticalSection[1].LockSemaphore );
  }
  RtlInitEnumerationHashTable(&lpCriticalSection[5].LockSemaphore, &v9[2]);
  v9[1] = (char *)lpCriticalSection + 224;
  while ( 1 )
  {
    v5 = RtlEnumerateEntryHashTable(v9[1], &v9[2]);
    v6 = v5;
    if ( !v5 )
      break;
    if ( !a2 || a2 == *(_QWORD *)(v5 + 24) )
    {
      SetEvent(*(HANDLE *)(v5 + 56));
      RtlRemoveEntryHashTable(&lpCriticalSection[5].LockSemaphore, v6, 0);
      *(_DWORD *)(v6 + 48) = 0;
    }
  }
  RtlEndEnumerationHashTable(v9[1], &v9[2]);
  LeaveCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x18001e8fc  push    rbx
0x18001e8fe  push    rbp
0x18001e8ff  push    rsi
0x18001e900  push    rdi
0x18001e901  sub     rsp, 68h
0x18001e905  mov     rax, cs:__security_cookie
0x18001e90c  xor     rax, rsp
0x18001e90f  mov     [rsp+88h+var_30], rax
0x18001e914  xorps   xmm0, xmm0
0x18001e917  mov     rbp, rdx
0x18001e91a  movups  [rsp+88h+var_60], xmm0
0x18001e91f  mov     rdi, rcx
0x18001e922  movups  [rsp+88h+var_50], xmm0
0x18001e927  movups  [rsp+88h+var_40], xmm0
0x18001e92c  call    cs:__imp_EnterCriticalSection
0x18001e933  nop     dword ptr [rax+rax+00h]
0x18001e938  lea     rsi, [rdi+40h]
0x18001e93c  mov     rcx, [rsi]
0x18001e93f  cmp     rcx, rsi
0x18001e942  jnz     short loc_18001E9C2
0x18001e944  lea     rsi, [rdi+0E0h]
0x18001e94b  mov     rcx, rsi
0x18001e94e  lea     rdx, [rsp+88h+var_60+8]
0x18001e953  call    cs:__imp_RtlInitEnumerationHashTable
0x18001e95a  nop     dword ptr [rax+rax+00h]
0x18001e95f  mov     qword ptr [rsp+88h+var_60], rsi
0x18001e964  mov     rcx, qword ptr [rsp+88h+var_60]
0x18001e969  lea     rdx, [rsp+88h+var_60+8]
0x18001e96e  call    cs:__imp_RtlEnumerateEntryHashTable
0x18001e975  nop     dword ptr [rax+rax+00h]
0x18001e97a  mov     rbx, rax
0x18001e97d  test    rax, rax
0x18001e980  jnz     loc_18001EA1C
0x18001e986  mov     rcx, qword ptr [rsp+88h+var_60]
0x18001e98b  lea     rdx, [rsp+88h+var_60+8]
0x18001e990  call    cs:__imp_RtlEndEnumerationHashTable
0x18001e997  nop     dword ptr [rax+rax+00h]
0x18001e99c  mov     rcx, rdi; lpCriticalSection
0x18001e99f  call    cs:__imp_LeaveCriticalSection
0x18001e9a6  nop     dword ptr [rax+rax+00h]
0x18001e9ab  mov     rcx, [rsp+88h+var_30]
0x18001e9b0  xor     rcx, rsp; StackCookie
0x18001e9b3  call    __security_check_cookie
0x18001e9b8  add     rsp, 68h
0x18001e9bc  pop     rdi
0x18001e9bd  pop     rsi
0x18001e9be  pop     rbp
0x18001e9bf  pop     rbx
0x18001e9c0  retn
0x18001e9c2  mov     rbx, [rcx]
0x18001e9c5  mov     [rsp+88h+var_68], rcx
0x18001e9ca  test    rbp, rbp
0x18001e9cd  jnz     short loc_18001EA10
0x18001e9cf  cmp     [rbx+8], rcx
0x18001e9d3  jnz     short loc_18001EA09
0x18001e9d5  mov     rax, [rcx+8]
0x18001e9d9  cmp     [rax], rcx
0x18001e9dc  jnz     short loc_18001EA09
0x18001e9de  mov     [rax], rbx
0x18001e9e1  add     rcx, 10h
0x18001e9e5  mov     [rbx+8], rax
0x18001e9e9  dec     dword ptr [rdi+38h]
0x18001e9ec  call    WfpMemFree
0x18001e9f1  lea     rcx, [rsp+88h+var_68]
0x18001e9f6  call    WfpMemFree
0x18001e9fb  mov     rcx, rbx
0x18001e9fe  cmp     rbx, rsi
0x18001ea01  jz      loc_18001E944
0x18001ea07  jmp     short loc_18001E9C2
0x18001ea09  mov     ecx, 3
0x18001ea0e  int     29h; Win8: RtlFailFast(ecx)
0x18001ea10  mov     rax, [rcx+10h]
0x18001ea14  cmp     rbp, [rax+8]
0x18001ea18  jnz     short loc_18001E9FB
0x18001ea1a  jmp     short loc_18001E9CF
0x18001ea1c  test    rbp, rbp
0x18001ea1f  jz      loc_18008BBAC
0x18001ea25  cmp     rbp, [rax+18h]
0x18001ea29  jnz     loc_18001E964
0x18001ea2f  jmp     loc_18008BBAC
0x18008bbac  mov     rcx, [rax+38h]; hEvent
0x18008bbb0  call    cs:__imp_SetEvent
0x18008bbb7  nop     dword ptr [rax+rax+00h]
0x18008bbbc  xor     r8d, r8d
0x18008bbbf  mov     rdx, rbx
0x18008bbc2  mov     rcx, rsi
0x18008bbc5  call    cs:__imp_RtlRemoveEntryHashTable
0x18008bbcc  nop     dword ptr [rax+rax+00h]
0x18008bbd1  mov     dword ptr [rbx+30h], 0
0x18008bbd8  jmp     loc_18001E964
```
