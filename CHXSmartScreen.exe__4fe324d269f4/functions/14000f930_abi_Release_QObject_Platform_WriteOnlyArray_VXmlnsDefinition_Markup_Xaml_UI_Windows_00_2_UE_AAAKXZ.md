# ?__abi_Release@?QObject@Platform@@?$WriteOnlyArray@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@2@UE$AAAKXZ

- ea: `0x14000f930`
- end: `0x14000f9bd`
- name: `?__abi_Release@?QObject@Platform@@?$WriteOnlyArray@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@2@UE$AAAKXZ`
- size: `141`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000f9d0`
- `0x14000f9e0`
- `0x14000f9f0`
- `0x14000fa00`

## callees

- `0x14000614c`
- `0x1400086b0`
- `0x14000f930`
- `0x140035010`

## import_xrefs

- `wincorlib!?ReleaseTarget@ControlBlock@Details@Platform@@AEAAXXZ` at `0x14000f979`
- `wincorlib!?ReleaseTarget@ControlBlock@Details@Platform@@AEAAXXZ` at `0x14000f979`
- `wincorlib!?AlignedFree@Heap@Details@Platform@@SAXPEAX@Z` at `0x14000f995`
- `wincorlib!?AlignedFree@Heap@Details@Platform@@SAXPEAX@Z` at `0x14000f995`
- `wincorlib!?Free@Heap@Details@Platform@@SAXPEAX@Z` at `0x14000f99d`
- `wincorlib!?Free@Heap@Details@Platform@@SAXPEAX@Z` at `0x14000f99d`

## pseudocode

```c
__int64 __fastcall ___abi_Release__QObject_Platform____WriteOnlyArray_VXmlnsDefinition_Markup_Xaml_UI_Windows___00_2_UE_AAAKXZ(
        __int64 a1)
{
  Platform::Details::ControlBlock **v1; // rsi
  unsigned int v3; // edi
  __int64 v4; // rcx
  int v5; // eax
  Platform::Details::ControlBlock *v6; // rbx

  v1 = (Platform::Details::ControlBlock **)(a1 + 56);
  v3 = __abi_FTMWeakRefData::Decrement(a1 + 56);
  if ( !v3 )
  {
    v4 = (a1 + 8) & -(__int64)(a1 != 0);
    if ( v4 )
    {
      v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 48LL))(v4);
      if ( v5 < 0 )
        __abi_WinRTraiseException(v5);
    }
    v6 = *v1;
    Platform::Details::ControlBlock::ReleaseTarget(*v1);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v6 + 2, 0xFFFFFFFF) == 1 )
    {
      if ( *((_BYTE *)v6 + 25) )
        Platform::Details::Heap::AlignedFree(v6);
      else
        Platform::Details::Heap::Free(v6);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x14000f930  mov     [rsp+arg_8], rbx
0x14000f935  mov     [rsp+arg_10], rsi
0x14000f93a  push    rdi
0x14000f93b  sub     rsp, 20h
0x14000f93f  lea     rsi, [rcx+38h]
0x14000f943  mov     rbx, rcx
0x14000f946  mov     rcx, rsi
0x14000f949  call    ?Decrement@__abi_FTMWeakRefData@@QECAKXZ; __abi_FTMWeakRefData::Decrement(void)
0x14000f94e  mov     edi, eax
0x14000f950  test    eax, eax
0x14000f952  jnz     short loc_14000F9A3
0x14000f954  lea     rdx, [rbx+8]
0x14000f958  neg     rbx
0x14000f95b  sbb     rcx, rcx
0x14000f95e  and     rcx, rdx
0x14000f961  jz      short loc_14000F973
0x14000f963  mov     rdx, [rcx]
0x14000f966  mov     rax, [rdx+30h]
0x14000f96a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f96f  test    eax, eax
0x14000f971  js      short loc_14000F9B5
0x14000f973  mov     rbx, [rsi]
0x14000f976  mov     rcx, rbx
0x14000f979  call    cs:__imp_?ReleaseTarget@ControlBlock@Details@Platform@@AEAAXXZ; Platform::Details::ControlBlock::ReleaseTarget(void)
0x14000f97f  or      eax, 0FFFFFFFFh
0x14000f982  lock xadd [rbx+8], eax
0x14000f987  cmp     eax, 1
0x14000f98a  jnz     short loc_14000F9A3
0x14000f98c  cmp     byte ptr [rbx+19h], 0
0x14000f990  mov     rcx, rbx
0x14000f993  jz      short loc_14000F99D
0x14000f995  call    cs:__imp_?AlignedFree@Heap@Details@Platform@@SAXPEAX@Z; Platform::Details::Heap::AlignedFree(void *)
0x14000f99b  jmp     short loc_14000F9A3
0x14000f99d  call    cs:__imp_?Free@Heap@Details@Platform@@SAXPEAX@Z; Platform::Details::Heap::Free(void *)
0x14000f9a3  mov     rbx, [rsp+28h+arg_8]
0x14000f9a8  mov     eax, edi
0x14000f9aa  mov     rsi, [rsp+28h+arg_10]
0x14000f9af  add     rsp, 20h
0x14000f9b3  pop     rdi
0x14000f9b4  retn
0x14000f9b5  mov     ecx, eax; int
0x14000f9b7  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
```
