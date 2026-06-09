# AfdSanFastSetServiceProcess

- ea: `0x14005c7b0`
- end: `0x14005c86d`
- name: `AfdSanFastSetServiceProcess`
- size: `189`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, service_task`

## callees

- `0x14005c7b0`

## import_xrefs

- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14005c84c`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14005c84c`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x14005c801`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x14005c801`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14005c820`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14005c820`
- `ntoskrnl!IoGetCurrentProcess` at `0x14005c7dc`
- `ntoskrnl!IoGetCurrentProcess` at `0x14005c7dc`

## pseudocode

```c
__int64 __fastcall AfdSanFastSetServiceProcess(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        int a7,
        _QWORD *a8)
{
  __int64 v8; // rdi
  struct _KPROCESS *v9; // rbx
  unsigned int v11; // ebx

  *a8 = 0;
  v8 = *(_QWORD *)(a1 + 24);
  if ( *(_WORD *)v8 != 2813 )
    return 3221225480LL;
  v9 = *(struct _KPROCESS **)(v8 + 48);
  if ( v9 != IoGetCurrentProcess() )
    return 3221225480LL;
  if ( !*(_BYTE *)(v8 + 3) )
    return 3221225506LL;
  ExEnterCriticalRegionAndAcquireResourceExclusive(AfdGlobalData);
  if ( AfdSanServiceHelper )
  {
    v11 = v8 != AfdSanServiceHelper ? 0xC000020A : 0;
  }
  else
  {
    AfdSanServiceHelper = v8;
    AfdSanServicePid = (__int64)PsGetCurrentProcessId();
    v11 = 0;
  }
  ExReleaseResourceAndLeaveCriticalRegion(AfdGlobalData);
  return v11;
}

```

## disassembly

```asm
0x14005c7b0  mov     [rsp+arg_0], rbx
0x14005c7b5  push    rdi
0x14005c7b6  sub     rsp, 20h
0x14005c7ba  mov     rax, [rsp+28h+arg_38]
0x14005c7bf  mov     qword ptr [rax], 0
0x14005c7c6  mov     eax, 0AFDh
0x14005c7cb  mov     rdi, [rcx+18h]
0x14005c7cf  cmp     [rdi], ax
0x14005c7d2  jnz     loc_14005C85C
0x14005c7d8  mov     rbx, [rdi+30h]
0x14005c7dc  call    cs:__imp_IoGetCurrentProcess
0x14005c7e3  nop     dword ptr [rax+rax+00h]
0x14005c7e8  cmp     rbx, rax
0x14005c7eb  jnz     short loc_14005C85C
0x14005c7ed  cmp     byte ptr [rdi+3], 0
0x14005c7f1  jnz     short loc_14005C7FA
0x14005c7f3  mov     eax, 0C0000022h
0x14005c7f8  jmp     short loc_14005C861
0x14005c7fa  mov     rcx, cs:AfdGlobalData; Resource
0x14005c801  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x14005c808  nop     dword ptr [rax+rax+00h]
0x14005c80d  mov     rax, cs:AfdSanServiceHelper
0x14005c814  test    rax, rax
0x14005c817  jnz     short loc_14005C837
0x14005c819  mov     cs:AfdSanServiceHelper, rdi
0x14005c820  call    cs:__imp_PsGetCurrentProcessId
0x14005c827  nop     dword ptr [rax+rax+00h]
0x14005c82c  mov     cs:AfdSanServicePid, rax
0x14005c833  xor     ebx, ebx
0x14005c835  jmp     short loc_14005C845
0x14005c837  sub     rax, rdi
0x14005c83a  neg     rax
0x14005c83d  sbb     ebx, ebx
0x14005c83f  and     ebx, 0C000020Ah
0x14005c845  mov     rcx, cs:AfdGlobalData; Resource
0x14005c84c  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x14005c853  nop     dword ptr [rax+rax+00h]
0x14005c858  mov     eax, ebx
0x14005c85a  jmp     short loc_14005C861
0x14005c85c  mov     eax, 0C0000008h
0x14005c861  mov     rbx, [rsp+28h+arg_0]
0x14005c866  add     rsp, 20h
0x14005c86a  pop     rdi
0x14005c86b  retn
```
