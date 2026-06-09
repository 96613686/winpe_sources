# BfeNotifySinkDestroy

- ea: `0x180037828`
- end: `0x180037971`
- name: `BfeNotifySinkDestroy`
- size: `329`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800040f0`
- `0x18004b220`

## callees

- `0x18000e000`
- `0x180037828`
- `0x180037978`

## import_xrefs

- `ntdll!RtlDeleteHashTable` at `0x1800378fd`
- `ntdll!RtlDeleteHashTable` at `0x1800378fd`
- `ntdll!RtlRemoveEntryHashTable` at `0x180037951`
- `ntdll!RtlRemoveEntryHashTable` at `0x180037951`
- `ntdll!RtlInitEnumerationHashTable` at `0x1800378d0`
- `ntdll!RtlInitEnumerationHashTable` at `0x1800378d0`
- `ntdll!RtlEnumerateEntryHashTable` at `0x1800378e1`
- `ntdll!RtlEnumerateEntryHashTable` at `0x1800378e1`
- `ntdll!RtlEndEnumerationHashTable` at `0x1800378f4`
- `ntdll!RtlEndEnumerationHashTable` at `0x1800378f4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180037924`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180037924`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037912`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037912`

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
0x180037828  mov     [rsp-8+arg_8], rbx
0x18003782d  mov     [rsp-8+arg_10], rdi
0x180037832  push    rbp
0x180037833  mov     rbp, rsp
0x180037836  sub     rsp, 50h
0x18003783a  mov     rbx, rcx
0x18003783d  mov     rcx, [rcx]
0x180037840  test    rcx, rcx
0x180037843  jz      loc_180037931
0x180037849  cmp     dword ptr [rcx+38h], 0
0x18003784d  jbe     loc_180037964
0x180037853  lea     rdx, [rcx+40h]
0x180037857  mov     rax, [rdx]
0x18003785a  cmp     [rax+8], rdx
0x18003785e  jnz     loc_18003795D
0x180037864  mov     r8, [rax]
0x180037867  cmp     [r8+8], rax
0x18003786b  jnz     loc_18003795D
0x180037871  mov     [rdx], r8
0x180037874  mov     [r8+8], rdx
0x180037878  dec     dword ptr [rcx+38h]
0x18003787b  mov     [rbp+arg_0], rax
0x18003787f  test    rax, rax
0x180037882  jz      short loc_18003788D
0x180037884  lea     rcx, [rax+10h]
0x180037888  call    WfpMemFree
0x18003788d  lea     rcx, [rbp+arg_0]
0x180037891  call    WfpMemFree
0x180037896  mov     rcx, [rbx]
0x180037899  call    BfeNotifySinkGetNext
0x18003789e  mov     [rbp+arg_0], rax
0x1800378a2  test    rax, rax
0x1800378a5  jnz     short loc_180037884
0x1800378a7  mov     rax, [rbx]
0x1800378aa  cmp     dword ptr [rax+108h], 0
0x1800378b1  jz      short loc_180037903
0x1800378b3  xorps   xmm0, xmm0
0x1800378b6  lea     rdi, [rax+0E0h]
0x1800378bd  mov     rcx, rdi
0x1800378c0  lea     rdx, [rbp+var_28]
0x1800378c4  movups  xmmword ptr [rbp-30h], xmm0
0x1800378c8  movups  [rbp+var_20], xmm0
0x1800378cc  movups  [rbp+var_10], xmm0
0x1800378d0  call    cs:__imp_RtlInitEnumerationHashTable
0x1800378d6  mov     rcx, rdi
0x1800378d9  mov     [rbp+var_30], rcx
0x1800378dd  lea     rdx, [rbp+var_28]
0x1800378e1  call    cs:__imp_RtlEnumerateEntryHashTable
0x1800378e7  test    rax, rax
0x1800378ea  jnz     short loc_180037948
0x1800378ec  mov     rcx, [rbp+var_30]
0x1800378f0  lea     rdx, [rbp+var_28]
0x1800378f4  call    cs:__imp_RtlEndEnumerationHashTable
0x1800378fa  mov     rcx, rdi
0x1800378fd  call    cs:__imp_RtlDeleteHashTable
0x180037903  mov     rax, [rbx]
0x180037906  mov     rcx, [rax+0D8h]; hObject
0x18003790d  test    rcx, rcx
0x180037910  jz      short loc_180037918
0x180037912  call    cs:__imp_CloseHandle
0x180037918  mov     rdi, [rbx]
0x18003791b  cmp     dword ptr [rdi+28h], 0
0x18003791f  jz      short loc_180037931
0x180037921  mov     rcx, rdi; lpCriticalSection
0x180037924  call    cs:__imp_DeleteCriticalSection
0x18003792a  mov     dword ptr [rdi+28h], 0
0x180037931  mov     rcx, rbx
0x180037934  mov     rbx, [rsp+50h+arg_8]
0x180037939  mov     rdi, [rsp+50h+arg_10]
0x18003793e  add     rsp, 50h
0x180037942  pop     rbp
0x180037943  jmp     WfpMemFree
0x180037948  xor     r8d, r8d
0x18003794b  mov     rdx, rax
0x18003794e  mov     rcx, rdi
0x180037951  call    cs:__imp_RtlRemoveEntryHashTable
0x180037957  mov     rcx, [rbp+var_30]
0x18003795b  jmp     short loc_1800378DD
0x18003795d  mov     ecx, 3
0x180037962  int     29h; Win8: RtlFailFast(ecx)
0x180037964  mov     [rbp+arg_0], 0
0x18003796c  jmp     loc_1800378A7
```
