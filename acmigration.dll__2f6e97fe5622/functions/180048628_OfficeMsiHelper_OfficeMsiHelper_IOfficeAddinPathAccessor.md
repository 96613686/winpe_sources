# OfficeMsiHelper::OfficeMsiHelper(IOfficeAddinPathAccessor &)

- ea: `0x180048628`
- end: `0x1800486fd`
- name: `??0OfficeMsiHelper@@AEAA@AEAVIOfficeAddinPathAccessor@@@Z`
- size: `213`
- prototype: `OfficeMsiHelper *__fastcall(OfficeMsiHelper *__hidden this, struct IOfficeAddinPathAccessor *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180048a08`

## callees

- `0x180002120`
- `0x180029198`
- `0x18004937c`
- `0x1800543c0`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x1800486ae`
- `KERNEL32!GetTickCount64` at `0x1800486bf`
- `KERNEL32!GetTickCount64` at `0x1800486ae`
- `KERNEL32!GetTickCount64` at `0x1800486bf`

## string_xrefs

- `0x1800486cb`: `Component preprocessing duration: %d ms.`
- `0x1800486d8`: `_LoadComponentsMapping`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
OfficeMsiHelper *__fastcall OfficeMsiHelper::OfficeMsiHelper(
        OfficeMsiHelper *this,
        struct IOfficeAddinPathAccessor *a2)
{
  char *v3; // rdi
  _QWORD *v4; // rax
  int TickCount64; // ebx
  int v6; // eax

  *(_QWORD *)this = &OfficeMsiHelper::`vftable';
  *((_QWORD *)this + 1) = a2;
  v3 = (char *)this + 16;
  *((_DWORD *)this + 4) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  v4 = operator new(0x48u);
  *v4 = v4;
  v4[1] = v4;
  *((_QWORD *)v3 + 1) = v4;
  *((_QWORD *)v3 + 3) = 0;
  *((_QWORD *)v3 + 4) = 0;
  *((_QWORD *)v3 + 5) = 0;
  *((_QWORD *)v3 + 6) = 7;
  *((_QWORD *)v3 + 7) = 8;
  *(_DWORD *)v3 = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(
    v3 + 24,
    16,
    *((_QWORD *)v3 + 1));
  TickCount64 = GetTickCount64();
  _CacheMsiComponents((__int64)v3);
  v6 = GetTickCount64();
  AslLogCallPrintf(3, "_LoadComponentsMapping", 246, "Component preprocessing duration: %d ms.", v6 - TickCount64);
  return this;
}

```

## disassembly

```asm
0x180048628  mov     r11, rsp
0x18004862b  mov     [r11+8], rcx
0x18004862f  push    rdi
0x180048630  sub     rsp, 40h
0x180048634  mov     qword ptr [r11-18h], 0FFFFFFFFFFFFFFFEh
0x18004863c  mov     [r11+18h], rbx
0x180048640  mov     [r11+20h], rsi
0x180048644  mov     rsi, rcx
0x180048647  lea     rax, ??_7OfficeMsiHelper@@6B@; const OfficeMsiHelper::`vftable'
0x18004864e  mov     [rcx], rax
0x180048651  mov     [rcx+8], rdx
0x180048655  lea     rdi, [rcx+10h]
0x180048659  mov     [r11+10h], rdi
0x18004865d  xor     ebx, ebx
0x18004865f  mov     [rdi], ebx
0x180048661  mov     [rdi+8], rbx
0x180048665  mov     [rdi+10h], rbx
0x180048669  lea     ecx, [rbx+48h]; Size
0x18004866c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180048671  mov     [rax], rax
0x180048674  mov     [rax+8], rax
0x180048678  mov     [rdi+8], rax
0x18004867c  lea     rcx, [rdi+18h]
0x180048680  mov     [rcx], rbx
0x180048683  mov     [rcx+8], rbx
0x180048687  mov     [rcx+10h], rbx
0x18004868b  mov     qword ptr [rdi+30h], 7
0x180048693  mov     qword ptr [rdi+38h], 8
0x18004869b  mov     dword ptr [rdi], 3F800000h
0x1800486a1  mov     r8, [rdi+8]
0x1800486a5  lea     edx, [rbx+10h]
0x1800486a8  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>)
0x1800486ad  nop
0x1800486ae  call    cs:__imp_GetTickCount64
0x1800486b4  mov     rbx, rax
0x1800486b7  mov     rcx, rdi
0x1800486ba  call    ?_CacheMsiComponents@@YAXAEAV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@@Z; _CacheMsiComponents(std::unordered_map<std::wstring,std::vector<std::wstring>> &)
0x1800486bf  call    cs:__imp_GetTickCount64
0x1800486c5  sub     eax, ebx
0x1800486c7  mov     [rsp+48h+var_28], eax
0x1800486cb  lea     r9, aComponentPrepr; "Component preprocessing duration: %d ms"...
0x1800486d2  mov     r8d, 0F6h
0x1800486d8  lea     rdx, aLoadcomponents; "_LoadComponentsMapping"
0x1800486df  mov     ecx, 3
0x1800486e4  call    AslLogCallPrintf
0x1800486e9  nop
0x1800486ea  mov     rax, rsi
0x1800486ed  mov     rbx, [rsp+48h+arg_10]
0x1800486f2  mov     rsi, [rsp+48h+arg_18]
0x1800486f7  add     rsp, 40h
0x1800486fb  pop     rdi
0x1800486fc  retn
```
