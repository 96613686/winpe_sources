# GetRegistrationRootKeyFromIntegrityLevel(HKEY__ * *)

- ea: `0x409dbc`
- end: `0x409dfb`
- name: `?GetRegistrationRootKeyFromIntegrityLevel@@YGJPAPAUHKEY__@@@Z`
- size: `63`
- prototype: `int __thiscall(_DWORD *this)`
- caller_count: `4`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x40351a`
- `0x4044ae`
- `0x404c02`
- `0x405304`

## callees

- `0x409d63`
- `0x409dbc`

## pseudocode

```c
int __thiscall GetRegistrationRootKeyFromIntegrityLevel(_DWORD *this)
{
  int result; // eax
  int v3; // [esp+4h] [ebp-4h] BYREF

  *this = 0;
  result = GetInstallScopeFromIntegrityLevel(&v3);
  if ( !result )
  {
    if ( v3 == 1 )
    {
      *this = -2147483646;
    }
    else if ( v3 == 2 )
    {
      *this = -2147483647;
    }
    else
    {
      return -2147467259;
    }
  }
  return result;
}

```

## disassembly

```asm
0x409dbc  mov     edi, edi
0x409dbe  push    ebp
0x409dbf  mov     ebp, esp
0x409dc1  push    ecx
0x409dc2  push    esi; unsigned int *
0x409dc3  mov     esi, ecx
0x409dc5  lea     ecx, [ebp+var_4]
0x409dc8  mov     dword ptr [esi], 0
0x409dce  call    ?GetInstallScopeFromIntegrityLevel@@YGJPAK@Z; GetInstallScopeFromIntegrityLevel(ulong *)
0x409dd3  test    eax, eax
0x409dd5  jnz     short loc_409DF8
0x409dd7  cmp     [ebp+var_4], 1
0x409ddb  jnz     short loc_409DE5
0x409ddd  mov     dword ptr [esi], 80000002h
0x409de3  jmp     short loc_409DF8
0x409de5  cmp     [ebp+var_4], 2
0x409de9  jnz     short loc_409DF3
0x409deb  mov     dword ptr [esi], 80000001h
0x409df1  jmp     short loc_409DF8
0x409df3  mov     eax, 80004005h
0x409df8  pop     esi
0x409df9  leave
0x409dfa  retn
```
