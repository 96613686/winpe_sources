# DrvUtilsIsValidPrimitiveDriver

- ea: `0x140024fe0`
- end: `0x1400250f7`
- name: `DrvUtilsIsValidPrimitiveDriver`
- size: `279`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140013e14`
- `0x140014860`
- `0x140026994`

## callees

- `0x140024fe0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025041`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002509a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025041`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002509a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400250df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400250df`
- `drvstore!DriverPackageClose` at `0x1400250d7`
- `drvstore!DriverPackageClose` at `0x1400250d7`
- `drvstore!DriverPackageOpenW` at `0x140025033`
- `drvstore!DriverPackageOpenW` at `0x140025033`
- `drvstore!DriverPackageGetPropertyW` at `0x140025090`
- `drvstore!DriverPackageGetPropertyW` at `0x140025090`

## pseudocode

```c
__int64 __fastcall DrvUtilsIsValidPrimitiveDriver(__int64 a1, __int64 a2, unsigned __int16 a3)
{
  unsigned int v3; // ebp
  DWORD LastError; // ebx
  __int64 v6; // rdi
  _DWORD v8[10]; // [rsp+50h] [rbp-28h] BYREF
  char v9; // [rsp+80h] [rbp+8h] BYREF
  int v10; // [rsp+98h] [rbp+20h] BYREF

  v3 = 0;
  v10 = 0;
  v8[0] = 0;
  v9 = 0;
  if ( a1 )
  {
    v6 = a1;
  }
  else
  {
    if ( !a2 )
    {
      LastError = 87;
      goto LABEL_15;
    }
    v6 = DriverPackageOpenW(a2, a3, 0, 0, 0);
    if ( !v6 )
    {
      LastError = GetLastError();
      goto LABEL_15;
    }
  }
  if ( (unsigned int)DriverPackageGetPropertyW(v6, 0, 0, DEVPKEY_DriverPackage_Primitive, &v10, &v9, 1, v8, 0) )
  {
    if ( v10 == 17 && v8[0] == 1 )
    {
      LastError = 0;
      LOBYTE(v3) = v9 == -1;
    }
    else
    {
      LastError = 13;
    }
  }
  else
  {
    LastError = GetLastError();
  }
  if ( !a1 )
    DriverPackageClose(v6);
LABEL_15:
  SetLastError(LastError);
  return v3;
}

```

## disassembly

```asm
0x140024fe0  mov     r11, rsp
0x140024fe3  mov     [r11+10h], rbx
0x140024fe7  push    rbp
0x140024fe8  push    rsi
0x140024fe9  push    rdi
0x140024fea  sub     rsp, 60h
0x140024fee  xor     ebp, ebp
0x140024ff0  mov     dword ptr [r11+20h], 0
0x140024ff8  mov     [rsp+78h+var_28], 0
0x140025000  movzx   r10d, r8w
0x140025004  mov     byte ptr [r11+8], 0
0x140025009  mov     rax, rdx
0x14002500c  mov     rsi, rcx
0x14002500f  test    rcx, rcx
0x140025012  jnz     short loc_14002504E
0x140025014  test    rax, rax
0x140025017  jnz     short loc_140025021
0x140025019  lea     ebx, [rdx+57h]
0x14002501c  jmp     loc_1400250DD
0x140025021  xor     r9d, r9d
0x140025024  mov     [rsp+78h+var_58], rbp
0x140025029  xor     r8d, r8d
0x14002502c  movzx   edx, r10w
0x140025030  mov     rcx, rax
0x140025033  call    cs:__imp_DriverPackageOpenW
0x140025039  mov     rdi, rax
0x14002503c  test    rax, rax
0x14002503f  jnz     short loc_140025051
0x140025041  call    cs:__imp_GetLastError
0x140025047  mov     ebx, eax
0x140025049  jmp     loc_1400250DD
0x14002504e  mov     rdi, rsi
0x140025051  mov     [rsp+78h+var_38], ebp
0x140025055  lea     rax, [rsp+78h+var_28]
0x14002505a  mov     [rsp+78h+var_40], rax
0x14002505f  lea     r9, DEVPKEY_DriverPackage_Primitive
0x140025066  lea     rax, [rsp+78h+arg_0]
0x14002506e  mov     [rsp+78h+var_48], 1
0x140025076  mov     [rsp+78h+var_50], rax
0x14002507b  xor     r8d, r8d
0x14002507e  lea     rax, [rsp+78h+arg_18]
0x140025086  xor     edx, edx
0x140025088  mov     rcx, rdi
0x14002508b  mov     [rsp+78h+var_58], rax
0x140025090  call    cs:__imp_DriverPackageGetPropertyW
0x140025096  test    eax, eax
0x140025098  jnz     short loc_1400250A4
0x14002509a  call    cs:__imp_GetLastError
0x1400250a0  mov     ebx, eax
0x1400250a2  jmp     short loc_1400250CA
0x1400250a4  cmp     [rsp+78h+arg_18], 11h
0x1400250ac  jnz     short loc_1400250C5
0x1400250ae  cmp     [rsp+78h+var_28], 1
0x1400250b3  jnz     short loc_1400250C5
0x1400250b5  xor     ebx, ebx
0x1400250b7  cmp     [rsp+78h+arg_0], 0FFh
0x1400250bf  setz    bpl
0x1400250c3  jmp     short loc_1400250CA
0x1400250c5  mov     ebx, 0Dh
0x1400250ca  test    rsi, rsi
0x1400250cd  jnz     short loc_1400250DD
0x1400250cf  test    rdi, rdi
0x1400250d2  jz      short loc_1400250DD
0x1400250d4  mov     rcx, rdi
0x1400250d7  call    cs:__imp_DriverPackageClose
0x1400250dd  mov     ecx, ebx; dwErrCode
0x1400250df  call    cs:__imp_SetLastError
0x1400250e5  mov     rbx, [rsp+78h+arg_8]
0x1400250ed  mov     eax, ebp
0x1400250ef  add     rsp, 60h
0x1400250f3  pop     rdi
0x1400250f4  pop     rsi
0x1400250f5  pop     rbp
0x1400250f6  retn
```
