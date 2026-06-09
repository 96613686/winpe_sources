# SusRunOEMTaskOnline(int)

- ea: `0x180001a00`
- end: `0x180001a4f`
- name: `?SusRunOEMTaskOnline@@YAKH@Z`
- size: `79`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x180001a00`
- `0x180001bc0`
- `0x180003610`

## pseudocode

```c
__int64 __fastcall SusRunOEMTaskOnline(int a1)
{
  int v1; // eax

  if ( !a1 )
  {
    v1 = SuspRunStartupAppTask(0, 1u);
    if ( v1 < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_a998e44d15d036c13a6bc2c2021de65f_Traceguids,
        (unsigned __int16)v1);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180001a00  sub     rsp, 28h
0x180001a04  test    ecx, ecx
0x180001a06  jnz     short loc_180001A48
0x180001a08  lea     edx, [rcx+1]
0x180001a0b  xor     ecx, ecx
0x180001a0d  call    ?SuspRunStartupAppTask@@YAJPEAU_SYSPREP_OS_OFFLINE@@W4StartupScanFlags@@@Z; SuspRunStartupAppTask(_SYSPREP_OS_OFFLINE *,StartupScanFlags)
0x180001a12  test    eax, eax
0x180001a14  jns     short loc_180001A48
0x180001a16  mov     rcx, cs:WPP_GLOBAL_Control
0x180001a1d  lea     rdx, WPP_GLOBAL_Control
0x180001a24  cmp     rcx, rdx
0x180001a27  jz      short loc_180001A48
0x180001a29  test    byte ptr [rcx+1Ch], 1
0x180001a2d  jz      short loc_180001A48
0x180001a2f  mov     rcx, [rcx+10h]
0x180001a33  lea     r8, WPP_a998e44d15d036c13a6bc2c2021de65f_Traceguids
0x180001a3a  movzx   r9d, ax
0x180001a3e  mov     edx, 0Ch
0x180001a43  call    WPP_SF_D
0x180001a48  xor     eax, eax
0x180001a4a  add     rsp, 28h
0x180001a4e  retn
```
