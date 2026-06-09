# GetProgramFilesDir(ushort *,ulong)

- ea: `0x180002c74`
- end: `0x180002d48`
- name: `?GetProgramFilesDir@@YAHPEAGK@Z`
- size: `212`
- prototype: `__int64 __fastcall(unsigned __int16 *, DWORD)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000279c`
- `0x1800042f8`
- `0x180005a8c`
- `0x18000e060`
- `0x18000ef90`

## callees

- `0x180002c74`
- `0x1800076a8`
- `0x18001b980`

## import_xrefs

- `KERNEL32!GetEnvironmentVariableW` at `0x180002cb3`
- `KERNEL32!GetEnvironmentVariableW` at `0x180002d0b`
- `KERNEL32!GetEnvironmentVariableW` at `0x180002cb3`
- `KERNEL32!GetEnvironmentVariableW` at `0x180002d0b`

## pseudocode

```c
__int64 __fastcall GetProgramFilesDir(unsigned __int16 *a1, DWORD a2)
{
  WCHAR Buffer[4]; // [rsp+30h] [rbp-28h] BYREF
  __int16 v6; // [rsp+38h] [rbp-20h]

  *a1 = 0;
  if ( ctx >= 3u && GetEnvironmentVariableW(L"ProgramFiles", a1, a2) )
    return 1;
  if ( (unsigned int)GetValueFromRegistry(
                       a1,
                       a2,
                       L"HKLM",
                       L"Software\\Microsoft\\Windows\\CurrentVersion",
                       L"ProgramFilesDir") )
  {
    if ( ctx >= 2u )
    {
      *(_QWORD *)Buffer = 0;
      v6 = 0;
      if ( GetEnvironmentVariableW(L"SystemDrive", Buffer, 5u) )
      {
        if ( Buffer[0] )
          *a1 = Buffer[0];
      }
    }
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180002c74  mov     [rsp+arg_10], rbx
0x180002c79  mov     [rsp+arg_18], rsi
0x180002c7e  push    rdi
0x180002c7f  sub     rsp, 50h
0x180002c83  mov     rax, cs:__security_cookie
0x180002c8a  xor     rax, rsp
0x180002c8d  mov     [rsp+58h+var_18], rax
0x180002c92  xor     esi, esi
0x180002c94  mov     edi, edx
0x180002c96  mov     [rcx], si
0x180002c99  mov     rbx, rcx
0x180002c9c  cmp     cs:?ctx@@3UADVCONTEXTW@@A, 3; ADVCONTEXTW ctx
0x180002ca4  jb      short loc_180002CBD
0x180002ca6  mov     r8d, edx; nSize
0x180002ca9  mov     rdx, rcx; lpBuffer
0x180002cac  lea     rcx, aProgramfiles_0; "ProgramFiles"
0x180002cb3  call    cs:__imp_GetEnvironmentVariableW
0x180002cb9  test    eax, eax
0x180002cbb  jnz     short loc_180002D22
0x180002cbd  lea     rax, aProgramfilesdi; "ProgramFilesDir"
0x180002cc4  mov     edx, edi; unsigned int
0x180002cc6  lea     r9, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180002ccd  mov     [rsp+58h+lpValueName], rax; lpValueName
0x180002cd2  lea     r8, String1; "HKLM"
0x180002cd9  mov     rcx, rbx; unsigned __int16 *
0x180002cdc  call    ?GetValueFromRegistry@@YAHPEAGKPEBG11@Z; GetValueFromRegistry(ushort *,ulong,ushort const *,ushort const *,ushort const *)
0x180002ce1  test    eax, eax
0x180002ce3  jz      short loc_180002D29
0x180002ce5  cmp     cs:?ctx@@3UADVCONTEXTW@@A, 2; ADVCONTEXTW ctx
0x180002ced  jb      short loc_180002D22
0x180002cef  xor     eax, eax
0x180002cf1  lea     rdx, [rsp+58h+Buffer]; lpBuffer
0x180002cf6  lea     rcx, aSystemdrive; "SystemDrive"
0x180002cfd  mov     qword ptr [rsp+58h+Buffer], rax
0x180002d02  mov     [rsp+58h+var_20], ax
0x180002d07  lea     r8d, [rax+5]; nSize
0x180002d0b  call    cs:__imp_GetEnvironmentVariableW
0x180002d11  test    eax, eax
0x180002d13  jz      short loc_180002D22
0x180002d15  movzx   eax, [rsp+58h+Buffer]
0x180002d1a  test    ax, ax
0x180002d1d  jz      short loc_180002D22
0x180002d1f  mov     [rbx], ax
0x180002d22  mov     eax, 1
0x180002d27  jmp     short loc_180002D2B
0x180002d29  xor     eax, eax
0x180002d2b  mov     rcx, [rsp+58h+var_18]
0x180002d30  xor     rcx, rsp; StackCookie
0x180002d33  call    __security_check_cookie
0x180002d38  mov     rbx, [rsp+58h+arg_10]
0x180002d3d  mov     rsi, [rsp+58h+arg_18]
0x180002d42  add     rsp, 50h
0x180002d46  pop     rdi
0x180002d47  retn
```
