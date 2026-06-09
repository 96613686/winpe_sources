# CredUIBrokerTelemetry::LogBadOwnerWindow(CredUIBrokerTelemetry::BadWindowType)

- ea: `0x14000ee08`
- end: `0x14000ee46`
- name: `?LogBadOwnerWindow@CredUIBrokerTelemetry@@SAXW4BadWindowType@1@@Z`
- size: `62`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000f14c`

## callees

- `0x140009cfc`
- `0x14000ee08`
- `0x140017f90`

## string_xrefs

- `0x14000ee2d`: `pcshell\shell\auth\creduibroker\exe\CredUIBrokerTelemetry.h`

## pseudocode

```c
void __fastcall CredUIBrokerTelemetry::LogBadOwnerWindow(int a1, __int64 a2)
{
  int v2; // eax
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int v5; // [rsp+30h] [rbp+8h] BYREF
  int *v6; // [rsp+38h] [rbp+10h] BYREF

  v5 = a1;
  v6 = &v5;
  v2 = _lambda_77fac54a0df37977b8af88e4a8690683_::operator()(&v6, a2);
  if ( v2 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x57,
      (unsigned int)"pcshell\\shell\\auth\\creduibroker\\exe\\CredUIBrokerTelemetry.h",
      (const char *)(unsigned int)v2,
      v3);
}

```

## disassembly

```asm
0x14000ee08  mov     [rsp+arg_0], ecx
0x14000ee0c  sub     rsp, 28h
0x14000ee10  lea     rax, [rsp+28h+arg_0]
0x14000ee15  lea     rcx, [rsp+28h+arg_8]
0x14000ee1a  mov     [rsp+28h+arg_8], rax
0x14000ee1f  call    ??R_lambda_77fac54a0df37977b8af88e4a8690683_@@QEBAJXZ; _lambda_77fac54a0df37977b8af88e4a8690683_::operator()(void)
0x14000ee24  test    eax, eax
0x14000ee26  jns     short loc_14000EE41
0x14000ee28  mov     rcx, [rsp+28h]; this
0x14000ee2d  lea     r8, aPcshellShellAu; "pcshell\\shell\\auth\\creduibroker\\exe"...
0x14000ee34  mov     r9d, eax; char *
0x14000ee37  mov     edx, 57h ; 'W'; void *
0x14000ee3c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14000ee41  add     rsp, 28h
0x14000ee45  retn
```
