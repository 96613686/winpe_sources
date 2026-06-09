# StartMSRAReverseProcess(void)

- ea: `0x14000ed54`
- end: `0x14000eee6`
- name: `?StartMSRAReverseProcess@@YAJXZ`
- size: `402`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000e810`

## callees

- `0x14000aab8`
- `0x14000ed54`
- `0x140015240`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x14000ed7b`
- `KERNEL32!HeapAlloc` at `0x14000edc7`
- `KERNEL32!HeapAlloc` at `0x14000ed7b`
- `KERNEL32!HeapAlloc` at `0x14000edc7`
- `KERNEL32!GetProcessHeap` at `0x14000ed63`
- `KERNEL32!GetProcessHeap` at `0x14000edb9`
- `KERNEL32!GetProcessHeap` at `0x14000eea7`
- `KERNEL32!GetProcessHeap` at `0x14000eec0`
- `KERNEL32!GetProcessHeap` at `0x14000ed63`
- `KERNEL32!GetProcessHeap` at `0x14000edb9`
- `KERNEL32!GetProcessHeap` at `0x14000eea7`
- `KERNEL32!GetProcessHeap` at `0x14000eec0`
- `KERNEL32!HeapFree` at `0x14000eeb5`
- `KERNEL32!HeapFree` at `0x14000eece`
- `KERNEL32!HeapFree` at `0x14000eeb5`
- `KERNEL32!HeapFree` at `0x14000eece`
- `SHELL32!ShellExecuteW` at `0x14000ee70`
- `SHELL32!ShellExecuteW` at `0x14000ee70`
- `SHELL32!SHGetSpecialFolderPathW` at `0x14000edfc`
- `SHELL32!SHGetSpecialFolderPathW` at `0x14000edfc`

## string_xrefs

- `0x14000eda3`: `base\diagnosis\ra\dcom\src\remoteassistance.cpp`
- `0x14000ee0a`: `base\diagnosis\ra\dcom\src\remoteassistance.cpp`
- `0x14000ee96`: `base\diagnosis\ra\dcom\src\remoteassistance.cpp`
- `0x14000ee2f`: `-CreateRAReverseConnectionString `

## pseudocode

```c
__int64 StartMSRAReverseProcess(void)
{
  HANDLE ProcessHeap; // rax
  const struct _EVENT_DESCRIPTOR *v1; // rdx
  CEventLogger *v2; // rcx
  unsigned __int16 *v3; // rsi
  unsigned int v4; // ebx
  HANDLE v5; // rax
  WCHAR *v6; // rax
  const struct _EVENT_DESCRIPTOR *v7; // rdx
  CEventLogger *v8; // rcx
  WCHAR *lpDirectory; // rdi
  const struct _EVENT_DESCRIPTOR *v10; // rdx
  CEventLogger *v11; // rcx
  signed int v12; // eax
  const struct _EVENT_DESCRIPTOR *v13; // rdx
  CEventLogger *v14; // rcx
  const struct _EVENT_DESCRIPTOR *v15; // rdx
  CEventLogger *v16; // rcx
  HANDLE v17; // rax
  HANDLE v18; // rax

  ProcessHeap = GetProcessHeap();
  v3 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 0x208u);
  if ( v3 )
  {
    v5 = GetProcessHeap();
    v6 = (WCHAR *)HeapAlloc(v5, 8u, 0x208u);
    lpDirectory = v6;
    if ( v6 )
    {
      if ( SHGetSpecialFolderPathW(0, v6, 37, 1) )
      {
        v12 = StringCchCopyW(v3, 0x104u, L"-CreateRAReverseConnectionString ");
        v4 = v12;
        if ( v12 >= 0 )
        {
          if ( (__int64)ShellExecuteW(0, 0, L"msra.exe", v3, lpDirectory, 1) <= 32 )
          {
            v4 = -2147467259;
            CEventLogger::LogError(
              v16,
              v15,
              L"base\\diagnosis\\ra\\dcom\\src\\remoteassistance.cpp",
              0xAEu,
              L"StartMSRAReverseProcess",
              0x80004005);
          }
        }
        else
        {
          CEventLogger::LogError(
            v14,
            v13,
            L"base\\diagnosis\\ra\\dcom\\src\\remoteassistance.cpp",
            0x99u,
            L"StartMSRAReverseProcess",
            v12);
        }
      }
      else
      {
        CEventLogger::LogError(
          v11,
          v10,
          L"base\\diagnosis\\ra\\dcom\\src\\remoteassistance.cpp",
          0x91u,
          L"StartMSRAReverseProcess",
          0);
        v4 = -2147467259;
      }
    }
    else
    {
      v4 = -2147024882;
      CEventLogger::LogError(
        v8,
        v7,
        L"base\\diagnosis\\ra\\dcom\\src\\remoteassistance.cpp",
        0x8Cu,
        L"StartMSRAReverseProcess",
        0x8007000E);
    }
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v3);
    if ( lpDirectory )
    {
      v18 = GetProcessHeap();
      HeapFree(v18, 0, lpDirectory);
    }
  }
  else
  {
    v4 = -2147024882;
    CEventLogger::LogError(
      v2,
      v1,
      L"base\\diagnosis\\ra\\dcom\\src\\remoteassistance.cpp",
      0x8Bu,
      L"StartMSRAReverseProcess",
      0x8007000E);
  }
  return v4;
}

```

## disassembly

```asm
0x14000ed54  mov     [rsp+arg_0], rbx
0x14000ed59  mov     [rsp+arg_8], rsi
0x14000ed5e  push    rdi
0x14000ed5f  sub     rsp, 30h
0x14000ed63  call    cs:__imp_GetProcessHeap
0x14000ed69  mov     ebx, 208h
0x14000ed6e  mov     edi, 8
0x14000ed73  mov     rcx, rax; hHeap
0x14000ed76  mov     r8d, ebx; dwBytes
0x14000ed79  mov     edx, edi; dwFlags
0x14000ed7b  call    cs:__imp_HeapAlloc
0x14000ed81  mov     rsi, rax
0x14000ed84  test    rax, rax
0x14000ed87  jnz     short loc_14000EDB9
0x14000ed89  lea     rax, aStartmsrarever; "StartMSRAReverseProcess"
0x14000ed90  mov     [rsp+38h+nShowCmd], 8007000Eh; unsigned int
0x14000ed98  mov     r9d, 8Bh; unsigned int
0x14000ed9e  mov     [rsp+38h+lpDirectory], rax; unsigned __int16 *
0x14000eda3  lea     r8, aBaseDiagnosisR_6; "base\\diagnosis\\ra\\dcom\\src\\remotea"...
0x14000edaa  mov     ebx, 8007000Eh
0x14000edaf  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000edb4  jmp     loc_14000EED4
0x14000edb9  call    cs:__imp_GetProcessHeap
0x14000edbf  mov     r8, rbx; dwBytes
0x14000edc2  mov     edx, edi; dwFlags
0x14000edc4  mov     rcx, rax; hHeap
0x14000edc7  call    cs:__imp_HeapAlloc
0x14000edcd  mov     rdi, rax
0x14000edd0  test    rax, rax
0x14000edd3  jnz     short loc_14000EDED
0x14000edd5  mov     ebx, 8007000Eh
0x14000edda  mov     [rsp+38h+nShowCmd], 8007000Eh
0x14000ede2  mov     r9d, 8Ch
0x14000ede8  jmp     loc_14000EE8F
0x14000eded  mov     r9d, 1; fCreate
0x14000edf3  mov     rdx, rdi; pszPath
0x14000edf6  xor     ecx, ecx; hwnd
0x14000edf8  lea     r8d, [r9+24h]; csidl
0x14000edfc  call    cs:__imp_SHGetSpecialFolderPathW
0x14000ee02  test    eax, eax
0x14000ee04  jnz     short loc_14000EE2F
0x14000ee06  mov     [rsp+38h+nShowCmd], eax; unsigned int
0x14000ee0a  lea     r8, aBaseDiagnosisR_6; "base\\diagnosis\\ra\\dcom\\src\\remotea"...
0x14000ee11  lea     rax, aStartmsrarever; "StartMSRAReverseProcess"
0x14000ee18  mov     r9d, 91h; unsigned int
0x14000ee1e  mov     [rsp+38h+lpDirectory], rax; unsigned __int16 *
0x14000ee23  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000ee28  mov     ebx, 80004005h
0x14000ee2d  jmp     short loc_14000EEA7
0x14000ee2f  lea     r8, aCreaterarevers; "-CreateRAReverseConnectionString "
0x14000ee36  mov     edx, 104h; unsigned __int64
0x14000ee3b  mov     rcx, rsi; unsigned __int16 *
0x14000ee3e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000ee43  mov     ebx, eax
0x14000ee45  test    eax, eax
0x14000ee47  jns     short loc_14000EE55
0x14000ee49  mov     [rsp+38h+nShowCmd], eax
0x14000ee4d  mov     r9d, 99h
0x14000ee53  jmp     short loc_14000EE8F
0x14000ee55  mov     [rsp+38h+nShowCmd], 1; nShowCmd
0x14000ee5d  lea     r8, aMsraExe_1; "msra.exe"
0x14000ee64  mov     r9, rsi; lpParameters
0x14000ee67  mov     [rsp+38h+lpDirectory], rdi; lpDirectory
0x14000ee6c  xor     edx, edx; lpOperation
0x14000ee6e  xor     ecx, ecx; hwnd
0x14000ee70  call    cs:__imp_ShellExecuteW
0x14000ee76  cmp     rax, 20h ; ' '
0x14000ee7a  jg      short loc_14000EEA7
0x14000ee7c  mov     ebx, 80004005h
0x14000ee81  mov     [rsp+38h+nShowCmd], 80004005h; unsigned int
0x14000ee89  mov     r9d, 0AEh; unsigned int
0x14000ee8f  lea     rax, aStartmsrarever; "StartMSRAReverseProcess"
0x14000ee96  lea     r8, aBaseDiagnosisR_6; "base\\diagnosis\\ra\\dcom\\src\\remotea"...
0x14000ee9d  mov     [rsp+38h+lpDirectory], rax; unsigned __int16 *
0x14000eea2  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000eea7  call    cs:__imp_GetProcessHeap
0x14000eead  mov     r8, rsi; lpMem
0x14000eeb0  xor     edx, edx; dwFlags
0x14000eeb2  mov     rcx, rax; hHeap
0x14000eeb5  call    cs:__imp_HeapFree
0x14000eebb  test    rdi, rdi
0x14000eebe  jz      short loc_14000EED4
0x14000eec0  call    cs:__imp_GetProcessHeap
0x14000eec6  mov     r8, rdi; lpMem
0x14000eec9  xor     edx, edx; dwFlags
0x14000eecb  mov     rcx, rax; hHeap
0x14000eece  call    cs:__imp_HeapFree
0x14000eed4  mov     rsi, [rsp+38h+arg_8]
0x14000eed9  mov     eax, ebx
0x14000eedb  mov     rbx, [rsp+38h+arg_0]
0x14000eee0  add     rsp, 30h
0x14000eee4  pop     rdi
0x14000eee5  retn
```
