# std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>>>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>>>,void *>>>(std::allocator<std::_Tree_node<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>>>,void *>> &,std::_Tree_node<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>>>,void *> *,Sid const &,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>> &)

- ea: `0x180014c24`
- end: `0x180014d91`
- name: `??$?0AEBVSid@@AEAV?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@@?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBVSid@@V?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_Tree_node@U?$pair@$$CBVSid@@V?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBVSid@@V?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@@std@@PEAX@1@AEBVSid@@AEAV?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@1@@Z`
- size: `365`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180015888`

## callees

- `0x1800032c4`
- `0x180005a04`
- `0x180014c24`
- `0x180014e38`
- `0x1800161b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>>,void *>>>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5)
{
  _OWORD *v8; // rax
  char *v9; // rbx
  char *v10; // rdi
  _QWORD *v11; // rax
  _QWORD *v12; // r8
  __int64 **v13; // rdx
  __int64 *i; // rcx
  __int64 j; // rcx
  __int64 k; // rcx
  char *v18; // [rsp+20h] [rbp-28h] BYREF
  char *v19; // [rsp+28h] [rbp-20h]

  *a1 = a2;
  a1[1] = 0;
  v8 = operator new(0x98u);
  a1[1] = v8;
  v9 = (char *)(v8 + 2);
  v8[2] = *(_OWORD *)a4;
  v8[3] = *(_OWORD *)(a4 + 16);
  v8[4] = *(_OWORD *)(a4 + 32);
  v8[5] = *(_OWORD *)(a4 + 48);
  *((_DWORD *)v8 + 24) = *(_DWORD *)(a4 + 64);
  std::wstring::wstring((char *)v8 + 104, a4 + 72);
  v10 = v9 + 104;
  *((_QWORD *)v9 + 13) = 0;
  *((_QWORD *)v9 + 14) = 0;
  v18 = v9 + 104;
  v19 = v9 + 104;
  v11 = operator new(0x158u);
  *v11 = v11;
  v11[1] = v11;
  v11[2] = v11;
  *((_WORD *)v11 + 12) = 257;
  *((_QWORD *)v9 + 13) = v11;
  *(_QWORD *)(*((_QWORD *)v9 + 13) + 8LL) = std::_Tree<std::_Tmap_traits<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>,0>>::_Copy_nodes<0>(
                                              v9 + 104,
                                              *(_QWORD *)(*a5 + 8LL),
                                              v11);
  *((_QWORD *)v9 + 14) = a5[1];
  v12 = (_QWORD *)*((_QWORD *)v9 + 13);
  v13 = (__int64 **)v12[1];
  if ( *((_BYTE *)v13 + 25) )
  {
    *v12 = v12;
    *(_QWORD *)(*(_QWORD *)v10 + 16LL) = *(_QWORD *)v10;
  }
  else
  {
    for ( i = *v13; !*((_BYTE *)i + 25); i = (__int64 *)*i )
      v13 = (__int64 **)i;
    *v12 = v13;
    for ( j = *(_QWORD *)(*(_QWORD *)v10 + 8LL); !*(_BYTE *)(*(_QWORD *)(j + 16) + 25LL); j = *(_QWORD *)(j + 16) )
      ;
    *(_QWORD *)(*(_QWORD *)v10 + 16LL) = j;
  }
  v19 = 0;
  std::_Tree_head_scoped_ptr<std::allocator<std::_Tree_node<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>>>::~_Tree_head_scoped_ptr<std::allocator<std::_Tree_node<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>>>(&v18);
  *(_QWORD *)a1[1] = a3;
  *(_QWORD *)(a1[1] + 8LL) = a3;
  *(_QWORD *)(a1[1] + 16LL) = a3;
  for ( k = 0; k != 2; ++k )
    *(_BYTE *)(a1[1] + k + 24) = 0;
  return a1;
}

```

## disassembly

```asm
0x180014c24  mov     [rsp+arg_10], rbx
0x180014c29  mov     [rsp+arg_0], rcx
0x180014c2e  push    rbp
0x180014c2f  push    rsi
0x180014c30  push    rdi
0x180014c31  sub     rsp, 30h
0x180014c35  mov     rdi, r9
0x180014c38  mov     rbp, r8
0x180014c3b  mov     rsi, rcx
0x180014c3e  mov     [rcx], rdx
0x180014c41  mov     qword ptr [rcx+8], 0
0x180014c49  mov     ecx, 98h; Size
0x180014c4e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014c53  mov     [rsi+8], rax
0x180014c57  lea     rbx, [rax+20h]
0x180014c5b  mov     [rsp+48h+arg_8], rbx
0x180014c60  movups  xmm0, xmmword ptr [rdi]
0x180014c63  movups  xmmword ptr [rbx], xmm0
0x180014c66  movups  xmm1, xmmword ptr [rdi+10h]
0x180014c6a  movups  xmmword ptr [rbx+10h], xmm1
0x180014c6e  movups  xmm0, xmmword ptr [rdi+20h]
0x180014c72  movups  xmmword ptr [rbx+20h], xmm0
0x180014c76  movups  xmm1, xmmword ptr [rdi+30h]
0x180014c7a  movups  xmmword ptr [rbx+30h], xmm1
0x180014c7e  mov     eax, [rdi+40h]
0x180014c81  mov     [rbx+40h], eax
0x180014c84  lea     rdx, [rdi+48h]
0x180014c88  lea     rcx, [rbx+48h]
0x180014c8c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180014c91  nop
0x180014c92  lea     rdi, [rbx+68h]
0x180014c96  mov     qword ptr [rdi], 0
0x180014c9d  mov     qword ptr [rdi+8], 0
0x180014ca5  mov     [rsp+48h+var_28], rdi
0x180014caa  mov     [rsp+48h+var_20], rdi
0x180014caf  mov     ecx, 158h; Size
0x180014cb4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014cb9  mov     [rax], rax
0x180014cbc  mov     [rax+8], rax
0x180014cc0  mov     [rax+10h], rax
0x180014cc4  mov     word ptr [rax+18h], 101h
0x180014cca  mov     [rdi], rax
0x180014ccd  mov     rbx, [rsp+48h+arg_20]
0x180014cd2  mov     rdx, [rbx]
0x180014cd5  mov     r8, rax
0x180014cd8  mov     rdx, [rdx+8]
0x180014cdc  mov     rcx, rdi
0x180014cdf  call    ??$_Copy_nodes@$0A@@?$_Tree@V?$_Tmap_traits@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@PEAX@1@PEAU21@0@Z; std::_Tree<std::_Tmap_traits<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>,0>>::_Copy_nodes<0>(std::_Tree_node<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>,void *> *,std::_Tree_node<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>,void *> *)
0x180014ce4  mov     rcx, [rdi]
0x180014ce7  mov     [rcx+8], rax
0x180014ceb  mov     rax, [rbx+8]
0x180014cef  mov     [rdi+8], rax
0x180014cf3  mov     r8, [rdi]
0x180014cf6  mov     rdx, [r8+8]
0x180014cfa  cmp     byte ptr [rdx+19h], 0
0x180014cfe  jnz     short loc_180014D38
0x180014d00  mov     rcx, [rdx]
0x180014d03  cmp     byte ptr [rcx+19h], 0
0x180014d07  jnz     short loc_180014D18
0x180014d09  mov     rdx, rcx
0x180014d0c  mov     rax, [rcx]
0x180014d0f  mov     rcx, rax
0x180014d12  cmp     byte ptr [rax+19h], 0
0x180014d16  jz      short loc_180014D09
0x180014d18  mov     [r8], rdx
0x180014d1b  mov     rdx, [rdi]
0x180014d1e  mov     rcx, [rdx+8]
0x180014d22  jmp     short loc_180014D28
0x180014d24  mov     rcx, [rcx+10h]
0x180014d28  mov     rax, [rcx+10h]
0x180014d2c  cmp     byte ptr [rax+19h], 0
0x180014d30  jz      short loc_180014D24
0x180014d32  mov     [rdx+10h], rcx
0x180014d36  jmp     short loc_180014D42
0x180014d38  mov     [r8], r8
0x180014d3b  mov     rax, [rdi]
0x180014d3e  mov     [rax+10h], rax
0x180014d42  mov     [rsp+48h+var_20], 0
0x180014d4b  lea     rcx, [rsp+48h+var_28]
0x180014d50  call    ??1?$_Tree_head_scoped_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@PEAX@std@@@std@@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@std@@@2@@std@@QEAA@XZ; std::_Tree_head_scoped_ptr<std::allocator<std::_Tree_node<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>>>::~_Tree_head_scoped_ptr<std::allocator<std::_Tree_node<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>>>(void)
0x180014d55  nop
0x180014d56  mov     rax, [rsi+8]
0x180014d5a  mov     [rax], rbp
0x180014d5d  mov     rax, [rsi+8]
0x180014d61  mov     [rax+8], rbp
0x180014d65  mov     rax, [rsi+8]
0x180014d69  mov     [rax+10h], rbp
0x180014d6d  xor     ecx, ecx
0x180014d6f  mov     rax, [rsi+8]
0x180014d73  mov     byte ptr [rax+rcx+18h], 0
0x180014d78  inc     rcx
0x180014d7b  cmp     rcx, 2
0x180014d7f  jnz     short loc_180014D6F
0x180014d81  mov     rax, rsi
0x180014d84  mov     rbx, [rsp+48h+arg_10]
0x180014d89  add     rsp, 30h
0x180014d8d  pop     rdi
0x180014d8e  pop     rsi
0x180014d8f  pop     rbp
0x180014d90  retn
```
