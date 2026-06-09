# CPolicyChannelNode::DeleteChild(IConfigManager2URI *)

- ea: `0x18000c260`
- end: `0x18000c407`
- name: `?DeleteChild@CPolicyChannelNode@@UEAAJPEAUIConfigManager2URI@@@Z`
- size: `423`
- prototype: `__int64 __fastcall(CPolicyChannelNode *__hidden this, struct IConfigManager2URI *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000108c`
- `0x18000c260`
- `0x18000cb9c`
- `0x180012618`
- `0x1800127d4`
- `0x180037010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000c30e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000c33c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000c35a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000c378`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000c30e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000c33c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000c35a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000c378`

## string_xrefs

- `0x18000c364`: `ChannelAccess`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPolicyChannelNode::DeleteChild(CPolicyChannelNode *this, struct IConfigManager2URI *a2)
{
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  int v7; // ebx
  const WCHAR *v8; // rdx
  __int64 v9; // rax
  unsigned __int16 *v11; // [rsp+60h] [rbp+30h] BYREF
  __int64 v12; // [rsp+68h] [rbp+38h] BYREF

  if ( CPolicyChannelNode::PoliciesKeyExist() )
  {
    if ( !a2 )
    {
LABEL_3:
      v7 = -2147024809;
      goto LABEL_22;
    }
    v4 = (unsigned int)(*((_DWORD *)this + 11) - 33);
    if ( *((_DWORD *)this + 11) == 33 )
    {
      v9 = *(_QWORD *)a2;
      v11 = 0;
      v7 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, _QWORD, unsigned __int16 **))(v9 + 88))(a2, 0, &v11);
      if ( v7 >= 0 )
        v7 = CPolicyChannel::DeletePolicyChannel(v11);
    }
    else
    {
      if ( *((_DWORD *)this + 11) != 34 )
      {
        v7 = -2046820335;
        goto LABEL_22;
      }
      v4 = *((_QWORD *)this + 3);
      v12 = 0;
      if ( !v4 )
        goto LABEL_3;
      v11 = 0;
      v7 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned __int16 **))(*(_QWORD *)v4 + 88LL))(v4, 3, &v11);
      if ( v7 >= 0 )
      {
        v7 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, _QWORD, __int64 *))(*(_QWORD *)a2 + 88LL))(
               a2,
               0,
               &v12);
        if ( v7 >= 0 )
        {
          if ( (unsigned int)_o__wcsicmp(v12, L"ActionWhenFull") )
          {
            if ( (unsigned int)_o__wcsicmp(v12, L"MaximumFileSize") )
            {
              if ( (unsigned int)_o__wcsicmp(v12, L"SDDL") )
              {
                if ( (unsigned int)_o__wcsicmp(v12, L"Enabled") )
                  goto LABEL_22;
                v8 = L"Enabled";
              }
              else
              {
                v8 = L"ChannelAccess";
              }
            }
            else
            {
              v8 = L"MaxSize";
            }
          }
          else
          {
            CPolicyChannel::DeletePolicyChannelLeaf(v11, L"Retention");
            v8 = L"AutoBackupLogFiles";
          }
          CPolicyChannel::DeletePolicyChannelLeaf(v11, v8);
        }
      }
    }
  }
  else
  {
    v7 = 0;
  }
LABEL_22:
  if ( (unsigned int)dword_180048E90 > 5 )
  {
    LODWORD(v12) = *((_DWORD *)this + 11);
    LODWORD(v11) = v7;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v4,
      (__int64)&byte_18003F0D7,
      v5,
      v6,
      (__int64)&v12,
      (__int64)&v11);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000c260  mov     [rsp-18h+arg_0], rbx
0x18000c265  push    rbp
0x18000c266  push    rsi
0x18000c267  push    rdi
0x18000c268  mov     rbp, rsp
0x18000c26b  sub     rsp, 30h
0x18000c26f  mov     rsi, rdx
0x18000c272  mov     rdi, rcx
0x18000c275  call    ?PoliciesKeyExist@CPolicyChannelNode@@CA_NXZ; CPolicyChannelNode::PoliciesKeyExist(void)
0x18000c27a  test    al, al
0x18000c27c  jz      loc_18000C3C4
0x18000c282  test    rsi, rsi
0x18000c285  jnz     short loc_18000C291
0x18000c287  mov     ebx, 80070057h
0x18000c28c  jmp     loc_18000C3C6
0x18000c291  mov     ecx, [rdi+2Ch]
0x18000c294  sub     ecx, 21h ; '!'
0x18000c297  jz      loc_18000C394
0x18000c29d  cmp     ecx, 1
0x18000c2a0  jz      short loc_18000C2AC
0x18000c2a2  mov     ebx, 86000011h
0x18000c2a7  jmp     loc_18000C3C6
0x18000c2ac  mov     rcx, [rdi+18h]
0x18000c2b0  mov     [rbp+arg_18], 0
0x18000c2b8  test    rcx, rcx
0x18000c2bb  jz      short loc_18000C287
0x18000c2bd  mov     [rbp+arg_10], 0
0x18000c2c5  lea     r8, [rbp+arg_10]
0x18000c2c9  mov     rax, [rcx]
0x18000c2cc  mov     edx, 3
0x18000c2d1  mov     rax, [rax+58h]
0x18000c2d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2da  mov     ebx, eax
0x18000c2dc  test    eax, eax
0x18000c2de  js      loc_18000C3C6
0x18000c2e4  mov     rax, [rsi]
0x18000c2e7  lea     r8, [rbp+arg_18]
0x18000c2eb  xor     edx, edx
0x18000c2ed  mov     rcx, rsi
0x18000c2f0  mov     rax, [rax+58h]
0x18000c2f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2f9  mov     ebx, eax
0x18000c2fb  test    eax, eax
0x18000c2fd  js      loc_18000C3C6
0x18000c303  mov     rcx, [rbp+arg_18]
0x18000c307  lea     rdx, aActionwhenfull; "ActionWhenFull"
0x18000c30e  call    cs:__imp__o__wcsicmp
0x18000c314  test    eax, eax
0x18000c316  jnz     short loc_18000C331
0x18000c318  mov     rcx, [rbp+arg_10]; unsigned __int16 *
0x18000c31c  lea     rdx, aRetention; "Retention"
0x18000c323  call    ?DeletePolicyChannelLeaf@CPolicyChannel@@SAJPEBG0@Z; CPolicyChannel::DeletePolicyChannelLeaf(ushort const *,ushort const *)
0x18000c328  lea     rdx, aAutobackuplogf; "AutoBackupLogFiles"
0x18000c32f  jmp     short loc_18000C389
0x18000c331  mov     rcx, [rbp+arg_18]
0x18000c335  lea     rdx, aMaximumfilesiz; "MaximumFileSize"
0x18000c33c  call    cs:__imp__o__wcsicmp
0x18000c342  test    eax, eax
0x18000c344  jnz     short loc_18000C34F
0x18000c346  lea     rdx, aMaxsize; "MaxSize"
0x18000c34d  jmp     short loc_18000C389
0x18000c34f  mov     rcx, [rbp+arg_18]
0x18000c353  lea     rdx, aSddl; "SDDL"
0x18000c35a  call    cs:__imp__o__wcsicmp
0x18000c360  test    eax, eax
0x18000c362  jnz     short loc_18000C36D
0x18000c364  lea     rdx, aChannelaccess; "ChannelAccess"
0x18000c36b  jmp     short loc_18000C389
0x18000c36d  mov     rcx, [rbp+arg_18]
0x18000c371  lea     rdx, aEnabled; "Enabled"
0x18000c378  call    cs:__imp__o__wcsicmp
0x18000c37e  test    eax, eax
0x18000c380  jnz     short loc_18000C3C6
0x18000c382  lea     rdx, aEnabled; "Enabled"
0x18000c389  mov     rcx, [rbp+arg_10]; unsigned __int16 *
0x18000c38d  call    ?DeletePolicyChannelLeaf@CPolicyChannel@@SAJPEBG0@Z; CPolicyChannel::DeletePolicyChannelLeaf(ushort const *,ushort const *)
0x18000c392  jmp     short loc_18000C3C6
0x18000c394  mov     rax, [rsi]
0x18000c397  lea     r8, [rbp+arg_10]
0x18000c39b  xor     edx, edx
0x18000c39d  mov     [rbp+arg_10], 0
0x18000c3a5  mov     rcx, rsi
0x18000c3a8  mov     rax, [rax+58h]
0x18000c3ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3b1  mov     ebx, eax
0x18000c3b3  test    eax, eax
0x18000c3b5  js      short loc_18000C3C6
0x18000c3b7  mov     rcx, [rbp+arg_10]; unsigned __int16 *
0x18000c3bb  call    ?DeletePolicyChannel@CPolicyChannel@@SAJPEBG@Z; CPolicyChannel::DeletePolicyChannel(ushort const *)
0x18000c3c0  mov     ebx, eax
0x18000c3c2  jmp     short loc_18000C3C6
0x18000c3c4  xor     ebx, ebx
0x18000c3c6  mov     eax, cs:dword_180048E90
0x18000c3cc  cmp     eax, 5
0x18000c3cf  jbe     short loc_18000C3F8
0x18000c3d1  mov     eax, [rdi+2Ch]
0x18000c3d4  lea     rdx, byte_18003F0D7
0x18000c3db  mov     dword ptr [rbp+arg_18], eax
0x18000c3de  lea     rax, [rbp+arg_10]
0x18000c3e2  mov     [rsp+30h+var_8], rax
0x18000c3e7  lea     rax, [rbp+arg_18]
0x18000c3eb  mov     [rsp+30h+var_10], rax
0x18000c3f0  mov     dword ptr [rbp+arg_10], ebx
0x18000c3f3  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000c3f8  mov     eax, ebx
0x18000c3fa  mov     rbx, [rsp+30h+arg_0]
0x18000c3ff  add     rsp, 30h
0x18000c403  pop     rdi
0x18000c404  pop     rsi
0x18000c405  pop     rbp
0x18000c406  retn
```
