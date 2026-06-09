# BiIsPortableWorkspaceBoot

- ea: `0x1400201ec`
- end: `0x140020291`
- name: `BiIsPortableWorkspaceBoot`
- size: `165`
- prototype: `bool()`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x140021f58`
- `0x140023714`

## callees

- `0x14001e5e4`
- `0x14001f324`
- `0x14001f980`
- `0x1400201ec`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x140020283`
- `ntdll!RtlFreeHeap` at `0x140020283`

## string_xrefs

- `0x140020245`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control`
- `0x14002020e`: `\Registry\Machine\System\CurrentControlSet\Control\MiniNT`

## pseudocode

```c
bool BiIsPortableWorkspaceBoot()
{
  bool v0; // bl
  ULONG v2; // [rsp+40h] [rbp+8h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp+10h] BYREF
  PVOID P; // [rsp+50h] [rbp+18h] BYREF

  P = 0;
  Handle = 0;
  v2 = 0;
  v0 = 0;
  if ( (int)BiOpenKey(0, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\MiniNT", 131097, &Handle) < 0 )
  {
    if ( (int)BiGetRegistryValue(
                0,
                L"PortableOperatingSystem",
                (__int64)L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Control",
                4u,
                &P,
                &v2) >= 0 )
    {
      v0 = *(_DWORD *)P != 0;
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
    }
  }
  else
  {
    BiCloseKey(Handle);
  }
  return v0;
}

```

## disassembly

```asm
0x1400201ec  mov     rax, rsp
0x1400201ef  push    rbx
0x1400201f0  sub     rsp, 30h
0x1400201f4  lea     r9, [rax+10h]
0x1400201f8  mov     qword ptr [rax+18h], 0
0x140020200  mov     r8d, 20019h
0x140020206  mov     qword ptr [rax+10h], 0
0x14002020e  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x140020215  mov     dword ptr [rax+8], 0
0x14002021c  xor     ecx, ecx
0x14002021e  xor     bl, bl
0x140020220  call    BiOpenKey
0x140020225  test    eax, eax
0x140020227  js      short loc_140020235
0x140020229  mov     rcx, [rsp+38h+Handle]; Handle
0x14002022e  call    BiCloseKey
0x140020233  jmp     short loc_140020289
0x140020235  lea     rax, [rsp+38h+arg_0]
0x14002023a  mov     r9d, 4
0x140020240  mov     [rsp+38h+var_10], rax
0x140020245  lea     r8, aRegistryMachin_0; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x14002024c  lea     rax, [rsp+38h+P]
0x140020251  xor     ecx, ecx
0x140020253  lea     rdx, aPortableoperat; "PortableOperatingSystem"
0x14002025a  mov     [rsp+38h+var_18], rax
0x14002025f  call    BiGetRegistryValue
0x140020264  test    eax, eax
0x140020266  js      short loc_140020289
0x140020268  mov     r8, [rsp+38h+P]; P
0x14002026d  mov     rcx, gs:60h
0x140020276  cmp     dword ptr [r8], 0
0x14002027a  mov     rcx, [rcx+30h]; HeapHandle
0x14002027e  setnz   bl
0x140020281  xor     edx, edx; Flags
0x140020283  call    cs:__imp_RtlFreeHeap
0x140020289  mov     al, bl
0x14002028b  add     rsp, 30h
0x14002028f  pop     rbx
0x140020290  retn
```
