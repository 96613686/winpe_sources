# UninstallDriver

- ea: `0x140014860`
- end: `0x1400149d9`
- name: `UninstallDriver`
- size: `377`
- prototype: `__int64 __fastcall(__int64, __int64, int, int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x1400161bc`
- `0x14001c2e4`

## callees

- `0x140013a4c`
- `0x140014860`
- `0x14002138c`
- `0x140023b08`
- `0x140023b40`
- `0x140024fe0`
- `0x140045f30`

## import_xrefs

- `DEVRTL!DevRtlWriteTextLog` at `0x140014972`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001499f`
- `DEVRTL!DevRtlWriteTextLog` at `0x140014972`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001499f`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x1400148a1`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x1400148a1`
- `drvstore!DriverStoreUnconfigureW` at `0x1400148fb`
- `drvstore!DriverStoreUnconfigureW` at `0x1400148fb`

## pseudocode

```c
__int64 __fastcall UninstallDriver(__int64 a1, __int64 a2, int a3, int *a4)
{
  int v7; // ebx
  int v8; // edi
  unsigned int v9; // r12d
  __int64 ThreadLogToken; // r15
  __int64 result; // rax
  __int128 v12; // [rsp+30h] [rbp-A8h] BYREF
  _WORD v13[40]; // [rsp+40h] [rbp-98h] BYREF

  v12 = 0;
  v7 = 0;
  v8 = 0;
  v9 = (a3 & 0xFFFFFF00) << 23;
  ThreadLogToken = DevRtlGetThreadLogToken();
  if ( (unsigned int)DrvUtilsIsValidPrimitiveDriver(0, a2, 9) )
  {
    if ( !(unsigned int)GetDriverPackageClassGuid(a1, a2, &v12) )
      v12 = 0;
    v8 = 1;
  }
  result = DriverStoreUnconfigureW(a1, a2, 0, 0, 0);
  if ( !(_DWORD)result )
    goto LABEL_16;
  if ( (_DWORD)result == 3010 )
  {
    v7 = 1;
LABEL_15:
    result = 0;
LABEL_16:
    if ( a4 )
      *a4 = v7;
    return result;
  }
  if ( v8 && (_DWORD)result == 3011 )
  {
    if ( !(unsigned int)SpUtilsIsGuidNull(&v12) )
    {
      if ( (unsigned int)SpUtilsStringFromGuid(&v12, v13) )
      {
        v13[0] = 0;
      }
      else
      {
        DevRtlWriteTextLog(ThreadLogToken, 1, 4, "Restarting all devices in %ws class.", v13);
        if ( !(unsigned int)RestartAllClassDevices(&v12, v9) )
          goto LABEL_15;
      }
    }
    v7 = 1;
    DevRtlWriteTextLog(ThreadLogToken, 1, 2, "Reboot required to restart all devices in class.");
    goto LABEL_15;
  }
  return result;
}

```

## disassembly

```asm
0x140014860  mov     [rsp+arg_10], rbx
0x140014865  push    rbp
0x140014866  push    rsi
0x140014867  push    rdi
0x140014868  push    r12
0x14001486a  push    r13
0x14001486c  push    r14
0x14001486e  push    r15
0x140014870  sub     rsp, 0A0h
0x140014877  mov     rax, cs:__security_cookie
0x14001487e  xor     rax, rsp
0x140014881  mov     [rsp+0D8h+var_48], rax
0x140014889  xorps   xmm0, xmm0
0x14001488c  mov     rsi, r9
0x14001488f  movups  [rsp+0D8h+var_A8], xmm0
0x140014894  mov     r12d, r8d
0x140014897  mov     rbp, rdx
0x14001489a  mov     r14, rcx
0x14001489d  xor     ebx, ebx
0x14001489f  xor     edi, edi
0x1400148a1  call    cs:__imp_DevRtlGetThreadLogToken
0x1400148a7  and     r12d, 0FFFFFF00h
0x1400148ae  lea     r8d, [rbx+9]
0x1400148b2  mov     rdx, rbp
0x1400148b5  shl     r12d, 17h
0x1400148b9  xor     ecx, ecx
0x1400148bb  mov     r15, rax
0x1400148be  call    DrvUtilsIsValidPrimitiveDriver
0x1400148c3  lea     r13d, [rbx+1]
0x1400148c7  test    eax, eax
0x1400148c9  jz      short loc_1400148EA
0x1400148cb  lea     r8, [rsp+0D8h+var_A8]
0x1400148d0  mov     rdx, rbp
0x1400148d3  mov     rcx, r14
0x1400148d6  call    GetDriverPackageClassGuid
0x1400148db  test    eax, eax
0x1400148dd  jnz     short loc_1400148E7
0x1400148df  xorps   xmm0, xmm0
0x1400148e2  movups  [rsp+0D8h+var_A8], xmm0
0x1400148e7  mov     edi, r13d
0x1400148ea  xor     r9d, r9d
0x1400148ed  mov     [rsp+0D8h+var_B8], rbx
0x1400148f2  xor     r8d, r8d
0x1400148f5  mov     rdx, rbp
0x1400148f8  mov     rcx, r14
0x1400148fb  call    cs:__imp_DriverStoreUnconfigureW
0x140014901  test    eax, eax
0x140014903  jz      loc_1400149A7
0x140014909  cmp     eax, 0BC2h
0x14001490e  jnz     short loc_140014918
0x140014910  mov     ebx, r13d
0x140014913  jmp     loc_1400149A5
0x140014918  test    edi, edi
0x14001491a  jz      loc_1400149AE
0x140014920  cmp     eax, 0BC3h
0x140014925  jnz     loc_1400149AE
0x14001492b  lea     rcx, [rsp+0D8h+var_A8]
0x140014930  call    SpUtilsIsGuidNull
0x140014935  test    eax, eax
0x140014937  jnz     short loc_140014989
0x140014939  lea     rdx, [rsp+0D8h+var_98]
0x14001493e  lea     rcx, [rsp+0D8h+var_A8]
0x140014943  call    SpUtilsStringFromGuid
0x140014948  test    eax, eax
0x14001494a  jz      short loc_140014955
0x14001494c  xor     eax, eax
0x14001494e  mov     [rsp+0D8h+var_98], ax
0x140014953  jmp     short loc_140014989
0x140014955  lea     rax, [rsp+0D8h+var_98]
0x14001495a  mov     r8d, 4
0x140014960  lea     r9, aRestartingAllD; "Restarting all devices in %ws class."
0x140014967  mov     [rsp+0D8h+var_B8], rax
0x14001496c  mov     edx, r13d
0x14001496f  mov     rcx, r15
0x140014972  call    cs:__imp_DevRtlWriteTextLog
0x140014978  mov     edx, r12d
0x14001497b  lea     rcx, [rsp+0D8h+var_A8]
0x140014980  call    RestartAllClassDevices
0x140014985  test    eax, eax
0x140014987  jz      short loc_1400149A5
0x140014989  lea     r9, aRebootRequired_3; "Reboot required to restart all devices "...
0x140014990  mov     r8d, 2
0x140014996  mov     edx, r13d
0x140014999  mov     rcx, r15
0x14001499c  mov     ebx, r13d
0x14001499f  call    cs:__imp_DevRtlWriteTextLog
0x1400149a5  xor     eax, eax
0x1400149a7  test    rsi, rsi
0x1400149aa  jz      short loc_1400149AE
0x1400149ac  mov     [rsi], ebx
0x1400149ae  mov     rcx, [rsp+0D8h+var_48]
0x1400149b6  xor     rcx, rsp; StackCookie
0x1400149b9  call    __security_check_cookie
0x1400149be  mov     rbx, [rsp+0D8h+arg_10]
0x1400149c6  add     rsp, 0A0h
0x1400149cd  pop     r15
0x1400149cf  pop     r14
0x1400149d1  pop     r13
0x1400149d3  pop     r12
0x1400149d5  pop     rdi
0x1400149d6  pop     rsi
0x1400149d7  pop     rbp
0x1400149d8  retn
```
