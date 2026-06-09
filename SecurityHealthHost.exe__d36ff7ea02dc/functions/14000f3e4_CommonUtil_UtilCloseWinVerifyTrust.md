# CommonUtil::UtilCloseWinVerifyTrust

- ea: `0x14000f3e4`
- end: `0x14000f47f`
- name: `CommonUtil::UtilCloseWinVerifyTrust`
- size: `155`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000ed88`
- `0x14000ee14`
- `0x14000f1bc`

## callees

- `0x1400015f0`
- `0x140003018`
- `0x14000ed88`
- `0x14000f3e4`

## pseudocode

```c
void __fastcall CommonUtil::UtilCloseWinVerifyTrust(__int64 a1)
{
  bool v1; // zf
  GUID v2; // [rsp+20h] [rbp-20h] BYREF

  if ( a1 )
  {
    v1 = *(_QWORD *)(a1 + 56) == 0;
    v2.Data1 = 11191659;
    *(_DWORD *)&v2.Data2 = 298896708;
    *(_DWORD *)v2.Data4 = -1073692020;
    *(_DWORD *)&v2.Data4[4] = -292175281;
    if ( !v1 )
    {
      *(_DWORD *)(a1 + 48) = 2;
      if ( CommonUtil::HrWinVerifyTrust(0, &v2, a1) < 0
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_adde249b3c3e3d6a586c05ab82af40e6_Traceguids);
      }
    }
  }
}

```

## disassembly

```asm
0x14000f3e4  test    rcx, rcx
0x14000f3e7  jz      locret_14000F47E
0x14000f3ed  push    rbp
0x14000f3ee  mov     rbp, rsp
0x14000f3f1  sub     rsp, 40h
0x14000f3f5  mov     rax, cs:__security_cookie
0x14000f3fc  xor     rax, rsp
0x14000f3ff  mov     [rbp+var_10], rax
0x14000f403  cmp     qword ptr [rcx+38h], 0
0x14000f408  mov     [rbp+var_20], 0AAC56Bh
0x14000f40f  mov     [rbp+var_1C], 11D0CD44h
0x14000f416  mov     [rbp+var_18], 0C000C28Ch
0x14000f41d  mov     [rbp+var_14], 0EE95C24Fh
0x14000f424  jz      short loc_14000F46D
0x14000f426  mov     dword ptr [rcx+30h], 2
0x14000f42d  lea     rdx, [rbp+var_20]
0x14000f431  mov     r8, rcx
0x14000f434  xor     ecx, ecx
0x14000f436  call    CommonUtil__HrWinVerifyTrust
0x14000f43b  test    eax, eax
0x14000f43d  jns     short loc_14000F46D
0x14000f43f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f446  lea     rax, WPP_GLOBAL_Control
0x14000f44d  cmp     rcx, rax
0x14000f450  jz      short loc_14000F46D
0x14000f452  test    byte ptr [rcx+1Ch], 1
0x14000f456  jz      short loc_14000F46D
0x14000f458  mov     rcx, [rcx+10h]
0x14000f45c  lea     r8, WPP_adde249b3c3e3d6a586c05ab82af40e6_Traceguids
0x14000f463  mov     edx, 11h
0x14000f468  call    WPP_SF_
0x14000f46d  mov     rcx, [rbp+var_10]
0x14000f471  xor     rcx, rsp; StackCookie
0x14000f474  call    __security_check_cookie
0x14000f479  add     rsp, 40h
0x14000f47d  pop     rbp
0x14000f47e  retn
```
