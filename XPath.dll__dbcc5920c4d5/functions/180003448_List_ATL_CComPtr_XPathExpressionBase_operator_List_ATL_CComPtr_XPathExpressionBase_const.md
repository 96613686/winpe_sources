# List<ATL::CComPtr<XPathExpressionBase>>::operator=(List<ATL::CComPtr<XPathExpressionBase>> const &)

- ea: `0x180003448`
- end: `0x180003491`
- name: `??4?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@QEAAAEAV0@AEBV0@@Z`
- size: `73`
- prototype: ``
- caller_count: `23`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800036f0`
- `0x1800037b0`
- `0x180003870`
- `0x180003940`
- `0x180003a00`
- `0x180003ac0`
- `0x180003b80`
- `0x180003c60`
- `0x180003d20`
- `0x180003e00`
- `0x180003ee0`
- `0x180003fc0`
- `0x180004080`
- `0x180004140`
- `0x180004200`
- `0x1800042c0`
- `0x180004380`
- `0x180004440`
- `0x180004500`
- `0x1800045c0`
- `0x180004680`
- `0x180004750`
- `0x180004830`

## callees

- `0x180003448`
- `0x180004bdc`

## pseudocode

```c
__int64 __fastcall List<ATL::CComPtr<XPathExpressionBase>>::operator=(__int64 a1, __int64 a2)
{
  _DWORD *v4; // rcx

  if ( a1 != a2 )
  {
    List<ATL::CComPtr<XPathExpressionBase>>::Clear(a1);
    v4 = *(_DWORD **)a2;
    *(_QWORD *)a1 = *(_QWORD *)a2;
    *(_QWORD *)(a1 + 8) = *(_QWORD *)(a2 + 8);
    *(_DWORD *)(a1 + 16) = *(_DWORD *)(a2 + 16);
    *(_DWORD *)(a1 + 20) = *(_DWORD *)(a2 + 20);
    if ( v4 )
      ++*v4;
  }
  return a1;
}

```

## disassembly

```asm
0x180003448  mov     [rsp+arg_0], rbx
0x18000344d  push    rdi
0x18000344e  sub     rsp, 20h
0x180003452  mov     rdi, rdx
0x180003455  mov     rbx, rcx
0x180003458  cmp     rcx, rdx
0x18000345b  jz      short loc_180003483
0x18000345d  call    ?Clear@?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@QEAAXXZ; List<ATL::CComPtr<XPathExpressionBase>>::Clear(void)
0x180003462  mov     rcx, [rdi]
0x180003465  mov     [rbx], rcx
0x180003468  mov     rax, [rdi+8]
0x18000346c  mov     [rbx+8], rax
0x180003470  mov     eax, [rdi+10h]
0x180003473  mov     [rbx+10h], eax
0x180003476  mov     eax, [rdi+14h]
0x180003479  mov     [rbx+14h], eax
0x18000347c  test    rcx, rcx
0x18000347f  jz      short loc_180003483
0x180003481  inc     dword ptr [rcx]
0x180003483  mov     rax, rbx
0x180003486  mov     rbx, [rsp+28h+arg_0]
0x18000348b  add     rsp, 20h
0x18000348f  pop     rdi
0x180003490  retn
```
