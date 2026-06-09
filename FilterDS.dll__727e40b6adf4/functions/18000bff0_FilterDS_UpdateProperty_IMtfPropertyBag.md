# FilterDS::UpdateProperty(IMtfPropertyBag *)

- ea: `0x18000bff0`
- end: `0x18000c06e`
- name: `?UpdateProperty@FilterDS@@UEAAJPEAUIMtfPropertyBag@@@Z`
- size: `126`
- prototype: `__int64 __fastcall(FilterDS *__hidden this, struct IMtfPropertyBag *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callees

- `0x18000bff0`
- `0x18000e0a8`
- `0x18000e140`
- `0x180024010`

## pseudocode

```c
__int64 __fastcall FilterDS::UpdateProperty(FilterDS *this, struct IMtfPropertyBag *a2, __int64 a3, const char *a4)
{
  unsigned __int16 v5; // dx
  __int64 result; // rax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v8; // [rsp+40h] [rbp+8h] BYREF

  try
  {
    if ( *((_QWORD *)this + 4) )
    {
      v8 = 0;
      if ( (*(int (__fastcall **)(struct IMtfPropertyBag *, __int64 *, int *, __int64))(*(_QWORD *)a2 + 40LL))(
             a2,
             MTF_PROPBAG_KEY_DS_CMD_RELOADCONFIG,
             &v8,
             4) >= 0
        && v8 != *((_DWORD *)this + 6) )
      {
        v5 = *((_WORD *)this + 8);
        if ( v5 )
        {
          *((_DWORD *)this + 6) = v8;
          FilterManager::InitializeFilters(*((FilterManager **)this + 4), v5);
          FilterManager::LoadFilterDictionary(*((FilterManager **)this + 4), *((_WORD *)this + 8));
        }
      }
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x152,
                           (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\lib\\filterds.cpp",
                           a4);
  }
  return result;
}

```

## disassembly

```asm
0x18000bff0  mov     [rsp+arg_8], rbx
0x18000bff5  push    rdi
0x18000bff6  sub     rsp, 30h
0x18000bffa  mov     r10, rdx
0x18000bffd  mov     rbx, rcx
0x18000c000  xor     edi, edi
0x18000c002  cmp     [rcx+20h], rdi
0x18000c006  jz      short loc_18000C05A
0x18000c008  mov     [rsp+38h+arg_0], edi
0x18000c00c  mov     rax, [rdx]
0x18000c00f  lea     r9d, [rdi+4]
0x18000c013  lea     r8, [rsp+38h+arg_0]
0x18000c018  lea     rdx, MTF_PROPBAG_KEY_DS_CMD_RELOADCONFIG
0x18000c01f  mov     rcx, r10
0x18000c022  mov     rax, [rax+28h]
0x18000c026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c02b  test    eax, eax
0x18000c02d  js      short loc_18000C05A
0x18000c02f  mov     eax, [rsp+38h+arg_0]
0x18000c033  cmp     eax, [rbx+18h]
0x18000c036  jz      short loc_18000C05A
0x18000c038  movzx   edx, word ptr [rbx+10h]; unsigned __int16
0x18000c03c  test    dx, dx
0x18000c03f  jz      short loc_18000C05A
0x18000c041  mov     [rbx+18h], eax
0x18000c044  mov     rcx, [rbx+20h]; this
0x18000c048  call    ?InitializeFilters@FilterManager@@QEAAXG@Z; FilterManager::InitializeFilters(ushort)
0x18000c04d  movzx   edx, word ptr [rbx+10h]; unsigned __int16
0x18000c051  mov     rcx, [rbx+20h]; this
0x18000c055  call    ?LoadFilterDictionary@FilterManager@@QEAAXG@Z; FilterManager::LoadFilterDictionary(ushort)
0x18000c05a  xor     eax, eax
0x18000c05c  jmp     short loc_18000C062
0x18000c05e  mov     eax, [rsp+38h+arg_0]
0x18000c062  mov     rbx, [rsp+38h+arg_8]
0x18000c067  add     rsp, 30h
0x18000c06b  pop     rdi
0x18000c06c  retn
```
