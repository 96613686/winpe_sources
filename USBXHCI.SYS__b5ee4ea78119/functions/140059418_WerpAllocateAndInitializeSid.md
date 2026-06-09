# WerpAllocateAndInitializeSid

- ea: `0x140059418`
- end: `0x140059549`
- name: `WerpAllocateAndInitializeSid`
- size: `305`
- prototype: `__int64 __usercall@<rax>(PSID_IDENTIFIER_AUTHORITY IdentifierAuthority@<rcx>, int, int, int, int, int, int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140058c20`

## callees

- `0x140059418`
- `0x140059690`
- `0x140059d80`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140059457`
- `ntoskrnl!DbgPrintEx` at `0x1400594d9`
- `ntoskrnl!DbgPrintEx` at `0x140059511`
- `ntoskrnl!DbgPrintEx` at `0x140059457`
- `ntoskrnl!DbgPrintEx` at `0x1400594d9`
- `ntoskrnl!DbgPrintEx` at `0x140059511`
- `ntoskrnl!RtlInitializeSid` at `0x1400594b4`
- `ntoskrnl!RtlInitializeSid` at `0x1400594b4`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140059524`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140059524`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14005942b`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14005942b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14005947e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14005947e`

## string_xrefs

- `0x1400594cc`: `WERLIVEKERNELREPORTING:%u: ERROR RtlInitializeSid failed\n`

## pseudocode

```c
__int64 __fastcall WerpAllocateAndInitializeSid(
        PSID_IDENTIFIER_AUTHORITY IdentifierAuthority,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        int a7,
        int a8,
        int a9,
        int a10,
        _QWORD *a11)
{
  signed int v12; // eax
  size_t v14; // rdi
  PVOID PoolWithTag; // rax
  void *v16; // rbx
  PVOID v17; // rsi
  NTSTATUS v18; // edi

  v12 = RtlLengthRequiredSid(1u);
  if ( !a11 )
  {
    DbgPrintEx(0x96u, 0, "WERLIVEKERNELREPORTING:%u: ERROR Invalid params\n", 242);
    return 3221225485LL;
  }
  v14 = v12;
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1025, v12, 0x7765726Bu);
  v16 = PoolWithTag;
  if ( !ExPoolZeroingNativelySupported && PoolWithTag )
  {
    memset(PoolWithTag, 0, v14);
    v17 = v16;
    goto LABEL_6;
  }
  v17 = PoolWithTag;
  if ( PoolWithTag )
  {
LABEL_6:
    v18 = RtlInitializeSid(v16, IdentifierAuthority, 1u);
    if ( v18 >= 0 )
    {
      v18 = 0;
      *RtlSubAuthoritySid(v16, 0) = 18;
    }
    else
    {
      DbgPrintEx(0x96u, 0, "WERLIVEKERNELREPORTING:%u: ERROR RtlInitializeSid failed\n", 258);
      WerpFreeMem(v16);
      v17 = 0;
    }
    goto LABEL_11;
  }
  v18 = -1073741823;
  DbgPrintEx(0x96u, 0, "WERLIVEKERNELREPORTING:%u: ERROR NtAllocateVirtualMemory failed\n", 250);
LABEL_11:
  *a11 = v17;
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x140059418  push    rbx
0x14005941a  push    rbp
0x14005941b  push    rsi
0x14005941c  push    rdi
0x14005941d  push    r14
0x14005941f  sub     rsp, 20h
0x140059423  mov     rbp, rcx
0x140059426  mov     ecx, 1; SubAuthorityCount
0x14005942b  call    cs:__imp_RtlLengthRequiredSid
0x140059432  nop     dword ptr [rax+rax+00h]
0x140059437  mov     r14, [rsp+48h+arg_50]
0x14005943f  test    r14, r14
0x140059442  jnz     short loc_14005946D
0x140059444  mov     r9d, 0F2h
0x14005944a  lea     r8, aWerlivekernelr_23; "WERLIVEKERNELREPORTING:%u: ERROR Invali"...
0x140059451  xor     edx, edx; Level
0x140059453  lea     ecx, [r9-5Ch]; ComponentId
0x140059457  call    cs:__imp_DbgPrintEx
0x14005945e  nop     dword ptr [rax+rax+00h]
0x140059463  mov     eax, 0C000000Dh
0x140059468  jmp     loc_14005953D
0x14005946d  movsxd  rdi, eax
0x140059470  mov     r8d, 7765726Bh; Tag
0x140059476  mov     rdx, rdi; NumberOfBytes
0x140059479  mov     ecx, 401h; PoolType
0x14005947e  call    cs:__imp_ExAllocatePoolWithTag
0x140059485  nop     dword ptr [rax+rax+00h]
0x14005948a  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140059491  mov     rbx, rax
0x140059494  jnz     short loc_1400594F1
0x140059496  test    rax, rax
0x140059499  jz      short loc_1400594F1
0x14005949b  mov     r8, rdi; Size
0x14005949e  xor     edx, edx; Val
0x1400594a0  mov     rcx, rax; void *
0x1400594a3  call    memset
0x1400594a8  mov     rsi, rbx
0x1400594ab  mov     r8b, 1; SubAuthorityCount
0x1400594ae  mov     rdx, rbp; IdentifierAuthority
0x1400594b1  mov     rcx, rbx; Sid
0x1400594b4  call    cs:__imp_RtlInitializeSid
0x1400594bb  nop     dword ptr [rax+rax+00h]
0x1400594c0  mov     edi, eax
0x1400594c2  test    eax, eax
0x1400594c4  jns     short loc_14005951F
0x1400594c6  mov     r9d, 102h
0x1400594cc  lea     r8, aWerlivekernelr_16; "WERLIVEKERNELREPORTING:%u: ERROR RtlIni"...
0x1400594d3  xor     edx, edx; Level
0x1400594d5  lea     ecx, [r9-6Ch]; ComponentId
0x1400594d9  call    cs:__imp_DbgPrintEx
0x1400594e0  nop     dword ptr [rax+rax+00h]
0x1400594e5  mov     rcx, rbx
0x1400594e8  call    WerpFreeMem
0x1400594ed  xor     esi, esi
0x1400594ef  jmp     short loc_140059538
0x1400594f1  mov     rsi, rbx
0x1400594f4  test    rbx, rbx
0x1400594f7  jnz     short loc_1400594AB
0x1400594f9  mov     r9d, 0FAh
0x1400594ff  lea     r8, aWerlivekernelr_11; "WERLIVEKERNELREPORTING:%u: ERROR NtAllo"...
0x140059506  xor     edx, edx; Level
0x140059508  mov     edi, 0C0000001h
0x14005950d  lea     ecx, [r9-64h]; ComponentId
0x140059511  call    cs:__imp_DbgPrintEx
0x140059518  nop     dword ptr [rax+rax+00h]
0x14005951d  jmp     short loc_140059538
0x14005951f  xor     edx, edx; SubAuthority
0x140059521  mov     rcx, rbx; Sid
0x140059524  call    cs:__imp_RtlSubAuthoritySid
0x14005952b  nop     dword ptr [rax+rax+00h]
0x140059530  xor     edi, edi
0x140059532  mov     dword ptr [rax], 12h
0x140059538  mov     [r14], rsi
0x14005953b  mov     eax, edi
0x14005953d  add     rsp, 20h
0x140059541  pop     r14
0x140059543  pop     rdi
0x140059544  pop     rsi
0x140059545  pop     rbp
0x140059546  pop     rbx
0x140059547  retn
```
