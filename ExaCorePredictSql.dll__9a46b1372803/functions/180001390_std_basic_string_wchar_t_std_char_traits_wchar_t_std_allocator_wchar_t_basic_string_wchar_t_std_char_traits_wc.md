# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(void)

- ea: `0x180001390`
- end: `0x18000142c`
- name: `??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ`
- size: `156`
- prototype: `void(void *)`
- caller_count: `14`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180004b00`
- `0x180004b0c`
- `0x180004b18`
- `0x180004b24`
- `0x180004b30`
- `0x180004ba0`
- `0x180004bac`
- `0x180004bb8`
- `0x180004d80`
- `0x180004e10`
- `0x180004e1c`
- `0x180004e28`
- `0x180004e34`
- `0x180004e40`

## callees

- `0x180001390`
- `0x180001be0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1800013b8`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1800013cf`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1800013df`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1800013ef`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1800013fc`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1800013b8`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1800013cf`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1800013df`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1800013ef`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1800013fc`

## pseudocode

```c
void __fastcall std::wstring::~wstring(_QWORD *a1)
{
  unsigned __int64 v1; // rax
  _QWORD *v2; // rbx
  char *v3; // rcx
  unsigned __int64 v4; // rax
  char *v5; // rax
  unsigned __int64 v6; // rcx
  bool v7; // cf

  v1 = a1[3];
  v2 = a1;
  if ( v1 >= 8 )
  {
    v3 = (char *)*a1;
    v4 = v1 + 1;
    if ( v4 > 0x7FFFFFFFFFFFFFFFLL )
      _invalid_parameter_noinfo_noreturn();
    if ( 2 * v4 >= 0x1000 )
    {
      if ( ((unsigned __int8)v3 & 0x1F) != 0 )
        _invalid_parameter_noinfo_noreturn();
      v5 = (char *)*((_QWORD *)v3 - 1);
      if ( v5 >= v3 )
        _invalid_parameter_noinfo_noreturn();
      v6 = v3 - v5;
      if ( v6 < 8 )
        _invalid_parameter_noinfo_noreturn();
      if ( v6 > 0x27 )
        _invalid_parameter_noinfo_noreturn();
      v3 = v5;
    }
    operator delete(v3);
  }
  v2[3] = 7;
  v7 = v2[3] < 8u;
  v2[2] = 0;
  if ( !v7 )
    v2 = (_QWORD *)*v2;
  *(_WORD *)v2 = 0;
}

```

## disassembly

```asm
0x180001390  push    rbx
0x180001392  sub     rsp, 20h
0x180001396  mov     rax, [rcx+18h]
0x18000139a  mov     rbx, rcx
0x18000139d  cmp     rax, 8
0x1800013a1  jb      short loc_18000140B
0x1800013a3  mov     rcx, [rcx]
0x1800013a6  inc     rax
0x1800013a9  mov     rdx, 7FFFFFFFFFFFFFFFh
0x1800013b3  cmp     rax, rdx
0x1800013b6  jbe     short loc_1800013BF
0x1800013b8  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1800013bf  add     rax, rax
0x1800013c2  cmp     rax, 1000h
0x1800013c8  jb      short loc_180001406
0x1800013ca  test    cl, 1Fh
0x1800013cd  jz      short loc_1800013D6
0x1800013cf  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1800013d6  mov     rax, [rcx-8]
0x1800013da  cmp     rax, rcx
0x1800013dd  jb      short loc_1800013E6
0x1800013df  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1800013e6  sub     rcx, rax
0x1800013e9  cmp     rcx, 8
0x1800013ed  jnb     short loc_1800013F6
0x1800013ef  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1800013f6  cmp     rcx, 27h ; '''
0x1800013fa  jbe     short loc_180001403
0x1800013fc  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x180001403  mov     rcx, rax; void *
0x180001406  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000140b  xor     eax, eax
0x18000140d  mov     qword ptr [rbx+18h], 7
0x180001415  cmp     qword ptr [rbx+18h], 8
0x18000141a  mov     [rbx+10h], rax
0x18000141e  jb      short loc_180001423
0x180001420  mov     rbx, [rbx]
0x180001423  mov     [rbx], ax
0x180001426  add     rsp, 20h
0x18000142a  pop     rbx
0x18000142b  retn
```
