# List<ATL::CComPtr<XPathExpressionBase>>::Clear(void)

- ea: `0x180004bdc`
- end: `0x180004c2a`
- name: `?Clear@?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@QEAAXXZ`
- size: `78`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000334c`
- `0x180003448`
- `0x180004c30`
- `0x180005550`
- `0x180009164`
- `0x1800094f4`

## callees

- `0x1800010b8`
- `0x180003498`
- `0x180004bdc`

## pseudocode

```c
void __fastcall List<ATL::CComPtr<XPathExpressionBase>>::Clear(__int64 a1)
{
  _DWORD *v2; // rcx
  __int64 v3; // rcx

  v2 = *(_DWORD **)a1;
  if ( !v2 || *v2 == 1 )
  {
    operator delete(v2);
    v3 = *(_QWORD *)(a1 + 8);
    if ( v3 )
      ATL::CComPtr<XPathExpressionBase>::`vector deleting destructor'(v3);
  }
  else
  {
    --*v2;
  }
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
}

```

## disassembly

```asm
0x180004bdc  push    rbx
0x180004bde  sub     rsp, 20h
0x180004be2  mov     rbx, rcx
0x180004be5  mov     rcx, [rcx]; Block
0x180004be8  test    rcx, rcx
0x180004beb  jz      short loc_180004BFA
0x180004bed  mov     eax, [rcx]
0x180004bef  cmp     eax, 1
0x180004bf2  jz      short loc_180004BFA
0x180004bf4  dec     eax
0x180004bf6  mov     [rcx], eax
0x180004bf8  jmp     short loc_180004C0D
0x180004bfa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004bff  mov     rcx, [rbx+8]
0x180004c03  test    rcx, rcx
0x180004c06  jz      short loc_180004C0D
0x180004c08  call    ??_E?$CComPtr@VXPathExpressionBase@@@ATL@@QEAAPEAXI@Z; ATL::CComPtr<XPathExpressionBase>::`vector deleting destructor'(uint)
0x180004c0d  mov     qword ptr [rbx], 0
0x180004c14  mov     qword ptr [rbx+8], 0
0x180004c1c  mov     qword ptr [rbx+10h], 0
0x180004c24  add     rsp, 20h
0x180004c28  pop     rbx
0x180004c29  retn
```
