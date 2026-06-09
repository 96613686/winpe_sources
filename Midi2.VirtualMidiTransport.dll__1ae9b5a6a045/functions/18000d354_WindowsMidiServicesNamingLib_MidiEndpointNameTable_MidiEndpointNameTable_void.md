# WindowsMidiServicesNamingLib::MidiEndpointNameTable::MidiEndpointNameTable(void)

- ea: `0x18000d354`
- end: `0x18000d3e8`
- name: `??0MidiEndpointNameTable@WindowsMidiServicesNamingLib@@QEAA@XZ`
- size: `148`
- prototype: `__int64 __fastcall(WindowsMidiServicesNamingLib::MidiEndpointNameTable *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18000d9b4`

## callees

- `0x180003940`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
WindowsMidiServicesNamingLib::MidiEndpointNameTable *__fastcall WindowsMidiServicesNamingLib::MidiEndpointNameTable::MidiEndpointNameTable(
        WindowsMidiServicesNamingLib::MidiEndpointNameTable *this)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rax

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  v2 = operator new(0x38u);
  *v2 = v2;
  v2[1] = v2;
  v2[2] = v2;
  *((_WORD *)v2 + 12) = 257;
  *(_QWORD *)this = v2;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  v3 = operator new(0x38u);
  *v3 = v3;
  v3[1] = v3;
  v3[2] = v3;
  *((_WORD *)v3 + 12) = 257;
  *((_QWORD *)this + 2) = v3;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  return this;
}

```

## disassembly

```asm
0x18000d354  mov     [rsp+arg_10], rbx
0x18000d359  mov     [rsp+arg_0], rcx
0x18000d35e  push    rdi
0x18000d35f  sub     rsp, 20h
0x18000d363  mov     rdi, rcx
0x18000d366  mov     qword ptr [rcx], 0
0x18000d36d  mov     qword ptr [rcx+8], 0
0x18000d375  mov     ecx, 38h ; '8'; Size
0x18000d37a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d37f  mov     [rax], rax
0x18000d382  mov     [rax+8], rax
0x18000d386  mov     [rax+10h], rax
0x18000d38a  mov     word ptr [rax+18h], 101h
0x18000d390  mov     [rdi], rax
0x18000d393  mov     qword ptr [rdi+10h], 0
0x18000d39b  mov     qword ptr [rdi+18h], 0
0x18000d3a3  mov     ecx, 38h ; '8'; Size
0x18000d3a8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d3ad  mov     [rax], rax
0x18000d3b0  mov     [rax+8], rax
0x18000d3b4  mov     [rax+10h], rax
0x18000d3b8  mov     word ptr [rax+18h], 101h
0x18000d3be  mov     [rdi+10h], rax
0x18000d3c2  mov     qword ptr [rdi+20h], 0
0x18000d3ca  mov     qword ptr [rdi+28h], 0
0x18000d3d2  mov     qword ptr [rdi+30h], 0
0x18000d3da  mov     rax, rdi
0x18000d3dd  mov     rbx, [rsp+28h+arg_10]
0x18000d3e2  add     rsp, 20h
0x18000d3e6  pop     rdi
0x18000d3e7  retn
```
