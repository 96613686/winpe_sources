# __acrt_update_multibyte_info

- ea: `0x180012e94`
- end: `0x180012ec5`
- name: `__acrt_update_multibyte_info`
- size: `49`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180008c44`
- `0x1800135a0`
- `0x180013740`
- `0x1800138c0`
- `0x180013a70`
- `0x180019fa0`
- `0x18001a2c0`
- `0x180020680`

## callees

- `0x18000a4b0`
- `0x180012e94`

## pseudocode

```c
__int64 __fastcall _acrt_update_multibyte_info(__int64 a1, __int64 *a2)
{
  __int64 result; // rax

  result = (__int64)_acrt_current_multibyte_data;
  if ( (void *)*a2 != _acrt_current_multibyte_data )
  {
    result = *(unsigned int *)(a1 + 936);
    if ( ((unsigned int)result & _globallocalestatus) == 0 )
    {
      result = _acrt_update_thread_multibyte_data();
      *a2 = result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180012e94  push    rbx
0x180012e96  sub     rsp, 20h
0x180012e9a  mov     rax, cs:__acrt_current_multibyte_data
0x180012ea1  mov     rbx, rdx
0x180012ea4  cmp     [rdx], rax
0x180012ea7  jz      short loc_180012EBF
0x180012ea9  mov     eax, [rcx+3A8h]
0x180012eaf  test    cs:__globallocalestatus, eax
0x180012eb5  jnz     short loc_180012EBF
0x180012eb7  call    __acrt_update_thread_multibyte_data
0x180012ebc  mov     [rbx], rax
0x180012ebf  add     rsp, 20h
0x180012ec3  pop     rbx
0x180012ec4  retn
```
