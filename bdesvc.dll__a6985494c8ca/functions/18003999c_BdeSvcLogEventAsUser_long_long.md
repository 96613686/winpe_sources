# BdeSvcLogEventAsUser(long,long)

- ea: `0x18003999c`
- end: `0x180039cad`
- name: `?BdeSvcLogEventAsUser@@YAXJJ@Z`
- size: `785`
- prototype: `void __fastcall(int, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1800488b4`
- `0x18004c830`

## callees

- `0x180009f60`
- `0x180034070`
- `0x18003999c`
- `0x18006a26c`
- `0x18006a594`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x1800399fc`
- `RPCRT4!RpcImpersonateClient` at `0x1800399fc`
- `RPCRT4!RpcRevertToSelf` at `0x180039c4c`
- `RPCRT4!RpcRevertToSelf` at `0x180039c4c`

## pseudocode

```c
void __fastcall BdeSvcLogEventAsUser(int a1, unsigned int a2)
{
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r9
  unsigned int v7; // eax
  unsigned int v8; // eax
  __int64 v9; // [rsp+20h] [rbp-39h] BYREF
  __int64 v10; // [rsp+28h] [rbp-31h]
  __int64 v11; // [rsp+30h] [rbp-29h]
  __int64 v12; // [rsp+38h] [rbp-21h] BYREF
  __int64 *v13; // [rsp+40h] [rbp-19h]
  _QWORD **v14; // [rsp+48h] [rbp-11h] BYREF
  _QWORD **v15; // [rsp+50h] [rbp-9h]
  int v16; // [rsp+58h] [rbp-1h] BYREF
  _QWORD *v17; // [rsp+60h] [rbp+7h] BYREF
  _QWORD *v18; // [rsp+68h] [rbp+Fh]
  const wchar_t *v19; // [rsp+70h] [rbp+17h]
  const wchar_t *v20; // [rsp+78h] [rbp+1Fh]
  int *v21; // [rsp+80h] [rbp+27h]
  __int64 v22; // [rsp+88h] [rbp+2Fh]

  if ( a2 == 8 || a2 == 2 )
  {
    v7 = RpcImpersonateClient(0);
    v6 = v7;
    if ( v7 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v5 = 16;
        goto LABEL_26;
      }
    }
    else
    {
      if ( a1 == -2144272221 || a1 == -2144272192 )
      {
        v12 = 0;
        v9 = 0;
        v10 = 0;
        v11 = 0;
        v15 = &v14;
        v14 = &v14;
        v13 = FVEAPI_OP_MAX_CHANGE_ATTEMPTS_REACHED;
        FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&v9, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v12);
        FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v9);
      }
      else if ( a1 )
      {
        if ( a2 == 8 )
        {
          v12 = 0;
          v9 = 0;
          v10 = 0;
          v11 = 0;
          v16 = a1;
          v19 = L"hr";
          v20 = L"HRESULT";
          v21 = &v16;
          v22 = 4;
          v17 = &v14;
          v18 = &v14;
          v14 = &v17;
          v15 = &v17;
          v13 = FVEAPI_OP_CHANGE_PASSPHRASE_FAILURE;
          FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&v9, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v12);
          FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v9);
        }
        else if ( a2 == 2 )
        {
          v12 = 0;
          v9 = 0;
          v10 = 0;
          v11 = 0;
          v16 = a1;
          v19 = L"hr";
          v20 = L"HRESULT";
          v21 = &v16;
          v22 = 4;
          v17 = &v14;
          v18 = &v14;
          v14 = &v17;
          v15 = &v17;
          v13 = FVEAPI_OP_CHANGE_PIN_FAILURE;
          FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&v9, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v12);
          FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v9);
        }
      }
      else if ( a2 == 8 )
      {
        v12 = 0;
        v9 = 0;
        v10 = 0;
        v11 = 0;
        v15 = &v14;
        v14 = &v14;
        v13 = FVEAPI_OP_CHANGE_PASSPHRASE_SUCCESS;
        FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&v9, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v12);
        FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v9);
      }
      else if ( a2 == 2 )
      {
        v12 = 0;
        v9 = 0;
        v10 = 0;
        v11 = 0;
        v15 = &v14;
        v14 = &v14;
        v13 = FVEAPI_OP_CHANGE_PIN_SUCCESS;
        FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&v9, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v12);
        FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v9);
      }
      v8 = RpcRevertToSelf();
      v6 = v8;
      if ( v8 )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v5 = 17;
          goto LABEL_26;
        }
      }
    }
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v5 = 15;
      v6 = a2;
LABEL_26:
      WPP_SF_d(v4[2], v5, WPP_b49306262e623cc86cddd9e33f8f13e1_Traceguids, v6);
    }
  }
}

```

## disassembly

```asm
0x18003999c  mov     [rsp-8+arg_10], rbx
0x1800399a1  push    rbp
0x1800399a2  push    rsi
0x1800399a3  push    rdi
0x1800399a4  lea     rbp, [rsp-47h]
0x1800399a9  sub     rsp, 0A0h
0x1800399b0  mov     rax, cs:__security_cookie
0x1800399b7  xor     rax, rsp
0x1800399ba  mov     [rbp+57h+var_20], rax
0x1800399be  mov     ebx, edx
0x1800399c0  mov     edi, ecx
0x1800399c2  cmp     edx, 8
0x1800399c5  jz      short loc_1800399FA
0x1800399c7  cmp     edx, 2
0x1800399ca  jz      short loc_1800399FA
0x1800399cc  lea     rax, WPP_GLOBAL_Control
0x1800399d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800399da  cmp     rcx, rax
0x1800399dd  jz      loc_180039C8D
0x1800399e3  test    byte ptr [rcx+1Ch], 2
0x1800399e7  jz      loc_180039C8D
0x1800399ed  mov     edx, 0Fh
0x1800399f2  mov     r9d, ebx
0x1800399f5  jmp     loc_180039C7D
0x1800399fa  xor     ecx, ecx; BindingHandle
0x1800399fc  call    cs:__imp_RpcImpersonateClient
0x180039a03  nop     dword ptr [rax+rax+00h]
0x180039a08  mov     r9d, eax
0x180039a0b  xor     esi, esi
0x180039a0d  test    eax, eax
0x180039a0f  jz      short loc_180039A3A
0x180039a11  lea     rax, WPP_GLOBAL_Control
0x180039a18  mov     rcx, cs:WPP_GLOBAL_Control
0x180039a1f  cmp     rcx, rax
0x180039a22  jz      loc_180039C8D
0x180039a28  test    byte ptr [rcx+1Ch], 2
0x180039a2c  jz      loc_180039C8D
0x180039a32  lea     edx, [rsi+10h]
0x180039a35  jmp     loc_180039C7D
0x180039a3a  cmp     edi, 803100A3h
0x180039a40  jz      loc_180039C09
0x180039a46  cmp     edi, 803100C0h
0x180039a4c  jz      loc_180039C09
0x180039a52  test    edi, edi
0x180039a54  jz      loc_180039B6E
0x180039a5a  cmp     ebx, 8
0x180039a5d  jnz     loc_180039AE4
0x180039a63  mov     [rbp+57h+var_78], rsi
0x180039a67  mov     [rbp+57h+var_90], rsi
0x180039a6b  mov     [rbp+57h+var_88], rsi
0x180039a6f  mov     [rbp+57h+var_80], rsi
0x180039a73  mov     [rbp+57h+var_58], edi
0x180039a76  lea     rax, aHr; "hr"
0x180039a7d  lea     rcx, aHresult; "HRESULT"
0x180039a84  lea     r8, [rbp+57h+var_58]
0x180039a88  mov     [rbp+57h+var_40], rax
0x180039a8c  mov     [rbp+57h+var_38], rcx
0x180039a90  mov     [rbp+57h+var_30], r8
0x180039a94  mov     [rbp+57h+var_28], 4
0x180039a9c  lea     rax, [rbp+57h+var_68]
0x180039aa0  mov     [rbp+57h+var_50], rax
0x180039aa4  lea     rax, [rbp+57h+var_68]
0x180039aa8  mov     [rbp+57h+var_48], rax
0x180039aac  lea     rax, [rbp+57h+var_50]
0x180039ab0  mov     [rbp+57h+var_68], rax
0x180039ab4  lea     rax, [rbp+57h+var_50]
0x180039ab8  mov     [rbp+57h+var_60], rax
0x180039abc  lea     rax, FVEAPI_OP_CHANGE_PASSPHRASE_FAILURE
0x180039ac3  mov     [rbp+57h+var_70], rax
0x180039ac7  lea     rdx, [rbp+57h+var_78]; struct _FVEAPI_EVENT_DATA_COLLECTION *
0x180039acb  lea     rcx, [rbp+57h+var_90]; this
0x180039acf  call    ?LogFveApiEvent@FveEventLogHandle@@QEAAJPEAU_FVEAPI_EVENT_DATA_COLLECTION@@@Z; FveEventLogHandle::LogFveApiEvent(_FVEAPI_EVENT_DATA_COLLECTION *)
0x180039ad4  nop
0x180039ad5  lea     rcx, [rbp+57h+var_90]; this
0x180039ad9  call    ?EventLogCleanup@FveEventLogHandle@@AEAAXXZ; FveEventLogHandle::EventLogCleanup(void)
0x180039ade  nop
0x180039adf  jmp     loc_180039C4C
0x180039ae4  cmp     ebx, 2
0x180039ae7  jnz     loc_180039C4C
0x180039aed  mov     [rbp+57h+var_78], rsi
0x180039af1  mov     [rbp+57h+var_90], rsi
0x180039af5  mov     [rbp+57h+var_88], rsi
0x180039af9  mov     [rbp+57h+var_80], rsi
0x180039afd  mov     [rbp+57h+var_58], edi
0x180039b00  lea     rax, aHr; "hr"
0x180039b07  lea     rcx, aHresult; "HRESULT"
0x180039b0e  lea     r8, [rbp+57h+var_58]
0x180039b12  mov     [rbp+57h+var_40], rax
0x180039b16  mov     [rbp+57h+var_38], rcx
0x180039b1a  mov     [rbp+57h+var_30], r8
0x180039b1e  mov     [rbp+57h+var_28], 4
0x180039b26  lea     rax, [rbp+57h+var_68]
0x180039b2a  mov     [rbp+57h+var_50], rax
0x180039b2e  lea     rax, [rbp+57h+var_68]
0x180039b32  mov     [rbp+57h+var_48], rax
0x180039b36  lea     rax, [rbp+57h+var_50]
0x180039b3a  mov     [rbp+57h+var_68], rax
0x180039b3e  lea     rax, [rbp+57h+var_50]
0x180039b42  mov     [rbp+57h+var_60], rax
0x180039b46  lea     rax, FVEAPI_OP_CHANGE_PIN_FAILURE
0x180039b4d  mov     [rbp+57h+var_70], rax
0x180039b51  lea     rdx, [rbp+57h+var_78]; struct _FVEAPI_EVENT_DATA_COLLECTION *
0x180039b55  lea     rcx, [rbp+57h+var_90]; this
0x180039b59  call    ?LogFveApiEvent@FveEventLogHandle@@QEAAJPEAU_FVEAPI_EVENT_DATA_COLLECTION@@@Z; FveEventLogHandle::LogFveApiEvent(_FVEAPI_EVENT_DATA_COLLECTION *)
0x180039b5e  nop
0x180039b5f  lea     rcx, [rbp+57h+var_90]; this
0x180039b63  call    ?EventLogCleanup@FveEventLogHandle@@AEAAXXZ; FveEventLogHandle::EventLogCleanup(void)
0x180039b68  nop
0x180039b69  jmp     loc_180039C4C
0x180039b6e  cmp     ebx, 8
0x180039b71  jnz     short loc_180039BBB
0x180039b73  mov     [rbp+57h+var_78], rsi
0x180039b77  mov     [rbp+57h+var_90], rsi
0x180039b7b  mov     [rbp+57h+var_88], rsi
0x180039b7f  mov     [rbp+57h+var_80], rsi
0x180039b83  lea     rax, [rbp+57h+var_68]
0x180039b87  mov     [rbp+57h+var_60], rax
0x180039b8b  lea     rax, [rbp+57h+var_68]
0x180039b8f  mov     [rbp+57h+var_68], rax
0x180039b93  lea     rax, FVEAPI_OP_CHANGE_PASSPHRASE_SUCCESS
0x180039b9a  mov     [rbp+57h+var_70], rax
0x180039b9e  lea     rdx, [rbp+57h+var_78]; struct _FVEAPI_EVENT_DATA_COLLECTION *
0x180039ba2  lea     rcx, [rbp+57h+var_90]; this
0x180039ba6  call    ?LogFveApiEvent@FveEventLogHandle@@QEAAJPEAU_FVEAPI_EVENT_DATA_COLLECTION@@@Z; FveEventLogHandle::LogFveApiEvent(_FVEAPI_EVENT_DATA_COLLECTION *)
0x180039bab  nop
0x180039bac  lea     rcx, [rbp+57h+var_90]; this
0x180039bb0  call    ?EventLogCleanup@FveEventLogHandle@@AEAAXXZ; FveEventLogHandle::EventLogCleanup(void)
0x180039bb5  nop
0x180039bb6  jmp     loc_180039C4C
0x180039bbb  cmp     ebx, 2
0x180039bbe  jnz     loc_180039C4C
0x180039bc4  mov     [rbp+57h+var_78], rsi
0x180039bc8  mov     [rbp+57h+var_90], rsi
0x180039bcc  mov     [rbp+57h+var_88], rsi
0x180039bd0  mov     [rbp+57h+var_80], rsi
0x180039bd4  lea     rax, [rbp+57h+var_68]
0x180039bd8  mov     [rbp+57h+var_60], rax
0x180039bdc  lea     rax, [rbp+57h+var_68]
0x180039be0  mov     [rbp+57h+var_68], rax
0x180039be4  lea     rax, FVEAPI_OP_CHANGE_PIN_SUCCESS
0x180039beb  mov     [rbp+57h+var_70], rax
0x180039bef  lea     rdx, [rbp+57h+var_78]; struct _FVEAPI_EVENT_DATA_COLLECTION *
0x180039bf3  lea     rcx, [rbp+57h+var_90]; this
0x180039bf7  call    ?LogFveApiEvent@FveEventLogHandle@@QEAAJPEAU_FVEAPI_EVENT_DATA_COLLECTION@@@Z; FveEventLogHandle::LogFveApiEvent(_FVEAPI_EVENT_DATA_COLLECTION *)
0x180039bfc  nop
0x180039bfd  lea     rcx, [rbp+57h+var_90]; this
0x180039c01  call    ?EventLogCleanup@FveEventLogHandle@@AEAAXXZ; FveEventLogHandle::EventLogCleanup(void)
0x180039c06  nop
0x180039c07  jmp     short loc_180039C4C
0x180039c09  mov     [rbp+57h+var_78], rsi
0x180039c0d  mov     [rbp+57h+var_90], rsi
0x180039c11  mov     [rbp+57h+var_88], rsi
0x180039c15  mov     [rbp+57h+var_80], rsi
0x180039c19  lea     rax, [rbp+57h+var_68]
0x180039c1d  mov     [rbp+57h+var_60], rax
0x180039c21  lea     rax, [rbp+57h+var_68]
0x180039c25  mov     [rbp+57h+var_68], rax
0x180039c29  lea     rax, FVEAPI_OP_MAX_CHANGE_ATTEMPTS_REACHED
0x180039c30  mov     [rbp+57h+var_70], rax
0x180039c34  lea     rdx, [rbp+57h+var_78]; struct _FVEAPI_EVENT_DATA_COLLECTION *
0x180039c38  lea     rcx, [rbp+57h+var_90]; this
0x180039c3c  call    ?LogFveApiEvent@FveEventLogHandle@@QEAAJPEAU_FVEAPI_EVENT_DATA_COLLECTION@@@Z; FveEventLogHandle::LogFveApiEvent(_FVEAPI_EVENT_DATA_COLLECTION *)
0x180039c41  nop
0x180039c42  lea     rcx, [rbp+57h+var_90]; this
0x180039c46  call    ?EventLogCleanup@FveEventLogHandle@@AEAAXXZ; FveEventLogHandle::EventLogCleanup(void)
0x180039c4b  nop
0x180039c4c  call    cs:__imp_RpcRevertToSelf
0x180039c53  nop     dword ptr [rax+rax+00h]
0x180039c58  mov     r9d, eax
0x180039c5b  test    eax, eax
0x180039c5d  jz      short loc_180039C8D
0x180039c5f  lea     rax, WPP_GLOBAL_Control
0x180039c66  mov     rcx, cs:WPP_GLOBAL_Control
0x180039c6d  cmp     rcx, rax
0x180039c70  jz      short loc_180039C8D
0x180039c72  test    byte ptr [rcx+1Ch], 2
0x180039c76  jz      short loc_180039C8D
0x180039c78  mov     edx, 11h
0x180039c7d  lea     r8, WPP_b49306262e623cc86cddd9e33f8f13e1_Traceguids
0x180039c84  mov     rcx, [rcx+10h]
0x180039c88  call    WPP_SF_d
0x180039c8d  mov     rcx, [rbp+57h+var_20]
0x180039c91  xor     rcx, rsp; StackCookie
0x180039c94  call    __security_check_cookie
0x180039c99  mov     rbx, [rsp+0B0h+arg_10]
0x180039ca1  add     rsp, 0A0h
0x180039ca8  pop     rdi
0x180039ca9  pop     rsi
0x180039caa  pop     rbp
0x180039cab  retn
```
