# FwFieldParserNetworkName(ushort const *,_tag_FW_RULE *)

- ea: `0x18001ad40`
- end: `0x18001ae10`
- name: `?FwFieldParserNetworkName@@YAJPEBGPEAU_tag_FW_RULE@@@Z`
- size: `208`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _tag_FW_RULE *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800042c4`
- `0x18001ad40`
- `0x18001f650`

## import_xrefs

- `fwbase!FwFree` at `0x18001adf0`
- `fwbase!FwFree` at `0x18001adf0`
- `fwbase!FwStringCopy` at `0x18001ad6a`
- `fwbase!FwStringCopy` at `0x18001ad6a`
- `fwbase!FwArrayAppend` at `0x18001adae`
- `fwbase!FwArrayAppend` at `0x18001adae`

## pseudocode

```c
__int64 __fastcall FwFieldParserNetworkName(const unsigned __int16 *a1, struct _tag_FW_RULE *a2)
{
  int v3; // ebx
  LPCOLESTR v4; // rcx
  __int64 v5; // rdx
  __int64 v7; // [rsp+20h] [rbp-18h] BYREF

  v7 = 0;
  v3 = FwStringCopy(a1, &v7);
  if ( v3 < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_10;
    v5 = 18;
LABEL_9:
    WPP_SF_d(*((_QWORD *)v4 + 2), v5, WPP_8aa7cdc55e8b3bac71a43653bf0f119d_Traceguids, (unsigned int)v3);
LABEL_10:
    FwFree(v7);
    return (unsigned int)v3;
  }
  v3 = FwArrayAppend(8, FwCopyIPv4SubNet, (char *)a2 + 400, &v7);
  if ( v3 < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_10;
    v5 = 19;
    goto LABEL_9;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001ad40  mov     [rsp+arg_10], rbx
0x18001ad45  push    rdi
0x18001ad46  sub     rsp, 30h
0x18001ad4a  mov     rax, cs:__security_cookie
0x18001ad51  xor     rax, rsp
0x18001ad54  mov     [rsp+38h+var_10], rax
0x18001ad59  mov     rdi, rdx
0x18001ad5c  mov     [rsp+38h+var_18], 0
0x18001ad65  lea     rdx, [rsp+38h+var_18]
0x18001ad6a  call    cs:__imp_FwStringCopy
0x18001ad70  mov     ebx, eax
0x18001ad72  test    eax, eax
0x18001ad74  jns     short loc_18001AD96
0x18001ad76  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ad7d  lea     rax, WPP_GLOBAL_Control
0x18001ad84  cmp     rcx, rax
0x18001ad87  jz      short loc_18001ADEB
0x18001ad89  test    byte ptr [rcx+1Ch], 1
0x18001ad8d  jz      short loc_18001ADEB
0x18001ad8f  mov     edx, 12h
0x18001ad94  jmp     short loc_18001ADD8
0x18001ad96  lea     r8, [rdi+190h]
0x18001ad9d  mov     ecx, 8
0x18001ada2  lea     r9, [rsp+38h+var_18]
0x18001ada7  lea     rdx, FwCopyIPv4SubNet
0x18001adae  call    cs:__imp_FwArrayAppend
0x18001adb4  mov     ebx, eax
0x18001adb6  test    eax, eax
0x18001adb8  jns     short loc_18001ADF6
0x18001adba  mov     rcx, cs:WPP_GLOBAL_Control
0x18001adc1  lea     rax, WPP_GLOBAL_Control
0x18001adc8  cmp     rcx, rax
0x18001adcb  jz      short loc_18001ADEB
0x18001adcd  test    byte ptr [rcx+1Ch], 1
0x18001add1  jz      short loc_18001ADEB
0x18001add3  mov     edx, 13h
0x18001add8  mov     rcx, [rcx+10h]
0x18001addc  lea     r8, WPP_8aa7cdc55e8b3bac71a43653bf0f119d_Traceguids
0x18001ade3  mov     r9d, ebx
0x18001ade6  call    WPP_SF_d
0x18001adeb  mov     rcx, [rsp+38h+var_18]
0x18001adf0  call    cs:__imp_FwFree
0x18001adf6  mov     eax, ebx
0x18001adf8  mov     rcx, [rsp+38h+var_10]
0x18001adfd  xor     rcx, rsp; StackCookie
0x18001ae00  call    __security_check_cookie
0x18001ae05  mov     rbx, [rsp+38h+arg_10]
0x18001ae0a  add     rsp, 30h
0x18001ae0e  pop     rdi
0x18001ae0f  retn
```
