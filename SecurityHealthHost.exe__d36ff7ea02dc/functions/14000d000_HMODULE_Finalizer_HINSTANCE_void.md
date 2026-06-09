# _HMODULE_Finalizer(HINSTANCE__ *,void *)

- ea: `0x14000d000`
- end: `0x14000d05f`
- name: `?_HMODULE_Finalizer@@YAXPEAUHINSTANCE__@@PEAX@Z`
- size: `95`
- prototype: `void __fastcall(HINSTANCE, void *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140005bd8`
- `0x140005bf0`
- `0x140005fdc`
- `0x14000c688`

## callees

- `0x14000d000`
- `0x14000d068`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x14000d009`
- `KERNEL32!FreeLibrary` at `0x14000d009`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d013`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d013`

## pseudocode

```c
void __fastcall _HMODULE_Finalizer(HINSTANCE a1, void *a2)
{
  signed int LastError; // eax

  if ( a1 && !FreeLibrary(a1) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_f9d18e1b35b534c89be06ddedda22e4c_Traceguids,
        (unsigned int)LastError,
        LastError);
  }
}

```

## disassembly

```asm
0x14000d000  sub     rsp, 38h
0x14000d004  test    rcx, rcx
0x14000d007  jz      short loc_14000D05A
0x14000d009  call    cs:__imp_FreeLibrary
0x14000d00f  test    eax, eax
0x14000d011  jnz     short loc_14000D05A
0x14000d013  call    cs:__imp_GetLastError
0x14000d019  test    eax, eax
0x14000d01b  jle     short loc_14000D025
0x14000d01d  movzx   eax, ax
0x14000d020  or      eax, 80070000h
0x14000d025  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d02c  lea     rdx, WPP_GLOBAL_Control
0x14000d033  cmp     rcx, rdx
0x14000d036  jz      short loc_14000D05A
0x14000d038  test    byte ptr [rcx+1Ch], 1
0x14000d03c  jz      short loc_14000D05A
0x14000d03e  mov     rcx, [rcx+10h]
0x14000d042  lea     r8, WPP_f9d18e1b35b534c89be06ddedda22e4c_Traceguids
0x14000d049  mov     edx, 0Ch
0x14000d04e  mov     [rsp+38h+var_18], eax
0x14000d052  mov     r9d, eax
0x14000d055  call    WPP_SF_Dd
0x14000d05a  add     rsp, 38h
0x14000d05e  retn
```
