# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Tidy(bool,unsigned __int64)

- ea: `0x18000cf10`
- end: `0x18000cf68`
- name: `?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z`
- size: `88`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000c584`
- `0x18000c878`
- `0x18000f4c6`

## callees

- `0x1800026f0`
- `0x180007c76`
- `0x18000cf10`

## pseudocode

```c
void __fastcall std::string::_Tidy(void **a1, char a2, size_t a3)
{
  void *v5; // rsi

  if ( a2 && (unsigned __int64)a1[3] >= 0x10 )
  {
    v5 = *a1;
    if ( a3 )
      memcpy_0(a1, *a1, a3);
    operator delete(v5);
  }
  a1[3] = (void *)15;
  a1[2] = (void *)a3;
  *((_BYTE *)a1 + a3) = 0;
}

```

## disassembly

```asm
0x18000cf10  mov     [rsp+arg_0], rbx
0x18000cf15  mov     [rsp+arg_8], rsi
0x18000cf1a  push    rdi
0x18000cf1b  sub     rsp, 20h
0x18000cf1f  mov     rdi, r8
0x18000cf22  mov     rbx, rcx
0x18000cf25  test    dl, dl
0x18000cf27  jz      short loc_18000CF48
0x18000cf29  cmp     qword ptr [rcx+18h], 10h
0x18000cf2e  jb      short loc_18000CF48
0x18000cf30  mov     rsi, [rcx]
0x18000cf33  test    r8, r8
0x18000cf36  jz      short loc_18000CF40
0x18000cf38  mov     rdx, rsi; Src
0x18000cf3b  call    memcpy_0
0x18000cf40  mov     rcx, rsi; lpMem
0x18000cf43  call    ??3@YAXPEAX@Z
0x18000cf48  mov     rsi, [rsp+28h+arg_8]
0x18000cf4d  mov     qword ptr [rbx+18h], 0Fh
0x18000cf55  mov     [rbx+10h], rdi
0x18000cf59  mov     byte ptr [rdi+rbx], 0
0x18000cf5d  mov     rbx, [rsp+28h+arg_0]
0x18000cf62  add     rsp, 20h
0x18000cf66  pop     rdi
0x18000cf67  retn
```
