# FSConfiguration::InternalInitialize(bool)

- ea: `0x18003dc70`
- end: `0x18003dd07`
- name: `?InternalInitialize@FSConfiguration@@MEAAJ_N@Z`
- size: `151`
- prototype: `__int64 __fastcall(FSConfiguration *__hidden this, bool)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006a68`
- `0x180006a98`
- `0x18003dc70`

## import_xrefs

- `MFPlat!MFCreateAttributes` at `0x18003dcd1`
- `MFPlat!MFCreateAttributes` at `0x18003dcd1`

## pseudocode

```c
__int64 __fastcall FSConfiguration::InternalInitialize(IMFAttributes **this, char a2)
{
  unsigned int v4; // ebx
  HRESULT v5; // eax

  if ( this[7] )
  {
    wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(this + 10);
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
0x18003dc70  mov     [rsp+arg_0], rbx
0x18003dc75  mov     [rsp+arg_8], rsi
0x18003dc7a  push    rdi
0x18003dc7b  sub     rsp, 30h
0x18003dc7f  cmp     qword ptr [rcx+38h], 0
0x18003dc84  mov     sil, dl
0x18003dc87  mov     rdi, rcx
0x18003dc8a  jnz     short loc_18003DCBF
0x18003dc8c  mov     ebx, 80070057h
0x18003dc91  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003dc98  jb      short loc_18003DCF5
0x18003dc9a  mov     edx, 49h ; 'I'
0x18003dc9f  mov     [rsp+38h+var_18], ebx
0x18003dca3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003dcaa  lea     r8, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x18003dcb1  mov     r9, rdi
0x18003dcb4  mov     rcx, [rcx+10h]
0x18003dcb8  call    WPP_SF_qD
0x18003dcbd  jmp     short loc_18003DCF5
0x18003dcbf  add     rcx, 50h ; 'P'
0x18003dcc3  call    ?reset@?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(void)
0x18003dcc8  mov     edx, 1; cInitialSize
0x18003dccd  lea     rcx, [rdi+50h]; ppMFAttributes
0x18003dcd1  call    cs:__imp_MFCreateAttributes
0x18003dcd7  mov     ebx, eax
0x18003dcd9  test    eax, eax
0x18003dcdb  jns     short loc_18003DCF1
0x18003dcdd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003dce4  jb      short loc_18003DCF5
0x18003dce6  mov     edx, 4Ah ; 'J'
0x18003dceb  mov     [rsp+38h+var_18], eax
0x18003dcef  jmp     short loc_18003DCA3
0x18003dcf1  mov     [rdi+58h], sil
0x18003dcf5  mov     rsi, [rsp+38h+arg_8]
0x18003dcfa  mov     eax, ebx
0x18003dcfc  mov     rbx, [rsp+38h+arg_0]
0x18003dd01  add     rsp, 30h
0x18003dd05  pop     rdi
0x18003dd06  retn
```
