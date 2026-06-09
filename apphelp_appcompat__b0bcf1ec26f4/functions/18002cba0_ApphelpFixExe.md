# ApphelpFixExe

- ea: `0x18002cba0`
- end: `0x18002ce3d`
- name: `ApphelpFixExe`
- size: `669`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180034170`
- `0x180039ef0`
- `0x18003a3d0`

## callees

- `0x18000f114`
- `0x18001e760`
- `0x18002cba0`
- `0x180039a72`

## import_xrefs

- `ntdll!RtlSetEnvironmentVariable` at `0x18002cdc1`
- `ntdll!RtlSetEnvironmentVariable` at `0x18002cdef`
- `ntdll!RtlSetEnvironmentVariable` at `0x18002cdc1`
- `ntdll!RtlSetEnvironmentVariable` at `0x18002cdef`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18002cc37`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18002cc37`
- `ntdll!RtlQueryEnvironmentVariable_U` at `0x18002cd35`
- `ntdll!RtlQueryEnvironmentVariable_U` at `0x18002cd9c`
- `ntdll!RtlQueryEnvironmentVariable_U` at `0x18002cd35`
- `ntdll!RtlQueryEnvironmentVariable_U` at `0x18002cd9c`
- `ntdll!RtlFreeHeap` at `0x18002ce32`
- `ntdll!RtlFreeHeap` at `0x18002ce32`
- `ntdll!RtlFreeAnsiString` at `0x18002cc98`
- `ntdll!RtlFreeAnsiString` at `0x18002cc98`
- `ntdll!RtlAllocateHeap` at `0x18002cd67`
- `ntdll!RtlAllocateHeap` at `0x18002cd67`
- `ntdll!RtlInitUnicodeStringEx` at `0x18002cc22`
- `ntdll!RtlInitUnicodeStringEx` at `0x18002ccfa`
- `ntdll!RtlInitUnicodeStringEx` at `0x18002cc22`
- `ntdll!RtlInitUnicodeStringEx` at `0x18002ccfa`

## string_xrefs

- `0x18002ccef`: `__COMPAT_LAYER`
- `0x18002cda6`: `Failed to get the value of __COMPAT_LAYER.`
- `0x18002cdcb`: `Failed to clear the __COMPAT_LAYER env var.`
- `0x18002cdfd`: `Failed to set the __COMPAT_LAYER env var.`

## pseudocode

```c
_BOOL8 __fastcall ApphelpFixExe(__int64 a1, const wchar_t *a2, _DWORD *a3, int a4, char a5)
{
  bool v5; // zf
  BOOL v10; // edi
  int v11; // r14d
  const char *Buffer; // r9
  wchar_t *v13; // rax
  const WCHAR *v14; // rax
  NTSTATUS inited; // eax
  const char *v16; // r9
  __int64 v17; // r8
  USHORT v19; // r14
  struct _UNICODE_STRING Value; // [rsp+30h] [rbp-48h] BYREF
  UNICODE_STRING Name; // [rsp+40h] [rbp-38h] BYREF
  struct _STRING AnsiString; // [rsp+50h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-18h] BYREF
  char v24; // [rsp+D0h] [rbp+58h] BYREF

  v5 = *a3 == 0;
  AnsiString = 0;
  DestinationString = 0;
  Name = 0;
  Value = 0;
  if ( v5 && !a3[32] )
  {
    v10 = 1;
    goto LABEL_15;
  }
  v10 = 0;
  v11 = 0;
  if ( (a5 & 1) != 0 )
  {
    if ( RtlInitUnicodeStringEx(&Name, L"__COMPAT_LAYER") < 0 )
    {
      AslLogCallPrintf(1, "ApphelpFixExe", 556, "Failed to initialize environment variable string.");
      goto LABEL_15;
    }
    if ( RtlQueryEnvironmentVariable_U(0, &Name, &Value) == -1073741789 )
    {
      v19 = Value.Length + 2;
      Value.Buffer = (PWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned __int16)(Value.Length + 2));
      if ( !Value.Buffer )
      {
        AslLogCallPrintf(1, "ApphelpFixExe", 575, "Memory allocation error.");
        goto LABEL_15;
      }
      Value.MaximumLength = v19;
      if ( RtlQueryEnvironmentVariable_U(0, &Name, &Value) < 0 )
      {
        AslLogCallPrintf(1, "ApphelpFixExe", 586, "Failed to get the value of __COMPAT_LAYER.");
        goto LABEL_15;
      }
      if ( RtlSetEnvironmentVariable(0, &Name, 0) < 0 )
      {
        AslLogCallPrintf(1, "ApphelpFixExe", 597, "Failed to clear the __COMPAT_LAYER env var.");
        goto LABEL_15;
      }
      v11 = 1;
    }
  }
  Buffer = 0;
  if ( a2 && a4 )
  {
    v13 = wcsrchr_0(a2, 0x5Cu);
    if ( v13 )
      v14 = v13 + 1;
    else
      v14 = a2;
    inited = RtlInitUnicodeStringEx(&DestinationString, v14);
    if ( inited < 0 )
    {
      v16 = "Failed to initialize module name, Status 0x%lx.";
      v17 = 625;
      goto LABEL_13;
    }
    inited = RtlUnicodeStringToAnsiString(&AnsiString, &DestinationString, 1u);
    if ( inited < 0 )
    {
      v16 = "RtlUnicodeStringToAnsiString failed [%x]";
      v17 = 633;
LABEL_13:
      AslLogCallPrintf(1, "ApphelpFixExe", v17, v16, inited);
      goto LABEL_14;
    }
    Buffer = AnsiString.Buffer;
  }
  v10 = SE_DynamicShim((__int64)a2, a1, (__int64)a3, Buffer);
  if ( v10 )
    v10 = 1;
  else
    AslLogCallPrintf(1, "ApphelpFixExe", 647, "Failed to call Dynamic Shim.", &v24);
LABEL_14:
  if ( v11 && RtlSetEnvironmentVariable(0, &Name, &Value) < 0 )
  {
    AslLogCallPrintf(1, "ApphelpFixExe", 662, "Failed to set the __COMPAT_LAYER env var.");
    v10 = 0;
  }
LABEL_15:
  if ( Value.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Value.Buffer);
  RtlFreeAnsiString(&AnsiString);
  return v10;
}

```

## disassembly

```asm
0x18002cba0  push    rbp
0x18002cba2  push    rbx
0x18002cba3  push    rsi
0x18002cba4  push    rdi
0x18002cba5  push    r12
0x18002cba7  push    r13
0x18002cba9  push    r14
0x18002cbab  push    r15
0x18002cbad  mov     rbp, rsp
0x18002cbb0  sub     rsp, 78h
0x18002cbb4  cmp     dword ptr [r8], 0
0x18002cbb8  xorps   xmm0, xmm0
0x18002cbbb  xorps   xmm1, xmm1
0x18002cbbe  mov     r12d, r9d
0x18002cbc1  movups  xmmword ptr [rbp+AnsiString.Length], xmm0
0x18002cbc5  mov     r15, r8
0x18002cbc8  mov     rsi, rdx
0x18002cbcb  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x18002cbcf  mov     r13, rcx
0x18002cbd2  movups  xmmword ptr [rbp+Name.Length], xmm0
0x18002cbd6  movups  xmmword ptr [rbp+Value.Length], xmm1
0x18002cbda  jz      short loc_18002CC50
0x18002cbdc  xor     edi, edi
0x18002cbde  xor     r14d, r14d
0x18002cbe1  lea     ebx, [rdi+1]
0x18002cbe4  test    [rbp+arg_20], bl
0x18002cbe7  jnz     loc_18002CCEF
0x18002cbed  xor     r9d, r9d
0x18002cbf0  test    rsi, rsi
0x18002cbf3  jz      loc_18002CCB5
0x18002cbf9  test    r12d, r12d
0x18002cbfc  jz      loc_18002CCB5
0x18002cc02  lea     edx, [r9+5Ch]; Ch
0x18002cc06  mov     rcx, rsi; Str
0x18002cc09  call    wcsrchr_0
0x18002cc0e  test    rax, rax
0x18002cc11  jz      loc_18002CD85
0x18002cc17  add     rax, 2
0x18002cc1b  mov     rdx, rax; SourceString
0x18002cc1e  lea     rcx, [rbp+DestinationString]; DestinationString
0x18002cc22  call    cs:__imp_RtlInitUnicodeStringEx
0x18002cc28  test    eax, eax
0x18002cc2a  js      short loc_18002CC61
0x18002cc2c  mov     r8b, bl; AllocateDestinationString
0x18002cc2f  lea     rdx, [rbp+DestinationString]; SourceString
0x18002cc33  lea     rcx, [rbp+AnsiString]; DestinationString
0x18002cc37  call    cs:__imp_RtlUnicodeStringToAnsiString
0x18002cc3d  test    eax, eax
0x18002cc3f  jns     short loc_18002CCB1
0x18002cc41  lea     r9, aRtlunicodestri_1; "RtlUnicodeStringToAnsiString failed [%x"...
0x18002cc48  mov     r8d, 279h
0x18002cc4e  jmp     short loc_18002CC6E
0x18002cc50  cmp     dword ptr [r8+80h], 0
0x18002cc58  jnz     short loc_18002CBDC
0x18002cc5a  mov     edi, 1
0x18002cc5f  jmp     short loc_18002CC89
0x18002cc61  lea     r9, aFailedToInitia_8; "Failed to initialize module name, Statu"...
0x18002cc68  mov     r8d, 271h
0x18002cc6e  lea     rdx, aApphelpfixexe; "ApphelpFixExe"
0x18002cc75  mov     dword ptr [rsp+78h+var_58], eax
0x18002cc79  mov     ecx, ebx
0x18002cc7b  call    AslLogCallPrintf
0x18002cc80  test    r14d, r14d
0x18002cc83  jnz     loc_18002CDE5
0x18002cc89  cmp     [rbp+Value.Buffer], 0
0x18002cc8e  jnz     loc_18002CE1F
0x18002cc94  lea     rcx, [rbp+AnsiString]; AnsiString
0x18002cc98  call    cs:__imp_RtlFreeAnsiString
0x18002cc9e  mov     eax, edi
0x18002cca0  add     rsp, 78h
0x18002cca4  pop     r15
0x18002cca6  pop     r14
0x18002cca8  pop     r13
0x18002ccaa  pop     r12
0x18002ccac  pop     rdi
0x18002ccad  pop     rsi
0x18002ccae  pop     rbx
0x18002ccaf  pop     rbp
0x18002ccb0  retn
0x18002ccb1  mov     r9, [rbp+AnsiString.Buffer]
0x18002ccb5  lea     rax, [rbp+arg_10]
0x18002ccb9  mov     r8, r15
0x18002ccbc  mov     rdx, r13
0x18002ccbf  mov     [rsp+78h+var_58], rax
0x18002ccc4  mov     rcx, rsi
0x18002ccc7  call    SE_DynamicShim
0x18002cccc  mov     edi, eax
0x18002ccce  test    eax, eax
0x18002ccd0  jnz     short loc_18002CD24
0x18002ccd2  lea     r9, aFailedToCallDy; "Failed to call Dynamic Shim."
0x18002ccd9  mov     r8d, 287h
0x18002ccdf  lea     rdx, aApphelpfixexe; "ApphelpFixExe"
0x18002cce6  mov     ecx, ebx
0x18002cce8  call    AslLogCallPrintf
0x18002cced  jmp     short loc_18002CC80
0x18002ccef  lea     rdx, aCompatLayer; "__COMPAT_LAYER"
0x18002ccf6  lea     rcx, [rbp+Name]; DestinationString
0x18002ccfa  call    cs:__imp_RtlInitUnicodeStringEx
0x18002cd00  test    eax, eax
0x18002cd02  jns     short loc_18002CD2B
0x18002cd04  lea     r9, aFailedToInitia_2; "Failed to initialize environment variab"...
0x18002cd0b  mov     r8d, 22Ch
0x18002cd11  lea     rdx, aApphelpfixexe; "ApphelpFixExe"
0x18002cd18  mov     ecx, ebx
0x18002cd1a  call    AslLogCallPrintf
0x18002cd1f  jmp     loc_18002CC89
0x18002cd24  mov     edi, ebx
0x18002cd26  jmp     loc_18002CC80
0x18002cd2b  lea     r8, [rbp+Value]; Value
0x18002cd2f  xor     ecx, ecx; Environment
0x18002cd31  lea     rdx, [rbp+Name]; Name
0x18002cd35  call    cs:__imp_RtlQueryEnvironmentVariable_U
0x18002cd3b  cmp     eax, 0C0000023h
0x18002cd40  jnz     loc_18002CBED
0x18002cd46  movzx   eax, [rbp+Value.Length]
0x18002cd4a  mov     edx, 8; Flags
0x18002cd4f  mov     rcx, gs:60h
0x18002cd58  add     ax, 2
0x18002cd5c  movzx   r14d, ax
0x18002cd60  mov     r8d, r14d; Size
0x18002cd63  mov     rcx, [rcx+30h]; HeapHandle
0x18002cd67  call    cs:__imp_RtlAllocateHeap
0x18002cd6d  mov     [rbp+Value.Buffer], rax
0x18002cd71  test    rax, rax
0x18002cd74  jnz     short loc_18002CD8D
0x18002cd76  lea     r9, aMemoryAllocati_1; "Memory allocation error."
0x18002cd7d  mov     r8d, 23Fh
0x18002cd83  jmp     short loc_18002CD11
0x18002cd85  mov     rax, rsi
0x18002cd88  jmp     loc_18002CC1B
0x18002cd8d  lea     r8, [rbp+Value]; Value
0x18002cd91  mov     [rbp+Value.MaximumLength], r14w
0x18002cd96  lea     rdx, [rbp+Name]; Name
0x18002cd9a  xor     ecx, ecx; Environment
0x18002cd9c  call    cs:__imp_RtlQueryEnvironmentVariable_U
0x18002cda2  test    eax, eax
0x18002cda4  jns     short loc_18002CDB8
0x18002cda6  lea     r9, aFailedToGetThe_6; "Failed to get the value of __COMPAT_LAY"...
0x18002cdad  mov     r8d, 24Ah
0x18002cdb3  jmp     loc_18002CD11
0x18002cdb8  xor     r8d, r8d; Value
0x18002cdbb  lea     rdx, [rbp+Name]; Name
0x18002cdbf  xor     ecx, ecx; Environment
0x18002cdc1  call    cs:__imp_RtlSetEnvironmentVariable
0x18002cdc7  test    eax, eax
0x18002cdc9  jns     short loc_18002CDDD
0x18002cdcb  lea     r9, aFailedToClearT; "Failed to clear the __COMPAT_LAYER env "...
0x18002cdd2  mov     r8d, 255h
0x18002cdd8  jmp     loc_18002CD11
0x18002cddd  mov     r14d, ebx
0x18002cde0  jmp     loc_18002CBED
0x18002cde5  lea     r8, [rbp+Value]; Value
0x18002cde9  xor     ecx, ecx; Environment
0x18002cdeb  lea     rdx, [rbp+Name]; Name
0x18002cdef  call    cs:__imp_RtlSetEnvironmentVariable
0x18002cdf5  test    eax, eax
0x18002cdf7  jns     loc_18002CC89
0x18002cdfd  lea     r9, aFailedToSetThe; "Failed to set the __COMPAT_LAYER env va"...
0x18002ce04  mov     r8d, 296h
0x18002ce0a  lea     rdx, aApphelpfixexe; "ApphelpFixExe"
0x18002ce11  mov     ecx, ebx
0x18002ce13  call    AslLogCallPrintf
0x18002ce18  xor     edi, edi
0x18002ce1a  jmp     loc_18002CC89
0x18002ce1f  mov     rcx, gs:60h
0x18002ce28  xor     edx, edx; Flags
0x18002ce2a  mov     r8, [rbp+Value.Buffer]; P
0x18002ce2e  mov     rcx, [rcx+30h]; HeapHandle
0x18002ce32  call    cs:__imp_RtlFreeHeap
0x18002ce38  jmp     loc_18002CC94
```
