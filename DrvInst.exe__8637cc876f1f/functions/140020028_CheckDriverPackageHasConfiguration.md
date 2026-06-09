# CheckDriverPackageHasConfiguration

- ea: `0x140020028`
- end: `0x140020157`
- name: `CheckDriverPackageHasConfiguration`
- size: `303`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140020bbc`

## callees

- `0x140020028`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020093`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002010c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020093`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002010c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002012f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002012f`
- `drvstore!DriverPackageClose` at `0x140020127`
- `drvstore!DriverPackageClose` at `0x140020127`
- `drvstore!DriverPackageEnumConfigurationsW` at `0x140020102`
- `drvstore!DriverPackageEnumConfigurationsW` at `0x140020102`
- `drvstore!DriverStoreFindW` at `0x140020089`
- `drvstore!DriverStoreFindW` at `0x140020089`
- `drvstore!DriverStoreDriverPackageResolveCallbackW` at `0x1400200a0`
- `drvstore!DriverPackageOpenW` at `0x1400200cb`
- `drvstore!DriverPackageOpenW` at `0x1400200cb`

## pseudocode

```c
_BOOL8 __fastcall CheckDriverPackageHasConfiguration(__int64 a1, __int64 a2, __int64 a3)
{
  DWORD LastError; // ebx
  __int64 v6; // rdi
  __int128 v8; // [rsp+40h] [rbp-258h] BYREF
  __int128 v9; // [rsp+50h] [rbp-248h] BYREF
  _BYTE v10[528]; // [rsp+60h] [rbp-238h] BYREF

  v9 = 0;
  v8 = 0;
  if ( (unsigned int)DriverStoreFindW(a1, a2, 9, 0, 1, v10, 260, 0)
    && (*(_QWORD *)&v9 = DriverStoreDriverPackageResolveCallbackW,
        *((_QWORD *)&v9 + 1) = a1,
        (v6 = DriverPackageOpenW(v10, 9, 0, 1, &v9)) != 0) )
  {
    *(_QWORD *)&v8 = a3;
    DWORD2(v8) = 0;
    if ( (unsigned int)DriverPackageEnumConfigurationsW(
                         v6,
                         0,
                         4096,
                         CheckDriverPackageHasConfigurationEnumCallback,
                         &v8) )
    {
      LastError = 0;
      if ( !DWORD2(v8) )
        LastError = 1168;
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
0x140020028  push    rbx
0x14002002a  push    rsi
0x14002002b  push    rdi
0x14002002c  sub     rsp, 280h
0x140020033  mov     rax, cs:__security_cookie
0x14002003a  xor     rax, rsp
0x14002003d  mov     [rsp+298h+var_28], rax
0x140020045  mov     [rsp+298h+var_260], 0
0x14002004e  lea     rax, [rsp+298h+var_238]
0x140020053  mov     [rsp+298h+var_268], 104h
0x14002005b  mov     rsi, r8
0x14002005e  xorps   xmm0, xmm0
0x140020061  mov     [rsp+298h+var_270], rax
0x140020066  xorps   xmm1, xmm1
0x140020069  mov     dword ptr [rsp+298h+var_278], 1
0x140020071  mov     edi, 9
0x140020076  xor     r9d, r9d
0x140020079  mov     r8d, edi
0x14002007c  mov     rbx, rcx
0x14002007f  movups  [rsp+298h+var_248], xmm0
0x140020084  movups  [rsp+298h+var_258], xmm1
0x140020089  call    cs:__imp_DriverStoreFindW
0x14002008f  test    eax, eax
0x140020091  jnz     short loc_1400200A0
0x140020093  call    cs:__imp_GetLastError
0x140020099  mov     ebx, eax
0x14002009b  jmp     loc_14002012D
0x1400200a0  mov     rax, cs:__imp_DriverStoreDriverPackageResolveCallbackW
0x1400200a7  lea     rcx, [rsp+298h+var_238]
0x1400200ac  mov     qword ptr [rsp+298h+var_248], rax
0x1400200b1  mov     edx, edi
0x1400200b3  lea     rax, [rsp+298h+var_248]
0x1400200b8  mov     qword ptr [rsp+298h+var_248+8], rbx
0x1400200bd  mov     r9d, 1
0x1400200c3  mov     [rsp+298h+var_278], rax
0x1400200c8  xor     r8d, r8d
0x1400200cb  call    cs:__imp_DriverPackageOpenW
0x1400200d1  mov     rdi, rax
0x1400200d4  test    rax, rax
0x1400200d7  jz      short loc_140020093
0x1400200d9  lea     rax, [rsp+298h+var_258]
0x1400200de  mov     qword ptr [rsp+298h+var_258], rsi
0x1400200e3  lea     r9, CheckDriverPackageHasConfigurationEnumCallback
0x1400200ea  mov     [rsp+298h+var_278], rax
0x1400200ef  xor     edx, edx
0x1400200f1  mov     dword ptr [rsp+298h+var_258+8], 0
0x1400200f9  mov     r8d, 1000h
0x1400200ff  mov     rcx, rdi
0x140020102  call    cs:__imp_DriverPackageEnumConfigurationsW
0x140020108  test    eax, eax
0x14002010a  jnz     short loc_140020116
0x14002010c  call    cs:__imp_GetLastError
0x140020112  mov     ebx, eax
0x140020114  jmp     short loc_140020124
0x140020116  xor     ebx, ebx
0x140020118  mov     eax, 490h
0x14002011d  cmp     dword ptr [rsp+298h+var_258+8], ebx
0x140020121  cmovz   ebx, eax
0x140020124  mov     rcx, rdi
0x140020127  call    cs:__imp_DriverPackageClose
0x14002012d  mov     ecx, ebx; dwErrCode
0x14002012f  call    cs:__imp_SetLastError
0x140020135  xor     eax, eax
0x140020137  test    ebx, ebx
0x140020139  setz    al
0x14002013c  mov     rcx, [rsp+298h+var_28]
0x140020144  xor     rcx, rsp; StackCookie
0x140020147  call    __security_check_cookie
0x14002014c  add     rsp, 280h
0x140020153  pop     rdi
0x140020154  pop     rsi
0x140020155  pop     rbx
0x140020156  retn
```
