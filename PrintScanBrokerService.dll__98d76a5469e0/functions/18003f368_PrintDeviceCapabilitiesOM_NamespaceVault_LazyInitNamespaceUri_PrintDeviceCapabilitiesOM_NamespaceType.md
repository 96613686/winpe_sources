# PrintDeviceCapabilitiesOM::NamespaceVault::LazyInitNamespaceUri(PrintDeviceCapabilitiesOM::NamespaceType)

- ea: `0x18003f368`
- end: `0x18003f405`
- name: `?LazyInitNamespaceUri@NamespaceVault@PrintDeviceCapabilitiesOM@@CAAEBV?$shared_ptr@$$CBVNamespaceUri@PrintDeviceCapabilitiesOM@@@std@@W4NamespaceType@2@@Z`
- size: `157`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `16`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18003b7f4`
- `0x18003bb30`
- `0x18003bfd4`
- `0x18003c428`
- `0x18003cadc`
- `0x18003cc3c`
- `0x18003e10c`
- `0x18003e53c`
- `0x18003e734`
- `0x18003faa4`
- `0x18003fda4`
- `0x18003fef0`
- `0x18003ff90`
- `0x180040324`
- `0x1800405f4`
- `0x180040d78`

## callees

- `0x180002d70`
- `0x1800384a0`
- `0x18003f368`
- `0x1800421e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003f382`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003f382`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f3ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f3ee`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 *__fastcall PrintDeviceCapabilitiesOM::NamespaceVault::LazyInitNamespaceUri(int a1)
{
  __int64 v1; // rbx
  __int64 v2; // rdi
  __int64 *v3; // rbx
  __int64 v4; // rax
  std::_Ref_count_base *v5; // rcx
  void *v7; // [rsp+50h] [rbp+18h]

  v1 = a1;
  EnterCriticalSection(&PrintDeviceCapabilitiesOM::NamespaceVault::_cs);
  v2 = v1;
  v3 = &PrintDeviceCapabilitiesOM::NamespaceVault::_namespaceUriTable[2 * v1];
  if ( !*v3 )
  {
    v7 = operator new(0x28u);
    v4 = std::_Ref_count_obj2<PrintDeviceCapabilitiesOM::NamespaceUri>::_Ref_count_obj2<PrintDeviceCapabilitiesOM::NamespaceUri>(
           (__int64)v7,
           &(&PrintDeviceCapabilitiesOM::NamespaceVault::_nameTable)[v2]);
    *v3 = v4 + 16;
    v5 = (std::_Ref_count_base *)v3[1];
    v3[1] = v4;
    if ( v5 )
      std::_Ref_count_base::_Decref(v5);
  }
  LeaveCriticalSection(&PrintDeviceCapabilitiesOM::NamespaceVault::_cs);
  return v3;
}

```

## disassembly

```asm
0x18003f368  mov     [rsp+arg_18], rbx
0x18003f36d  push    rsi
0x18003f36e  push    rdi
0x18003f36f  push    r14
0x18003f371  sub     rsp, 20h
0x18003f375  movsxd  rbx, ecx
0x18003f378  lea     rsi, ?_cs@NamespaceVault@PrintDeviceCapabilitiesOM@@0VCriticalSection@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::CriticalSection PrintDeviceCapabilitiesOM::NamespaceVault::_cs
0x18003f37f  mov     rcx, rsi; lpCriticalSection
0x18003f382  call    cs:__imp_EnterCriticalSection
0x18003f388  mov     [rsp+38h+arg_8], rsi
0x18003f38d  mov     rdi, rbx
0x18003f390  mov     rax, rbx
0x18003f393  shl     rax, 4
0x18003f397  lea     r14, __ImageBase
0x18003f39e  lea     rbx, rva ?_namespaceUriTable@NamespaceVault@PrintDeviceCapabilitiesOM@@0PAV?$shared_ptr@$$CBVNamespaceUri@PrintDeviceCapabilitiesOM@@@std@@A[r14]; std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceUri const> near * PrintDeviceCapabilitiesOM::NamespaceVault::_namespaceUriTable ...
0x18003f3a5  add     rbx, rax
0x18003f3a8  cmp     qword ptr [rbx], 0
0x18003f3ac  jnz     short loc_18003F3EB
0x18003f3ae  mov     ecx, 28h ; '('; Size
0x18003f3b3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003f3b8  mov     [rsp+38h+arg_10], rax
0x18003f3bd  lea     rdx, rva ?_nameTable@NamespaceVault@PrintDeviceCapabilitiesOM@@0QBQEBGB[r14]; ushort const * const near * const PrintDeviceCapabilitiesOM::NamespaceVault::_nameTable ...
0x18003f3c4  lea     rdx, [rdx+rdi*8]
0x18003f3c8  mov     rcx, rax
0x18003f3cb  call    ??$?0AEBQEBG@?$_Ref_count_obj2@VNamespaceUri@PrintDeviceCapabilitiesOM@@@std@@QEAA@AEBQEBG@Z; std::_Ref_count_obj2<PrintDeviceCapabilitiesOM::NamespaceUri>::_Ref_count_obj2<PrintDeviceCapabilitiesOM::NamespaceUri>(ushort const * const &)
0x18003f3d0  nop
0x18003f3d1  lea     rdx, [rax+10h]
0x18003f3d5  mov     [rbx], rdx
0x18003f3d8  mov     rcx, [rbx+8]; this
0x18003f3dc  mov     [rbx+8], rax
0x18003f3e0  test    rcx, rcx
0x18003f3e3  jz      short loc_18003F3EB
0x18003f3e5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003f3ea  nop
0x18003f3eb  mov     rcx, rsi; lpCriticalSection
0x18003f3ee  call    cs:__imp_LeaveCriticalSection
0x18003f3f4  mov     rax, rbx
0x18003f3f7  mov     rbx, [rsp+38h+arg_18]
0x18003f3fc  add     rsp, 20h
0x18003f400  pop     r14
0x18003f402  pop     rdi
0x18003f403  pop     rsi
0x18003f404  retn
```
