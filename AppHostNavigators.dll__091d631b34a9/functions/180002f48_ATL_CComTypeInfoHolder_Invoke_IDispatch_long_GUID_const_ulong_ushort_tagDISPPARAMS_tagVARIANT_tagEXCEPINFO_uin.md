# ATL::CComTypeInfoHolder::Invoke(IDispatch *,long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x180002f48`
- end: `0x180002fe3`
- name: `?Invoke@CComTypeInfoHolder@ATL@@QEAAJPEAUIDispatch@@JAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `155`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, struct IDispatch *, int, const struct _GUID *, LCID lcid, unsigned __int16, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, unsigned int *)`
- caller_count: `7`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180002ee0`
- `0x1800051a0`
- `0x180006230`
- `0x180006e50`
- `0x180008080`
- `0x1800093f0`
- `0x180009810`

## callees

- `0x180002ae0`
- `0x180002f48`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::Invoke(
        ATL::CComTypeInfoHolder *this,
        struct IDispatch *a2,
        unsigned int a3,
        const struct _GUID *a4,
        LCID lcid,
        unsigned __int16 a6,
        struct tagDISPPARAMS *a7,
        struct tagVARIANT *a8,
        struct tagEXCEPINFO *a9,
        unsigned int *a10)
{
  __int64 result; // rax
  __int64 v14; // rcx

  if ( !*((_QWORD *)this + 3) || (result = 0, !*((_QWORD *)this + 5)) )
    result = ATL::CComTypeInfoHolder::GetTI(this, lcid);
  v14 = *((_QWORD *)this + 3);
  if ( v14 )
    return (*(__int64 (__fastcall **)(__int64, struct IDispatch *, _QWORD, _QWORD, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, unsigned int *))(*(_QWORD *)v14 + 88LL))(
             v14,
             a2,
             a3,
             a6,
             a7,
             a8,
             a9,
             a10);
  return result;
}

```

## disassembly

```asm
0x180002f48  mov     [rsp+arg_0], rbx
0x180002f4d  mov     [rsp+arg_8], rsi
0x180002f52  push    rdi
0x180002f53  sub     rsp, 50h
0x180002f57  cmp     qword ptr [rcx+18h], 0
0x180002f5c  mov     edi, r8d
0x180002f5f  mov     rsi, rdx
0x180002f62  mov     rbx, rcx
0x180002f65  jz      short loc_180002F6F
0x180002f67  xor     eax, eax
0x180002f69  cmp     [rcx+28h], rax
0x180002f6d  jnz     short loc_180002F7B
0x180002f6f  mov     edx, [rsp+58h+lcid]; lcid
0x180002f76  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x180002f7b  mov     rcx, [rbx+18h]
0x180002f7f  test    rcx, rcx
0x180002f82  jz      short loc_180002FD3
0x180002f84  mov     rdx, [rsp+58h+arg_48]
0x180002f8c  mov     r8d, edi
0x180002f8f  mov     rax, [rcx]
0x180002f92  movzx   r9d, [rsp+58h+arg_28]
0x180002f9b  mov     [rsp+58h+var_20], rdx
0x180002fa0  mov     rdx, [rsp+58h+arg_40]
0x180002fa8  mov     rax, [rax+58h]
0x180002fac  mov     [rsp+58h+var_28], rdx
0x180002fb1  mov     rdx, [rsp+58h+arg_38]
0x180002fb9  mov     [rsp+58h+var_30], rdx
0x180002fbe  mov     rdx, [rsp+58h+arg_30]
0x180002fc6  mov     [rsp+58h+var_38], rdx
0x180002fcb  mov     rdx, rsi
0x180002fce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fd3  mov     rbx, [rsp+58h+arg_0]
0x180002fd8  mov     rsi, [rsp+58h+arg_8]
0x180002fdd  add     rsp, 50h
0x180002fe1  pop     rdi
0x180002fe2  retn
```
