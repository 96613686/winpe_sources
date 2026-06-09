# std::_Temporary_owner<XinputHid::XInputHidDevice>::~_Temporary_owner<XinputHid::XInputHidDevice>(void)

- ea: `0x18000ee1c`
- end: `0x18000ee67`
- name: `??1?$_Temporary_owner@UXInputHidDevice@XinputHid@@@std@@QEAA@XZ`
- size: `75`
- prototype: `void __fastcall(_QWORD **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180011812`

## callees

- `0x180001b6c`
- `0x180009260`
- `0x18000ee1c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ee33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ee33`

## pseudocode

```c
void __fastcall std::_Temporary_owner<XinputHid::XInputHidDevice>::~_Temporary_owner<XinputHid::XInputHidDevice>(
        _QWORD **a1)
{
  _QWORD *v1; // rbx
  void *v2; // rcx
  const char *v3; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = *a1;
  if ( *a1 )
  {
    v2 = (void *)v1[1];
    if ( v2 )
    {
      if ( !CloseHandle(v2) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0x17,
          (unsigned int)"onecoreuap\\xbox\\devices\\gipmanagementsvc\\lib\\XinputHidInterface.h",
          v3);
    }
    operator delete(v1, (const struct std::nothrow_t *)0x20);
  }
}

```

## disassembly

```asm
0x18000ee1c  push    rbx
0x18000ee1e  sub     rsp, 20h
0x18000ee22  mov     rbx, [rcx]
0x18000ee25  test    rbx, rbx
0x18000ee28  jz      short loc_18000EE4A
0x18000ee2a  mov     rcx, [rbx+8]; hObject
0x18000ee2e  test    rcx, rcx
0x18000ee31  jz      short loc_18000EE3D
0x18000ee33  call    cs:__imp_CloseHandle
0x18000ee39  test    eax, eax
0x18000ee3b  jz      short loc_18000EE50
0x18000ee3d  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x18000ee42  mov     rcx, rbx; void *
0x18000ee45  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000ee4a  add     rsp, 20h
0x18000ee4e  pop     rbx
0x18000ee4f  retn
0x18000ee50  mov     rcx, [rsp+28h]; this
0x18000ee55  lea     r8, aOnecoreuapXbox; "onecoreuap\\xbox\\devices\\gipmanagemen"...
0x18000ee5c  mov     edx, 17h; void *
0x18000ee61  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
