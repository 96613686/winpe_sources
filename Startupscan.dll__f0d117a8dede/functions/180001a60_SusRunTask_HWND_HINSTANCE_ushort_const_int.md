# SusRunTask(HWND__ *,HINSTANCE__ *,ushort const *,int)

- ea: `0x180001a60`
- end: `0x180001aa8`
- name: `?SusRunTask@@YAXPEAUHWND__@@PEAUHINSTANCE__@@PEBGH@Z`
- size: `72`
- prototype: `void __fastcall(HWND, HINSTANCE, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x180001a60`
- `0x180001bc0`
- `0x180003610`

## pseudocode

```c
void __fastcall SusRunTask(HWND a1, HINSTANCE a2, const unsigned __int16 *a3)
{
  int v3; // eax

  v3 = SuspRunStartupAppTask(0, 0, a3);
  if ( v3 < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_a998e44d15d036c13a6bc2c2021de65f_Traceguids,
      (unsigned __int16)v3);
}

```

## disassembly

```asm
0x180001a60  sub     rsp, 28h
0x180001a64  xor     edx, edx
0x180001a66  xor     ecx, ecx
0x180001a68  call    ?SuspRunStartupAppTask@@YAJPEAU_SYSPREP_OS_OFFLINE@@W4StartupScanFlags@@@Z; SuspRunStartupAppTask(_SYSPREP_OS_OFFLINE *,StartupScanFlags)
0x180001a6d  test    eax, eax
0x180001a6f  jns     short loc_180001AA3
0x180001a71  mov     rcx, cs:WPP_GLOBAL_Control
0x180001a78  lea     rdx, WPP_GLOBAL_Control
0x180001a7f  cmp     rcx, rdx
0x180001a82  jz      short loc_180001AA3
0x180001a84  test    byte ptr [rcx+1Ch], 1
0x180001a88  jz      short loc_180001AA3
0x180001a8a  mov     rcx, [rcx+10h]
0x180001a8e  lea     r8, WPP_a998e44d15d036c13a6bc2c2021de65f_Traceguids
0x180001a95  movzx   r9d, ax
0x180001a99  mov     edx, 0Ah
0x180001a9e  call    WPP_SF_D
0x180001aa3  add     rsp, 28h
0x180001aa7  retn
```
