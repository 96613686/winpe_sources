# CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::GetAllocatedString(_GUID const &,ushort * *,uint *)

- ea: `0x1800996c0`
- end: `0x18009979f`
- name: `?GetAllocatedString@?$CMFAttributesImpl@UIMFTelemetrySession@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@PEAPEAGPEAI@Z`
- size: `223`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800996c0`
- `0x18009e6d0`
- `0x1800b0460`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180099743`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180099743`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180099777`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180099777`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800996ed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800996ed`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::GetAllocatedString(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        _DWORD *a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbp
  unsigned int v9; // esi
  __int64 Item; // rax
  __int64 v11; // rdi
  __int64 v12; // rcx
  unsigned __int64 v13; // rax
  SIZE_T v14; // rbx
  void *v15; // rax

  v4 = (struct _RTL_CRITICAL_SECTION *)(a1 + 8);
  v9 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  Item = CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::_FindItem(a1, a2);
  v11 = Item;
  if ( Item )
  {
    if ( *(_WORD *)Item == 31 )
    {
      v12 = *(_QWORD *)(Item + 8);
      v13 = -1;
      do
        ++v13;
      while ( *(_WORD *)(v12 + 2 * v13) );
      if ( v13 >= 0x7FFFFFFE )
        goto LABEL_6;
      if ( a4 )
        *a4 = v13;
      v14 = 2LL * (unsigned int)(v13 + 1);
      v15 = CoTaskMemAlloc(v14);
      *a3 = v15;
      if ( v15 )
        memmove(v15, *(const void **)(v11 + 8), v14);
      else
LABEL_6:
        v9 = -2147024882;
    }
    else
    {
      v9 = -1072875843;
    }
  }
  else
  {
    v9 = -1072875802;
  }
  LeaveCriticalSection(v4);
  return v9;
}

```

## disassembly

```asm
0x1800996c0  mov     [rsp+arg_0], rbx
0x1800996c5  mov     [rsp+arg_8], rbp
0x1800996ca  mov     [rsp+arg_10], rsi
0x1800996cf  push    rdi
0x1800996d0  push    r14
0x1800996d2  push    r15
0x1800996d4  sub     rsp, 20h
0x1800996d8  lea     rbp, [rcx+8]
0x1800996dc  mov     rdi, rcx
0x1800996df  mov     rcx, rbp; lpCriticalSection
0x1800996e2  mov     r14, r9
0x1800996e5  mov     r15, r8
0x1800996e8  mov     rbx, rdx
0x1800996eb  xor     esi, esi
0x1800996ed  call    cs:__imp_EnterCriticalSection
0x1800996f4  nop     dword ptr [rax+rax+00h]
0x1800996f9  mov     rdx, rbx
0x1800996fc  mov     rcx, rdi
0x1800996ff  call    ?_FindItem@?$CMFAttributesImpl@UIMFTelemetrySession@@VCWin32AttributeLock@@@@IEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::_FindItem(_GUID const &)
0x180099704  mov     rdi, rax
0x180099707  test    rax, rax
0x18009970a  jz      short loc_18009976F
0x18009970c  cmp     word ptr [rax], 1Fh
0x180099710  jnz     short loc_180099768
0x180099712  mov     rcx, [rax+8]
0x180099716  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009971a  inc     rax
0x18009971d  cmp     [rcx+rax*2], si
0x180099721  jnz     short loc_18009971A
0x180099723  cmp     rax, 7FFFFFFEh
0x180099729  jb      short loc_180099732
0x18009972b  mov     esi, 8007000Eh
0x180099730  jmp     short loc_180099774
0x180099732  test    r14, r14
0x180099735  jz      short loc_18009973A
0x180099737  mov     [r14], eax
0x18009973a  lea     ebx, [rax+1]
0x18009973d  add     rbx, rbx
0x180099740  mov     rcx, rbx; cb
0x180099743  call    cs:__imp_CoTaskMemAlloc
0x18009974a  nop     dword ptr [rax+rax+00h]
0x18009974f  mov     [r15], rax
0x180099752  test    rax, rax
0x180099755  jz      short loc_18009972B
0x180099757  mov     rdx, [rdi+8]; Src
0x18009975b  mov     r8, rbx; Size
0x18009975e  mov     rcx, rax; void *
0x180099761  call    memmove
0x180099766  jmp     short loc_180099774
0x180099768  mov     esi, 0C00D36BDh
0x18009976d  jmp     short loc_180099774
0x18009976f  mov     esi, 0C00D36E6h
0x180099774  mov     rcx, rbp; lpCriticalSection
0x180099777  call    cs:__imp_LeaveCriticalSection
0x18009977e  nop     dword ptr [rax+rax+00h]
0x180099783  mov     rbx, [rsp+38h+arg_0]
0x180099788  mov     eax, esi
0x18009978a  mov     rsi, [rsp+38h+arg_10]
0x18009978f  mov     rbp, [rsp+38h+arg_8]
0x180099794  add     rsp, 20h
0x180099798  pop     r15
0x18009979a  pop     r14
0x18009979c  pop     rdi
0x18009979d  retn
```
