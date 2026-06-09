# SendWinStationBSM

- ea: `0x18000789c`
- end: `0x180007986`
- name: `SendWinStationBSM`
- size: `234`
- prototype: `NTSTATUS()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006ba0`

## callees

- `0x18000789c`
- `0x18000e010`

## import_xrefs

- `ntdll!LdrGetProcedureAddress` at `0x180007901`
- `ntdll!LdrGetProcedureAddress` at `0x180007901`
- `ntdll!LdrLoadDll` at `0x1800078d9`
- `ntdll!LdrLoadDll` at `0x1800078d9`
- `ntdll!LdrUnloadDll` at `0x180007961`
- `ntdll!LdrUnloadDll` at `0x180007961`

## pseudocode

```c
NTSTATUS SendWinStationBSM()
{
  NTSTATUS result; // eax
  NTSTATUS v1; // ebx
  PVOID BaseAddress; // [rsp+60h] [rbp-18h] BYREF
  PVOID ProcedureAddress; // [rsp+68h] [rbp-10h] BYREF

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
0x18000789c  mov     rax, rsp
0x18000789f  mov     [rax+8], rbx
0x1800078a3  mov     [rax+10h], rbp
0x1800078a7  mov     [rax+20h], rsi
0x1800078ab  mov     [rax+18h], r8d
0x1800078af  push    rdi
0x1800078b0  sub     rsp, 70h
0x1800078b4  and     qword ptr [rax-10h], 0
0x1800078b9  lea     r8, stru_18000F8C0; Name
0x1800078c0  and     qword ptr [rax-18h], 0
0x1800078c5  mov     rdi, r9
0x1800078c8  and     dword ptr [rax+18h], 0
0x1800078cc  lea     r9, [rax-18h]; BaseAddress
0x1800078d0  mov     rsi, rdx
0x1800078d3  mov     ebp, ecx
0x1800078d5  xor     edx, edx; LoadFlags
0x1800078d7  xor     ecx, ecx; SearchPath
0x1800078d9  call    cs:__imp_LdrLoadDll
0x1800078e0  nop     dword ptr [rax+rax+00h]
0x1800078e5  test    eax, eax
0x1800078e7  js      loc_18000796F
0x1800078ed  mov     rcx, [rsp+78h+BaseAddress]; BaseAddress
0x1800078f2  lea     r9, [rsp+78h+ProcedureAddress]; ProcedureAddress
0x1800078f7  xor     r8d, r8d; Ordinal
0x1800078fa  lea     rdx, stru_18000F8B0; Name
0x180007901  call    cs:__imp_LdrGetProcedureAddress
0x180007908  nop     dword ptr [rax+rax+00h]
0x18000790d  mov     ebx, eax
0x18000790f  test    eax, eax
0x180007911  js      short loc_18000795C
0x180007913  mov     rcx, [rsp+78h+arg_20]
0x18000791b  lea     rax, [rsp+78h+arg_10]
0x180007923  mov     [rsp+78h+var_30], rax
0x180007928  mov     r9d, 5
0x18000792e  mov     rax, [rsp+78h+ProcedureAddress]
0x180007933  xor     r8d, r8d
0x180007936  mov     [rsp+78h+var_38], rcx
0x18000793b  xor     ecx, ecx
0x18000793d  mov     [rsp+78h+var_40], rdi
0x180007942  mov     [rsp+78h+var_48], 219h
0x18000794a  lea     edx, [r9-4]
0x18000794e  mov     [rsp+78h+var_50], rsi
0x180007953  mov     [rsp+78h+var_58], ebp
0x180007957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000795c  mov     rcx, [rsp+78h+BaseAddress]; BaseAddress
0x180007961  call    cs:__imp_LdrUnloadDll
0x180007968  nop     dword ptr [rax+rax+00h]
0x18000796d  mov     eax, ebx
0x18000796f  lea     r11, [rsp+78h+var_8]
0x180007974  mov     rbx, [r11+10h]
0x180007978  mov     rbp, [r11+18h]
0x18000797c  mov     rsi, [r11+28h]
0x180007980  mov     rsp, r11
0x180007983  pop     rdi
0x180007984  retn
```
