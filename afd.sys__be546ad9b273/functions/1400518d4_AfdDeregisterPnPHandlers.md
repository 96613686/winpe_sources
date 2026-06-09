# AfdDeregisterPnPHandlers

- ea: `0x1400518d4`
- end: `0x140051a9b`
- name: `AfdDeregisterPnPHandlers`
- size: `455`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1400483e0`
- `0x140051b30`

## callees

- `0x1400036ac`
- `0x1400518d4`

## import_xrefs

- `ntoskrnl!KeResetEvent` at `0x14005193c`
- `ntoskrnl!KeResetEvent` at `0x14005193c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140051953`
- `ntoskrnl!ExReleaseResourceLite` at `0x140051a52`
- `ntoskrnl!ExReleaseResourceLite` at `0x140051953`
- `ntoskrnl!ExReleaseResourceLite` at `0x140051a52`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400519bb`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400519d0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400519bb`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400519d0`
- `ntoskrnl!KeSetEvent` at `0x140051a70`
- `ntoskrnl!KeSetEvent` at `0x140051a70`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140051a83`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140051a83`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x1400518e9`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x1400518e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140051a06`
- `ntoskrnl!ExFreePoolWithTag` at `0x140051a06`
- `TDI!TdiDeregisterPnPHandlers` at `0x140051967`
- `TDI!TdiDeregisterPnPHandlers` at `0x140051967`
- `NETIO!NsiDeregisterChangeNotification` at `0x140051989`
- `NETIO!NsiDeregisterChangeNotification` at `0x1400519a6`
- `NETIO!NsiDeregisterChangeNotification` at `0x140051989`
- `NETIO!NsiDeregisterChangeNotification` at `0x1400519a6`

## pseudocode

```c
void __fastcall AfdDeregisterPnPHandlers(__int64 a1)
{
  void *v2; // rdi
  __int64 v3; // rsi
  __int64 v4; // rbp
  struct _ERESOURCE *v5; // rcx
  _QWORD **v6; // rdi
  _QWORD *v7; // rcx
  _QWORD *v8; // rax
  struct _ERESOURCE *v9; // rcx
  KPRIORITY v10; // edx

  ExEnterCriticalRegionAndAcquireResourceExclusive(AfdGlobalData);
  if ( !*(_BYTE *)(a1 + 88) )
  {
    v2 = *(void **)(a1 + 56);
    if ( v2 || *(_QWORD *)(a1 + 32) || *(_QWORD *)(a1 + 48) )
    {
      v3 = *(_QWORD *)(a1 + 32);
      v4 = *(_QWORD *)(a1 + 48);
      *(_QWORD *)(a1 + 32) = 0;
      *(_QWORD *)(a1 + 48) = 0;
      *(_QWORD *)(a1 + 56) = 0;
      KeResetEvent((PRKEVENT)(a1 + 64));
      v5 = AfdGlobalData;
      *(_BYTE *)(a1 + 88) = 1;
      ExReleaseResourceLite(v5);
      if ( v2 )
        TdiDeregisterPnPHandlers(v2);
      if ( v3 )
        NsiDeregisterChangeNotification(&NPI_MS_IPV4_MODULEID, 10);
      if ( v4 )
        NsiDeregisterChangeNotification(&NPI_MS_IPV6_MODULEID, 10);
      ExAcquireResourceExclusiveLite(AfdGlobalData, 1u);
      ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 192), 1u);
      v6 = (_QWORD **)(a1 + 168);
      while ( 1 )
      {
        v7 = *v6;
        if ( *v6 == v6 )
          break;
        if ( (_QWORD **)v7[1] != v6 || (v8 = (_QWORD *)*v7, *(_QWORD **)(*v7 + 8LL) != v7) )
          __fastfail(3u);
        *v6 = v8;
        v8[1] = v6;
        ExFreePoolWithTag(v7, 0x74646641u);
      }
      if ( (__int64 *)AfdEndpointListHead != &AfdEndpointListHead || AfdWskInitialized )
        AfdProcessAddressChangeList(a1, 0, 0);
      v9 = *(struct _ERESOURCE **)(a1 + 192);
      *(_DWORD *)(a1 + 184) = 0;
      ExReleaseResourceLite(v9);
      v10 = AfdPriorityBoost;
      *(_BYTE *)(a1 + 88) = 0;
      KeSetEvent((PRKEVENT)(a1 + 64), v10, 0);
    }
  }
  ExReleaseResourceAndLeaveCriticalRegion(AfdGlobalData);
}

```

## disassembly

```asm
0x1400518d4  push    rbx
0x1400518d6  push    rbp
0x1400518d7  push    rsi
0x1400518d8  push    rdi
0x1400518d9  push    r14
0x1400518db  sub     rsp, 20h
0x1400518df  mov     rbx, rcx
0x1400518e2  mov     rcx, cs:AfdGlobalData; Resource
0x1400518e9  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x1400518f0  nop     dword ptr [rax+rax+00h]
0x1400518f5  cmp     byte ptr [rbx+58h], 0
0x1400518f9  jnz     loc_140051A7C
0x1400518ff  mov     rdi, [rbx+38h]
0x140051903  test    rdi, rdi
0x140051906  jnz     short loc_140051918
0x140051908  cmp     [rbx+20h], rdi
0x14005190c  jnz     short loc_140051918
0x14005190e  cmp     [rbx+30h], rdi
0x140051912  jz      loc_140051A7C
0x140051918  mov     rsi, [rbx+20h]
0x14005191c  lea     rcx, [rbx+40h]; Event
0x140051920  mov     rbp, [rbx+30h]
0x140051924  mov     qword ptr [rbx+20h], 0
0x14005192c  mov     qword ptr [rbx+30h], 0
0x140051934  mov     qword ptr [rbx+38h], 0
0x14005193c  call    cs:__imp_KeResetEvent
0x140051943  nop     dword ptr [rax+rax+00h]
0x140051948  mov     rcx, cs:AfdGlobalData; Resource
0x14005194f  mov     byte ptr [rbx+58h], 1
0x140051953  call    cs:__imp_ExReleaseResourceLite
0x14005195a  nop     dword ptr [rax+rax+00h]
0x14005195f  test    rdi, rdi
0x140051962  jz      short loc_140051973
0x140051964  mov     rcx, rdi; BindingHandle
0x140051967  call    cs:__imp_TdiDeregisterPnPHandlers
0x14005196e  nop     dword ptr [rax+rax+00h]
0x140051973  mov     edi, 0Ah
0x140051978  test    rsi, rsi
0x14005197b  jz      short loc_140051995
0x14005197d  mov     r8, rsi
0x140051980  lea     rcx, NPI_MS_IPV4_MODULEID
0x140051987  mov     edx, edi
0x140051989  call    cs:__imp_NsiDeregisterChangeNotification
0x140051990  nop     dword ptr [rax+rax+00h]
0x140051995  test    rbp, rbp
0x140051998  jz      short loc_1400519B2
0x14005199a  mov     r8, rbp
0x14005199d  lea     rcx, NPI_MS_IPV6_MODULEID
0x1400519a4  mov     edx, edi
0x1400519a6  call    cs:__imp_NsiDeregisterChangeNotification
0x1400519ad  nop     dword ptr [rax+rax+00h]
0x1400519b2  mov     rcx, cs:AfdGlobalData; Resource
0x1400519b9  mov     dl, 1; Wait
0x1400519bb  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400519c2  nop     dword ptr [rax+rax+00h]
0x1400519c7  mov     rcx, [rbx+0C0h]; Resource
0x1400519ce  mov     dl, 1; Wait
0x1400519d0  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400519d7  nop     dword ptr [rax+rax+00h]
0x1400519dc  lea     rdi, [rbx+0A8h]
0x1400519e3  mov     rcx, [rdi]; P
0x1400519e6  cmp     rcx, rdi
0x1400519e9  jz      short loc_140051A1B
0x1400519eb  cmp     [rcx+8], rdi
0x1400519ef  jnz     short loc_140051A14
0x1400519f1  mov     rax, [rcx]
0x1400519f4  cmp     [rax+8], rcx
0x1400519f8  jnz     short loc_140051A14
0x1400519fa  mov     [rdi], rax
0x1400519fd  mov     edx, 74646641h; Tag
0x140051a02  mov     [rax+8], rdi
0x140051a06  call    cs:__imp_ExFreePoolWithTag
0x140051a0d  nop     dword ptr [rax+rax+00h]
0x140051a12  jmp     short loc_1400519E3
0x140051a14  mov     ecx, 3
0x140051a19  int     29h; Win8: RtlFailFast(ecx)
0x140051a1b  lea     rax, AfdEndpointListHead
0x140051a22  cmp     cs:AfdEndpointListHead, rax
0x140051a29  jnz     short loc_140051A34
0x140051a2b  cmp     cs:AfdWskInitialized, 0
0x140051a32  jz      short loc_140051A41
0x140051a34  xor     edx, edx
0x140051a36  xor     r8d, r8d
0x140051a39  mov     rcx, rbx
0x140051a3c  call    AfdProcessAddressChangeList
0x140051a41  mov     rcx, [rbx+0C0h]; Resource
0x140051a48  mov     dword ptr [rbx+0B8h], 0
0x140051a52  call    cs:__imp_ExReleaseResourceLite
0x140051a59  nop     dword ptr [rax+rax+00h]
0x140051a5e  movsx   edx, cs:AfdPriorityBoost; Increment
0x140051a65  lea     rcx, [rbx+40h]; Event
0x140051a69  xor     r8d, r8d; Wait
0x140051a6c  mov     byte ptr [rbx+58h], 0
0x140051a70  call    cs:__imp_KeSetEvent
0x140051a77  nop     dword ptr [rax+rax+00h]
0x140051a7c  mov     rcx, cs:AfdGlobalData; Resource
0x140051a83  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x140051a8a  nop     dword ptr [rax+rax+00h]
0x140051a8f  add     rsp, 20h
0x140051a93  pop     r14
0x140051a95  pop     rdi
0x140051a96  pop     rsi
0x140051a97  pop     rbp
0x140051a98  pop     rbx
0x140051a99  retn
```
