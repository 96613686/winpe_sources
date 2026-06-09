# _HMODULE_Finalizer(HINSTANCE__ *,void *)

- ea: `0x14000dd0c`
- end: `0x14000dd6b`
- name: `?_HMODULE_Finalizer@@YAXPEAUHINSTANCE__@@PEAX@Z`
- size: `95`
- prototype: `void __fastcall(HINSTANCE, void *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140007430`
- `0x140007448`
- `0x140007538`
- `0x14000d15c`

## callees

- `0x14000dd0c`
- `0x14000dd74`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000dd1f`
- `KERNEL32!GetLastError` at `0x14000dd1f`
- `KERNEL32!FreeLibrary` at `0x14000dd15`
- `KERNEL32!FreeLibrary` at `0x14000dd15`

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
0x14000dd0c  sub     rsp, 38h
0x14000dd10  test    rcx, rcx
0x14000dd13  jz      short loc_14000DD66
0x14000dd15  call    cs:__imp_FreeLibrary
0x14000dd1b  test    eax, eax
0x14000dd1d  jnz     short loc_14000DD66
0x14000dd1f  call    cs:__imp_GetLastError
0x14000dd25  test    eax, eax
0x14000dd27  jle     short loc_14000DD31
0x14000dd29  movzx   eax, ax
0x14000dd2c  or      eax, 80070000h
0x14000dd31  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dd38  lea     rdx, WPP_GLOBAL_Control
0x14000dd3f  cmp     rcx, rdx
0x14000dd42  jz      short loc_14000DD66
0x14000dd44  test    byte ptr [rcx+1Ch], 1
0x14000dd48  jz      short loc_14000DD66
0x14000dd4a  mov     rcx, [rcx+10h]
0x14000dd4e  lea     r8, WPP_f9d18e1b35b534c89be06ddedda22e4c_Traceguids
0x14000dd55  mov     edx, 0Ch
0x14000dd5a  mov     [rsp+38h+var_18], eax
0x14000dd5e  mov     r9d, eax
0x14000dd61  call    WPP_SF_Dd
0x14000dd66  add     rsp, 38h
0x14000dd6a  retn
```
