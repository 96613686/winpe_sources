# CommonUtil::UtilCloseWinVerifyTrust

- ea: `0x140010b20`
- end: `0x140010bbb`
- name: `CommonUtil::UtilCloseWinVerifyTrust`
- size: `155`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140010458`
- `0x1400104e4`
- `0x1400108f8`

## callees

- `0x1400015d0`
- `0x14000536c`
- `0x140010458`
- `0x140010b20`

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
0x140010b20  test    rcx, rcx
0x140010b23  jz      locret_140010BBA
0x140010b29  push    rbp
0x140010b2a  mov     rbp, rsp
0x140010b2d  sub     rsp, 40h
0x140010b31  mov     rax, cs:__security_cookie
0x140010b38  xor     rax, rsp
0x140010b3b  mov     [rbp+var_10], rax
0x140010b3f  cmp     qword ptr [rcx+38h], 0
0x140010b44  mov     [rbp+var_20], 0AAC56Bh
0x140010b4b  mov     [rbp+var_1C], 11D0CD44h
0x140010b52  mov     [rbp+var_18], 0C000C28Ch
0x140010b59  mov     [rbp+var_14], 0EE95C24Fh
0x140010b60  jz      short loc_140010BA9
0x140010b62  mov     dword ptr [rcx+30h], 2
0x140010b69  lea     rdx, [rbp+var_20]
0x140010b6d  mov     r8, rcx
0x140010b70  xor     ecx, ecx
0x140010b72  call    CommonUtil__HrWinVerifyTrust
0x140010b77  test    eax, eax
0x140010b79  jns     short loc_140010BA9
0x140010b7b  mov     rcx, cs:WPP_GLOBAL_Control
0x140010b82  lea     rax, WPP_GLOBAL_Control
0x140010b89  cmp     rcx, rax
0x140010b8c  jz      short loc_140010BA9
0x140010b8e  test    byte ptr [rcx+1Ch], 1
0x140010b92  jz      short loc_140010BA9
0x140010b94  mov     rcx, [rcx+10h]
0x140010b98  lea     r8, WPP_adde249b3c3e3d6a586c05ab82af40e6_Traceguids
0x140010b9f  mov     edx, 11h
0x140010ba4  call    WPP_SF_
0x140010ba9  mov     rcx, [rbp+var_10]
0x140010bad  xor     rcx, rsp; StackCookie
0x140010bb0  call    __security_check_cookie
0x140010bb5  add     rsp, 40h
0x140010bb9  pop     rbp
0x140010bba  retn
```
