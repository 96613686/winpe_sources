# CheckProtectedProcessForHardening(bool *,_PS_PROTECTION *)

- ea: `0x180057e0c`
- end: `0x180057ec1`
- name: `?CheckProtectedProcessForHardening@@YAJPEA_NPEAU_PS_PROTECTION@@@Z`
- size: `181`
- prototype: `__int64 __fastcall(bool *, struct _PS_PROTECTION *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180012b70`
- `0x180058f90`

## callees

- `0x1800161b8`
- `0x180057e0c`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x180057e5e`
- `ntdll!NtQueryInformationProcess` at `0x180057e5e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180057e3c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180057e3c`

## string_xrefs

- `0x180057e73`: `mincore\com\oleaut32\typelib\tlibapi.cpp`

## pseudocode

```c
__int64 __fastcall CheckProtectedProcessForHardening(bool *a1, struct _PS_PROTECTION *a2)
{
  HANDLE CurrentProcess; // rax
  NTSTATUS v5; // eax
  unsigned int v6; // ebx
  unsigned __int8 v8; // al
  int ReturnLength; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  unsigned __int8 ProcessInformation; // [rsp+40h] [rbp+8h] BYREF
  ULONG v12; // [rsp+50h] [rbp+18h] BYREF

  ProcessInformation = 0;
  v12 = 0;
  *a1 = 0;
  if ( (NtCurrentPeb()->BitField & 2) != 0 )
  {
    CurrentProcess = GetCurrentProcess();
    v5 = NtQueryInformationProcess(
           CurrentProcess,
           ProcessAffinityUpdateMode|ProcessUserModeIOPL,
           &ProcessInformation,
           1u,
           &v12);
    v6 = v5 | 0x10000000;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x394,
        (unsigned int)"mincore\\com\\oleaut32\\typelib\\tlibapi.cpp",
        (const char *)v6,
        ReturnLength);
      return v6;
    }
    if ( v12 != 1 )
      return 2147942487LL;
    v8 = ProcessInformation;
    if ( (unsigned __int8)((ProcessInformation >> 4) - 5) <= 1u )
    {
      *a1 = 1;
      *(_BYTE *)a2 = v8;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180057e0c  mov     [rsp+arg_8], rbx
0x180057e11  mov     [rsp+arg_18], rsi
0x180057e16  push    rdi
0x180057e17  sub     rsp, 30h
0x180057e1b  xor     eax, eax
0x180057e1d  mov     rsi, rdx
0x180057e20  mov     [rsp+38h+ProcessInformation], al
0x180057e24  mov     rdi, rcx
0x180057e27  mov     [rsp+38h+arg_10], eax
0x180057e2b  mov     [rcx], al
0x180057e2d  mov     rax, gs:60h
0x180057e36  test    byte ptr [rax+3], 2
0x180057e3a  jz      short loc_180057EAF
0x180057e3c  call    cs:__imp_GetCurrentProcess
0x180057e42  mov     r9d, 1; ProcessInformationLength
0x180057e48  lea     r8, [rsp+38h+ProcessInformation]; ProcessInformation
0x180057e4d  mov     rcx, rax; ProcessHandle
0x180057e50  lea     rax, [rsp+38h+arg_10]
0x180057e55  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x180057e5a  lea     edx, [r9+3Ch]; ProcessInformationClass
0x180057e5e  call    cs:__imp_NtQueryInformationProcess
0x180057e64  mov     ebx, eax
0x180057e66  or      ebx, 10000000h
0x180057e6c  jge     short loc_180057E8B
0x180057e6e  mov     rcx, [rsp+38h]; this
0x180057e73  lea     r8, aMincoreComOlea_3; "mincore\\com\\oleaut32\\typelib\\tlibap"...
0x180057e7a  mov     r9d, ebx; char *
0x180057e7d  mov     edx, 394h; void *
0x180057e82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057e87  mov     eax, ebx
0x180057e89  jmp     short loc_180057EB1
0x180057e8b  cmp     [rsp+38h+arg_10], 1
0x180057e90  jz      short loc_180057E99
0x180057e92  mov     eax, 80070057h
0x180057e97  jmp     short loc_180057EB1
0x180057e99  mov     al, [rsp+38h+ProcessInformation]
0x180057e9d  mov     cl, al
0x180057e9f  shr     cl, 4
0x180057ea2  sub     cl, 5
0x180057ea5  cmp     cl, 1
0x180057ea8  ja      short loc_180057EAF
0x180057eaa  mov     byte ptr [rdi], 1
0x180057ead  mov     [rsi], al
0x180057eaf  xor     eax, eax
0x180057eb1  mov     rbx, [rsp+38h+arg_8]
0x180057eb6  mov     rsi, [rsp+38h+arg_18]
0x180057ebb  add     rsp, 30h
0x180057ebf  pop     rdi
0x180057ec0  retn
```
