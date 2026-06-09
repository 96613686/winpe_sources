# Sid::Sid(wchar_t const *)

- ea: `0x18009dca0`
- end: `0x18009dd4a`
- name: `??0Sid@@QEAA@PEB_W@Z`
- size: `170`
- prototype: `Sid *__fastcall(Sid *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18009d72c`

## callees

- `0x180004810`
- `0x1800217ac`
- `0x18002faf0`
- `0x18008fb80`
- `0x18009dca0`
- `0x1800aa650`

## import_xrefs

- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x18009dced`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x18009dced`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
Sid *__fastcall Sid::Sid(Sid *this, const wchar_t *a2)
{
  signed int v3; // eax
  int v5; // [rsp+20h] [rbp-98h] BYREF
  _QWORD v6[3]; // [rsp+28h] [rbp-90h] BYREF
  _BYTE v7[48]; // [rsp+40h] [rbp-78h] BYREF
  _BYTE v8[48]; // [rsp+70h] [rbp-48h] BYREF

  v6[2] = this;
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(this);
  v6[0] = 2228258;
  v6[1] = L"lpacAppExperience";
  v3 = RtlDeriveCapabilitySidsFromName(v6, v8, v7);
  if ( v3 < 0 )
  {
    Exception::Exception((Exception *)&v5, v3 | 0x10000000, v3);
    LogAndThrow<OSException>(&v5, 4475219, 75);
  }
  Sid::CopySidFrom(this, v7);
  return this;
}

```

## disassembly

```asm
0x18009dca0  push    rbx
0x18009dca2  sub     rsp, 0B0h
0x18009dca9  mov     rax, cs:__security_cookie
0x18009dcb0  xor     rax, rsp
0x18009dcb3  mov     [rsp+0B8h+var_18], rax
0x18009dcbb  mov     rbx, rcx
0x18009dcbe  mov     [rsp+0B8h+var_80], rcx
0x18009dcc3  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x18009dcc8  nop
0x18009dcc9  mov     [rsp+0B8h+var_90], 220022h
0x18009dcd2  lea     rax, aLpacappexperie; "lpacAppExperience"
0x18009dcd9  mov     [rsp+0B8h+var_88], rax
0x18009dcde  lea     r8, [rsp+0B8h+var_78]
0x18009dce3  lea     rdx, [rsp+0B8h+var_48]
0x18009dce8  lea     rcx, [rsp+0B8h+var_90]
0x18009dced  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x18009dcf3  test    eax, eax
0x18009dcf5  jns     short loc_18009DD20
0x18009dcf7  mov     edx, eax
0x18009dcf9  bts     edx, 1Ch; int
0x18009dcfd  mov     r8d, eax; unsigned int
0x18009dd00  lea     rcx, [rsp+0B8h+var_98]; this
0x18009dd05  call    ??0Exception@@IEAA@HI@Z; Exception::Exception(int,uint)
0x18009dd0a  mov     edx, 444953h
0x18009dd0f  mov     r8d, 4Bh ; 'K'
0x18009dd15  lea     rcx, [rsp+0B8h+var_98]
0x18009dd1a  call    ??$LogAndThrow@VOSException@@@@YAXAEBVOSException@@VEventTag@@I@Z; LogAndThrow<OSException>(OSException const &,EventTag,uint)
0x18009dd20  lea     rdx, [rsp+0B8h+var_78]; void *
0x18009dd25  mov     rcx, rbx; this
0x18009dd28  call    ?CopySidFrom@Sid@@AEAAXPEAX@Z; Sid::CopySidFrom(void *)
0x18009dd2d  nop
0x18009dd2e  mov     rax, rbx
0x18009dd31  mov     rcx, [rsp+0B8h+var_18]
0x18009dd39  xor     rcx, rsp; StackCookie
0x18009dd3c  call    __security_check_cookie
0x18009dd41  add     rsp, 0B0h
0x18009dd48  pop     rbx
0x18009dd49  retn
```
