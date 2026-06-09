# InstallDriver

- ea: `0x140013e14`
- end: `0x140013f63`
- name: `InstallDriver`
- size: `335`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x1400161bc`
- `0x14001b8d8`

## callees

- `0x140013a4c`
- `0x140013e14`
- `0x14002138c`
- `0x140023b40`
- `0x140024fe0`
- `0x140045f30`

## import_xrefs

- `DEVRTL!DevRtlWriteTextLog` at `0x140013efb`
- `DEVRTL!DevRtlWriteTextLog` at `0x140013f30`
- `DEVRTL!DevRtlWriteTextLog` at `0x140013efb`
- `DEVRTL!DevRtlWriteTextLog` at `0x140013f30`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x140013e4e`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x140013e4e`
- `drvstore!DriverStoreConfigureW` at `0x140013e73`
- `drvstore!DriverStoreConfigureW` at `0x140013e73`

## pseudocode

```c
__int64 __fastcall InstallDriver(__int64 a1, __int64 a2, int a3, int *a4)
{
  int v7; // edi
  unsigned int v8; // r15d
  __int64 ThreadLogToken; // r14
  unsigned int v10; // eax
  unsigned int v11; // ebx
  __int128 v13; // [rsp+30h] [rbp-A8h] BYREF
  _WORD v14[40]; // [rsp+40h] [rbp-98h] BYREF

  v13 = 0;
  v7 = 0;
  v8 = (a3 & 0xFFFFFF00) << 23;
  ThreadLogToken = DevRtlGetThreadLogToken();
  v10 = DriverStoreConfigureW(a1, a2, 0, 0, 0);
  v11 = v10;
  if ( v10 )
  {
    if ( v10 == 3010 )
    {
      v7 = 1;
LABEL_12:
      v11 = 0;
      goto LABEL_13;
    }
    if ( v10 != 3011 || !(unsigned int)DrvUtilsIsValidPrimitiveDriver(0, a2, 9) )
      return v11;
    if ( !(unsigned int)GetDriverPackageClassGuid(a1, a2, &v13) || (unsigned int)SpUtilsStringFromGuid(&v13, v14) )
    {
      v14[0] = 0;
    }
    else
    {
      DevRtlWriteTextLog(ThreadLogToken, 1, 4, "Restarting all devices in %ws class.", v14);
      if ( !(unsigned int)RestartAllClassDevices(&v13, v8) )
        goto LABEL_12;
    }
    v7 = 1;
    DevRtlWriteTextLog(ThreadLogToken, 1, 2, "Reboot required to restart all devices in class.");
    goto LABEL_12;
  }
LABEL_13:
  if ( a4 )
    *a4 = v7;
  return v11;
}

```

## disassembly

```asm
0x140013e14  push    rbx
0x140013e16  push    rbp
0x140013e17  push    rsi
0x140013e18  push    rdi
0x140013e19  push    r12
0x140013e1b  push    r14
0x140013e1d  push    r15
0x140013e1f  sub     rsp, 0A0h
0x140013e26  mov     rax, cs:__security_cookie
0x140013e2d  xor     rax, rsp
0x140013e30  mov     [rsp+0D8h+var_48], rax
0x140013e38  xorps   xmm0, xmm0
0x140013e3b  mov     rsi, r9
0x140013e3e  movups  [rsp+0D8h+var_A8], xmm0
0x140013e43  mov     r15d, r8d
0x140013e46  mov     rbp, rdx
0x140013e49  mov     r12, rcx
0x140013e4c  xor     edi, edi
0x140013e4e  call    cs:__imp_DevRtlGetThreadLogToken
0x140013e54  and     r15d, 0FFFFFF00h
0x140013e5b  mov     [rsp+0D8h+var_B8], rdi
0x140013e60  xor     r9d, r9d
0x140013e63  shl     r15d, 17h
0x140013e67  xor     r8d, r8d
0x140013e6a  mov     rdx, rbp
0x140013e6d  mov     rcx, r12
0x140013e70  mov     r14, rax
0x140013e73  call    cs:__imp_DriverStoreConfigureW
0x140013e79  mov     ebx, eax
0x140013e7b  test    eax, eax
0x140013e7d  jz      loc_140013F38
0x140013e83  cmp     eax, 0BC2h
0x140013e88  jnz     short loc_140013E94
0x140013e8a  mov     edi, 1
0x140013e8f  jmp     loc_140013F36
0x140013e94  cmp     eax, 0BC3h
0x140013e99  jnz     loc_140013F3F
0x140013e9f  mov     r8d, 9
0x140013ea5  mov     rdx, rbp
0x140013ea8  xor     ecx, ecx
0x140013eaa  call    DrvUtilsIsValidPrimitiveDriver
0x140013eaf  test    eax, eax
0x140013eb1  jz      loc_140013F3F
0x140013eb7  lea     r8, [rsp+0D8h+var_A8]
0x140013ebc  mov     rdx, rbp
0x140013ebf  mov     rcx, r12
0x140013ec2  call    GetDriverPackageClassGuid
0x140013ec7  test    eax, eax
0x140013ec9  jz      short loc_140013F14
0x140013ecb  lea     rdx, [rsp+0D8h+var_98]
0x140013ed0  lea     rcx, [rsp+0D8h+var_A8]
0x140013ed5  call    SpUtilsStringFromGuid
0x140013eda  test    eax, eax
0x140013edc  jnz     short loc_140013F14
0x140013ede  mov     edx, 1
0x140013ee3  lea     rax, [rsp+0D8h+var_98]
0x140013ee8  lea     r9, aRestartingAllD; "Restarting all devices in %ws class."
0x140013eef  mov     [rsp+0D8h+var_B8], rax
0x140013ef4  mov     rcx, r14
0x140013ef7  lea     r8d, [rdx+3]
0x140013efb  call    cs:__imp_DevRtlWriteTextLog
0x140013f01  mov     edx, r15d
0x140013f04  lea     rcx, [rsp+0D8h+var_A8]
0x140013f09  call    RestartAllClassDevices
0x140013f0e  test    eax, eax
0x140013f10  jz      short loc_140013F36
0x140013f12  jmp     short loc_140013F1B
0x140013f14  xor     eax, eax
0x140013f16  mov     [rsp+0D8h+var_98], ax
0x140013f1b  mov     edi, 1
0x140013f20  lea     r9, aRebootRequired_3; "Reboot required to restart all devices "...
0x140013f27  mov     edx, edi
0x140013f29  mov     rcx, r14
0x140013f2c  lea     r8d, [rdi+1]
0x140013f30  call    cs:__imp_DevRtlWriteTextLog
0x140013f36  xor     ebx, ebx
0x140013f38  test    rsi, rsi
0x140013f3b  jz      short loc_140013F3F
0x140013f3d  mov     [rsi], edi
0x140013f3f  mov     eax, ebx
0x140013f41  mov     rcx, [rsp+0D8h+var_48]
0x140013f49  xor     rcx, rsp; StackCookie
0x140013f4c  call    __security_check_cookie
0x140013f51  add     rsp, 0A0h
0x140013f58  pop     r15
0x140013f5a  pop     r14
0x140013f5c  pop     r12
0x140013f5e  pop     rdi
0x140013f5f  pop     rsi
0x140013f60  pop     rbp
0x140013f61  pop     rbx
0x140013f62  retn
```
