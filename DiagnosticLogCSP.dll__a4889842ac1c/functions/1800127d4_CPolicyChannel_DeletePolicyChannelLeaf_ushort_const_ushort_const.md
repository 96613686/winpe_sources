# CPolicyChannel::DeletePolicyChannelLeaf(ushort const *,ushort const *)

- ea: `0x1800127d4`
- end: `0x180012887`
- name: `?DeletePolicyChannelLeaf@CPolicyChannel@@SAJPEBG0@Z`
- size: `179`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPCWSTR lpValueName, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000c260`

## callees

- `0x1800011a4`
- `0x180012440`
- `0x1800127d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012821`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012821`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180012811`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180012811`

## pseudocode

```c
__int64 __fastcall CPolicyChannel::DeletePolicyChannelLeaf(
        const unsigned __int16 *a1,
        LPCWSTR lpValueName,
        __int64 a3,
        __int64 a4)
{
  const WCHAR *v5; // rbx
  unsigned int v6; // edi
  unsigned int v8; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey[4]; // [rsp+38h] [rbp-20h] BYREF
  const unsigned __int16 *v10; // [rsp+60h] [rbp+8h] BYREF
  const WCHAR *v11; // [rsp+70h] [rbp+18h] BYREF

  v10 = a1;
  v5 = a1;
  v6 = 0;
  if ( a1 )
  {
    try
    {
      CPolicyChannel::CPolicyChannel((CPolicyChannel *)hKey, a1);
      RegDeleteValueW(hKey[0], lpValueName);
      a1 = (const unsigned __int16 *)hKey[0];
      if ( hKey[0] )
        RegCloseKey(hKey[0]);
    }
    catch ( long v8 )
    {
      v6 = v8;
      v5 = v10;
    }
    catch ( ... )
    {
      v6 = -2147467259;
      v5 = v10;
    }
  }
  else
  {
    v6 = -2147024809;
  }
  if ( (unsigned int)dword_180048E90 > 5 )
  {
    LODWORD(v10) = v6;
    if ( !v5 )
      v5 = &String2;
    v11 = v5;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (__int64)a1,
      (__int64)byte_18004001B,
      a3,
      a4,
      &v11,
      (__int64)&v10);
  }
  return v6;
}

```

## disassembly

```asm
0x1800127d4  mov     [rsp+arg_8], rbx
0x1800127d9  mov     [rsp+arg_18], rsi
0x1800127de  mov     [rsp+arg_0], rcx
0x1800127e3  push    rdi
0x1800127e4  sub     rsp, 50h
0x1800127e8  mov     rsi, rdx
0x1800127eb  mov     rbx, rcx
0x1800127ee  xor     edi, edi
0x1800127f0  test    rcx, rcx
0x1800127f3  jnz     short loc_1800127FC
0x1800127f5  mov     edi, 80070057h
0x1800127fa  jmp     short loc_180012833
0x1800127fc  mov     rdx, rcx; unsigned __int16 *
0x1800127ff  lea     rcx, [rsp+58h+hKey]; this
0x180012804  call    ??0CPolicyChannel@@QEAA@PEBG@Z; CPolicyChannel::CPolicyChannel(ushort const *)
0x180012809  mov     rdx, rsi; lpValueName
0x18001280c  mov     rcx, [rsp+58h+hKey]; hKey
0x180012811  call    cs:__imp_RegDeleteValueW
0x180012817  mov     rcx, [rsp+58h+hKey]; hKey
0x18001281c  test    rcx, rcx
0x18001281f  jz      short loc_180012828
0x180012821  call    cs:__imp_RegCloseKey
0x180012827  nop
0x180012828  jmp     short loc_180012833
0x18001282a  mov     edi, dword ptr [rsp+58h+arg_10]
0x18001282e  mov     rbx, [rsp+58h+arg_0]
0x180012833  mov     eax, cs:dword_180048E90
0x180012839  cmp     eax, 5
0x18001283c  jbe     short loc_180012875
0x18001283e  mov     dword ptr [rsp+58h+arg_0], edi
0x180012842  lea     rax, String2
0x180012849  test    rbx, rbx
0x18001284c  cmovz   rbx, rax
0x180012850  mov     [rsp+58h+arg_10], rbx
0x180012855  lea     rax, [rsp+58h+arg_0]
0x18001285a  mov     [rsp+58h+var_30], rax
0x18001285f  lea     rax, [rsp+58h+arg_10]
0x180012864  mov     [rsp+58h+var_38], rax
0x180012869  lea     rdx, byte_18004001B
0x180012870  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180012875  mov     eax, edi
0x180012877  mov     rbx, [rsp+58h+arg_8]
0x18001287c  mov     rsi, [rsp+58h+arg_18]
0x180012881  add     rsp, 50h
0x180012885  pop     rdi
0x180012886  retn
```
