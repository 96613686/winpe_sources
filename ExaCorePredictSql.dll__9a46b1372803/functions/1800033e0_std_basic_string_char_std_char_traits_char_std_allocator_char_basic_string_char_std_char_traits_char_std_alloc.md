# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::~basic_string<char,std::char_traits<char>,std::allocator<char>>(void)

- ea: `0x1800033e0`
- end: `0x180003465`
- name: `??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ`
- size: `133`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180004bd0`
- `0x180004bdc`

## callees

- `0x180001be0`
- `0x1800033e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180003406`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180003416`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180003426`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180003433`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180003406`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180003416`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180003426`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180003433`

## pseudocode

```c
void __fastcall std::string::~string(_QWORD *a1)
{
  unsigned __int64 v1; // rax
  _QWORD *v2; // rbx
  char *v3; // rcx
  char *v4; // rax
  unsigned __int64 v5; // rcx
  bool v6; // cf

  v1 = a1[3];
  v2 = a1;
  if ( v1 >= 0x10 )
  {
    v3 = (char *)*a1;
    if ( v1 + 1 >= 0x1000 )
    {
      if ( ((unsigned __int8)v3 & 0x1F) != 0 )
        _invalid_parameter_noinfo_noreturn();
      v4 = (char *)*((_QWORD *)v3 - 1);
      if ( v4 >= v3 )
        _invalid_parameter_noinfo_noreturn();
      v5 = v3 - v4;
      if ( v5 < 8 )
        _invalid_parameter_noinfo_noreturn();
      if ( v5 > 0x27 )
        _invalid_parameter_noinfo_noreturn();
      v3 = v4;
    }
    operator delete(v3);
  }
  v2[3] = 15;
  v6 = v2[3] < 0x10u;
  v2[2] = 0;
  if ( !v6 )
    v2 = (_QWORD *)*v2;
  *(_BYTE *)v2 = 0;
}

```

## disassembly

```asm
0x1800033e0  push    rbx
0x1800033e2  sub     rsp, 20h
0x1800033e6  mov     rax, [rcx+18h]
0x1800033ea  mov     rbx, rcx
0x1800033ed  cmp     rax, 10h
0x1800033f1  jb      short loc_180003442
0x1800033f3  mov     rcx, [rcx]
0x1800033f6  inc     rax
0x1800033f9  cmp     rax, 1000h
0x1800033ff  jb      short loc_18000343D
0x180003401  test    cl, 1Fh
0x180003404  jz      short loc_18000340D
0x180003406  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x18000340d  mov     rax, [rcx-8]
0x180003411  cmp     rax, rcx
0x180003414  jb      short loc_18000341D
0x180003416  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x18000341d  sub     rcx, rax
0x180003420  cmp     rcx, 8
0x180003424  jnb     short loc_18000342D
0x180003426  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x18000342d  cmp     rcx, 27h ; '''
0x180003431  jbe     short loc_18000343A
0x180003433  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x18000343a  mov     rcx, rax; void *
0x18000343d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003442  mov     qword ptr [rbx+18h], 0Fh
0x18000344a  cmp     qword ptr [rbx+18h], 10h
0x18000344f  mov     qword ptr [rbx+10h], 0
0x180003457  jb      short loc_18000345C
0x180003459  mov     rbx, [rbx]
0x18000345c  mov     byte ptr [rbx], 0
0x18000345f  add     rsp, 20h
0x180003463  pop     rbx
0x180003464  retn
```
