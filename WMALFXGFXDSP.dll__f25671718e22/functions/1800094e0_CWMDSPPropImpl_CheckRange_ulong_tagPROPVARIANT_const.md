# CWMDSPPropImpl::CheckRange(ulong,tagPROPVARIANT const &)

- ea: `0x1800094e0`
- end: `0x18000956e`
- name: `?CheckRange@CWMDSPPropImpl@@MEAAHKAEBUtagPROPVARIANT@@@Z`
- size: `142`
- prototype: `__int64 __fastcall(CWMDSPPropImpl *__hidden this, unsigned int, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800094e0`
- `0x180009574`
- `0x180086010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009552`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009552`
- `OLEAUT32!__imp_SysFreeString` at `0x180009566`
- `OLEAUT32!__imp_SysFreeString` at `0x180009566`

## pseudocode

```c
__int64 __fastcall CWMDSPPropImpl::CheckRange(CWMDSPPropImpl *this, unsigned int a2, const struct tagPROPVARIANT *a3)
{
  unsigned int v6; // edi
  BSTR bstrString[3]; // [rsp+20h] [rbp-18h] BYREF

  if ( a3->vt == 8 )
    return 1;
  *(_OWORD *)bstrString = 0;
  WMDSPPropValFromVar((__int64)a3, bstrString);
  v6 = (*(__int64 (__fastcall **)(CWMDSPPropImpl *, _QWORD, BSTR *))(*(_QWORD *)this + 88LL))(this, a2, bstrString);
  if ( a3->vt == 8 )
  {
    SysFreeString(bstrString[0]);
  }
  else if ( a3->vt == 65 )
  {
    if ( bstrString[1] )
      CoTaskMemFree(bstrString[1]);
  }
  return v6;
}

```

## disassembly

```asm
0x1800094e0  mov     rax, rsp
0x1800094e3  mov     [rax+8], rbx
0x1800094e7  mov     [rax+10h], rsi
0x1800094eb  push    rdi
0x1800094ec  sub     rsp, 30h
0x1800094f0  cmp     word ptr [r8], 8
0x1800094f5  mov     rbx, r8
0x1800094f8  mov     esi, edx
0x1800094fa  mov     rdi, rcx
0x1800094fd  jz      short loc_18000955A
0x1800094ff  xorps   xmm0, xmm0
0x180009502  lea     rdx, [rax-18h]
0x180009506  mov     rcx, rbx
0x180009509  movups  xmmword ptr [rax-18h], xmm0
0x18000950d  call    WMDSPPropValFromVar
0x180009512  mov     rax, [rdi]
0x180009515  lea     r8, [rsp+38h+bstrString]
0x18000951a  mov     edx, esi
0x18000951c  mov     rcx, rdi
0x18000951f  mov     rax, [rax+58h]
0x180009523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009528  cmp     word ptr [rbx], 8
0x18000952c  mov     edi, eax
0x18000952e  jz      short loc_180009561
0x180009530  cmp     word ptr [rbx], 41h ; 'A'
0x180009534  jz      short loc_180009548
0x180009536  mov     eax, edi
0x180009538  mov     rbx, [rsp+38h+arg_0]
0x18000953d  mov     rsi, [rsp+38h+arg_8]
0x180009542  add     rsp, 30h
0x180009546  pop     rdi
0x180009547  retn
0x180009548  mov     rcx, [rsp+38h+pv]; pv
0x18000954d  test    rcx, rcx
0x180009550  jz      short loc_180009536
0x180009552  call    cs:__imp_CoTaskMemFree
0x180009558  jmp     short loc_180009536
0x18000955a  mov     eax, 1
0x18000955f  jmp     short loc_180009538
0x180009561  mov     rcx, [rsp+38h+bstrString]; bstrString
0x180009566  call    cs:__imp_SysFreeString
0x18000956c  jmp     short loc_180009536
```
