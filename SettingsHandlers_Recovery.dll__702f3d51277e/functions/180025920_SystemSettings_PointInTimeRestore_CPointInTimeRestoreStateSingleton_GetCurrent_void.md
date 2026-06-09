# SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent(void)

- ea: `0x180025920`
- end: `0x180025988`
- name: `?GetCurrent@CPointInTimeRestoreStateSingleton@PointInTimeRestore@SystemSettings@@SAPEAV123@XZ`
- size: `104`
- prototype: `struct SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton *(void)`
- caller_count: `41`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010efc`
- `0x180011008`
- `0x18001127c`
- `0x180011378`
- `0x180011544`
- `0x180011648`
- `0x1800120e0`
- `0x180012198`
- `0x1800123b0`
- `0x180012468`
- `0x1800125a4`
- `0x18001265c`
- `0x180014070`
- `0x180014820`
- `0x180014bd0`
- `0x180016bd0`
- `0x1800171a0`
- `0x1800177a0`
- `0x180017de0`
- `0x180019bc0`
- `0x180019c60`
- `0x180019fb0`
- `0x18001a2a0`
- `0x18001a3c0`
- `0x18001ae50`
- `0x18001d8d0`
- `0x18001f470`
- `0x18001faf0`
- `0x18001fe30`
- `0x180020370`
- `0x180020900`
- `0x180022b20`
- `0x180022bf0`
- `0x180022cc0`
- `0x180022d90`
- `0x180022ea0`
- `0x180022f00`
- `0x180022f60`
- `0x180022fc0`
- `0x180029a29`
- `0x180029ae1`

## callees

- `0x180002800`
- `0x18000335c`
- `0x1800033c4`
- `0x1800245c4`
- `0x180025920`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton *SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent(
        void)
{
  SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton *v1; // rcx

  if ( dword_18005A0A0 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_18005A0A0);
    if ( dword_18005A0A0 == -1 )
    {
      SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::CPointInTimeRestoreStateSingleton(v1);
      atexit(SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent_::_2_::_dynamic_atexit_destructor_for__s_pointInTimeRestoreStateSingleton__);
      Init_thread_footer(&dword_18005A0A0);
    }
  }
  return (struct SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton *)&qword_18005A0B0;
}

```

## disassembly

```asm
0x180025920  sub     rsp, 28h
0x180025924  mov     ecx, cs:_tls_index
0x18002592a  mov     rax, gs:58h
0x180025933  mov     edx, 4
0x180025938  mov     rax, [rax+rcx*8]
0x18002593c  mov     eax, [rdx+rax]
0x18002593f  cmp     cs:dword_18005A0A0, eax
0x180025945  jg      short loc_180025953
0x180025947  lea     rax, qword_18005A0B0
0x18002594e  add     rsp, 28h
0x180025952  retn
0x180025953  lea     rcx, dword_18005A0A0
0x18002595a  call    _Init_thread_header
0x18002595f  cmp     cs:dword_18005A0A0, 0FFFFFFFFh
0x180025966  jnz     short loc_180025947
0x180025968  call    ??0CPointInTimeRestoreStateSingleton@PointInTimeRestore@SystemSettings@@AEAA@XZ; SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::CPointInTimeRestoreStateSingleton(void)
0x18002596d  lea     rcx, _SystemSettings__PointInTimeRestore__CPointInTimeRestoreStateSingleton__GetCurrent____2____dynamic_atexit_destructor_for__s_pointInTimeRestoreStateSingleton__; void (__cdecl *)()
0x180025974  call    atexit
0x180025979  nop
0x18002597a  lea     rcx, dword_18005A0A0
0x180025981  call    _Init_thread_footer
0x180025986  jmp     short loc_180025947
```
