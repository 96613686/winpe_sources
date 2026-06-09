# CBaseInputPin::GetAllocator(IMemAllocator * *)

- ea: `0x1800042f0`
- end: `0x180004377`
- name: `?GetAllocator@CBaseInputPin@@UEAAJPEAPEAUIMemAllocator@@@Z`
- size: `135`
- prototype: `__int64 __fastcall(CBaseInputPin *__hidden this, struct IMemAllocator **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800042f0`
- `0x180034010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180004365`
- `KERNEL32!LeaveCriticalSection` at `0x180004365`
- `KERNEL32!EnterCriticalSection` at `0x180004316`
- `KERNEL32!EnterCriticalSection` at `0x180004316`
- `ole32!CoCreateInstance` at `0x18000433f`
- `ole32!CoCreateInstance` at `0x18000433f`

## pseudocode

```c
__int64 __fastcall CBaseInputPin::GetAllocator(CBaseInputPin *this, LPVOID *a2)
{
  struct _RTL_CRITICAL_SECTION *v5; // rdi
  LPVOID *ppv; // rbx
  HRESULT Instance; // esi

  if ( !a2 )
    return 2147500035LL;
  v5 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this - 19);
  EnterCriticalSection(v5);
  ppv = (LPVOID *)((char *)this + 8);
  if ( *ppv || (Instance = CoCreateInstance(&CLSID_MemoryAllocator, 0, 1u, &IID_IMemAllocator, ppv), Instance >= 0) )
  {
    *a2 = *ppv;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)*ppv + 8LL))(*ppv);
    Instance = 0;
  }
  LeaveCriticalSection(v5);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800042f0  push    rbx
0x1800042f2  push    rsi
0x1800042f3  push    rdi
0x1800042f4  push    r14
0x1800042f6  sub     rsp, 38h
0x1800042fa  mov     r14, rdx
0x1800042fd  mov     rbx, rcx
0x180004300  test    rdx, rdx
0x180004303  jnz     short loc_18000430C
0x180004305  mov     eax, 80004003h
0x18000430a  jmp     short loc_18000436D
0x18000430c  mov     rdi, [rcx-98h]
0x180004313  mov     rcx, rdi; lpCriticalSection
0x180004316  call    cs:__imp_EnterCriticalSection
0x18000431c  add     rbx, 8
0x180004320  cmp     qword ptr [rbx], 0
0x180004324  jnz     short loc_18000434B
0x180004326  xor     edx, edx; pUnkOuter
0x180004328  mov     [rsp+58h+ppv], rbx; ppv
0x18000432d  lea     r9, IID_IMemAllocator; riid
0x180004334  lea     rcx, CLSID_MemoryAllocator; rclsid
0x18000433b  lea     r8d, [rdx+1]; dwClsContext
0x18000433f  call    cs:__imp_CoCreateInstance
0x180004345  mov     esi, eax
0x180004347  test    eax, eax
0x180004349  js      short loc_180004362
0x18000434b  mov     rax, [rbx]
0x18000434e  mov     [r14], rax
0x180004351  mov     rcx, [rbx]
0x180004354  mov     rax, [rcx]
0x180004357  mov     rax, [rax+8]
0x18000435b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004360  xor     esi, esi
0x180004362  mov     rcx, rdi; lpCriticalSection
0x180004365  call    cs:__imp_LeaveCriticalSection
0x18000436b  mov     eax, esi
0x18000436d  add     rsp, 38h
0x180004371  pop     r14
0x180004373  pop     rdi
0x180004374  pop     rsi
0x180004375  pop     rbx
0x180004376  retn
```
