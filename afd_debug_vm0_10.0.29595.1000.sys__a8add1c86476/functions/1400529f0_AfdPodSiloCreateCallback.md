# AfdPodSiloCreateCallback

- ea: `0x1400529f0`
- end: `0x140052b85`
- name: `AfdPodSiloCreateCallback`
- size: `405`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1400528e8`
- `0x1400529f0`
- `0x140052c4c`
- `0x140072c80`
- `0x14009304c`
- `0x140094900`

## import_xrefs

- `ntoskrnl!ExInitializeRundownProtection` at `0x140052ad8`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140052ad8`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140052a76`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140052a76`
- `ntoskrnl!PsGetSiloIdentifier` at `0x140052a07`
- `ntoskrnl!PsGetSiloIdentifier` at `0x140052a07`
- `ntoskrnl!PsCreateSiloContext` at `0x140052a59`
- `ntoskrnl!PsCreateSiloContext` at `0x140052a59`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x140052b12`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x140052b12`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x140052afd`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x140052afd`
- `ntoskrnl!PsDereferenceSiloContext` at `0x140052b6d`
- `ntoskrnl!PsDereferenceSiloContext` at `0x140052b6d`

## pseudocode

```c
__int64 __fastcall AfdPodSiloCreateCallback(__int64 a1)
{
  int SiloIdentifier; // eax
  int v3; // esi
  int started; // edi
  unsigned int SiloMonitorContextSlot; // eax
  int inserted; // eax
  void *v8; // [rsp+68h] [rbp+30h] BYREF

  v8 = 0;
  SiloIdentifier = PsGetSiloIdentifier();
  v3 = SiloIdentifier;
  if ( SBYTE2(xmmword_1400875E0) < 0 )
    WPP_SF_qD(1047, 12, WPP_2c6c30891f8f331355edd6dbfe12c426_Traceguids, a1, SiloIdentifier);
  started = PsCreateSiloContext(a1, 160, 512, AfdPodSiloCleanupCallback, &v8);
  if ( started >= 0 )
  {
    ExAcquireRundownProtection(&AfdPodModuleRundown);
    memset(v8, 0, 0xA0u);
    if ( SBYTE2(xmmword_1400875E0) < 0 )
      WPP_SF_qqD(1047, 13, WPP_2c6c30891f8f331355edd6dbfe12c426_Traceguids, a1, v8, v3);
    *(_QWORD *)v8 = a1;
    *((_DWORD *)v8 + 2) = v3;
    ExInitializeRundownProtection((PEX_RUNDOWN_REF)v8 + 2);
    started = AfdPodStartModules(a1, v8);
    if ( started >= 0 )
    {
      SiloMonitorContextSlot = PsGetSiloMonitorContextSlot(AfdPodMonitor);
      inserted = PsInsertPermanentSiloContext(a1, SiloMonitorContextSlot, v8);
      started = inserted;
      if ( inserted >= 0 )
        goto LABEL_12;
      if ( SBYTE2(xmmword_1400875E0) < 0 )
        WPP_SF_qqD(1047, 14, WPP_2c6c30891f8f331355edd6dbfe12c426_Traceguids, a1, v8, inserted);
    }
  }
  if ( !v8 )
    return (unsigned int)started;
  AfdPodShutdownModules(a1);
LABEL_12:
  if ( v8 )
    PsDereferenceSiloContext();
  return (unsigned int)started;
}

```

## disassembly

```asm
0x1400529f0  push    rbp
0x1400529f2  push    rbx
0x1400529f3  push    rsi
0x1400529f4  push    rdi
0x1400529f5  mov     rbp, rsp
0x1400529f8  sub     rsp, 38h
0x1400529fc  mov     rbx, rcx
0x1400529ff  mov     [rbp+arg_8], 0
0x140052a07  call    cs:__imp_PsGetSiloIdentifier
0x140052a0e  nop     dword ptr [rax+rax+00h]
0x140052a13  mov     esi, eax
0x140052a15  cmp     byte ptr cs:xmmword_1400875E0+2, 0
0x140052a1c  jge     short loc_140052A3B
0x140052a1e  mov     edx, 0Ch
0x140052a23  mov     dword ptr [rsp+38h+var_18], eax
0x140052a27  mov     ecx, 417h
0x140052a2c  lea     r8, WPP_2c6c30891f8f331355edd6dbfe12c426_Traceguids
0x140052a33  mov     r9, rbx
0x140052a36  call    WPP_SF_qD
0x140052a3b  lea     rax, [rbp+arg_8]
0x140052a3f  mov     edx, 0A0h
0x140052a44  lea     r9, AfdPodSiloCleanupCallback
0x140052a4b  mov     [rsp+38h+var_18], rax
0x140052a50  mov     r8d, 200h
0x140052a56  mov     rcx, rbx
0x140052a59  call    cs:__imp_PsCreateSiloContext
0x140052a60  nop     dword ptr [rax+rax+00h]
0x140052a65  mov     edi, eax
0x140052a67  test    eax, eax
0x140052a69  js      loc_140052B53
0x140052a6f  lea     rcx, AfdPodModuleRundown; RunRef
0x140052a76  call    cs:__imp_ExAcquireRundownProtection
0x140052a7d  nop     dword ptr [rax+rax+00h]
0x140052a82  mov     rcx, [rbp+arg_8]; void *
0x140052a86  xor     edx, edx; Val
0x140052a88  mov     r8d, 0A0h; Size
0x140052a8e  call    memset
0x140052a93  cmp     byte ptr cs:xmmword_1400875E0+2, 0
0x140052a9a  jge     short loc_140052AC2
0x140052a9c  mov     rax, [rbp+arg_8]
0x140052aa0  lea     r8, WPP_2c6c30891f8f331355edd6dbfe12c426_Traceguids
0x140052aa7  mov     edx, 0Dh
0x140052aac  mov     [rsp+38h+var_10], esi
0x140052ab0  mov     ecx, 417h
0x140052ab5  mov     [rsp+38h+var_18], rax
0x140052aba  mov     r9, rbx
0x140052abd  call    WPP_SF_qqD
0x140052ac2  mov     rax, [rbp+arg_8]
0x140052ac6  mov     [rax], rbx
0x140052ac9  mov     rax, [rbp+arg_8]
0x140052acd  mov     [rax+8], esi
0x140052ad0  mov     rcx, [rbp+arg_8]
0x140052ad4  add     rcx, 10h; RunRef
0x140052ad8  call    cs:__imp_ExInitializeRundownProtection
0x140052adf  nop     dword ptr [rax+rax+00h]
0x140052ae4  mov     rdx, [rbp+arg_8]
0x140052ae8  mov     rcx, rbx
0x140052aeb  call    AfdPodStartModules
0x140052af0  mov     edi, eax
0x140052af2  test    eax, eax
0x140052af4  js      short loc_140052B53
0x140052af6  mov     rcx, cs:AfdPodMonitor
0x140052afd  call    cs:__imp_PsGetSiloMonitorContextSlot
0x140052b04  nop     dword ptr [rax+rax+00h]
0x140052b09  mov     r8, [rbp+arg_8]
0x140052b0d  mov     rcx, rbx
0x140052b10  mov     edx, eax
0x140052b12  call    cs:__imp_PsInsertPermanentSiloContext
0x140052b19  nop     dword ptr [rax+rax+00h]
0x140052b1e  mov     edi, eax
0x140052b20  test    eax, eax
0x140052b22  jns     short loc_140052B64
0x140052b24  cmp     byte ptr cs:xmmword_1400875E0+2, 0
0x140052b2b  jge     short loc_140052B53
0x140052b2d  mov     [rsp+38h+var_10], eax
0x140052b31  lea     r8, WPP_2c6c30891f8f331355edd6dbfe12c426_Traceguids
0x140052b38  mov     rax, [rbp+arg_8]
0x140052b3c  mov     edx, 0Eh
0x140052b41  mov     ecx, 417h
0x140052b46  mov     [rsp+38h+var_18], rax
0x140052b4b  mov     r9, rbx
0x140052b4e  call    WPP_SF_qqD
0x140052b53  mov     rdx, [rbp+arg_8]
0x140052b57  test    rdx, rdx
0x140052b5a  jz      short loc_140052B79
0x140052b5c  mov     rcx, rbx
0x140052b5f  call    AfdPodShutdownModules
0x140052b64  mov     rcx, [rbp+arg_8]
0x140052b68  test    rcx, rcx
0x140052b6b  jz      short loc_140052B79
0x140052b6d  call    cs:__imp_PsDereferenceSiloContext
0x140052b74  nop     dword ptr [rax+rax+00h]
0x140052b79  mov     eax, edi
0x140052b7b  add     rsp, 38h
0x140052b7f  pop     rdi
0x140052b80  pop     rsi
0x140052b81  pop     rbx
0x140052b82  pop     rbp
0x140052b83  retn
```
