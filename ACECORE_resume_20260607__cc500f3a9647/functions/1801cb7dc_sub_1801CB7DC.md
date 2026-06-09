# sub_1801CB7DC

- ea: `0x1801cb7dc`
- end: `0x1801cb8fe`
- name: `sub_1801CB7DC`
- size: `290`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000d874`

## callees

- `0x1801cb7dc`
- `0x1801ce394`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1801cb81a`
- `KERNEL32!GetProcAddress` at `0x1801cb835`
- `KERNEL32!GetProcAddress` at `0x1801cb81a`
- `KERNEL32!GetProcAddress` at `0x1801cb835`
- `KERNEL32!InitializeCriticalSection` at `0x1801cb881`
- `KERNEL32!InitializeCriticalSection` at `0x1801cb881`
- `KERNEL32!WaitForSingleObject` at `0x1801cb8cc`
- `KERNEL32!WaitForSingleObject` at `0x1801cb8cc`
- `KERNEL32!CreateEventA` at `0x1801cb856`
- `KERNEL32!CreateEventA` at `0x1801cb86d`
- `KERNEL32!CreateEventA` at `0x1801cb856`
- `KERNEL32!CreateEventA` at `0x1801cb86d`
- `api-ms-win-crt-runtime-l1-1-0!_beginthreadex` at `0x1801cb8b5`
- `api-ms-win-crt-runtime-l1-1-0!_beginthreadex` at `0x1801cb8b5`

## string_xrefs

- `0x1801cb7f4`: `ole32.dll`

## pseudocode

```c
__int64 sub_1801CB7DC()
{
  unsigned int v0; // ebx
  HMODULE v1; // rax
  HRESULT (__stdcall *CoInitializeEx)(LPVOID, DWORD); // rax
  unsigned int ThrdAddr; // [rsp+40h] [rbp+8h] BYREF

  v0 = 0;
  ThrdAddr = 0;
  if ( !dword_18025EC48 )
  {
    v1 = (HMODULE)sub_1801CE394(L"ole32.dll");
    hLibModule = v1;
    if ( v1
      && (CoUninitialize = (void (__stdcall *)())GetProcAddress(v1, "CoUninitialize"),
          CoInitializeEx = (HRESULT (__stdcall *)(LPVOID, DWORD))GetProcAddress(hLibModule, "CoInitializeEx"),
          dword_18025E8F0 = 1000,
          qword_18025EC60 = (__int64)CoInitializeEx,
          hHandle = CreateEventA(0, 0, 0, 0),
          qword_18025EC58 = CreateEventA(0, 0, 0, 0),
          InitializeCriticalSection(&CriticalSection),
          hHandle)
      && qword_18025EC58 )
    {
      qword_18025EC40 = (HANDLE)beginthreadex(0, 0, (_beginthreadex_proc_type)sub_1801CB3A0, 0, 0, &ThrdAddr);
      WaitForSingleObject(hHandle, 0xFFFFFFFF);
      v0 = qword_18025EC40 == 0 ? 0x80004005 : 0;
    }
    else
    {
      v0 = -2147467259;
    }
  }
  return v0 != 0 ? 0xFFFFEC77 : 0;
}

```

## disassembly

```asm
0x1801cb7dc  push    rbx
0x1801cb7de  sub     rsp, 30h
0x1801cb7e2  xor     ebx, ebx
0x1801cb7e4  cmp     cs:dword_18025EC48, ebx
0x1801cb7ea  mov     [rsp+38h+arg_0], ebx
0x1801cb7ee  jnz     loc_1801CB8EF
0x1801cb7f4  lea     rcx, aOle32Dll_0; "ole32.dll"
0x1801cb7fb  call    sub_1801CE394
0x1801cb800  mov     cs:hLibModule, rax
0x1801cb807  test    rax, rax
0x1801cb80a  jz      loc_1801CB8EA
0x1801cb810  lea     rdx, aCouninitialize; "CoUninitialize"
0x1801cb817  mov     rcx, rax; hModule
0x1801cb81a  call    cs:GetProcAddress
0x1801cb820  mov     rcx, cs:hLibModule; hModule
0x1801cb827  lea     rdx, aCoinitializeex; "CoInitializeEx"
0x1801cb82e  mov     cs:CoUninitialize, rax
0x1801cb835  call    cs:GetProcAddress
0x1801cb83b  xor     r9d, r9d; lpName
0x1801cb83e  mov     cs:dword_18025E8F0, 3E8h
0x1801cb848  xor     r8d, r8d; bInitialState
0x1801cb84b  mov     cs:qword_18025EC60, rax
0x1801cb852  xor     edx, edx; bManualReset
0x1801cb854  xor     ecx, ecx; lpEventAttributes
0x1801cb856  call    cs:CreateEventA
0x1801cb85c  xor     r9d, r9d; lpName
0x1801cb85f  xor     r8d, r8d; bInitialState
0x1801cb862  xor     edx, edx; bManualReset
0x1801cb864  mov     cs:hHandle, rax
0x1801cb86b  xor     ecx, ecx; lpEventAttributes
0x1801cb86d  call    cs:CreateEventA
0x1801cb873  lea     rcx, CriticalSection; lpCriticalSection
0x1801cb87a  mov     cs:qword_18025EC58, rax
0x1801cb881  call    cs:InitializeCriticalSection
0x1801cb887  cmp     cs:hHandle, rbx
0x1801cb88e  jz      short loc_1801CB8EA
0x1801cb890  cmp     cs:qword_18025EC58, rbx
0x1801cb897  jz      short loc_1801CB8EA
0x1801cb899  lea     rax, [rsp+38h+arg_0]
0x1801cb89e  xor     r9d, r9d; ArgList
0x1801cb8a1  mov     [rsp+38h+ThrdAddr], rax; ThrdAddr
0x1801cb8a6  lea     r8, sub_1801CB3A0; StartAddress
0x1801cb8ad  xor     edx, edx; StackSize
0x1801cb8af  mov     [rsp+38h+InitFlag], ebx; InitFlag
0x1801cb8b3  xor     ecx, ecx; Security
0x1801cb8b5  call    cs:_beginthreadex
0x1801cb8bb  mov     rcx, cs:hHandle; hHandle
0x1801cb8c2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1801cb8c5  mov     cs:qword_18025EC40, rax
0x1801cb8cc  call    cs:WaitForSingleObject
0x1801cb8d2  mov     rax, cs:qword_18025EC40
0x1801cb8d9  neg     rax
0x1801cb8dc  sbb     ecx, ecx
0x1801cb8de  not     ecx
0x1801cb8e0  and     ecx, 80004005h
0x1801cb8e6  mov     ebx, ecx
0x1801cb8e8  jmp     short loc_1801CB8EF
0x1801cb8ea  mov     ebx, 80004005h
0x1801cb8ef  neg     ebx
0x1801cb8f1  sbb     eax, eax
0x1801cb8f3  and     eax, 0FFFFEC77h
0x1801cb8f8  add     rsp, 30h
0x1801cb8fc  pop     rbx
0x1801cb8fd  retn
```
