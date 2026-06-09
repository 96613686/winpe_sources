# wpc::Policy::operator==(wpc::Policy::AppTimeLimitsSettings const &,wpc::Policy::AppTimeLimitsSettings const &)

- ea: `0x180078004`
- end: `0x1800780ae`
- name: `??8Policy@wpc@@YA_NAEBUAppTimeLimitsSettings@01@0@Z`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800783bc`
- `0x18007908c`

## callees

- `0x1800777a8`
- `0x180078004`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180078077`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18007808c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180078077`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18007808c`

## pseudocode

```c
bool __fastcall wpc::Policy::operator==(__int64 a1, __int64 a2)
{
  const FILETIME *v4; // rbx
  const FILETIME *v5; // rdi
  int v6; // ecx

  if ( *(_BYTE *)a1 != *(_BYTE *)a2
    || *(_QWORD *)(a1 + 40) != *(_QWORD *)(a2 + 40)
    || !(unsigned __int8)std::equal<std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<appids::AnyRuntimeApp const,wpc::Policy::TimeLimitsRule>>>,std::_Iterator_base0>,std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<appids::AnyRuntimeApp const,wpc::Policy::TimeLimitsRule>>>,std::_Iterator_base0>>(
                           **(_QWORD **)(a1 + 32),
                           *(_QWORD *)(a1 + 32),
                           **(_QWORD **)(a2 + 32)) )
  {
    return 0;
  }
  v4 = *(const FILETIME **)(a2 + 24);
  v5 = *(const FILETIME **)(((a1 + 8) & -(__int64)(a1 != -9)) + 0x10);
  if ( v5 == v4 )
    return 1;
  if ( v5 )
  {
    if ( !v4 )
      return 0;
    if ( CompareFileTime(v5, v4) >= 0 )
      v6 = CompareFileTime(v5, v4) > 0;
    else
      v6 = -1;
  }
  else
  {
    v6 = -(v4 != 0);
  }
  return !v6;
}

```

## disassembly

```asm
0x180078004  mov     [rsp+arg_0], rbx
0x180078009  push    rdi
0x18007800a  sub     rsp, 20h
0x18007800e  mov     al, [rdx]
0x180078010  mov     rbx, rdx
0x180078013  mov     rdi, rcx
0x180078016  cmp     [rcx], al
0x180078018  jnz     loc_1800780A1
0x18007801e  mov     rax, [rdx+28h]
0x180078022  cmp     [rcx+28h], rax
0x180078026  jnz     short loc_1800780A1
0x180078028  mov     rcx, [rcx+20h]
0x18007802c  mov     r8, [rdx+20h]
0x180078030  mov     rdx, rcx
0x180078033  mov     rcx, [rcx]
0x180078036  mov     r8, [r8]
0x180078039  call    ??$equal@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVAnyRuntimeApp@appids@@UTimeLimitsRule@Policy@wpc@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@V12@@std@@YA_NV?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVAnyRuntimeApp@appids@@UTimeLimitsRule@Policy@wpc@@@std@@@std@@@std@@U_Iterator_base0@2@@0@00@Z; std::equal<std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<appids::AnyRuntimeApp const,wpc::Policy::TimeLimitsRule>>>,std::_Iterator_base0>,std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<appids::AnyRuntimeApp const,wpc::Policy::TimeLimitsRule>>>,std::_Iterator_base0>>(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<appids::AnyRuntimeApp const,wpc::Policy::TimeLimitsRule>>>,std::_Iterator_base0>,std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<appids::AnyRuntimeApp const,wpc::Policy::TimeLimitsRule>>>,std::_Iterator_base0>,std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<appids::AnyRuntimeApp const,wpc::Policy::TimeLimitsRule>>>,std::_Iterator_base0>)
0x18007803e  test    al, al
0x180078040  jz      short loc_1800780A1
0x180078042  mov     rbx, [rbx+18h]
0x180078046  lea     rdx, [rdi+8]
0x18007804a  lea     rax, [rdx+1]
0x18007804e  neg     rax
0x180078051  sbb     rcx, rcx
0x180078054  and     rcx, rdx
0x180078057  mov     rdi, [rcx+10h]
0x18007805b  cmp     rdi, rbx
0x18007805e  jz      short loc_18007809D
0x180078060  test    rdi, rdi
0x180078063  jnz     short loc_18007806C
0x180078065  neg     rbx
0x180078068  sbb     ecx, ecx
0x18007806a  jmp     short loc_180078099
0x18007806c  test    rbx, rbx
0x18007806f  jz      short loc_1800780A1
0x180078071  mov     rdx, rbx; lpFileTime2
0x180078074  mov     rcx, rdi; lpFileTime1
0x180078077  call    cs:__imp_CompareFileTime
0x18007807d  test    eax, eax
0x18007807f  jns     short loc_180078086
0x180078081  or      ecx, 0FFFFFFFFh
0x180078084  jmp     short loc_180078099
0x180078086  mov     rdx, rbx; lpFileTime2
0x180078089  mov     rcx, rdi; lpFileTime1
0x18007808c  call    cs:__imp_CompareFileTime
0x180078092  xor     ecx, ecx
0x180078094  test    eax, eax
0x180078096  setnle  cl
0x180078099  test    ecx, ecx
0x18007809b  jnz     short loc_1800780A1
0x18007809d  mov     al, 1
0x18007809f  jmp     short loc_1800780A3
0x1800780a1  xor     al, al
0x1800780a3  mov     rbx, [rsp+28h+arg_0]
0x1800780a8  add     rsp, 20h
0x1800780ac  pop     rdi
0x1800780ad  retn
```
