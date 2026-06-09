# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Grow(unsigned __int64,bool)

- ea: `0x140007494`
- end: `0x1400074f8`
- name: `?_Grow@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_N_K_N@Z`
- size: `100`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1400078b0`
- `0x1400079a0`
- `0x140007bfc`
- `0x140007cc8`

## callees

- `0x1400016b0`
- `0x14000727c`
- `0x140007494`

## pseudocode

```c
bool __fastcall std::wstring::_Grow(_QWORD *a1, unsigned __int64 a2)
{
  bool v3; // zf
  _WORD *v4; // rdx

  if ( a2 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlength_error("string too long");
  if ( a1[3] < a2 )
  {
    std::wstring::_Copy(a1, a2, a1[2]);
LABEL_10:
    v3 = a2 == 0;
    return !v3;
  }
  v3 = a2 == 0;
  if ( !a2 )
  {
    if ( a1[3] < 8u )
      v4 = a1;
    else
      v4 = (_WORD *)*a1;
    a1[2] = 0;
    *v4 = 0;
    goto LABEL_10;
  }
  return !v3;
}

```

## disassembly

```asm
0x140007494  push    rbx
0x140007496  sub     rsp, 20h
0x14000749a  mov     rax, 7FFFFFFFFFFFFFFEh
0x1400074a4  mov     rbx, rdx
0x1400074a7  cmp     rdx, rax
0x1400074aa  jbe     short loc_1400074B9
0x1400074ac  lea     rcx, aStringTooLong; "string too long"
0x1400074b3  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1400074b9  cmp     [rcx+18h], rbx
0x1400074bd  jnb     short loc_1400074CA
0x1400074bf  mov     r8, [rcx+10h]
0x1400074c3  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x1400074c8  jmp     short loc_1400074EB
0x1400074ca  test    rbx, rbx
0x1400074cd  jnz     short loc_1400074EE
0x1400074cf  cmp     qword ptr [rcx+18h], 8
0x1400074d4  jb      short loc_1400074DB
0x1400074d6  mov     rdx, [rcx]
0x1400074d9  jmp     short loc_1400074DE
0x1400074db  mov     rdx, rcx
0x1400074de  xor     eax, eax
0x1400074e0  mov     qword ptr [rcx+10h], 0
0x1400074e8  mov     [rdx], ax
0x1400074eb  test    rbx, rbx
0x1400074ee  setnz   al
0x1400074f1  add     rsp, 20h
0x1400074f5  pop     rbx
0x1400074f6  retn
```
