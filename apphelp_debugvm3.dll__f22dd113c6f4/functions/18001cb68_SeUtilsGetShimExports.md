# SeUtilsGetShimExports

- ea: `0x18001cb68`
- end: `0x18001cc89`
- name: `SeUtilsGetShimExports`
- size: `289`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001c73c`

## callees

- `0x18000f114`
- `0x18001cb68`

## import_xrefs

- `ntdll!LdrFindEntryForAddress` at `0x18001cba5`
- `ntdll!LdrFindEntryForAddress` at `0x18001cba5`
- `ntdll!LdrGetProcedureAddress` at `0x18001cc24`
- `ntdll!LdrGetProcedureAddress` at `0x18001cc4f`
- `ntdll!LdrGetProcedureAddress` at `0x18001cc24`
- `ntdll!LdrGetProcedureAddress` at `0x18001cc4f`
- `ntdll!RtlInitString` at `0x18001cc10`
- `ntdll!RtlInitString` at `0x18001cc3b`
- `ntdll!RtlInitString` at `0x18001cc10`
- `ntdll!RtlInitString` at `0x18001cc3b`

## pseudocode

```c
__int64 __fastcall SeUtilsGetShimExports(_QWORD *a1, __int64 (__fastcall **a2)(), void *a3)
{
  NTSTATUS EntryForAddress; // ebx
  PVOID v7; // rax
  __int64 (__fastcall *v8)(); // rcx
  __int64 result; // rax
  struct _STRING DestinationString; // [rsp+20h] [rbp-10h] BYREF
  PLDR_DATA_TABLE_ENTRY Module; // [rsp+60h] [rbp+30h] BYREF
  PVOID ProcedureAddress; // [rsp+68h] [rbp+38h] BYREF
  PVOID v13; // [rsp+78h] [rbp+48h] BYREF

  Module = 0;
  ProcedureAddress = 0;
  v13 = 0;
  DestinationString = 0;
  EntryForAddress = LdrFindEntryForAddress(a3, &Module);
  if ( EntryForAddress < 0 )
  {
    AslLogCallPrintf(
      1,
      "SeUtilsGetShimExports",
      426,
      "Failed to find loader entry",
      *(_QWORD *)&DestinationString.Length,
      DestinationString.Buffer);
    goto LABEL_7;
  }
  if ( Module != g_DataTableEntry )
  {
    RtlInitString(&DestinationString, "GetHookAPIs");
    EntryForAddress = LdrGetProcedureAddress(a3, &DestinationString, 0, &ProcedureAddress);
    if ( EntryForAddress < 0 )
    {
      AslLogCallPrintf(
        1,
        "SeUtilsGetShimExports",
        453,
        "Failed to get address of GetHookAPIs",
        *(_QWORD *)&DestinationString.Length,
        DestinationString.Buffer);
    }
    else
    {
      RtlInitString(&DestinationString, "NotifyShims");
      EntryForAddress = LdrGetProcedureAddress(a3, &DestinationString, 0, &v13);
      if ( EntryForAddress >= 0 )
      {
        v7 = ProcedureAddress;
        v8 = (__int64 (__fastcall *)())v13;
        goto LABEL_4;
      }
      AslLogCallPrintf(
        1,
        "SeUtilsGetShimExports",
        463,
        "Failed to get address of NotifyShims",
        *(_QWORD *)&DestinationString.Length,
        DestinationString.Buffer);
    }
LABEL_7:
    v7 = 0;
    v8 = 0;
    goto LABEL_5;
  }
  v7 = &InternalGetHookAPIs;
  v8 = InternalNotifyShims;
LABEL_4:
  EntryForAddress = 0;
LABEL_5:
  *a1 = v7;
  result = (unsigned int)EntryForAddress;
  *a2 = v8;
  return result;
}

```

## disassembly

```asm
0x18001cb68  push    rbp
0x18001cb6a  push    rbx
0x18001cb6b  push    rsi
0x18001cb6c  push    rdi
0x18001cb6d  push    r14
0x18001cb6f  mov     rbp, rsp
0x18001cb72  sub     rsp, 30h
0x18001cb76  mov     rsi, rdx
0x18001cb79  mov     [rbp+Module], 0
0x18001cb81  mov     r14, rcx
0x18001cb84  mov     [rbp+ProcedureAddress], 0
0x18001cb8c  xorps   xmm0, xmm0
0x18001cb8f  mov     [rbp+arg_18], 0
0x18001cb97  lea     rdx, [rbp+Module]; Module
0x18001cb9b  mov     rcx, r8; Address
0x18001cb9e  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18001cba2  mov     rdi, r8
0x18001cba5  call    cs:__imp_LdrFindEntryForAddress
0x18001cbab  mov     ebx, eax
0x18001cbad  test    eax, eax
0x18001cbaf  js      short loc_18001CBE1
0x18001cbb1  mov     rax, cs:g_DataTableEntry
0x18001cbb8  cmp     [rbp+Module], rax
0x18001cbbc  jnz     short loc_18001CC05
0x18001cbbe  lea     rax, InternalGetHookAPIs
0x18001cbc5  lea     rcx, InternalNotifyShims
0x18001cbcc  xor     ebx, ebx
0x18001cbce  mov     [r14], rax
0x18001cbd1  mov     eax, ebx
0x18001cbd3  mov     [rsi], rcx
0x18001cbd6  add     rsp, 30h
0x18001cbda  pop     r14
0x18001cbdc  pop     rdi
0x18001cbdd  pop     rsi
0x18001cbde  pop     rbx
0x18001cbdf  pop     rbp
0x18001cbe0  retn
0x18001cbe1  mov     r8d, 1AAh
0x18001cbe7  lea     r9, aFailedToFindLo; "Failed to find loader entry"
0x18001cbee  mov     ecx, 1
0x18001cbf3  lea     rdx, aSeutilsgetshim; "SeUtilsGetShimExports"
0x18001cbfa  call    AslLogCallPrintf
0x18001cbff  xor     eax, eax
0x18001cc01  xor     ecx, ecx
0x18001cc03  jmp     short loc_18001CBCE
0x18001cc05  lea     rdx, aGethookapis; "GetHookAPIs"
0x18001cc0c  lea     rcx, [rbp+DestinationString]; DestinationString
0x18001cc10  call    cs:__imp_RtlInitString
0x18001cc16  lea     r9, [rbp+ProcedureAddress]; ProcedureAddress
0x18001cc1a  xor     r8d, r8d; Ordinal
0x18001cc1d  lea     rdx, [rbp+DestinationString]; Name
0x18001cc21  mov     rcx, rdi; BaseAddress
0x18001cc24  call    cs:__imp_LdrGetProcedureAddress
0x18001cc2a  mov     ebx, eax
0x18001cc2c  test    eax, eax
0x18001cc2e  js      short loc_18001CC6A
0x18001cc30  lea     rdx, aNotifyshims; "NotifyShims"
0x18001cc37  lea     rcx, [rbp+DestinationString]; DestinationString
0x18001cc3b  call    cs:__imp_RtlInitString
0x18001cc41  lea     r9, [rbp+arg_18]; ProcedureAddress
0x18001cc45  xor     r8d, r8d; Ordinal
0x18001cc48  lea     rdx, [rbp+DestinationString]; Name
0x18001cc4c  mov     rcx, rdi; BaseAddress
0x18001cc4f  call    cs:__imp_LdrGetProcedureAddress
0x18001cc55  mov     ebx, eax
0x18001cc57  test    eax, eax
0x18001cc59  jns     short loc_18001CC7C
0x18001cc5b  mov     r8d, 1CFh
0x18001cc61  lea     r9, aFailedToGetAdd; "Failed to get address of NotifyShims"
0x18001cc68  jmp     short loc_18001CBEE
0x18001cc6a  mov     r8d, 1C5h
0x18001cc70  lea     r9, aFailedToGetAdd_0; "Failed to get address of GetHookAPIs"
0x18001cc77  jmp     loc_18001CBEE
0x18001cc7c  mov     rax, [rbp+ProcedureAddress]
0x18001cc80  mov     rcx, [rbp+arg_18]
0x18001cc84  jmp     loc_18001CBCC
```
