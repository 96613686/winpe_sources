# List<ATL::CComPtr<XPathExpressionBase>>::Append(ATL::CComPtr<XPathExpressionBase> &)

- ea: `0x180004aac`
- end: `0x180004b7c`
- name: `?Append@?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@QEAAJAEAV?$CComPtr@VXPathExpressionBase@@@ATL@@@Z`
- size: `208`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180001b20`
- `0x180005550`

## callees

- `0x1800020b4`
- `0x1800032c4`
- `0x180004aac`
- `0x180004b84`
- `0x180004c30`

## pseudocode

```c
__int64 __fastcall List<ATL::CComPtr<XPathExpressionBase>>::Append(__int64 a1, struct IUnknown **a2)
{
  __int64 result; // rax
  struct IUnknown *v5; // rdx
  unsigned int v6; // edx
  unsigned int v7; // edx
  int v8; // edi
  struct IUnknown **v9; // rcx
  struct IUnknown **v10; // rcx
  struct IUnknown *v11; // [rsp+30h] [rbp+8h] BYREF

  if ( !*(_QWORD *)a1
    || **(_DWORD **)a1 == 1
    || (result = List<ATL::CComPtr<XPathExpressionBase>>::CloneBackingStore(a1, *(_DWORD *)(a1 + 20) + 1),
        (int)result >= 0) )
  {
    v5 = *a2;
    if ( *(_DWORD *)(a1 + 20) == *(_DWORD *)(a1 + 16) )
    {
      ATL::CComPtrBase<XPathExpressionBase>::CComPtrBase<XPathExpressionBase>(&v11, v5);
      v6 = *(_DWORD *)(a1 + 20);
      if ( v6 )
      {
        if ( v6 >= 0x2000 )
          v7 = v6 + 4096;
        else
          v7 = 2 * v6;
      }
      else
      {
        v7 = 16;
      }
      if ( v7 > *(_DWORD *)(a1 + 16) )
      {
        v8 = List<ATL::CComPtr<XPathExpressionBase>>::CloneBackingStore(a1, v7);
        if ( v8 < 0 )
        {
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v11);
          return (unsigned int)v8;
        }
      }
      v9 = (struct IUnknown **)(*(_QWORD *)(a1 + 8) + 8LL * *(unsigned int *)(a1 + 20));
      if ( *v9 != v11 )
        ATL::AtlComPtrAssign(v9, v11);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v11);
    }
    else
    {
      v10 = (struct IUnknown **)(*(_QWORD *)(a1 + 8) + 8LL * *(unsigned int *)(a1 + 20));
      if ( *v10 != v5 )
        ATL::AtlComPtrAssign(v10, v5);
    }
    ++*(_DWORD *)(a1 + 20);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180004aac  mov     [rsp+arg_8], rbx
0x180004ab1  push    rdi
0x180004ab2  sub     rsp, 20h
0x180004ab6  mov     rax, [rcx]
0x180004ab9  mov     rdi, rdx
0x180004abc  mov     rbx, rcx
0x180004abf  test    rax, rax
0x180004ac2  jz      short loc_180004ADB
0x180004ac4  cmp     dword ptr [rax], 1
0x180004ac7  jz      short loc_180004ADB
0x180004ac9  mov     edx, [rcx+14h]
0x180004acc  inc     edx
0x180004ace  call    ?CloneBackingStore@?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@AEAAJK@Z; List<ATL::CComPtr<XPathExpressionBase>>::CloneBackingStore(ulong)
0x180004ad3  test    eax, eax
0x180004ad5  js      loc_180004B71
0x180004adb  mov     eax, [rbx+14h]
0x180004ade  mov     rdx, [rdi]; struct IUnknown *
0x180004ae1  cmp     eax, [rbx+10h]
0x180004ae4  jnz     short loc_180004B57
0x180004ae6  lea     rcx, [rsp+28h+arg_0]
0x180004aeb  call    ??0?$CComPtrBase@VXPathExpressionBase@@@ATL@@IEAA@PEAVXPathExpressionBase@@@Z; ATL::CComPtrBase<XPathExpressionBase>::CComPtrBase<XPathExpressionBase>(XPathExpressionBase *)
0x180004af0  mov     edx, [rbx+14h]
0x180004af3  test    edx, edx
0x180004af5  jnz     short loc_180004AFE
0x180004af7  mov     edx, 10h
0x180004afc  jmp     short loc_180004B10
0x180004afe  cmp     edx, 2000h
0x180004b04  jnb     short loc_180004B0A
0x180004b06  add     edx, edx
0x180004b08  jmp     short loc_180004B10
0x180004b0a  add     edx, 1000h
0x180004b10  cmp     edx, [rbx+10h]
0x180004b13  jbe     short loc_180004B31
0x180004b15  mov     rcx, rbx
0x180004b18  call    ?CloneBackingStore@?$List@V?$CComPtr@VXPathExpressionBase@@@ATL@@@@AEAAJK@Z; List<ATL::CComPtr<XPathExpressionBase>>::CloneBackingStore(ulong)
0x180004b1d  mov     edi, eax
0x180004b1f  test    eax, eax
0x180004b21  jns     short loc_180004B31
0x180004b23  lea     rcx, [rsp+28h+arg_0]
0x180004b28  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180004b2d  mov     eax, edi
0x180004b2f  jmp     short loc_180004B71
0x180004b31  mov     ecx, [rbx+14h]
0x180004b34  mov     rax, [rbx+8]
0x180004b38  mov     rdx, [rsp+28h+arg_0]; struct IUnknown *
0x180004b3d  lea     rcx, [rax+rcx*8]; struct IUnknown **
0x180004b41  cmp     [rcx], rdx
0x180004b44  jz      short loc_180004B4B
0x180004b46  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180004b4b  lea     rcx, [rsp+28h+arg_0]
0x180004b50  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180004b55  jmp     short loc_180004B6C
0x180004b57  mov     rcx, rax
0x180004b5a  mov     rax, [rbx+8]
0x180004b5e  lea     rcx, [rax+rcx*8]; struct IUnknown **
0x180004b62  cmp     [rcx], rdx
0x180004b65  jz      short loc_180004B6C
0x180004b67  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180004b6c  inc     dword ptr [rbx+14h]
0x180004b6f  xor     eax, eax
0x180004b71  mov     rbx, [rsp+28h+arg_8]
0x180004b76  add     rsp, 20h
0x180004b7a  pop     rdi
0x180004b7b  retn
```
