# AslpFileGetImageNtHeader

- ea: `0x140051e8c`
- end: `0x140051fc4`
- name: `AslpFileGetImageNtHeader`
- size: `312`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `9`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x14003475c`
- `0x140034ec0`
- `0x140035304`
- `0x1400355e8`
- `0x1400357b8`
- `0x140035a68`
- `0x140035f34`
- `0x1400363a4`
- `0x140051a20`

## callees

- `0x140004445`
- `0x1400045b0`
- `0x1400079f0`
- `0x140007e40`
- `0x14003e364`
- `0x140051e8c`

## string_xrefs

- `0x140051ee2`: `AslpFileGetImageNtHeader`
- `0x140051f60`: `AslpFileGetImageNtHeader`
- `0x140051f8a`: `AslpFileGetImageNtHeader`

## pseudocode

```c
__int64 __fastcall AslpFileGetImageNtHeader(_QWORD *a1, __int64 a2)
{
  unsigned int v4; // ebx
  int *v5; // rdi
  __int64 v6; // rcx
  _BYTE v8[64]; // [rsp+40h] [rbp-58h] BYREF

  memset(v8, 0, sizeof(v8));
  if ( *(_DWORD *)(a2 + 64) == 6 )
  {
    v5 = *(int **)(a2 + 32);
    if ( (unsigned __int8)MmIsUserAddress_0(v5) )
    {
      RtlCopyFromUser(v8, v5, 0x40u);
      v5 = (int *)v8;
    }
    v6 = v5[15];
    if ( *(_QWORD *)(a2 + 24) < (unsigned __int64)(v6 + 264) || *(_QWORD *)(a2 + 40) < (unsigned __int64)(v6 + 264) )
    {
      v4 = -1073741701;
      AslLogCallPrintf(1, "AslpFileGetImageNtHeader", 3777, "File mapping invalid [%x]", -1073741701);
    }
    else
    {
      *a1 = *(_QWORD *)(a2 + 32) + v6;
      return 0;
    }
  }
  else
  {
    v4 = -1073741637;
    AslLogCallPrintf(1, "AslpFileGetImageNtHeader", 3758, "File mapping not a PE [%x]", -1073741637);
  }
  return v4;
}

```

## disassembly

```asm
0x140051e8c  mov     [rsp+arg_10], rbx
0x140051e91  mov     [rsp+arg_18], rsi
0x140051e96  push    rdi
0x140051e97  sub     rsp, 90h
0x140051e9e  mov     rax, cs:__security_cookie
0x140051ea5  xor     rax, rsp
0x140051ea8  mov     [rsp+98h+var_18], rax
0x140051eb0  mov     rbx, rdx
0x140051eb3  mov     rsi, rcx
0x140051eb6  xor     edx, edx; Val
0x140051eb8  lea     r8d, [rdx+40h]; Size
0x140051ebc  lea     rcx, [rsp+98h+var_58]; void *
0x140051ec1  call    memset
0x140051ec6  cmp     dword ptr [rbx+40h], 6
0x140051eca  jz      short loc_140051EF8
0x140051ecc  mov     ebx, 0C00000BBh
0x140051ed1  mov     [rsp+98h+var_78], ebx
0x140051ed5  lea     r9, aFileMappingNot; "File mapping not a PE [%x]"
0x140051edc  mov     r8d, 0EAEh
0x140051ee2  lea     rdx, aAslpfilegetima_3; "AslpFileGetImageNtHeader"
0x140051ee9  mov     ecx, 1
0x140051eee  call    AslLogCallPrintf
0x140051ef3  jmp     loc_140051F9C
0x140051ef8  mov     rdi, [rbx+20h]
0x140051efc  mov     rcx, rdi
0x140051eff  call    MmIsUserAddress_0
0x140051f04  test    al, al
0x140051f06  jz      short loc_140051F20
0x140051f08  mov     r8d, 40h ; '@'; Size
0x140051f0e  mov     rdx, rdi; Src
0x140051f11  lea     rcx, [rsp+98h+var_58]; void *
0x140051f16  call    RtlCopyFromUser
0x140051f1b  lea     rdi, [rsp+98h+var_58]
0x140051f20  movsxd  rcx, dword ptr [rdi+3Ch]
0x140051f24  lea     rax, [rcx+108h]
0x140051f2b  cmp     [rbx+18h], rax
0x140051f2f  jb      short loc_140051F46
0x140051f31  cmp     [rbx+28h], rax
0x140051f35  jb      short loc_140051F46
0x140051f37  add     rcx, [rbx+20h]
0x140051f3b  mov     [rsi], rcx
0x140051f3e  xor     ebx, ebx
0x140051f40  mov     [rsp+98h+var_68], ebx
0x140051f44  jmp     short loc_140051F71
0x140051f46  mov     ebx, 0C000007Bh
0x140051f4b  mov     [rsp+98h+var_68], ebx
0x140051f4f  mov     [rsp+98h+var_78], ebx
0x140051f53  lea     r9, aFileMappingInv; "File mapping invalid [%x]"
0x140051f5a  mov     r8d, 0EC1h
0x140051f60  lea     rdx, aAslpfilegetima_3; "AslpFileGetImageNtHeader"
0x140051f67  mov     ecx, 1
0x140051f6c  call    AslLogCallPrintf
0x140051f71  jmp     short loc_140051F9C
0x140051f73  mov     ebx, eax
0x140051f75  mov     [rsp+98h+var_68], eax
0x140051f79  mov     [rsp+98h+var_78], eax
0x140051f7d  lea     r9, aExceptionEncou_0; "Exception encountered [%x]"
0x140051f84  mov     r8d, 0ECAh
0x140051f8a  lea     rdx, aAslpfilegetima_3; "AslpFileGetImageNtHeader"
0x140051f91  mov     ecx, 1
0x140051f96  call    AslLogCallPrintf
0x140051f9b  nop
0x140051f9c  mov     eax, ebx
0x140051f9e  mov     rcx, [rsp+98h+var_18]
0x140051fa6  xor     rcx, rsp; StackCookie
0x140051fa9  call    __security_check_cookie
0x140051fae  lea     r11, [rsp+98h+var_8]
0x140051fb6  mov     rbx, [r11+20h]
0x140051fba  mov     rsi, [r11+28h]
0x140051fbe  mov     rsp, r11
0x140051fc1  pop     rdi
0x140051fc2  retn
0x14005bf35  push    rbp
0x14005bf37  sub     rsp, 30h
0x14005bf3b  mov     rbp, rdx
0x14005bf3e  mov     eax, 1
0x14005bf43  add     rsp, 30h
0x14005bf47  pop     rbp
0x14005bf48  retn
```
