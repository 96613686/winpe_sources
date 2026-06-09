# CProviderDSO::CloseSession(void)

- ea: `0x18002cf30`
- end: `0x18002cf93`
- name: `?CloseSession@CProviderDSO@@UEAAXXZ`
- size: `99`
- prototype: `void __fastcall(CProviderDSO *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18002cf30`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18002cf52`
- `KERNEL32!GetCurrentThreadId` at `0x18002cf52`
- `KERNEL32!LeaveCriticalSection` at `0x18002cf8c`
- `MSDART!UMSEnterCSWraper` at `0x18002cf46`
- `MSDART!UMSEnterCSWraper` at `0x18002cf46`

## pseudocode

```c
void __fastcall CProviderDSO::CloseSession(CProviderDSO *this)
{
  __int64 v3; // rcx

  UMSEnterCSWraper((char *)this + 72);
  if ( !*((_DWORD *)this + 21) )
    *((_DWORD *)this + 20) = GetCurrentThreadId();
  ++*((_DWORD *)this + 21);
  ++*((_DWORD *)this + 22);
  --*((_DWORD *)this + 16);
  --*((_DWORD *)this + 22);
  if ( (*((_DWORD *)this + 21))-- == 1 )
    *((_DWORD *)this + 20) = -1;
  v3 = *((_QWORD *)this + 9);
  --*(_DWORD *)(v3 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 8));
}

```

## disassembly

```asm
0x18002cf30  mov     [rsp+arg_8], rbx
0x18002cf35  mov     [rsp+arg_10], rsi
0x18002cf3a  push    rdi
0x18002cf3b  sub     rsp, 20h
0x18002cf3f  mov     rsi, rcx
0x18002cf42  add     rcx, 48h ; 'H'
0x18002cf46  call    cs:__imp_UMSEnterCSWraper
0x18002cf4c  cmp     dword ptr [rsi+54h], 0
0x18002cf50  jnz     short loc_18002CF5B
0x18002cf52  call    cs:__imp_GetCurrentThreadId
0x18002cf58  mov     [rsi+50h], eax
0x18002cf5b  inc     dword ptr [rsi+54h]
0x18002cf5e  or      ecx, 0FFFFFFFFh
0x18002cf61  inc     dword ptr [rsi+58h]
0x18002cf64  add     [rsi+40h], ecx
0x18002cf67  add     [rsi+58h], ecx
0x18002cf6a  add     [rsi+54h], ecx
0x18002cf6d  jnz     short loc_18002CF72
0x18002cf6f  mov     [rsi+50h], ecx
0x18002cf72  mov     rcx, [rsi+48h]
0x18002cf76  dec     dword ptr [rcx+30h]
0x18002cf79  add     rcx, 8
0x18002cf7d  mov     rbx, [rsp+28h+arg_8]
0x18002cf82  mov     rsi, [rsp+28h+arg_10]
0x18002cf87  add     rsp, 20h
0x18002cf8b  pop     rdi
0x18002cf8c  jmp     cs:__imp_LeaveCriticalSection
```
