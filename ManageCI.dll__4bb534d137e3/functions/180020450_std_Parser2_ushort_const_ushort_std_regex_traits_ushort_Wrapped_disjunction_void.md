# std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Wrapped_disjunction(void)

- ea: `0x180020450`
- end: `0x180020507`
- name: `?_Wrapped_disjunction@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAA_NXZ`
- size: `183`
- prototype: `char __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path`

## callers

- `0x18001d46c`

## callees

- `0x18001e498`
- `0x18001e4e4`
- `0x18001eaf8`
- `0x18001f1c8`
- `0x180020028`
- `0x180020450`

## pseudocode

```c
char __fastcall std::_Parser2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Wrapped_disjunction(
        __int64 a1)
{
  int *v2; // rdi
  int v3; // edi
  __int64 v4; // rdx
  __int64 v5; // rcx

  if ( (int)++*(_DWORD *)(a1 + 20) >= 1000 )
    std::_Parser2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Error(a1, 0xCu);
  v2 = (int *)(a1 + 112);
  if ( (*(_QWORD *)(a1 + 96) & 0x4000000LL) == 0 && *v2 == 41 )
    std::_Parser2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Error(a1, 5u);
  if ( (*(_BYTE *)(a1 + 96) & 0x20) == 0 || *v2 != 63 )
  {
    if ( (*(_DWORD *)(a1 + 104) & 0x200) == 0 )
    {
      std::_Parser2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Do_capture_group();
      goto LABEL_15;
    }
LABEL_13:
    std::_Parser2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Do_noncapture_group(a1);
LABEL_15:
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
0x180020450  mov     [rsp+arg_0], rbx
0x180020455  push    rdi
0x180020456  sub     rsp, 20h
0x18002045a  inc     dword ptr [rcx+14h]
0x18002045d  mov     rbx, rcx
0x180020460  cmp     dword ptr [rcx+14h], 3E8h
0x180020467  jge     loc_1800204F1
0x18002046d  test    qword ptr [rcx+60h], 4000000h
0x180020475  lea     rdi, [rcx+70h]
0x180020479  jnz     short loc_180020480
0x18002047b  cmp     dword ptr [rdi], 29h ; ')'
0x18002047e  jz      short loc_1800204FC
0x180020480  test    byte ptr [rcx+60h], 20h
0x180020484  jz      short loc_1800204BE
0x180020486  cmp     dword ptr [rdi], 3Fh ; '?'
0x180020489  jnz     short loc_1800204BE
0x18002048b  call    ?_Next@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXXZ; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Next(void)
0x180020490  mov     edi, [rdi]
0x180020492  mov     rcx, rbx
0x180020495  call    ?_Next@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXXZ; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Next(void)
0x18002049a  cmp     edi, 3Ah ; ':'
0x18002049d  jz      short loc_1800204C7
0x18002049f  cmp     edi, 21h ; '!'
0x1800204a2  jnz     short loc_1800204B5
0x1800204a4  mov     dl, 1
0x1800204a6  mov     rcx, rbx
0x1800204a9  call    ?_Do_assert_group@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAX_N@Z; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Do_assert_group(bool)
0x1800204ae  dec     dword ptr [rbx+14h]
0x1800204b1  xor     al, al
0x1800204b3  jmp     short loc_1800204DB
0x1800204b5  cmp     edi, 3Dh ; '='
0x1800204b8  jnz     short loc_1800204E6
0x1800204ba  xor     edx, edx
0x1800204bc  jmp     short loc_1800204A6
0x1800204be  test    dword ptr [rcx+68h], 200h
0x1800204c5  jz      short loc_1800204D1
0x1800204c7  mov     rcx, rbx
0x1800204ca  call    ?_Do_noncapture_group@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXXZ; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Do_noncapture_group(void)
0x1800204cf  jmp     short loc_1800204D6
0x1800204d1  call    ?_Do_capture_group@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXXZ; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Do_capture_group(void)
0x1800204d6  dec     dword ptr [rbx+14h]
0x1800204d9  mov     al, 1
0x1800204db  mov     rbx, [rsp+28h+arg_0]
0x1800204e0  add     rsp, 20h
0x1800204e4  pop     rdi
0x1800204e5  retn
0x1800204e6  mov     edx, 0Ah
0x1800204eb  call    ?_Error@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXW4error_type@regex_constants@2@@Z; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Error(std::regex_constants::error_type)
0x1800204f1  mov     edx, 0Ch
0x1800204f6  call    ?_Error@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXW4error_type@regex_constants@2@@Z; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Error(std::regex_constants::error_type)
0x1800204fc  mov     edx, 5
0x180020501  call    ?_Error@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXW4error_type@regex_constants@2@@Z; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Error(std::regex_constants::error_type)
```
