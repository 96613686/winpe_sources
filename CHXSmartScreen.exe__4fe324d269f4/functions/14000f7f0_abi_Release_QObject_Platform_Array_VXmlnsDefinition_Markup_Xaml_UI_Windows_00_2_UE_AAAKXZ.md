# ?__abi_Release@?QObject@Platform@@?$Array@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@2@UE$AAAKXZ

- ea: `0x14000f7f0`
- end: `0x14000f87d`
- name: `?__abi_Release@?QObject@Platform@@?$Array@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@2@UE$AAAKXZ`
- size: `141`
- prototype: ``
- caller_count: `10`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000f890`
- `0x14000f8a0`
- `0x14000f8b0`
- `0x14000f8c0`
- `0x14000f8d0`
- `0x14000f8e0`
- `0x14000f8f0`
- `0x14000f900`
- `0x14000f910`
- `0x14000f920`

## callees

- `0x14000614c`
- `0x1400086b0`
- `0x14000f7f0`
- `0x140035010`

## import_xrefs

- `wincorlib!?ReleaseTarget@ControlBlock@Details@Platform@@AEAAXXZ` at `0x14000f839`
- `wincorlib!?ReleaseTarget@ControlBlock@Details@Platform@@AEAAXXZ` at `0x14000f839`
- `wincorlib!?AlignedFree@Heap@Details@Platform@@SAXPEAX@Z` at `0x14000f855`
- `wincorlib!?AlignedFree@Heap@Details@Platform@@SAXPEAX@Z` at `0x14000f855`
- `wincorlib!?Free@Heap@Details@Platform@@SAXPEAX@Z` at `0x14000f85d`
- `wincorlib!?Free@Heap@Details@Platform@@SAXPEAX@Z` at `0x14000f85d`

## pseudocode

```c
__int64 __fastcall ___abi_Release__QObject_Platform____Array_VXmlnsDefinition_Markup_Xaml_UI_Windows___00_2_UE_AAAKXZ(
        __int64 a1)
{
  Platform::Details::ControlBlock **v1; // rsi
  unsigned int v3; // edi
  __int64 v4; // rcx
  int v5; // eax
  Platform::Details::ControlBlock *v6; // rbx

  v1 = (Platform::Details::ControlBlock **)(a1 + 88);
  v3 = __abi_FTMWeakRefData::Decrement(a1 + 88);
  if ( !v3 )
  {
    v4 = (a1 + 24) & -(__int64)(a1 != 0);
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
0x14000f7f0  mov     [rsp+arg_8], rbx
0x14000f7f5  mov     [rsp+arg_10], rsi
0x14000f7fa  push    rdi
0x14000f7fb  sub     rsp, 20h
0x14000f7ff  lea     rsi, [rcx+58h]
0x14000f803  mov     rbx, rcx
0x14000f806  mov     rcx, rsi
0x14000f809  call    ?Decrement@__abi_FTMWeakRefData@@QECAKXZ; __abi_FTMWeakRefData::Decrement(void)
0x14000f80e  mov     edi, eax
0x14000f810  test    eax, eax
0x14000f812  jnz     short loc_14000F863
0x14000f814  lea     rdx, [rbx+18h]
0x14000f818  neg     rbx
0x14000f81b  sbb     rcx, rcx
0x14000f81e  and     rcx, rdx
0x14000f821  jz      short loc_14000F833
0x14000f823  mov     rdx, [rcx]
0x14000f826  mov     rax, [rdx+30h]
0x14000f82a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f82f  test    eax, eax
0x14000f831  js      short loc_14000F875
0x14000f833  mov     rbx, [rsi]
0x14000f836  mov     rcx, rbx
0x14000f839  call    cs:__imp_?ReleaseTarget@ControlBlock@Details@Platform@@AEAAXXZ; Platform::Details::ControlBlock::ReleaseTarget(void)
0x14000f83f  or      eax, 0FFFFFFFFh
0x14000f842  lock xadd [rbx+8], eax
0x14000f847  cmp     eax, 1
0x14000f84a  jnz     short loc_14000F863
0x14000f84c  cmp     byte ptr [rbx+19h], 0
0x14000f850  mov     rcx, rbx
0x14000f853  jz      short loc_14000F85D
0x14000f855  call    cs:__imp_?AlignedFree@Heap@Details@Platform@@SAXPEAX@Z; Platform::Details::Heap::AlignedFree(void *)
0x14000f85b  jmp     short loc_14000F863
0x14000f85d  call    cs:__imp_?Free@Heap@Details@Platform@@SAXPEAX@Z; Platform::Details::Heap::Free(void *)
0x14000f863  mov     rbx, [rsp+28h+arg_8]
0x14000f868  mov     eax, edi
0x14000f86a  mov     rsi, [rsp+28h+arg_10]
0x14000f86f  add     rsp, 20h
0x14000f873  pop     rdi
0x14000f874  retn
0x14000f875  mov     ecx, eax; int
0x14000f877  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
```
