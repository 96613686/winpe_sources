# wpc::AppLimits::AppInventory::AppInventoryManager::TryGetDisplayNameForUserApp(Sid,appids::AnyRuntimeApp const &)

- ea: `0x1800183a4`
- end: `0x1800184e0`
- name: `?TryGetDisplayNameForUserApp@AppInventoryManager@AppInventory@AppLimits@wpc@@QEAA?AV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@VSid@@AEBVAnyRuntimeApp@appids@@@Z`
- size: `316`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x180014480`

## callees

- `0x1800032a0`
- `0x180004bb0`
- `0x180005a04`
- `0x180005f9c`
- `0x1800154dc`
- `0x1800183a4`
- `0x18002c010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall wpc::AppLimits::AppInventory::AppInventoryManager::TryGetDisplayNameForUserApp(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  const wchar_t **v7; // rbx
  const wchar_t *v8; // rax
  const wchar_t *v9; // rdi
  __int64 *v10; // rbx
  __int64 *v11; // rbp
  char v12; // al
  __int64 *v13; // rcx
  void (*v14)(void); // rax
  __int64 v16; // [rsp+20h] [rbp-78h] BYREF
  const wchar_t **v17; // [rsp+28h] [rbp-70h]
  int v18; // [rsp+44h] [rbp-54h]
  __int64 v19; // [rsp+50h] [rbp-48h]

  v19 = a3;
  (*(void (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a1 + 40LL))(*a1, &v16);
  v7 = v17;
  v8 = std::_Tree<std::_Tmap_traits<Sid,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>,std::less<Sid>,std::allocator<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>>>,0>>::_Find<Sid>(
         v17,
         a3);
  if ( v8 == *v7 )
    goto LABEL_15;
  v9 = v8 + 68;
  if ( v8 == (const wchar_t *)-136LL )
    goto LABEL_15;
  v10 = *(__int64 **)v9;
  v11 = *(__int64 **)(*(_QWORD *)v9 + 8LL);
  v18 = 0;
  if ( !*((_BYTE *)v11 + 25) )
  {
    do
    {
      v12 = std::operator<<unsigned short>((const wchar_t *)v11 + 40, (const wchar_t *)(a4 + 48));
      if ( !v12 )
        v10 = v11;
      v13 = v11 + 2;
      if ( !v12 )
        v13 = v11;
      v11 = (__int64 *)*v13;
    }
    while ( !*(_BYTE *)(*v13 + 25) );
  }
  if ( *((_BYTE *)v10 + 25)
    || (unsigned __int8)std::operator<<unsigned short>((const wchar_t *)(a4 + 48), (const wchar_t *)v10 + 40)
    || v10 == *(__int64 **)v9
    || v10 == (__int64 *)-112LL )
  {
LABEL_15:
    *(_BYTE *)(a2 + 32) = 0;
    if ( v16 )
    {
      v14 = *(void (**)(void))(*(_QWORD *)v16 + 8LL);
      goto LABEL_17;
    }
  }
  else
  {
    std::wstring::wstring(a2, (__int64)(v10 + 24));
    *(_BYTE *)(a2 + 32) = 1;
    if ( v16 )
    {
      v14 = *(void (**)(void))(*(_QWORD *)v16 + 8LL);
LABEL_17:
      v14();
      v16 = 0;
    }
  }
  std::wstring::~wstring((char **)(a3 + 72));
  return a2;
}

```

## disassembly

```asm
0x1800183a4  mov     r11, rsp
0x1800183a7  mov     [r11+18h], r8
0x1800183ab  mov     [r11+10h], rdx
0x1800183af  push    rbx
0x1800183b0  push    rbp
0x1800183b1  push    rsi
0x1800183b2  push    rdi
0x1800183b3  push    r12
0x1800183b5  push    r14
0x1800183b7  push    r15
0x1800183b9  sub     rsp, 60h
0x1800183bd  mov     rax, cs:__security_cookie
0x1800183c4  xor     rax, rsp
0x1800183c7  mov     [rsp+98h+var_40], rax
0x1800183cc  mov     r14, r9
0x1800183cf  mov     r15, r8
0x1800183d2  mov     rsi, rdx
0x1800183d5  mov     [rsp+98h+var_48], rdx
0x1800183da  mov     [r11-48h], r8
0x1800183de  mov     rcx, [rcx]
0x1800183e1  mov     rax, [rcx]
0x1800183e4  lea     rdx, [r11-78h]
0x1800183e8  mov     rax, [rax+28h]
0x1800183ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800183f1  nop
0x1800183f2  mov     rbx, [rsp+98h+var_70]
0x1800183f7  mov     rdx, r15
0x1800183fa  mov     rcx, rbx
0x1800183fd  call    ??$_Find@VSid@@@?$_Tree@V?$_Tmap_traits@VSid@@V?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@U?$less@VSid@@@3@V?$allocator@U?$pair@$$CBVSid@@V?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@@std@@@3@$0A@@std@@@std@@AEBAPEAU?$_Tree_node@U?$pair@$$CBVSid@@V?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@@std@@PEAX@1@AEBVSid@@@Z; std::_Tree<std::_Tmap_traits<Sid,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>,std::less<Sid>,std::allocator<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>>>,0>>::_Find<Sid>(Sid const &)
0x180018402  cmp     rax, [rbx]
0x180018405  jz      loc_180018495
0x18001840b  lea     rdi, [rax+88h]
0x180018412  test    rdi, rdi
0x180018415  jz      short loc_180018495
0x180018417  mov     rbx, [rdi]
0x18001841a  mov     rbp, [rbx+8]
0x18001841e  xor     eax, eax
0x180018420  mov     [rsp+98h+var_54], eax
0x180018424  cmp     [rbp+19h], al
0x180018427  jnz     short loc_18001844D
0x180018429  lea     rcx, [rbp+50h]
0x18001842d  lea     rdx, [r14+30h]
0x180018431  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x180018436  test    al, al
0x180018438  cmovz   rbx, rbp
0x18001843c  lea     rcx, [rbp+10h]
0x180018440  cmovz   rcx, rbp
0x180018444  mov     rbp, [rcx]
0x180018447  cmp     byte ptr [rbp+19h], 0
0x18001844b  jz      short loc_180018429
0x18001844d  cmp     byte ptr [rbx+19h], 0
0x180018451  jnz     short loc_180018495
0x180018453  lea     rdx, [rbx+50h]
0x180018457  lea     rcx, [r14+30h]
0x18001845b  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x180018460  test    al, al
0x180018462  jnz     short loc_180018495
0x180018464  cmp     rbx, [rdi]
0x180018467  jz      short loc_180018495
0x180018469  lea     rdx, [rbx+70h]
0x18001846d  test    rdx, rdx
0x180018470  jz      short loc_180018495
0x180018472  add     rdx, 50h ; 'P'
0x180018476  mov     rcx, rsi
0x180018479  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001847e  mov     byte ptr [rsi+20h], 1
0x180018482  mov     rcx, [rsp+98h+var_78]
0x180018487  test    rcx, rcx
0x18001848a  jz      short loc_1800184B8
0x18001848c  mov     rax, [rcx]
0x18001848f  mov     rax, [rax+8]
0x180018493  jmp     short loc_1800184AA
0x180018495  mov     byte ptr [rsi+20h], 0
0x180018499  mov     rcx, [rsp+98h+var_78]
0x18001849e  test    rcx, rcx
0x1800184a1  jz      short loc_1800184B8
0x1800184a3  mov     rdx, [rcx]
0x1800184a6  mov     rax, [rdx+8]
0x1800184aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800184af  mov     [rsp+98h+var_78], 0
0x1800184b8  lea     rcx, [r15+48h]
0x1800184bc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800184c1  mov     rax, rsi
0x1800184c4  mov     rcx, [rsp+98h+var_40]
0x1800184c9  xor     rcx, rsp; StackCookie
0x1800184cc  call    __security_check_cookie
0x1800184d1  add     rsp, 60h
0x1800184d5  pop     r15
0x1800184d7  pop     r14
0x1800184d9  pop     r12
0x1800184db  pop     rdi
0x1800184dc  pop     rsi
0x1800184dd  pop     rbp
0x1800184de  pop     rbx
0x1800184df  retn
```
