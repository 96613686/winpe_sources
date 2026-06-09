# SiIsWinPEBoot

- ea: `0x14001d3f8`
- end: `0x14001d473`
- name: `SiIsWinPEBoot`
- size: `123`
- prototype: `bool __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x140013484`
- `0x1400254d0`

## callees

- `0x14001d260`
- `0x14001d3f8`

## import_xrefs

- `msvcrt!wcsstr` at `0x14001d445`
- `msvcrt!wcsstr` at `0x14001d445`
- `ntdll!RtlFreeHeap` at `0x14001d465`
- `ntdll!RtlFreeHeap` at `0x14001d465`

## string_xrefs

- `0x14001d410`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control`

## pseudocode

```c
bool __fastcall SiIsWinPEBoot(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  bool v4; // bl
  ULONG v6; // [rsp+40h] [rbp+8h] BYREF
  wchar_t *Str; // [rsp+48h] [rbp+10h] BYREF

  Str = 0;
  v6 = 0;
  v4 = 0;
  if ( (int)SiGetRegistryValue(
              a1,
              L"SystemStartOptions",
              (__int64)L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Control",
              a4,
              &Str,
              &v6) >= 0 )
  {
    v4 = wcsstr(Str, L"MININT") != 0;
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Str);
  }
  return v4;
}

```

## disassembly

```asm
0x14001d3f8  mov     r11, rsp
0x14001d3fb  push    rbx
0x14001d3fc  sub     rsp, 30h
0x14001d400  lea     rax, [r11+8]
0x14001d404  mov     qword ptr [r11+10h], 0
0x14001d40c  mov     [r11-10h], rax
0x14001d410  lea     r8, aRegistryMachin_0; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x14001d417  lea     rax, [r11+10h]
0x14001d41b  mov     [rsp+38h+arg_0], 0
0x14001d423  lea     rdx, aSystemstartopt; "SystemStartOptions"
0x14001d42a  mov     [r11-18h], rax
0x14001d42e  xor     bl, bl
0x14001d430  call    SiGetRegistryValue
0x14001d435  test    eax, eax
0x14001d437  js      short loc_14001D46B
0x14001d439  mov     rcx, [rsp+38h+Str]; Str
0x14001d43e  lea     rdx, aMinint; "MININT"
0x14001d445  call    cs:__imp_wcsstr
0x14001d44b  mov     rcx, gs:60h
0x14001d454  test    rax, rax
0x14001d457  mov     r8, [rsp+38h+Str]; P
0x14001d45c  setnz   bl
0x14001d45f  xor     edx, edx; Flags
0x14001d461  mov     rcx, [rcx+30h]; HeapHandle
0x14001d465  call    cs:__imp_RtlFreeHeap
0x14001d46b  mov     al, bl
0x14001d46d  add     rsp, 30h
0x14001d471  pop     rbx
0x14001d472  retn
```
