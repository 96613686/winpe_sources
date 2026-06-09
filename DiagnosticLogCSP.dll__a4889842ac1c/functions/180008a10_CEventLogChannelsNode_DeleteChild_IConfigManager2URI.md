# CEventLogChannelsNode::DeleteChild(IConfigManager2URI *)

- ea: `0x180008a10`
- end: `0x180008aac`
- name: `?DeleteChild@CEventLogChannelsNode@@UEAAJPEAUIConfigManager2URI@@@Z`
- size: `156`
- prototype: `__int64 __fastcall(CEventLogChannelsNode *this, struct IConfigManager2URI *, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000108c`
- `0x180008a10`
- `0x18000f924`
- `0x180037010`

## pseudocode

```c
__int64 __fastcall CEventLogChannelsNode::DeleteChild(
        CEventLogChannelsNode *this,
        struct IConfigManager2URI *a2,
        __int64 a3)
{
  int *v3; // rbx
  struct IConfigManager2URI *v4; // r9
  int v5; // edi
  __int64 v6; // rax
  unsigned __int16 *v8; // [rsp+48h] [rbp+10h] BYREF
  int v9; // [rsp+50h] [rbp+18h] BYREF

  v3 = (int *)((char *)this + 44);
  v4 = a2;
  if ( a2 )
  {
    if ( *v3 == 13 )
    {
      v6 = *(_QWORD *)a2;
      v8 = 0;
      v5 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, _QWORD, unsigned __int16 **))(v6 + 88))(a2, 0, &v8);
      if ( v5 >= 0 )
        v5 = CEventLogChannel::UnregisterChannel(v8);
    }
    else
    {
      v5 = -2046820335;
    }
  }
  else
  {
    v5 = -2147024809;
  }
  if ( (unsigned int)dword_180048E90 > 5 )
  {
    v9 = *v3;
    LODWORD(v8) = v5;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)this,
      (__int64)&word_18003EA16,
      a3,
      (__int64)v4,
      (__int64)&v9,
      (__int64)&v8);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180008a10  mov     [rsp+arg_0], rbx
0x180008a15  push    rdi
0x180008a16  sub     rsp, 30h
0x180008a1a  lea     rbx, [rcx+2Ch]
0x180008a1e  mov     r9, rdx
0x180008a21  test    rdx, rdx
0x180008a24  jnz     short loc_180008A2D
0x180008a26  mov     edi, 80070057h
0x180008a2b  jmp     short loc_180008A6A
0x180008a2d  cmp     dword ptr [rbx], 0Dh
0x180008a30  jz      short loc_180008A39
0x180008a32  mov     edi, 86000011h
0x180008a37  jmp     short loc_180008A6A
0x180008a39  mov     rax, [rdx]
0x180008a3c  lea     r8, [rsp+38h+arg_8]
0x180008a41  xor     edx, edx
0x180008a43  mov     [rsp+38h+arg_8], 0
0x180008a4c  mov     rcx, r9
0x180008a4f  mov     rax, [rax+58h]
0x180008a53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a58  mov     edi, eax
0x180008a5a  test    eax, eax
0x180008a5c  js      short loc_180008A6A
0x180008a5e  mov     rcx, [rsp+38h+arg_8]; unsigned __int16 *
0x180008a63  call    ?UnregisterChannel@CEventLogChannel@@SAJPEBG@Z; CEventLogChannel::UnregisterChannel(ushort const *)
0x180008a68  mov     edi, eax
0x180008a6a  mov     eax, cs:dword_180048E90
0x180008a70  cmp     eax, 5
0x180008a73  jbe     short loc_180008A9F
0x180008a75  mov     eax, [rbx]
0x180008a77  lea     rdx, word_18003EA16
0x180008a7e  mov     [rsp+38h+arg_10], eax
0x180008a82  lea     rax, [rsp+38h+arg_8]
0x180008a87  mov     [rsp+38h+var_10], rax
0x180008a8c  lea     rax, [rsp+38h+arg_10]
0x180008a91  mov     [rsp+38h+var_18], rax
0x180008a96  mov     dword ptr [rsp+38h+arg_8], edi
0x180008a9a  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180008a9f  mov     rbx, [rsp+38h+arg_0]
0x180008aa4  mov     eax, edi
0x180008aa6  add     rsp, 30h
0x180008aaa  pop     rdi
0x180008aab  retn
```
