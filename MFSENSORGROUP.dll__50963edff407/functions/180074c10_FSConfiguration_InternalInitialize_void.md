# FSConfiguration::InternalInitialize(void)

- ea: `0x180074c10`
- end: `0x180074c94`
- name: `?InternalInitialize@FSConfiguration@@MEAAJXZ`
- size: `132`
- prototype: `__int64 __fastcall(FSConfiguration *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005fa0`
- `0x180028d34`
- `0x180074c10`

## import_xrefs

- `MFPlat!MFCreateAttributes` at `0x180074c4f`
- `MFPlat!MFCreateAttributes` at `0x180074c4f`

## pseudocode

```c
__int64 __fastcall FSConfiguration::InternalInitialize(IMFAttributes **this)
{
  unsigned int v2; // ebx
  HRESULT v3; // eax

  if ( this[7] )
  {
    wil::com_ptr_t<IMFAttributes,wil::err_returncode_policy>::reset(this + 10);
    v3 = MFCreateAttributes(this + 10, 1u);
    v2 = v3;
    if ( v3 < 0 && g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids, this, v3);
  }
  else
  {
    v2 = -2147024809;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        71,
        &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids,
        this,
        -2147024809);
  }
  return v2;
}

```

## disassembly

```asm
0x180074c10  mov     [rsp+arg_0], rbx
0x180074c15  push    rdi
0x180074c16  sub     rsp, 30h
0x180074c1a  cmp     qword ptr [rcx+38h], 0
0x180074c1f  mov     rdi, rcx
0x180074c22  jnz     short loc_180074C3D
0x180074c24  mov     ebx, 80070057h
0x180074c29  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180074c30  jb      short loc_180074C87
0x180074c32  mov     edx, 47h ; 'G'
0x180074c37  mov     [rsp+38h+var_18], ebx
0x180074c3b  jmp     short loc_180074C6D
0x180074c3d  add     rcx, 50h ; 'P'
0x180074c41  call    ?reset@?$com_ptr_t@UIMFAttributes@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMFAttributes,wil::err_returncode_policy>::reset(void)
0x180074c46  mov     edx, 1; cInitialSize
0x180074c4b  lea     rcx, [rdi+50h]; ppMFAttributes
0x180074c4f  call    cs:__imp_MFCreateAttributes
0x180074c55  mov     ebx, eax
0x180074c57  test    eax, eax
0x180074c59  jns     short loc_180074C87
0x180074c5b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180074c62  jb      short loc_180074C87
0x180074c64  mov     edx, 48h ; 'H'
0x180074c69  mov     [rsp+38h+var_18], eax
0x180074c6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180074c74  lea     r8, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x180074c7b  mov     r9, rdi
0x180074c7e  mov     rcx, [rcx+10h]
0x180074c82  call    WPP_SF_qD
0x180074c87  mov     eax, ebx
0x180074c89  mov     rbx, [rsp+38h+arg_0]
0x180074c8e  add     rsp, 30h
0x180074c92  pop     rdi
0x180074c93  retn
```
