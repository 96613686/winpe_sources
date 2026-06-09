# SetPoolThreadBasePriority(_TP_POOL *,long)

- ea: `0x180007510`
- end: `0x18000757e`
- name: `?SetPoolThreadBasePriority@@YAJPEAU_TP_POOL@@J@Z`
- size: `110`
- prototype: `signed int __fastcall(struct _TP_POOL *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180007510`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007531`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007531`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007526`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007526`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000754f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000754f`

## string_xrefs

- `0x18000751f`: `ntdll.dll`
- `0x180007545`: `TpSetPoolThreadBasePriority`

## pseudocode

```c
signed int __fastcall SetPoolThreadBasePriority(struct _TP_POOL *a1, unsigned int a2)
{
  HMODULE ModuleHandleW; // rax
  signed int result; // eax
  FARPROC ProcAddress; // rax
  int v7; // edx

  ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
  if ( ModuleHandleW && (ProcAddress = GetProcAddress(ModuleHandleW, "TpSetPoolThreadBasePriority")) != 0 )
  {
    v7 = ((__int64 (__fastcall *)(struct _TP_POOL *, _QWORD))ProcAddress)(a1, a2);
    result = 0;
    if ( v7 < 0 )
      return v7 | 0x10000000;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180007510  mov     [rsp+arg_0], rbx
0x180007515  push    rdi
0x180007516  sub     rsp, 20h
0x18000751a  mov     rdi, rcx
0x18000751d  mov     ebx, edx
0x18000751f  lea     rcx, ModuleName; "ntdll.dll"
0x180007526  call    cs:__imp_GetModuleHandleW
0x18000752c  test    rax, rax
0x18000752f  jnz     short loc_180007545
0x180007531  call    cs:__imp_GetLastError
0x180007537  test    eax, eax
0x180007539  jle     short loc_180007573
0x18000753b  movzx   eax, ax
0x18000753e  or      eax, 80070000h
0x180007543  jmp     short loc_180007573
0x180007545  lea     rdx, ProcName; "TpSetPoolThreadBasePriority"
0x18000754c  mov     rcx, rax; hModule
0x18000754f  call    cs:__imp_GetProcAddress
0x180007555  test    rax, rax
0x180007558  jz      short loc_180007531
0x18000755a  mov     edx, ebx
0x18000755c  mov     rcx, rdi
0x18000755f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007564  mov     ecx, eax
0x180007566  mov     edx, eax
0x180007568  bts     ecx, 1Ch
0x18000756c  xor     eax, eax
0x18000756e  test    edx, edx
0x180007570  cmovs   eax, ecx
0x180007573  mov     rbx, [rsp+28h+arg_0]
0x180007578  add     rsp, 20h
0x18000757c  pop     rdi
0x18000757d  retn
```
