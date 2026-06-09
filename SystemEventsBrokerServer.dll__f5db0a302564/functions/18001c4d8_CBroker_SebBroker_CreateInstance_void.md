# CBroker::SebBroker::CreateInstance(void)

- ea: `0x18001c4d8`
- end: `0x18001c573`
- name: `?CreateInstance@SebBroker@CBroker@@SAXXZ`
- size: `155`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001fb20`

## callees

- `0x180005a50`
- `0x1800076a0`
- `0x180017120`
- `0x18001c4d8`
- `0x18001c57c`
- `0x18001c824`
- `0x18001c8e4`

## pseudocode

```c
void CBroker::SebBroker::CreateInstance(void)
{
  __int64 *v0; // rax
  __int64 v1; // [rsp+20h] [rbp-18h] BYREF
  std::_Ref_count_base *v2; // [rsp+28h] [rbp-10h]

  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
  TlgRegisterAggregateProviderEx(&qword_180035088);
  v0 = std::make_shared<CBroker::SebBroker,>(&v1);
  std::shared_ptr<CBroker::SebBroker>::operator=(&CBroker::SebBroker::Instance, v0);
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  try
  {
    CBroker::SebBroker::Initialize(CBroker::SebBroker::Instance);
  }
  catch ( ... )
  {
    std::shared_ptr<CBroker::SebBroker>::reset();
    throw;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
}

```

## disassembly

```asm
0x18001c4d8  sub     rsp, 38h
0x18001c4dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c4e3  test    byte ptr [rcx+1Ch], 1
0x18001c4e7  jz      short loc_18001C504
0x18001c4e9  cmp     byte ptr [rcx+19h], 4
0x18001c4ed  jb      short loc_18001C504
0x18001c4ef  mov     edx, 0Ch
0x18001c4f4  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x18001c4fb  mov     rcx, [rcx+10h]
0x18001c4ff  call    WPP_SF_
0x18001c504  lea     rcx, qword_180035088; CallbackContext
0x18001c50b  call    TlgRegisterAggregateProviderEx
0x18001c510  lea     rcx, [rsp+38h+var_18]
0x18001c515  call    ??$make_shared@VSebBroker@CBroker@@$$V@std@@YA?AV?$shared_ptr@VSebBroker@CBroker@@@0@XZ; std::make_shared<CBroker::SebBroker,>(void)
0x18001c51a  mov     rdx, rax
0x18001c51d  lea     rcx, ?Instance@SebBroker@CBroker@@0V?$shared_ptr@VSebBroker@CBroker@@@std@@A; std::shared_ptr<CBroker::SebBroker> CBroker::SebBroker::Instance
0x18001c524  call    ??4?$shared_ptr@VSebBroker@CBroker@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CBroker::SebBroker>::operator=(std::shared_ptr<CBroker::SebBroker> &&)
0x18001c529  mov     rcx, [rsp+38h+var_10]; this
0x18001c52e  test    rcx, rcx
0x18001c531  jz      short loc_18001C539
0x18001c533  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001c538  nop
0x18001c539  mov     rcx, qword ptr cs:?Instance@SebBroker@CBroker@@0V?$shared_ptr@VSebBroker@CBroker@@@std@@A; this
0x18001c540  call    ?Initialize@SebBroker@CBroker@@QEAAXXZ; CBroker::SebBroker::Initialize(void)
0x18001c545  nop
0x18001c546  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c54d  test    byte ptr [rcx+1Ch], 1
0x18001c551  jz      short loc_18001C56E
0x18001c553  cmp     byte ptr [rcx+19h], 4
0x18001c557  jb      short loc_18001C56E
0x18001c559  mov     edx, 0Dh
0x18001c55e  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x18001c565  mov     rcx, [rcx+10h]
0x18001c569  call    WPP_SF_
0x18001c56e  add     rsp, 38h
0x18001c572  retn
```
