# Rdp::Utils::Graphics::CRenderDevice::GetDxgiDevice(void)

- ea: `0x18002b6c8`
- end: `0x18002b733`
- name: `?GetDxgiDevice@CRenderDevice@Graphics@Utils@Rdp@@QEAAPEAUIDXGIDevice2@@XZ`
- size: `107`
- prototype: `struct IDXGIDevice2 *(Rdp::Utils::Graphics::CRenderDevice *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002badc`

## callees

- `0x18000ead8`
- `0x18001dd50`
- `0x18002b6c8`
- `0x18003f010`

## string_xrefs

- `0x18002b721`: `onecore\internal\sdk\inc\wil\opensource/wil/result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct IDXGIDevice2 *__fastcall Rdp::Utils::Graphics::CRenderDevice::GetDxgiDevice(
        Rdp::Utils::Graphics::CRenderDevice *this)
{
  __int64 v1; // rbx
  __int64 (__fastcall ***v2)(_QWORD, GUID *, __int64 *); // rcx
  int v3; // eax
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF

  v1 = 0;
  v7 = 0;
  v2 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 2);
  if ( v2 )
  {
    v3 = (**v2)(v2, &GUID_05008617_fbfd_4051_a790_144884b4f6a9, &v7);
    if ( v3 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/result_macros.h",
        (const char *)(unsigned int)v3,
        v5);
    v1 = v7;
  }
  else
  {
    v7 = 0;
  }
  wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(&v7);
  return (struct IDXGIDevice2 *)v1;
}

```

## disassembly

```asm
0x18002b6c8  push    rbx; int
0x18002b6ca  sub     rsp, 20h
0x18002b6ce  xor     ebx, ebx
0x18002b6d0  mov     [rsp+28h+arg_0], rbx
0x18002b6d5  mov     rcx, [rcx+10h]
0x18002b6d9  test    rcx, rcx
0x18002b6dc  jz      short loc_18002B705
0x18002b6de  mov     rax, [rcx]
0x18002b6e1  lea     r8, [rsp+28h+arg_0]
0x18002b6e6  lea     rdx, _GUID_05008617_fbfd_4051_a790_144884b4f6a9
0x18002b6ed  mov     rax, [rax]
0x18002b6f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b6f5  mov     rcx, [rsp+28h]; this
0x18002b6fa  test    eax, eax
0x18002b6fc  js      short loc_18002B71E
0x18002b6fe  mov     rbx, [rsp+28h+arg_0]
0x18002b703  jmp     short loc_18002B70A
0x18002b705  mov     [rsp+28h+arg_0], rbx
0x18002b70a  lea     rcx, [rsp+28h+arg_0]
0x18002b70f  call    ??1?$com_ptr_t@UIColorSpaceTransform@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(void)
0x18002b714  mov     rax, rbx
0x18002b717  add     rsp, 20h
0x18002b71b  pop     rbx
0x18002b71c  retn
0x18002b71e  mov     r9d, eax; char *
0x18002b721  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002b728  mov     edx, 1CBEh; void *
0x18002b72d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
