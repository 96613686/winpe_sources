# UtilElevatedManager::UpdateTimeZone(void)

- ea: `0x18004a0a0`
- end: `0x18004a0d3`
- name: `?UpdateTimeZone@UtilElevatedManager@@UEAAJXZ`
- size: `51`
- prototype: `__int64 __fastcall(UtilElevatedManager *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800227ac`
- `0x18004a0a0`

## import_xrefs

- `tzautoupdate!AttemptToUpdateTimeZoneAndEnableChangeDetection` at `0x18004a0a9`
- `tzautoupdate!AttemptToUpdateTimeZoneAndEnableChangeDetection` at `0x18004a0a9`

## string_xrefs

- `0x18004a0b8`: `onecoreuap\shell\cloudexperiencehost\onecore\comapi\utilelevatedmanager.cpp`

## pseudocode

```c
__int64 __fastcall UtilElevatedManager::UpdateTimeZone(UtilElevatedManager *this)
{
  int v1; // eax
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = AttemptToUpdateTimeZoneAndEnableChangeDetection(60);
  if ( v1 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x4C,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\comapi\\utilelevatedmanager.cpp",
      (const char *)(unsigned int)v1,
      v3);
  return 0;
}

```

## disassembly

```asm
0x18004a0a0  sub     rsp, 28h
0x18004a0a4  mov     ecx, 3Ch ; '<'
0x18004a0a9  call    cs:__imp_AttemptToUpdateTimeZoneAndEnableChangeDetection
0x18004a0af  test    eax, eax
0x18004a0b1  jns     short loc_18004A0CC
0x18004a0b3  mov     rcx, [rsp+28h]; this
0x18004a0b8  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\cloudexperiencehost"...
0x18004a0bf  mov     r9d, eax; char *
0x18004a0c2  mov     edx, 4Ch ; 'L'; void *
0x18004a0c7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004a0cc  xor     eax, eax
0x18004a0ce  add     rsp, 28h
0x18004a0d2  retn
```
