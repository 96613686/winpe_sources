# DiagHubCommon::ModulePath::GetModulePath(HINSTANCE__ *,std::vector<ushort,std::allocator<ushort>> &)

- ea: `0x1400108a8`
- end: `0x140010941`
- name: `?GetModulePath@ModulePath@DiagHubCommon@@SAJPEAUHINSTANCE__@@AEAV?$vector@GV?$allocator@G@std@@@std@@@Z`
- size: `153`
- prototype: `__int64 __fastcall(HMODULE hModule, __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000395c`
- `0x140005b70`
- `0x14000a42c`
- `0x14000eaec`
- `0x14000f510`
- `0x14000f9d4`
- `0x14000fcfc`

## callees

- `0x14000b73c`
- `0x1400108a8`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x1400108d5`
- `KERNEL32!GetModuleFileNameW` at `0x1400108d5`
- `KERNEL32!GetLastError` at `0x1400108df`
- `KERNEL32!GetLastError` at `0x140010919`
- `KERNEL32!GetLastError` at `0x1400108df`
- `KERNEL32!GetLastError` at `0x140010919`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall DiagHubCommon::ModulePath::GetModulePath(HMODULE hModule, __int64 a2)
{
  unsigned __int64 v4; // rdx
  __int64 result; // rax
  signed int LastError; // ecx

  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    std::vector<unsigned short>::resize(a2, 261);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      result = 2147942414LL;
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_140010930);
      return result;
    }
  }
  while ( GetModuleFileNameW(hModule, *(LPWSTR *)a2, (__int64)(*(_QWORD *)(a2 + 8) - *(_QWORD *)a2) >> 1) )
  {
    if ( GetLastError() != 122 )
      return 0;
    v4 = 2 * ((__int64)(*(_QWORD *)(a2 + 8) - *(_QWORD *)a2) >> 1);
    if ( v4 >= 0xFFFFFFFF )
      return 2147549183LL;
    _mm_lfence();
    std::vector<unsigned short>::resize(a2, v4);
  }
  LastError = GetLastError();
  result = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    return (unsigned int)LastError;
  return result;
}

```

## disassembly

```asm
0x1400108a8  mov     [rsp+arg_0], rbx
0x1400108ad  push    rdi
0x1400108ae  sub     rsp, 20h
0x1400108b2  mov     rbx, rdx
0x1400108b5  mov     rdi, rcx
0x1400108b8  mov     edx, 105h
0x1400108bd  mov     rcx, rbx
0x1400108c0  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1400108c5  mov     r8, [rbx+8]
0x1400108c9  sub     r8, [rbx]
0x1400108cc  sar     r8, 1; nSize
0x1400108cf  mov     rdx, [rbx]; lpFilename
0x1400108d2  mov     rcx, rdi; hModule
0x1400108d5  call    cs:__imp_GetModuleFileNameW
0x1400108db  test    eax, eax
0x1400108dd  jz      short loc_140010919
0x1400108df  call    cs:__imp_GetLastError
0x1400108e5  cmp     eax, 7Ah ; 'z'
0x1400108e8  jnz     short loc_140010915
0x1400108ea  mov     rdx, [rbx+8]
0x1400108ee  sub     rdx, [rbx]
0x1400108f1  sar     rdx, 1
0x1400108f4  add     rdx, rdx
0x1400108f7  mov     eax, 0FFFFFFFFh
0x1400108fc  cmp     rdx, rax
0x1400108ff  jb      short loc_140010908
0x140010901  mov     eax, 8000FFFFh
0x140010906  jmp     short loc_140010935
0x140010908  lfence
0x14001090b  mov     rcx, rbx
0x14001090e  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x140010913  jmp     short loc_1400108C5
0x140010915  xor     eax, eax
0x140010917  jmp     short loc_140010935
0x140010919  call    cs:__imp_GetLastError
0x14001091f  mov     ecx, eax
0x140010921  movzx   eax, ax
0x140010924  or      eax, 80070000h
0x140010929  test    ecx, ecx
0x14001092b  cmovle  eax, ecx
0x14001092e  jmp     short loc_140010935
0x140010930  mov     eax, 8007000Eh
0x140010935  mov     rbx, [rsp+28h+arg_0]
0x14001093a  add     rsp, 20h
0x14001093e  pop     rdi
0x14001093f  retn
```
