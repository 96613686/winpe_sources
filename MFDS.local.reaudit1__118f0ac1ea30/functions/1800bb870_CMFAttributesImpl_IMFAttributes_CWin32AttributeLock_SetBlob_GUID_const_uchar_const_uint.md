# CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::SetBlob(_GUID const &,uchar const *,uint)

- ea: `0x1800bb870`
- end: `0x1800bb926`
- name: `?SetBlob@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@PEBEI@Z`
- size: `182`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000fe60`
- `0x180074a12`
- `0x1800bb870`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bb908`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bb908`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bb88f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bb88f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bb8b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bb8b8`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::SetBlob(
        __int64 a1,
        __int64 a2,
        const void *a3,
        unsigned int a4)
{
  SIZE_T v5; // r15
  __int64 Item; // rsi
  unsigned int v9; // ebx
  void *v10; // rax

  v5 = a4;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  Item = CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::CreateItem(a1, a2);
  if ( Item )
  {
    v10 = CoTaskMemAlloc(v5);
    *(_QWORD *)(Item + 16) = v10;
    if ( v10 )
    {
      v9 = 0;
      memcpy_0(v10, a3, v5);
      *(_WORD *)Item = 4113;
      *(_DWORD *)(Item + 8) = v5;
      *(_DWORD *)(a1 + 64) = 1;
      goto LABEL_6;
    }
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 152LL))(a1, a2);
  }
  v9 = -2147024882;
LABEL_6:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  return v9;
}

```

## disassembly

```asm
0x1800bb870  push    rbx
0x1800bb872  push    rbp
0x1800bb873  push    rsi
0x1800bb874  push    rdi
0x1800bb875  push    r12
0x1800bb877  push    r14
0x1800bb879  push    r15
0x1800bb87b  sub     rsp, 20h
0x1800bb87f  mov     rdi, rcx
0x1800bb882  mov     r15d, r9d
0x1800bb885  add     rcx, 8; lpCriticalSection
0x1800bb889  mov     r12, r8
0x1800bb88c  mov     rbx, rdx
0x1800bb88f  call    cs:__imp_EnterCriticalSection
0x1800bb896  nop     dword ptr [rax+rax+00h]
0x1800bb89b  mov     rdx, rbx
0x1800bb89e  mov     rcx, rdi
0x1800bb8a1  call    ?CreateItem@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::CreateItem(_GUID const &)
0x1800bb8a6  mov     rsi, rax
0x1800bb8a9  test    rax, rax
0x1800bb8ac  jnz     short loc_1800BB8B5
0x1800bb8ae  mov     ebx, 8007000Eh
0x1800bb8b3  jmp     short loc_1800BB904
0x1800bb8b5  mov     rcx, r15; cb
0x1800bb8b8  call    cs:__imp_CoTaskMemAlloc
0x1800bb8bf  nop     dword ptr [rax+rax+00h]
0x1800bb8c4  mov     [rsi+10h], rax
0x1800bb8c8  test    rax, rax
0x1800bb8cb  jnz     short loc_1800BB8E4
0x1800bb8cd  mov     rax, [rdi]
0x1800bb8d0  mov     rdx, rbx
0x1800bb8d3  mov     rcx, rdi
0x1800bb8d6  mov     rax, [rax+98h]
0x1800bb8dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb8e2  jmp     short loc_1800BB8AE
0x1800bb8e4  xor     ebx, ebx
0x1800bb8e6  mov     r8, r15; Size
0x1800bb8e9  mov     rdx, r12; Src
0x1800bb8ec  mov     rcx, rax; void *
0x1800bb8ef  call    memcpy_0
0x1800bb8f4  mov     word ptr [rsi], 1011h
0x1800bb8f9  mov     [rsi+8], r15d
0x1800bb8fd  mov     dword ptr [rdi+40h], 1
0x1800bb904  lea     rcx, [rdi+8]; lpCriticalSection
0x1800bb908  call    cs:__imp_LeaveCriticalSection
0x1800bb90f  nop     dword ptr [rax+rax+00h]
0x1800bb914  mov     eax, ebx
0x1800bb916  add     rsp, 20h
0x1800bb91a  pop     r15
0x1800bb91c  pop     r14
0x1800bb91e  pop     r12
0x1800bb920  pop     rdi
0x1800bb921  pop     rsi
0x1800bb922  pop     rbp
0x1800bb923  pop     rbx
0x1800bb924  retn
```
