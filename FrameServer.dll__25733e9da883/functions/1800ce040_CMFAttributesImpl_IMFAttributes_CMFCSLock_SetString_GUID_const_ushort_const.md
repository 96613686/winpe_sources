# CMFAttributesImpl<IMFAttributes,CMFCSLock>::SetString(_GUID const &,ushort const *)

- ea: `0x1800ce040`
- end: `0x1800ce10d`
- name: `?SetString@?$CMFAttributesImpl@UIMFAttributes@@VCMFCSLock@@@@UEAAJAEBU_GUID@@PEBG@Z`
- size: `205`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800cc868`
- `0x1800ce040`
- `0x1800e924c`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ce0f6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ce0f6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ce05c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ce05c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ce0af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ce0af`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFAttributes,CMFCSLock>::SetString(__int64 a1, _DWORD *a2, _WORD *a3)
{
  __int64 Item; // rax
  __int64 v7; // rsi
  unsigned int v8; // ebx
  __int64 v9; // rax
  unsigned __int64 v10; // rax
  size_t v11; // rbp
  void *v12; // rax

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  Item = CMFAttributesImpl<IMFAttributes,CMFCSLock>::CreateItem(a1, a2);
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
    (*(void (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)a1 + 152LL))(a1, a2);
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
0x1800ce040  push    rbx
0x1800ce042  push    rbp
0x1800ce043  push    rsi
0x1800ce044  push    rdi
0x1800ce045  push    r12
0x1800ce047  push    r14
0x1800ce049  push    r15
0x1800ce04b  sub     rsp, 20h
0x1800ce04f  mov     rdi, rcx
0x1800ce052  mov     r14, r8
0x1800ce055  add     rcx, 8; lpCriticalSection
0x1800ce059  mov     rbx, rdx
0x1800ce05c  call    cs:__imp_EnterCriticalSection
0x1800ce062  mov     rdx, rbx
0x1800ce065  mov     rcx, rdi
0x1800ce068  call    ?CreateItem@?$CMFAttributesImpl@UIMFAttributes@@VCMFCSLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CMFCSLock>::CreateItem(_GUID const &)
0x1800ce06d  xor     r12d, r12d
0x1800ce070  mov     rsi, rax
0x1800ce073  test    r14, r14
0x1800ce076  jnz     short loc_1800CE07F
0x1800ce078  mov     ebx, 80070057h
0x1800ce07d  jmp     short loc_1800CE0F2
0x1800ce07f  test    rsi, rsi
0x1800ce082  jnz     short loc_1800CE08B
0x1800ce084  mov     ebx, 8007000Eh
0x1800ce089  jmp     short loc_1800CE0F2
0x1800ce08b  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ce08f  inc     rax
0x1800ce092  cmp     [r14+rax*2], r12w
0x1800ce097  jnz     short loc_1800CE08F
0x1800ce099  lea     rax, ds:2[rax*2]
0x1800ce0a1  mov     ecx, 0FFFFFFFFh
0x1800ce0a6  cmp     rax, rcx
0x1800ce0a9  jnb     short loc_1800CE078
0x1800ce0ab  mov     ecx, eax; cb
0x1800ce0ad  mov     ebp, eax
0x1800ce0af  call    cs:__imp_CoTaskMemAlloc
0x1800ce0b5  mov     [rsi+8], rax
0x1800ce0b9  test    rax, rax
0x1800ce0bc  jnz     short loc_1800CE0D5
0x1800ce0be  mov     rax, [rdi]
0x1800ce0c1  mov     rdx, rbx
0x1800ce0c4  mov     rcx, rdi
0x1800ce0c7  mov     rax, [rax+98h]
0x1800ce0ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce0d3  jmp     short loc_1800CE084
0x1800ce0d5  mov     r8, rbp; Size
0x1800ce0d8  mov     rdx, r14; Src
0x1800ce0db  mov     rcx, rax; void *
0x1800ce0de  mov     ebx, r12d
0x1800ce0e1  call    memcpy_0
0x1800ce0e6  mov     word ptr [rsi], 1Fh
0x1800ce0eb  mov     dword ptr [rdi+40h], 1
0x1800ce0f2  lea     rcx, [rdi+8]; lpCriticalSection
0x1800ce0f6  call    cs:__imp_LeaveCriticalSection
0x1800ce0fc  mov     eax, ebx
0x1800ce0fe  add     rsp, 20h
0x1800ce102  pop     r15
0x1800ce104  pop     r14
0x1800ce106  pop     r12
0x1800ce108  pop     rdi
0x1800ce109  pop     rsi
0x1800ce10a  pop     rbp
0x1800ce10b  pop     rbx
0x1800ce10c  retn
```
