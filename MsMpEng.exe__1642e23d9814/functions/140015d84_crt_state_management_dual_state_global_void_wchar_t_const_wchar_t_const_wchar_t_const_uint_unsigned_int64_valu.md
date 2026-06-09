# __crt_state_management::dual_state_global<void (*)(wchar_t const *,wchar_t const *,wchar_t const *,uint,unsigned __int64)>::value(__crt_cached_ptd_host &)

- ea: `0x140015d84`
- end: `0x140015dd0`
- name: `?value@?$dual_state_global@P6AXPEB_W00I_K@Z@__crt_state_management@@QEAAAEAP6AXPEB_W00I_K@ZAEAV__crt_cached_ptd_host@@@Z`
- size: `76`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140015fe4`

## callees

- `0x140015d84`

## import_xrefs

- `KERNEL32!SetLastError` at `0x140015db0`
- `KERNEL32!SetLastError` at `0x140015db0`
- `KERNEL32!GetLastError` at `0x140015da0`
- `KERNEL32!GetLastError` at `0x140015da0`

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
0x140015d84  mov     [rsp+arg_0], rbx
0x140015d89  mov     [rsp+arg_8], rsi
0x140015d8e  push    rdi
0x140015d8f  sub     rsp, 20h
0x140015d93  xor     ebx, ebx
0x140015d95  mov     rdi, rdx
0x140015d98  mov     rsi, rcx
0x140015d9b  cmp     [rdx+10h], bl
0x140015d9e  jnz     short loc_140015DB8
0x140015da0  call    cs:GetLastError
0x140015da6  mov     ecx, eax; dwErrCode
0x140015da8  mov     [rdi+8], rbx
0x140015dac  mov     byte ptr [rdi+10h], 1
0x140015db0  call    cs:SetLastError
0x140015db6  jmp     short loc_140015DBC
0x140015db8  mov     rbx, [rdx+8]
0x140015dbc  lea     rax, [rsi+rbx*8]
0x140015dc0  mov     rbx, [rsp+28h+arg_0]
0x140015dc5  mov     rsi, [rsp+28h+arg_8]
0x140015dca  add     rsp, 20h
0x140015dce  pop     rdi
0x140015dcf  retn
```
