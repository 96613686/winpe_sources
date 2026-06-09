# CRdpIdAdapter::ProcessUnloadAvenc(void)

- ea: `0x18001b644`
- end: `0x18001b6d8`
- name: `?ProcessUnloadAvenc@CRdpIdAdapter@@AEAAXXZ`
- size: `148`
- prototype: `void __fastcall(CRdpIdAdapter *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800185bc`
- `0x18001b584`

## callees

- `0x18001d938`
- `0x18001dd70`
- `0x180020d00`
- `0x180021780`

## string_xrefs

- `0x18001b65c`: `Video encoder dll has not been loaded`

## pseudocode

```c
void __fastcall CRdpIdAdapter::ProcessUnloadAvenc(CRdpIdAdapter *this)
{
  char *v1; // rbx
  __int64 v3; // rdx
  __int64 v4; // r8
  const char *v5; // [rsp+30h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v1 = (char *)this + 416;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0xD25,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
    (const char *)0x80070057LL,
    *((_QWORD *)this + 52) == 0,
    (bool)"Video encoder dll has not been loaded",
    v5);
  CRdpIdAdapter::StopEncodingProcessor(this);
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
    v1,
    0);
  *((_OWORD *)this + 22) = 0;
  *((_OWORD *)this + 23) = 0;
  *((_QWORD *)this + 50) = 0;
  *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 384, v3, v4) = 0;
}

```

## disassembly

```asm
0x18001b644  mov     [rsp+arg_0], rbx
0x18001b649  push    rdi; char *
0x18001b64a  sub     rsp, 30h
0x18001b64e  lea     rbx, [rcx+1A0h]
0x18001b655  mov     rdi, rcx
0x18001b658  cmp     qword ptr [rbx], 0
0x18001b65c  lea     rdx, aVideoEncoderDl; "Video encoder dll has not been loaded"
0x18001b663  mov     rcx, [rsp+38h]; this
0x18001b668  lea     r8, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18001b66f  mov     qword ptr [rsp+38h+var_10], rdx; bool
0x18001b674  setz    al
0x18001b677  mov     r9d, 80070057h; char *
0x18001b67d  mov     [rsp+38h+var_18], al; char
0x18001b681  mov     edx, 0D25h; void *
0x18001b686  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001b68b  mov     rcx, rdi; this
0x18001b68e  call    ?StopEncodingProcessor@CRdpIdAdapter@@AEAAXXZ; CRdpIdAdapter::StopEncodingProcessor(void)
0x18001b693  xor     edx, edx
0x18001b695  mov     rcx, rbx
0x18001b698  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x18001b69d  lea     rcx, [rdi+180h]
0x18001b6a4  xorps   xmm0, xmm0
0x18001b6a7  movdqu  xmmword ptr [rdi+160h], xmm0
0x18001b6af  xorps   xmm1, xmm1
0x18001b6b2  movdqu  xmmword ptr [rdi+170h], xmm1
0x18001b6ba  mov     qword ptr [rcx+10h], 0
0x18001b6c2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001b6c7  mov     rbx, [rsp+38h+arg_0]
0x18001b6cc  xor     ecx, ecx
0x18001b6ce  mov     [rax], cx
0x18001b6d1  add     rsp, 30h
0x18001b6d5  pop     rdi
0x18001b6d6  retn
```
