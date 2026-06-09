# BfeNotifyCancel

- ea: `0x18001dcb8`
- end: `0x18001ddd1`
- name: `BfeNotifyCancel`
- size: `281`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18001e578`
- `0x1800572d8`
- `0x180070e08`

## callees

- `0x18000e000`
- `0x18001dcb8`
- `0x180058b30`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x180088d15`
- `ntdll!RtlRemoveEntryHashTable` at `0x180088d15`
- `ntdll!RtlInitEnumerationHashTable` at `0x18001dd09`
- `ntdll!RtlInitEnumerationHashTable` at `0x18001dd09`
- `ntdll!RtlEnumerateEntryHashTable` at `0x18001dd1e`
- `ntdll!RtlEnumerateEntryHashTable` at `0x18001dd1e`
- `ntdll!RtlEndEnumerationHashTable` at `0x18001dd3a`
- `ntdll!RtlEndEnumerationHashTable` at `0x18001dd3a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180088d06`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180088d06`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001dce8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001dce8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001dd43`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001dd43`

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
0x18001dcb8  push    rbx
0x18001dcba  push    rbp
0x18001dcbb  push    rsi
0x18001dcbc  push    rdi
0x18001dcbd  sub     rsp, 68h
0x18001dcc1  mov     rax, cs:__security_cookie
0x18001dcc8  xor     rax, rsp
0x18001dccb  mov     [rsp+88h+var_30], rax
0x18001dcd0  xorps   xmm0, xmm0
0x18001dcd3  mov     rbp, rdx
0x18001dcd6  movups  [rsp+88h+var_60], xmm0
0x18001dcdb  mov     rdi, rcx
0x18001dcde  movups  [rsp+88h+var_50], xmm0
0x18001dce3  movups  [rsp+88h+var_40], xmm0
0x18001dce8  call    cs:__imp_EnterCriticalSection
0x18001dcee  lea     rsi, [rdi+40h]
0x18001dcf2  mov     rcx, [rsi]
0x18001dcf5  cmp     rcx, rsi
0x18001dcf8  jnz     short loc_18001DD5F
0x18001dcfa  lea     rsi, [rdi+0E0h]
0x18001dd01  mov     rcx, rsi
0x18001dd04  lea     rdx, [rsp+88h+var_60+8]
0x18001dd09  call    cs:__imp_RtlInitEnumerationHashTable
0x18001dd0f  mov     qword ptr [rsp+88h+var_60], rsi
0x18001dd14  mov     rcx, qword ptr [rsp+88h+var_60]
0x18001dd19  lea     rdx, [rsp+88h+var_60+8]
0x18001dd1e  call    cs:__imp_RtlEnumerateEntryHashTable
0x18001dd24  mov     rbx, rax
0x18001dd27  test    rax, rax
0x18001dd2a  jnz     loc_18001DDB9
0x18001dd30  mov     rcx, qword ptr [rsp+88h+var_60]
0x18001dd35  lea     rdx, [rsp+88h+var_60+8]
0x18001dd3a  call    cs:__imp_RtlEndEnumerationHashTable
0x18001dd40  mov     rcx, rdi; lpCriticalSection
0x18001dd43  call    cs:__imp_LeaveCriticalSection
0x18001dd49  mov     rcx, [rsp+88h+var_30]
0x18001dd4e  xor     rcx, rsp; StackCookie
0x18001dd51  call    __security_check_cookie
0x18001dd56  add     rsp, 68h
0x18001dd5a  pop     rdi
0x18001dd5b  pop     rsi
0x18001dd5c  pop     rbp
0x18001dd5d  pop     rbx
0x18001dd5e  retn
0x18001dd5f  mov     rbx, [rcx]
0x18001dd62  mov     [rsp+88h+var_68], rcx
0x18001dd67  test    rbp, rbp
0x18001dd6a  jnz     short loc_18001DDAD
0x18001dd6c  cmp     [rbx+8], rcx
0x18001dd70  jnz     short loc_18001DDA6
0x18001dd72  mov     rax, [rcx+8]
0x18001dd76  cmp     [rax], rcx
0x18001dd79  jnz     short loc_18001DDA6
0x18001dd7b  mov     [rax], rbx
0x18001dd7e  add     rcx, 10h
0x18001dd82  mov     [rbx+8], rax
0x18001dd86  dec     dword ptr [rdi+38h]
0x18001dd89  call    WfpMemFree
0x18001dd8e  lea     rcx, [rsp+88h+var_68]
0x18001dd93  call    WfpMemFree
0x18001dd98  mov     rcx, rbx
0x18001dd9b  cmp     rbx, rsi
0x18001dd9e  jz      loc_18001DCFA
0x18001dda4  jmp     short loc_18001DD5F
0x18001dda6  mov     ecx, 3
0x18001ddab  int     29h; Win8: RtlFailFast(ecx)
0x18001ddad  mov     rax, [rcx+10h]
0x18001ddb1  cmp     rbp, [rax+8]
0x18001ddb5  jnz     short loc_18001DD98
0x18001ddb7  jmp     short loc_18001DD6C
0x18001ddb9  test    rbp, rbp
0x18001ddbc  jz      loc_180088D02
0x18001ddc2  cmp     rbp, [rax+18h]
0x18001ddc6  jnz     loc_18001DD14
0x18001ddcc  jmp     loc_180088D02
0x180088d02  mov     rcx, [rax+38h]; hEvent
0x180088d06  call    cs:__imp_SetEvent
0x180088d0c  xor     r8d, r8d
0x180088d0f  mov     rdx, rbx
0x180088d12  mov     rcx, rsi
0x180088d15  call    cs:__imp_RtlRemoveEntryHashTable
0x180088d1b  mov     dword ptr [rbx+30h], 0
0x180088d22  jmp     loc_18001DD14
```
