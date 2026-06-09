# CMFAttributesImpl<IMFAttributes,CMFCSLock>::SetString(_GUID const &,ushort const *)

- ea: `0x18007a5b0`
- end: `0x18007a693`
- name: `?SetString@?$CMFAttributesImpl@UIMFAttributes@@VCMFCSLock@@@@UEAAJAEBU_GUID@@PEBG@Z`
- size: `227`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800781c8`
- `0x18007a5b0`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18007a602`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18007a602`
- `api-ms-win-crt-private-l1-1-0!memcpy` at `0x18007a65b`
- `api-ms-win-crt-private-l1-1-0!memcpy` at `0x18007a65b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007a677`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007a677`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007a5ca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007a5ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007a624`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007a624`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFAttributes,CMFCSLock>::SetString(__int64 a1, _DWORD *a2, const wchar_t *a3)
{
  PROPVARIANT *Item; // rax
  PROPVARIANT *v7; // rsi
  unsigned int v8; // ebx
  size_t v9; // rax
  size_t v10; // rbp
  void *v11; // rax

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  Item = CMFAttributesImpl<IMFAttributes,CMFCSLock>::CreateItem(a1, a2);
  v7 = Item;
  if ( !a3 )
    goto LABEL_2;
  if ( !Item )
  {
LABEL_4:
    v8 = -2147024882;
    goto LABEL_9;
  }
  v9 = 2 * wcslen(a3) + 2;
  if ( v9 < 0xFFFFFFFF )
  {
    v10 = (unsigned int)v9;
    v11 = CoTaskMemAlloc((unsigned int)v9);
    v7->hVal.QuadPart = (LONGLONG)v11;
    if ( v11 )
    {
      v8 = 0;
      memcpy(v11, a3, v10);
      v7->vt = 31;
      *(_DWORD *)(a1 + 64) = 1;
      goto LABEL_9;
    }
    (*(void (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)a1 + 152LL))(a1, a2);
    goto LABEL_4;
  }
LABEL_2:
  v8 = -2147024809;
LABEL_9:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  return v8;
}

```

## disassembly

```asm
0x18007a5b0  push    rbx
0x18007a5b2  push    rbp
0x18007a5b3  push    rsi
0x18007a5b4  push    rdi
0x18007a5b5  push    r14
0x18007a5b7  push    r15
0x18007a5b9  sub     rsp, 28h
0x18007a5bd  mov     rdi, rcx
0x18007a5c0  mov     r14, r8
0x18007a5c3  add     rcx, 8; lpCriticalSection
0x18007a5c7  mov     rbx, rdx
0x18007a5ca  call    cs:__imp_EnterCriticalSection
0x18007a5d1  nop     dword ptr [rax+rax+00h]
0x18007a5d6  mov     rdx, rbx
0x18007a5d9  mov     rcx, rdi
0x18007a5dc  call    ?CreateItem@?$CMFAttributesImpl@UIMFAttributes@@VCMFCSLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CMFCSLock>::CreateItem(_GUID const &)
0x18007a5e1  mov     rsi, rax
0x18007a5e4  test    r14, r14
0x18007a5e7  jnz     short loc_18007A5F3
0x18007a5e9  mov     ebx, 80070057h
0x18007a5ee  jmp     loc_18007A673
0x18007a5f3  test    rsi, rsi
0x18007a5f6  jnz     short loc_18007A5FF
0x18007a5f8  mov     ebx, 8007000Eh
0x18007a5fd  jmp     short loc_18007A673
0x18007a5ff  mov     rcx, r14; String
0x18007a602  call    cs:__imp_wcslen
0x18007a609  nop     dword ptr [rax+rax+00h]
0x18007a60e  mov     ecx, 0FFFFFFFFh
0x18007a613  lea     rax, ds:2[rax*2]
0x18007a61b  cmp     rax, rcx
0x18007a61e  jnb     short loc_18007A5E9
0x18007a620  mov     ecx, eax; cb
0x18007a622  mov     ebp, eax
0x18007a624  call    cs:__imp_CoTaskMemAlloc
0x18007a62b  nop     dword ptr [rax+rax+00h]
0x18007a630  mov     [rsi+8], rax
0x18007a634  test    rax, rax
0x18007a637  jnz     short loc_18007A650
0x18007a639  mov     rax, [rdi]
0x18007a63c  mov     rdx, rbx
0x18007a63f  mov     rcx, rdi
0x18007a642  mov     rax, [rax+98h]
0x18007a649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a64e  jmp     short loc_18007A5F8
0x18007a650  xor     ebx, ebx
0x18007a652  mov     r8, rbp; Size
0x18007a655  mov     rdx, r14; Src
0x18007a658  mov     rcx, rax; void *
0x18007a65b  call    cs:__imp_memcpy
0x18007a662  nop     dword ptr [rax+rax+00h]
0x18007a667  mov     word ptr [rsi], 1Fh
0x18007a66c  mov     dword ptr [rdi+40h], 1
0x18007a673  lea     rcx, [rdi+8]; lpCriticalSection
0x18007a677  call    cs:__imp_LeaveCriticalSection
0x18007a67e  nop     dword ptr [rax+rax+00h]
0x18007a683  mov     eax, ebx
0x18007a685  add     rsp, 28h
0x18007a689  pop     r15
0x18007a68b  pop     r14
0x18007a68d  pop     rdi
0x18007a68e  pop     rsi
0x18007a68f  pop     rbp
0x18007a690  pop     rbx
0x18007a691  retn
```
