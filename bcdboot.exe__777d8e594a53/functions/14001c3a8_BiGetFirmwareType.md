# BiGetFirmwareType

- ea: `0x14001c3a8`
- end: `0x14001c44f`
- name: `BiGetFirmwareType`
- size: `167`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14001acec`
- `0x14001b1f4`
- `0x14001b4bc`
- `0x14001bd44`
- `0x14001c14c`
- `0x14001c508`
- `0x14001c6e4`
- `0x1400200a0`

## callees

- `0x14001c3a8`
- `0x140026650`

## import_xrefs

- `ntdll!ZwQuerySystemInformation` at `0x14001c3ef`
- `ntdll!ZwQuerySystemInformation` at `0x14001c3ef`

## pseudocode

```c
__int64 __fastcall BiGetFirmwareType(_QWORD *a1)
{
  unsigned int v2; // ebx
  __int128 SystemInformation; // [rsp+20h] [rbp-38h] BYREF
  __int128 v5; // [rsp+30h] [rbp-28h]

  SystemInformation = 0;
  v5 = 0;
  if ( byte_14003F841 )
  {
    v2 = dword_14003F1D4;
  }
  else
  {
    v2 = 1;
    if ( ZwQuerySystemInformation(SystemBootEnvironmentInformation, &SystemInformation, 0x20u, 0) >= 0 )
    {
      v2 = 0;
      qword_14003F868 = *((_QWORD *)&v5 + 1);
      if ( (int)v5 < 3 )
        v2 = v5;
    }
    dword_14003F1D4 = v2;
    byte_14003F841 = 1;
  }
  if ( a1 )
    *a1 = qword_14003F868;
  return v2;
}

```

## disassembly

```asm
0x14001c3a8  mov     [rsp+arg_8], rbx
0x14001c3ad  push    rdi
0x14001c3ae  sub     rsp, 50h
0x14001c3b2  mov     rax, cs:__security_cookie
0x14001c3b9  xor     rax, rsp
0x14001c3bc  mov     [rsp+58h+var_18], rax
0x14001c3c1  mov     al, cs:byte_14003F841
0x14001c3c7  xorps   xmm0, xmm0
0x14001c3ca  mov     rdi, rcx
0x14001c3cd  movups  [rsp+58h+SystemInformation], xmm0
0x14001c3d2  movups  [rsp+58h+var_28], xmm0
0x14001c3d7  test    al, al
0x14001c3d9  jnz     short loc_14001C420
0x14001c3db  mov     ebx, 1
0x14001c3e0  lea     rdx, [rsp+58h+SystemInformation]; SystemInformation
0x14001c3e5  xor     r9d, r9d; ReturnLength
0x14001c3e8  lea     r8d, [rbx+1Fh]; SystemInformationLength
0x14001c3ec  lea     ecx, [rbx+59h]; SystemInformationClass
0x14001c3ef  call    cs:__imp_ZwQuerySystemInformation
0x14001c3f5  test    eax, eax
0x14001c3f7  js      short loc_14001C411
0x14001c3f9  mov     rax, qword ptr [rsp+58h+var_28+8]
0x14001c3fe  xor     ebx, ebx
0x14001c400  cmp     dword ptr [rsp+58h+var_28], 3
0x14001c405  mov     cs:qword_14003F868, rax
0x14001c40c  cmovl   ebx, dword ptr [rsp+58h+var_28]
0x14001c411  mov     cs:dword_14003F1D4, ebx
0x14001c417  mov     cs:byte_14003F841, 1
0x14001c41e  jmp     short loc_14001C426
0x14001c420  mov     ebx, cs:dword_14003F1D4
0x14001c426  test    rdi, rdi
0x14001c429  jz      short loc_14001C435
0x14001c42b  mov     rcx, cs:qword_14003F868
0x14001c432  mov     [rdi], rcx
0x14001c435  mov     eax, ebx
0x14001c437  mov     rcx, [rsp+58h+var_18]
0x14001c43c  xor     rcx, rsp; StackCookie
0x14001c43f  call    __security_check_cookie
0x14001c444  mov     rbx, [rsp+58h+arg_8]
0x14001c449  add     rsp, 50h
0x14001c44d  pop     rdi
0x14001c44e  retn
```
