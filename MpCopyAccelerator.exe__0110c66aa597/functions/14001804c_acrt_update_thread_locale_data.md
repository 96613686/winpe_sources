# __acrt_update_thread_locale_data

- ea: `0x14001804c`
- end: `0x1400180ba`
- name: `__acrt_update_thread_locale_data`
- size: `110`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140013d34`
- `0x140013d68`

## callees

- `0x140013658`
- `0x140013b68`
- `0x140016848`
- `0x1400168a8`
- `0x14001804c`
- `0x1400180bc`

## pseudocode

```c
__int64 _acrt_update_thread_locale_data()
{
  __int64 v0; // rax
  __int64 *v1; // rdi
  __int64 v2; // rbx

  v0 = _acrt_getptd();
  v1 = (__int64 *)(v0 + 144);
  if ( (*(_DWORD *)(v0 + 936) & _globallocalestatus) == 0 || (v2 = *v1) == 0 )
  {
    _acrt_lock(4);
    v2 = updatetlocinfoEx_nolock(v1, _acrt_current_locale_data);
    _acrt_unlock(4);
    if ( !v2 )
      abort();
  }
  return v2;
}

```

## disassembly

```asm
0x14001804c  mov     [rsp+arg_0], rbx
0x140018051  push    rdi
0x140018052  sub     rsp, 20h
0x140018056  call    __acrt_getptd
0x14001805b  lea     rdi, [rax+90h]
0x140018062  mov     ecx, [rax+3A8h]
0x140018068  mov     eax, cs:__globallocalestatus
0x14001806e  test    eax, ecx
0x140018070  jz      short loc_14001807A
0x140018072  mov     rbx, [rdi]
0x140018075  test    rbx, rbx
0x140018078  jnz     short loc_1400180A6
0x14001807a  mov     ecx, 4
0x14001807f  call    __acrt_lock
0x140018084  nop
0x140018085  mov     rdx, cs:__acrt_current_locale_data
0x14001808c  mov     rcx, rdi
0x14001808f  call    _updatetlocinfoEx_nolock
0x140018094  mov     rbx, rax
0x140018097  mov     ecx, 4
0x14001809c  call    __acrt_unlock
0x1400180a1  test    rbx, rbx
0x1400180a4  jz      short loc_1400180B4
0x1400180a6  mov     rax, rbx
0x1400180a9  mov     rbx, [rsp+28h+arg_0]
0x1400180ae  add     rsp, 20h
0x1400180b2  pop     rdi
0x1400180b3  retn
0x1400180b4  call    abort
0x140026046  push    rbp
0x140026048  sub     rsp, 20h
0x14002604c  mov     rbp, rdx
0x14002604f  mov     ecx, 4
0x140026054  add     rsp, 20h
0x140026058  pop     rbp
0x140026059  jmp     __acrt_unlock
```
