# IcfChangeNotificationCreate

- ea: `0x18001bae0`
- end: `0x18001bb95`
- name: `IcfChangeNotificationCreate`
- size: `181`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18001bae0`
- `0x1800277b0`
- `0x18003104c`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x18001bb46`
- `fwbase!FwHResultToWindowsError` at `0x18001bb46`
- `fwbase!FwChangeSinkCreate` at `0x18001bb30`
- `fwbase!FwChangeSinkCreate` at `0x18001bb30`
- `fwbase!FwReportReturnError` at `0x18001bb72`
- `fwbase!FwReportReturnError` at `0x18001bb72`

## string_xrefs

- `0x18001bb6b`: `IcfChangeNotificationCreate`

## pseudocode

```c
__int64 __fastcall IcfChangeNotificationCreate(__int64 a1, _QWORD *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v7; // rdx
  __int64 v8; // [rsp+20h] [rbp-18h] BYREF

  v8 = 0;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids);
  if ( !a2 )
  {
    v5 = -2147467261;
    v7 = 2147500035LL;
LABEL_9:
    FwReportReturnError("IcfChangeNotificationCreate", v7);
    return FwHResultToWindowsError(v5);
  }
  v4 = FwChangeSinkCreate(a1, 0, &v8);
  v5 = v4;
  if ( v4 < 0 )
  {
    v7 = (unsigned int)v4;
    goto LABEL_9;
  }
  *a2 = v8;
  return FwHResultToWindowsError(v5);
}

```

## disassembly

```asm
0x18001bae0  mov     [rsp+arg_10], rbx; FWChangeNotificationCreate
0x18001bae5  push    rdi
0x18001bae6  sub     rsp, 30h
0x18001baea  mov     rax, cs:__security_cookie
0x18001baf1  xor     rax, rsp
0x18001baf4  mov     [rsp+38h+var_10], rax
0x18001baf9  mov     rdi, rdx
0x18001bafc  mov     [rsp+38h+var_18], 0
0x18001bb05  mov     rbx, rcx
0x18001bb08  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bb0f  lea     rax, WPP_GLOBAL_Control
0x18001bb16  cmp     rcx, rax
0x18001bb19  jz      short loc_18001BB21
0x18001bb1b  test    byte ptr [rcx+1Ch], 8
0x18001bb1f  jnz     short loc_18001BB7A
0x18001bb21  test    rdi, rdi
0x18001bb24  jz      short loc_18001BB64
0x18001bb26  lea     r8, [rsp+38h+var_18]
0x18001bb2b  xor     edx, edx
0x18001bb2d  mov     rcx, rbx
0x18001bb30  call    cs:__imp_FwChangeSinkCreate
0x18001bb36  mov     ebx, eax
0x18001bb38  test    eax, eax
0x18001bb3a  js      short loc_18001BB91
0x18001bb3c  mov     rax, [rsp+38h+var_18]
0x18001bb41  mov     [rdi], rax
0x18001bb44  mov     ecx, ebx
0x18001bb46  call    cs:__imp_FwHResultToWindowsError
0x18001bb4c  mov     rcx, [rsp+38h+var_10]
0x18001bb51  xor     rcx, rsp; StackCookie
0x18001bb54  call    __security_check_cookie
0x18001bb59  mov     rbx, [rsp+38h+arg_10]
0x18001bb5e  add     rsp, 30h
0x18001bb62  pop     rdi
0x18001bb63  retn
0x18001bb64  mov     ebx, 80004003h
0x18001bb69  mov     edx, ebx
0x18001bb6b  lea     rcx, aIcfchangenotif_1; "IcfChangeNotificationCreate"
0x18001bb72  call    cs:__imp_FwReportReturnError
0x18001bb78  jmp     short loc_18001BB44
0x18001bb7a  mov     rcx, [rcx+10h]
0x18001bb7e  lea     r8, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids
0x18001bb85  mov     edx, 0Bh
0x18001bb8a  call    WPP_SF_
0x18001bb8f  jmp     short loc_18001BB21
0x18001bb91  mov     edx, eax
0x18001bb93  jmp     short loc_18001BB6B
```
