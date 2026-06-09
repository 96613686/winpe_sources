# Windows::System::Diagnostics::DiagnosticInvokerStatics::RuntimeClassInitialize(void)

- ea: `0x180007700`
- end: `0x180007839`
- name: `?RuntimeClassInitialize@DiagnosticInvokerStatics@Diagnostics@System@Windows@@QEAAJXZ`
- size: `313`
- prototype: `__int64 __fastcall(Windows::System::Diagnostics::DiagnosticInvokerStatics *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180006680`

## callees

- `0x1800022c0`
- `0x1800022fc`
- `0x180007088`
- `0x180007700`
- `0x180007840`

## import_xrefs

- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180007771`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180007771`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007808`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007808`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800077b7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800077b7`

## pseudocode

```c
__int64 __fastcall Windows::System::Diagnostics::DiagnosticInvokerStatics::RuntimeClassInitialize(
        Windows::System::Diagnostics::DiagnosticInvokerStatics *this)
{
  char *v1; // rbx
  int v3; // esi
  TraceLoggingCorrelationVector *v4; // rax
  TraceLoggingCorrelationVector *v5; // rax
  TraceLoggingCorrelationVector *v6; // rdi
  char v7; // bl
  bool v8; // al
  LSTATUS v9; // eax
  bool v10; // sf
  LSTATUS v11; // eax
  bool v12; // sf
  __int64 result; // rax
  int Data; // [rsp+60h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+38h] BYREF
  DWORD Type; // [rsp+70h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+48h] BYREF

  v1 = (char *)this + 50;
  if ( this == (Windows::System::Diagnostics::DiagnosticInvokerStatics *)-50LL )
  {
    v3 = -2147024809;
  }
  else
  {
    v3 = 0;
    v4 = (TraceLoggingCorrelationVector *)operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v4 )
    {
      v5 = TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(v4);
      v6 = v5;
      if ( v5 )
      {
        TraceLoggingCorrelationVector::ToString(v5, v1);
        operator delete(v6, (const struct std::nothrow_t *)0x90);
      }
    }
  }
  Data = 0;
  RtlGetDeviceFamilyInfoEnum(0, &Data, 0);
  v7 = 1;
  v8 = Data == 3 || Data == 16;
  *((_BYTE *)this + 48) = v8;
  hKey = 0;
  v9 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Policies\\Microsoft\\Windows\\ScriptedDiagnostics",
         0,
         0x20019u,
         &hKey);
  v10 = v9 < 0;
  if ( v9 > 0 )
    v10 = 1;
  if ( v10 )
    goto LABEL_17;
  cbData = 4;
  Type = 0;
  Data = 0;
  v11 = RegQueryValueExW(hKey, L"EnableDiagnostics", 0, &Type, (LPBYTE)&Data, &cbData);
  v12 = v11 < 0;
  if ( v11 > 0 )
    v12 = 1;
  if ( v12 || Data )
LABEL_17:
    v7 = 0;
  result = 0;
  *((_BYTE *)this + 49) = v7;
  if ( v3 >= 0 )
    return (unsigned int)v3;
  return result;
}

```

## disassembly

```asm
0x180007700  push    rbp
0x180007702  push    rbx
0x180007703  push    rsi
0x180007704  push    rdi
0x180007705  push    r14
0x180007707  mov     rbp, rsp
0x18000770a  sub     rsp, 30h
0x18000770e  lea     rbx, [rcx+32h]
0x180007712  mov     r14, rcx
0x180007715  test    rbx, rbx
0x180007718  jnz     short loc_180007721
0x18000771a  mov     esi, 80070057h
0x18000771f  jmp     short loc_180007761
0x180007721  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007728  mov     ecx, 90h; unsigned __int64
0x18000772d  xor     esi, esi
0x18000772f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180007734  test    rax, rax
0x180007737  jz      short loc_180007761
0x180007739  mov     rcx, rax; this
0x18000773c  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x180007741  mov     rdi, rax
0x180007744  test    rax, rax
0x180007747  jz      short loc_180007761
0x180007749  mov     rdx, rbx; char *
0x18000774c  mov     rcx, rax; this
0x18000774f  call    ?ToString@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::ToString(char *)
0x180007754  mov     edx, 90h; struct std::nothrow_t *
0x180007759  mov     rcx, rdi; void *
0x18000775c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007761  xor     r8d, r8d
0x180007764  mov     [rbp+Data], 0
0x18000776b  lea     rdx, [rbp+Data]
0x18000776f  xor     ecx, ecx
0x180007771  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x180007777  cmp     [rbp+Data], 3
0x18000777b  mov     bl, 1
0x18000777d  jz      short loc_180007789
0x18000777f  cmp     [rbp+Data], 10h
0x180007783  jz      short loc_180007789
0x180007785  xor     al, al
0x180007787  jmp     short loc_18000778B
0x180007789  mov     al, bl
0x18000778b  mov     [r14+30h], al
0x18000778f  lea     rdx, SubKey; "Software\\Policies\\Microsoft\\Windows"...
0x180007796  lea     rax, [rbp+hKey]
0x18000779a  mov     [rbp+hKey], 0
0x1800077a2  mov     r9d, 20019h; samDesired
0x1800077a8  mov     [rsp+30h+phkResult], rax; phkResult
0x1800077ad  xor     r8d, r8d; ulOptions
0x1800077b0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800077b7  call    cs:__imp_RegOpenKeyExW
0x1800077bd  mov     edi, 80070000h
0x1800077c2  test    eax, eax
0x1800077c4  jle     short loc_1800077CD
0x1800077c6  movzx   eax, ax
0x1800077c9  or      eax, edi
0x1800077cb  test    eax, eax
0x1800077cd  js      short loc_180007821
0x1800077cf  mov     rcx, [rbp+hKey]; hKey
0x1800077d3  lea     rax, [rbp+cbData]
0x1800077d7  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800077dc  lea     r9, [rbp+Type]; lpType
0x1800077e0  lea     rax, [rbp+Data]
0x1800077e4  mov     [rbp+cbData], 4
0x1800077eb  xor     r8d, r8d; lpReserved
0x1800077ee  mov     [rsp+30h+phkResult], rax; lpData
0x1800077f3  lea     rdx, ValueName; "EnableDiagnostics"
0x1800077fa  mov     [rbp+Type], 0
0x180007801  mov     [rbp+Data], 0
0x180007808  call    cs:__imp_RegQueryValueExW
0x18000780e  test    eax, eax
0x180007810  jle     short loc_180007819
0x180007812  movzx   eax, ax
0x180007815  or      eax, edi
0x180007817  test    eax, eax
0x180007819  js      short loc_180007821
0x18000781b  cmp     [rbp+Data], 0
0x18000781f  jz      short loc_180007823
0x180007821  xor     bl, bl
0x180007823  xor     eax, eax
0x180007825  mov     [r14+31h], bl
0x180007829  test    esi, esi
0x18000782b  cmovns  eax, esi
0x18000782e  add     rsp, 30h
0x180007832  pop     r14
0x180007834  pop     rdi
0x180007835  pop     rsi
0x180007836  pop     rbx
0x180007837  pop     rbp
0x180007838  retn
```
