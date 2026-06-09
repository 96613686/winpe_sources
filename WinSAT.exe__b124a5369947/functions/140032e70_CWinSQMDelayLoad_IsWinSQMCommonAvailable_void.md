# CWinSQMDelayLoad::IsWinSQMCommonAvailable(void)

- ea: `0x140032e70`
- end: `0x140032ec2`
- name: `?IsWinSQMCommonAvailable@CWinSQMDelayLoad@@QEAA_NXZ`
- size: `82`
- prototype: `bool __fastcall(CWinSQMDelayLoad *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140034840`
- `0x140035340`

## callees

- `0x140032e70`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140032ea1`
- `KERNEL32!GetProcAddress` at `0x140032ea1`
- `KERNEL32!LoadLibraryW` at `0x140032e88`
- `KERNEL32!LoadLibraryW` at `0x140032e88`

## string_xrefs

- `0x140032e81`: `ntdll.dll`
- `0x140032e97`: `WinSqmCommonDatapointSetDWORD`

## pseudocode

```c
bool __fastcall CWinSQMDelayLoad::IsWinSQMCommonAvailable(CWinSQMDelayLoad *this)
{
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax

  if ( !*(_BYTE *)this )
  {
    *(_BYTE *)this = 1;
    LibraryW = LoadLibraryW(L"ntdll.dll");
    *((_QWORD *)this + 1) = LibraryW;
    if ( LibraryW )
    {
      ProcAddress = GetProcAddress(LibraryW, "WinSqmCommonDatapointSetDWORD");
      *((_QWORD *)this + 2) = ProcAddress;
      if ( !ProcAddress )
        *((_QWORD *)this + 1) = 0;
    }
  }
  return *((_QWORD *)this + 2) != 0;
}

```

## disassembly

```asm
0x140032e70  push    rbx
0x140032e72  sub     rsp, 20h
0x140032e76  cmp     byte ptr [rcx], 0
0x140032e79  mov     rbx, rcx
0x140032e7c  jnz     short loc_140032EB4
0x140032e7e  mov     byte ptr [rcx], 1
0x140032e81  lea     rcx, ModuleName; "ntdll.dll"
0x140032e88  call    cs:__imp_LoadLibraryW
0x140032e8e  mov     [rbx+8], rax
0x140032e92  test    rax, rax
0x140032e95  jz      short loc_140032EB4
0x140032e97  lea     rdx, aWinsqmcommonda; "WinSqmCommonDatapointSetDWORD"
0x140032e9e  mov     rcx, rax; hModule
0x140032ea1  call    cs:__imp_GetProcAddress
0x140032ea7  mov     [rbx+10h], rax
0x140032eab  test    rax, rax
0x140032eae  jnz     short loc_140032EB4
0x140032eb0  mov     [rbx+8], rax
0x140032eb4  cmp     qword ptr [rbx+10h], 0
0x140032eb9  setnz   al
0x140032ebc  add     rsp, 20h
0x140032ec0  pop     rbx
0x140032ec1  retn
```
