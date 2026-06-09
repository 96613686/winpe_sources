# std::_Tree<std::_Tmap_traits<Sid,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>>,std::less<Sid>,std::allocator<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::AppLimits::AppInventory::AppInfo>>>>>,0>>::_Find<Sid>(Sid const &)

- ea: `0x1800154dc`
- end: `0x180015570`
- name: `??$_Find@VSid@@@?$_Tree@V?$_Tmap_traits@VSid@@V?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@U?$less@VSid@@@3@V?$allocator@U?$pair@$$CBVSid@@V?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@@std@@@3@$0A@@std@@@std@@AEBAPEAU?$_Tree_node@U?$pair@$$CBVSid@@V?$map@VAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@U?$less@VAnyRuntimeApp@appids@@@std@@V?$allocator@U?$pair@$$CBVAnyRuntimeApp@appids@@UAppInfo@AppInventory@AppLimits@wpc@@@std@@@8@@std@@@std@@PEAX@1@AEBVSid@@@Z`
- size: `148`
- prototype: `const wchar_t *__fastcall(const wchar_t **, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180016974`
- `0x1800171f0`
- `0x1800183a4`
- `0x180018a70`

## callees

- `0x180004bb0`
- `0x1800154dc`

## pseudocode

```c
const wchar_t *__fastcall std::_Tree<std::_Tmap_traits<Sid,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>,std::less<Sid>,std::allocator<std::pair<Sid const,std::map<appids::AnyRuntimeApp,wpc::AppLimits::AppInventory::AppInfo>>>,0>>::_Find<Sid>(
        const wchar_t **a1,
        __int64 a2)
{
  const wchar_t *v2; // rsi
  const wchar_t *v5; // rbx
  const wchar_t *v6; // rdi

  v2 = *a1;
  v5 = (const wchar_t *)*((_QWORD *)*a1 + 1);
  if ( *((_BYTE *)v5 + 25) )
  {
    v6 = (const wchar_t *)(a2 + 72);
  }
  else
  {
    do
    {
      v6 = (const wchar_t *)(a2 + 72);
      if ( (unsigned __int8)std::operator<<unsigned short>(v5 + 52, (const wchar_t *)(a2 + 72)) )
      {
        v5 += 8;
      }
      else
      {
        std::operator<<unsigned short>((const wchar_t *)(a2 + 72), v5 + 52);
        v2 = v5;
      }
      v5 = *(const wchar_t **)v5;
    }
    while ( !*((_BYTE *)v5 + 25) );
  }
  if ( *((_BYTE *)v2 + 25) || (unsigned __int8)std::operator<<unsigned short>(v6, v2 + 52) )
    return *a1;
  std::operator<<unsigned short>(v2 + 52, v6);
  return v2;
}

```

## disassembly

```asm
0x1800154dc  push    rbx
0x1800154de  push    rbp
0x1800154df  push    rsi
0x1800154e0  push    rdi
0x1800154e1  push    r14
0x1800154e3  push    r15
0x1800154e5  sub     rsp, 48h
0x1800154e9  mov     rsi, [rcx]
0x1800154ec  xor     eax, eax
0x1800154ee  mov     rbp, rdx
0x1800154f1  mov     [rsp+78h+var_4C], eax
0x1800154f5  mov     r14, rcx
0x1800154f8  mov     rbx, [rsi+8]
0x1800154fc  cmp     [rbx+19h], al
0x1800154ff  jnz     short loc_180015535
0x180015501  lea     rdi, [rbp+48h]
0x180015505  mov     rdx, rdi
0x180015508  lea     rcx, [rbx+68h]
0x18001550c  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x180015511  test    al, al
0x180015513  jz      short loc_18001551B
0x180015515  add     rbx, 10h
0x180015519  jmp     short loc_18001552A
0x18001551b  lea     rdx, [rbx+68h]
0x18001551f  mov     rcx, rdi
0x180015522  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x180015527  mov     rsi, rbx
0x18001552a  mov     rbx, [rbx]
0x18001552d  cmp     byte ptr [rbx+19h], 0
0x180015531  jz      short loc_180015501
0x180015533  jmp     short loc_180015539
0x180015535  lea     rdi, [rdx+48h]
0x180015539  cmp     byte ptr [rsi+19h], 0
0x18001553d  jnz     short loc_180015560
0x18001553f  lea     rdx, [rsi+68h]
0x180015543  mov     rcx, rdi
0x180015546  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x18001554b  test    al, al
0x18001554d  jnz     short loc_180015560
0x18001554f  mov     rdx, rdi
0x180015552  lea     rcx, [rsi+68h]
0x180015556  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x18001555b  mov     rax, rsi
0x18001555e  jmp     short loc_180015563
0x180015560  mov     rax, [r14]
0x180015563  add     rsp, 48h
0x180015567  pop     r15
0x180015569  pop     r14
0x18001556b  pop     rdi
0x18001556c  pop     rsi
0x18001556d  pop     rbp
0x18001556e  pop     rbx
0x18001556f  retn
```
