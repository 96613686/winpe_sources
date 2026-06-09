# CPolicyCheck::Cleanup(void)

- ea: `0x180003794`
- end: `0x180003834`
- name: `?Cleanup@CPolicyCheck@@QEAAXXZ`
- size: `160`
- prototype: `void __fastcall(CPolicyCheck *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180002b78`
- `0x180009f74`

## callees

- `0x180003794`
- `0x180003f7c`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800037f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800037f9`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800037bc`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800037bc`
- `ntdll!RtlReleaseResource` at `0x1800037cd`
- `ntdll!RtlReleaseResource` at `0x1800037cd`
- `ntdll!RtlDeleteResource` at `0x1800037d6`
- `ntdll!RtlDeleteResource` at `0x1800037d6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CPolicyCheck::Cleanup(CPolicyCheck *this)
{
  HKEY v2; // rsi
  struct _RTL_RESOURCE *v3; // rbx
  __int64 v4; // rcx

  v2 = (HKEY)*((_QWORD *)this + 20);
  if ( *((_DWORD *)this + 2) )
  {
    v3 = (struct _RTL_RESOURCE *)((char *)this + 16);
    RtlAcquireResourceExclusive((PRTL_RESOURCE)((char *)this + 16), 1u);
    CPolicyCheck::ResetPolicy(this);
    RtlReleaseResource(v3);
    RtlDeleteResource(v3);
    *((_DWORD *)this + 2) = 0;
  }
  if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 20, 0, (signed __int64)v2) )
    RegCloseKey(v2);
  v4 = *((_QWORD *)this + 21);
  if ( v4 )
  {
    *((_QWORD *)this + 21) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
}

```

## disassembly

```asm
0x180003794  mov     [rsp+arg_0], rbx
0x180003799  mov     [rsp+arg_8], rsi
0x18000379e  push    rdi
0x18000379f  sub     rsp, 20h
0x1800037a3  mov     rdi, rcx
0x1800037a6  mov     rsi, [rcx+0A0h]
0x1800037ad  cmp     dword ptr [rcx+8], 0
0x1800037b1  jz      short loc_1800037E3
0x1800037b3  lea     rbx, [rcx+10h]
0x1800037b7  mov     dl, 1; Wait
0x1800037b9  mov     rcx, rbx; Resource
0x1800037bc  call    cs:__imp_RtlAcquireResourceExclusive
0x1800037c2  mov     rcx, rdi; this
0x1800037c5  call    ?ResetPolicy@CPolicyCheck@@QEAAJXZ; CPolicyCheck::ResetPolicy(void)
0x1800037ca  mov     rcx, rbx; Resource
0x1800037cd  call    cs:__imp_RtlReleaseResource
0x1800037d3  mov     rcx, rbx; Resource
0x1800037d6  call    cs:__imp_RtlDeleteResource
0x1800037dc  mov     dword ptr [rdi+8], 0
0x1800037e3  xor     edx, edx
0x1800037e5  mov     rax, rsi
0x1800037e8  lock cmpxchg [rdi+0A0h], rdx
0x1800037f1  test    rax, rax
0x1800037f4  jz      short loc_180003800
0x1800037f6  mov     rcx, rsi; hKey
0x1800037f9  call    cs:__imp_RegCloseKey
0x1800037ff  nop
0x180003800  mov     rcx, [rdi+0A8h]
0x180003807  test    rcx, rcx
0x18000380a  jz      short loc_180003824
0x18000380c  mov     qword ptr [rdi+0A8h], 0
0x180003817  mov     rax, [rcx]
0x18000381a  mov     rax, [rax+10h]
0x18000381e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003823  nop
0x180003824  mov     rbx, [rsp+28h+arg_0]
0x180003829  mov     rsi, [rsp+28h+arg_8]
0x18000382e  add     rsp, 20h
0x180003832  pop     rdi
0x180003833  retn
```
