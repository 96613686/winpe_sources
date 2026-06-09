# CAuthenticatorList::Age(_LARGE_INTEGER const &,_LARGE_INTEGER const &)

- ea: `0x1800838fc`
- end: `0x180083963`
- name: `?Age@CAuthenticatorList@@AEAAKAEBT_LARGE_INTEGER@@0@Z`
- size: `103`
- prototype: `__int64 __fastcall(PRTL_GENERIC_TABLE Table, const union _LARGE_INTEGER *, const union _LARGE_INTEGER *)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800838ac`
- `0x180083990`
- `0x180083c9c`

## callees

- `0x1800838fc`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180083950`
- `ntdll!RtlLeaveCriticalSection` at `0x180083950`
- `ntdll!RtlEnterCriticalSection` at `0x180083916`
- `ntdll!RtlEnterCriticalSection` at `0x180083916`
- `ntdll!RtlDeleteElementGenericTable` at `0x180083942`
- `ntdll!RtlDeleteElementGenericTable` at `0x180083942`
- `ntdll!RtlGetElementGenericTable` at `0x180083921`
- `ntdll!RtlGetElementGenericTable` at `0x180083921`

## pseudocode

```c
__int64 __fastcall CAuthenticatorList::Age(
        PRTL_GENERIC_TABLE Table,
        const union _LARGE_INTEGER *a2,
        const union _LARGE_INTEGER *a3)
{
  unsigned int v4; // ebx
  _QWORD *ElementGenericTable; // rax
  void *v8; // rdx
  LONGLONG v9; // rax

  v4 = 0;
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)&Table[1].InsertOrderList.Blink);
  do
  {
    ElementGenericTable = RtlGetElementGenericTable(Table, 0);
    v8 = ElementGenericTable;
    if ( !ElementGenericTable )
      break;
    v9 = *ElementGenericTable;
    if ( v9 >= a2->QuadPart && v9 <= a3->QuadPart )
      break;
    ++v4;
  }
  while ( RtlDeleteElementGenericTable(Table, v8) );
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)&Table[1].InsertOrderList.Blink);
  return v4;
}

```

## disassembly

```asm
0x1800838fc  push    rbx
0x1800838fe  push    rbp
0x1800838ff  push    rsi
0x180083900  push    rdi
0x180083901  push    r14
0x180083903  sub     rsp, 20h
0x180083907  mov     rsi, rcx
0x18008390a  xor     ebx, ebx
0x18008390c  add     rcx, 58h ; 'X'; CriticalSection
0x180083910  mov     rbp, r8
0x180083913  mov     r14, rdx
0x180083916  call    cs:__imp_RtlEnterCriticalSection
0x18008391c  xor     edx, edx; I
0x18008391e  mov     rcx, rsi; Table
0x180083921  call    cs:__imp_RtlGetElementGenericTable
0x180083927  mov     rdx, rax; Buffer
0x18008392a  test    rax, rax
0x18008392d  jz      short loc_18008394C
0x18008392f  mov     rax, [rax]
0x180083932  cmp     rax, [r14]
0x180083935  jl      short loc_18008393D
0x180083937  cmp     rax, [rbp+0]
0x18008393b  jle     short loc_18008394C
0x18008393d  mov     rcx, rsi; Table
0x180083940  inc     ebx
0x180083942  call    cs:__imp_RtlDeleteElementGenericTable
0x180083948  test    al, al
0x18008394a  jnz     short loc_18008391C
0x18008394c  lea     rcx, [rsi+58h]; CriticalSection
0x180083950  call    cs:__imp_RtlLeaveCriticalSection
0x180083956  mov     eax, ebx
0x180083958  add     rsp, 20h
0x18008395c  pop     r14
0x18008395e  pop     rdi
0x18008395f  pop     rsi
0x180083960  pop     rbp
0x180083961  pop     rbx
0x180083962  retn
```
