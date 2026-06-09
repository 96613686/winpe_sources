# FsTxpLoadFunction

- ea: `0x18012e1cc`
- end: `0x18012e2d8`
- name: `FsTxpLoadFunction`
- size: `268`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180125bb0`
- `0x180127d70`
- `0x180129290`
- `0x18012b030`
- `0x18012b900`
- `0x18012e2e0`
- `0x18012e334`
- `0x18012e424`

## callees

- `0x18012e1cc`

## import_xrefs

- `ntdll!LdrGetDllHandle` at `0x18012e22f`
- `ntdll!LdrGetDllHandle` at `0x18012e22f`
- `ntdll!RtlInitString` at `0x18012e286`
- `ntdll!RtlInitString` at `0x18012e286`
- `ntdll!RtlNtStatusToDosError` at `0x18012e241`
- `ntdll!RtlNtStatusToDosError` at `0x18012e241`
- `ntdll!RtlSetLastWin32Error` at `0x18012e24f`
- `ntdll!RtlSetLastWin32Error` at `0x18012e24f`
- `ntdll!RtlInitUnicodeString` at `0x18012e217`
- `ntdll!RtlInitUnicodeString` at `0x18012e217`
- `ntdll!LdrGetProcedureAddress` at `0x18012e2a4`
- `ntdll!LdrGetProcedureAddress` at `0x18012e2a4`

## string_xrefs

- `0x18012e208`: `FsTx.dll`

## pseudocode

```c
bool __fastcall FsTxpLoadFunction(__int64 *a1, const char *a2)
{
  __int64 v2; // rax
  int v5; // eax
  ULONG v6; // eax
  bool v7; // sf
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-10h] BYREF
  PVOID ProcedureAddress; // [rsp+40h] [rbp+10h] BYREF
  PVOID DllHandle; // [rsp+50h] [rbp+20h] BYREF

  v2 = *a1;
  if ( !*a1 )
  {
    ProcedureAddress = (PVOID)1;
    if ( !FsTxModule )
    {
      DllHandle = 0;
      DestinationString = 0;
      RtlInitUnicodeString(&DestinationString, L"FsTx.dll");
      v5 = LdrGetDllHandle(0, 0, &DestinationString, &DllHandle);
      if ( v5 < 0 )
      {
        v6 = RtlNtStatusToDosError(v5);
        RtlSetLastWin32Error(v6);
        FsTxModule = 0;
        goto LABEL_7;
      }
      FsTxModule = DllHandle;
      if ( !DllHandle )
        goto LABEL_7;
    }
    DestinationString = 0;
    RtlInitString((PSTRING)&DestinationString, a2);
    v7 = LdrGetProcedureAddress(FsTxModule, (PANSI_STRING)&DestinationString, 0, &ProcedureAddress) < 0;
    v2 = 1;
    if ( v7 )
    {
LABEL_8:
      *a1 = v2;
      return v2 != 1;
    }
LABEL_7:
    v2 = (__int64)ProcedureAddress;
    goto LABEL_8;
  }
  return v2 != 1;
}

```

## disassembly

```asm
0x18012e1cc  mov     [rsp-8+arg_8], rbx
0x18012e1d1  mov     [rsp-8+arg_18], rdi
0x18012e1d6  push    rbp
0x18012e1d7  mov     rbp, rsp
0x18012e1da  sub     rsp, 30h
0x18012e1de  mov     rax, [rcx]
0x18012e1e1  mov     rdi, rdx
0x18012e1e4  mov     rbx, rcx
0x18012e1e7  test    rax, rax
0x18012e1ea  jnz     loc_18012E2C0
0x18012e1f0  cmp     cs:?FsTxModule@@3PEAXEA, rax; void * FsTxModule
0x18012e1f7  mov     [rbp+ProcedureAddress], 1
0x18012e1ff  jnz     short loc_18012E278
0x18012e201  xorps   xmm0, xmm0
0x18012e204  mov     [rbp+DllHandle], rax
0x18012e208  lea     rdx, SourceString; "FsTx.dll"
0x18012e20f  lea     rcx, [rbp+DestinationString]; DestinationString
0x18012e213  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18012e217  call    cs:__imp_RtlInitUnicodeString
0x18012e21e  nop     dword ptr [rax+rax+00h]
0x18012e223  lea     r9, [rbp+DllHandle]; DllHandle
0x18012e227  xor     edx, edx; DllCharacteristics
0x18012e229  lea     r8, [rbp+DestinationString]; DllName
0x18012e22d  xor     ecx, ecx; DllPath
0x18012e22f  call    cs:__imp_LdrGetDllHandle
0x18012e236  nop     dword ptr [rax+rax+00h]
0x18012e23b  test    eax, eax
0x18012e23d  jns     short loc_18012E268
0x18012e23f  mov     ecx, eax; Status
0x18012e241  call    cs:__imp_RtlNtStatusToDosError
0x18012e248  nop     dword ptr [rax+rax+00h]
0x18012e24d  mov     ecx, eax; LastError
0x18012e24f  call    cs:__imp_RtlSetLastWin32Error
0x18012e256  nop     dword ptr [rax+rax+00h]
0x18012e25b  mov     cs:?FsTxModule@@3PEAXEA, 0; void * FsTxModule
0x18012e266  jmp     short loc_18012E2B9
0x18012e268  mov     rax, [rbp+DllHandle]
0x18012e26c  mov     cs:?FsTxModule@@3PEAXEA, rax; void * FsTxModule
0x18012e273  test    rax, rax
0x18012e276  jz      short loc_18012E2B9
0x18012e278  xorps   xmm0, xmm0
0x18012e27b  lea     rcx, [rbp+DestinationString]; DestinationString
0x18012e27f  mov     rdx, rdi; SourceString
0x18012e282  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18012e286  call    cs:__imp_RtlInitString
0x18012e28d  nop     dword ptr [rax+rax+00h]
0x18012e292  mov     rcx, cs:?FsTxModule@@3PEAXEA; BaseAddress
0x18012e299  lea     r9, [rbp+ProcedureAddress]; ProcedureAddress
0x18012e29d  xor     r8d, r8d; Ordinal
0x18012e2a0  lea     rdx, [rbp+DestinationString]; Name
0x18012e2a4  call    cs:__imp_LdrGetProcedureAddress
0x18012e2ab  nop     dword ptr [rax+rax+00h]
0x18012e2b0  test    eax, eax
0x18012e2b2  mov     eax, 1
0x18012e2b7  js      short loc_18012E2BD
0x18012e2b9  mov     rax, [rbp+ProcedureAddress]
0x18012e2bd  mov     [rbx], rax
0x18012e2c0  mov     rbx, [rsp+30h+arg_8]
0x18012e2c5  cmp     rax, 1
0x18012e2c9  mov     rdi, [rsp+30h+arg_18]
0x18012e2ce  setnz   al
0x18012e2d1  add     rsp, 30h
0x18012e2d5  pop     rbp
0x18012e2d6  retn
```
