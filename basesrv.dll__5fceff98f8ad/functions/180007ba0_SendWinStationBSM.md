# SendWinStationBSM

- ea: `0x180007ba0`
- end: `0x180007c7d`
- name: `SendWinStationBSM`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006e30`

## callees

- `0x180007ba0`
- `0x18000e010`

## import_xrefs

- `ntdll!LdrGetProcedureAddress` at `0x180007c05`
- `ntdll!LdrGetProcedureAddress` at `0x180007c05`
- `ntdll!LdrLoadDll` at `0x180007bdd`
- `ntdll!LdrLoadDll` at `0x180007bdd`
- `ntdll!LdrUnloadDll` at `0x180007c65`
- `ntdll!LdrUnloadDll` at `0x180007c65`

## pseudocode

```c
NTSTATUS SendWinStationBSM()
{
  NTSTATUS result; // eax
  NTSTATUS v1; // ebx
  PVOID BaseAddress; // [rsp+60h] [rbp-38h] BYREF
  PVOID ProcedureAddress; // [rsp+68h] [rbp-30h] BYREF

  ProcedureAddress = 0;
  BaseAddress = 0;
  result = LdrLoadDll(0, 0, (PUNICODE_STRING)&stru_18000F8C0, &BaseAddress);
  if ( result >= 0 )
  {
    v1 = LdrGetProcedureAddress(BaseAddress, (PANSI_STRING)&stru_18000F8B0, 0, &ProcedureAddress);
    if ( v1 >= 0 )
      ((void (__fastcall *)(_QWORD, __int64, _QWORD))ProcedureAddress)(0, 1, 0);
    LdrUnloadDll(BaseAddress);
    return v1;
  }
  return result;
}

```

## disassembly

```asm
0x180007ba0  mov     rax, rsp
0x180007ba3  mov     [rax+18h], r8d
0x180007ba7  push    rbx
0x180007ba8  push    rbp
0x180007ba9  push    rsi
0x180007baa  push    rdi
0x180007bab  sub     rsp, 78h
0x180007baf  mov     rdi, r9
0x180007bb2  mov     qword ptr [rax-30h], 0
0x180007bba  mov     rsi, rdx
0x180007bbd  mov     qword ptr [rax-38h], 0
0x180007bc5  mov     ebp, ecx
0x180007bc7  mov     dword ptr [rax+18h], 0
0x180007bce  lea     r9, [rax-38h]; BaseAddress
0x180007bd2  xor     edx, edx; LoadFlags
0x180007bd4  xor     ecx, ecx; SearchPath
0x180007bd6  lea     r8, stru_18000F8C0; Name
0x180007bdd  call    cs:__imp_LdrLoadDll
0x180007be4  nop     dword ptr [rax+rax+00h]
0x180007be9  test    eax, eax
0x180007beb  js      loc_180007C73
0x180007bf1  mov     rcx, [rsp+98h+BaseAddress]; BaseAddress
0x180007bf6  lea     r9, [rsp+98h+ProcedureAddress]; ProcedureAddress
0x180007bfb  xor     r8d, r8d; Ordinal
0x180007bfe  lea     rdx, stru_18000F8B0; Name
0x180007c05  call    cs:__imp_LdrGetProcedureAddress
0x180007c0c  nop     dword ptr [rax+rax+00h]
0x180007c11  mov     ebx, eax
0x180007c13  test    eax, eax
0x180007c15  js      short loc_180007C60
0x180007c17  mov     rcx, [rsp+98h+arg_20]
0x180007c1f  lea     rax, [rsp+98h+arg_10]
0x180007c27  mov     [rsp+98h+var_50], rax
0x180007c2c  mov     r9d, 5
0x180007c32  mov     rax, [rsp+98h+ProcedureAddress]
0x180007c37  xor     r8d, r8d
0x180007c3a  mov     [rsp+98h+var_58], rcx
0x180007c3f  xor     ecx, ecx
0x180007c41  mov     [rsp+98h+var_60], rdi
0x180007c46  mov     [rsp+98h+var_68], 219h
0x180007c4e  lea     edx, [r9-4]
0x180007c52  mov     [rsp+98h+var_70], rsi
0x180007c57  mov     [rsp+98h+var_78], ebp
0x180007c5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c60  mov     rcx, [rsp+98h+BaseAddress]; BaseAddress
0x180007c65  call    cs:__imp_LdrUnloadDll
0x180007c6c  nop     dword ptr [rax+rax+00h]
0x180007c71  mov     eax, ebx
0x180007c73  add     rsp, 78h
0x180007c77  pop     rdi
0x180007c78  pop     rsi
0x180007c79  pop     rbp
0x180007c7a  pop     rbx
0x180007c7b  retn
```
