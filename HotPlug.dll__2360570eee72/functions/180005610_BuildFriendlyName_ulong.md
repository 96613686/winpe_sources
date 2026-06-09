# BuildFriendlyName(ulong)

- ea: `0x180005610`
- end: `0x18000571b`
- name: `?BuildFriendlyName@@YAPEAGK@Z`
- size: `267`
- prototype: `unsigned __int16 *__fastcall(DEVINST dnDevInst)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180002824`
- `0x180005724`
- `0x18000712c`

## callees

- `0x180002fd4`
- `0x180005610`
- `0x180008760`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x1800056c6`
- `KERNEL32!LocalAlloc` at `0x1800056c6`
- `CFGMGR32!CM_Get_DevNode_Registry_Property_ExW` at `0x180005665`
- `CFGMGR32!CM_Get_DevNode_Registry_Property_ExW` at `0x1800056a2`
- `CFGMGR32!CM_Get_DevNode_Registry_Property_ExW` at `0x180005665`
- `CFGMGR32!CM_Get_DevNode_Registry_Property_ExW` at `0x1800056a2`

## pseudocode

```c
unsigned __int16 *__fastcall BuildFriendlyName(DEVINST dnDevInst)
{
  unsigned __int16 v2; // ax
  unsigned __int16 *v3; // rax
  unsigned __int16 *v4; // r11
  ULONG pulLength[4]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 Buffer[264]; // [rsp+50h] [rbp-B0h] BYREF

  pulLength[0] = 520;
  if ( CM_Get_DevNode_Registry_Property_ExW(dnDevInst, 0xDu, 0, Buffer, pulLength, 0, 0) || (v2 = Buffer[0]) == 0 )
  {
    pulLength[0] = 520;
    if ( CM_Get_DevNode_Registry_Property_ExW(dnDevInst, 1u, 0, Buffer, pulLength, 0, 0) )
      return 0;
    v2 = Buffer[0];
  }
  if ( pulLength[0] <= 2 || !v2 )
    return 0;
  v3 = (unsigned __int16 *)LocalAlloc(0x40u, pulLength[0]);
  v4 = v3;
  if ( v3 )
  {
    Buffer[259] = 0;
    StringCchCopyW(v3, (unsigned __int64)pulLength[0] >> 1, Buffer);
  }
  return v4;
}

```

## disassembly

```asm
0x180005610  mov     [rsp-8+arg_8], rbx
0x180005615  mov     [rsp-8+arg_10], rdi
0x18000561a  push    rbp
0x18000561b  lea     rbp, [rsp-170h]
0x180005623  sub     rsp, 270h
0x18000562a  mov     rax, cs:__security_cookie
0x180005631  xor     rax, rsp
0x180005634  mov     [rbp+170h+var_10], rax
0x18000563b  xor     edi, edi
0x18000563d  mov     [rsp+270h+var_230], 208h
0x180005645  mov     [rsp+270h+hMachine], rdi; hMachine
0x18000564a  lea     rax, [rsp+270h+var_230]
0x18000564f  mov     [rsp+270h+ulFlags], edi; ulFlags
0x180005653  lea     r9, [rsp+270h+Buffer]; Buffer
0x180005658  xor     r8d, r8d; pulRegDataType
0x18000565b  mov     [rsp+270h+pulLength], rax; pulLength
0x180005660  lea     edx, [rdi+0Dh]; ulProperty
0x180005663  mov     ebx, ecx
0x180005665  call    cs:__imp_CM_Get_DevNode_Registry_Property_ExW
0x18000566b  test    eax, eax
0x18000566d  jnz     short loc_180005679
0x18000566f  movzx   eax, [rsp+270h+Buffer]
0x180005674  test    ax, ax
0x180005677  jnz     short loc_1800056B1
0x180005679  xor     r8d, r8d; pulRegDataType
0x18000567c  mov     [rsp+270h+hMachine], rdi; hMachine
0x180005681  lea     rax, [rsp+270h+var_230]
0x180005686  mov     [rsp+270h+ulFlags], edi; ulFlags
0x18000568a  lea     r9, [rsp+270h+Buffer]; Buffer
0x18000568f  mov     [rsp+270h+var_230], 208h
0x180005697  mov     ecx, ebx; dnDevInst
0x180005699  mov     [rsp+270h+pulLength], rax; pulLength
0x18000569e  lea     edx, [r8+1]; ulProperty
0x1800056a2  call    cs:__imp_CM_Get_DevNode_Registry_Property_ExW
0x1800056a8  test    eax, eax
0x1800056aa  jnz     short loc_1800056F1
0x1800056ac  movzx   eax, [rsp+270h+Buffer]
0x1800056b1  cmp     [rsp+270h+var_230], 2
0x1800056b6  jbe     short loc_1800056F1
0x1800056b8  test    ax, ax
0x1800056bb  jz      short loc_1800056F1
0x1800056bd  mov     edx, [rsp+270h+var_230]; uBytes
0x1800056c1  mov     ecx, 40h ; '@'; uFlags
0x1800056c6  call    cs:__imp_LocalAlloc
0x1800056cc  mov     r11, rax
0x1800056cf  test    rax, rax
0x1800056d2  jz      short loc_1800056F4
0x1800056d4  mov     edx, [rsp+270h+var_230]
0x1800056d8  lea     r8, [rsp+270h+Buffer]; unsigned __int16 *
0x1800056dd  shr     rdx, 1; unsigned __int64
0x1800056e0  mov     rcx, rax; unsigned __int16 *
0x1800056e3  mov     [rbp+170h+var_1A], di
0x1800056ea  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800056ef  jmp     short loc_1800056F4
0x1800056f1  mov     r11, rdi
0x1800056f4  mov     rax, r11
0x1800056f7  mov     rcx, [rbp+170h+var_10]
0x1800056fe  xor     rcx, rsp; StackCookie
0x180005701  call    __security_check_cookie
0x180005706  lea     r11, [rsp+270h+var_s0]
0x18000570e  mov     rbx, [r11+18h]
0x180005712  mov     rdi, [r11+20h]
0x180005716  mov     rsp, r11
0x180005719  pop     rbp
0x18000571a  retn
```
