# MidiPortsRemoveByDeviceInterfaceId(ushort const *)

- ea: `0x180022d38`
- end: `0x180022ddd`
- name: `?MidiPortsRemoveByDeviceInterfaceId@@YAXPEBG@Z`
- size: `165`
- prototype: `void __fastcall(LPCWCH lpString2)`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002c798`
- `0x180043b50`
- `0x180047bf8`
- `0x180049424`
- `0x180056a88`

## callees

- `0x180022d38`
- `0x180022e08`
- `0x180037558`
- `0x180052844`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022d76`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022d76`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022da9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022da9`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x180022dcd`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x180022dcd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall MidiPortsRemoveByDeviceInterfaceId(LPCWCH lpString2)
{
  __int64 v2; // rcx
  _QWORD *v3; // rbx
  _QWORD *v4; // rbp
  __int64 v5; // rdi
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+30h] [rbp-38h] BYREF
  char v7; // [rsp+38h] [rbp-30h]

  lpCriticalSection = &MidiPortsLock;
  v7 = 0;
  ATL::CCritSecLock::Lock((ATL::CCritSecLock *)&lpCriticalSection);
  v3 = (_QWORD *)MidiPorts;
  while ( v3 )
  {
    v4 = v3;
    v5 = v3[2];
    v3 = (_QWORD *)*v3;
    if ( !lpString2 || CompareStringOrdinal(*(LPCWCH *)v5, -1, lpString2, -1, 1) == 2 )
    {
      *(_DWORD *)(v5 + 8) = 0;
      if ( *(_DWORD *)(v5 + 16) == 2 )
      {
        ATL::CAtlList<_MIDIPORT *,ATL::CElementTraits<_MIDIPORT *>>::RemoveAt(v2, v4);
        SwDeviceClose(*(_QWORD *)(v5 + 24));
        MidiPortDeepFree((LPVOID *)v5);
      }
    }
  }
  if ( v7 )
    LeaveCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x180022d38  push    rbx
0x180022d3a  push    rbp
0x180022d3b  push    rsi
0x180022d3c  push    rdi
0x180022d3d  sub     rsp, 48h
0x180022d41  mov     rsi, rcx
0x180022d44  lea     rax, ?MidiPortsLock@@3VCCriticalSection@ATL@@A; ATL::CCriticalSection MidiPortsLock
0x180022d4b  mov     [rsp+68h+lpCriticalSection], rax
0x180022d50  mov     [rsp+68h+var_30], 0
0x180022d55  lea     rcx, [rsp+68h+lpCriticalSection]; this
0x180022d5a  call    ?Lock@CCritSecLock@ATL@@QEAAXXZ; ATL::CCritSecLock::Lock(void)
0x180022d5f  mov     rbx, cs:?MidiPorts@@3V?$CAtlList@PEAU_MIDIPORT@@V?$CElementTraits@PEAU_MIDIPORT@@@ATL@@@ATL@@A; ATL::CAtlList<_MIDIPORT *,ATL::CElementTraits<_MIDIPORT *>> MidiPorts
0x180022d66  test    rbx, rbx
0x180022d69  jnz     short loc_180022D85
0x180022d6b  cmp     [rsp+68h+var_30], bl
0x180022d6f  jz      short loc_180022D7C
0x180022d71  mov     rcx, [rsp+68h+lpCriticalSection]; lpCriticalSection
0x180022d76  call    cs:__imp_LeaveCriticalSection
0x180022d7c  add     rsp, 48h
0x180022d80  pop     rdi
0x180022d81  pop     rsi
0x180022d82  pop     rbp
0x180022d83  pop     rbx
0x180022d84  retn
0x180022d85  mov     rbp, rbx
0x180022d88  mov     rdi, [rbx+10h]
0x180022d8c  mov     rbx, [rbx]
0x180022d8f  test    rsi, rsi
0x180022d92  jz      short loc_180022DB4
0x180022d94  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x180022d9c  or      r9d, 0FFFFFFFFh; cchCount2
0x180022da0  mov     r8, rsi; lpString2
0x180022da3  or      edx, r9d; cchCount1
0x180022da6  mov     rcx, [rdi]; lpString1
0x180022da9  call    cs:__imp_CompareStringOrdinal
0x180022daf  cmp     eax, 2
0x180022db2  jnz     short loc_180022D66
0x180022db4  mov     dword ptr [rdi+8], 0
0x180022dbb  cmp     dword ptr [rdi+10h], 2
0x180022dbf  jnz     short loc_180022D66
0x180022dc1  mov     rdx, rbp
0x180022dc4  call    ?RemoveAt@?$CAtlList@PEAU_MIDIPORT@@V?$CElementTraits@PEAU_MIDIPORT@@@ATL@@@ATL@@QEAAXPEAU__POSITION@@@Z; ATL::CAtlList<_MIDIPORT *,ATL::CElementTraits<_MIDIPORT *>>::RemoveAt(__POSITION *)
0x180022dc9  mov     rcx, [rdi+18h]
0x180022dcd  call    cs:__imp_SwDeviceClose
0x180022dd3  mov     rcx, rdi; pv
0x180022dd6  call    ?MidiPortDeepFree@@YAXPEAU_MIDIPORT@@@Z; MidiPortDeepFree(_MIDIPORT *)
0x180022ddb  jmp     short loc_180022D66
```
