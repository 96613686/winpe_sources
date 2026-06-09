# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Tidy(bool,unsigned __int64)

- ea: `0x1800062ac`
- end: `0x18000630e`
- name: `?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z`
- size: `98`
- prototype: ``
- caller_count: `88`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180002cec`
- `0x180004950`
- `0x180005fb4`
- `0x18000617c`
- `0x180006df0`
- `0x1800070a4`
- `0x180007110`
- `0x1800078f4`
- `0x180007a3c`
- `0x180007b5c`
- `0x180007c00`
- `0x180007edc`
- `0x180008cec`
- `0x180009304`
- `0x180009cec`
- `0x18000ba58`
- `0x18000ba84`
- `0x18000bb58`
- `0x18000bbf8`
- `0x18000bc40`
- `0x18000bc8c`
- `0x18000bccc`
- `0x18000bd00`
- `0x18000c734`
- `0x18000ccb4`
- `0x18000d2cc`
- `0x18000e070`
- `0x18000e0a8`
- `0x18000e524`
- `0x18000e980`
- `0x18000ea88`
- `0x18000f704`
- `0x18000f7d4`
- `0x18000f924`
- `0x18000fe4c`
- `0x1800100a4`
- `0x1800102b8`
- `0x1800110c0`
- `0x180011160`
- `0x180011398`
- `0x180011574`
- `0x18001180c`
- `0x180011a44`
- `0x180011bfc`
- `0x180011e54`
- `0x180012050`
- `0x180012338`
- `0x1800132a0`
- `0x1800132c0`
- `0x1800132e0`

## callees

- `0x1800062ac`
- `0x18000670c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800062df`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800062df`

## pseudocode

```c
__int64 __fastcall std::wstring::_Tidy(void **a1, char a2, __int64 a3)
{
  void *v5; // rsi
  __int64 result; // rax

  if ( a2 && (unsigned __int64)a1[3] >= 8 )
  {
    v5 = *a1;
    if ( a3 )
      std::char_traits<unsigned short>::copy(a1, *a1, a3);
    operator delete(v5);
  }
  result = 0;
  a1[3] = (void *)7;
  a1[2] = (void *)a3;
  *((_WORD *)a1 + a3) = 0;
  return result;
}

```

## disassembly

```asm
0x1800062ac  mov     [rsp+arg_0], rbx
0x1800062b1  mov     [rsp+arg_8], rsi
0x1800062b6  push    rdi
0x1800062b7  sub     rsp, 20h
0x1800062bb  mov     rdi, r8
0x1800062be  mov     rbx, rcx
0x1800062c1  test    dl, dl
0x1800062c3  jz      short loc_1800062EB
0x1800062c5  cmp     qword ptr [rcx+18h], 8
0x1800062ca  jb      short loc_1800062EB
0x1800062cc  mov     rsi, [rcx]
0x1800062cf  test    r8, r8
0x1800062d2  jz      short loc_1800062DC
0x1800062d4  mov     rdx, rsi
0x1800062d7  call    ?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)
0x1800062dc  mov     rcx, rsi
0x1800062df  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800062e6  nop     dword ptr [rax+rax+00h]
0x1800062eb  mov     rsi, [rsp+28h+arg_8]
0x1800062f0  xor     eax, eax
0x1800062f2  mov     qword ptr [rbx+18h], 7
0x1800062fa  mov     [rbx+10h], rdi
0x1800062fe  mov     [rbx+rdi*2], ax
0x180006302  mov     rbx, [rsp+28h+arg_0]
0x180006307  add     rsp, 20h
0x18000630b  pop     rdi
0x18000630c  retn
```
