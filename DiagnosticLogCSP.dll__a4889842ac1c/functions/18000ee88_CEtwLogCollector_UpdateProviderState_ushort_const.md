# CEtwLogCollector::UpdateProviderState(ushort const *)

- ea: `0x18000ee88`
- end: `0x18000eefd`
- name: `?UpdateProviderState@CEtwLogCollector@@AEAAJPEBG@Z`
- size: `117`
- prototype: `__int64 __fastcall(CEtwLogCollector *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18000d710`
- `0x18000d818`
- `0x18000e374`

## callees

- `0x1800011a4`
- `0x18000ed34`
- `0x18000ee88`

## pseudocode

```c
__int64 __fastcall CEtwLogCollector::UpdateProviderState(
        CEtwLogCollector *this,
        const unsigned __int16 *a2,
        __int64 a3,
        __int64 a4)
{
  const WCHAR *v4; // rbx
  unsigned int updated; // edi
  unsigned int v7; // [rsp+48h] [rbp+10h] BYREF
  const WCHAR *v8; // [rsp+50h] [rbp+18h] BYREF

  v4 = a2;
  if ( a2 )
    updated = CEtwLogCollector::UpdateProviderProperties(this, a2, 1, a4);
  else
    updated = -2147024809;
  if ( (unsigned int)dword_180048E90 > 5 )
  {
    v7 = updated;
    if ( !v4 )
      v4 = &String2;
    v8 = v4;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (unsigned int)dword_180048E90,
      (__int64)byte_18003F2C5,
      a3,
      a4,
      &v8,
      (__int64)&v7);
  }
  return updated;
}

```

## disassembly

```asm
0x18000ee88  mov     [rsp+arg_0], rbx
0x18000ee8d  push    rdi
0x18000ee8e  sub     rsp, 30h
0x18000ee92  mov     rbx, rdx
0x18000ee95  test    rdx, rdx
0x18000ee98  jnz     short loc_18000EEA1
0x18000ee9a  mov     edi, 80070057h
0x18000ee9f  jmp     short loc_18000EEAE
0x18000eea1  mov     r8d, 1; int
0x18000eea7  call    ?UpdateProviderProperties@CEtwLogCollector@@AEAAJPEBGH@Z; CEtwLogCollector::UpdateProviderProperties(ushort const *,int)
0x18000eeac  mov     edi, eax
0x18000eeae  mov     ecx, cs:dword_180048E90
0x18000eeb4  cmp     ecx, 5
0x18000eeb7  jbe     short loc_18000EEF0
0x18000eeb9  test    rbx, rbx
0x18000eebc  mov     [rsp+38h+arg_8], edi
0x18000eec0  lea     rax, String2
0x18000eec7  cmovz   rbx, rax
0x18000eecb  lea     rdx, byte_18003F2C5
0x18000eed2  lea     rax, [rsp+38h+arg_8]
0x18000eed7  mov     [rsp+38h+arg_10], rbx
0x18000eedc  mov     [rsp+38h+var_10], rax
0x18000eee1  lea     rax, [rsp+38h+arg_10]
0x18000eee6  mov     [rsp+38h+var_18], rax
0x18000eeeb  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000eef0  mov     rbx, [rsp+38h+arg_0]
0x18000eef5  mov     eax, edi
0x18000eef7  add     rsp, 30h
0x18000eefb  pop     rdi
0x18000eefc  retn
```
