# __crt_state_management::dual_state_global<void (*)(wchar_t const *,wchar_t const *,wchar_t const *,uint,unsigned __int64)>::value(__crt_cached_ptd_host &)

- ea: `0x1400043b4`
- end: `0x140004400`
- name: `?value@?$dual_state_global@P6AXPEB_W00I_K@Z@__crt_state_management@@QEAAAEAP6AXPEB_W00I_K@ZAEAV__crt_cached_ptd_host@@@Z`
- size: `76`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140004614`

## callees

- `0x1400043b4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400043d0`
- `KERNEL32!GetLastError` at `0x1400043d0`
- `KERNEL32!SetLastError` at `0x1400043e0`
- `KERNEL32!SetLastError` at `0x1400043e0`

## pseudocode

```c
__int64 __fastcall __crt_state_management::dual_state_global<void (*)(wchar_t const *,wchar_t const *,wchar_t const *,unsigned int,unsigned __int64)>::value(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rbx
  DWORD LastError; // eax

  v2 = 0;
  if ( *(_BYTE *)(a2 + 16) )
  {
    v2 = *(_QWORD *)(a2 + 8);
  }
  else
  {
    LastError = GetLastError();
    *(_QWORD *)(a2 + 8) = 0;
    *(_BYTE *)(a2 + 16) = 1;
    SetLastError(LastError);
  }
  return a1 + 8 * v2;
}

```

## disassembly

```asm
0x1400043b4  mov     [rsp+arg_0], rbx
0x1400043b9  mov     [rsp+arg_8], rsi
0x1400043be  push    rdi
0x1400043bf  sub     rsp, 20h
0x1400043c3  xor     ebx, ebx
0x1400043c5  mov     rdi, rdx
0x1400043c8  mov     rsi, rcx
0x1400043cb  cmp     [rdx+10h], bl
0x1400043ce  jnz     short loc_1400043E8
0x1400043d0  call    cs:GetLastError
0x1400043d6  mov     ecx, eax; dwErrCode
0x1400043d8  mov     [rdi+8], rbx
0x1400043dc  mov     byte ptr [rdi+10h], 1
0x1400043e0  call    cs:SetLastError
0x1400043e6  jmp     short loc_1400043EC
0x1400043e8  mov     rbx, [rdx+8]
0x1400043ec  lea     rax, [rsi+rbx*8]
0x1400043f0  mov     rbx, [rsp+28h+arg_0]
0x1400043f5  mov     rsi, [rsp+28h+arg_8]
0x1400043fa  add     rsp, 20h
0x1400043fe  pop     rdi
0x1400043ff  retn
```
