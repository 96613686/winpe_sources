# CPolicyChannelNode::DeleteChild(IConfigManager2URI *)

- ea: `0x18000c7b0`
- end: `0x18000c970`
- name: `?DeleteChild@CPolicyChannelNode@@UEAAJPEAUIConfigManager2URI@@@Z`
- size: `448`
- prototype: `__int64 __fastcall(CPolicyChannelNode *__hidden this, struct IConfigManager2URI *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001090`
- `0x18000c7b0`
- `0x18000d194`
- `0x180012fe0`
- `0x1800131ac`
- `0x180039010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000c85e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000c892`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000c8b6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000c8da`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000c85e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000c892`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000c8b6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000c8da`

## string_xrefs

- `0x18000c8c6`: `ChannelAccess`

## pseudocode

```c
__int64 __fastcall CPolicyChannelNode::DeleteChild(CPolicyChannelNode *this, struct IConfigManager2URI *a2)
{
  __int64 v4; // rcx
  int v5; // r8d
  int v6; // r9d
  int v7; // ebx
  int v8; // r8d
  int v9; // r9d
  const WCHAR *v10; // rdx
  __int64 v11; // rax
  unsigned __int16 *v13; // [rsp+60h] [rbp+30h] BYREF
  __int64 v14; // [rsp+68h] [rbp+38h] BYREF

  if ( CPolicyChannelNode::PoliciesKeyExist() )
  {
    if ( !a2 )
    {
LABEL_3:
      v7 = -2147024809;
      goto LABEL_22;
    }
    LODWORD(v4) = *((_DWORD *)this + 11) - 33;
    if ( *((_DWORD *)this + 11) == 33 )
    {
      v11 = *(_QWORD *)a2;
      v13 = 0;
      v7 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, _QWORD, unsigned __int16 **))(v11 + 88))(a2, 0, &v13);
      if ( v7 >= 0 )
        v7 = CPolicyChannel::DeletePolicyChannel(v13);
    }
    else
    {
      if ( *((_DWORD *)this + 11) != 34 )
      {
        v7 = -2046820335;
        goto LABEL_22;
      }
      v4 = *((_QWORD *)this + 3);
      v14 = 0;
      if ( !v4 )
        goto LABEL_3;
      v13 = 0;
      v7 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned __int16 **))(*(_QWORD *)v4 + 88LL))(v4, 3, &v13);
      if ( v7 >= 0 )
      {
        v7 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, _QWORD, __int64 *))(*(_QWORD *)a2 + 88LL))(
               a2,
               0,
               &v14);
        if ( v7 >= 0 )
        {
          if ( (unsigned int)_o__wcsicmp(v14, L"ActionWhenFull") )
          {
            if ( (unsigned int)_o__wcsicmp(v14, L"MaximumFileSize") )
            {
              if ( (unsigned int)_o__wcsicmp(v14, L"SDDL") )
              {
                if ( (unsigned int)_o__wcsicmp(v14, L"Enabled") )
                  goto LABEL_22;
                v10 = L"Enabled";
              }
              else
              {
                v10 = L"ChannelAccess";
              }
            }
            else
            {
              v10 = L"MaxSize";
            }
          }
          else
          {
            CPolicyChannel::DeletePolicyChannelLeaf(v13, L"Retention", v8, v9);
            v10 = L"AutoBackupLogFiles";
          }
          CPolicyChannel::DeletePolicyChannelLeaf(v13, v10, v5, v6);
        }
      }
    }
  }
  else
  {
    v7 = 0;
  }
LABEL_22:
  if ( (unsigned int)dword_18004AE90 > 5 )
  {
    LODWORD(v14) = *((_DWORD *)this + 11);
    LODWORD(v13) = v7;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v4,
      (unsigned int)&byte_1800410D7,
      v5,
      v6,
      (__int64)&v14,
      (__int64)&v13);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000c7b0  mov     [rsp-18h+arg_0], rbx
0x18000c7b5  push    rbp
0x18000c7b6  push    rsi
0x18000c7b7  push    rdi
0x18000c7b8  mov     rbp, rsp
0x18000c7bb  sub     rsp, 30h
0x18000c7bf  mov     rsi, rdx
0x18000c7c2  mov     rdi, rcx
0x18000c7c5  call    ?PoliciesKeyExist@CPolicyChannelNode@@CA_NXZ; CPolicyChannelNode::PoliciesKeyExist(void)
0x18000c7ca  test    al, al
0x18000c7cc  jz      loc_18000C92C
0x18000c7d2  test    rsi, rsi
0x18000c7d5  jnz     short loc_18000C7E1
0x18000c7d7  mov     ebx, 80070057h
0x18000c7dc  jmp     loc_18000C92E
0x18000c7e1  mov     ecx, [rdi+2Ch]
0x18000c7e4  sub     ecx, 21h ; '!'
0x18000c7e7  jz      loc_18000C8FC
0x18000c7ed  cmp     ecx, 1
0x18000c7f0  jz      short loc_18000C7FC
0x18000c7f2  mov     ebx, 86000011h
0x18000c7f7  jmp     loc_18000C92E
0x18000c7fc  mov     rcx, [rdi+18h]
0x18000c800  mov     [rbp+arg_18], 0
0x18000c808  test    rcx, rcx
0x18000c80b  jz      short loc_18000C7D7
0x18000c80d  mov     [rbp+arg_10], 0
0x18000c815  lea     r8, [rbp+arg_10]
0x18000c819  mov     rax, [rcx]
0x18000c81c  mov     edx, 3
0x18000c821  mov     rax, [rax+58h]
0x18000c825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c82a  mov     ebx, eax
0x18000c82c  test    eax, eax
0x18000c82e  js      loc_18000C92E
0x18000c834  mov     rax, [rsi]
0x18000c837  lea     r8, [rbp+arg_18]
0x18000c83b  xor     edx, edx
0x18000c83d  mov     rcx, rsi
0x18000c840  mov     rax, [rax+58h]
0x18000c844  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c849  mov     ebx, eax
0x18000c84b  test    eax, eax
0x18000c84d  js      loc_18000C92E
0x18000c853  mov     rcx, [rbp+arg_18]
0x18000c857  lea     rdx, aActionwhenfull; "ActionWhenFull"
0x18000c85e  call    cs:__imp__o__wcsicmp
0x18000c865  nop     dword ptr [rax+rax+00h]
0x18000c86a  test    eax, eax
0x18000c86c  jnz     short loc_18000C887
0x18000c86e  mov     rcx, [rbp+arg_10]; unsigned __int16 *
0x18000c872  lea     rdx, aRetention; "Retention"
0x18000c879  call    ?DeletePolicyChannelLeaf@CPolicyChannel@@SAJPEBG0@Z; CPolicyChannel::DeletePolicyChannelLeaf(ushort const *,ushort const *)
0x18000c87e  lea     rdx, aAutobackuplogf; "AutoBackupLogFiles"
0x18000c885  jmp     short loc_18000C8F1
0x18000c887  mov     rcx, [rbp+arg_18]
0x18000c88b  lea     rdx, aMaximumfilesiz; "MaximumFileSize"
0x18000c892  call    cs:__imp__o__wcsicmp
0x18000c899  nop     dword ptr [rax+rax+00h]
0x18000c89e  test    eax, eax
0x18000c8a0  jnz     short loc_18000C8AB
0x18000c8a2  lea     rdx, aMaxsize; "MaxSize"
0x18000c8a9  jmp     short loc_18000C8F1
0x18000c8ab  mov     rcx, [rbp+arg_18]
0x18000c8af  lea     rdx, aSddl; "SDDL"
0x18000c8b6  call    cs:__imp__o__wcsicmp
0x18000c8bd  nop     dword ptr [rax+rax+00h]
0x18000c8c2  test    eax, eax
0x18000c8c4  jnz     short loc_18000C8CF
0x18000c8c6  lea     rdx, aChannelaccess; "ChannelAccess"
0x18000c8cd  jmp     short loc_18000C8F1
0x18000c8cf  mov     rcx, [rbp+arg_18]
0x18000c8d3  lea     rdx, aEnabled; "Enabled"
0x18000c8da  call    cs:__imp__o__wcsicmp
0x18000c8e1  nop     dword ptr [rax+rax+00h]
0x18000c8e6  test    eax, eax
0x18000c8e8  jnz     short loc_18000C92E
0x18000c8ea  lea     rdx, aEnabled; "Enabled"
0x18000c8f1  mov     rcx, [rbp+arg_10]; unsigned __int16 *
0x18000c8f5  call    ?DeletePolicyChannelLeaf@CPolicyChannel@@SAJPEBG0@Z; CPolicyChannel::DeletePolicyChannelLeaf(ushort const *,ushort const *)
0x18000c8fa  jmp     short loc_18000C92E
0x18000c8fc  mov     rax, [rsi]
0x18000c8ff  lea     r8, [rbp+arg_10]
0x18000c903  xor     edx, edx
0x18000c905  mov     [rbp+arg_10], 0
0x18000c90d  mov     rcx, rsi
0x18000c910  mov     rax, [rax+58h]
0x18000c914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c919  mov     ebx, eax
0x18000c91b  test    eax, eax
0x18000c91d  js      short loc_18000C92E
0x18000c91f  mov     rcx, [rbp+arg_10]; unsigned __int16 *
0x18000c923  call    ?DeletePolicyChannel@CPolicyChannel@@SAJPEBG@Z; CPolicyChannel::DeletePolicyChannel(ushort const *)
0x18000c928  mov     ebx, eax
0x18000c92a  jmp     short loc_18000C92E
0x18000c92c  xor     ebx, ebx
0x18000c92e  mov     eax, cs:dword_18004AE90
0x18000c934  cmp     eax, 5
0x18000c937  jbe     short loc_18000C960
0x18000c939  mov     eax, [rdi+2Ch]
0x18000c93c  lea     rdx, byte_1800410D7
0x18000c943  mov     dword ptr [rbp+arg_18], eax
0x18000c946  lea     rax, [rbp+arg_10]
0x18000c94a  mov     [rsp+30h+var_8], rax
0x18000c94f  lea     rax, [rbp+arg_18]
0x18000c953  mov     [rsp+30h+var_10], rax
0x18000c958  mov     dword ptr [rbp+arg_10], ebx
0x18000c95b  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000c960  mov     eax, ebx
0x18000c962  mov     rbx, [rsp+30h+arg_0]
0x18000c967  add     rsp, 30h
0x18000c96b  pop     rdi
0x18000c96c  pop     rsi
0x18000c96d  pop     rbp
0x18000c96e  retn
```
