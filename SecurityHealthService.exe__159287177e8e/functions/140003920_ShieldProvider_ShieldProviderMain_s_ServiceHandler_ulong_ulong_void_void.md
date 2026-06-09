# ShieldProvider::ShieldProviderMain::s_ServiceHandler(ulong,ulong,void *,void *)

- ea: `0x140003920`
- end: `0x14000399b`
- name: `?s_ServiceHandler@ShieldProviderMain@ShieldProvider@@SAKKKPEAX0@Z`
- size: `123`
- prototype: `__int64 __fastcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x140003920`
- `0x140013010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x140003955`
- `KERNEL32!EnterCriticalSection` at `0x140003955`
- `KERNEL32!LeaveCriticalSection` at `0x140003984`
- `KERNEL32!LeaveCriticalSection` at `0x140003984`

## pseudocode

```c
__int64 __fastcall ShieldProvider::ShieldProviderMain::s_ServiceHandler(
        DWORD dwControl,
        DWORD dwEventType,
        LPVOID lpEventData,
        LPVOID lpContext)
{
  struct ShieldProvider::ShieldProviderMain *v8; // rsi
  unsigned int v9; // ebx
  __int64 (__fastcall *v10)(_QWORD, _QWORD, LPVOID, LPVOID); // rax

  v8 = ShieldProvider::g_pMain;
  v9 = 0;
  if ( ShieldProvider::g_pMain )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)ShieldProvider::g_pMain + 8));
    v10 = (__int64 (__fastcall *)(_QWORD, _QWORD, LPVOID, LPVOID))*((_QWORD *)v8 + 11);
    if ( v10 )
      v9 = v10(dwControl, dwEventType, lpEventData, lpContext);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v8 + 8));
  }
  return v9;
}

```

## disassembly

```asm
0x140003920  push    rbx
0x140003922  push    rbp
0x140003923  push    rsi
0x140003924  push    rdi
0x140003925  push    r12
0x140003927  push    r14
0x140003929  push    r15
0x14000392b  sub     rsp, 50h
0x14000392f  mov     rbp, r9
0x140003932  mov     r14, r8
0x140003935  mov     r15d, edx
0x140003938  mov     r12d, ecx
0x14000393b  mov     rsi, cs:?g_pMain@ShieldProvider@@3PEAVShieldProviderMain@1@EA; ShieldProvider::ShieldProviderMain * ShieldProvider::g_pMain
0x140003942  xor     ebx, ebx
0x140003944  test    rsi, rsi
0x140003947  jz      short loc_14000398A
0x140003949  lea     rdi, [rsi+8]
0x14000394d  mov     [rsp+88h+var_58], rdi
0x140003952  mov     rcx, rdi; lpCriticalSection
0x140003955  call    cs:__imp_EnterCriticalSection
0x14000395b  mov     [rsp+88h+var_50], 1
0x140003960  mov     [rsp+88h+var_48], 1
0x140003965  mov     rax, [rsi+58h]
0x140003969  test    rax, rax
0x14000396c  jz      short loc_140003981
0x14000396e  mov     r9, rbp
0x140003971  mov     r8, r14
0x140003974  mov     edx, r15d
0x140003977  mov     ecx, r12d
0x14000397a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000397f  mov     ebx, eax
0x140003981  mov     rcx, rdi; lpCriticalSection
0x140003984  call    cs:__imp_LeaveCriticalSection
0x14000398a  mov     eax, ebx
0x14000398c  add     rsp, 50h
0x140003990  pop     r15
0x140003992  pop     r14
0x140003994  pop     r12
0x140003996  pop     rdi
0x140003997  pop     rsi
0x140003998  pop     rbp
0x140003999  pop     rbx
0x14000399a  retn
```
