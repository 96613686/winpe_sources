# CreateTempDir(char *,ulong)

- ea: `0x407ca8`
- end: `0x407d0e`
- name: `?CreateTempDir@@YGJPADK@Z`
- size: `102`
- prototype: `unsigned int __thiscall(_BYTE *this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x4035e8`
- `0x405628`

## callees

- `0x407a3f`
- `0x407ca8`
- `0x40cb60`

## import_xrefs

- `KERNEL32!GetTempPath2A` at `0x407ccf`
- `KERNEL32!GetTempPath2A` at `0x407ccf`
- `KERNEL32!GetLastError` at `0x407ceb`
- `KERNEL32!GetLastError` at `0x407ceb`

## pseudocode

```c
unsigned int __thiscall CreateTempDir(_BYTE *this)
{
  const char *v1; // ecx
  unsigned int v2; // ecx
  signed int LastError; // eax
  char *v5; // [esp+0h] [ebp-10Ch]
  unsigned int v6[65]; // [esp+4h] [ebp-108h] BYREF

  *this = 0;
  if ( GetTempPath2A(260, v6) )
    return MakeUniqueTempDirectory(v1, v5, v6[0]);
  LastError = GetLastError();
  v2 = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    return LastError;
  return v2;
}

```

## disassembly

```asm
0x407ca8  mov     edi, edi
0x407caa  push    ebp
0x407cab  mov     ebp, esp
0x407cad  sub     esp, 108h
0x407cb3  mov     eax, ___security_cookie
0x407cb8  xor     eax, ebp
0x407cba  mov     [ebp+var_4], eax
0x407cbd  push    esi; char *
0x407cbe  mov     esi, ecx
0x407cc0  lea     eax, [ebp+var_108]
0x407cc6  push    eax
0x407cc7  push    104h
0x407ccc  mov     byte ptr [esi], 0
0x407ccf  call    ds:__imp__GetTempPath2A@8; GetTempPath2A(x,x)
0x407cd5  test    eax, eax
0x407cd7  jz      short loc_407CEB
0x407cd9  push    ecx; char *
0x407cda  mov     edx, esi
0x407cdc  lea     ecx, [ebp+var_108]
0x407ce2  call    ?MakeUniqueTempDirectory@@YGJPBDPADK@Z; MakeUniqueTempDirectory(char const *,char *,ulong)
0x407ce7  mov     ecx, eax
0x407ce9  jmp     short loc_407CFF
0x407ceb  call    ds:__imp__GetLastError@0; GetLastError()
0x407cf1  movzx   ecx, ax
0x407cf4  or      ecx, 80070000h
0x407cfa  test    eax, eax
0x407cfc  cmovle  ecx, eax
0x407cff  mov     eax, ecx
0x407d01  mov     ecx, [ebp+var_4]
0x407d04  xor     ecx, ebp; StackCookie
0x407d06  pop     esi
0x407d07  call    @__security_check_cookie@4; __security_check_cookie(x)
0x407d0c  leave
0x407d0d  retn
```
