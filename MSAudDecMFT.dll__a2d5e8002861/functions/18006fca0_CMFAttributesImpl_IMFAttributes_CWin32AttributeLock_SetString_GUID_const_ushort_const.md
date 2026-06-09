# CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::SetString(_GUID const &,ushort const *)

- ea: `0x18006fca0`
- end: `0x18006fd81`
- name: `?SetString@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@PEBG@Z`
- size: `225`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006e004`

## callees

- `0x18006cf6c`
- `0x18006fca0`
- `0x18009606c`
- `0x1800960c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006fd63`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006fd63`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006fcbc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006fcbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006fd15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006fd15`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::SetString(__int64 a1, __int64 a2, _WORD *a3)
{
  __int64 Item; // rax
  __int64 v7; // rsi
  unsigned int v8; // ebx
  __int64 v9; // rax
  unsigned __int64 v10; // rax
  size_t v11; // rbp
  void *v12; // rax

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  Item = CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::CreateItem(a1, a2);
  v7 = Item;
  if ( !a3 )
    goto LABEL_2;
  if ( !Item )
  {
LABEL_4:
    v8 = -2147024882;
    goto LABEL_11;
  }
  v9 = -1;
  do
    ++v9;
  while ( a3[v9] );
  v10 = 2 * v9 + 2;
  if ( v10 < 0xFFFFFFFF )
  {
    v11 = (unsigned int)v10;
    v12 = CoTaskMemAlloc((unsigned int)v10);
    *(_QWORD *)(v7 + 8) = v12;
    if ( v12 )
    {
      v8 = 0;
      memcpy_0(v12, a3, v11);
      *(_WORD *)v7 = 31;
      *(_DWORD *)(a1 + 64) = 1;
      goto LABEL_11;
    }
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 152LL))(a1, a2);
    goto LABEL_4;
  }
LABEL_2:
  v8 = -2147024809;
LABEL_11:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  return v8;
}

```

## disassembly

```asm
0x18006fca0  push    rbx
0x18006fca2  push    rbp
0x18006fca3  push    rsi
0x18006fca4  push    rdi
0x18006fca5  push    r12
0x18006fca7  push    r14
0x18006fca9  push    r15
0x18006fcab  sub     rsp, 20h
0x18006fcaf  mov     rdi, rcx
0x18006fcb2  mov     r14, r8
0x18006fcb5  add     rcx, 8; lpCriticalSection
0x18006fcb9  mov     rbx, rdx
0x18006fcbc  call    cs:__imp_EnterCriticalSection
0x18006fcc3  nop     dword ptr [rax+rax+00h]
0x18006fcc8  mov     rdx, rbx
0x18006fccb  mov     rcx, rdi
0x18006fcce  call    ?CreateItem@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::CreateItem(_GUID const &)
0x18006fcd3  xor     r12d, r12d
0x18006fcd6  mov     rsi, rax
0x18006fcd9  test    r14, r14
0x18006fcdc  jnz     short loc_18006FCE5
0x18006fcde  mov     ebx, 80070057h
0x18006fce3  jmp     short loc_18006FD5F
0x18006fce5  test    rsi, rsi
0x18006fce8  jnz     short loc_18006FCF1
0x18006fcea  mov     ebx, 8007000Eh
0x18006fcef  jmp     short loc_18006FD5F
0x18006fcf1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006fcf5  inc     rax
0x18006fcf8  cmp     [r14+rax*2], r12w
0x18006fcfd  jnz     short loc_18006FCF5
0x18006fcff  lea     rax, ds:2[rax*2]
0x18006fd07  mov     ecx, 0FFFFFFFFh
0x18006fd0c  cmp     rax, rcx
0x18006fd0f  jnb     short loc_18006FCDE
0x18006fd11  mov     ecx, eax; cb
0x18006fd13  mov     ebp, eax
0x18006fd15  call    cs:__imp_CoTaskMemAlloc
0x18006fd1c  nop     dword ptr [rax+rax+00h]
0x18006fd21  mov     [rsi+8], rax
0x18006fd25  test    rax, rax
0x18006fd28  jnz     short loc_18006FD42
0x18006fd2a  mov     rax, [rdi]
0x18006fd2d  mov     rdx, rbx
0x18006fd30  mov     rcx, rdi
0x18006fd33  mov     rax, [rax+98h]
0x18006fd3a  call    cs:__guard_dispatch_icall_fptr
0x18006fd40  jmp     short loc_18006FCEA
0x18006fd42  mov     r8, rbp; Size
0x18006fd45  mov     rdx, r14; Src
0x18006fd48  mov     rcx, rax; void *
0x18006fd4b  mov     ebx, r12d
0x18006fd4e  call    memcpy_0
0x18006fd53  mov     word ptr [rsi], 1Fh
0x18006fd58  mov     dword ptr [rdi+40h], 1
0x18006fd5f  lea     rcx, [rdi+8]; lpCriticalSection
0x18006fd63  call    cs:__imp_LeaveCriticalSection
0x18006fd6a  nop     dword ptr [rax+rax+00h]
0x18006fd6f  mov     eax, ebx
0x18006fd71  add     rsp, 20h
0x18006fd75  pop     r15
0x18006fd77  pop     r14
0x18006fd79  pop     r12
0x18006fd7b  pop     rdi
0x18006fd7c  pop     rsi
0x18006fd7d  pop     rbp
0x18006fd7e  pop     rbx
0x18006fd7f  retn
```
