# replace_current_thread_locale_nolock(__acrt_ptd * const,__crt_locale_data * const)

- ea: `0x1400195f0`
- end: `0x140019657`
- name: `?replace_current_thread_locale_nolock@@YAXQEAU__acrt_ptd@@QEAU__crt_locale_data@@@Z`
- size: `103`
- prototype: `void __fastcall(struct __acrt_ptd *const, struct __crt_locale_data *const)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140019268`
- `0x1400192a8`

## callees

- `0x1400195f0`
- `0x14001eb08`
- `0x14001eb94`
- `0x14001ed94`

## pseudocode

```c
void __fastcall replace_current_thread_locale_nolock(struct __acrt_ptd *const a1, struct __crt_locale_data *const a2)
{
  wchar_t **v4; // rcx

  if ( *((_QWORD *)a1 + 18) )
  {
    _acrt_release_locale_ref();
    v4 = (wchar_t **)*((_QWORD *)a1 + 18);
    if ( v4 != (wchar_t **)qword_14003E5A8 && v4 != &off_14003C7A0 && !*((_DWORD *)v4 + 4) )
      _acrt_free_locale(v4);
  }
  *((_QWORD *)a1 + 18) = a2;
  if ( a2 )
    _acrt_add_locale_ref(a2);
}

```

## disassembly

```asm
0x1400195f0  mov     [rsp+arg_0], rbx
0x1400195f5  push    rdi
0x1400195f6  sub     rsp, 20h
0x1400195fa  mov     rdi, rcx
0x1400195fd  mov     rbx, rdx
0x140019600  mov     rcx, [rcx+90h]
0x140019607  test    rcx, rcx
0x14001960a  jz      short loc_140019638
0x14001960c  call    __acrt_release_locale_ref
0x140019611  mov     rcx, [rdi+90h]; Block
0x140019618  cmp     rcx, cs:qword_14003E5A8
0x14001961f  jz      short loc_140019638
0x140019621  lea     rax, off_14003C7A0
0x140019628  cmp     rcx, rax
0x14001962b  jz      short loc_140019638
0x14001962d  cmp     dword ptr [rcx+10h], 0
0x140019631  jnz     short loc_140019638
0x140019633  call    __acrt_free_locale
0x140019638  mov     [rdi+90h], rbx
0x14001963f  test    rbx, rbx
0x140019642  jz      short loc_14001964C
0x140019644  mov     rcx, rbx
0x140019647  call    __acrt_add_locale_ref
0x14001964c  mov     rbx, [rsp+28h+arg_0]
0x140019651  add     rsp, 20h
0x140019655  pop     rdi
0x140019656  retn
```
