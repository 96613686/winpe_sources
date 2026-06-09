# CEtwLogCollector::UpdateProviderState(ushort const *)

- ea: `0x18000f5cc`
- end: `0x18000f642`
- name: `?UpdateProviderState@CEtwLogCollector@@AEAAJPEBG@Z`
- size: `118`
- prototype: `__int64 __fastcall(CEtwLogCollector *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18000ddbc`
- `0x18000dec8`
- `0x18000ea88`

## callees

- `0x1800011ac`
- `0x18000f478`
- `0x18000f5cc`

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
  if ( (unsigned int)dword_18004AE90 > 5 )
  {
    v7 = updated;
    if ( !v4 )
      v4 = &String2;
    v8 = v4;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (unsigned int)dword_18004AE90,
      (unsigned __int8 *)byte_1800412C5,
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
0x18000f5cc  mov     [rsp+arg_0], rbx
0x18000f5d1  push    rdi
0x18000f5d2  sub     rsp, 30h
0x18000f5d6  mov     rbx, rdx
0x18000f5d9  test    rdx, rdx
0x18000f5dc  jnz     short loc_18000F5E5
0x18000f5de  mov     edi, 80070057h
0x18000f5e3  jmp     short loc_18000F5F2
0x18000f5e5  mov     r8d, 1; int
0x18000f5eb  call    ?UpdateProviderProperties@CEtwLogCollector@@AEAAJPEBGH@Z; CEtwLogCollector::UpdateProviderProperties(ushort const *,int)
0x18000f5f0  mov     edi, eax
0x18000f5f2  mov     ecx, cs:dword_18004AE90
0x18000f5f8  cmp     ecx, 5
0x18000f5fb  jbe     short loc_18000F634
0x18000f5fd  test    rbx, rbx
0x18000f600  mov     [rsp+38h+arg_8], edi
0x18000f604  lea     rax, String2
0x18000f60b  cmovz   rbx, rax
0x18000f60f  lea     rdx, byte_1800412C5
0x18000f616  lea     rax, [rsp+38h+arg_8]
0x18000f61b  mov     [rsp+38h+arg_10], rbx
0x18000f620  mov     [rsp+38h+var_10], rax
0x18000f625  lea     rax, [rsp+38h+arg_10]
0x18000f62a  mov     [rsp+38h+var_18], rax
0x18000f62f  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000f634  mov     rbx, [rsp+38h+arg_0]
0x18000f639  mov     eax, edi
0x18000f63b  add     rsp, 30h
0x18000f63f  pop     rdi
0x18000f640  retn
```
