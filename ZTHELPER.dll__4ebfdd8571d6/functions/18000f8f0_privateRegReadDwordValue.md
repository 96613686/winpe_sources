# privateRegReadDwordValue

- ea: `0x18000f8f0`
- end: `0x18000f9c2`
- name: `privateRegReadDwordValue`
- size: `210`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *, _DWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180003674`
- `0x1800039e4`
- `0x18001011c`

## callees

- `0x1800014b0`
- `0x18000f8f0`
- `0x180016134`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f963`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f963`

## pseudocode

```c
__int64 __fastcall privateRegReadDwordValue(HKEY a1, const WCHAR *a2, _DWORD *a3)
{
  int v4; // esi
  unsigned int v5; // ebx
  LSTATUS v6; // eax
  DWORD Type; // [rsp+30h] [rbp-38h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-34h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-30h] BYREF

  *(_DWORD *)Data = 0;
  Type = 0;
  v4 = (int)a2;
  cbData = 4;
  if ( a3 )
    *a3 = 0;
  if ( a1 && a2 && a3 )
  {
    v6 = RegQueryValueExW(a1, a2, 0, &Type, Data, &cbData);
    v5 = v6;
    if ( v6 )
    {
      if ( v6 == 2 )
        return v5;
    }
    else
    {
      if ( Type == 4 && cbData == 4 )
      {
        *a3 = *(_DWORD *)Data;
        return v5;
      }
      v5 = 1010;
    }
  }
  else
  {
    v5 = 87;
  }
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_SD((_DWORD)a1, 12, (_DWORD)a3, v4, v5);
  return v5;
}

```

## disassembly

```asm
0x18000f8f0  push    rbx
0x18000f8f2  push    rsi
0x18000f8f3  push    rdi
0x18000f8f4  sub     rsp, 50h
0x18000f8f8  mov     rax, cs:__security_cookie
0x18000f8ff  xor     rax, rsp
0x18000f902  mov     [rsp+68h+var_28], rax
0x18000f907  mov     dword ptr [rsp+68h+Data], 0
0x18000f90f  mov     rdi, r8
0x18000f912  mov     [rsp+68h+Type], 0
0x18000f91a  mov     rsi, rdx
0x18000f91d  mov     [rsp+68h+cbData], 4
0x18000f925  test    r8, r8
0x18000f928  jz      short loc_18000F931
0x18000f92a  mov     dword ptr [r8], 0
0x18000f931  test    rcx, rcx
0x18000f934  jnz     short loc_18000F93D
0x18000f936  mov     ebx, 57h ; 'W'
0x18000f93b  jmp     short loc_18000F991
0x18000f93d  test    rsi, rsi
0x18000f940  jz      short loc_18000F936
0x18000f942  test    rdi, rdi
0x18000f945  jz      short loc_18000F936
0x18000f947  lea     rax, [rsp+68h+cbData]
0x18000f94c  xor     r8d, r8d; lpReserved
0x18000f94f  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18000f954  lea     r9, [rsp+68h+Type]; lpType
0x18000f959  lea     rax, [rsp+68h+Data]
0x18000f95e  mov     [rsp+68h+lpData], rax; lpData
0x18000f963  call    cs:__imp_RegQueryValueExW
0x18000f969  mov     ebx, eax
0x18000f96b  test    eax, eax
0x18000f96d  jnz     short loc_18000F98C
0x18000f96f  cmp     [rsp+68h+Type], 4
0x18000f974  jnz     short loc_18000F985
0x18000f976  cmp     [rsp+68h+cbData], 4
0x18000f97b  jnz     short loc_18000F985
0x18000f97d  mov     eax, dword ptr [rsp+68h+Data]
0x18000f981  mov     [rdi], eax
0x18000f983  jmp     short loc_18000F9AB
0x18000f985  mov     ebx, 3F2h
0x18000f98a  jmp     short loc_18000F991
0x18000f98c  cmp     eax, 2
0x18000f98f  jz      short loc_18000F9AB
0x18000f991  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000f998  jz      short loc_18000F9AB
0x18000f99a  mov     edx, 0Ch
0x18000f99f  mov     dword ptr [rsp+68h+lpData], ebx
0x18000f9a3  mov     r9, rsi
0x18000f9a6  call    WPP_SF_SD
0x18000f9ab  mov     eax, ebx
0x18000f9ad  mov     rcx, [rsp+68h+var_28]
0x18000f9b2  xor     rcx, rsp; StackCookie
0x18000f9b5  call    __security_check_cookie
0x18000f9ba  add     rsp, 50h
0x18000f9be  pop     rdi
0x18000f9bf  pop     rsi
0x18000f9c0  pop     rbx
0x18000f9c1  retn
```
