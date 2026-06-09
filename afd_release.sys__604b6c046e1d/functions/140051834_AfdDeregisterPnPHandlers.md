# AfdDeregisterPnPHandlers

- ea: `0x140051834`
- end: `0x1400519fb`
- name: `AfdDeregisterPnPHandlers`
- size: `455`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140048360`
- `0x140051a90`

## callees

- `0x1400036ac`
- `0x140051834`

## import_xrefs

- `ntoskrnl!KeResetEvent` at `0x14005189c`
- `ntoskrnl!KeResetEvent` at `0x14005189c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400518b3`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400519b2`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400518b3`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400519b2`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005191b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140051930`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005191b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140051930`
- `ntoskrnl!KeSetEvent` at `0x1400519d0`
- `ntoskrnl!KeSetEvent` at `0x1400519d0`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400519e3`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400519e3`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140051849`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140051849`
- `ntoskrnl!ExFreePoolWithTag` at `0x140051966`
- `ntoskrnl!ExFreePoolWithTag` at `0x140051966`
- `TDI!TdiDeregisterPnPHandlers` at `0x1400518c7`
- `TDI!TdiDeregisterPnPHandlers` at `0x1400518c7`
- `NETIO!NsiDeregisterChangeNotification` at `0x1400518e9`
- `NETIO!NsiDeregisterChangeNotification` at `0x140051906`
- `NETIO!NsiDeregisterChangeNotification` at `0x1400518e9`
- `NETIO!NsiDeregisterChangeNotification` at `0x140051906`

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
0x140051834  push    rbx
0x140051836  push    rbp
0x140051837  push    rsi
0x140051838  push    rdi
0x140051839  push    r14
0x14005183b  sub     rsp, 20h
0x14005183f  mov     rbx, rcx
0x140051842  mov     rcx, cs:AfdGlobalData; Resource
0x140051849  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x140051850  nop     dword ptr [rax+rax+00h]
0x140051855  cmp     byte ptr [rbx+58h], 0
0x140051859  jnz     loc_1400519DC
0x14005185f  mov     rdi, [rbx+38h]
0x140051863  test    rdi, rdi
0x140051866  jnz     short loc_140051878
0x140051868  cmp     [rbx+20h], rdi
0x14005186c  jnz     short loc_140051878
0x14005186e  cmp     [rbx+30h], rdi
0x140051872  jz      loc_1400519DC
0x140051878  mov     rsi, [rbx+20h]
0x14005187c  lea     rcx, [rbx+40h]; Event
0x140051880  mov     rbp, [rbx+30h]
0x140051884  mov     qword ptr [rbx+20h], 0
0x14005188c  mov     qword ptr [rbx+30h], 0
0x140051894  mov     qword ptr [rbx+38h], 0
0x14005189c  call    cs:__imp_KeResetEvent
0x1400518a3  nop     dword ptr [rax+rax+00h]
0x1400518a8  mov     rcx, cs:AfdGlobalData; Resource
0x1400518af  mov     byte ptr [rbx+58h], 1
0x1400518b3  call    cs:__imp_ExReleaseResourceLite
0x1400518ba  nop     dword ptr [rax+rax+00h]
0x1400518bf  test    rdi, rdi
0x1400518c2  jz      short loc_1400518D3
0x1400518c4  mov     rcx, rdi; BindingHandle
0x1400518c7  call    cs:__imp_TdiDeregisterPnPHandlers
0x1400518ce  nop     dword ptr [rax+rax+00h]
0x1400518d3  mov     edi, 0Ah
0x1400518d8  test    rsi, rsi
0x1400518db  jz      short loc_1400518F5
0x1400518dd  mov     r8, rsi
0x1400518e0  lea     rcx, NPI_MS_IPV4_MODULEID
0x1400518e7  mov     edx, edi
0x1400518e9  call    cs:__imp_NsiDeregisterChangeNotification
0x1400518f0  nop     dword ptr [rax+rax+00h]
0x1400518f5  test    rbp, rbp
0x1400518f8  jz      short loc_140051912
0x1400518fa  mov     r8, rbp
0x1400518fd  lea     rcx, NPI_MS_IPV6_MODULEID
0x140051904  mov     edx, edi
0x140051906  call    cs:__imp_NsiDeregisterChangeNotification
0x14005190d  nop     dword ptr [rax+rax+00h]
0x140051912  mov     rcx, cs:AfdGlobalData; Resource
0x140051919  mov     dl, 1; Wait
0x14005191b  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140051922  nop     dword ptr [rax+rax+00h]
0x140051927  mov     rcx, [rbx+0C0h]; Resource
0x14005192e  mov     dl, 1; Wait
0x140051930  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140051937  nop     dword ptr [rax+rax+00h]
0x14005193c  lea     rdi, [rbx+0A8h]
0x140051943  mov     rcx, [rdi]; P
0x140051946  cmp     rcx, rdi
0x140051949  jz      short loc_14005197B
0x14005194b  cmp     [rcx+8], rdi
0x14005194f  jnz     short loc_140051974
0x140051951  mov     rax, [rcx]
0x140051954  cmp     [rax+8], rcx
0x140051958  jnz     short loc_140051974
0x14005195a  mov     [rdi], rax
0x14005195d  mov     edx, 74646641h; Tag
0x140051962  mov     [rax+8], rdi
0x140051966  call    cs:__imp_ExFreePoolWithTag
0x14005196d  nop     dword ptr [rax+rax+00h]
0x140051972  jmp     short loc_140051943
0x140051974  mov     ecx, 3
0x140051979  int     29h; Win8: RtlFailFast(ecx)
0x14005197b  lea     rax, AfdEndpointListHead
0x140051982  cmp     cs:AfdEndpointListHead, rax
0x140051989  jnz     short loc_140051994
0x14005198b  cmp     cs:AfdWskInitialized, 0
0x140051992  jz      short loc_1400519A1
0x140051994  xor     edx, edx
0x140051996  xor     r8d, r8d
0x140051999  mov     rcx, rbx
0x14005199c  call    AfdProcessAddressChangeList
0x1400519a1  mov     rcx, [rbx+0C0h]; Resource
0x1400519a8  mov     dword ptr [rbx+0B8h], 0
0x1400519b2  call    cs:__imp_ExReleaseResourceLite
0x1400519b9  nop     dword ptr [rax+rax+00h]
0x1400519be  movsx   edx, cs:AfdPriorityBoost; Increment
0x1400519c5  lea     rcx, [rbx+40h]; Event
0x1400519c9  xor     r8d, r8d; Wait
0x1400519cc  mov     byte ptr [rbx+58h], 0
0x1400519d0  call    cs:__imp_KeSetEvent
0x1400519d7  nop     dword ptr [rax+rax+00h]
0x1400519dc  mov     rcx, cs:AfdGlobalData; Resource
0x1400519e3  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x1400519ea  nop     dword ptr [rax+rax+00h]
0x1400519ef  add     rsp, 20h
0x1400519f3  pop     r14
0x1400519f5  pop     rdi
0x1400519f6  pop     rsi
0x1400519f7  pop     rbp
0x1400519f8  pop     rbx
0x1400519f9  retn
```
