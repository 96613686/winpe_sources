# GetDriverPackageCatalogFilename

- ea: `0x140019d98`
- end: `0x140019eda`
- name: `GetDriverPackageCatalogFilename`
- size: `322`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x14001ae4c`

## callees

- `0x1400070bc`
- `0x14000bb4c`
- `0x14000c354`
- `0x140019d98`
- `0x140045eea`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019df5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019e1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019df5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019e1c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140019eaa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140019eaa`
- `drvstore!DriverPackageClose` at `0x140019ea2`
- `drvstore!DriverPackageClose` at `0x140019ea2`
- `drvstore!DriverPackageOpenW` at `0x140019de7`
- `drvstore!DriverPackageOpenW` at `0x140019de7`
- `drvstore!DriverPackageGetVersionInfoW` at `0x140019e12`
- `drvstore!DriverPackageGetVersionInfoW` at `0x140019e12`

## pseudocode

```c
_BOOL8 __fastcall GetDriverPackageCatalogFilename(size_t *a1, __int64 a2, unsigned __int16 *a3)
{
  __int64 v5; // rax
  __int64 v6; // rsi
  DWORD LastError; // ebx
  unsigned int v8; // r11d
  unsigned int v9; // r11d
  _DWORD v11[313]; // [rsp+30h] [rbp-928h] BYREF
  _WORD v12[262]; // [rsp+514h] [rbp-444h] BYREF
  size_t v13[66]; // [rsp+720h] [rbp-238h] BYREF

  memset_0(v11, 0, 0x6F0u);
  v5 = DriverPackageOpenW(a1, 9, 0, 1, 0);
  v6 = v5;
  if ( v5 )
  {
    v11[0] = 1776;
    if ( (unsigned int)DriverPackageGetVersionInfoW(v5, v11) )
    {
      if ( (int)StringCchCopyW((unsigned __int16 *)v13, 0x104u, a1) >= 0 && (unsigned int)pSetupTrimFileTitle(v13) )
      {
        LastError = 0;
        if ( v12[0] )
        {
          if ( (int)StringCchCopyW(a3, v8, v13) < 0 || !(unsigned int)pSetupConcatenatePaths(a3, v12, v9) )
            LastError = 122;
        }
        else
        {
          *a3 = 0;
        }
      }
      else
      {
        LastError = 87;
      }
    }
    else
    {
      LastError = GetLastError();
    }
    DriverPackageClose(v6);
  }
  else
  {
    LastError = GetLastError();
  }
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x140019d98  mov     [rsp+arg_8], rbx
0x140019d9d  push    rbp
0x140019d9e  push    rsi
0x140019d9f  push    rdi
0x140019da0  sub     rsp, 940h
0x140019da7  mov     rax, cs:__security_cookie
0x140019dae  xor     rax, rsp
0x140019db1  mov     [rsp+958h+var_28], rax
0x140019db9  mov     rdi, r8
0x140019dbc  mov     rbx, rcx
0x140019dbf  mov     r8d, 6F0h; Size
0x140019dc5  lea     rcx, [rsp+958h+var_928]; void *
0x140019dca  xor     edx, edx; Val
0x140019dcc  call    memset_0
0x140019dd1  mov     edx, 9
0x140019dd6  xor     ebp, ebp
0x140019dd8  xor     r8d, r8d
0x140019ddb  mov     [rsp+958h+var_938], rbp
0x140019de0  mov     rcx, rbx
0x140019de3  lea     r9d, [rdx-8]
0x140019de7  call    cs:__imp_DriverPackageOpenW
0x140019ded  mov     rsi, rax
0x140019df0  test    rax, rax
0x140019df3  jnz     short loc_140019E02
0x140019df5  call    cs:__imp_GetLastError
0x140019dfb  mov     ebx, eax
0x140019dfd  jmp     loc_140019EA8
0x140019e02  lea     rdx, [rsp+958h+var_928]
0x140019e07  mov     [rsp+958h+var_928], 6F0h
0x140019e0f  mov     rcx, rsi
0x140019e12  call    cs:__imp_DriverPackageGetVersionInfoW
0x140019e18  test    eax, eax
0x140019e1a  jnz     short loc_140019E26
0x140019e1c  call    cs:__imp_GetLastError
0x140019e22  mov     ebx, eax
0x140019e24  jmp     short loc_140019E9F
0x140019e26  mov     r11d, 104h
0x140019e2c  lea     rcx, [rsp+958h+var_238]; unsigned __int16 *
0x140019e34  mov     edx, r11d; unsigned __int64
0x140019e37  mov     r8, rbx; unsigned __int16 *
0x140019e3a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140019e3f  test    eax, eax
0x140019e41  js      short loc_140019E9A
0x140019e43  lea     rcx, [rsp+958h+var_238]
0x140019e4b  call    pSetupTrimFileTitle
0x140019e50  test    eax, eax
0x140019e52  jz      short loc_140019E9A
0x140019e54  mov     ebx, ebp
0x140019e56  cmp     [rsp+958h+var_444], bp
0x140019e5e  jz      short loc_140019E95
0x140019e60  lea     r8, [rsp+958h+var_238]; unsigned __int16 *
0x140019e68  mov     edx, r11d; unsigned __int64
0x140019e6b  mov     rcx, rdi; unsigned __int16 *
0x140019e6e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140019e73  test    eax, eax
0x140019e75  js      short loc_140019E8E
0x140019e77  mov     r8d, r11d
0x140019e7a  lea     rdx, [rsp+958h+var_444]
0x140019e82  mov     rcx, rdi
0x140019e85  call    pSetupConcatenatePaths
0x140019e8a  test    eax, eax
0x140019e8c  jnz     short loc_140019E9F
0x140019e8e  mov     ebx, 7Ah ; 'z'
0x140019e93  jmp     short loc_140019E9F
0x140019e95  mov     [rdi], bp
0x140019e98  jmp     short loc_140019E9F
0x140019e9a  mov     ebx, 57h ; 'W'
0x140019e9f  mov     rcx, rsi
0x140019ea2  call    cs:__imp_DriverPackageClose
0x140019ea8  mov     ecx, ebx; dwErrCode
0x140019eaa  call    cs:__imp_SetLastError
0x140019eb0  test    ebx, ebx
0x140019eb2  mov     eax, ebp
0x140019eb4  setz    al
0x140019eb7  mov     rcx, [rsp+958h+var_28]
0x140019ebf  xor     rcx, rsp; StackCookie
0x140019ec2  call    __security_check_cookie
0x140019ec7  mov     rbx, [rsp+958h+arg_8]
0x140019ecf  add     rsp, 940h
0x140019ed6  pop     rdi
0x140019ed7  pop     rsi
0x140019ed8  pop     rbp
0x140019ed9  retn
```
