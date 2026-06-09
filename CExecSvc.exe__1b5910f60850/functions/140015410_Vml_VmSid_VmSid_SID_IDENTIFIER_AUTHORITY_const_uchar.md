# Vml::VmSid::VmSid(_SID_IDENTIFIER_AUTHORITY const &,uchar,...)

- ea: `0x140015410`
- end: `0x14001548b`
- name: `??0VmSid@Vml@@QEAA@AEBU_SID_IDENTIFIER_AUTHORITY@@EZZ`
- size: `123`
- prototype: `Vml::VmSid *(Vml::VmSid *this, const struct _SID_IDENTIFIER_AUTHORITY *, unsigned __int8, ...)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1400183f8`
- `0x1400188cc`

## callees

- `0x140002310`
- `0x1400165e4`

## pseudocode

```c
Vml::VmSid *Vml::VmSid::VmSid(Vml::VmSid *this, const struct _SID_IDENTIFIER_AUTHORITY *a2, unsigned __int8 a3, ...)
{
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, a3);
  *(_QWORD *)this = 0;
  *((_DWORD *)this + 2) = 7;
  *((_OWORD *)this + 1) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 7;
  *((_WORD *)this + 8) = 0;
  *((_OWORD *)this + 3) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 7;
  *((_WORD *)this + 24) = 0;
  Vml::VmSid::CreateV(this, a2, a3, va);
  return this;
}

```

## disassembly

```asm
0x140015410  mov     r11, rsp
0x140015413  mov     [r11+18h], r8b
0x140015417  mov     [r11+20h], r9
0x14001541b  push    rbx
0x14001541c  sub     rsp, 40h
0x140015420  mov     rax, cs:__security_cookie
0x140015427  xor     rax, rsp
0x14001542a  mov     [rsp+48h+var_18], rax
0x14001542f  mov     rbx, rcx
0x140015432  mov     [r11-28h], rcx
0x140015436  xor     r9d, r9d
0x140015439  mov     [rcx], r9
0x14001543c  lea     ecx, [r9+7]
0x140015440  mov     [rbx+8], ecx
0x140015443  xorps   xmm0, xmm0
0x140015446  movups  xmmword ptr [rbx+10h], xmm0
0x14001544a  mov     [rbx+20h], r9
0x14001544e  mov     [rbx+28h], rcx
0x140015452  mov     [rbx+10h], r9w
0x140015457  movups  xmmword ptr [rbx+30h], xmm0
0x14001545b  mov     [rbx+40h], r9
0x14001545f  mov     [rbx+48h], rcx
0x140015463  mov     [rbx+30h], r9w
0x140015468  lea     r9, [r11+20h]; char *
0x14001546c  mov     rcx, rbx; this
0x14001546f  call    ?CreateV@VmSid@Vml@@AEAAXAEBU_SID_IDENTIFIER_AUTHORITY@@EPEAD@Z; Vml::VmSid::CreateV(_SID_IDENTIFIER_AUTHORITY const &,uchar,char *)
0x140015474  nop
0x140015475  mov     rax, rbx
0x140015478  mov     rcx, [rsp+48h+var_18]
0x14001547d  xor     rcx, rsp; StackCookie
0x140015480  call    __security_check_cookie
0x140015485  add     rsp, 40h
0x140015489  pop     rbx
0x14001548a  retn
```
