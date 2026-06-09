# RegistryT<256>::Clear(void)

- ea: `0x180025b50`
- end: `0x180025be1`
- name: `?Clear@?$RegistryT@$0BAA@@@UEAAAEAV1@XZ`
- size: `145`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180003d20`
- `0x18000b29c`
- `0x1800195c4`
- `0x180025b50`

## import_xrefs

- `ADVAPI32!RegDeleteTreeW` at `0x180025b68`
- `ADVAPI32!RegDeleteTreeW` at `0x180025b68`

## pseudocode

```c
__int64 __fastcall RegistryT<256>::Clear(__int64 a1)
{
  LSTATUS v2; // eax
  unsigned int v3; // ebx
  _BYTE pExceptionObject[56]; // [rsp+20h] [rbp-38h] BYREF

  v2 = RegDeleteTreeW(*(HKEY *)(a1 + 16), &SubKey);
  v3 = v2;
  if ( (v2 & 0xFFFFFFFD) != 0 )
  {
    if ( v2 > 0 )
      v3 = (unsigned __int16)v2 | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 18, WPP_65e306aa03cb33dd77e1945f965d0384_Traceguids, v3);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v3);
    throw (ErrorCodeException *)pExceptionObject;
  }
  return a1;
}

```

## disassembly

```asm
0x180025b50  mov     [rsp+arg_0], rbx
0x180025b55  push    rdi
0x180025b56  sub     rsp, 50h
0x180025b5a  mov     rdi, rcx
0x180025b5d  lea     rdx, SubKey; lpSubKey
0x180025b64  mov     rcx, [rcx+10h]; hKey
0x180025b68  call    cs:__imp_RegDeleteTreeW
0x180025b6e  mov     ebx, eax
0x180025b70  test    eax, 0FFFFFFFDh
0x180025b75  jnz     short loc_180025B85
0x180025b77  mov     rbx, [rsp+58h+arg_0]
0x180025b7c  mov     rax, rdi
0x180025b7f  add     rsp, 50h
0x180025b83  pop     rdi
0x180025b84  retn
0x180025b85  test    eax, eax
0x180025b87  jle     short loc_180025B92
0x180025b89  movzx   ebx, ax
0x180025b8c  or      ebx, 80070000h
0x180025b92  mov     rcx, cs:WPP_GLOBAL_Control
0x180025b99  lea     rax, WPP_GLOBAL_Control
0x180025ba0  cmp     rcx, rax
0x180025ba3  jz      short loc_180025BC3
0x180025ba5  test    byte ptr [rcx+1Ch], 1
0x180025ba9  jz      short loc_180025BC3
0x180025bab  mov     rcx, [rcx+10h]
0x180025baf  lea     r8, WPP_65e306aa03cb33dd77e1945f965d0384_Traceguids
0x180025bb6  mov     edx, 12h
0x180025bbb  mov     r9d, ebx
0x180025bbe  call    WPP_SF_d
0x180025bc3  mov     edx, ebx; int
0x180025bc5  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180025bca  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x180025bcf  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180025bd6  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180025bdb  call    _CxxThrowException_0
```
