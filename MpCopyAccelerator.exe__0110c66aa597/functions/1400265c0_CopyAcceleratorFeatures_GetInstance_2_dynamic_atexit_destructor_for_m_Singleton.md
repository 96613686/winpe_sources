# _CopyAcceleratorFeatures::GetInstance_::_2_::_dynamic_atexit_destructor_for__m_Singleton__

- ea: `0x1400265c0`
- end: `0x1400265db`
- name: `_CopyAcceleratorFeatures::GetInstance_::_2_::_dynamic_atexit_destructor_for__m_Singleton__`
- size: `27`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400265c0`

## import_xrefs

- `MpClient!MpConfigUnregisterNotifications` at `0x1400265d0`
- `MpClient!MpConfigUnregisterNotifications` at `0x1400265d0`

## pseudocode

```c
void __fastcall CopyAcceleratorFeatures::GetInstance_::_2_::_dynamic_atexit_destructor_for__m_Singleton__()
{
  if ( qword_14003DBE0 )
    MpConfigUnregisterNotifications();
}

```

## disassembly

```asm
0x1400265c0  sub     rsp, 28h
0x1400265c4  mov     rcx, cs:qword_14003DBE0
0x1400265cb  test    rcx, rcx
0x1400265ce  jz      short loc_1400265D6
0x1400265d0  call    cs:__imp_MpConfigUnregisterNotifications
0x1400265d6  add     rsp, 28h
0x1400265da  retn
```
