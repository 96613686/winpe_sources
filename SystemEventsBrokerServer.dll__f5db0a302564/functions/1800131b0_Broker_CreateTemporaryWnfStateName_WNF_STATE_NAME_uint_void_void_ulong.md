# Broker::CreateTemporaryWnfStateName(_WNF_STATE_NAME *,uint,void *,void *,ulong)

- ea: `0x1800131b0`
- end: `0x180013220`
- name: `?CreateTemporaryWnfStateName@Broker@@YAJPEAU_WNF_STATE_NAME@@IPEAX1K@Z`
- size: `112`
- prototype: `__int64 __fastcall(Broker *this, struct _WNF_STATE_NAME *, void *, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001305c`

## callees

- `0x1800131b0`
- `0x180013228`

## import_xrefs

- `ntdll!NtCreateWnfStateName` at `0x1800131f7`
- `ntdll!NtCreateWnfStateName` at `0x1800131f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800131ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800131ff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001320d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001320d`

## pseudocode

```c
__int64 __fastcall Broker::CreateTemporaryWnfStateName(Broker *this, struct _WNF_STATE_NAME *a2, void *a3, void *a4)
{
  void *Sd; // rdi
  unsigned int WnfStateName; // ebx
  HANDLE ProcessHeap; // rax
  unsigned int v9; // [rsp+20h] [rbp-28h]

  Sd = Broker::CreateSd(a3, a2, (unsigned int)a3, a4, v9);
  if ( !Sd )
    return 3221225485LL;
  WnfStateName = NtCreateWnfStateName(this, 3, 0);
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, Sd);
  return WnfStateName;
}

```

## disassembly

```asm
0x1800131b0  mov     [rsp+arg_0], rbx
0x1800131b5  push    rdi
0x1800131b6  sub     rsp, 40h
0x1800131ba  mov     rbx, rcx
0x1800131bd  mov     rcx, r8; Owner
0x1800131c0  call    ?CreateSd@Broker@@YAPEAXPEAXK0K@Z; Broker::CreateSd(void *,ulong,void *,ulong)
0x1800131c5  mov     rdi, rax
0x1800131c8  test    rax, rax
0x1800131cb  jnz     short loc_1800131D4
0x1800131cd  mov     eax, 0C000000Dh
0x1800131d2  jmp     short loc_180013215
0x1800131d4  xor     r9d, r9d
0x1800131d7  mov     [rsp+48h+var_18], rdi
0x1800131dc  mov     [rsp+48h+var_20], 8
0x1800131e4  xor     r8d, r8d
0x1800131e7  mov     rcx, rbx
0x1800131ea  mov     [rsp+48h+var_28], 0
0x1800131f3  lea     edx, [r9+3]
0x1800131f7  call    cs:__imp_NtCreateWnfStateName
0x1800131fd  mov     ebx, eax
0x1800131ff  call    cs:__imp_GetProcessHeap
0x180013205  mov     r8, rdi; lpMem
0x180013208  xor     edx, edx; dwFlags
0x18001320a  mov     rcx, rax; hHeap
0x18001320d  call    cs:__imp_HeapFree
0x180013213  mov     eax, ebx
0x180013215  mov     rbx, [rsp+48h+arg_0]
0x18001321a  add     rsp, 40h
0x18001321e  pop     rdi
0x18001321f  retn
```
