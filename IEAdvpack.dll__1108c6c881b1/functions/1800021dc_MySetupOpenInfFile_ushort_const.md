# MySetupOpenInfFile(ushort const *)

- ea: `0x1800021dc`
- end: `0x180002262`
- name: `?MySetupOpenInfFile@@YAJPEBG@Z`
- size: `134`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180004754`
- `0x180006d24`
- `0x180006e54`
- `0x1800071c0`
- `0x180007454`

## callees

- `0x1800021dc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180002233`
- `KERNEL32!GetLastError` at `0x180002233`
- `SETUPAPI!SetupOpenInfFileW` at `0x1800021fb`
- `SETUPAPI!SetupOpenInfFileW` at `0x1800021fb`
- `SETUPAPI!SetupOpenAppendInfFileW` at `0x18000221b`
- `SETUPAPI!SetupOpenAppendInfFileW` at `0x18000221b`

## pseudocode

```c
__int64 __fastcall MySetupOpenInfFile(const unsigned __int16 *a1)
{
  char *v1; // rdx
  signed int LastError; // ecx
  unsigned int ErrorLine; // [rsp+38h] [rbp+10h] BYREF

  ErrorLine = 0;
  if ( InfHandle )
    return 0;
  v1 = (char *)SetupOpenInfFileW(a1, 0, 2u, 0);
  InfHandle = v1;
  if ( (unsigned __int64)(v1 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    SetupOpenAppendInfFileW(0, v1, &ErrorLine);
    return 0;
  }
  InfHandle = 0;
  LastError = GetLastError();
  if ( (LastError & 0xE0000000) == 0xE0000000 )
  {
    return (unsigned __int16)LastError | 0x800F0000;
  }
  else if ( LastError > 0 )
  {
    return (unsigned __int16)LastError | 0x80070000;
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800021dc  sub     rsp, 28h
0x1800021e0  cmp     cs:InfHandle, 0
0x1800021e8  mov     [rsp+28h+ErrorLine], 0
0x1800021f0  jnz     short loc_180002221
0x1800021f2  xor     r9d, r9d; ErrorLine
0x1800021f5  xor     edx, edx; InfClass
0x1800021f7  lea     r8d, [r9+2]; InfStyle
0x1800021fb  call    cs:__imp_SetupOpenInfFileW
0x180002201  mov     rdx, rax; InfHandle
0x180002204  mov     cs:InfHandle, rax
0x18000220b  dec     rax
0x18000220e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180002212  ja      short loc_180002228
0x180002214  lea     r8, [rsp+28h+ErrorLine]; ErrorLine
0x180002219  xor     ecx, ecx; FileName
0x18000221b  call    cs:__imp_SetupOpenAppendInfFileW
0x180002221  xor     eax, eax
0x180002223  add     rsp, 28h
0x180002227  retn
0x180002228  mov     cs:InfHandle, 0
0x180002233  call    cs:__imp_GetLastError
0x180002239  mov     edx, 0E0000000h
0x18000223e  mov     ecx, eax
0x180002240  and     eax, edx
0x180002242  cmp     eax, edx
0x180002244  jnz     short loc_180002251
0x180002246  movzx   ecx, cx
0x180002249  or      ecx, 800F0000h
0x18000224f  jmp     short loc_18000225E
0x180002251  test    ecx, ecx
0x180002253  jle     short loc_18000225E
0x180002255  movzx   ecx, cx
0x180002258  or      ecx, 80070000h
0x18000225e  mov     eax, ecx
0x180002260  jmp     short loc_180002223
```
