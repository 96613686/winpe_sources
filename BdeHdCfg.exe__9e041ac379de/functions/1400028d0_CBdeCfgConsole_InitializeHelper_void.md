# CBdeCfgConsole::InitializeHelper(void)

- ea: `0x1400028d0`
- end: `0x140002929`
- name: `?InitializeHelper@CBdeCfgConsole@@AEAAJXZ`
- size: `89`
- prototype: `signed int __fastcall(CBdeCfgConsole *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140001dbc`

## callees

- `0x1400028d0`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x140002902`
- `KERNEL32!WaitForSingleObject` at `0x140002902`
- `KERNEL32!GetLastError` at `0x14000290c`
- `KERNEL32!GetLastError` at `0x14000290c`
- `BDEHDCFGLIB!?Initialize@CDriveConfiguration@@QEAAJPEBU_BDECFG_PARAMS@@QEAU_BDECFG_SIZE_REQUIREMENTS@@PEAVIConfigurationProgress@@@Z` at `0x1400028ee`
- `BDEHDCFGLIB!?Initialize@CDriveConfiguration@@QEAAJPEBU_BDECFG_PARAMS@@QEAU_BDECFG_SIZE_REQUIREMENTS@@PEAVIConfigurationProgress@@@Z` at `0x1400028ee`

## pseudocode

```c
signed int __fastcall CBdeCfgConsole::InitializeHelper(CBdeCfgConsole *this)
{
  signed int result; // eax

  result = CDriveConfiguration::Initialize(
             (CBdeCfgConsole *)((char *)this + 72),
             (CBdeCfgConsole *)((char *)this + 1360),
             (CBdeCfgConsole *)((char *)this + 1392),
             this);
  if ( result >= 0 )
  {
    if ( WaitForSingleObject(*((HANDLE *)this + 180), 0xFFFFFFFF) )
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
    else
    {
      return *((_DWORD *)this + 19);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400028d0  push    rbx
0x1400028d2  sub     rsp, 20h
0x1400028d6  mov     rbx, rcx
0x1400028d9  lea     r8, [rcx+570h]
0x1400028e0  lea     rdx, [rcx+550h]
0x1400028e7  add     rcx, 48h ; 'H'
0x1400028eb  mov     r9, rbx
0x1400028ee  call    cs:__imp_?Initialize@CDriveConfiguration@@QEAAJPEBU_BDECFG_PARAMS@@QEAU_BDECFG_SIZE_REQUIREMENTS@@PEAVIConfigurationProgress@@@Z; CDriveConfiguration::Initialize(_BDECFG_PARAMS const *,_BDECFG_SIZE_REQUIREMENTS * const,IConfigurationProgress *)
0x1400028f4  test    eax, eax
0x1400028f6  js      short loc_140002923
0x1400028f8  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400028fb  mov     rcx, [rbx+5A0h]; hHandle
0x140002902  call    cs:__imp_WaitForSingleObject
0x140002908  test    eax, eax
0x14000290a  jz      short loc_140002920
0x14000290c  call    cs:__imp_GetLastError
0x140002912  test    eax, eax
0x140002914  jle     short loc_140002923
0x140002916  movzx   eax, ax
0x140002919  or      eax, 80070000h
0x14000291e  jmp     short loc_140002923
0x140002920  mov     eax, [rbx+4Ch]
0x140002923  add     rsp, 20h
0x140002927  pop     rbx
0x140002928  retn
0x140004604  push    rbp
0x140004606  sub     rsp, 20h
0x14000460a  mov     rbp, rdx
0x14000460d  add     rsp, 20h
0x140004611  pop     rbp
0x140004612  retn
```
