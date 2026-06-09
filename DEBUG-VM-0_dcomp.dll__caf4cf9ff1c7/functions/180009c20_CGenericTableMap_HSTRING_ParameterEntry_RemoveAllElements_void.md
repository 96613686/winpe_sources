# CGenericTableMap<HSTRING__ *,ParameterEntry>::RemoveAllElements(void)

- ea: `0x180009c20`
- end: `0x180009cbe`
- name: `?RemoveAllElements@?$CGenericTableMap@PEAUHSTRING__@@VParameterEntry@@@@QEAAXXZ`
- size: `158`
- prototype: `__int64 __fastcall(PRTL_GENERIC_TABLE Table)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180009cc4`

## callees

- `0x180009c20`
- `0x18000f334`
- `0x1800f6f10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x180009cb6`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x180009cb6`
- `ntdll!RtlDeleteElementGenericTable` at `0x180009c6b`
- `ntdll!RtlDeleteElementGenericTable` at `0x180009c6b`
- `ntdll!RtlEnumerateGenericTableWithoutSplaying` at `0x180009c90`
- `ntdll!RtlEnumerateGenericTableWithoutSplaying` at `0x180009c90`

## pseudocode

```c
ParameterEntry *__fastcall CGenericTableMap<HSTRING__ *,ParameterEntry>::RemoveAllElements(PRTL_GENERIC_TABLE Table)
{
  struct _RTL_GENERIC_TABLE *i; // rbx
  ParameterEntry *result; // rax
  PVOID RestartKey; // [rsp+20h] [rbp-58h] BYREF
  __int64 Buffer; // [rsp+28h] [rbp-50h] BYREF
  int v5; // [rsp+30h] [rbp-48h]
  __int128 v6; // [rsp+38h] [rbp-40h]
  int v7; // [rsp+48h] [rbp-30h]

  for ( i = Table; ; Table = i )
  {
    RestartKey = 0;
    result = (ParameterEntry *)RtlEnumerateGenericTableWithoutSplaying(Table, &RestartKey);
    if ( !result )
      break;
    Buffer = *(_QWORD *)result;
    v5 = 0;
    v6 = 0;
    v7 = 0;
    ParameterEntry::~ParameterEntry(result);
    if ( !RtlDeleteElementGenericTable(i, &Buffer) )
      RaiseFailFastException(0, 0, 1u);
    ParameterEntry::~ParameterEntry((ParameterEntry *)&Buffer);
  }
  return result;
}

```

## disassembly

```asm
0x180009c20  push    rbx
0x180009c22  sub     rsp, 70h
0x180009c26  mov     rax, cs:__security_cookie
0x180009c2d  xor     rax, rsp
0x180009c30  mov     [rsp+78h+var_18], rax
0x180009c35  mov     rbx, rcx
0x180009c38  jmp     short loc_180009C82
0x180009c3a  mov     rcx, [rax]
0x180009c3d  xorps   xmm0, xmm0
0x180009c40  mov     [rsp+78h+Buffer], rcx
0x180009c45  mov     rcx, rax; this
0x180009c48  mov     [rsp+78h+var_48], 0
0x180009c50  movdqu  [rsp+78h+var_40], xmm0
0x180009c56  mov     [rsp+78h+var_30], 0
0x180009c5e  call    ??1ParameterEntry@@QEAA@XZ; ParameterEntry::~ParameterEntry(void)
0x180009c63  lea     rdx, [rsp+78h+Buffer]; Buffer
0x180009c68  mov     rcx, rbx; Table
0x180009c6b  call    cs:__imp_RtlDeleteElementGenericTable
0x180009c71  test    al, al
0x180009c73  jz      short loc_180009CAE
0x180009c75  lea     rcx, [rsp+78h+Buffer]; this
0x180009c7a  call    ??1ParameterEntry@@QEAA@XZ; ParameterEntry::~ParameterEntry(void)
0x180009c7f  mov     rcx, rbx; Table
0x180009c82  lea     rdx, [rsp+78h+RestartKey]; RestartKey
0x180009c87  mov     [rsp+78h+RestartKey], 0
0x180009c90  call    cs:__imp_RtlEnumerateGenericTableWithoutSplaying
0x180009c96  test    rax, rax
0x180009c99  jnz     short loc_180009C3A
0x180009c9b  mov     rcx, [rsp+78h+var_18]
0x180009ca0  xor     rcx, rsp; StackCookie
0x180009ca3  call    __security_check_cookie
0x180009ca8  add     rsp, 70h
0x180009cac  pop     rbx
0x180009cad  retn
0x180009cae  xor     edx, edx; pContextRecord
0x180009cb0  xor     ecx, ecx; pExceptionRecord
0x180009cb2  lea     r8d, [rdx+1]; dwFlags
0x180009cb6  call    cs:__imp_RaiseFailFastException
0x180009cbc  jmp     short loc_180009C75
```
