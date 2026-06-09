# CEditionUpgradeHelper::UpdateOperatingSystem(ushort const *)

- ea: `0x18000aed0`
- end: `0x18000af4b`
- name: `?UpdateOperatingSystem@CEditionUpgradeHelper@@UEAAJPEBG@Z`
- size: `123`
- prototype: `__int64 __fastcall(CEditionUpgradeHelper *this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x180008c60`
- `0x1800096e8`
- `0x180009978`
- `0x18000aed0`
- `0x180027010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000aee5`
- `OLEAUT32!__imp_SysAllocString` at `0x18000aee5`
- `OLEAUT32!__imp_SysFreeString` at `0x18000af2c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000af2c`

## pseudocode

```c
__int64 __fastcall CEditionUpgradeHelper::UpdateOperatingSystem(
        CEditionUpgradeHelper *this,
        const unsigned __int16 *a2)
{
  OLECHAR *v3; // rdi
  int v4; // eax
  unsigned int v5; // ebx

  v3 = SysAllocString(a2);
  if ( !*((_QWORD *)this + 3)
    && (v4 = CEditionUpgradeHelper::Initialize((CEditionUpgradeHelper *)((char *)this - 8)), v5 = v4, v4 < 0)
    || (v4 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *))(**((_QWORD **)this + 3) + 32LL))(*((_QWORD *)this + 3), v3),
        v5 = v4,
        v4 < 0) )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v4);
  }
  if ( v3 )
    SysFreeString(v3);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  return v5;
}

```

## disassembly

```asm
0x18000aed0  mov     [rsp+arg_0], rbx
0x18000aed5  mov     [rsp+arg_8], rsi
0x18000aeda  push    rdi
0x18000aedb  sub     rsp, 20h
0x18000aedf  mov     rsi, rcx
0x18000aee2  mov     rcx, rdx; psz
0x18000aee5  call    cs:__imp_SysAllocString
0x18000aeeb  cmp     qword ptr [rsi+18h], 0
0x18000aef0  mov     rdi, rax
0x18000aef3  jnz     short loc_18000AF04
0x18000aef5  lea     rcx, [rsi-8]; this
0x18000aef9  call    ?Initialize@CEditionUpgradeHelper@@AEAAJXZ; CEditionUpgradeHelper::Initialize(void)
0x18000aefe  mov     ebx, eax
0x18000af00  test    eax, eax
0x18000af02  js      short loc_18000AF1D
0x18000af04  mov     rcx, [rsi+18h]
0x18000af08  mov     rdx, rdi
0x18000af0b  mov     rax, [rcx]
0x18000af0e  mov     rax, [rax+20h]
0x18000af12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af17  mov     ebx, eax
0x18000af19  test    eax, eax
0x18000af1b  jns     short loc_18000AF24
0x18000af1d  mov     ecx, eax
0x18000af1f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000af24  test    rdi, rdi
0x18000af27  jz      short loc_18000AF32
0x18000af29  mov     rcx, rdi; bstrString
0x18000af2c  call    cs:__imp_SysFreeString
0x18000af32  mov     ecx, ebx
0x18000af34  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000af39  mov     rsi, [rsp+28h+arg_8]
0x18000af3e  mov     eax, ebx
0x18000af40  mov     rbx, [rsp+28h+arg_0]
0x18000af45  add     rsp, 20h
0x18000af49  pop     rdi
0x18000af4a  retn
```
