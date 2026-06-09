# GetTranslatedInt(ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x180006d24`
- end: `0x180006e4d`
- name: `?GetTranslatedInt@@YAKPEBG00K@Z`
- size: `297`
- prototype: `__int64 __fastcall(const unsigned __int16 *, PCWSTR Section, PCWSTR Key, unsigned int nDefault)`
- caller_count: `6`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180002ad4`
- `0x180004880`
- `0x1800088c4`
- `0x18000a24c`
- `0x18000a428`
- `0x18000dbec`

## callees

- `0x1800020a0`
- `0x1800021dc`
- `0x1800045e8`
- `0x180006d24`
- `0x180007968`
- `0x18001b980`

## import_xrefs

- `msvcrt!_wtol` at `0x180006e17`
- `msvcrt!_wtol` at `0x180006e17`
- `KERNEL32!GetPrivateProfileIntW` at `0x180006dde`
- `KERNEL32!GetPrivateProfileIntW` at `0x180006dde`

## pseudocode

```c
__int64 __fastcall GetTranslatedInt(const unsigned __int16 *a1, PCWSTR Section, PCWSTR Key, unsigned int nDefault)
{
  int v8; // ebp
  int v9; // esi
  unsigned int PrivateProfileIntW; // eax
  DWORD v12[4]; // [rsp+30h] [rbp-128h] BYREF
  wchar_t String[104]; // [rsp+40h] [rbp-118h] BYREF

  v12[0] = 0;
  v8 = 0;
  v9 = 0;
  if ( hLibModule )
  {
    if ( !InfHandle )
      MySetupOpenInfFile(a1);
  }
  else if ( (unsigned int)CheckOSVersion() && ctx )
  {
    dword_1800257F8 = 0;
    if ( !(unsigned int)InitializeSetupAPI() || (int)MySetupOpenInfFile(a1) < 0 )
      return nDefault;
  }
  else
  {
    v9 = dword_1800257F8;
    v8 = 1;
    dword_1800257F8 = 1;
  }
  if ( dword_1800257F8 == 1 )
  {
    PrivateProfileIntW = GetPrivateProfileIntW(Section, Key, nDefault, a1);
LABEL_15:
    nDefault = PrivateProfileIntW;
    goto LABEL_16;
  }
  String[0] = 0;
  if ( (int)MySetupGetLineText(Section, Key, String, 0x64u, v12) >= 0 && String[0] )
  {
    PrivateProfileIntW = _wtol(String);
    goto LABEL_15;
  }
LABEL_16:
  if ( v8 )
    dword_1800257F8 = v9;
  return nDefault;
}

```

## disassembly

```asm
0x180006d24  push    rbx
0x180006d26  push    rbp
0x180006d27  push    rsi
0x180006d28  push    rdi
0x180006d29  push    r12
0x180006d2b  push    r14
0x180006d2d  push    r15
0x180006d2f  sub     rsp, 120h
0x180006d36  mov     rax, cs:__security_cookie
0x180006d3d  xor     rax, rsp
0x180006d40  mov     [rsp+158h+var_48], rax
0x180006d48  xor     r12d, r12d
0x180006d4b  mov     ebx, r9d
0x180006d4e  cmp     cs:hLibModule, r12
0x180006d55  mov     r15, r8
0x180006d58  mov     r14, rdx
0x180006d5b  mov     [rsp+158h+var_128], r12d
0x180006d60  mov     rdi, rcx
0x180006d63  mov     ebp, r12d
0x180006d66  mov     esi, r12d
0x180006d69  jnz     short loc_180006DBB
0x180006d6b  call    ?CheckOSVersion@@YAHXZ; CheckOSVersion(void)
0x180006d70  test    eax, eax
0x180006d72  jz      short loc_180006DA4
0x180006d74  cmp     cs:?ctx@@3UADVCONTEXTW@@A, r12w; ADVCONTEXTW ctx
0x180006d7c  jz      short loc_180006DA4
0x180006d7e  mov     cs:dword_1800257F8, r12d
0x180006d85  call    ?InitializeSetupAPI@@YAHXZ; InitializeSetupAPI(void)
0x180006d8a  test    eax, eax
0x180006d8c  jz      loc_180006E29
0x180006d92  mov     rcx, rdi; unsigned __int16 *
0x180006d95  call    ?MySetupOpenInfFile@@YAJPEBG@Z; MySetupOpenInfFile(ushort const *)
0x180006d9a  test    eax, eax
0x180006d9c  js      loc_180006E29
0x180006da2  jmp     short loc_180006DC9
0x180006da4  mov     esi, cs:dword_1800257F8
0x180006daa  mov     ebp, 1
0x180006daf  mov     cs:dword_1800257F8, 1
0x180006db9  jmp     short loc_180006DC9
0x180006dbb  cmp     cs:InfHandle, r12
0x180006dc2  jnz     short loc_180006DC9
0x180006dc4  call    ?MySetupOpenInfFile@@YAJPEBG@Z; MySetupOpenInfFile(ushort const *)
0x180006dc9  cmp     cs:dword_1800257F8, 1
0x180006dd0  mov     rdx, r15; Key
0x180006dd3  mov     rcx, r14; Section
0x180006dd6  jnz     short loc_180006DE6
0x180006dd8  mov     r9, rdi; lpFileName
0x180006ddb  mov     r8d, ebx; nDefault
0x180006dde  call    cs:__imp_GetPrivateProfileIntW
0x180006de4  jmp     short loc_180006E1D
0x180006de6  lea     rax, [rsp+158h+var_128]
0x180006deb  mov     [rsp+158h+String], r12w
0x180006df1  mov     r9d, 64h ; 'd'; ReturnBufferSize
0x180006df7  mov     [rsp+158h+var_138], rax; PDWORD
0x180006dfc  lea     r8, [rsp+158h+String]; ReturnBuffer
0x180006e01  call    ?MySetupGetLineText@@YAJPEBG0PEAGKPEAK@Z; MySetupGetLineText(ushort const *,ushort const *,ushort *,ulong,ulong *)
0x180006e06  test    eax, eax
0x180006e08  js      short loc_180006E1F
0x180006e0a  cmp     [rsp+158h+String], r12w
0x180006e10  jz      short loc_180006E1F
0x180006e12  lea     rcx, [rsp+158h+String]; String
0x180006e17  call    cs:__imp__wtol
0x180006e1d  mov     ebx, eax
0x180006e1f  test    ebp, ebp
0x180006e21  jz      short loc_180006E29
0x180006e23  mov     cs:dword_1800257F8, esi
0x180006e29  mov     eax, ebx
0x180006e2b  mov     rcx, [rsp+158h+var_48]
0x180006e33  xor     rcx, rsp; StackCookie
0x180006e36  call    __security_check_cookie
0x180006e3b  add     rsp, 120h
0x180006e42  pop     r15
0x180006e44  pop     r14
0x180006e46  pop     r12
0x180006e48  pop     rdi
0x180006e49  pop     rsi
0x180006e4a  pop     rbp
0x180006e4b  pop     rbx
0x180006e4c  retn
```
