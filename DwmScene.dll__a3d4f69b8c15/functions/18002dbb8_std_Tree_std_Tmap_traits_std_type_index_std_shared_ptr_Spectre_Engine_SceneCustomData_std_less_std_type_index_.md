# std::_Tree<std::_Tmap_traits<std::type_index,std::shared_ptr<Spectre::Engine::SceneCustomData>,std::less<std::type_index>,std::allocator<std::pair<std::type_index const,std::shared_ptr<Spectre::Engine::SceneCustomData>>>,0>>::_Find_lower_bound<std::type_index>(std::type_index const &)

- ea: `0x18002dbb8`
- end: `0x18002dc3c`
- name: `??$_Find_lower_bound@Vtype_index@std@@@?$_Tree@V?$_Tmap_traits@Vtype_index@std@@V?$shared_ptr@USceneCustomData@Engine@Spectre@@@2@U?$less@Vtype_index@std@@@2@V?$allocator@U?$pair@$$CBVtype_index@std@@V?$shared_ptr@USceneCustomData@Engine@Spectre@@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBVtype_index@std@@V?$shared_ptr@USceneCustomData@Engine@Spectre@@@2@@std@@PEAX@std@@@1@AEBVtype_index@1@@Z`
- size: `132`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002d60c`
- `0x18002e3a4`
- `0x180036de8`

## callees

- `0x18002dbb8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18002dc02`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18002dc02`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<std::type_index,std::shared_ptr<Spectre::Engine::SceneCustomData>,std::less<std::type_index>,std::allocator<std::pair<std::type_index const,std::shared_ptr<Spectre::Engine::SceneCustomData>>>,0>>::_Find_lower_bound<std::type_index>(
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
    if ( (int)__std_type_info_compare(v6[4] + 8, *a3 + 8LL) >= 0 )
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
0x18002dbb8  mov     [rsp+arg_0], rbx
0x18002dbbd  mov     [rsp+arg_8], rsi
0x18002dbc2  push    rdi
0x18002dbc3  sub     rsp, 20h
0x18002dbc7  mov     rax, [rcx]
0x18002dbca  mov     rsi, r8
0x18002dbcd  mov     rdi, rdx
0x18002dbd0  mov     r9, [rax+8]
0x18002dbd4  mov     [rdx], r9
0x18002dbd7  mov     rbx, r9
0x18002dbda  mov     qword ptr [rdx+8], 0
0x18002dbe2  mov     rax, [rcx]
0x18002dbe5  mov     [rdx+10h], rax
0x18002dbe9  cmp     byte ptr [r9+19h], 0
0x18002dbee  jnz     short loc_18002DC29
0x18002dbf0  mov     [rdi], rbx
0x18002dbf3  mov     rdx, [rsi]
0x18002dbf6  mov     rcx, [rbx+20h]
0x18002dbfa  add     rdx, 8
0x18002dbfe  add     rcx, 8
0x18002dc02  call    cs:__imp___std_type_info_compare
0x18002dc08  test    eax, eax
0x18002dc0a  jns     short loc_18002DC14
0x18002dc0c  add     rbx, 10h
0x18002dc10  xor     eax, eax
0x18002dc12  jmp     short loc_18002DC1D
0x18002dc14  mov     [rdi+10h], rbx
0x18002dc18  mov     eax, 1
0x18002dc1d  mov     [rdi+8], eax
0x18002dc20  mov     rbx, [rbx]
0x18002dc23  cmp     byte ptr [rbx+19h], 0
0x18002dc27  jz      short loc_18002DBF0
0x18002dc29  mov     rbx, [rsp+28h+arg_0]
0x18002dc2e  mov     rax, rdi
0x18002dc31  mov     rsi, [rsp+28h+arg_8]
0x18002dc36  add     rsp, 20h
0x18002dc3a  pop     rdi
0x18002dc3b  retn
```
