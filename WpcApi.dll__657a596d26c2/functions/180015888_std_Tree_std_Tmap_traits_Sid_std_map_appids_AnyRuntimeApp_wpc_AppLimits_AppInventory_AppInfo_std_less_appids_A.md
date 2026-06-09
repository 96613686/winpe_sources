# std::_Tree<std::_Tmap_traits<Sid,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>>,std::less<Sid>,std::allocator<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>>>>,0>>::emplace<Sid const &,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>> &>(Sid const &,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>> &)

- ea: `0x180015888`
- end: `0x1800159fa`
- name: `??$emplace@AEBVSid@@AEAV?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@@?$_Tree@V?$_Tmap_traits@VSid@@V?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@U?$less@VSid@@@3@V?$allocator@U?$pair@$$CBVSid@@V?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@@std@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVSid@@V?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@@std@@@std@@@std@@@std@@_N@1@AEBVSid@@AEAV?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@1@@Z`
- size: `370`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180016974`
- `0x18001757c`

## callees

- `0x1800036e4`
- `0x180004bb0`
- `0x180005f9c`
- `0x18000d6fc`
- `0x18000d970`
- `0x180014c24`
- `0x180015888`
- `0x1800160ac`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall std::_Tree<std::_Tmap_traits<Sid,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>,std::less<Sid>,std::allocator<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>>>,0>>::emplace<Sid const &,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo> &>(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  __int64 inserted; // rdi
  const wchar_t *v5; // rsi
  int v6; // r13d
  __int64 v9; // rbx
  char v10; // r15
  _QWORD *v11; // rax
  __int64 v12; // rsi
  char *v13; // rdi
  __int64 result; // rax
  __int64 v15; // [rsp+30h] [rbp-68h] BYREF
  int v16; // [rsp+38h] [rbp-60h]
  int v17; // [rsp+3Ch] [rbp-5Ch]
  __int64 v18; // [rsp+40h] [rbp-58h]
  __int64 v19; // [rsp+48h] [rbp-50h] BYREF
  void *Block; // [rsp+50h] [rbp-48h]

  inserted = *a1;
  v5 = (const wchar_t *)(a3 + 72);
  v6 = 0;
  v18 = 0;
  v9 = *(_QWORD *)(inserted + 8);
  v10 = 1;
  if ( !*(_BYTE *)(v9 + 25) )
  {
    do
    {
      v15 = v9;
      if ( (unsigned __int8)std::operator<<unsigned short>((const wchar_t *)(v9 + 104), v5) )
      {
        v9 = *(_QWORD *)(v9 + 16);
        v6 = 0;
      }
      else
      {
        std::operator<<unsigned short>(v5, (const wchar_t *)(v9 + 104));
        inserted = v9;
        v6 = 1;
        v9 = *(_QWORD *)v9;
      }
    }
    while ( !*(_BYTE *)(v9 + 25) );
    v9 = v15;
  }
  if ( *(_BYTE *)(inserted + 25)
    || (unsigned __int8)std::operator<<unsigned short>(v5, (const wchar_t *)(inserted + 104)) )
  {
    if ( a1[1] == 0x1AF286BCA1AF286LL )
      std::_Throw_tree_length_error();
    v11 = std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>>,void *>>>(
            &v19,
            (__int64)a1,
            *a1,
            a3,
            a4);
    v12 = v11[1];
    v11[1] = 0;
    v13 = (char *)Block;
    if ( Block )
    {
      std::_Tree<std::_Tmap_traits<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>,0>>::~_Tree<std::_Tmap_traits<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>,0>>((char *)Block + 136);
      std::wstring::~wstring(v13 + 104);
      if ( Block )
        operator delete(Block);
    }
    v17 = v18;
    v15 = v9;
    v16 = v6;
    inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>>>>::_Insert_node(
                 a1,
                 &v15,
                 v12);
  }
  else
  {
    std::operator<<unsigned short>((const wchar_t *)(inserted + 104), v5);
    v10 = 0;
  }
  result = a2;
  *(_QWORD *)a2 = inserted;
  *(_BYTE *)(a2 + 8) = v10;
  return result;
}

```

## disassembly

```asm
0x180015888  mov     [rsp+arg_8], rbx
0x18001588d  mov     [rsp+arg_18], r9
0x180015892  mov     [rsp+arg_10], r8
0x180015897  push    rbp
0x180015898  push    rsi
0x180015899  push    rdi
0x18001589a  push    r12
0x18001589c  push    r13
0x18001589e  push    r14
0x1800158a0  push    r15
0x1800158a2  sub     rsp, 60h
0x1800158a6  mov     rdi, [rcx]
0x1800158a9  lea     rsi, [r8+48h]
0x1800158ad  xor     r13d, r13d
0x1800158b0  mov     r12, rcx
0x1800158b3  xor     ecx, ecx
0x1800158b5  mov     r14, rdx
0x1800158b8  mov     [rsp+98h+var_58], rcx
0x1800158bd  mov     rbx, [rdi+8]
0x1800158c1  lea     r15d, [r13+1]
0x1800158c5  cmp     [rbx+19h], cl
0x1800158c8  jnz     short loc_180015908
0x1800158ca  mov     rdx, rsi
0x1800158cd  mov     [rsp+98h+var_68], rbx
0x1800158d2  lea     rcx, [rbx+68h]
0x1800158d6  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x1800158db  test    al, al
0x1800158dd  jz      short loc_1800158E8
0x1800158df  mov     rbx, [rbx+10h]
0x1800158e3  xor     r13d, r13d
0x1800158e6  jmp     short loc_1800158FD
0x1800158e8  lea     rdx, [rbx+68h]
0x1800158ec  mov     rcx, rsi
0x1800158ef  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x1800158f4  mov     rdi, rbx
0x1800158f7  mov     r13d, r15d
0x1800158fa  mov     rbx, [rbx]
0x1800158fd  cmp     byte ptr [rbx+19h], 0
0x180015901  jz      short loc_1800158CA
0x180015903  mov     rbx, [rsp+98h+var_68]
0x180015908  cmp     byte ptr [rdi+19h], 0
0x18001590c  jnz     short loc_180015932
0x18001590e  lea     rdx, [rdi+68h]
0x180015912  mov     rcx, rsi
0x180015915  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x18001591a  test    al, al
0x18001591c  jnz     short loc_180015932
0x18001591e  mov     rdx, rsi
0x180015921  lea     rcx, [rdi+68h]
0x180015925  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x18001592a  xor     r15b, r15b
0x18001592d  jmp     loc_1800159D2
0x180015932  mov     rax, 1AF286BCA1AF286h
0x18001593c  cmp     [r12+8], rax
0x180015941  jz      loc_1800159F4
0x180015947  mov     rax, [rsp+98h+arg_18]
0x18001594f  lea     rcx, [rsp+98h+var_50]
0x180015954  mov     r9, [rsp+98h+arg_10]
0x18001595c  mov     rdx, r12
0x18001595f  mov     r8, [r12]
0x180015963  mov     [rsp+98h+var_78], rax
0x180015968  call    ??$?0AEBVSid@@AEAV?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@@?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBVSid@@V?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_Tree_node@U?$pair@$$CBVSid@@V?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBVSid@@V?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@@std@@PEAX@1@AEBVSid@@AEAV?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@1@@Z; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>>,void *>>>(std::allocator<std::_Tree_node<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>>,void *>> &,std::_Tree_node<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>>,void *> *,Sid const &,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo> &)
0x18001596d  mov     rsi, [rax+8]
0x180015971  mov     qword ptr [rax+8], 0
0x180015979  mov     rdi, [rsp+98h+Block]
0x18001597e  test    rdi, rdi
0x180015981  jz      short loc_1800159AC
0x180015983  lea     rcx, [rdi+88h]
0x18001598a  call    ??1?$_Tree@V?$_Tmap_traits@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>,0>>::~_Tree<std::_Tmap_traits<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>,0>>(void)
0x18001598f  lea     rcx, [rdi+68h]
0x180015993  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180015998  mov     rcx, [rsp+98h+Block]; Block
0x18001599d  test    rcx, rcx
0x1800159a0  jz      short loc_1800159AC
0x1800159a2  mov     edx, 98h
0x1800159a7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800159ac  mov     rax, [rsp+98h+var_58]
0x1800159b1  lea     rdx, [rsp+98h+var_68]
0x1800159b6  mov     r8, rsi
0x1800159b9  mov     [rsp+98h+var_5C], eax
0x1800159bd  mov     rcx, r12
0x1800159c0  mov     [rsp+98h+var_68], rbx
0x1800159c5  mov     [rsp+98h+var_60], r13d
0x1800159ca  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVSid@@V?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBVSid@@V?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBVSid@@V?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>>,void *> *>,std::_Tree_node<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>>,void *> * const)
0x1800159cf  mov     rdi, rax
0x1800159d2  mov     rbx, [rsp+98h+arg_8]
0x1800159da  mov     rax, r14
0x1800159dd  mov     [r14], rdi
0x1800159e0  mov     [r14+8], r15b
0x1800159e4  add     rsp, 60h
0x1800159e8  pop     r15
0x1800159ea  pop     r14
0x1800159ec  pop     r13
0x1800159ee  pop     r12
0x1800159f0  pop     rdi
0x1800159f1  pop     rsi
0x1800159f2  pop     rbp
0x1800159f3  retn
0x1800159f4  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
