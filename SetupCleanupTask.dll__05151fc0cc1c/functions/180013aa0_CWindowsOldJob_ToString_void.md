# CWindowsOldJob::ToString(void)

- ea: `0x180013aa0`
- end: `0x180013ae5`
- name: `?ToString@CWindowsOldJob@@UEBAPEAVString@UnBCL@@XZ`
- size: `69`
- prototype: `struct UnBCL::String *__fastcall(CWindowsOldJob *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180013aa0`

## import_xrefs

- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180013aab`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180013aab`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180013ac8`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180013ac8`

## string_xrefs

- `0x180013abe`: `Windows.old`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct UnBCL::String *__fastcall CWindowsOldJob::ToString(CWindowsOldJob *this)
{
  UnBCL::String *v1; // rax
  UnBCL::String *v2; // rbx

  v1 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
  v2 = v1;
  if ( !v1 )
    return 0;
  UnBCL::String::String(v1, L"Windows.old");
  *(_QWORD *)v2 = &UnBCL::String::`local vftable';
  return v2;
}

```

## disassembly

```asm
0x180013aa0  push    rbx
0x180013aa2  sub     rsp, 20h
0x180013aa6  mov     ecx, 18h
0x180013aab  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180013ab1  mov     rbx, rax
0x180013ab4  mov     [rsp+28h+arg_8], rax
0x180013ab9  test    rax, rax
0x180013abc  jz      short loc_180013ADA
0x180013abe  lea     rdx, aWindowsOld_0; "Windows.old"
0x180013ac5  mov     rcx, rax
0x180013ac8  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180013ace  lea     rax, ??_SString@UnBCL@@6B@; const UnBCL::String::`local vftable'
0x180013ad5  mov     [rbx], rax
0x180013ad8  jmp     short loc_180013ADC
0x180013ada  xor     ebx, ebx
0x180013adc  mov     rax, rbx
0x180013adf  add     rsp, 20h
0x180013ae3  pop     rbx
0x180013ae4  retn
```
