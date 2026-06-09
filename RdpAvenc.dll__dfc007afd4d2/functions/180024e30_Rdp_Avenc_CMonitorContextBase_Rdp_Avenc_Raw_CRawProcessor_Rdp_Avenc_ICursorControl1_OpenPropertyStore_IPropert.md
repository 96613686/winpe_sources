# Rdp::Avenc::CMonitorContextBase<Rdp::Avenc::Raw::CRawProcessor,Rdp::Avenc::ICursorControl1>::OpenPropertyStore(IPropertyStore * *)

- ea: `0x180024e30`
- end: `0x180024ece`
- name: `?OpenPropertyStore@?$CMonitorContextBase@VCRawProcessor@Raw@Avenc@Rdp@@UICursorControl1@34@@Avenc@Rdp@@UEAAJPEAPEAUIPropertyStore@@@Z`
- size: `158`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000e848`
- `0x18000ec04`
- `0x180024e30`
- `0x180089010`

## import_xrefs

- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180024e62`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180024e62`

## string_xrefs

- `0x180024e6d`: `Failed to create property store`
- `0x180024e7c`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\common/MonitorContextBase.h`
- `0x180024eb8`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\common/MonitorContextBase.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Rdp::Avenc::CMonitorContextBase<Rdp::Avenc::Raw::CRawProcessor,Rdp::Avenc::ICursorControl1>::OpenPropertyStore(
        __int64 a1,
        __int64 *a2)
{
  __int64 *v3; // rbx
  unsigned int v4; // eax
  __int64 v5; // rcx
  const char *v6; // r9
  __int64 result; // rax
  int v8; // [rsp+20h] [rbp-18h]
  const char *v9; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  try
  {
    if ( !a2 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x92,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/MonitorContextBase.h",
        (const char *)0x80004003LL,
        v8);
    v3 = (__int64 *)(a1 + 24);
    if ( !*(_QWORD *)(a1 + 24) )
    {
      *v3 = 0;
      v4 = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, (void **)(a1 + 24));
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x9D,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/MonitorContextBase.h",
        (const char *)v4,
        (int)"Failed to create property store",
        v9);
    }
    v5 = *v3;
    *a2 = *v3;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xA4,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/MonitorContextBase.h",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x180024e30  mov     [rsp+arg_0], rbx
0x180024e35  push    rdi
0x180024e36  sub     rsp, 30h
0x180024e3a  mov     rdi, rdx
0x180024e3d  mov     rax, [rsp+38h]
0x180024e42  test    rdx, rdx
0x180024e45  jz      short loc_180024EB2
0x180024e47  lea     rbx, [rcx+18h]
0x180024e4b  cmp     qword ptr [rbx], 0
0x180024e4f  jnz     short loc_180024E8D
0x180024e51  mov     qword ptr [rbx], 0
0x180024e58  mov     rdx, rbx; ppv
0x180024e5b  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x180024e62  call    cs:__imp_PSCreateMemoryPropertyStore
0x180024e68  mov     rcx, [rsp+38h]; this
0x180024e6d  lea     rdx, aFailedToCreate_10; "Failed to create property store"
0x180024e74  mov     qword ptr [rsp+38h+var_18], rdx; int
0x180024e79  mov     r9d, eax; char *
0x180024e7c  lea     r8, aOnecoreuapTerm_27; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180024e83  mov     edx, 9Dh; void *
0x180024e88  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180024e8d  mov     rcx, [rbx]
0x180024e90  mov     [rdi], rcx
0x180024e93  mov     rax, [rcx]
0x180024e96  mov     rax, [rax+8]
0x180024e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e9f  xor     eax, eax
0x180024ea1  jmp     short loc_180024EA7
0x180024ea3  mov     eax, [rsp+38h+arg_8]
0x180024ea7  mov     rbx, [rsp+38h+arg_0]
0x180024eac  add     rsp, 30h
0x180024eb0  pop     rdi
0x180024eb1  retn
0x180024eb2  mov     r9d, 80004003h; char *
0x180024eb8  lea     r8, aOnecoreuapTerm_27; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180024ebf  mov     edx, 92h; void *
0x180024ec4  mov     rcx, rax; this
0x180024ec7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
