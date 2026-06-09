# CWMDSPPropImpl::CheckRange(ulong,tagPROPVARIANT const &)

- ea: `0x18001ff80`
- end: `0x18002000d`
- name: `?CheckRange@CWMDSPPropImpl@@MEAAHKAEBUtagPROPVARIANT@@@Z`
- size: `141`
- prototype: `__int64 __fastcall(CWMDSPPropImpl *__hidden this, unsigned int, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001ff80`
- `0x1800207a0`
- `0x180022010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001fff5`
- `OLEAUT32!__imp_SysFreeString` at `0x18001fff5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ffe8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ffe8`

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
0x18001ff80  mov     [rsp+arg_0], rbx
0x18001ff85  mov     [rsp+arg_8], rsi
0x18001ff8a  push    rdi
0x18001ff8b  sub     rsp, 30h
0x18001ff8f  cmp     word ptr [r8], 8
0x18001ff94  mov     rbx, r8
0x18001ff97  mov     esi, edx
0x18001ff99  mov     rdi, rcx
0x18001ff9c  jnz     short loc_18001FFA5
0x18001ff9e  mov     eax, 1
0x18001ffa3  jmp     short loc_18001FFFD
0x18001ffa5  xorps   xmm0, xmm0
0x18001ffa8  lea     rdx, [rsp+38h+pv]
0x18001ffad  mov     rcx, rbx
0x18001ffb0  movups  xmmword ptr [rsp+38h+pv], xmm0
0x18001ffb5  call    WMDSPPropValFromVar
0x18001ffba  mov     rax, [rdi]
0x18001ffbd  lea     r8, [rsp+38h+pv]
0x18001ffc2  mov     edx, esi
0x18001ffc4  mov     rcx, rdi
0x18001ffc7  mov     rax, [rax+58h]
0x18001ffcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ffd0  cmp     word ptr [rbx], 8
0x18001ffd4  mov     edi, eax
0x18001ffd6  jz      short loc_18001FFF0
0x18001ffd8  cmp     word ptr [rbx], 41h ; 'A'
0x18001ffdc  jnz     short loc_18001FFFB
0x18001ffde  mov     rcx, [rsp+38h+pv+8]; pv
0x18001ffe3  test    rcx, rcx
0x18001ffe6  jz      short loc_18001FFFB
0x18001ffe8  call    cs:__imp_CoTaskMemFree
0x18001ffee  jmp     short loc_18001FFFB
0x18001fff0  mov     rcx, [rsp+38h+pv]; bstrString
0x18001fff5  call    cs:__imp_SysFreeString
0x18001fffb  mov     eax, edi
0x18001fffd  mov     rbx, [rsp+38h+arg_0]
0x180020002  mov     rsi, [rsp+38h+arg_8]
0x180020007  add     rsp, 30h
0x18002000b  pop     rdi
0x18002000c  retn
```
