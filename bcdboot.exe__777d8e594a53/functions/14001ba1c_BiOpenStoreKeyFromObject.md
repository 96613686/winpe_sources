# BiOpenStoreKeyFromObject

- ea: `0x14001ba1c`
- end: `0x14001baf7`
- name: `BiOpenStoreKeyFromObject`
- size: `219`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14001c088`
- `0x1400214ec`

## callees

- `0x14001ba1c`
- `0x14001e5e4`
- `0x14001f980`
- `0x1400265fa`
- `0x140026650`

## import_xrefs

- `ntdll!ZwQueryKey` at `0x14001ba8b`
- `ntdll!ZwQueryKey` at `0x14001ba8b`

## pseudocode

```c
__int64 __fastcall BiOpenStoreKeyFromObject(HANDLE KeyHandle, void **a2)
{
  int v4; // ebx
  ULONG ResultLength[4]; // [rsp+30h] [rbp-C8h] BYREF
  unsigned int KeyInformation; // [rsp+40h] [rbp-B8h] BYREF
  WCHAR v8[78]; // [rsp+44h] [rbp-B4h] BYREF

  memset_0(&KeyInformation, 0, 0xA0u);
  ResultLength[0] = 160;
  *a2 = 0;
  if ( ((unsigned __int8)KeyHandle & 1) != 0 )
  {
    v4 = -1073741822;
  }
  else
  {
    v4 = ZwQueryKey(KeyHandle, KeyNameInformation, &KeyInformation, 0xA0u, ResultLength);
    if ( v4 >= 0 )
    {
      if ( KeyInformation < 0x4C )
        return (unsigned int)v4;
      v8[29] = 0;
      v4 = BiOpenKey(0, v8, 0x2001Fu, a2);
      if ( v4 >= 0 )
        return (unsigned int)v4;
    }
  }
  if ( *a2 )
  {
    BiCloseKey(*a2);
    *a2 = 0;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14001ba1c  mov     [rsp+arg_10], rbx
0x14001ba21  push    rdi
0x14001ba22  sub     rsp, 0F0h
0x14001ba29  mov     rax, cs:__security_cookie
0x14001ba30  xor     rax, rsp
0x14001ba33  mov     [rsp+0F8h+var_18], rax
0x14001ba3b  mov     rdi, rdx
0x14001ba3e  mov     rbx, rcx
0x14001ba41  xor     edx, edx; Val
0x14001ba43  lea     rcx, [rsp+0F8h+KeyInformation]; void *
0x14001ba48  mov     r8d, 0A0h; Size
0x14001ba4e  call    memset_0
0x14001ba53  mov     [rsp+0F8h+var_C8], 0A0h
0x14001ba5b  mov     qword ptr [rdi], 0
0x14001ba62  test    bl, 1
0x14001ba65  jz      short loc_14001BA6E
0x14001ba67  mov     ebx, 0C0000002h
0x14001ba6c  jmp     short loc_14001BAC0
0x14001ba6e  lea     rax, [rsp+0F8h+var_C8]
0x14001ba73  mov     r9d, 0A0h; Length
0x14001ba79  lea     r8, [rsp+0F8h+KeyInformation]; KeyInformation
0x14001ba7e  mov     [rsp+0F8h+ResultLength], rax; ResultLength
0x14001ba83  mov     edx, 3; KeyInformationClass
0x14001ba88  mov     rcx, rbx; KeyHandle
0x14001ba8b  call    cs:__imp_ZwQueryKey
0x14001ba91  mov     ebx, eax
0x14001ba93  test    eax, eax
0x14001ba95  js      short loc_14001BAC0
0x14001ba97  cmp     [rsp+0F8h+KeyInformation], 4Ch ; 'L'
0x14001ba9c  jb      short loc_14001BAD4
0x14001ba9e  xor     eax, eax
0x14001baa0  lea     rdx, [rsp+0F8h+var_B4]
0x14001baa5  mov     r9, rdi
0x14001baa8  mov     [rsp+0F8h+var_7A], ax
0x14001baad  mov     r8d, 2001Fh
0x14001bab3  xor     ecx, ecx
0x14001bab5  call    BiOpenKey
0x14001baba  mov     ebx, eax
0x14001babc  test    eax, eax
0x14001babe  jns     short loc_14001BAD4
0x14001bac0  mov     rcx, [rdi]; Handle
0x14001bac3  test    rcx, rcx
0x14001bac6  jz      short loc_14001BAD4
0x14001bac8  call    BiCloseKey
0x14001bacd  mov     qword ptr [rdi], 0
0x14001bad4  mov     eax, ebx
0x14001bad6  mov     rcx, [rsp+0F8h+var_18]
0x14001bade  xor     rcx, rsp; StackCookie
0x14001bae1  call    __security_check_cookie
0x14001bae6  mov     rbx, [rsp+0F8h+arg_10]
0x14001baee  add     rsp, 0F0h
0x14001baf5  pop     rdi
0x14001baf6  retn
```
