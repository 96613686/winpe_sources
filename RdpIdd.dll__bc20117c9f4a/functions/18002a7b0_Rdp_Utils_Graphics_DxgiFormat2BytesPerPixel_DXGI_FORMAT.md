# Rdp::Utils::Graphics::DxgiFormat2BytesPerPixel(DXGI_FORMAT)

- ea: `0x18002a7b0`
- end: `0x18002a804`
- name: `?DxgiFormat2BytesPerPixel@Graphics@Utils@Rdp@@YAIW4DXGI_FORMAT@@@Z`
- size: `84`
- prototype: `unsigned int __fastcall(Rdp::Utils::Graphics *__hidden this, enum DXGI_FORMAT)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800299ac`
- `0x180029c18`

## callees

- `0x1800089f0`
- `0x18001ddbc`
- `0x18002a7b0`

## string_xrefs

- `0x18002a7df`: `onecoreuap\termsrv\rdp_bin\win\common/inc/GraphicsUtils.h`

## pseudocode

```c
__int64 __fastcall Rdp::Utils::Graphics::DxgiFormat2BytesPerPixel(Rdp::Utils::Graphics *this, enum DXGI_FORMAT a2)
{
  unsigned int v3; // eax
  int v4; // edx
  char *v5; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( (_DWORD)this == 10 )
    return 8;
  if ( (_DWORD)this != 87 )
  {
    v3 = wil::verify_hresult<long>(2147942487LL);
    LODWORD(v5) = v4;
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x89,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/GraphicsUtils.h",
      (const char *)v3,
      (int)"Unsupported DXGI_FORMAT: %d",
      v5);
  }
  return 4;
}

```

## disassembly

```asm
0x18002a7b0  sub     rsp, 38h
0x18002a7b4  mov     edx, ecx
0x18002a7b6  cmp     ecx, 0Ah
0x18002a7b9  jz      short loc_18002A7C5
0x18002a7bb  cmp     ecx, 57h ; 'W'
0x18002a7be  jnz     short loc_18002A7D0
0x18002a7c0  lea     eax, [rcx-53h]
0x18002a7c3  jmp     short loc_18002A7CA
0x18002a7c5  mov     eax, 8
0x18002a7ca  add     rsp, 38h
0x18002a7ce  retn
0x18002a7d0  mov     ecx, 80070057h
0x18002a7d5  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002a7da  mov     rcx, [rsp+38h]; this
0x18002a7df  lea     r8, aOnecoreuapTerm_4; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x18002a7e6  mov     dword ptr [rsp+38h+var_10], edx; char *
0x18002a7ea  mov     r9d, eax; char *
0x18002a7ed  lea     rax, aUnsupportedDxg; "Unsupported DXGI_FORMAT: %d"
0x18002a7f4  mov     edx, 89h; void *
0x18002a7f9  mov     qword ptr [rsp+38h+var_18], rax; int
0x18002a7fe  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
