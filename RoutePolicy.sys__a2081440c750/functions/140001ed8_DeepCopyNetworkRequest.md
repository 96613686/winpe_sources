# DeepCopyNetworkRequest

- ea: `0x140001ed8`
- end: `0x140001fb9`
- name: `DeepCopyNetworkRequest`
- size: `225`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x1400018cc`

## callees

- `0x140001008`
- `0x140001aac`
- `0x140001ed8`

## string_xrefs

- `0x140001f32`: `Failed to copy AppId`

## pseudocode

```c
__int64 __fastcall DeepCopyNetworkRequest(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  int v6; // esi
  __int16 *v7; // rdx
  int v9; // [rsp+48h] [rbp+10h] BYREF
  const char *v10; // [rsp+50h] [rbp+18h] BYREF

  *(_OWORD *)a1 = 0;
  *(_OWORD *)(a1 + 16) = 0;
  *(_OWORD *)(a1 + 32) = 0;
  if ( (*(_DWORD *)a2 & 0x800) != 0 )
  {
    v6 = RoutePolicyCache::AllocateAndCopyStringParameter(
           (const char **)(a1 + 8),
           *(unsigned __int16 ***)(a2 + 8),
           a3,
           a4);
    if ( v6 < 0 )
    {
      if ( (unsigned int)dword_140012050 <= 2 )
        return (unsigned int)v6;
      v7 = (__int16 *)byte_14000E77B;
LABEL_5:
      v10 = "Failed to copy AppId";
      v9 = v6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (unsigned int)"Failed to copy AppId",
        (_DWORD)v7,
        a3,
        a4,
        (__int64)&v10,
        (__int64)&v9);
      return (unsigned int)v6;
    }
  }
  if ( (*(_DWORD *)a2 & 0x1000) != 0 )
  {
    v6 = RoutePolicyCache::AllocateAndCopyStringParameter(
           (const char **)(a1 + 16),
           *(unsigned __int16 ***)(a2 + 16),
           a3,
           a4);
    if ( v6 < 0 )
    {
      if ( (unsigned int)dword_140012050 <= 2 )
        return (unsigned int)v6;
      v7 = word_14000E5A2;
      goto LABEL_5;
    }
  }
  if ( (*(_DWORD *)a2 & 0x10000) != 0 )
    *(_DWORD *)(a1 + 24) = *(_DWORD *)(a2 + 24);
  *(_DWORD *)a1 = *(_DWORD *)a2;
  *(_WORD *)(a1 + 40) = *(_WORD *)(a2 + 40);
  *(_QWORD *)(a1 + 32) = *(_QWORD *)(a2 + 32);
  return 0;
}

```

## disassembly

```asm
0x140001ed8  mov     [rsp+arg_0], rbx
0x140001edd  mov     [rsp+arg_18], rsi
0x140001ee2  push    rdi
0x140001ee3  sub     rsp, 30h
0x140001ee7  xorps   xmm0, xmm0
0x140001eea  mov     rbx, rdx
0x140001eed  movups  xmmword ptr [rcx], xmm0
0x140001ef0  mov     rdi, rcx
0x140001ef3  movups  xmmword ptr [rcx+10h], xmm0
0x140001ef7  movups  xmmword ptr [rcx+20h], xmm0
0x140001efb  test    dword ptr [rdx], 800h
0x140001f01  jz      short loc_140001F55
0x140001f03  mov     rdx, [rdx+8]; unsigned __int16 **
0x140001f07  add     rcx, 8; this
0x140001f0b  call    ?AllocateAndCopyStringParameter@RoutePolicyCache@@YAJPEAPEAGPEBG@Z; RoutePolicyCache::AllocateAndCopyStringParameter(ushort * *,ushort const *)
0x140001f10  mov     esi, eax
0x140001f12  test    eax, eax
0x140001f14  jns     short loc_140001F55
0x140001f16  mov     ecx, cs:dword_140012050
0x140001f1c  cmp     ecx, 2
0x140001f1f  jbe     short loc_140001F51
0x140001f21  lea     rdx, byte_14000E77B
0x140001f28  lea     rax, [rsp+38h+arg_8]
0x140001f2d  mov     [rsp+38h+var_10], rax
0x140001f32  lea     rcx, aFailedToCopyAp; "Failed to copy AppId"
0x140001f39  lea     rax, [rsp+38h+arg_10]
0x140001f3e  mov     [rsp+38h+arg_10], rcx
0x140001f43  mov     [rsp+38h+var_18], rax
0x140001f48  mov     [rsp+38h+arg_8], esi
0x140001f4c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140001f51  mov     eax, esi
0x140001f53  jmp     short loc_140001FA8
0x140001f55  test    dword ptr [rbx], 1000h
0x140001f5b  jz      short loc_140001F84
0x140001f5d  mov     rdx, [rbx+10h]; unsigned __int16 **
0x140001f61  lea     rcx, [rdi+10h]; this
0x140001f65  call    ?AllocateAndCopyStringParameter@RoutePolicyCache@@YAJPEAPEAGPEBG@Z; RoutePolicyCache::AllocateAndCopyStringParameter(ushort * *,ushort const *)
0x140001f6a  mov     esi, eax
0x140001f6c  test    eax, eax
0x140001f6e  jns     short loc_140001F84
0x140001f70  mov     ecx, cs:dword_140012050
0x140001f76  cmp     ecx, 2
0x140001f79  jbe     short loc_140001F51
0x140001f7b  lea     rdx, word_14000E5A2
0x140001f82  jmp     short loc_140001F28
0x140001f84  test    dword ptr [rbx], 10000h
0x140001f8a  jz      short loc_140001F92
0x140001f8c  mov     eax, [rbx+18h]
0x140001f8f  mov     [rdi+18h], eax
0x140001f92  mov     eax, [rbx]
0x140001f94  mov     [rdi], eax
0x140001f96  movzx   eax, word ptr [rbx+28h]
0x140001f9a  mov     [rdi+28h], ax
0x140001f9e  mov     rax, [rbx+20h]
0x140001fa2  mov     [rdi+20h], rax
0x140001fa6  xor     eax, eax
0x140001fa8  mov     rbx, [rsp+38h+arg_0]
0x140001fad  mov     rsi, [rsp+38h+arg_18]
0x140001fb2  add     rsp, 30h
0x140001fb6  pop     rdi
0x140001fb7  retn
```
