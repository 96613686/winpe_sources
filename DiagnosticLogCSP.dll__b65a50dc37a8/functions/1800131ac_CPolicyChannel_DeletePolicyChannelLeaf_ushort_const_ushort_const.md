# CPolicyChannel::DeletePolicyChannelLeaf(ushort const *,ushort const *)

- ea: `0x1800131ac`
- end: `0x18001326c`
- name: `?DeletePolicyChannelLeaf@CPolicyChannel@@SAJPEBG0@Z`
- size: `192`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPCWSTR lpValueName)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000c7b0`

## callees

- `0x1800011ac`
- `0x180012e00`
- `0x1800131ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800131ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800131ff`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800131e9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800131e9`

## pseudocode

```c
__int64 __fastcall CPolicyChannel::DeletePolicyChannelLeaf(
        const unsigned __int16 *a1,
        LPCWSTR lpValueName,
        int a3,
        int a4)
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
      LODWORD(a1) = hKey[0];
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
  if ( (unsigned int)dword_18004AE90 > 5 )
  {
    LODWORD(v10) = v6;
    if ( !v5 )
      v5 = &String2;
    v11 = v5;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (_DWORD)a1,
      (unsigned int)byte_18004201B,
      a3,
      a4,
      (__int64)&v11,
      (__int64)&v10);
  }
  return v6;
}

```

## disassembly

```asm
0x1800131ac  mov     [rsp+arg_8], rbx
0x1800131b1  mov     [rsp+arg_18], rsi
0x1800131b6  mov     [rsp+arg_0], rcx
0x1800131bb  push    rdi
0x1800131bc  sub     rsp, 50h
0x1800131c0  mov     rsi, rdx
0x1800131c3  mov     rbx, rcx
0x1800131c6  xor     edi, edi
0x1800131c8  test    rcx, rcx
0x1800131cb  jnz     short loc_1800131D4
0x1800131cd  mov     edi, 80070057h
0x1800131d2  jmp     short loc_180013217
0x1800131d4  mov     rdx, rcx; unsigned __int16 *
0x1800131d7  lea     rcx, [rsp+58h+hKey]; this
0x1800131dc  call    ??0CPolicyChannel@@QEAA@PEBG@Z; CPolicyChannel::CPolicyChannel(ushort const *)
0x1800131e1  mov     rdx, rsi; lpValueName
0x1800131e4  mov     rcx, [rsp+58h+hKey]; hKey
0x1800131e9  call    cs:__imp_RegDeleteValueW
0x1800131f0  nop     dword ptr [rax+rax+00h]
0x1800131f5  mov     rcx, [rsp+58h+hKey]; hKey
0x1800131fa  test    rcx, rcx
0x1800131fd  jz      short loc_18001320C
0x1800131ff  call    cs:__imp_RegCloseKey
0x180013206  nop     dword ptr [rax+rax+00h]
0x18001320b  nop
0x18001320c  jmp     short loc_180013217
0x18001320e  mov     edi, dword ptr [rsp+58h+arg_10]
0x180013212  mov     rbx, [rsp+58h+arg_0]
0x180013217  mov     eax, cs:dword_18004AE90
0x18001321d  cmp     eax, 5
0x180013220  jbe     short loc_180013259
0x180013222  mov     dword ptr [rsp+58h+arg_0], edi
0x180013226  lea     rax, String2
0x18001322d  test    rbx, rbx
0x180013230  cmovz   rbx, rax
0x180013234  mov     [rsp+58h+arg_10], rbx
0x180013239  lea     rax, [rsp+58h+arg_0]
0x18001323e  mov     [rsp+58h+var_30], rax
0x180013243  lea     rax, [rsp+58h+arg_10]
0x180013248  mov     [rsp+58h+var_38], rax
0x18001324d  lea     rdx, byte_18004201B
0x180013254  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180013259  mov     eax, edi
0x18001325b  mov     rbx, [rsp+58h+arg_8]
0x180013260  mov     rsi, [rsp+58h+arg_18]
0x180013265  add     rsp, 50h
0x180013269  pop     rdi
0x18001326a  retn
```
