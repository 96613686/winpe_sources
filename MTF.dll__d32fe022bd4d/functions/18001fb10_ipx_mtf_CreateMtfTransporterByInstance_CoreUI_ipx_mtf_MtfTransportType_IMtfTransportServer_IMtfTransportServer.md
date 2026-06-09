# ipx::mtf::CreateMtfTransporterByInstance_CoreUI(ipx::mtf::MtfTransportType,IMtfTransportServer *,IMtfTransportServer * *)

- ea: `0x18001fb10`
- end: `0x18001fb86`
- name: `?CreateMtfTransporterByInstance_CoreUI@mtf@ipx@@YAJW4MtfTransportType@12@PEAUIMtfTransportServer@@PEAPEAU4@@Z`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180016b18`

## callees

- `0x180001fc4`
- `0x18001ed80`
- `0x18001fb10`
- `0x18002f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ipx::mtf::CreateMtfTransporterByInstance_CoreUI(int a1, __int64 a2, __int64 *a3)
{
  void *v6; // rax
  const char *v7; // r9
  __int64 v8; // rbx
  __int64 result; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *a3 = 0;
  try
  {
    v6 = operator new(0x118u);
    if ( v6 )
      v8 = ipx::mtf::MtfTransportServerCoreUI::MtfTransportServerCoreUI((__int64)v6, a1, a2);
    else
      v8 = 0;
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
    *a3 = v8;
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x31,
                           (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\transportcoreui.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x18001fb10  mov     [rsp+arg_0], rbx
0x18001fb15  mov     [rsp+arg_8], rsi
0x18001fb1a  push    rdi
0x18001fb1b  sub     rsp, 20h
0x18001fb1f  mov     rdi, r8
0x18001fb22  mov     rbx, rdx
0x18001fb25  mov     esi, ecx
0x18001fb27  mov     qword ptr [r8], 0
0x18001fb2e  mov     ecx, 118h; Size
0x18001fb33  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001fb38  mov     [rsp+28h+arg_10], rax
0x18001fb3d  test    rax, rax
0x18001fb40  jz      short loc_18001FB54
0x18001fb42  mov     r8, rbx
0x18001fb45  mov     edx, esi
0x18001fb47  mov     rcx, rax
0x18001fb4a  call    ??0MtfTransportServerCoreUI@mtf@ipx@@QEAA@W4MtfTransportType@12@PEAUIMtfTransportServer@@@Z; ipx::mtf::MtfTransportServerCoreUI::MtfTransportServerCoreUI(ipx::mtf::MtfTransportType,IMtfTransportServer *)
0x18001fb4f  mov     rbx, rax
0x18001fb52  jmp     short loc_18001FB56
0x18001fb54  xor     ebx, ebx
0x18001fb56  test    rbx, rbx
0x18001fb59  jz      short loc_18001FB6A
0x18001fb5b  mov     rax, [rbx]
0x18001fb5e  mov     rcx, rbx
0x18001fb61  mov     rax, [rax+8]
0x18001fb65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb6a  mov     [rdi], rbx
0x18001fb6d  xor     eax, eax
0x18001fb6f  jmp     short loc_18001FB75
0x18001fb71  mov     eax, dword ptr [rsp+28h+arg_10]
0x18001fb75  mov     rbx, [rsp+28h+arg_0]
0x18001fb7a  mov     rsi, [rsp+28h+arg_8]
0x18001fb7f  add     rsp, 20h
0x18001fb83  pop     rdi
0x18001fb84  retn
```
