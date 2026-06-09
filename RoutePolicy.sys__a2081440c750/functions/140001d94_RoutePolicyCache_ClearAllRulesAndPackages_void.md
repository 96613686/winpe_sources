# RoutePolicyCache::ClearAllRulesAndPackages(void)

- ea: `0x140001d94`
- end: `0x140001ed2`
- name: `?ClearAllRulesAndPackages@RoutePolicyCache@@YAXXZ`
- size: `318`
- prototype: `void __fastcall(RoutePolicyCache *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x14000607c`

## callees

- `0x1400012f0`
- `0x140001d94`
- `0x14000242c`
- `0x140007d28`
- `0x140007d7c`
- `0x14000a680`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140001e0d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001e0d`

## pseudocode

```c
void __fastcall RoutePolicyCache::ClearAllRulesAndPackages(RoutePolicyCache *this)
{
  PVOID *i; // rbx
  PVOID v2; // rcx
  _QWORD *v3; // rax
  PVOID *v4; // rdx
  __int128 v5; // [rsp+30h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+40h] [rbp-38h] BYREF

  AcquireSpinLock(&v5, &g_cacheLock);
  if ( (unsigned int)dword_140012050 > 5 )
    tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140012050, (unsigned __int8 *)&qword_14000E738, 0, 0, 2u, &v6);
  for ( i = (PVOID *)g_rulesListHead; i != &g_rulesListHead; i = (PVOID *)*i )
  {
    ExFreePoolWithTag(i[2], 0x64667072u);
    i[2] = 0;
  }
  if ( (unsigned int)dword_140012050 > 5 )
    tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140012050, (unsigned __int8 *)&word_14000E3F2, 0, 0, 2u, &v6);
  while ( 1 )
  {
    v2 = g_packageListHead;
    if ( g_packageListHead == &g_packageListHead )
      break;
    v3 = *(_QWORD **)g_packageListHead;
    if ( *(PVOID *)(*(_QWORD *)g_packageListHead + 8LL) != g_packageListHead
      || (v4 = (PVOID *)*((_QWORD *)g_packageListHead + 1), *v4 != g_packageListHead) )
    {
      __fastfail(3u);
    }
    *v4 = v3;
    v3[1] = v4;
    FreePackageEntry(v2);
  }
  if ( (_QWORD)v5 )
    SpinLockAndSavedIrql::Release((const struct SpinLockAndSavedIrql *)&v5);
}

```

## disassembly

```asm
0x140001d94  mov     [rsp+arg_0], rbx
0x140001d99  push    rdi
0x140001d9a  sub     rsp, 70h
0x140001d9e  mov     rax, cs:__security_cookie
0x140001da5  xor     rax, rsp
0x140001da8  mov     [rsp+78h+var_18], rax
0x140001dad  lea     rdx, ?g_cacheLock@@3_KA; unsigned __int64 g_cacheLock
0x140001db4  lea     rcx, [rsp+78h+var_48]
0x140001db9  call    ?AcquireSpinLock@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUSpinLockAndSavedIrql@@@Z$1?Release@1@SAX0@ZU?$integral_constant@_K$01@wistd@@U1@PEA_K$0A@$$T@details@wil@@@details@wil@@@wil@@PEA_K@Z; AcquireSpinLock(unsigned __int64 *)
0x140001dbe  mov     eax, cs:dword_140012050
0x140001dc4  cmp     eax, 5
0x140001dc7  jbe     short loc_140001DF4
0x140001dc9  lea     rax, [rsp+78h+var_38]
0x140001dce  xor     r9d, r9d; int
0x140001dd1  mov     [rsp+78h+var_50], rax; PEVENT_DATA_DESCRIPTOR
0x140001dd6  lea     rdx, qword_14000E738; int
0x140001ddd  xor     r8d, r8d; int
0x140001de0  mov     [rsp+78h+var_58], 2; ULONG
0x140001de8  lea     rcx, dword_140012050; int
0x140001def  call    _tlgWriteTransfer_EtwWriteTransfer
0x140001df4  mov     rbx, cs:?g_rulesListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_rulesListHead
0x140001dfb  lea     rdi, ?g_rulesListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_rulesListHead
0x140001e02  jmp     short loc_140001E24
0x140001e04  mov     rcx, [rbx+10h]; P
0x140001e08  mov     edx, 64667072h; Tag
0x140001e0d  call    cs:__imp_ExFreePoolWithTag
0x140001e14  nop     dword ptr [rax+rax+00h]
0x140001e19  mov     qword ptr [rbx+10h], 0
0x140001e21  mov     rbx, [rbx]
0x140001e24  cmp     rbx, rdi
0x140001e27  jnz     short loc_140001E04
0x140001e29  mov     eax, cs:dword_140012050
0x140001e2f  cmp     eax, 5
0x140001e32  jbe     short loc_140001E5F
0x140001e34  lea     rax, [rsp+78h+var_38]
0x140001e39  xor     r9d, r9d; int
0x140001e3c  mov     [rsp+78h+var_50], rax; PEVENT_DATA_DESCRIPTOR
0x140001e41  lea     rdx, word_14000E3F2; int
0x140001e48  xor     r8d, r8d; int
0x140001e4b  mov     [rsp+78h+var_58], 2; ULONG
0x140001e53  lea     rcx, dword_140012050; int
0x140001e5a  call    _tlgWriteTransfer_EtwWriteTransfer
0x140001e5f  mov     rcx, cs:?g_packageListHead@@3U_LIST_ENTRY@@A; P
0x140001e66  lea     rax, ?g_packageListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_packageListHead
0x140001e6d  cmp     rcx, rax
0x140001e70  jz      short loc_140001E99
0x140001e72  mov     rax, [rcx]
0x140001e75  cmp     [rax+8], rcx
0x140001e79  jnz     short loc_140001E92
0x140001e7b  mov     rdx, [rcx+8]
0x140001e7f  cmp     [rdx], rcx
0x140001e82  jnz     short loc_140001E92
0x140001e84  mov     [rdx], rax
0x140001e87  mov     [rax+8], rdx
0x140001e8b  call    FreePackageEntry
0x140001e90  jmp     short loc_140001E5F
0x140001e92  mov     ecx, 3
0x140001e97  int     29h; Win8: RtlFailFast(ecx)
0x140001e99  cmp     qword ptr [rsp+78h+var_48], 0
0x140001e9f  jz      short loc_140001EB6
0x140001ea1  movaps  xmm0, [rsp+78h+var_48]
0x140001ea6  lea     rcx, [rsp+78h+var_48]; struct SpinLockAndSavedIrql *
0x140001eab  movdqa  [rsp+78h+var_48], xmm0
0x140001eb1  call    ?Release@SpinLockAndSavedIrql@@SAXAEBU1@@Z; SpinLockAndSavedIrql::Release(SpinLockAndSavedIrql const &)
0x140001eb6  mov     rcx, [rsp+78h+var_18]
0x140001ebb  xor     rcx, rsp; StackCookie
0x140001ebe  call    __security_check_cookie
0x140001ec3  mov     rbx, [rsp+78h+arg_0]
0x140001ecb  add     rsp, 70h
0x140001ecf  pop     rdi
0x140001ed0  retn
```
