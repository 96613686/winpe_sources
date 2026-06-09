# std::_Tree<std::_Tset_traits<WindowsStorage::Utilities::registry_key_entry,std::less<WindowsStorage::Utilities::registry_key_entry>,std::allocator<WindowsStorage::Utilities::registry_key_entry>,0>>::_Find_lower_bound<WindowsStorage::Utilities::registry_key_entry>(WindowsStorage::Utilities::registry_key_entry const &)

- ea: `0x18000b974`
- end: `0x18000ba1a`
- name: `??$_Find_lower_bound@Vregistry_key_entry@Utilities@WindowsStorage@@@?$_Tree@V?$_Tset_traits@Vregistry_key_entry@Utilities@WindowsStorage@@U?$less@Vregistry_key_entry@Utilities@WindowsStorage@@@std@@V?$allocator@Vregistry_key_entry@Utilities@WindowsStorage@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@Vregistry_key_entry@Utilities@WindowsStorage@@PEAX@std@@@1@AEBVregistry_key_entry@Utilities@WindowsStorage@@@Z`
- size: `166`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b4d0`

## callees

- `0x18000b974`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000b9df`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000b9df`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tset_traits<WindowsStorage::Utilities::registry_key_entry,std::less<WindowsStorage::Utilities::registry_key_entry>,std::allocator<WindowsStorage::Utilities::registry_key_entry>,0>>::_Find_lower_bound<WindowsStorage::Utilities::registry_key_entry>(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  __int64 *v5; // r9
  __int64 *v6; // rbx
  const WCHAR **v7; // rax
  const WCHAR *v8; // r8
  const WCHAR **v9; // rax
  const WCHAR *v10; // rcx
  int v11; // eax

  v5 = *(__int64 **)(*(_QWORD *)a1 + 8LL);
  *a2 = v5;
  v6 = v5;
  a2[1] = 0;
  for ( a2[2] = *(_QWORD *)a1; !*((_BYTE *)v6 + 25); v6 = (__int64 *)*v6 )
  {
    *a2 = v6;
    v7 = *(const WCHAR ***)(a3 + 8);
    if ( v7 )
      v8 = *v7;
    else
      v8 = 0;
    v9 = (const WCHAR **)v6[5];
    if ( v9 )
      v10 = *v9;
    else
      v10 = 0;
    if ( CompareStringOrdinal(v10, -1, v8, -1, 1) == 1 )
    {
      v6 += 2;
      v11 = 0;
    }
    else
    {
      a2[2] = v6;
      v11 = 1;
    }
    *((_DWORD *)a2 + 2) = v11;
  }
  return a2;
}

```

## disassembly

```asm
0x18000b974  mov     [rsp+arg_0], rbx
0x18000b979  mov     [rsp+arg_8], rsi
0x18000b97e  push    rdi
0x18000b97f  sub     rsp, 30h
0x18000b983  mov     rax, [rcx]
0x18000b986  mov     rsi, r8
0x18000b989  mov     rdi, rdx
0x18000b98c  mov     r9, [rax+8]
0x18000b990  mov     [rdx], r9
0x18000b993  mov     rbx, r9
0x18000b996  mov     qword ptr [rdx+8], 0
0x18000b99e  mov     rax, [rcx]
0x18000b9a1  mov     [rdx+10h], rax
0x18000b9a5  cmp     byte ptr [r9+19h], 0
0x18000b9aa  jnz     short loc_18000BA07
0x18000b9ac  mov     [rdi], rbx
0x18000b9af  mov     rax, [rsi+8]
0x18000b9b3  test    rax, rax
0x18000b9b6  jz      short loc_18000B9BD
0x18000b9b8  mov     r8, [rax]
0x18000b9bb  jmp     short loc_18000B9C0
0x18000b9bd  xor     r8d, r8d; lpString2
0x18000b9c0  mov     rax, [rbx+28h]
0x18000b9c4  test    rax, rax
0x18000b9c7  jz      short loc_18000B9CE
0x18000b9c9  mov     rcx, [rax]
0x18000b9cc  jmp     short loc_18000B9D0
0x18000b9ce  xor     ecx, ecx; lpString1
0x18000b9d0  or      r9d, 0FFFFFFFFh; cchCount2
0x18000b9d4  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18000b9dc  or      edx, r9d; cchCount1
0x18000b9df  call    cs:__imp_CompareStringOrdinal
0x18000b9e5  cmp     eax, 1
0x18000b9e8  jnz     short loc_18000B9F2
0x18000b9ea  add     rbx, 10h
0x18000b9ee  xor     eax, eax
0x18000b9f0  jmp     short loc_18000B9FB
0x18000b9f2  mov     [rdi+10h], rbx
0x18000b9f6  mov     eax, 1
0x18000b9fb  mov     [rdi+8], eax
0x18000b9fe  mov     rbx, [rbx]
0x18000ba01  cmp     byte ptr [rbx+19h], 0
0x18000ba05  jz      short loc_18000B9AC
0x18000ba07  mov     rbx, [rsp+38h+arg_0]
0x18000ba0c  mov     rax, rdi
0x18000ba0f  mov     rsi, [rsp+38h+arg_8]
0x18000ba14  add     rsp, 30h
0x18000ba18  pop     rdi
0x18000ba19  retn
```
