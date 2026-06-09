# std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Wrapped_disjunction(void)

- ea: `0x180021988`
- end: `0x180021ab1`
- name: `?_Wrapped_disjunction@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAA_NXZ`
- size: `297`
- prototype: `char __fastcall(__int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path`

## callers

- `0x18001dc38`

## callees

- `0x18001e16c`
- `0x18001eee0`
- `0x18001f004`
- `0x18001f6c4`
- `0x18001fcfc`
- `0x18001fd78`
- `0x180021010`
- `0x180021988`
- `0x1800225e0`

## import_xrefs

- `msvcp_win!?_Xregex_error@std@@YAXW4error_type@regex_constants@1@@Z` at `0x180021a29`
- `msvcp_win!?_Xregex_error@std@@YAXW4error_type@regex_constants@1@@Z` at `0x180021a29`

## pseudocode

```c
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
0x180021988  mov     [rsp+arg_0], rbx
0x18002198d  mov     [rsp+arg_8], rsi
0x180021992  push    rdi
0x180021993  sub     rsp, 20h
0x180021997  inc     dword ptr [rcx+14h]
0x18002199a  mov     eax, 3E8h
0x18002199f  mov     rsi, rcx
0x1800219a2  cmp     [rcx+14h], eax
0x1800219a5  jge     loc_180021A9B
0x1800219ab  test    qword ptr [rcx+60h], 4000000h
0x1800219b3  lea     rbx, [rcx+70h]
0x1800219b7  jnz     short loc_1800219C2
0x1800219b9  cmp     dword ptr [rbx], 29h ; ')'
0x1800219bc  jz      loc_180021AA6
0x1800219c2  test    byte ptr [rcx+60h], 20h
0x1800219c6  jz      short loc_180021A07
0x1800219c8  cmp     dword ptr [rbx], 3Fh ; '?'
0x1800219cb  jnz     short loc_180021A07
0x1800219cd  call    ?_Next@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXXZ; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Next(void)
0x1800219d2  mov     ebx, [rbx]
0x1800219d4  mov     rcx, rsi
0x1800219d7  call    ?_Next@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXXZ; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Next(void)
0x1800219dc  cmp     ebx, 3Ah ; ':'
0x1800219df  jz      short loc_180021A10
0x1800219e1  cmp     ebx, 21h ; '!'
0x1800219e4  jnz     short loc_1800219FA
0x1800219e6  mov     dl, 1
0x1800219e8  mov     rcx, rsi
0x1800219eb  call    ?_Do_assert_group@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAX_N@Z; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Do_assert_group(bool)
0x1800219f0  dec     dword ptr [rsi+14h]
0x1800219f3  xor     al, al
0x1800219f5  jmp     loc_180021A80
0x1800219fa  cmp     ebx, 3Dh ; '='
0x1800219fd  jnz     loc_180021A90
0x180021a03  xor     edx, edx
0x180021a05  jmp     short loc_1800219E8
0x180021a07  test    dword ptr [rcx+68h], 200h
0x180021a0e  jz      short loc_180021A1A
0x180021a10  mov     rcx, rsi
0x180021a13  call    ?_Do_noncapture_group@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXXZ; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Do_noncapture_group(void)
0x180021a18  jmp     short loc_180021A7B
0x180021a1a  inc     dword ptr [rcx+10h]
0x180021a1d  mov     edx, [rcx+10h]
0x180021a20  cmp     edx, eax
0x180021a22  jb      short loc_180021A30
0x180021a24  mov     ecx, 0Ch
0x180021a29  call    cs:__imp_?_Xregex_error@std@@YAXW4error_type@regex_constants@1@@Z; std::_Xregex_error(std::regex_constants::error_type)
0x180021a2f  int     3; Trap to Debugger
0x180021a30  add     rcx, 38h ; '8'
0x180021a34  call    ?_Begin_capture_group@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@QEAAPEAV_Node_base@2@I@Z; std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_Begin_capture_group(uint)
0x180021a39  mov     rcx, rsi
0x180021a3c  mov     rdi, rax
0x180021a3f  call    ?_Disjunction@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXXZ; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Disjunction(void)
0x180021a44  mov     rdx, rdi
0x180021a47  lea     rcx, [rsi+38h]
0x180021a4b  call    ?_End_group@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@QEAAXPEAV_Node_base@2@@Z; std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_End_group(std::_Node_base *)
0x180021a50  mov     edx, [rsi+10h]
0x180021a53  lea     rcx, [rsi+18h]
0x180021a57  inc     edx
0x180021a59  call    ?resize@?$vector@_NV?$allocator@_N@std@@@std@@QEAAX_K_N@Z; std::vector<bool>::resize(unsigned __int64,bool)
0x180021a5e  mov     r8d, [rdi+20h]
0x180021a62  mov     rcx, [rsi+18h]
0x180021a66  mov     edx, r8d
0x180021a69  shr     rdx, 5
0x180021a6d  and     r8d, 1Fh
0x180021a71  mov     eax, [rcx+rdx*4]
0x180021a74  bts     eax, r8d
0x180021a78  mov     [rcx+rdx*4], eax
0x180021a7b  dec     dword ptr [rsi+14h]
0x180021a7e  mov     al, 1
0x180021a80  mov     rbx, [rsp+28h+arg_0]
0x180021a85  mov     rsi, [rsp+28h+arg_8]
0x180021a8a  add     rsp, 20h
0x180021a8e  pop     rdi
0x180021a8f  retn
0x180021a90  mov     edx, 0Ah
0x180021a95  call    ?_Error@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXW4error_type@regex_constants@2@@Z; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Error(std::regex_constants::error_type)
0x180021a9b  mov     edx, 0Ch
0x180021aa0  call    ?_Error@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXW4error_type@regex_constants@2@@Z; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Error(std::regex_constants::error_type)
0x180021aa6  mov     edx, 5
0x180021aab  call    ?_Error@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXW4error_type@regex_constants@2@@Z; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Error(std::regex_constants::error_type)
```
