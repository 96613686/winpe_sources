# ATL::IDispatchImpl<IBrowserCap,&_GUID const IID_IBrowserCap,&_GUID const LIBID_BrowserType,1,0,ATL::CComTypeInfoHolder>::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x18000851c`
- end: `0x1800085b0`
- name: `?Invoke@?$IDispatchImpl@UIBrowserCap@@$1?IID_IBrowserCap@@3U_GUID@@B$1?LIBID_BrowserType@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `148`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800085c0`

## callees

- `0x180003f7c`
- `0x18000851c`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IBrowserCap,&_GUID const IID_IBrowserCap,&_GUID const LIBID_BrowserType,1,0,ATL::CComTypeInfoHolder>::Invoke(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        LCID a4,
        unsigned __int16 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  struct ITypeInfo *v11; // rcx
  __int64 result; // rax

  v11 = qword_1800120A8;
  if ( !qword_1800120A8 || (result = 0, !qword_1800120B8) )
  {
    result = ATL::CComTypeInfoHolder::GetTI((ATL::CComTypeInfoHolder *)qword_1800120A8, a4);
    v11 = qword_1800120A8;
  }
  if ( v11 )
    return ((__int64 (__fastcall *)(struct ITypeInfo *, __int64, _QWORD, _QWORD, __int64, __int64, __int64, __int64))v11->lpVtbl->Invoke)(
             v11,
             a1,
             a2,
             a5,
             a6,
             a7,
             a8,
             a9);
  return result;
}

```

## disassembly

```asm
0x18000851c  mov     [rsp+arg_0], rbx
0x180008521  push    rdi
0x180008522  sub     rsp, 50h
0x180008526  mov     rdi, rcx
0x180008529  mov     ebx, edx
0x18000852b  mov     rcx, cs:qword_1800120A8; this
0x180008532  test    rcx, rcx
0x180008535  jz      short loc_180008542
0x180008537  xor     eax, eax
0x180008539  cmp     cs:qword_1800120B8, rax
0x180008540  jnz     short loc_180008551
0x180008542  mov     edx, r9d; unsigned int
0x180008545  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x18000854a  mov     rcx, cs:qword_1800120A8
0x180008551  test    rcx, rcx
0x180008554  jz      short loc_1800085A5
0x180008556  mov     rdx, [rsp+58h+arg_40]
0x18000855e  mov     r8d, ebx
0x180008561  mov     rax, [rcx]
0x180008564  movzx   r9d, [rsp+58h+arg_20]
0x18000856d  mov     [rsp+58h+var_20], rdx
0x180008572  mov     rdx, [rsp+58h+arg_38]
0x18000857a  mov     rax, [rax+58h]
0x18000857e  mov     [rsp+58h+var_28], rdx
0x180008583  mov     rdx, [rsp+58h+arg_30]
0x18000858b  mov     [rsp+58h+var_30], rdx
0x180008590  mov     rdx, [rsp+58h+arg_28]
0x180008598  mov     [rsp+58h+var_38], rdx
0x18000859d  mov     rdx, rdi
0x1800085a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085a5  mov     rbx, [rsp+58h+arg_0]
0x1800085aa  add     rsp, 50h
0x1800085ae  pop     rdi
0x1800085af  retn
```
