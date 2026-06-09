# CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::GetAllocatedBlob(_GUID const &,uchar * *,uint *)

- ea: `0x18006d680`
- end: `0x18006d72c`
- name: `?GetAllocatedBlob@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@PEAPEAEPEAI@Z`
- size: `172`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800445e4`
- `0x18006d680`
- `0x18009606c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006d712`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006d712`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006d69e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006d69e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006d6d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006d6d4`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::GetAllocatedBlob(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        _DWORD *a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbp
  __int64 Item; // rdi
  void *v10; // rax
  unsigned int v11; // ebx

  v4 = (struct _RTL_CRITICAL_SECTION *)(a1 + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  Item = CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::_FindItem(a1, a2);
  if ( Item )
  {
    if ( *(_WORD *)Item == 4113 )
    {
      if ( a4 )
        *a4 = *(_DWORD *)(Item + 8);
      v10 = CoTaskMemAlloc(*(unsigned int *)(Item + 8));
      *a3 = v10;
      if ( v10 )
      {
        v11 = 0;
        memcpy_0(v10, *(const void **)(Item + 16), *(unsigned int *)(Item + 8));
      }
      else
      {
        v11 = -2147024882;
      }
    }
    else
    {
      v11 = -1072875843;
    }
  }
  else
  {
    v11 = -1072875802;
  }
  LeaveCriticalSection(v4);
  return v11;
}

```

## disassembly

```asm
0x18006d680  push    rbx
0x18006d682  push    rbp
0x18006d683  push    rsi
0x18006d684  push    rdi
0x18006d685  push    r14
0x18006d687  sub     rsp, 20h
0x18006d68b  lea     rbp, [rcx+8]
0x18006d68f  mov     rdi, rcx
0x18006d692  mov     rcx, rbp; lpCriticalSection
0x18006d695  mov     rsi, r9
0x18006d698  mov     r14, r8
0x18006d69b  mov     rbx, rdx
0x18006d69e  call    cs:__imp_EnterCriticalSection
0x18006d6a5  nop     dword ptr [rax+rax+00h]
0x18006d6aa  mov     rdx, rbx
0x18006d6ad  mov     rcx, rdi
0x18006d6b0  call    ?_FindItem@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@IEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::_FindItem(_GUID const &)
0x18006d6b5  mov     rdi, rax
0x18006d6b8  test    rax, rax
0x18006d6bb  jz      short loc_18006D70A
0x18006d6bd  mov     eax, 1011h
0x18006d6c2  cmp     [rdi], ax
0x18006d6c5  jnz     short loc_18006D703
0x18006d6c7  test    rsi, rsi
0x18006d6ca  jz      short loc_18006D6D1
0x18006d6cc  mov     ecx, [rdi+8]
0x18006d6cf  mov     [rsi], ecx
0x18006d6d1  mov     ecx, [rdi+8]; cb
0x18006d6d4  call    cs:__imp_CoTaskMemAlloc
0x18006d6db  nop     dword ptr [rax+rax+00h]
0x18006d6e0  mov     [r14], rax
0x18006d6e3  test    rax, rax
0x18006d6e6  jnz     short loc_18006D6EF
0x18006d6e8  mov     ebx, 8007000Eh
0x18006d6ed  jmp     short loc_18006D70F
0x18006d6ef  mov     r8d, [rdi+8]; Size
0x18006d6f3  xor     ebx, ebx
0x18006d6f5  mov     rdx, [rdi+10h]; Src
0x18006d6f9  mov     rcx, rax; void *
0x18006d6fc  call    memcpy_0
0x18006d701  jmp     short loc_18006D70F
0x18006d703  mov     ebx, 0C00D36BDh
0x18006d708  jmp     short loc_18006D70F
0x18006d70a  mov     ebx, 0C00D36E6h
0x18006d70f  mov     rcx, rbp; lpCriticalSection
0x18006d712  call    cs:__imp_LeaveCriticalSection
0x18006d719  nop     dword ptr [rax+rax+00h]
0x18006d71e  mov     eax, ebx
0x18006d720  add     rsp, 20h
0x18006d724  pop     r14
0x18006d726  pop     rdi
0x18006d727  pop     rsi
0x18006d728  pop     rbp
0x18006d729  pop     rbx
0x18006d72a  retn
```
