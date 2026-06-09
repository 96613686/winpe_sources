# FSConfiguration::InternalInitialize(bool)

- ea: `0x180074ca0`
- end: `0x180074d37`
- name: `?InternalInitialize@FSConfiguration@@MEAAJ_N@Z`
- size: `151`
- prototype: `__int64 __fastcall(FSConfiguration *__hidden this, bool)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005fa0`
- `0x180028d34`
- `0x180074ca0`

## import_xrefs

- `MFPlat!MFCreateAttributes` at `0x180074d01`
- `MFPlat!MFCreateAttributes` at `0x180074d01`

## pseudocode

```c
__int64 __fastcall FSConfiguration::InternalInitialize(IMFAttributes **this, char a2)
{
  unsigned int v4; // ebx
  HRESULT v5; // eax

  if ( this[7] )
  {
    wil::com_ptr_t<IMFAttributes,wil::err_returncode_policy>::reset(this + 10);
    v5 = MFCreateAttributes(this + 10, 1u);
    v4 = v5;
    if ( v5 >= 0 )
    {
      *((_BYTE *)this + 88) = a2;
    }
    else if ( g_wppLevels )
    {
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids, this, v5);
    }
  }
  else
  {
    v4 = -2147024809;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        73,
        &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids,
        this,
        -2147024809);
  }
  return v4;
}

```

## disassembly

```asm
0x180074ca0  mov     [rsp+arg_0], rbx
0x180074ca5  mov     [rsp+arg_8], rsi
0x180074caa  push    rdi
0x180074cab  sub     rsp, 30h
0x180074caf  cmp     qword ptr [rcx+38h], 0
0x180074cb4  mov     sil, dl
0x180074cb7  mov     rdi, rcx
0x180074cba  jnz     short loc_180074CEF
0x180074cbc  mov     ebx, 80070057h
0x180074cc1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180074cc8  jb      short loc_180074D25
0x180074cca  mov     edx, 49h ; 'I'
0x180074ccf  mov     [rsp+38h+var_18], ebx
0x180074cd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180074cda  lea     r8, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x180074ce1  mov     r9, rdi
0x180074ce4  mov     rcx, [rcx+10h]
0x180074ce8  call    WPP_SF_qD
0x180074ced  jmp     short loc_180074D25
0x180074cef  add     rcx, 50h ; 'P'
0x180074cf3  call    ?reset@?$com_ptr_t@UIMFAttributes@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMFAttributes,wil::err_returncode_policy>::reset(void)
0x180074cf8  mov     edx, 1; cInitialSize
0x180074cfd  lea     rcx, [rdi+50h]; ppMFAttributes
0x180074d01  call    cs:__imp_MFCreateAttributes
0x180074d07  mov     ebx, eax
0x180074d09  test    eax, eax
0x180074d0b  jns     short loc_180074D21
0x180074d0d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180074d14  jb      short loc_180074D25
0x180074d16  mov     edx, 4Ah ; 'J'
0x180074d1b  mov     [rsp+38h+var_18], eax
0x180074d1f  jmp     short loc_180074CD3
0x180074d21  mov     [rdi+58h], sil
0x180074d25  mov     rsi, [rsp+38h+arg_8]
0x180074d2a  mov     eax, ebx
0x180074d2c  mov     rbx, [rsp+38h+arg_0]
0x180074d31  add     rsp, 30h
0x180074d35  pop     rdi
0x180074d36  retn
```
