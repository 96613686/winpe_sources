# AfdPodSiloCreateCallback

- ea: `0x140052950`
- end: `0x140052ae5`
- name: `AfdPodSiloCreateCallback`
- size: `405`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140052848`
- `0x140052950`
- `0x140052bac`
- `0x140072b00`
- `0x14009304c`
- `0x140094900`

## import_xrefs

- `ntoskrnl!ExInitializeRundownProtection` at `0x140052a38`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140052a38`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1400529d6`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1400529d6`
- `ntoskrnl!PsGetSiloIdentifier` at `0x140052967`
- `ntoskrnl!PsGetSiloIdentifier` at `0x140052967`
- `ntoskrnl!PsCreateSiloContext` at `0x1400529b9`
- `ntoskrnl!PsCreateSiloContext` at `0x1400529b9`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x140052a72`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x140052a72`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x140052a5d`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x140052a5d`
- `ntoskrnl!PsDereferenceSiloContext` at `0x140052acd`
- `ntoskrnl!PsDereferenceSiloContext` at `0x140052acd`

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
0x140052950  push    rbp
0x140052952  push    rbx
0x140052953  push    rsi
0x140052954  push    rdi
0x140052955  mov     rbp, rsp
0x140052958  sub     rsp, 38h
0x14005295c  mov     rbx, rcx
0x14005295f  mov     [rbp+arg_8], 0
0x140052967  call    cs:__imp_PsGetSiloIdentifier
0x14005296e  nop     dword ptr [rax+rax+00h]
0x140052973  mov     esi, eax
0x140052975  cmp     byte ptr cs:xmmword_1400875E0+2, 0
0x14005297c  jge     short loc_14005299B
0x14005297e  mov     edx, 0Ch
0x140052983  mov     dword ptr [rsp+38h+var_18], eax
0x140052987  mov     ecx, 417h
0x14005298c  lea     r8, WPP_2c6c30891f8f331355edd6dbfe12c426_Traceguids
0x140052993  mov     r9, rbx
0x140052996  call    WPP_SF_qD
0x14005299b  lea     rax, [rbp+arg_8]
0x14005299f  mov     edx, 0A0h
0x1400529a4  lea     r9, AfdPodSiloCleanupCallback
0x1400529ab  mov     [rsp+38h+var_18], rax
0x1400529b0  mov     r8d, 200h
0x1400529b6  mov     rcx, rbx
0x1400529b9  call    cs:__imp_PsCreateSiloContext
0x1400529c0  nop     dword ptr [rax+rax+00h]
0x1400529c5  mov     edi, eax
0x1400529c7  test    eax, eax
0x1400529c9  js      loc_140052AB3
0x1400529cf  lea     rcx, AfdPodModuleRundown; RunRef
0x1400529d6  call    cs:__imp_ExAcquireRundownProtection
0x1400529dd  nop     dword ptr [rax+rax+00h]
0x1400529e2  mov     rcx, [rbp+arg_8]; void *
0x1400529e6  xor     edx, edx; Val
0x1400529e8  mov     r8d, 0A0h; Size
0x1400529ee  call    memset
0x1400529f3  cmp     byte ptr cs:xmmword_1400875E0+2, 0
0x1400529fa  jge     short loc_140052A22
0x1400529fc  mov     rax, [rbp+arg_8]
0x140052a00  lea     r8, WPP_2c6c30891f8f331355edd6dbfe12c426_Traceguids
0x140052a07  mov     edx, 0Dh
0x140052a0c  mov     [rsp+38h+var_10], esi
0x140052a10  mov     ecx, 417h
0x140052a15  mov     [rsp+38h+var_18], rax
0x140052a1a  mov     r9, rbx
0x140052a1d  call    WPP_SF_qqD
0x140052a22  mov     rax, [rbp+arg_8]
0x140052a26  mov     [rax], rbx
0x140052a29  mov     rax, [rbp+arg_8]
0x140052a2d  mov     [rax+8], esi
0x140052a30  mov     rcx, [rbp+arg_8]
0x140052a34  add     rcx, 10h; RunRef
0x140052a38  call    cs:__imp_ExInitializeRundownProtection
0x140052a3f  nop     dword ptr [rax+rax+00h]
0x140052a44  mov     rdx, [rbp+arg_8]
0x140052a48  mov     rcx, rbx
0x140052a4b  call    AfdPodStartModules
0x140052a50  mov     edi, eax
0x140052a52  test    eax, eax
0x140052a54  js      short loc_140052AB3
0x140052a56  mov     rcx, cs:AfdPodMonitor
0x140052a5d  call    cs:__imp_PsGetSiloMonitorContextSlot
0x140052a64  nop     dword ptr [rax+rax+00h]
0x140052a69  mov     r8, [rbp+arg_8]
0x140052a6d  mov     rcx, rbx
0x140052a70  mov     edx, eax
0x140052a72  call    cs:__imp_PsInsertPermanentSiloContext
0x140052a79  nop     dword ptr [rax+rax+00h]
0x140052a7e  mov     edi, eax
0x140052a80  test    eax, eax
0x140052a82  jns     short loc_140052AC4
0x140052a84  cmp     byte ptr cs:xmmword_1400875E0+2, 0
0x140052a8b  jge     short loc_140052AB3
0x140052a8d  mov     [rsp+38h+var_10], eax
0x140052a91  lea     r8, WPP_2c6c30891f8f331355edd6dbfe12c426_Traceguids
0x140052a98  mov     rax, [rbp+arg_8]
0x140052a9c  mov     edx, 0Eh
0x140052aa1  mov     ecx, 417h
0x140052aa6  mov     [rsp+38h+var_18], rax
0x140052aab  mov     r9, rbx
0x140052aae  call    WPP_SF_qqD
0x140052ab3  mov     rdx, [rbp+arg_8]
0x140052ab7  test    rdx, rdx
0x140052aba  jz      short loc_140052AD9
0x140052abc  mov     rcx, rbx
0x140052abf  call    AfdPodShutdownModules
0x140052ac4  mov     rcx, [rbp+arg_8]
0x140052ac8  test    rcx, rcx
0x140052acb  jz      short loc_140052AD9
0x140052acd  call    cs:__imp_PsDereferenceSiloContext
0x140052ad4  nop     dword ptr [rax+rax+00h]
0x140052ad9  mov     eax, edi
0x140052adb  add     rsp, 38h
0x140052adf  pop     rdi
0x140052ae0  pop     rsi
0x140052ae1  pop     rbx
0x140052ae2  pop     rbp
0x140052ae3  retn
```
