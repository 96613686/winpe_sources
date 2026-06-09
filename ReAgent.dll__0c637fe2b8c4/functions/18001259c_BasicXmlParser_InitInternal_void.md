# BasicXmlParser::InitInternal(void)

- ea: `0x18001259c`
- end: `0x18001260d`
- name: `?InitInternal@BasicXmlParser@@AEAAKXZ`
- size: `113`
- prototype: `__int64 __fastcall(BasicXmlParser *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180011f90`
- `0x180012120`

## callees

- `0x1800059fc`
- `0x18001259c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800125f9`
- `ntdll!RtlNtStatusToDosError` at `0x1800125f9`
- `ServicingCommon!RtlCreateUtf8UCSStringBuilder` at `0x1800125b5`
- `ServicingCommon!RtlCreateUtf8UCSStringBuilder` at `0x1800125b5`
- `ServicingCommon!RtlCreateDefaultXmlWriter` at `0x1800125d7`
- `ServicingCommon!RtlCreateDefaultXmlWriter` at `0x1800125d7`

## string_xrefs

- `0x1800125c1`: `RtlCreateUtf8UCSStringBuilder failed: 0x%x`
- `0x1800125e3`: `RtlCreateDefaultXmlWriter failed: 0x%x`

## pseudocode

```c
__int64 __fastcall BasicXmlParser::InitInternal(BasicXmlParser *this)
{
  NTSTATUS Utf8UCSStringBuilder; // ebx
  unsigned int v3; // edi

  Utf8UCSStringBuilder = RtlCreateUtf8UCSStringBuilder(0, 0, (char *)this + 56, (char *)this + 48);
  if ( Utf8UCSStringBuilder < 0 )
  {
    UnattendLogW(1, L"RtlCreateUtf8UCSStringBuilder failed: 0x%x", (unsigned int)Utf8UCSStringBuilder);
    return RtlNtStatusToDosError(Utf8UCSStringBuilder);
  }
  v3 = 0;
  Utf8UCSStringBuilder = RtlCreateDefaultXmlWriter(3, *((_QWORD *)this + 6), (char *)this + 40);
  if ( Utf8UCSStringBuilder < 0 )
  {
    UnattendLogW(1, L"RtlCreateDefaultXmlWriter failed: 0x%x", (unsigned int)Utf8UCSStringBuilder);
    return RtlNtStatusToDosError(Utf8UCSStringBuilder);
  }
  return v3;
}

```

## disassembly

```asm
0x18001259c  push    rbx
0x18001259e  push    rsi
0x18001259f  push    rdi
0x1800125a0  push    r14
0x1800125a2  sub     rsp, 28h
0x1800125a6  mov     rsi, rcx
0x1800125a9  lea     r8, [rcx+38h]
0x1800125ad  lea     r9, [rcx+30h]
0x1800125b1  xor     edx, edx
0x1800125b3  xor     ecx, ecx
0x1800125b5  call    cs:__imp_RtlCreateUtf8UCSStringBuilder
0x1800125bb  mov     ebx, eax
0x1800125bd  test    eax, eax
0x1800125bf  jns     short loc_1800125CA
0x1800125c1  lea     rdx, aRtlcreateutf8u_0; "RtlCreateUtf8UCSStringBuilder failed: 0"...
0x1800125c8  jmp     short loc_1800125EA
0x1800125ca  mov     rdx, [rsi+30h]
0x1800125ce  lea     r8, [rsi+28h]
0x1800125d2  xor     edi, edi
0x1800125d4  lea     ecx, [rdi+3]
0x1800125d7  call    cs:__imp_RtlCreateDefaultXmlWriter
0x1800125dd  mov     ebx, eax
0x1800125df  test    eax, eax
0x1800125e1  jns     short loc_180012601
0x1800125e3  lea     rdx, aRtlcreatedefau_0; "RtlCreateDefaultXmlWriter failed: 0x%x"
0x1800125ea  mov     ecx, 1
0x1800125ef  mov     r8d, ebx
0x1800125f2  call    UnattendLogW
0x1800125f7  mov     ecx, ebx; Status
0x1800125f9  call    cs:__imp_RtlNtStatusToDosError
0x1800125ff  mov     edi, eax
0x180012601  mov     eax, edi
0x180012603  add     rsp, 28h
0x180012607  pop     r14
0x180012609  pop     rdi
0x18001260a  pop     rsi
0x18001260b  pop     rbx
0x18001260c  retn
```
