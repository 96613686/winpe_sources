# ATL::CComTypeInfoHolder::Invoke(IDispatch *,long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x140007438`
- end: `0x1400074d3`
- name: `?Invoke@CComTypeInfoHolder@ATL@@QEAAJPEAUIDispatch@@JAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `155`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *this, struct IDispatch *, unsigned int, const struct _GUID *, LCID lcid, unsigned __int16, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140007360`
- `0x1400073d0`

## callees

- `0x1400069fc`
- `0x140007438`
- `0x140017010`

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
0x140007438  mov     [rsp+arg_0], rbx
0x14000743d  mov     [rsp+arg_8], rsi
0x140007442  push    rdi
0x140007443  sub     rsp, 50h
0x140007447  cmp     qword ptr [rcx+18h], 0
0x14000744c  mov     edi, r8d
0x14000744f  mov     rsi, rdx
0x140007452  mov     rbx, rcx
0x140007455  jz      short loc_14000745F
0x140007457  xor     eax, eax
0x140007459  cmp     [rcx+28h], rax
0x14000745d  jnz     short loc_14000746B
0x14000745f  mov     edx, [rsp+58h+lcid]; lcid
0x140007466  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x14000746b  mov     rcx, [rbx+18h]
0x14000746f  test    rcx, rcx
0x140007472  jz      short loc_1400074C3
0x140007474  mov     rdx, [rsp+58h+arg_48]
0x14000747c  mov     r8d, edi
0x14000747f  mov     rax, [rcx]
0x140007482  movzx   r9d, [rsp+58h+arg_28]
0x14000748b  mov     [rsp+58h+var_20], rdx
0x140007490  mov     rdx, [rsp+58h+arg_40]
0x140007498  mov     rax, [rax+58h]
0x14000749c  mov     [rsp+58h+var_28], rdx
0x1400074a1  mov     rdx, [rsp+58h+arg_38]
0x1400074a9  mov     [rsp+58h+var_30], rdx
0x1400074ae  mov     rdx, [rsp+58h+arg_30]
0x1400074b6  mov     [rsp+58h+var_38], rdx
0x1400074bb  mov     rdx, rsi
0x1400074be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400074c3  mov     rbx, [rsp+58h+arg_0]
0x1400074c8  mov     rsi, [rsp+58h+arg_8]
0x1400074cd  add     rsp, 50h
0x1400074d1  pop     rdi
0x1400074d2  retn
```
