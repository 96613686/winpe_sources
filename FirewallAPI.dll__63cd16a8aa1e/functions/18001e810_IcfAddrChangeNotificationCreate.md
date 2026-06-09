# IcfAddrChangeNotificationCreate

- ea: `0x18001e810`
- end: `0x18001e8c8`
- name: `IcfAddrChangeNotificationCreate`
- size: `184`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18001e810`
- `0x1800277b0`
- `0x18003104c`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x18001e86c`
- `fwbase!FwHResultToWindowsError` at `0x18001e86c`
- `fwbase!FwChangeSinkCreate` at `0x18001e897`
- `fwbase!FwChangeSinkCreate` at `0x18001e897`
- `fwbase!FwReportReturnError` at `0x18001e864`
- `fwbase!FwReportReturnError` at `0x18001e864`

## string_xrefs

- `0x18001e85d`: `IcfAddrChangeNotificationCreate`

## pseudocode

```c
__int64 __fastcall IcfAddrChangeNotificationCreate(__int64 a1, _QWORD *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  int v7; // eax
  __int64 v8; // [rsp+20h] [rbp-18h] BYREF

  v8 = 0;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids);
  if ( a2 )
  {
    v7 = FwChangeSinkCreate(a1, 1, &v8);
    v4 = v7;
    if ( v7 >= 0 )
    {
      *a2 = v8;
      return FwHResultToWindowsError(v4);
    }
    v5 = (unsigned int)v7;
  }
  else
  {
    v4 = -2147467261;
    v5 = 2147500035LL;
  }
  FwReportReturnError("IcfAddrChangeNotificationCreate", v5);
  return FwHResultToWindowsError(v4);
}

```

## disassembly

```asm
0x18001e810  mov     [rsp+arg_10], rbx
0x18001e815  push    rdi
0x18001e816  sub     rsp, 30h
0x18001e81a  mov     rax, cs:__security_cookie
0x18001e821  xor     rax, rsp
0x18001e824  mov     [rsp+38h+var_10], rax
0x18001e829  mov     rdi, rdx
0x18001e82c  mov     [rsp+38h+var_18], 0
0x18001e835  mov     rbx, rcx
0x18001e838  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e83f  lea     rax, WPP_GLOBAL_Control
0x18001e846  cmp     rcx, rax
0x18001e849  jz      short loc_18001E851
0x18001e84b  test    byte ptr [rcx+1Ch], 8
0x18001e84f  jnz     short loc_18001E8AD
0x18001e851  test    rdi, rdi
0x18001e854  jnz     short loc_18001E88A
0x18001e856  mov     ebx, 80004003h
0x18001e85b  mov     edx, ebx
0x18001e85d  lea     rcx, aIcfaddrchangen_0; "IcfAddrChangeNotificationCreate"
0x18001e864  call    cs:__imp_FwReportReturnError
0x18001e86a  mov     ecx, ebx
0x18001e86c  call    cs:__imp_FwHResultToWindowsError
0x18001e872  mov     rcx, [rsp+38h+var_10]
0x18001e877  xor     rcx, rsp; StackCookie
0x18001e87a  call    __security_check_cookie
0x18001e87f  mov     rbx, [rsp+38h+arg_10]
0x18001e884  add     rsp, 30h
0x18001e888  pop     rdi
0x18001e889  retn
0x18001e88a  lea     r8, [rsp+38h+var_18]
0x18001e88f  mov     edx, 1
0x18001e894  mov     rcx, rbx
0x18001e897  call    cs:__imp_FwChangeSinkCreate
0x18001e89d  mov     ebx, eax
0x18001e89f  test    eax, eax
0x18001e8a1  js      short loc_18001E8C4
0x18001e8a3  mov     rax, [rsp+38h+var_18]
0x18001e8a8  mov     [rdi], rax
0x18001e8ab  jmp     short loc_18001E86A
0x18001e8ad  mov     rcx, [rcx+10h]
0x18001e8b1  lea     r8, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids
0x18001e8b8  mov     edx, 0Dh
0x18001e8bd  call    WPP_SF_
0x18001e8c2  jmp     short loc_18001E851
0x18001e8c4  mov     edx, eax
0x18001e8c6  jmp     short loc_18001E85D
```
