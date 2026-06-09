# CEventLogChannelsNode::DeleteChild(IConfigManager2URI *)

- ea: `0x180008c10`
- end: `0x180008cad`
- name: `?DeleteChild@CEventLogChannelsNode@@UEAAJPEAUIConfigManager2URI@@@Z`
- size: `157`
- prototype: `__int64 __fastcall(CEventLogChannelsNode *__hidden this, struct IConfigManager2URI *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001090`
- `0x180008c10`
- `0x180010118`
- `0x180039010`

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
  if ( (unsigned int)dword_18004AE90 > 5 )
  {
    v9 = *v3;
    LODWORD(v8) = v5;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)this,
      (unsigned __int8 *)&word_180040A16,
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
0x180008c10  mov     [rsp+arg_0], rbx
0x180008c15  push    rdi
0x180008c16  sub     rsp, 30h
0x180008c1a  lea     rbx, [rcx+2Ch]
0x180008c1e  mov     r9, rdx
0x180008c21  test    rdx, rdx
0x180008c24  jnz     short loc_180008C2D
0x180008c26  mov     edi, 80070057h
0x180008c2b  jmp     short loc_180008C6A
0x180008c2d  cmp     dword ptr [rbx], 0Dh
0x180008c30  jz      short loc_180008C39
0x180008c32  mov     edi, 86000011h
0x180008c37  jmp     short loc_180008C6A
0x180008c39  mov     rax, [rdx]
0x180008c3c  lea     r8, [rsp+38h+arg_8]
0x180008c41  xor     edx, edx
0x180008c43  mov     [rsp+38h+arg_8], 0
0x180008c4c  mov     rcx, r9
0x180008c4f  mov     rax, [rax+58h]
0x180008c53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c58  mov     edi, eax
0x180008c5a  test    eax, eax
0x180008c5c  js      short loc_180008C6A
0x180008c5e  mov     rcx, [rsp+38h+arg_8]; unsigned __int16 *
0x180008c63  call    ?UnregisterChannel@CEventLogChannel@@SAJPEBG@Z; CEventLogChannel::UnregisterChannel(ushort const *)
0x180008c68  mov     edi, eax
0x180008c6a  mov     eax, cs:dword_18004AE90
0x180008c70  cmp     eax, 5
0x180008c73  jbe     short loc_180008C9F
0x180008c75  mov     eax, [rbx]
0x180008c77  lea     rdx, word_180040A16
0x180008c7e  mov     [rsp+38h+arg_10], eax
0x180008c82  lea     rax, [rsp+38h+arg_8]
0x180008c87  mov     [rsp+38h+var_10], rax
0x180008c8c  lea     rax, [rsp+38h+arg_10]
0x180008c91  mov     [rsp+38h+var_18], rax
0x180008c96  mov     dword ptr [rsp+38h+arg_8], edi
0x180008c9a  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180008c9f  mov     rbx, [rsp+38h+arg_0]
0x180008ca4  mov     eax, edi
0x180008ca6  add     rsp, 30h
0x180008caa  pop     rdi
0x180008cab  retn
```
