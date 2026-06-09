# ReleaseDataConvert(IDataConvert *)

- ea: `0x180020880`
- end: `0x180020904`
- name: `?ReleaseDataConvert@@YAXPEAUIDataConvert@@@Z`
- size: `132`
- prototype: `void __fastcall(struct IDataConvert *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18001a9f4`
- `0x18001fcdc`
- `0x1800232e4`

## callees

- `0x180020880`
- `0x180030010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800208a5`
- `KERNEL32!GetCurrentThreadId` at `0x1800208a5`
- `KERNEL32!LeaveCriticalSection` at `0x1800208f3`
- `KERNEL32!LeaveCriticalSection` at `0x1800208f3`
- `MSDART!UMSEnterCSWraper` at `0x180020899`
- `MSDART!UMSEnterCSWraper` at `0x180020899`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ReleaseDataConvert(struct IDataConvert *a1)
{
  unsigned __int8 *v1; // rbx
  __int64 v3; // rcx

  if ( a1 )
  {
    v1 = g_pcsDataConvert;
    UMSEnterCSWraper(g_pcsDataConvert);
    if ( !*((_DWORD *)v1 + 3) )
      *((_DWORD *)v1 + 2) = GetCurrentThreadId();
    ++*((_DWORD *)v1 + 3);
    ++*((_DWORD *)v1 + 4);
    if ( !(*(unsigned int (__fastcall **)(LPVOID))(*(_QWORD *)g_pIDataConvert + 16LL))(g_pIDataConvert) )
      g_pIDataConvert = 0;
    --*((_DWORD *)v1 + 4);
    if ( (*((_DWORD *)v1 + 3))-- == 1 )
      *((_DWORD *)v1 + 2) = -1;
    v3 = *(_QWORD *)v1;
    --*(_DWORD *)(v3 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 8));
  }
}

```

## disassembly

```asm
0x180020880  test    rcx, rcx
0x180020883  jz      short locret_180020903
0x180020885  mov     [rsp+arg_8], rbx
0x18002088a  push    rdi
0x18002088b  sub     rsp, 20h
0x18002088f  mov     rbx, cs:?g_pcsDataConvert@@3PEAVCFoxCriticalSection@@EA; CFoxCriticalSection * g_pcsDataConvert
0x180020896  mov     rcx, rbx
0x180020899  call    cs:__imp_UMSEnterCSWraper
0x18002089f  cmp     dword ptr [rbx+0Ch], 0
0x1800208a3  jnz     short loc_1800208AE
0x1800208a5  call    cs:__imp_GetCurrentThreadId
0x1800208ab  mov     [rbx+8], eax
0x1800208ae  inc     dword ptr [rbx+0Ch]
0x1800208b1  inc     dword ptr [rbx+10h]
0x1800208b4  mov     [rsp+28h+arg_0], rbx
0x1800208b9  mov     rcx, cs:?g_pIDataConvert@@3PEAUIDataConvert@@EA; IDataConvert * g_pIDataConvert
0x1800208c0  mov     rax, [rcx]
0x1800208c3  mov     rax, [rax+10h]
0x1800208c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800208cc  test    eax, eax
0x1800208ce  jnz     short loc_1800208DB
0x1800208d0  mov     cs:?g_pIDataConvert@@3PEAUIDataConvert@@EA, 0; IDataConvert * g_pIDataConvert
0x1800208db  or      ecx, 0FFFFFFFFh
0x1800208de  add     [rbx+10h], ecx
0x1800208e1  add     [rbx+0Ch], ecx
0x1800208e4  jnz     short loc_1800208E9
0x1800208e6  mov     [rbx+8], ecx
0x1800208e9  mov     rcx, [rbx]
0x1800208ec  dec     dword ptr [rcx+30h]
0x1800208ef  add     rcx, 8; lpCriticalSection
0x1800208f3  call    cs:__imp_LeaveCriticalSection
0x1800208f9  mov     rbx, [rsp+28h+arg_8]
0x1800208fe  add     rsp, 20h
0x180020902  pop     rdi
0x180020903  retn
```
