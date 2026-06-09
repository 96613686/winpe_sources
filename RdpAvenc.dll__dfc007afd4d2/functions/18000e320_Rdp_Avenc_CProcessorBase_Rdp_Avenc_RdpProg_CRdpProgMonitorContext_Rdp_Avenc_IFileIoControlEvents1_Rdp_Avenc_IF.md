# Rdp::Avenc::CProcessorBase<Rdp::Avenc::RdpProg::CRdpProgMonitorContext,Rdp::Avenc::IFileIoControlEvents1,Rdp::Avenc::IFileIoChannelEvents,Rdp::Avenc::ISerializePropertyBag>::OpenPropertyStore(IPropertyStore * *)

- ea: `0x18000e320`
- end: `0x18000e3be`
- name: `?OpenPropertyStore@?$CProcessorBase@VCRdpProgMonitorContext@RdpProg@Avenc@Rdp@@UIFileIoControlEvents1@34@UIFileIoChannelEvents@34@UISerializePropertyBag@34@@Avenc@Rdp@@UEAAJPEAPEAUIPropertyStore@@@Z`
- size: `158`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000e320`
- `0x18000e848`
- `0x18000ec04`
- `0x180089010`

## import_xrefs

- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18000e352`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18000e352`

## string_xrefs

- `0x18000e35d`: `Failed to create property store`
- `0x18000e36c`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\common/ProcessorBase.h`
- `0x18000e3a8`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\common/ProcessorBase.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Rdp::Avenc::CProcessorBase<Rdp::Avenc::RdpProg::CRdpProgMonitorContext,Rdp::Avenc::IFileIoControlEvents1,Rdp::Avenc::IFileIoChannelEvents,Rdp::Avenc::ISerializePropertyBag>::OpenPropertyStore(
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
        (void *)0x99,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/ProcessorBase.h",
        (const char *)0x80004003LL,
        v8);
    v3 = (__int64 *)(a1 + 32);
    if ( !*(_QWORD *)(a1 + 32) )
    {
      *v3 = 0;
      v4 = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, (void **)(a1 + 32));
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0xA4,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/ProcessorBase.h",
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
                           (void *)0xAB,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/ProcessorBase.h",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x18000e320  mov     [rsp+arg_0], rbx
0x18000e325  push    rdi
0x18000e326  sub     rsp, 30h
0x18000e32a  mov     rdi, rdx
0x18000e32d  mov     rax, [rsp+38h]
0x18000e332  test    rdx, rdx
0x18000e335  jz      short loc_18000E3A2
0x18000e337  lea     rbx, [rcx+20h]
0x18000e33b  cmp     qword ptr [rbx], 0
0x18000e33f  jnz     short loc_18000E37D
0x18000e341  mov     qword ptr [rbx], 0
0x18000e348  mov     rdx, rbx; ppv
0x18000e34b  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x18000e352  call    cs:__imp_PSCreateMemoryPropertyStore
0x18000e358  mov     rcx, [rsp+38h]; this
0x18000e35d  lea     rdx, aFailedToCreate_10; "Failed to create property store"
0x18000e364  mov     qword ptr [rsp+38h+var_18], rdx; int
0x18000e369  mov     r9d, eax; char *
0x18000e36c  lea     r8, aOnecoreuapTerm_44; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18000e373  mov     edx, 0A4h; void *
0x18000e378  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000e37d  mov     rcx, [rbx]
0x18000e380  mov     [rdi], rcx
0x18000e383  mov     rax, [rcx]
0x18000e386  mov     rax, [rax+8]
0x18000e38a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e38f  xor     eax, eax
0x18000e391  jmp     short loc_18000E397
0x18000e393  mov     eax, [rsp+38h+arg_8]
0x18000e397  mov     rbx, [rsp+38h+arg_0]
0x18000e39c  add     rsp, 30h
0x18000e3a0  pop     rdi
0x18000e3a1  retn
0x18000e3a2  mov     r9d, 80004003h; char *
0x18000e3a8  lea     r8, aOnecoreuapTerm_44; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18000e3af  mov     edx, 99h; void *
0x18000e3b4  mov     rcx, rax; this
0x18000e3b7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
