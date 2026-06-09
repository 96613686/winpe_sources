# SrpUpdatePolicy

- ea: `0x14001fef0`
- end: `0x140020046`
- name: `SrpUpdatePolicy`
- size: `342`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x140022ad0`
- `0x140033f50`

## callees

- `0x140006a20`
- `0x140006f40`
- `0x14001fef0`
- `0x140023c04`
- `0x140023f54`
- `0x140024044`
- `0x1400293ac`
- `0x140036330`
- `0x140036380`

## import_xrefs

- `CI!CiSetTrustedOriginClaimId` at `0x14002002d`
- `CI!CiSetTrustedOriginClaimId` at `0x14002002d`

## string_xrefs

- `0x14001ff9a`: `\REGISTRY\MACHINE\System\CurrentControlSet\Control\AppID\Configuration\SMARTLOCKER`

## pseudocode

```c
__int64 SrpUpdatePolicy()
{
  __int64 result; // rax
  int Policy; // edi
  __int64 PolicyRef; // rax
  __int64 v3; // rcx
  int v4; // eax
  int v5; // ebx
  int v6; // eax
  int v7; // ecx
  int v8; // [rsp+20h] [rbp-E0h] BYREF
  int v9; // [rsp+24h] [rbp-DCh] BYREF
  _QWORD v10[2]; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v11[2]; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v12[3]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v13[368]; // [rsp+60h] [rbp-A0h] BYREF

  memset(v13, 0, 0x168u);
  result = SrpGetPluginFileName((__int64)&v13[192]);
  if ( (int)result >= 0 )
  {
    Policy = SrpReadPolicy(v13);
    if ( Policy >= 0 )
    {
      PolicyRef = AllocatePolicyRef(v13);
      if ( PolicyRef )
      {
        ReplacePolicyRef(PolicyRef);
        v10[0] = 10879140;
        v10[1] = L"\\REGISTRY\\MACHINE\\System\\CurrentControlSet\\Control\\AppID\\Configuration\\SMARTLOCKER";
        v12[0] = 2621478;
        v12[1] = L"TrustedOriginDataId";
        v11[0] = 2621478;
        Policy = 0;
        v11[1] = L"CurrentOriginDataId";
        v8 = 0;
        v9 = 0;
        v4 = AiRegReadDwordValue(v3, v10, v11, &v8);
        v5 = v8;
        if ( v4 < 0 )
          v5 = 0;
        v6 = AiRegReadDwordValue(0, v10, v12, &v9);
        v7 = v9;
        dword_140019720 = v5;
        if ( v6 < 0 )
          v7 = 0;
        dword_140019724 = v7;
        CiSetTrustedOriginClaimId();
        return (unsigned int)Policy;
      }
      Policy = -1073741801;
    }
    SrpFreeGlobalPolicy(v13);
    return (unsigned int)Policy;
  }
  return result;
}

```

## disassembly

```asm
0x14001fef0  push    rbp
0x14001fef2  lea     rbp, [rsp-0E0h]
0x14001fefa  sub     rsp, 1E0h
0x14001ff01  mov     rax, cs:__security_cookie
0x14001ff08  xor     rax, rsp
0x14001ff0b  mov     [rbp+0E0h+var_10], rax
0x14001ff12  xor     edx, edx; Val
0x14001ff14  lea     rcx, [rsp+1E0h+var_180]; void *
0x14001ff19  mov     r8d, 168h; Size
0x14001ff1f  call    memset
0x14001ff24  lea     rcx, [rbp+0E0h+var_C0]
0x14001ff28  call    SrpGetPluginFileName
0x14001ff2d  test    eax, eax
0x14001ff2f  js      short loc_14001FF71
0x14001ff31  lea     rcx, [rsp+1E0h+var_180]
0x14001ff36  mov     [rsp+1E0h+arg_8], rdi
0x14001ff3e  call    SrpReadPolicy
0x14001ff43  mov     edi, eax
0x14001ff45  test    eax, eax
0x14001ff47  js      short loc_14001FF5D
0x14001ff49  lea     rcx, [rsp+1E0h+var_180]
0x14001ff4e  call    AllocatePolicyRef
0x14001ff53  test    rax, rax
0x14001ff56  jnz     short loc_14001FF8A
0x14001ff58  mov     edi, 0C0000017h
0x14001ff5d  lea     rcx, [rsp+1E0h+var_180]
0x14001ff62  call    SrpFreeGlobalPolicy
0x14001ff67  mov     eax, edi
0x14001ff69  mov     rdi, [rsp+1E0h+arg_8]
0x14001ff71  mov     rcx, [rbp+0E0h+var_10]
0x14001ff78  xor     rcx, rsp; StackCookie
0x14001ff7b  call    __security_check_cookie
0x14001ff80  add     rsp, 1E0h
0x14001ff87  pop     rbp
0x14001ff88  retn
0x14001ff8a  mov     rcx, rax
0x14001ff8d  mov     [rsp+1E0h+arg_0], rbx
0x14001ff95  call    ReplacePolicyRef
0x14001ff9a  lea     rax, aRegistryMachin; "\\REGISTRY\\MACHINE\\System\\CurrentCon"...
0x14001ffa1  mov     [rsp+1E0h+var_1B8], 0A600A4h
0x14001ffaa  mov     [rsp+1E0h+var_1B0], rax
0x14001ffaf  lea     r9, [rsp+1E0h+var_1C0]
0x14001ffb4  lea     rax, aTrustedorigind; "TrustedOriginDataId"
0x14001ffbb  mov     [rsp+1E0h+var_198], 280026h
0x14001ffc4  mov     [rsp+1E0h+var_190], rax
0x14001ffc9  lea     r8, [rsp+1E0h+var_1A8]
0x14001ffce  lea     rax, aCurrentorigind; "CurrentOriginDataId"
0x14001ffd5  mov     [rsp+1E0h+var_1A8], 280026h
0x14001ffde  xor     edi, edi
0x14001ffe0  mov     [rsp+1E0h+var_1A0], rax
0x14001ffe5  lea     rdx, [rsp+1E0h+var_1B8]
0x14001ffea  mov     [rsp+1E0h+var_1C0], edi
0x14001ffee  mov     [rsp+1E0h+var_1BC], edi
0x14001fff2  call    AiRegReadDwordValue
0x14001fff7  mov     ebx, [rsp+1E0h+var_1C0]
0x14001fffb  lea     r9, [rsp+1E0h+var_1BC]
0x140020000  xor     ecx, ecx
0x140020002  lea     r8, [rsp+1E0h+var_198]
0x140020007  test    eax, eax
0x140020009  lea     rdx, [rsp+1E0h+var_1B8]
0x14002000e  cmovs   ebx, ecx
0x140020011  call    AiRegReadDwordValue
0x140020016  mov     ecx, [rsp+1E0h+var_1BC]
0x14002001a  xor     edx, edx
0x14002001c  test    eax, eax
0x14002001e  mov     cs:dword_140019720, ebx
0x140020024  cmovs   ecx, edx
0x140020027  mov     cs:dword_140019724, ecx
0x14002002d  call    cs:__imp_CiSetTrustedOriginClaimId
0x140020034  nop     dword ptr [rax+rax+00h]
0x140020039  mov     rbx, [rsp+1E0h+arg_0]
0x140020041  jmp     loc_14001FF67
```
