# std::map<Sid,WpcDesktop::OTS::Manager::LocalRequestState,std::less<Sid>,std::allocator<std::pair<Sid const,WpcDesktop::OTS::Manager::LocalRequestState>>>::operator[](Sid const &)

- ea: `0x18000bdd0`
- end: `0x18000bf6c`
- name: `??A?$map@VSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@U?$less@VSid@@@std@@V?$allocator@U?$pair@$$CBVSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@@std@@@7@@std@@QEAAAEAULocalRequestState@Manager@OTS@WpcDesktop@@AEBVSid@@@Z`
- size: `412`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x18000bf74`
- `0x18000c164`

## callees

- `0x1800032c4`
- `0x180004bb0`
- `0x180005a04`
- `0x18000bdd0`
- `0x18000d6fc`
- `0x18000d970`
- `0x18001ca8c`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall std::map<Sid,WpcDesktop::OTS::Manager::LocalRequestState>::operator[](__int64 a1, __int64 a2)
{
  __int64 v3; // rbp
  __int64 v4; // r15
  unsigned int v5; // r14d
  __int64 inserted; // rdi
  __int64 v7; // rbx
  const wchar_t *v8; // rsi
  _OWORD *v9; // rdi
  __int64 *v11; // [rsp+20h] [rbp-48h] BYREF
  _OWORD *v12; // [rsp+28h] [rbp-40h]

  v3 = WpcDesktop::OTS::Manager::PendingTimeRequests;
  v4 = *(_QWORD *)(WpcDesktop::OTS::Manager::PendingTimeRequests + 8);
  v5 = 0;
  inserted = WpcDesktop::OTS::Manager::PendingTimeRequests;
  v7 = v4;
  v8 = (const wchar_t *)(a2 + 72);
  if ( !*(_BYTE *)(v4 + 25) )
  {
    do
    {
      v4 = v7;
      if ( (unsigned __int8)std::operator<<unsigned short>((const wchar_t *)(v7 + 104), v8) )
      {
        v5 = 0;
        v7 = *(_QWORD *)(v7 + 16);
      }
      else
      {
        std::operator<<unsigned short>(v8, (const wchar_t *)(v7 + 104));
        v5 = 1;
        inserted = v7;
        v7 = *(_QWORD *)v7;
      }
    }
    while ( !*(_BYTE *)(v7 + 25) );
    v3 = WpcDesktop::OTS::Manager::PendingTimeRequests;
  }
  if ( !*(_BYTE *)(inserted + 25) )
  {
    if ( !(unsigned __int8)std::operator<<unsigned short>(v8, (const wchar_t *)(inserted + 104)) )
    {
      std::operator<<unsigned short>((const wchar_t *)(inserted + 104), v8);
      return inserted + 136;
    }
    v3 = WpcDesktop::OTS::Manager::PendingTimeRequests;
  }
  if ( qword_18004A608 == 0x1AF286BCA1AF286LL )
    std::_Throw_tree_length_error();
  v11 = &WpcDesktop::OTS::Manager::PendingTimeRequests;
  v9 = operator new(0x98u);
  v12 = v9;
  v9[2] = *(_OWORD *)a2;
  v9[3] = *(_OWORD *)(a2 + 16);
  v9[4] = *(_OWORD *)(a2 + 32);
  v9[5] = *(_OWORD *)(a2 + 48);
  *((_DWORD *)v9 + 24) = *(_DWORD *)(a2 + 64);
  std::wstring::wstring((__int64)v9 + 104, (__int64)v8);
  DateTime::GetCurrent((char *)v9 + 136);
  *((_DWORD *)v9 + 37) = 0;
  *(_QWORD *)v9 = v3;
  *((_QWORD *)v9 + 1) = v3;
  *((_QWORD *)v9 + 2) = v3;
  *((_WORD *)v9 + 12) = 0;
  v11 = (__int64 *)v4;
  v12 = (_OWORD *)v5;
  inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>>>>::_Insert_node(
               &WpcDesktop::OTS::Manager::PendingTimeRequests,
               &v11,
               v9);
  return inserted + 136;
}

```

## disassembly

```asm
0x18000bdd0  mov     [rsp+arg_8], rbx
0x18000bdd5  mov     [rsp+arg_0], rcx
0x18000bdda  push    rbp
0x18000bddb  push    rsi
0x18000bddc  push    rdi
0x18000bddd  push    r12
0x18000bddf  push    r13
0x18000bde1  push    r14
0x18000bde3  push    r15
0x18000bde5  sub     rsp, 30h
0x18000bde9  mov     r13, rdx
0x18000bdec  mov     rbp, cs:?PendingTimeRequests@Manager@OTS@WpcDesktop@@3V?$map@VSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@U?$less@VSid@@@std@@V?$allocator@U?$pair@$$CBVSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@@std@@@7@@std@@A; std::map<Sid,WpcDesktop::OTS::Manager::LocalRequestState> WpcDesktop::OTS::Manager::PendingTimeRequests
0x18000bdf3  mov     r15, [rbp+8]
0x18000bdf7  xor     r12d, r12d
0x18000bdfa  mov     r14d, r12d
0x18000bdfd  xor     eax, eax
0x18000bdff  mov     [rsp+68h+arg_10], rax
0x18000be07  mov     rdi, rbp
0x18000be0a  mov     rbx, r15
0x18000be0d  lea     rsi, [rdx+48h]
0x18000be11  cmp     [r15+19h], r12b
0x18000be15  jnz     short loc_18000BE58
0x18000be17  mov     r15, rbx
0x18000be1a  mov     rdx, rsi
0x18000be1d  lea     rcx, [rbx+68h]
0x18000be21  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x18000be26  test    al, al
0x18000be28  jz      short loc_18000BE33
0x18000be2a  mov     r14d, r12d
0x18000be2d  mov     rbx, [rbx+10h]
0x18000be31  jmp     short loc_18000BE4B
0x18000be33  lea     rdx, [rbx+68h]
0x18000be37  mov     rcx, rsi
0x18000be3a  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x18000be3f  mov     r14d, 1
0x18000be45  mov     rdi, rbx
0x18000be48  mov     rbx, [rbx]
0x18000be4b  cmp     [rbx+19h], r12b
0x18000be4f  jz      short loc_18000BE17
0x18000be51  mov     rbp, cs:?PendingTimeRequests@Manager@OTS@WpcDesktop@@3V?$map@VSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@U?$less@VSid@@@std@@V?$allocator@U?$pair@$$CBVSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@@std@@@7@@std@@A; std::map<Sid,WpcDesktop::OTS::Manager::LocalRequestState> WpcDesktop::OTS::Manager::PendingTimeRequests
0x18000be58  cmp     [rdi+19h], r12b
0x18000be5c  jnz     short loc_18000BE86
0x18000be5e  lea     rdx, [rdi+68h]
0x18000be62  mov     rcx, rsi
0x18000be65  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x18000be6a  test    al, al
0x18000be6c  jnz     short loc_18000BE7F
0x18000be6e  mov     rdx, rsi
0x18000be71  lea     rcx, [rdi+68h]
0x18000be75  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x18000be7a  jmp     loc_18000BF4A
0x18000be7f  mov     rbp, cs:?PendingTimeRequests@Manager@OTS@WpcDesktop@@3V?$map@VSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@U?$less@VSid@@@std@@V?$allocator@U?$pair@$$CBVSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@@std@@@7@@std@@A; std::map<Sid,WpcDesktop::OTS::Manager::LocalRequestState> WpcDesktop::OTS::Manager::PendingTimeRequests
0x18000be86  mov     rax, 1AF286BCA1AF286h
0x18000be90  cmp     cs:qword_18004A608, rax
0x18000be97  jz      loc_18000BF66
0x18000be9d  lea     r12, ?PendingTimeRequests@Manager@OTS@WpcDesktop@@3V?$map@VSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@U?$less@VSid@@@std@@V?$allocator@U?$pair@$$CBVSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@@std@@@7@@std@@A; std::map<Sid,WpcDesktop::OTS::Manager::LocalRequestState> WpcDesktop::OTS::Manager::PendingTimeRequests
0x18000bea4  mov     [rsp+68h+var_48], r12
0x18000bea9  mov     [rsp+68h+var_40], 0
0x18000beb2  mov     ecx, 98h; Size
0x18000beb7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bebc  mov     rdi, rax
0x18000bebf  mov     [rsp+68h+var_40], rax
0x18000bec4  lea     rbx, [rax+20h]
0x18000bec8  mov     [rsp+68h+arg_0], rbx
0x18000becd  movups  xmm0, xmmword ptr [r13+0]
0x18000bed2  movups  xmmword ptr [rbx], xmm0
0x18000bed5  movups  xmm1, xmmword ptr [r13+10h]
0x18000beda  movups  xmmword ptr [rbx+10h], xmm1
0x18000bede  movups  xmm0, xmmword ptr [r13+20h]
0x18000bee3  movups  xmmword ptr [rbx+20h], xmm0
0x18000bee7  movups  xmm1, xmmword ptr [r13+30h]
0x18000beec  movups  xmmword ptr [rbx+30h], xmm1
0x18000bef0  mov     eax, [r13+40h]
0x18000bef4  mov     [rbx+40h], eax
0x18000bef7  lea     rcx, [rbx+48h]
0x18000befb  mov     rdx, rsi
0x18000befe  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000bf03  nop
0x18000bf04  lea     rcx, [rbx+68h]
0x18000bf08  call    ?GetCurrent@DateTime@@SA?AV1@XZ; DateTime::GetCurrent(void)
0x18000bf0d  xor     eax, eax
0x18000bf0f  mov     [rbx+74h], eax
0x18000bf12  mov     [rdi], rbp
0x18000bf15  mov     [rdi+8], rbp
0x18000bf19  mov     [rdi+10h], rbp
0x18000bf1d  mov     [rdi+18h], ax
0x18000bf21  mov     [rsp+68h+var_48], r15
0x18000bf26  mov     dword ptr [rsp+68h+var_40], r14d
0x18000bf2b  mov     rax, [rsp+68h+arg_10]
0x18000bf33  mov     dword ptr [rsp+68h+var_40+4], eax
0x18000bf37  mov     r8, rdi
0x18000bf3a  lea     rdx, [rsp+68h+var_48]
0x18000bf3f  mov     rcx, r12
0x18000bf42  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVSid@@V?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBVSid@@V?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBVSid@@V?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>>,void *> *>,std::_Tree_node<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>>,void *> * const)
0x18000bf47  mov     rdi, rax
0x18000bf4a  lea     rax, [rdi+88h]
0x18000bf51  mov     rbx, [rsp+68h+arg_8]
0x18000bf56  add     rsp, 30h
0x18000bf5a  pop     r15
0x18000bf5c  pop     r14
0x18000bf5e  pop     r13
0x18000bf60  pop     r12
0x18000bf62  pop     rdi
0x18000bf63  pop     rsi
0x18000bf64  pop     rbp
0x18000bf65  retn
0x18000bf66  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
