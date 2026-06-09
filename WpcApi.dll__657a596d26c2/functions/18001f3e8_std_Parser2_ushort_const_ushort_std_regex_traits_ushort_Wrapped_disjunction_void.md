# std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Wrapped_disjunction(void)

- ea: `0x18001f3e8`
- end: `0x18001f511`
- name: `?_Wrapped_disjunction@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAA_NXZ`
- size: `297`
- prototype: `char __fastcall(__int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path`

## callers

- `0x18001d798`

## callees

- `0x18001db94`
- `0x18001e4dc`
- `0x18001e600`
- `0x18001ea58`
- `0x18001eaa4`
- `0x18001eb20`
- `0x18001f0dc`
- `0x18001f3e8`
- `0x18001fa98`

## import_xrefs

- `msvcp_win!?_Xregex_error@std@@YAXW4error_type@regex_constants@1@@Z` at `0x18001f489`
- `msvcp_win!?_Xregex_error@std@@YAXW4error_type@regex_constants@1@@Z` at `0x18001f489`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
char __fastcall std::_Parser2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Wrapped_disjunction(
        __int64 a1)
{
  int *v2; // rbx
  int v3; // ebx
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v7; // rdi

  if ( (int)++*(_DWORD *)(a1 + 20) >= 1000 )
    std::_Parser2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Error(a1, 0xCu);
  v2 = (int *)(a1 + 112);
  if ( (*(_QWORD *)(a1 + 96) & 0x4000000LL) == 0 && *v2 == 41 )
    std::_Parser2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Error(a1, 5u);
  if ( (*(_BYTE *)(a1 + 96) & 0x20) == 0 || *v2 != 63 )
  {
    if ( (*(_DWORD *)(a1 + 104) & 0x200) == 0 )
    {
      if ( ++*(_DWORD *)(a1 + 16) >= 0x3E8u )
      {
        std::_Xregex_error(12);
        __debugbreak();
      }
      v7 = std::_Builder2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Begin_capture_group(a1 + 56);
      std::_Parser2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Disjunction(a1);
      std::_Builder2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_End_group(a1 + 56, v7);
      std::vector<bool>::resize(a1 + 24, (unsigned int)(*(_DWORD *)(a1 + 16) + 1));
      *(_DWORD *)(*(_QWORD *)(a1 + 24) + 4 * ((unsigned __int64)*(unsigned int *)(v7 + 32) >> 5)) |= 1 << (*(_BYTE *)(v7 + 32) & 0x1F);
      goto LABEL_17;
    }
LABEL_13:
    std::_Parser2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Do_noncapture_group(a1);
LABEL_17:
    --*(_DWORD *)(a1 + 20);
    return 1;
  }
  std::_Parser2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Next((_QWORD *)a1);
  v3 = *v2;
  std::_Parser2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Next((_QWORD *)a1);
  switch ( v3 )
  {
    case ':':
      goto LABEL_13;
    case '!':
      LOBYTE(v4) = 1;
      break;
    case '=':
      v4 = 0;
      break;
    default:
      std::_Parser2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Error(v5, 0xAu);
  }
  std::_Parser2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Do_assert_group(a1, v4);
  --*(_DWORD *)(a1 + 20);
  return 0;
}

```

## disassembly

```asm
0x18001f3e8  mov     [rsp+arg_0], rbx
0x18001f3ed  mov     [rsp+arg_8], rsi
0x18001f3f2  push    rdi
0x18001f3f3  sub     rsp, 20h
0x18001f3f7  inc     dword ptr [rcx+14h]
0x18001f3fa  mov     eax, 3E8h
0x18001f3ff  mov     rsi, rcx
0x18001f402  cmp     [rcx+14h], eax
0x18001f405  jge     loc_18001F4FB
0x18001f40b  test    qword ptr [rcx+60h], 4000000h
0x18001f413  lea     rbx, [rcx+70h]
0x18001f417  jnz     short loc_18001F422
0x18001f419  cmp     dword ptr [rbx], 29h ; ')'
0x18001f41c  jz      loc_18001F506
0x18001f422  test    byte ptr [rcx+60h], 20h
0x18001f426  jz      short loc_18001F467
0x18001f428  cmp     dword ptr [rbx], 3Fh ; '?'
0x18001f42b  jnz     short loc_18001F467
0x18001f42d  call    ?_Next@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXXZ; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Next(void)
0x18001f432  mov     ebx, [rbx]
0x18001f434  mov     rcx, rsi
0x18001f437  call    ?_Next@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXXZ; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Next(void)
0x18001f43c  cmp     ebx, 3Ah ; ':'
0x18001f43f  jz      short loc_18001F470
0x18001f441  cmp     ebx, 21h ; '!'
0x18001f444  jnz     short loc_18001F45A
0x18001f446  mov     dl, 1
0x18001f448  mov     rcx, rsi
0x18001f44b  call    ?_Do_assert_group@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAX_N@Z; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Do_assert_group(bool)
0x18001f450  dec     dword ptr [rsi+14h]
0x18001f453  xor     al, al
0x18001f455  jmp     loc_18001F4E0
0x18001f45a  cmp     ebx, 3Dh ; '='
0x18001f45d  jnz     loc_18001F4F0
0x18001f463  xor     edx, edx
0x18001f465  jmp     short loc_18001F448
0x18001f467  test    dword ptr [rcx+68h], 200h
0x18001f46e  jz      short loc_18001F47A
0x18001f470  mov     rcx, rsi
0x18001f473  call    ?_Do_noncapture_group@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXXZ; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Do_noncapture_group(void)
0x18001f478  jmp     short loc_18001F4DB
0x18001f47a  inc     dword ptr [rcx+10h]
0x18001f47d  mov     edx, [rcx+10h]
0x18001f480  cmp     edx, eax
0x18001f482  jb      short loc_18001F490
0x18001f484  mov     ecx, 0Ch
0x18001f489  call    cs:__imp_?_Xregex_error@std@@YAXW4error_type@regex_constants@1@@Z; std::_Xregex_error(std::regex_constants::error_type)
0x18001f48f  int     3; Trap to Debugger
0x18001f490  add     rcx, 38h ; '8'
0x18001f494  call    ?_Begin_capture_group@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@QEAAPEAV_Node_base@2@I@Z; std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_Begin_capture_group(uint)
0x18001f499  mov     rcx, rsi
0x18001f49c  mov     rdi, rax
0x18001f49f  call    ?_Disjunction@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXXZ; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Disjunction(void)
0x18001f4a4  mov     rdx, rdi
0x18001f4a7  lea     rcx, [rsi+38h]
0x18001f4ab  call    ?_End_group@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@QEAAXPEAV_Node_base@2@@Z; std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_End_group(std::_Node_base *)
0x18001f4b0  mov     edx, [rsi+10h]
0x18001f4b3  lea     rcx, [rsi+18h]
0x18001f4b7  inc     edx
0x18001f4b9  call    ?resize@?$vector@_NV?$allocator@_N@std@@@std@@QEAAX_K_N@Z; std::vector<bool>::resize(unsigned __int64,bool)
0x18001f4be  mov     r8d, [rdi+20h]
0x18001f4c2  mov     rcx, [rsi+18h]
0x18001f4c6  mov     edx, r8d
0x18001f4c9  shr     rdx, 5
0x18001f4cd  and     r8d, 1Fh
0x18001f4d1  mov     eax, [rcx+rdx*4]
0x18001f4d4  bts     eax, r8d
0x18001f4d8  mov     [rcx+rdx*4], eax
0x18001f4db  dec     dword ptr [rsi+14h]
0x18001f4de  mov     al, 1
0x18001f4e0  mov     rbx, [rsp+28h+arg_0]
0x18001f4e5  mov     rsi, [rsp+28h+arg_8]
0x18001f4ea  add     rsp, 20h
0x18001f4ee  pop     rdi
0x18001f4ef  retn
0x18001f4f0  mov     edx, 0Ah
0x18001f4f5  call    ?_Error@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXW4error_type@regex_constants@2@@Z; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Error(std::regex_constants::error_type)
0x18001f4fb  mov     edx, 0Ch
0x18001f500  call    ?_Error@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXW4error_type@regex_constants@2@@Z; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Error(std::regex_constants::error_type)
0x18001f506  mov     edx, 5
0x18001f50b  call    ?_Error@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXW4error_type@regex_constants@2@@Z; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Error(std::regex_constants::error_type)
```
