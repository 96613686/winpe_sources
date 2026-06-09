# PnpUtilsDriverRequiresGroupUpdate(HDRIVERSTORE__ *,ushort const *,int *)

- ea: `0x140029c38`
- end: `0x140029daf`
- name: `?PnpUtilsDriverRequiresGroupUpdate@@YAHPEAUHDRIVERSTORE__@@PEBGPEAH@Z`
- size: `375`
- prototype: `_BOOL8 __fastcall(struct HDRIVERSTORE__ *, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140029a3c`

## callees

- `0x140029c38`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140029c92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140029cdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140029c92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140029cdb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140029d05`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140029d05`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x140029d77`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x140029d77`
- `drvstore!DriverStoreFindW` at `0x140029cd1`
- `drvstore!DriverStoreFindW` at `0x140029cd1`
- `drvstore!DriverStoreOpenW` at `0x140029c84`
- `drvstore!DriverStoreOpenW` at `0x140029c84`
- `drvstore!DriverStoreClose` at `0x140029cfd`
- `drvstore!DriverStoreClose` at `0x140029cfd`

## pseudocode

```c
_BOOL8 __fastcall PnpUtilsDriverRequiresGroupUpdate(struct HDRIVERSTORE__ *a1, const unsigned __int16 *a2, int *a3)
{
  struct HDRIVERSTORE__ *v6; // rdi
  DWORD LastError; // ebx
  _BYTE v9[528]; // [rsp+60h] [rbp-238h] BYREF

  if ( a1 )
  {
    v6 = a1;
  }
  else
  {
    v6 = (struct HDRIVERSTORE__ *)DriverStoreOpenW(0, 0, 0, 0);
    if ( !v6 )
    {
      LastError = GetLastError();
      goto LABEL_10;
    }
  }
  if ( (unsigned int)DriverStoreFindW(v6, a2, 0xFFFF, 0, 1, v9, 260, 0) )
  {
    DriverStoreGetObjectPropertyW(v6, 2, v9, DEVPKEY_DriverPackage_NoGroupUpdate);
  }
  else
  {
    LastError = GetLastError();
    if ( LastError != 2 )
      goto LABEL_8;
  }
  *a3 = 1;
  LastError = 0;
LABEL_8:
  if ( !a1 )
    DriverStoreClose(v6);
LABEL_10:
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x140029c38  mov     [rsp+arg_18], rbx
0x140029c3d  push    rbp
0x140029c3e  push    rsi
0x140029c3f  push    rdi
0x140029c40  sub     rsp, 280h
0x140029c47  mov     rax, cs:__security_cookie
0x140029c4e  xor     rax, rsp
0x140029c51  mov     [rsp+298h+var_28], rax
0x140029c59  mov     [rsp+298h+var_248], 0
0x140029c5e  mov     rsi, r8
0x140029c61  mov     [rsp+298h+var_244], 0
0x140029c69  mov     rbx, rdx
0x140029c6c  mov     [rsp+298h+var_240], 0
0x140029c74  mov     rbp, rcx
0x140029c77  test    rcx, rcx
0x140029c7a  jnz     short loc_140029C9C
0x140029c7c  xor     r9d, r9d
0x140029c7f  xor     r8d, r8d
0x140029c82  xor     edx, edx
0x140029c84  call    cs:__imp_DriverStoreOpenW
0x140029c8a  mov     rdi, rax
0x140029c8d  test    rax, rax
0x140029c90  jnz     short loc_140029C9F
0x140029c92  call    cs:__imp_GetLastError
0x140029c98  mov     ebx, eax
0x140029c9a  jmp     short loc_140029D03
0x140029c9c  mov     rdi, rbp
0x140029c9f  mov     [rsp+298h+var_260], 0
0x140029ca8  lea     rax, [rsp+298h+var_238]
0x140029cad  mov     [rsp+298h+var_268], 104h
0x140029cb5  mov     r8d, 0FFFFh
0x140029cbb  mov     [rsp+298h+var_270], rax
0x140029cc0  xor     r9d, r9d
0x140029cc3  mov     rdx, rbx
0x140029cc6  mov     dword ptr [rsp+298h+var_278], 1
0x140029cce  mov     rcx, rdi
0x140029cd1  call    cs:__imp_DriverStoreFindW
0x140029cd7  test    eax, eax
0x140029cd9  jnz     short loc_140029D35
0x140029cdb  call    cs:__imp_GetLastError
0x140029ce1  mov     ebx, eax
0x140029ce3  cmp     eax, 2
0x140029ce6  jnz     short loc_140029CF0
0x140029ce8  mov     dword ptr [rsi], 1
0x140029cee  xor     ebx, ebx
0x140029cf0  test    rdi, rdi
0x140029cf3  jz      short loc_140029D03
0x140029cf5  test    rbp, rbp
0x140029cf8  jnz     short loc_140029D03
0x140029cfa  mov     rcx, rdi
0x140029cfd  call    cs:__imp_DriverStoreClose
0x140029d03  mov     ecx, ebx; dwErrCode
0x140029d05  call    cs:__imp_SetLastError
0x140029d0b  xor     eax, eax
0x140029d0d  test    ebx, ebx
0x140029d0f  setz    al
0x140029d12  mov     rcx, [rsp+298h+var_28]
0x140029d1a  xor     rcx, rsp; StackCookie
0x140029d1d  call    __security_check_cookie
0x140029d22  mov     rbx, [rsp+298h+arg_18]
0x140029d2a  add     rsp, 280h
0x140029d31  pop     rdi
0x140029d32  pop     rsi
0x140029d33  pop     rbp
0x140029d34  retn
0x140029d35  mov     [rsp+298h+var_258], 0
0x140029d3d  lea     rax, [rsp+298h+var_240]
0x140029d42  mov     [rsp+298h+var_260], rax
0x140029d47  lea     r9, DEVPKEY_DriverPackage_NoGroupUpdate
0x140029d4e  lea     rax, [rsp+298h+var_248]
0x140029d53  mov     [rsp+298h+var_268], 1
0x140029d5b  mov     [rsp+298h+var_270], rax
0x140029d60  lea     r8, [rsp+298h+var_238]
0x140029d65  lea     rax, [rsp+298h+var_244]
0x140029d6a  mov     edx, 2
0x140029d6f  mov     rcx, rdi
0x140029d72  mov     [rsp+298h+var_278], rax
0x140029d77  call    cs:__imp_DriverStoreGetObjectPropertyW
0x140029d7d  test    eax, eax
0x140029d7f  jz      loc_140029CE8
0x140029d85  cmp     [rsp+298h+var_244], 11h
0x140029d8a  jnz     loc_140029CE8
0x140029d90  cmp     [rsp+298h+var_240], 1
0x140029d95  jnz     loc_140029CE8
0x140029d9b  cmp     [rsp+298h+var_248], 0FFh
0x140029da0  jnz     loc_140029CE8
0x140029da6  xor     ebx, ebx
0x140029da8  mov     [rsi], ebx
0x140029daa  jmp     loc_140029CF0
```
