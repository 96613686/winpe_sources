# replace_current_thread_locale_nolock(__acrt_ptd * const,__crt_locale_data * const)

- ea: `0x140005f80`
- end: `0x140005fe7`
- name: `?replace_current_thread_locale_nolock@@YAXQEAU__acrt_ptd@@QEAU__crt_locale_data@@@Z`
- size: `103`
- prototype: `void __fastcall(struct __acrt_ptd *const, struct __crt_locale_data *const)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140005bf4`
- `0x140005c34`

## callees

- `0x140005f80`
- `0x140008fa8`
- `0x140009034`
- `0x140009234`

## pseudocode

```c
void __fastcall replace_current_thread_locale_nolock(struct __acrt_ptd *const a1, struct __crt_locale_data *const a2)
{
  wchar_t **v4; // rcx

  if ( *((_QWORD *)a1 + 18) )
  {
    _acrt_release_locale_ref();
    v4 = (wchar_t **)*((_QWORD *)a1 + 18);
    if ( v4 != (wchar_t **)qword_14001AB58 && v4 != &off_140019630 && !*((_DWORD *)v4 + 4) )
      _acrt_free_locale(v4);
  }
  *((_QWORD *)a1 + 18) = a2;
  if ( a2 )
    _acrt_add_locale_ref(a2);
}

```

## disassembly

```asm
0x140005f80  mov     [rsp+arg_0], rbx
0x140005f85  push    rdi
0x140005f86  sub     rsp, 20h
0x140005f8a  mov     rdi, rcx
0x140005f8d  mov     rbx, rdx
0x140005f90  mov     rcx, [rcx+90h]
0x140005f97  test    rcx, rcx
0x140005f9a  jz      short loc_140005FC8
0x140005f9c  call    __acrt_release_locale_ref
0x140005fa1  mov     rcx, [rdi+90h]; Block
0x140005fa8  cmp     rcx, cs:qword_14001AB58
0x140005faf  jz      short loc_140005FC8
0x140005fb1  lea     rax, off_140019630
0x140005fb8  cmp     rcx, rax
0x140005fbb  jz      short loc_140005FC8
0x140005fbd  cmp     dword ptr [rcx+10h], 0
0x140005fc1  jnz     short loc_140005FC8
0x140005fc3  call    __acrt_free_locale
0x140005fc8  mov     [rdi+90h], rbx
0x140005fcf  test    rbx, rbx
0x140005fd2  jz      short loc_140005FDC
0x140005fd4  mov     rcx, rbx
0x140005fd7  call    __acrt_add_locale_ref
0x140005fdc  mov     rbx, [rsp+28h+arg_0]
0x140005fe1  add     rsp, 20h
0x140005fe5  pop     rdi
0x140005fe6  retn
```
