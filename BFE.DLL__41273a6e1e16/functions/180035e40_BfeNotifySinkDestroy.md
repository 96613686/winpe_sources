# BfeNotifySinkDestroy

- ea: `0x180035e40`
- end: `0x180035fb6`
- name: `BfeNotifySinkDestroy`
- size: `374`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800040d0`
- `0x18004d068`

## callees

- `0x18000e7e0`
- `0x180035e40`
- `0x180035fbc`

## import_xrefs

- `ntdll!RtlDeleteHashTable` at `0x180035f27`
- `ntdll!RtlDeleteHashTable` at `0x180035f27`
- `ntdll!RtlRemoveEntryHashTable` at `0x180035f8d`
- `ntdll!RtlRemoveEntryHashTable` at `0x180035f8d`
- `ntdll!RtlInitEnumerationHashTable` at `0x180035ee8`
- `ntdll!RtlInitEnumerationHashTable` at `0x180035ee8`
- `ntdll!RtlEnumerateEntryHashTable` at `0x180035eff`
- `ntdll!RtlEnumerateEntryHashTable` at `0x180035eff`
- `ntdll!RtlEndEnumerationHashTable` at `0x180035f18`
- `ntdll!RtlEndEnumerationHashTable` at `0x180035f18`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180035f5a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180035f5a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035f42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035f42`

## pseudocode

```c
__int64 __fastcall BfeNotifySinkDestroy(LPCRITICAL_SECTION *a1)
{
  LPCRITICAL_SECTION v2; // rcx
  HANDLE *p_LockSemaphore; // rdx
  _QWORD *LockSemaphore; // rax
  _QWORD *v5; // r8
  LPCRITICAL_SECTION v6; // rax
  HANDLE *v7; // rdi
  HANDLE *i; // rcx
  __int64 v9; // rax
  HANDLE OwningThread; // rcx
  LPCRITICAL_SECTION v11; // rdi
  _OWORD v13[3]; // [rsp+20h] [rbp-30h] BYREF
  _QWORD *v14; // [rsp+60h] [rbp+10h] BYREF

  v2 = *a1;
  if ( v2 )
  {
    if ( LODWORD(v2[1].OwningThread) )
    {
      p_LockSemaphore = &v2[1].LockSemaphore;
      LockSemaphore = v2[1].LockSemaphore;
      if ( (HANDLE *)LockSemaphore[1] != &v2[1].LockSemaphore
        || (v5 = (_QWORD *)*LockSemaphore, *(_QWORD **)(*LockSemaphore + 8LL) != LockSemaphore) )
      {
        __fastfail(3u);
      }
      *p_LockSemaphore = v5;
      v5[1] = p_LockSemaphore;
      --LODWORD(v2[1].OwningThread);
      v14 = LockSemaphore;
      if ( !LockSemaphore )
        goto LABEL_7;
      do
      {
        WfpMemFree(LockSemaphore + 2);
LABEL_7:
        WfpMemFree(&v14);
        LockSemaphore = (_QWORD *)BfeNotifySinkGetNext(*a1);
        v14 = LockSemaphore;
      }
      while ( LockSemaphore );
    }
    else
    {
      v14 = 0;
    }
    v6 = *a1;
    if ( LODWORD((*a1)[6].LockSemaphore) )
    {
      v7 = &v6[5].LockSemaphore;
      memset(v13, 0, sizeof(v13));
      RtlInitEnumerationHashTable(&v6[5].LockSemaphore, (char *)v13 + 8);
      for ( i = v7; ; i = v7 )
      {
        v9 = RtlEnumerateEntryHashTable(i, (char *)v13 + 8);
        if ( !v9 )
          break;
        RtlRemoveEntryHashTable(v7, v9, 0);
      }
      RtlEndEnumerationHashTable(v7, (char *)v13 + 8);
      RtlDeleteHashTable(v7);
    }
    OwningThread = (*a1)[5].OwningThread;
    if ( OwningThread )
      CloseHandle(OwningThread);
    v11 = *a1;
    if ( LODWORD((*a1)[1].DebugInfo) )
    {
      DeleteCriticalSection(*a1);
      LODWORD(v11[1].DebugInfo) = 0;
    }
  }
  return WfpMemFree(a1);
}

```

## disassembly

```asm
0x180035e40  mov     [rsp-8+arg_8], rbx
0x180035e45  mov     [rsp-8+arg_10], rdi
0x180035e4a  push    rbp
0x180035e4b  mov     rbp, rsp
0x180035e4e  sub     rsp, 50h
0x180035e52  mov     rbx, rcx
0x180035e55  mov     rcx, [rcx]
0x180035e58  test    rcx, rcx
0x180035e5b  jz      loc_180035F6D
0x180035e61  cmp     dword ptr [rcx+38h], 0
0x180035e65  jbe     loc_180035FA9
0x180035e6b  lea     rdx, [rcx+40h]
0x180035e6f  mov     rax, [rdx]
0x180035e72  cmp     [rax+8], rdx
0x180035e76  jnz     loc_180035FA2
0x180035e7c  mov     r8, [rax]
0x180035e7f  cmp     [r8+8], rax
0x180035e83  jnz     loc_180035FA2
0x180035e89  mov     [rdx], r8
0x180035e8c  mov     [r8+8], rdx
0x180035e90  dec     dword ptr [rcx+38h]
0x180035e93  mov     [rbp+arg_0], rax
0x180035e97  test    rax, rax
0x180035e9a  jz      short loc_180035EA5
0x180035e9c  lea     rcx, [rax+10h]
0x180035ea0  call    WfpMemFree
0x180035ea5  lea     rcx, [rbp+arg_0]
0x180035ea9  call    WfpMemFree
0x180035eae  mov     rcx, [rbx]
0x180035eb1  call    BfeNotifySinkGetNext
0x180035eb6  mov     [rbp+arg_0], rax
0x180035eba  test    rax, rax
0x180035ebd  jnz     short loc_180035E9C
0x180035ebf  mov     rax, [rbx]
0x180035ec2  cmp     dword ptr [rax+108h], 0
0x180035ec9  jz      short loc_180035F33
0x180035ecb  xorps   xmm0, xmm0
0x180035ece  lea     rdi, [rax+0E0h]
0x180035ed5  mov     rcx, rdi
0x180035ed8  lea     rdx, [rbp+var_28]
0x180035edc  movups  xmmword ptr [rbp-30h], xmm0
0x180035ee0  movups  [rbp+var_20], xmm0
0x180035ee4  movups  [rbp+var_10], xmm0
0x180035ee8  call    cs:__imp_RtlInitEnumerationHashTable
0x180035eef  nop     dword ptr [rax+rax+00h]
0x180035ef4  mov     rcx, rdi
0x180035ef7  mov     [rbp+var_30], rcx
0x180035efb  lea     rdx, [rbp+var_28]
0x180035eff  call    cs:__imp_RtlEnumerateEntryHashTable
0x180035f06  nop     dword ptr [rax+rax+00h]
0x180035f0b  test    rax, rax
0x180035f0e  jnz     short loc_180035F84
0x180035f10  mov     rcx, [rbp+var_30]
0x180035f14  lea     rdx, [rbp+var_28]
0x180035f18  call    cs:__imp_RtlEndEnumerationHashTable
0x180035f1f  nop     dword ptr [rax+rax+00h]
0x180035f24  mov     rcx, rdi
0x180035f27  call    cs:__imp_RtlDeleteHashTable
0x180035f2e  nop     dword ptr [rax+rax+00h]
0x180035f33  mov     rax, [rbx]
0x180035f36  mov     rcx, [rax+0D8h]; hObject
0x180035f3d  test    rcx, rcx
0x180035f40  jz      short loc_180035F4E
0x180035f42  call    cs:__imp_CloseHandle
0x180035f49  nop     dword ptr [rax+rax+00h]
0x180035f4e  mov     rdi, [rbx]
0x180035f51  cmp     dword ptr [rdi+28h], 0
0x180035f55  jz      short loc_180035F6D
0x180035f57  mov     rcx, rdi; lpCriticalSection
0x180035f5a  call    cs:__imp_DeleteCriticalSection
0x180035f61  nop     dword ptr [rax+rax+00h]
0x180035f66  mov     dword ptr [rdi+28h], 0
0x180035f6d  mov     rcx, rbx
0x180035f70  mov     rbx, [rsp+50h+arg_8]
0x180035f75  mov     rdi, [rsp+50h+arg_10]
0x180035f7a  add     rsp, 50h
0x180035f7e  pop     rbp
0x180035f7f  jmp     WfpMemFree
0x180035f84  xor     r8d, r8d
0x180035f87  mov     rdx, rax
0x180035f8a  mov     rcx, rdi
0x180035f8d  call    cs:__imp_RtlRemoveEntryHashTable
0x180035f94  nop     dword ptr [rax+rax+00h]
0x180035f99  mov     rcx, [rbp+var_30]
0x180035f9d  jmp     loc_180035EFB
0x180035fa2  mov     ecx, 3
0x180035fa7  int     29h; Win8: RtlFailFast(ecx)
0x180035fa9  mov     [rbp+arg_0], 0
0x180035fb1  jmp     loc_180035EBF
```
