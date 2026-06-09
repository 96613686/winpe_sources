# std::_Tree<std::_Tmap_traits<Sid,WpcDesktop::OTS::Manager::LocalRequestState,std::less<Sid>,std::allocator<std::pair<Sid const,WpcDesktop::OTS::Manager::LocalRequestState>>,0>>::erase(Sid const &)

- ea: `0x18000d988`
- end: `0x18000dbca`
- name: `?erase@?$_Tree@V?$_Tmap_traits@VSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@U?$less@VSid@@@std@@V?$allocator@U?$pair@$$CBVSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@@std@@@7@$0A@@std@@@std@@QEAA_KAEBVSid@@@Z`
- size: `578`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18000bc98`

## callees

- `0x1800036e4`
- `0x180004bb0`
- `0x180005f9c`
- `0x18000b7ac`
- `0x18000d280`
- `0x18000d988`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall std::_Tree<std::_Tmap_traits<Sid,WpcDesktop::OTS::Manager::LocalRequestState,std::less<Sid>,std::allocator<std::pair<Sid const,WpcDesktop::OTS::Manager::LocalRequestState>>,0>>::erase(
        __int64 a1,
        __int64 a2)
{
  _QWORD *v2; // rdi
  const wchar_t *v3; // rbp
  __int64 v4; // rbx
  __int64 v5; // r14
  __int64 v6; // rsi
  __int64 *v7; // rsi
  __int64 v8; // rsi
  __int64 v9; // rax
  __int64 v10; // rbp
  __int64 v11; // rdx
  __int64 i; // rcx
  __int64 j; // rdx
  char *v14; // rsi
  char **v15; // rcx
  char *v16; // rbx
  _BYTE *v18; // rcx
  __int64 v19; // rdx
  __int64 *v20; // r8
  __int64 v21; // rax
  __int64 k; // rcx
  __int64 v23; // r8
  __int64 v24; // r8
  __int64 *v25; // r8
  char **v26; // rdi

  v2 = (_QWORD *)WpcDesktop::OTS::Manager::PendingTimeRequests;
  v3 = (const wchar_t *)(a2 + 72);
  v4 = WpcDesktop::OTS::Manager::PendingTimeRequests;
  v5 = WpcDesktop::OTS::Manager::PendingTimeRequests;
  v6 = *(_QWORD *)(WpcDesktop::OTS::Manager::PendingTimeRequests + 8);
  if ( !*(_BYTE *)(v6 + 25) )
  {
    do
    {
      if ( (unsigned __int8)std::operator<<unsigned short>((const wchar_t *)(v6 + 104), v3) )
      {
        v6 = *(_QWORD *)(v6 + 16);
      }
      else
      {
        std::operator<<unsigned short>(v3, (const wchar_t *)(v6 + 104));
        if ( *(_BYTE *)(v5 + 25) )
        {
          if ( (unsigned __int8)std::operator<<unsigned short>(v3, (const wchar_t *)(v6 + 104)) )
            v5 = v6;
          else
            std::operator<<unsigned short>((const wchar_t *)(v6 + 104), v3);
        }
        v4 = v6;
        v6 = *(_QWORD *)v6;
      }
    }
    while ( !*(_BYTE *)(v6 + 25) );
    v2 = (_QWORD *)WpcDesktop::OTS::Manager::PendingTimeRequests;
  }
  v7 = v2 + 1;
  if ( !*(_BYTE *)(v5 + 25) )
    v7 = (__int64 *)v5;
  v8 = *v7;
  if ( !*(_BYTE *)(v8 + 25) )
  {
    do
    {
      if ( (unsigned __int8)std::operator<<unsigned short>(v3, (const wchar_t *)(v8 + 104)) )
      {
        v5 = v8;
        v8 = *(_QWORD *)v8;
      }
      else
      {
        std::operator<<unsigned short>((const wchar_t *)(v8 + 104), v3);
        v8 = *(_QWORD *)(v8 + 16);
      }
    }
    while ( !*(_BYTE *)(v8 + 25) );
    v2 = (_QWORD *)WpcDesktop::OTS::Manager::PendingTimeRequests;
  }
  v9 = v4;
  v10 = 0;
  while ( v9 != v5 )
  {
    v11 = *(_QWORD *)(v9 + 16);
    ++v10;
    if ( *(_BYTE *)(v11 + 25) )
    {
      for ( i = *(_QWORD *)(v9 + 8); !*(_BYTE *)(i + 25) && v9 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
        v9 = i;
      v9 = i;
    }
    else
    {
      v9 = *(_QWORD *)(v9 + 16);
      for ( j = *(_QWORD *)v11; !*(_BYTE *)(j + 25); j = *(_QWORD *)j )
        v9 = j;
    }
  }
  if ( v4 == *v2 && *(_BYTE *)(v5 + 25) )
  {
    v14 = (char *)v2[1];
    while ( !v14[25] )
    {
      std::_Tree_val<std::_Tree_simple_types<std::pair<Sid const,WpcDesktop::OTS::Manager::LocalRequestState>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<Sid const,WpcDesktop::OTS::Manager::LocalRequestState>,void *>>>(
        (__int64)&WpcDesktop::OTS::Manager::PendingTimeRequests,
        (__int64)&WpcDesktop::OTS::Manager::PendingTimeRequests,
        *((_QWORD *)v14 + 2));
      v15 = (char **)v14;
      v16 = v14;
      v14 = *(char **)v14;
      std::wstring::~wstring(v15 + 13);
      operator delete(v16);
    }
    v2[1] = v2;
    *v2 = v2;
    v2[2] = v2;
    qword_18004A608 = 0;
  }
  else
  {
    while ( v4 != v5 )
    {
      v18 = *(_BYTE **)(v4 + 16);
      v19 = v4;
      if ( v18[25] )
      {
        v20 = (__int64 *)(v4 + 8);
        v21 = v4;
        for ( k = *(_QWORD *)(v4 + 8); !*(_BYTE *)(k + 25) && v4 == *(_QWORD *)(k + 16); k = *(_QWORD *)(k + 8) )
          v4 = k;
        v23 = *v20;
        v4 = k;
        while ( !*(_BYTE *)(v23 + 25) && v21 == *(_QWORD *)(v23 + 16) )
        {
          v21 = v23;
          v23 = *(_QWORD *)(v23 + 8);
        }
      }
      else
      {
        v24 = *(_QWORD *)v18;
        if ( *(_BYTE *)(*(_QWORD *)v18 + 25LL) )
        {
          v4 = *(_QWORD *)(v4 + 16);
        }
        else
        {
          do
          {
            v4 = v24;
            v24 = *(_QWORD *)v24;
          }
          while ( !*(_BYTE *)(v24 + 25) );
        }
        v25 = *(__int64 **)v18;
        if ( !*(_BYTE *)(*(_QWORD *)v18 + 25LL) )
        {
          do
            v25 = (__int64 *)*v25;
          while ( !*((_BYTE *)v25 + 25) );
        }
      }
      v26 = (char **)std::_Tree_val<std::_Tree_simple_types<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>>::_Extract(
                       &WpcDesktop::OTS::Manager::PendingTimeRequests,
                       v19);
      std::wstring::~wstring(v26 + 13);
      operator delete(v26);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x18000d988  mov     [rsp+arg_0], rcx
0x18000d98d  push    rbx
0x18000d98e  push    rbp
0x18000d98f  push    rsi
0x18000d990  push    rdi
0x18000d991  push    r14
0x18000d993  push    r15
0x18000d995  sub     rsp, 28h
0x18000d999  mov     rdi, cs:?PendingTimeRequests@Manager@OTS@WpcDesktop@@3V?$map@VSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@U?$less@VSid@@@std@@V?$allocator@U?$pair@$$CBVSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@@std@@@7@@std@@A; std::map<Sid,WpcDesktop::OTS::Manager::LocalRequestState> WpcDesktop::OTS::Manager::PendingTimeRequests
0x18000d9a0  lea     rbp, [rdx+48h]
0x18000d9a4  xor     r15d, r15d
0x18000d9a7  mov     rbx, rdi
0x18000d9aa  mov     r14, rdi
0x18000d9ad  mov     rsi, [rdi+8]
0x18000d9b1  cmp     [rsi+19h], r15b
0x18000d9b5  jnz     short loc_18000DA13
0x18000d9b7  lea     rdi, [rsi+68h]
0x18000d9bb  mov     rdx, rbp
0x18000d9be  mov     rcx, rdi
0x18000d9c1  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x18000d9c6  test    al, al
0x18000d9c8  jnz     short loc_18000DA02
0x18000d9ca  mov     rdx, rdi
0x18000d9cd  mov     rcx, rbp
0x18000d9d0  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x18000d9d5  cmp     [r14+19h], r15b
0x18000d9d9  jz      short loc_18000D9FA
0x18000d9db  mov     rdx, rdi
0x18000d9de  mov     rcx, rbp
0x18000d9e1  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x18000d9e6  test    al, al
0x18000d9e8  jnz     short loc_18000D9F7
0x18000d9ea  mov     rdx, rbp
0x18000d9ed  mov     rcx, rdi
0x18000d9f0  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x18000d9f5  jmp     short loc_18000D9FA
0x18000d9f7  mov     r14, rsi
0x18000d9fa  mov     rbx, rsi
0x18000d9fd  mov     rsi, [rsi]
0x18000da00  jmp     short loc_18000DA06
0x18000da02  mov     rsi, [rsi+10h]
0x18000da06  cmp     [rsi+19h], r15b
0x18000da0a  jz      short loc_18000D9B7
0x18000da0c  mov     rdi, cs:?PendingTimeRequests@Manager@OTS@WpcDesktop@@3V?$map@VSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@U?$less@VSid@@@std@@V?$allocator@U?$pair@$$CBVSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@@std@@@7@@std@@A; std::map<Sid,WpcDesktop::OTS::Manager::LocalRequestState> WpcDesktop::OTS::Manager::PendingTimeRequests
0x18000da13  lea     rsi, [rdi+8]
0x18000da17  cmp     [r14+19h], r15b
0x18000da1b  jnz     short loc_18000DA20
0x18000da1d  mov     rsi, r14
0x18000da20  mov     rsi, [rsi]
0x18000da23  cmp     [rsi+19h], r15b
0x18000da27  jnz     short loc_18000DA5E
0x18000da29  lea     rdx, [rsi+68h]
0x18000da2d  mov     rcx, rbp
0x18000da30  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x18000da35  test    al, al
0x18000da37  jnz     short loc_18000DA4B
0x18000da39  mov     rdx, rbp
0x18000da3c  lea     rcx, [rsi+68h]
0x18000da40  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x18000da45  mov     rsi, [rsi+10h]
0x18000da49  jmp     short loc_18000DA51
0x18000da4b  mov     r14, rsi
0x18000da4e  mov     rsi, [rsi]
0x18000da51  cmp     [rsi+19h], r15b
0x18000da55  jz      short loc_18000DA29
0x18000da57  mov     rdi, cs:?PendingTimeRequests@Manager@OTS@WpcDesktop@@3V?$map@VSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@U?$less@VSid@@@std@@V?$allocator@U?$pair@$$CBVSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@@std@@@7@@std@@A; std::map<Sid,WpcDesktop::OTS::Manager::LocalRequestState> WpcDesktop::OTS::Manager::PendingTimeRequests
0x18000da5e  mov     rax, rbx
0x18000da61  mov     rbp, r15
0x18000da64  cmp     rax, r14
0x18000da67  jz      short loc_18000DAB1
0x18000da69  mov     rdx, [rax+10h]
0x18000da6d  inc     rbp
0x18000da70  cmp     [rdx+19h], r15b
0x18000da74  jz      short loc_18000DA94
0x18000da76  mov     rcx, [rax+8]
0x18000da7a  jmp     short loc_18000DA89
0x18000da7c  cmp     rax, [rcx+10h]
0x18000da80  jnz     short loc_18000DA8F
0x18000da82  mov     rax, rcx
0x18000da85  mov     rcx, [rcx+8]
0x18000da89  cmp     [rcx+19h], r15b
0x18000da8d  jz      short loc_18000DA7C
0x18000da8f  mov     rax, rcx
0x18000da92  jmp     short loc_18000DA64
0x18000da94  mov     rax, rdx
0x18000da97  mov     rdx, [rdx]
0x18000da9a  cmp     [rdx+19h], r15b
0x18000da9e  jnz     short loc_18000DA64
0x18000daa0  mov     rcx, [rdx]
0x18000daa3  mov     rax, rdx
0x18000daa6  mov     rdx, rcx
0x18000daa9  cmp     [rcx+19h], r15b
0x18000daad  jz      short loc_18000DAA0
0x18000daaf  jmp     short loc_18000DA64
0x18000dab1  cmp     rbx, [rdi]
0x18000dab4  jnz     short loc_18000DB20
0x18000dab6  cmp     [r14+19h], r15b
0x18000daba  jz      short loc_18000DB20
0x18000dabc  mov     rsi, [rdi+8]
0x18000dac0  jmp     short loc_18000DAF8
0x18000dac2  mov     r8, [rsi+10h]
0x18000dac6  lea     rdx, ?PendingTimeRequests@Manager@OTS@WpcDesktop@@3V?$map@VSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@U?$less@VSid@@@std@@V?$allocator@U?$pair@$$CBVSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@@std@@@7@@std@@A; std::map<Sid,WpcDesktop::OTS::Manager::LocalRequestState> WpcDesktop::OTS::Manager::PendingTimeRequests
0x18000dacd  lea     rcx, ?PendingTimeRequests@Manager@OTS@WpcDesktop@@3V?$map@VSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@U?$less@VSid@@@std@@V?$allocator@U?$pair@$$CBVSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@@std@@@7@@std@@A; std::map<Sid,WpcDesktop::OTS::Manager::LocalRequestState> WpcDesktop::OTS::Manager::PendingTimeRequests
0x18000dad4  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBVSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBVSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBVSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<Sid const,WpcDesktop::OTS::Manager::LocalRequestState>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<Sid const,WpcDesktop::OTS::Manager::LocalRequestState>,void *>>>(std::allocator<std::_Tree_node<std::pair<Sid const,WpcDesktop::OTS::Manager::LocalRequestState>,void *>> &,std::_Tree_node<std::pair<Sid const,WpcDesktop::OTS::Manager::LocalRequestState>,void *> *)
0x18000dad9  mov     rcx, rsi
0x18000dadc  mov     rbx, rsi
0x18000dadf  mov     rsi, [rsi]
0x18000dae2  add     rcx, 68h ; 'h'
0x18000dae6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000daeb  mov     edx, 98h
0x18000daf0  mov     rcx, rbx; Block
0x18000daf3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000daf8  cmp     [rsi+19h], r15b
0x18000dafc  jz      short loc_18000DAC2
0x18000dafe  mov     [rdi+8], rdi
0x18000db02  mov     [rdi], rdi
0x18000db05  mov     [rdi+10h], rdi
0x18000db09  mov     cs:qword_18004A608, r15
0x18000db10  mov     rax, rbp
0x18000db13  add     rsp, 28h
0x18000db17  pop     r15
0x18000db19  pop     r14
0x18000db1b  pop     rdi
0x18000db1c  pop     rsi
0x18000db1d  pop     rbp
0x18000db1e  pop     rbx
0x18000db1f  retn
0x18000db20  cmp     rbx, r14
0x18000db23  jz      short loc_18000DB10
0x18000db25  mov     rcx, [rbx+10h]
0x18000db29  mov     rdx, rbx
0x18000db2c  cmp     [rcx+19h], r15b
0x18000db30  jz      short loc_18000DB6E
0x18000db32  lea     r8, [rbx+8]
0x18000db36  mov     rax, rbx
0x18000db39  mov     rcx, [r8]
0x18000db3c  jmp     short loc_18000DB4B
0x18000db3e  cmp     rbx, [rcx+10h]
0x18000db42  jnz     short loc_18000DB51
0x18000db44  mov     rbx, rcx
0x18000db47  mov     rcx, [rcx+8]
0x18000db4b  cmp     [rcx+19h], r15b
0x18000db4f  jz      short loc_18000DB3E
0x18000db51  mov     r8, [r8]
0x18000db54  mov     rbx, rcx
0x18000db57  jmp     short loc_18000DB66
0x18000db59  cmp     rax, [r8+10h]
0x18000db5d  jnz     short loc_18000DBA0
0x18000db5f  mov     rax, r8
0x18000db62  mov     r8, [r8+8]
0x18000db66  cmp     [r8+19h], r15b
0x18000db6a  jz      short loc_18000DB59
0x18000db6c  jmp     short loc_18000DBA0
0x18000db6e  mov     r8, [rcx]
0x18000db71  cmp     [r8+19h], r15b
0x18000db75  jnz     short loc_18000DB88
0x18000db77  mov     rax, [r8]
0x18000db7a  mov     rbx, r8
0x18000db7d  mov     r8, rax
0x18000db80  cmp     [rax+19h], r15b
0x18000db84  jz      short loc_18000DB77
0x18000db86  jmp     short loc_18000DB8B
0x18000db88  mov     rbx, rcx
0x18000db8b  mov     r8, [rcx]
0x18000db8e  cmp     [r8+19h], r15b
0x18000db92  jnz     short loc_18000DBA0
0x18000db94  mov     rax, [r8]
0x18000db97  mov     r8, rax
0x18000db9a  cmp     [rax+19h], r15b
0x18000db9e  jz      short loc_18000DB94
0x18000dba0  lea     rcx, ?PendingTimeRequests@Manager@OTS@WpcDesktop@@3V?$map@VSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@U?$less@VSid@@@std@@V?$allocator@U?$pair@$$CBVSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@@std@@@7@@std@@A; std::map<Sid,WpcDesktop::OTS::Manager::LocalRequestState> WpcDesktop::OTS::Manager::PendingTimeRequests
0x18000dba7  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>>,std::_Iterator_base0>)
0x18000dbac  mov     rdi, rax
0x18000dbaf  lea     rcx, [rax+68h]
0x18000dbb3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000dbb8  mov     edx, 98h
0x18000dbbd  mov     rcx, rdi; Block
0x18000dbc0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000dbc5  jmp     loc_18000DB20
```
