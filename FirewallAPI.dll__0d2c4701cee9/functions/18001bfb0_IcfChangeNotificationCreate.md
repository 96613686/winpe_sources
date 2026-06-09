# IcfChangeNotificationCreate

- ea: `0x18001bfb0`
- end: `0x18001c07b`
- name: `IcfChangeNotificationCreate`
- size: `203`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18001bfb0`
- `0x1800294b0`
- `0x18003336c`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x18001c01c`
- `fwbase!FwHResultToWindowsError` at `0x18001c01c`
- `fwbase!FwChangeSinkCreate` at `0x18001c000`
- `fwbase!FwChangeSinkCreate` at `0x18001c000`
- `fwbase!FwReportReturnError` at `0x18001c04f`
- `fwbase!FwReportReturnError` at `0x18001c04f`

## string_xrefs

- `0x18001c048`: `IcfChangeNotificationCreate`

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
0x18001bfb0  mov     [rsp+arg_10], rbx; FWChangeNotificationCreate
0x18001bfb5  push    rdi
0x18001bfb6  sub     rsp, 30h
0x18001bfba  mov     rax, cs:__security_cookie
0x18001bfc1  xor     rax, rsp
0x18001bfc4  mov     [rsp+38h+var_10], rax
0x18001bfc9  mov     rdi, rdx
0x18001bfcc  mov     [rsp+38h+var_18], 0
0x18001bfd5  mov     rbx, rcx
0x18001bfd8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bfdf  lea     rax, WPP_GLOBAL_Control
0x18001bfe6  cmp     rcx, rax
0x18001bfe9  jz      short loc_18001BFF1
0x18001bfeb  test    byte ptr [rcx+1Ch], 8
0x18001bfef  jnz     short loc_18001C05D
0x18001bff1  test    rdi, rdi
0x18001bff4  jz      short loc_18001C041
0x18001bff6  lea     r8, [rsp+38h+var_18]
0x18001bffb  xor     edx, edx
0x18001bffd  mov     rcx, rbx
0x18001c000  call    cs:__imp_FwChangeSinkCreate
0x18001c007  nop     dword ptr [rax+rax+00h]
0x18001c00c  mov     ebx, eax
0x18001c00e  test    eax, eax
0x18001c010  js      short loc_18001C077
0x18001c012  mov     rax, [rsp+38h+var_18]
0x18001c017  mov     [rdi], rax
0x18001c01a  mov     ecx, ebx
0x18001c01c  call    cs:__imp_FwHResultToWindowsError
0x18001c023  nop     dword ptr [rax+rax+00h]
0x18001c028  mov     rcx, [rsp+38h+var_10]
0x18001c02d  xor     rcx, rsp; StackCookie
0x18001c030  call    __security_check_cookie
0x18001c035  mov     rbx, [rsp+38h+arg_10]
0x18001c03a  add     rsp, 30h
0x18001c03e  pop     rdi
0x18001c03f  retn
0x18001c041  mov     ebx, 80004003h
0x18001c046  mov     edx, ebx
0x18001c048  lea     rcx, aIcfchangenotif_1; "IcfChangeNotificationCreate"
0x18001c04f  call    cs:__imp_FwReportReturnError
0x18001c056  nop     dword ptr [rax+rax+00h]
0x18001c05b  jmp     short loc_18001C01A
0x18001c05d  mov     rcx, [rcx+10h]
0x18001c061  lea     r8, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids
0x18001c068  mov     edx, 0Bh
0x18001c06d  call    WPP_SF_
0x18001c072  jmp     loc_18001BFF1
0x18001c077  mov     edx, eax
0x18001c079  jmp     short loc_18001C048
```
