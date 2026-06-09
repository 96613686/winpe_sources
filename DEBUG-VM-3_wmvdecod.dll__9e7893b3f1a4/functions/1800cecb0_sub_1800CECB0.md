# sub_1800CECB0

- ea: `0x1800cecb0`
- end: `0x1800ced60`
- name: `sub_1800CECB0`
- size: `176`
- prototype: `__int64 __fastcall(LPVOID lpAddress)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180058004`
- `0x1800cf1fc`

## callees

- `0x1800cecb0`
- `0x18020cab0`

## import_xrefs

- `ntdll!RtlDeleteFunctionTable` at `0x1800ced25`
- `ntdll!RtlDeleteFunctionTable` at `0x1800ced25`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800cece8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800cece8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ced54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cecbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cecbd`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800ced3c`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800ced3c`

## string_xrefs

- `0x1800cece1`: `RtlDeleteGrowableFunctionTable`

## pseudocode

```c
void __fastcall sub_1800CECB0(char *lpAddress)
{
  DWORD LastError; // edi
  HMODULE v3; // rcx
  FARPROC RtlDeleteGrowableFunctionTable; // rax

  LastError = GetLastError();
  if ( *((_QWORD *)lpAddress + 8062) )
  {
    v3 = (HMODULE)*((_QWORD *)lpAddress + 8063);
    if ( v3 )
    {
      RtlDeleteGrowableFunctionTable = GetProcAddress(v3, "RtlDeleteGrowableFunctionTable");
      if ( RtlDeleteGrowableFunctionTable )
        ((void (__fastcall *)(_QWORD))RtlDeleteGrowableFunctionTable)(*((_QWORD *)lpAddress + 8062));
      *((_QWORD *)lpAddress + 8063) = 0;
    }
    *((_QWORD *)lpAddress + 8062) = 0;
  }
  else
  {
    RtlDeleteFunctionTable((PRUNTIME_FUNCTION)(lpAddress + 64480));
  }
  VirtualFree(lpAddress, 0, 0x8000u);
  SetLastError(LastError);
}

```

## disassembly

```asm
0x1800cecb0  mov     [rsp+arg_0], rbx
0x1800cecb5  push    rdi
0x1800cecb6  sub     rsp, 20h
0x1800cecba  mov     rbx, rcx
0x1800cecbd  call    cs:GetLastError
0x1800cecc4  nop     dword ptr [rax+rax+00h]
0x1800cecc9  cmp     qword ptr [rbx+0FBF0h], 0
0x1800cecd1  mov     edi, eax
0x1800cecd3  jz      short loc_1800CED1E
0x1800cecd5  mov     rcx, [rbx+0FBF8h]; hModule
0x1800cecdc  test    rcx, rcx
0x1800cecdf  jz      short loc_1800CED11
0x1800cece1  lea     rdx, aRtldeletegrowa; "RtlDeleteGrowableFunctionTable"
0x1800cece8  call    cs:GetProcAddress
0x1800cecef  nop     dword ptr [rax+rax+00h]
0x1800cecf4  test    rax, rax
0x1800cecf7  jz      short loc_1800CED06
0x1800cecf9  mov     rcx, [rbx+0FBF0h]
0x1800ced00  call    cs:__guard_dispatch_icall_fptr
0x1800ced06  mov     qword ptr [rbx+0FBF8h], 0
0x1800ced11  mov     qword ptr [rbx+0FBF0h], 0
0x1800ced1c  jmp     short loc_1800CED31
0x1800ced1e  lea     rcx, [rbx+0FBE0h]; FunctionTable
0x1800ced25  call    cs:RtlDeleteFunctionTable
0x1800ced2c  nop     dword ptr [rax+rax+00h]
0x1800ced31  xor     edx, edx; dwSize
0x1800ced33  mov     r8d, 8000h; dwFreeType
0x1800ced39  mov     rcx, rbx; lpAddress
0x1800ced3c  call    cs:VirtualFree
0x1800ced43  nop     dword ptr [rax+rax+00h]
0x1800ced48  mov     ecx, edi
0x1800ced4a  mov     rbx, [rsp+28h+arg_0]
0x1800ced4f  add     rsp, 20h
0x1800ced53  pop     rdi
0x1800ced54  jmp     cs:SetLastError
```
