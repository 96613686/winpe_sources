# std::thread::thread(void (&)(void))

- ea: `0x18003ca38`
- end: `0x18003cad0`
- name: `??$?0A6AXXZ$$V$0A@@thread@std@@QEAA@A6AXXZ@Z`
- size: `152`
- prototype: `std::thread *__fastcall(std::thread *this, void (*)(void))`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180023a08`

## callees

- `0x18002cdec`
- `0x18003ca38`
- `0x18003cb80`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003cac3`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003cac3`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18003ca82`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18003ca82`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
std::thread *__fastcall std::thread::thread(std::thread *this, void (*a2)(void))
{
  void (*v3)(void); // rax
  __int64 v4; // rax
  void (*v6)(void); // [rsp+48h] [rbp+10h] BYREF

  v6 = a2;
  v3 = (void (*)(void))operator new(8u);
  *(_QWORD *)v3 = NgcIsoWatchdogLoop;
  v6 = v3;
  v4 = _o__beginthreadex(0, 0, std::thread::_Invoke<std::tuple<void (*)(void)>,0>, v3, 0, (char *)this + 8);
  *(_QWORD *)this = v4;
  if ( !v4 )
  {
    *((_DWORD *)this + 2) = 0;
    std::_Throw_Cpp_error(6);
    __debugbreak();
    JUMPOUT(0x18003CAD0LL);
  }
  v6 = 0;
  std::unique_ptr<std::tuple<void (*)(void)>>::~unique_ptr<std::tuple<void (*)(void)>>(&v6);
  return this;
}

```

## disassembly

```asm
0x18003ca38  mov     [rsp+arg_0], rbx
0x18003ca3d  mov     [rsp+arg_8], rdx
0x18003ca42  push    rdi
0x18003ca43  sub     rsp, 30h
0x18003ca47  mov     rbx, rcx
0x18003ca4a  mov     ecx, 8; Size
0x18003ca4f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003ca54  lea     rcx, ?NgcIsoWatchdogLoop@@YAXXZ; NgcIsoWatchdogLoop(void)
0x18003ca5b  mov     [rax], rcx
0x18003ca5e  mov     [rsp+38h+arg_8], rax
0x18003ca63  lea     rdi, [rbx+8]
0x18003ca67  mov     [rsp+38h+var_10], rdi
0x18003ca6c  mov     [rsp+38h+var_18], 0
0x18003ca74  mov     r9, rax
0x18003ca77  lea     r8, ??$_Invoke@V?$tuple@P6AXXZ@std@@$0A@@thread@std@@CAIPEAX@Z; std::thread::_Invoke<std::tuple<void (*)(void)>,0>(void *)
0x18003ca7e  xor     edx, edx
0x18003ca80  xor     ecx, ecx
0x18003ca82  call    cs:__imp__o__beginthreadex
0x18003ca89  nop     dword ptr [rax+rax+00h]
0x18003ca8e  mov     [rbx], rax
0x18003ca91  test    rax, rax
0x18003ca94  jz      short loc_18003CAB8
0x18003ca96  mov     [rsp+38h+arg_8], 0
0x18003ca9f  lea     rcx, [rsp+38h+arg_8]
0x18003caa4  call    ??1?$unique_ptr@V?$tuple@P6AXXZ@std@@U?$default_delete@V?$tuple@P6AXXZ@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::tuple<void (*)(void)>>::~unique_ptr<std::tuple<void (*)(void)>>(void)
0x18003caa9  mov     rax, rbx
0x18003caac  mov     rbx, [rsp+38h+arg_0]
0x18003cab1  add     rsp, 30h
0x18003cab5  pop     rdi
0x18003cab6  retn
0x18003cab8  mov     dword ptr [rdi], 0
0x18003cabe  mov     ecx, 6
0x18003cac3  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18003caca  nop     dword ptr [rax+rax+00h]
0x18003cacf  int     3; Trap to Debugger
```
