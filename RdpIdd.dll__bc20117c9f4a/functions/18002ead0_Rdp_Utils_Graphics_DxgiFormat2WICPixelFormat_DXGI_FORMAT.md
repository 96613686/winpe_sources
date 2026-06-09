# Rdp::Utils::Graphics::DxgiFormat2WICPixelFormat(DXGI_FORMAT)

- ea: `0x18002ead0`
- end: `0x18002eb2a`
- name: `?DxgiFormat2WICPixelFormat@Graphics@Utils@Rdp@@YAAEBU_GUID@@W4DXGI_FORMAT@@@Z`
- size: `90`
- prototype: `const struct _GUID *__fastcall(Rdp::Utils::Graphics *__hidden this, enum DXGI_FORMAT)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002ee40`

## callees

- `0x1800089f0`
- `0x18001ddbc`
- `0x18002ead0`

## string_xrefs

- `0x18002eb05`: `onecoreuap\termsrv\rdp_bin\win\common/inc/GraphicsUtils.h`

## pseudocode

```c
const struct _GUID *__fastcall Rdp::Utils::Graphics::DxgiFormat2WICPixelFormat(
        Rdp::Utils::Graphics *this,
        enum DXGI_FORMAT a2)
{
  unsigned int v3; // eax
  int v4; // edx
  char *v5; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( (_DWORD)this == 10 )
    return &GUID_WICPixelFormat64bppRGBHalf;
  if ( (_DWORD)this != 87 )
  {
    v3 = wil::verify_hresult<long>(2147942487LL);
    LODWORD(v5) = v4;
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x79,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/GraphicsUtils.h",
      (const char *)v3,
      (int)"Unsupported DXGI_FORMAT: %d",
      v5);
  }
  return &GUID_WICPixelFormat32bppPBGRA;
}

```

## disassembly

```asm
0x18002ead0  sub     rsp, 38h
0x18002ead4  mov     edx, ecx
0x18002ead6  cmp     ecx, 0Ah
0x18002ead9  jz      short loc_18002EAE9
0x18002eadb  cmp     ecx, 57h ; 'W'
0x18002eade  jnz     short loc_18002EAF6
0x18002eae0  lea     rax, GUID_WICPixelFormat32bppPBGRA
0x18002eae7  jmp     short loc_18002EAF0
0x18002eae9  lea     rax, GUID_WICPixelFormat64bppRGBHalf
0x18002eaf0  add     rsp, 38h
0x18002eaf4  retn
0x18002eaf6  mov     ecx, 80070057h
0x18002eafb  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002eb00  mov     rcx, [rsp+38h]; this
0x18002eb05  lea     r8, aOnecoreuapTerm_4; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x18002eb0c  mov     dword ptr [rsp+38h+var_10], edx; char *
0x18002eb10  mov     r9d, eax; char *
0x18002eb13  lea     rax, aUnsupportedDxg; "Unsupported DXGI_FORMAT: %d"
0x18002eb1a  mov     edx, 79h ; 'y'; void *
0x18002eb1f  mov     qword ptr [rsp+38h+var_18], rax; int
0x18002eb24  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
