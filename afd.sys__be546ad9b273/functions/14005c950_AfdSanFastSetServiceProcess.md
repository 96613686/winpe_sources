# AfdSanFastSetServiceProcess

- ea: `0x14005c950`
- end: `0x14005ca0d`
- name: `AfdSanFastSetServiceProcess`
- size: `189`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int, int, int, _QWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, service_task`

## callees

- `0x14005c950`

## import_xrefs

- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14005c9ec`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14005c9ec`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x14005c9a1`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x14005c9a1`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14005c9c0`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14005c9c0`
- `ntoskrnl!IoGetCurrentProcess` at `0x14005c97c`
- `ntoskrnl!IoGetCurrentProcess` at `0x14005c97c`

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
0x14005c950  mov     [rsp+arg_0], rbx
0x14005c955  push    rdi
0x14005c956  sub     rsp, 20h
0x14005c95a  mov     rax, [rsp+28h+arg_38]
0x14005c95f  mov     qword ptr [rax], 0
0x14005c966  mov     eax, 0AFDh
0x14005c96b  mov     rdi, [rcx+18h]
0x14005c96f  cmp     [rdi], ax
0x14005c972  jnz     loc_14005C9FC
0x14005c978  mov     rbx, [rdi+30h]
0x14005c97c  call    cs:__imp_IoGetCurrentProcess
0x14005c983  nop     dword ptr [rax+rax+00h]
0x14005c988  cmp     rbx, rax
0x14005c98b  jnz     short loc_14005C9FC
0x14005c98d  cmp     byte ptr [rdi+3], 0
0x14005c991  jnz     short loc_14005C99A
0x14005c993  mov     eax, 0C0000022h
0x14005c998  jmp     short loc_14005CA01
0x14005c99a  mov     rcx, cs:AfdGlobalData; Resource
0x14005c9a1  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x14005c9a8  nop     dword ptr [rax+rax+00h]
0x14005c9ad  mov     rax, cs:AfdSanServiceHelper
0x14005c9b4  test    rax, rax
0x14005c9b7  jnz     short loc_14005C9D7
0x14005c9b9  mov     cs:AfdSanServiceHelper, rdi
0x14005c9c0  call    cs:__imp_PsGetCurrentProcessId
0x14005c9c7  nop     dword ptr [rax+rax+00h]
0x14005c9cc  mov     cs:AfdSanServicePid, rax
0x14005c9d3  xor     ebx, ebx
0x14005c9d5  jmp     short loc_14005C9E5
0x14005c9d7  sub     rax, rdi
0x14005c9da  neg     rax
0x14005c9dd  sbb     ebx, ebx
0x14005c9df  and     ebx, 0C000020Ah
0x14005c9e5  mov     rcx, cs:AfdGlobalData; Resource
0x14005c9ec  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x14005c9f3  nop     dword ptr [rax+rax+00h]
0x14005c9f8  mov     eax, ebx
0x14005c9fa  jmp     short loc_14005CA01
0x14005c9fc  mov     eax, 0C0000008h
0x14005ca01  mov     rbx, [rsp+28h+arg_0]
0x14005ca06  add     rsp, 20h
0x14005ca0a  pop     rdi
0x14005ca0b  retn
```
