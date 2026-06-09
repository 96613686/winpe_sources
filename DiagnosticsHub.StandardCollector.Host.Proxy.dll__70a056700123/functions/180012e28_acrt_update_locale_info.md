# __acrt_update_locale_info

- ea: `0x180012e28`
- end: `0x180012e59`
- name: `__acrt_update_locale_info`
- size: `49`
- prototype: ``
- caller_count: `15`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180008c44`
- `0x18000f370`
- `0x1800135a0`
- `0x180013740`
- `0x1800138c0`
- `0x180013a70`
- `0x180015940`
- `0x180015974`
- `0x180016c4c`
- `0x180016c7c`
- `0x180016cac`
- `0x180016ce0`
- `0x180019fa0`
- `0x18001a2c0`
- `0x180020680`

## callees

- `0x18000fb1c`
- `0x180012e28`

## pseudocode

```c
__int64 __fastcall _acrt_update_locale_info(__int64 a1, __int64 *a2)
{
  __int64 result; // rax

  result = _acrt_current_locale_data;
  if ( *a2 != _acrt_current_locale_data )
  {
    result = *(unsigned int *)(a1 + 936);
    if ( ((unsigned int)result & _globallocalestatus) == 0 )
    {
      result = _acrt_update_thread_locale_data();
      *a2 = result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180012e28  push    rbx
0x180012e2a  sub     rsp, 20h
0x180012e2e  mov     rax, cs:__acrt_current_locale_data
0x180012e35  mov     rbx, rdx
0x180012e38  cmp     [rdx], rax
0x180012e3b  jz      short loc_180012E53
0x180012e3d  mov     eax, [rcx+3A8h]
0x180012e43  test    cs:__globallocalestatus, eax
0x180012e49  jnz     short loc_180012E53
0x180012e4b  call    __acrt_update_thread_locale_data
0x180012e50  mov     [rbx], rax
0x180012e53  add     rsp, 20h
0x180012e57  pop     rbx
0x180012e58  retn
```
