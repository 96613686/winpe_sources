# std::_Ref_count_obj2<CMidiSessionTracker>::_Destroy(void)

- ea: `0x140011850`
- end: `0x14001189f`
- name: `?_Destroy@?$_Ref_count_obj2@VCMidiSessionTracker@@@std@@EEAAXXZ`
- size: `79`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x14000dafc`
- `0x140011850`
- `0x14005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140011868`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140011868`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_obj2<CMidiSessionTracker>::_Destroy(__int64 a1)
{
  __int64 result; // rax
  volatile signed __int32 *v3; // rcx

  *(_QWORD *)(a1 + 16) = &CMidiSessionTracker::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 64));
  result = std::vector<MidiSessionEntry>::~vector<MidiSessionEntry>(a1 + 40);
  v3 = *(volatile signed __int32 **)(a1 + 32);
  if ( v3 )
  {
    result = (unsigned int)_InterlockedExchangeAdd(v3 + 3, 0xFFFFFFFF);
    if ( (_DWORD)result == 1 )
      return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v3 + 8LL))(v3);
  }
  return result;
}

```

## disassembly

```asm
0x140011850  push    rbx
0x140011852  sub     rsp, 20h
0x140011856  lea     rax, ??_7CMidiSessionTracker@@6B@; const CMidiSessionTracker::`vftable'
0x14001185d  mov     rbx, rcx
0x140011860  mov     [rcx+10h], rax
0x140011864  add     rcx, 40h ; '@'; lpCriticalSection
0x140011868  call    cs:__imp_DeleteCriticalSection
0x14001186e  lea     rcx, [rbx+28h]
0x140011872  call    ??1?$vector@UMidiSessionEntry@@V?$allocator@UMidiSessionEntry@@@std@@@std@@QEAA@XZ; std::vector<MidiSessionEntry>::~vector<MidiSessionEntry>(void)
0x140011877  mov     rcx, [rbx+20h]
0x14001187b  test    rcx, rcx
0x14001187e  jz      short loc_140011899
0x140011880  or      eax, 0FFFFFFFFh
0x140011883  lock xadd [rcx+0Ch], eax
0x140011888  cmp     eax, 1
0x14001188b  jnz     short loc_140011899
0x14001188d  mov     rax, [rcx]
0x140011890  mov     rax, [rax+8]
0x140011894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011899  add     rsp, 20h
0x14001189d  pop     rbx
0x14001189e  retn
```
