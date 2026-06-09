# CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::GetAllocatedBlob(_GUID const &,uchar * *,uint *)

- ea: `0x1800995f0`
- end: `0x1800996b6`
- name: `?GetAllocatedBlob@?$CMFAttributesImpl@UIMFTelemetrySession@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@PEAPEAEPEAI@Z`
- size: `198`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800995f0`
- `0x18009e6d0`
- `0x1800b0460`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180099651`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180099651`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009968e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009968e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009961a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009961a`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::GetAllocatedBlob(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        _DWORD *a4)
{
  unsigned int v8; // esi
  __int64 Item; // rbx
  void *v10; // rax

  v8 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  Item = CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::_FindItem(a1, a2);
  if ( Item )
  {
    if ( *(_WORD *)Item == 4113 )
    {
      if ( a4 )
        *a4 = *(_DWORD *)(Item + 8);
      v10 = CoTaskMemAlloc(*(unsigned int *)(Item + 8));
      *a3 = v10;
      if ( v10 )
        memmove(v10, *(const void **)(Item + 16), *(unsigned int *)(Item + 8));
      else
        v8 = -2147024882;
    }
    else
    {
      v8 = -1072875843;
    }
  }
  else
  {
    v8 = -1072875802;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  return v8;
}

```

## disassembly

```asm
0x1800995f0  mov     [rsp+arg_0], rbx
0x1800995f5  mov     [rsp+arg_8], rbp
0x1800995fa  mov     [rsp+arg_10], rsi
0x1800995ff  push    rdi
0x180099600  push    r14
0x180099602  push    r15
0x180099604  sub     rsp, 20h
0x180099608  mov     rdi, rcx
0x18009960b  mov     r14, r9
0x18009960e  add     rcx, 8; lpCriticalSection
0x180099612  mov     r15, r8
0x180099615  mov     rbx, rdx
0x180099618  xor     esi, esi
0x18009961a  call    cs:__imp_EnterCriticalSection
0x180099621  nop     dword ptr [rax+rax+00h]
0x180099626  mov     rdx, rbx
0x180099629  mov     rcx, rdi
0x18009962c  call    ?_FindItem@?$CMFAttributesImpl@UIMFTelemetrySession@@VCWin32AttributeLock@@@@IEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::_FindItem(_GUID const &)
0x180099631  mov     rbx, rax
0x180099634  test    rax, rax
0x180099637  jz      short loc_180099685
0x180099639  mov     eax, 1011h
0x18009963e  cmp     [rbx], ax
0x180099641  jnz     short loc_18009967E
0x180099643  test    r14, r14
0x180099646  jz      short loc_18009964E
0x180099648  mov     eax, [rbx+8]
0x18009964b  mov     [r14], eax
0x18009964e  mov     ecx, [rbx+8]; cb
0x180099651  call    cs:__imp_CoTaskMemAlloc
0x180099658  nop     dword ptr [rax+rax+00h]
0x18009965d  mov     [r15], rax
0x180099660  test    rax, rax
0x180099663  jnz     short loc_18009966C
0x180099665  mov     esi, 8007000Eh
0x18009966a  jmp     short loc_18009968A
0x18009966c  mov     r8d, [rbx+8]; Size
0x180099670  mov     rcx, rax; void *
0x180099673  mov     rdx, [rbx+10h]; Src
0x180099677  call    memmove
0x18009967c  jmp     short loc_18009968A
0x18009967e  mov     esi, 0C00D36BDh
0x180099683  jmp     short loc_18009968A
0x180099685  mov     esi, 0C00D36E6h
0x18009968a  lea     rcx, [rdi+8]; lpCriticalSection
0x18009968e  call    cs:__imp_LeaveCriticalSection
0x180099695  nop     dword ptr [rax+rax+00h]
0x18009969a  mov     rbx, [rsp+38h+arg_0]
0x18009969f  mov     eax, esi
0x1800996a1  mov     rsi, [rsp+38h+arg_10]
0x1800996a6  mov     rbp, [rsp+38h+arg_8]
0x1800996ab  add     rsp, 20h
0x1800996af  pop     r15
0x1800996b1  pop     r14
0x1800996b3  pop     rdi
0x1800996b4  retn
```
