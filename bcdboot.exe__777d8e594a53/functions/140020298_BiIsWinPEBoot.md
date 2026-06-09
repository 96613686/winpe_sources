# BiIsWinPEBoot

- ea: `0x140020298`
- end: `0x14002031b`
- name: `BiIsWinPEBoot`
- size: `131`
- prototype: `bool()`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x14001a8c4`
- `0x14001b354`

## callees

- `0x14001f324`
- `0x140020298`

## import_xrefs

- `msvcrt!wcsstr` at `0x1400202ed`
- `msvcrt!wcsstr` at `0x1400202ed`
- `ntdll!RtlFreeHeap` at `0x14002030d`
- `ntdll!RtlFreeHeap` at `0x14002030d`

## string_xrefs

- `0x1400202b0`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control`

## pseudocode

```c
bool BiIsWinPEBoot()
{
  bool v0; // bl
  ULONG v2; // [rsp+40h] [rbp+8h] BYREF
  wchar_t *Str; // [rsp+48h] [rbp+10h] BYREF

  Str = 0;
  v2 = 0;
  v0 = 0;
  if ( (int)BiGetRegistryValue(
              0,
              L"SystemStartOptions",
              (__int64)L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Control",
              1u,
              &Str,
              &v2) >= 0 )
  {
    v0 = wcsstr(Str, L"MININT") != 0;
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Str);
  }
  return v0;
}

```

## disassembly

```asm
0x140020298  mov     r11, rsp
0x14002029b  push    rbx
0x14002029c  sub     rsp, 30h
0x1400202a0  lea     rax, [r11+8]
0x1400202a4  mov     qword ptr [r11+10h], 0
0x1400202ac  mov     [r11-10h], rax
0x1400202b0  lea     r8, aRegistryMachin_0; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x1400202b7  lea     rax, [r11+10h]
0x1400202bb  mov     [rsp+38h+arg_0], 0
0x1400202c3  mov     r9d, 1
0x1400202c9  mov     [r11-18h], rax
0x1400202cd  lea     rdx, aSystemstartopt; "SystemStartOptions"
0x1400202d4  xor     ecx, ecx
0x1400202d6  xor     bl, bl
0x1400202d8  call    BiGetRegistryValue
0x1400202dd  test    eax, eax
0x1400202df  js      short loc_140020313
0x1400202e1  mov     rcx, [rsp+38h+Str]; Str
0x1400202e6  lea     rdx, aMinint; "MININT"
0x1400202ed  call    cs:__imp_wcsstr
0x1400202f3  mov     rcx, gs:60h
0x1400202fc  test    rax, rax
0x1400202ff  mov     r8, [rsp+38h+Str]; P
0x140020304  setnz   bl
0x140020307  xor     edx, edx; Flags
0x140020309  mov     rcx, [rcx+30h]; HeapHandle
0x14002030d  call    cs:__imp_RtlFreeHeap
0x140020313  mov     al, bl
0x140020315  add     rsp, 30h
0x140020319  pop     rbx
0x14002031a  retn
```
