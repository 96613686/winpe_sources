# __acrt_getptd_noexit

- ea: `0x180010420`
- end: `0x1800104ec`
- name: `__acrt_getptd_noexit`
- size: `204`
- prototype: `__int64()`
- caller_count: `8`
- callee_count: `6`
- tags: ``

## callers

- `0x18000bdec`
- `0x18000bf4c`
- `0x18000bf9c`
- `0x18000bfbc`
- `0x18000d764`
- `0x18000e6d0`
- `0x1800104f0`
- `0x180014190`

## callees

- `0x18000fe3c`
- `0x180010004`
- `0x180010420`
- `0x1800120b0`
- `0x180013d4c`
- `0x180013d94`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001042f`
- `KERNEL32!GetLastError` at `0x18001042f`
- `KERNEL32!SetLastError` at `0x1800104cd`
- `KERNEL32!SetLastError` at `0x1800104cd`

## pseudocode

```c
__int64 _acrt_getptd_noexit()
{
  DWORD LastError; // eax
  DWORD v1; // ecx
  DWORD v2; // ebx
  LPVOID Value; // rax
  void *v4; // rdi
  unsigned __int64 v5; // rsi
  void *v6; // rax
  void *v7; // rcx

  LastError = GetLastError();
  v1 = dword_18003D0D0;
  v2 = LastError;
  if ( dword_18003D0D0 == -1 )
  {
LABEL_6:
    if ( !_acrt_FlsSetValue(v1, (LPVOID)0xFFFFFFFFFFFFFFFFLL) )
      goto LABEL_4;
    v6 = calloc_base(1u, 0x3C8u);
    v4 = v6;
    if ( v6 )
    {
      if ( _acrt_FlsSetValue(dword_18003D0D0, v6) )
      {
        construct_ptd_array(v4);
        free_base(0);
        goto LABEL_13;
      }
      _acrt_FlsSetValue(dword_18003D0D0, 0);
      v7 = v4;
    }
    else
    {
      _acrt_FlsSetValue(dword_18003D0D0, 0);
      v7 = 0;
    }
    free_base(v7);
    goto LABEL_4;
  }
  Value = _acrt_FlsGetValue(dword_18003D0D0);
  v4 = Value;
  if ( !Value )
  {
    v1 = dword_18003D0D0;
    goto LABEL_6;
  }
  if ( Value != (LPVOID)-1LL )
  {
LABEL_13:
    v5 = (unsigned __int64)v4;
    goto LABEL_14;
  }
LABEL_4:
  v4 = 0;
  v5 = 0;
LABEL_14:
  SetLastError(v2);
  return v5 & -(__int64)(v4 != 0);
}

```

## disassembly

```asm
0x180010420  mov     [rsp+arg_0], rbx
0x180010425  mov     [rsp+arg_8], rsi
0x18001042a  push    rdi
0x18001042b  sub     rsp, 20h
0x18001042f  call    cs:__imp_GetLastError
0x180010435  mov     ecx, cs:dword_18003D0D0
0x18001043b  mov     ebx, eax
0x18001043d  cmp     ecx, 0FFFFFFFFh
0x180010440  jz      short loc_180010461
0x180010442  call    __acrt_FlsGetValue
0x180010447  mov     rdi, rax
0x18001044a  test    rax, rax
0x18001044d  jz      short loc_18001045B
0x18001044f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180010453  jnz     short loc_1800104C8
0x180010455  xor     edi, edi
0x180010457  xor     esi, esi
0x180010459  jmp     short loc_1800104CB
0x18001045b  mov     ecx, cs:dword_18003D0D0; dwTlsIndex
0x180010461  or      rdx, 0FFFFFFFFFFFFFFFFh; lpTlsValue
0x180010465  call    __acrt_FlsSetValue
0x18001046a  test    eax, eax
0x18001046c  jz      short loc_180010455
0x18001046e  mov     edx, 3C8h; Size
0x180010473  mov     ecx, 1; Count
0x180010478  call    _calloc_base
0x18001047d  mov     ecx, cs:dword_18003D0D0; dwTlsIndex
0x180010483  mov     rdi, rax
0x180010486  test    rax, rax
0x180010489  jnz     short loc_18001049B
0x18001048b  xor     edx, edx; lpTlsValue
0x18001048d  call    __acrt_FlsSetValue
0x180010492  xor     ecx, ecx; Block
0x180010494  call    _free_base
0x180010499  jmp     short loc_180010455
0x18001049b  mov     rdx, rdi; lpTlsValue
0x18001049e  call    __acrt_FlsSetValue
0x1800104a3  test    eax, eax
0x1800104a5  jnz     short loc_1800104B9
0x1800104a7  mov     ecx, cs:dword_18003D0D0; dwTlsIndex
0x1800104ad  xor     edx, edx; lpTlsValue
0x1800104af  call    __acrt_FlsSetValue
0x1800104b4  mov     rcx, rdi
0x1800104b7  jmp     short loc_180010494
0x1800104b9  mov     rcx, rdi
0x1800104bc  call    construct_ptd_array
0x1800104c1  xor     ecx, ecx; Block
0x1800104c3  call    _free_base
0x1800104c8  mov     rsi, rdi
0x1800104cb  mov     ecx, ebx; dwErrCode
0x1800104cd  call    cs:__imp_SetLastError
0x1800104d3  mov     rbx, [rsp+28h+arg_0]
0x1800104d8  neg     rdi
0x1800104db  sbb     rax, rax
0x1800104de  and     rax, rsi
0x1800104e1  mov     rsi, [rsp+28h+arg_8]
0x1800104e6  add     rsp, 20h
0x1800104ea  pop     rdi
0x1800104eb  retn
```
