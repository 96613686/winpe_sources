# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Become_small(void)

- ea: `0x180023560`
- end: `0x1800235d0`
- name: `?_Become_small@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ`
- size: `112`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180023838`
- `0x1800243f0`

## callees

- `0x180002c74`
- `0x180008de5`
- `0x180023560`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x1800235c3`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x1800235c3`

## pseudocode

```c
void __fastcall std::string::_Become_small(void **a1)
{
  _QWORD *v1; // rbx
  __int64 v3; // rcx

  v1 = *a1;
  memcpy_0(a1, *a1, (size_t)a1[2] + 1);
  if ( (unsigned __int64)a1[3] + 1 >= 0x1000 )
  {
    v3 = *(v1 - 1);
    if ( (unsigned __int64)v1 - v3 - 8 > 0x1F )
    {
      _o__invalid_parameter_noinfo_noreturn(v3, (char *)a1[3] + 40);
      __debugbreak();
      JUMPOUT(0x1800235D0LL);
    }
    v1 = (_QWORD *)*(v1 - 1);
  }
  operator delete(v1);
  a1[3] = (void *)15;
}

```

## disassembly

```asm
0x180023560  mov     [rsp+arg_0], rbx
0x180023565  push    rdi
0x180023566  sub     rsp, 20h
0x18002356a  mov     rbx, [rcx]
0x18002356d  mov     rdi, rcx
0x180023570  mov     r8, [rcx+10h]
0x180023574  mov     rdx, rbx; Src
0x180023577  inc     r8; Size
0x18002357a  call    memcpy_0
0x18002357f  mov     rdx, [rdi+18h]
0x180023583  inc     rdx
0x180023586  cmp     rdx, 1000h
0x18002358d  jb      short loc_1800235A7
0x18002358f  mov     rcx, [rbx-8]
0x180023593  add     rdx, 27h ; '''; unsigned __int64
0x180023597  sub     rbx, rcx
0x18002359a  lea     rax, [rbx-8]
0x18002359e  cmp     rax, 1Fh
0x1800235a2  ja      short loc_1800235C3
0x1800235a4  mov     rbx, rcx
0x1800235a7  mov     rcx, rbx; void *
0x1800235aa  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800235af  mov     rbx, [rsp+28h+arg_0]
0x1800235b4  mov     qword ptr [rdi+18h], 0Fh
0x1800235bc  add     rsp, 20h
0x1800235c0  pop     rdi
0x1800235c1  retn
0x1800235c3  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
0x1800235ca  nop     dword ptr [rax+rax+00h]
0x1800235cf  int     3; Trap to Debugger
```
