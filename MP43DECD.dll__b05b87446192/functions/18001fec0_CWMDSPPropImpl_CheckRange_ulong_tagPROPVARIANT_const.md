# CWMDSPPropImpl::CheckRange(ulong,tagPROPVARIANT const &)

- ea: `0x18001fec0`
- end: `0x18001ff4d`
- name: `?CheckRange@CWMDSPPropImpl@@MEAAHKAEBUtagPROPVARIANT@@@Z`
- size: `141`
- prototype: `__int64 __fastcall(CWMDSPPropImpl *__hidden this, unsigned int, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001fec0`
- `0x1800206e0`
- `0x180022010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001ff35`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ff35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ff28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ff28`

## pseudocode

```c
__int64 __fastcall CWMDSPPropImpl::CheckRange(CWMDSPPropImpl *this, unsigned int a2, const struct tagPROPVARIANT *a3)
{
  unsigned int v7; // edi
  BSTR pv[3]; // [rsp+20h] [rbp-18h] BYREF

  if ( a3->vt == 8 )
    return 1;
  *(_OWORD *)pv = 0;
  WMDSPPropValFromVar((__int64)a3, pv);
  v7 = (*(__int64 (__fastcall **)(CWMDSPPropImpl *, _QWORD, BSTR *))(*(_QWORD *)this + 88LL))(this, a2, pv);
  if ( a3->vt == 8 )
  {
    SysFreeString(pv[0]);
  }
  else if ( a3->vt == 65 )
  {
    if ( pv[1] )
      CoTaskMemFree(pv[1]);
  }
  return v7;
}

```

## disassembly

```asm
0x18001fec0  mov     [rsp+arg_0], rbx
0x18001fec5  mov     [rsp+arg_8], rsi
0x18001feca  push    rdi
0x18001fecb  sub     rsp, 30h
0x18001fecf  cmp     word ptr [r8], 8
0x18001fed4  mov     rbx, r8
0x18001fed7  mov     esi, edx
0x18001fed9  mov     rdi, rcx
0x18001fedc  jnz     short loc_18001FEE5
0x18001fede  mov     eax, 1
0x18001fee3  jmp     short loc_18001FF3D
0x18001fee5  xorps   xmm0, xmm0
0x18001fee8  lea     rdx, [rsp+38h+pv]
0x18001feed  mov     rcx, rbx
0x18001fef0  movups  xmmword ptr [rsp+38h+pv], xmm0
0x18001fef5  call    WMDSPPropValFromVar
0x18001fefa  mov     rax, [rdi]
0x18001fefd  lea     r8, [rsp+38h+pv]
0x18001ff02  mov     edx, esi
0x18001ff04  mov     rcx, rdi
0x18001ff07  mov     rax, [rax+58h]
0x18001ff0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff10  cmp     word ptr [rbx], 8
0x18001ff14  mov     edi, eax
0x18001ff16  jz      short loc_18001FF30
0x18001ff18  cmp     word ptr [rbx], 41h ; 'A'
0x18001ff1c  jnz     short loc_18001FF3B
0x18001ff1e  mov     rcx, [rsp+38h+pv+8]; pv
0x18001ff23  test    rcx, rcx
0x18001ff26  jz      short loc_18001FF3B
0x18001ff28  call    cs:__imp_CoTaskMemFree
0x18001ff2e  jmp     short loc_18001FF3B
0x18001ff30  mov     rcx, [rsp+38h+pv]; bstrString
0x18001ff35  call    cs:__imp_SysFreeString
0x18001ff3b  mov     eax, edi
0x18001ff3d  mov     rbx, [rsp+38h+arg_0]
0x18001ff42  mov     rsi, [rsp+38h+arg_8]
0x18001ff47  add     rsp, 30h
0x18001ff4b  pop     rdi
0x18001ff4c  retn
```
