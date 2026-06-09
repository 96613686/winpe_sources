# SusRunOEMTaskOffline(_SYSPREP_OS_OFFLINE *)

- ea: `0x1800019a0`
- end: `0x1800019eb`
- name: `?SusRunOEMTaskOffline@@YAKPEAU_SYSPREP_OS_OFFLINE@@@Z`
- size: `75`
- prototype: `__int64 __fastcall(struct _SYSPREP_OS_OFFLINE *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1800019a0`
- `0x180001bc0`
- `0x180003610`

## pseudocode

```c
__int64 __fastcall SusRunOEMTaskOffline(struct _SYSPREP_OS_OFFLINE *a1)
{
  int v1; // eax

  v1 = SuspRunStartupAppTask((__int64)a1, 1u);
  if ( v1 < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      WPP_a998e44d15d036c13a6bc2c2021de65f_Traceguids,
      (unsigned __int16)v1);
  return 0;
}

```

## disassembly

```asm
0x1800019a0  sub     rsp, 28h
0x1800019a4  mov     edx, 1
0x1800019a9  call    ?SuspRunStartupAppTask@@YAJPEAU_SYSPREP_OS_OFFLINE@@W4StartupScanFlags@@@Z; SuspRunStartupAppTask(_SYSPREP_OS_OFFLINE *,StartupScanFlags)
0x1800019ae  test    eax, eax
0x1800019b0  jns     short loc_1800019E4
0x1800019b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800019b9  lea     rdx, WPP_GLOBAL_Control
0x1800019c0  cmp     rcx, rdx
0x1800019c3  jz      short loc_1800019E4
0x1800019c5  test    byte ptr [rcx+1Ch], 1
0x1800019c9  jz      short loc_1800019E4
0x1800019cb  mov     rcx, [rcx+10h]
0x1800019cf  lea     r8, WPP_a998e44d15d036c13a6bc2c2021de65f_Traceguids
0x1800019d6  movzx   r9d, ax
0x1800019da  mov     edx, 0Bh
0x1800019df  call    WPP_SF_D
0x1800019e4  xor     eax, eax
0x1800019e6  add     rsp, 28h
0x1800019ea  retn
```
