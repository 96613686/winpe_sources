# FSConfiguration::InternalInitialize(void)

- ea: `0x18003dbe0`
- end: `0x18003dc60`
- name: `?InternalInitialize@FSConfiguration@@MEAAJXZ`
- size: `128`
- prototype: `__int64 __fastcall(FSConfiguration *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800060f8`
- `0x180006a68`
- `0x180006a98`
- `0x18003dbe0`

## import_xrefs

- `MFPlat!MFCreateAttributes` at `0x18003dc1b`
- `MFPlat!MFCreateAttributes` at `0x18003dc1b`

## pseudocode

```c
__int64 __fastcall FSConfiguration::InternalInitialize(IMFAttributes **this)
{
  HRESULT v2; // ebx
  __int64 v3; // rdx

  if ( this[7] )
  {
    wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(this + 10);
    v2 = MFCreateAttributes(this + 10, 1u);
    if ( v2 < 0 && _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v3 = 72;
      goto LABEL_7;
    }
  }
  else
  {
    v2 = -2147024809;
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v3 = 71;
LABEL_7:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v3, &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids, this, v2);
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18003dbe0  mov     [rsp+arg_0], rbx
0x18003dbe5  push    rdi
0x18003dbe6  sub     rsp, 30h
0x18003dbea  cmp     qword ptr [rcx+38h], 0
0x18003dbef  mov     rdi, rcx
0x18003dbf2  jnz     short loc_18003DC09
0x18003dbf4  mov     ebx, 80070057h
0x18003dbf9  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003dbfe  cmp     al, 1
0x18003dc00  jb      short loc_18003DC53
0x18003dc02  mov     edx, 47h ; 'G'
0x18003dc07  jmp     short loc_18003DC35
0x18003dc09  add     rcx, 50h ; 'P'
0x18003dc0d  call    ?reset@?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(void)
0x18003dc12  mov     edx, 1; cInitialSize
0x18003dc17  lea     rcx, [rdi+50h]; ppMFAttributes
0x18003dc1b  call    cs:__imp_MFCreateAttributes
0x18003dc21  mov     ebx, eax
0x18003dc23  test    eax, eax
0x18003dc25  jns     short loc_18003DC53
0x18003dc27  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003dc2c  cmp     al, 1
0x18003dc2e  jb      short loc_18003DC53
0x18003dc30  mov     edx, 48h ; 'H'
0x18003dc35  mov     rcx, cs:WPP_GLOBAL_Control
0x18003dc3c  lea     r8, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x18003dc43  mov     r9, rdi
0x18003dc46  mov     [rsp+38h+var_18], ebx
0x18003dc4a  mov     rcx, [rcx+10h]
0x18003dc4e  call    WPP_SF_qD
0x18003dc53  mov     eax, ebx
0x18003dc55  mov     rbx, [rsp+38h+arg_0]
0x18003dc5a  add     rsp, 30h
0x18003dc5e  pop     rdi
0x18003dc5f  retn
```
