# std::_Tree<std::_Tmap_traits<ATL::CComBSTR,CAxISUrlEntry *,AxISCaseInsensitiveLessThan,std::allocator<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>,0>>::_Find_lower_bound<ATL::CComBSTR>(ATL::CComBSTR const &)

- ea: `0x180011b08`
- end: `0x180011b84`
- name: `??$_Find_lower_bound@VCComBSTR@ATL@@@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@PEAVCAxISUrlEntry@@UAxISCaseInsensitiveLessThan@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@@std@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@std@@@1@AEBVCComBSTR@ATL@@@Z`
- size: `124`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800119a4`
- `0x180011ee0`

## callees

- `0x180011b08`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180011b4a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180011b4a`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<ATL::CComBSTR,CAxISUrlEntry *,AxISCaseInsensitiveLessThan,std::allocator<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>,0>>::_Find_lower_bound<ATL::CComBSTR>(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  __int64 *v5; // r9
  __int64 *v6; // rbx
  int v7; // eax

  v5 = *(__int64 **)(*(_QWORD *)a1 + 8LL);
  *a2 = v5;
  v6 = v5;
  a2[1] = 0;
  for ( a2[2] = *(_QWORD *)a1; !*((_BYTE *)v6 + 25); v6 = (__int64 *)*v6 )
  {
    *a2 = v6;
    if ( (int)_o__wcsicmp(v6[4], *a3) >= 0 )
    {
      a2[2] = v6;
      v7 = 1;
    }
    else
    {
      v6 += 2;
      v7 = 0;
    }
    *((_DWORD *)a2 + 2) = v7;
  }
  return a2;
}

```

## disassembly

```asm
0x180011b08  mov     [rsp+arg_0], rbx
0x180011b0d  mov     [rsp+arg_8], rsi
0x180011b12  push    rdi
0x180011b13  sub     rsp, 20h
0x180011b17  mov     rax, [rcx]
0x180011b1a  mov     rsi, r8
0x180011b1d  mov     rdi, rdx
0x180011b20  mov     r9, [rax+8]
0x180011b24  mov     [rdx], r9
0x180011b27  mov     rbx, r9
0x180011b2a  mov     qword ptr [rdx+8], 0
0x180011b32  mov     rax, [rcx]
0x180011b35  mov     [rdx+10h], rax
0x180011b39  cmp     byte ptr [r9+19h], 0
0x180011b3e  jnz     short loc_180011B71
0x180011b40  mov     [rdi], rbx
0x180011b43  mov     rdx, [rsi]
0x180011b46  mov     rcx, [rbx+20h]
0x180011b4a  call    cs:__imp__o__wcsicmp
0x180011b50  test    eax, eax
0x180011b52  jns     short loc_180011B5C
0x180011b54  add     rbx, 10h
0x180011b58  xor     eax, eax
0x180011b5a  jmp     short loc_180011B65
0x180011b5c  mov     [rdi+10h], rbx
0x180011b60  mov     eax, 1
0x180011b65  mov     [rdi+8], eax
0x180011b68  mov     rbx, [rbx]
0x180011b6b  cmp     byte ptr [rbx+19h], 0
0x180011b6f  jz      short loc_180011B40
0x180011b71  mov     rbx, [rsp+28h+arg_0]
0x180011b76  mov     rax, rdi
0x180011b79  mov     rsi, [rsp+28h+arg_8]
0x180011b7e  add     rsp, 20h
0x180011b82  pop     rdi
0x180011b83  retn
```
