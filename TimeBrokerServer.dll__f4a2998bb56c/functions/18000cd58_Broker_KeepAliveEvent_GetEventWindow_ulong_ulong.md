# Broker::KeepAliveEvent::GetEventWindow(ulong,ulong)

- ea: `0x18000cd58`
- end: `0x18000cdf2`
- name: `?GetEventWindow@KeepAliveEvent@Broker@@CAKKK@Z`
- size: `154`
- prototype: `__int64 __fastcall(unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000cca0`
- `0x18001811c`

## callees

- `0x18000cd58`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000cdb0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000cdb0`

## string_xrefs

- `0x18000cda1`: `SYSTEM\CurrentControlSet\Services\TimeBroker\Parameters`

## pseudocode

```c
__int64 __fastcall Broker::KeepAliveEvent::GetEventWindow(unsigned int a1, unsigned int a2)
{
  __int64 result; // rax
  DWORD v5; // [rsp+60h] [rbp+18h] BYREF

  result = (unsigned int)dword_18002667C;
  v5 = 4;
  if ( !dword_18002667C )
  {
    if ( RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"SYSTEM\\CurrentControlSet\\Services\\TimeBroker\\Parameters",
           L"MinKeepAliveTolerance",
           0x18u,
           0,
           &dword_18002667C,
           &v5) )
    {
      result = 0xFFFFFFFFLL;
      dword_18002667C = -1;
    }
    else
    {
      result = (unsigned int)dword_18002667C;
    }
    if ( !(_DWORD)result )
    {
      result = 0xFFFFFFFFLL;
      dword_18002667C = -1;
    }
  }
  if ( (_DWORD)result == -1 || a1 >= (unsigned int)result || (unsigned int)result >= a2 )
    return a1;
  return result;
}

```

## disassembly

```asm
0x18000cd58  mov     r11, rsp
0x18000cd5b  mov     [r11+8], rbx
0x18000cd5f  push    rdi
0x18000cd60  sub     rsp, 40h
0x18000cd64  mov     eax, cs:dword_18002667C
0x18000cd6a  mov     edi, edx
0x18000cd6c  mov     [rsp+48h+arg_10], 4
0x18000cd74  mov     ebx, ecx
0x18000cd76  test    eax, eax
0x18000cd78  jnz     short loc_18000CDD8
0x18000cd7a  lea     rax, [r11+18h]
0x18000cd7e  mov     r9d, 18h; dwFlags
0x18000cd84  mov     [r11-18h], rax
0x18000cd88  lea     r8, Value; "MinKeepAliveTolerance"
0x18000cd8f  lea     rax, dword_18002667C
0x18000cd96  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000cd9d  mov     [r11-20h], rax
0x18000cda1  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ti"...
0x18000cda8  mov     qword ptr [r11-28h], 0
0x18000cdb0  call    cs:__imp_RegGetValueW
0x18000cdb6  test    eax, eax
0x18000cdb8  jz      short loc_18000CDC5
0x18000cdba  or      eax, 0FFFFFFFFh
0x18000cdbd  mov     cs:dword_18002667C, eax
0x18000cdc3  jmp     short loc_18000CDCB
0x18000cdc5  mov     eax, cs:dword_18002667C
0x18000cdcb  test    eax, eax
0x18000cdcd  jnz     short loc_18000CDD8
0x18000cdcf  or      eax, 0FFFFFFFFh
0x18000cdd2  mov     cs:dword_18002667C, eax
0x18000cdd8  cmp     eax, 0FFFFFFFFh
0x18000cddb  jz      short loc_18000CDE5
0x18000cddd  cmp     ebx, eax
0x18000cddf  jnb     short loc_18000CDE5
0x18000cde1  cmp     eax, edi
0x18000cde3  jb      short loc_18000CDE7
0x18000cde5  mov     eax, ebx
0x18000cde7  mov     rbx, [rsp+48h+arg_0]
0x18000cdec  add     rsp, 40h
0x18000cdf0  pop     rdi
0x18000cdf1  retn
```
