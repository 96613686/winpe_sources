# NgcUtils::DoesTPMSupportNgcIso(void)

- ea: `0x180059ee8`
- end: `0x180059fbe`
- name: `?DoesTPMSupportNgcIso@NgcUtils@@YA_NXZ`
- size: `214`
- prototype: `bool __fastcall(NgcUtils *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180059e8c`

## callees

- `0x1800195a0`
- `0x1800299b4`
- `0x18002c640`
- `0x180059ee8`

## import_xrefs

- `tbs!Tbsi_GetDeviceInfo` at `0x180059f0d`
- `tbs!Tbsi_GetDeviceInfo` at `0x180059f0d`

## string_xrefs

- `0x180059f1e`: `onecore\ds\security\ngc\utils\common\lib\velocityutils.cpp`
- `0x180059f5d`: `onecore\ds\security\ngc\utils\common\lib\velocityutils.cpp`
- `0x180059f80`: `onecore\ds\security\ngc\utils\common\lib\velocityutils.cpp`

## pseudocode

```c
char __fastcall NgcUtils::DoesTPMSupportNgcIso(NgcUtils *this)
{
  unsigned int DeviceInfo; // eax
  char *v3; // [rsp+28h] [rbp-30h]
  char *v4[2]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *(_OWORD *)v4 = 0;
  DeviceInfo = Tbsi_GetDeviceInfo(16, v4);
  if ( (int)wil::details::in1diag3::Log_IfFailedWithExpected(
              retaddr,
              (void *)0x8E,
              (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\velocityutils.cpp",
              (const char *)DeviceInfo,
              1,
              15) < 0 )
  {
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x90,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\velocityutils.cpp",
      (const char *)0x80090029LL,
      (int)"TPM not found in the device",
      v3);
    return 0;
  }
  if ( HIDWORD(v4[0]) < 2 )
  {
    LODWORD(v3) = HIDWORD(v4[0]);
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x96,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\velocityutils.cpp",
      (const char *)0x80090029LL,
      (int)"TPM version %d is not supported for NgcIso.",
      v3);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180059ee8  sub     rsp, 58h
0x180059eec  mov     rax, cs:__security_cookie
0x180059ef3  xor     rax, rsp
0x180059ef6  mov     [rsp+58h+var_18], rax
0x180059efb  xorps   xmm0, xmm0
0x180059efe  lea     rdx, [rsp+58h+var_28]
0x180059f03  mov     ecx, 10h
0x180059f08  movups  xmmword ptr [rsp+58h+var_28], xmm0
0x180059f0d  call    cs:__imp_Tbsi_GetDeviceInfo
0x180059f14  nop     dword ptr [rax+rax+00h]
0x180059f19  mov     rcx, [rsp+58h]; this
0x180059f1e  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180059f25  mov     r9d, eax; char *
0x180059f28  mov     dword ptr [rsp+58h+var_30], 8028400Fh; char *
0x180059f30  mov     edx, 8Eh; void *
0x180059f35  mov     [rsp+58h+var_38], 1; int
0x180059f3d  call    ?Log_IfFailedWithExpected@in1diag3@details@wil@@YAJPEAXIPEBDJIZZ; wil::details::in1diag3::Log_IfFailedWithExpected(void *,uint,char const *,long,uint,...)
0x180059f42  test    eax, eax
0x180059f44  jns     short loc_180059F72
0x180059f46  mov     rcx, [rsp+58h]; this
0x180059f4b  lea     rax, aTpmNotFoundInT; "TPM not found in the device"
0x180059f52  mov     r9d, 80090029h; char *
0x180059f58  mov     qword ptr [rsp+58h+var_38], rax; int
0x180059f5d  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180059f64  mov     edx, 90h; void *
0x180059f69  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180059f6e  xor     al, al
0x180059f70  jmp     short loc_180059FAB
0x180059f72  mov     eax, dword ptr [rsp+58h+var_28+4]
0x180059f76  cmp     eax, 2
0x180059f79  jnb     short loc_180059FA9
0x180059f7b  mov     rcx, [rsp+58h]; this
0x180059f80  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180059f87  mov     dword ptr [rsp+58h+var_30], eax; char *
0x180059f8b  mov     r9d, 80090029h; char *
0x180059f91  lea     rax, aTpmVersionDIsN; "TPM version %d is not supported for Ngc"...
0x180059f98  mov     edx, 96h; void *
0x180059f9d  mov     qword ptr [rsp+58h+var_38], rax; int
0x180059fa2  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180059fa7  jmp     short loc_180059F6E
0x180059fa9  mov     al, 1
0x180059fab  mov     rcx, [rsp+58h+var_18]
0x180059fb0  xor     rcx, rsp; StackCookie
0x180059fb3  call    __security_check_cookie
0x180059fb8  add     rsp, 58h
0x180059fbc  retn
```
