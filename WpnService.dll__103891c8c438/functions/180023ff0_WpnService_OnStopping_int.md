# WpnService::OnStopping(int)

- ea: `0x180023ff0`
- end: `0x180024095`
- name: `?OnStopping@WpnService@@UEAAJH@Z`
- size: `165`
- prototype: `__int64 __fastcall(WpnService *__hidden this, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800109d4`
- `0x180023ff0`
- `0x18002409c`
- `0x1800242a0`
- `0x180024344`
- `0x180026200`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180024019`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180024019`

## string_xrefs

- `0x180024028`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\systemservice\dll\wpnservice.cpp`

## pseudocode

```c
__int64 __fastcall WpnService::OnStopping(WpnService *this)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  GUID pguid; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  pguid = 0;
  v2 = CoCreateGuid(&pguid);
  if ( v2 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xD1,
      (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\systemservice\\dll\\wpnservice.cpp",
      (const char *)(unsigned int)v2);
  v5 = (__int64)this + 8;
  ServiceHostTelemetry::StoppingService<unsigned short const *,_GUID &>(&v5, (__int128 *)&pguid);
  LODWORD(v5) = WpnService::OnStoppingHelper(this);
  v6 = (__int64)this + 8;
  v3 = v5;
  ServiceHostTelemetry::StoppedService<unsigned short const *,long &,_GUID &>(&v6, (int *)&v5, (__int128 *)&pguid);
  return v3;
}

```

## disassembly

```asm
0x180023ff0  mov     [rsp+arg_8], rbx
0x180023ff5  push    rdi
0x180023ff6  sub     rsp, 50h
0x180023ffa  mov     rax, cs:__security_cookie
0x180024001  xor     rax, rsp
0x180024004  mov     [rsp+58h+var_18], rax
0x180024009  mov     rbx, rcx
0x18002400c  xorps   xmm0, xmm0
0x18002400f  lea     rcx, [rsp+58h+pguid]; pguid
0x180024014  movups  xmmword ptr [rsp+58h+pguid.Data1], xmm0
0x180024019  call    cs:__imp_CoCreateGuid
0x18002401f  test    eax, eax
0x180024021  jns     short loc_18002403C
0x180024023  mov     rcx, [rsp+58h]; this
0x180024028  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002402f  mov     r9d, eax; char *
0x180024032  mov     edx, 0D1h; void *
0x180024037  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002403c  lea     rdi, [rbx+8]
0x180024040  lea     rdx, [rsp+58h+pguid]
0x180024045  mov     [rsp+58h+var_38], rdi
0x18002404a  lea     rcx, [rsp+58h+var_38]
0x18002404f  call    ??$StoppingService@PEBGAEAU_GUID@@@ServiceHostTelemetry@@SAX$$QEAPEBGAEAU_GUID@@@Z; ServiceHostTelemetry::StoppingService<ushort const *,_GUID &>(ushort const * &&,_GUID &)
0x180024054  mov     rcx, rbx; this
0x180024057  call    ?OnStoppingHelper@WpnService@@AEAAJXZ; WpnService::OnStoppingHelper(void)
0x18002405c  lea     r8, [rsp+58h+pguid]
0x180024061  mov     dword ptr [rsp+58h+var_38], eax
0x180024065  lea     rdx, [rsp+58h+var_38]
0x18002406a  mov     [rsp+58h+var_30], rdi
0x18002406f  lea     rcx, [rsp+58h+var_30]
0x180024074  mov     ebx, eax
0x180024076  call    ??$StoppedService@PEBGAEAJAEAU_GUID@@@ServiceHostTelemetry@@SAX$$QEAPEBGAEAJAEAU_GUID@@@Z; ServiceHostTelemetry::StoppedService<ushort const *,long &,_GUID &>(ushort const * &&,long &,_GUID &)
0x18002407b  mov     eax, ebx
0x18002407d  mov     rcx, [rsp+58h+var_18]
0x180024082  xor     rcx, rsp; StackCookie
0x180024085  call    __security_check_cookie
0x18002408a  mov     rbx, [rsp+58h+arg_8]
0x18002408f  add     rsp, 50h
0x180024093  pop     rdi
0x180024094  retn
```
