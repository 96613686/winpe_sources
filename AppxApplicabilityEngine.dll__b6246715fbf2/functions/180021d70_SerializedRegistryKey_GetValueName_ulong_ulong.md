# SerializedRegistryKey::GetValueName(ulong,ulong *)

- ea: `0x180021d70`
- end: `0x180021e1e`
- name: `?GetValueName@SerializedRegistryKey@@UEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KPEAK@Z`
- size: `174`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, _DWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x18000e024`
- `0x18000f7a0`
- `0x180021d70`
- `0x180021f34`

## pseudocode

```c
__int64 __fastcall SerializedRegistryKey::GetValueName(__int64 a1, __int64 a2, unsigned int a3, _DWORD *a4)
{
  __int64 v5; // rsi
  __int64 v7; // r8
  __int64 v8; // r9
  _QWORD *v9; // rax
  _QWORD v11[5]; // [rsp+30h] [rbp-28h] BYREF

  v5 = a3;
  SerializedRegistryKey::GetNameValuePairs(a1, v11);
  v8 = v11[0];
  if ( a4 )
  {
    *a4 = 0;
    v9 = (_QWORD *)(80 * v5 + v8 + 40);
    if ( *(_QWORD *)(80 * v5 + v8 + 64) >= 8u )
      v9 = (_QWORD *)*v9;
    switch ( *(_WORD *)v9 )
    {
      case 'D':
        *a4 = 4;
        break;
      case 'M':
        *a4 = 7;
        break;
      case 'S':
        *a4 = 1;
        break;
    }
  }
  std::wstring::wstring(a2, v8 + 80 * v5, v7);
  std::vector<std::pair<std::wstring,std::wstring>>::_Tidy(v11);
  return a2;
}

```

## disassembly

```asm
0x180021d70  mov     rax, rsp
0x180021d73  push    rdi
0x180021d74  sub     rsp, 50h
0x180021d78  mov     qword ptr [rax-30h], 0FFFFFFFFFFFFFFFEh
0x180021d80  mov     [rax+8], rbx
0x180021d84  mov     [rax+10h], rsi
0x180021d88  mov     rbx, r9
0x180021d8b  mov     esi, r8d
0x180021d8e  mov     rdi, rdx
0x180021d91  lea     rdx, [rax-28h]
0x180021d95  call    ?GetNameValuePairs@SerializedRegistryKey@@AEBA?AV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@XZ; SerializedRegistryKey::GetNameValuePairs(void)
0x180021d9a  nop
0x180021d9b  mov     r9, [rsp+58h+var_28]
0x180021da0  test    rbx, rbx
0x180021da3  jz      short loc_180021DED
0x180021da5  mov     dword ptr [rbx], 0
0x180021dab  lea     rcx, [rsi+rsi*4]
0x180021daf  shl     rcx, 4
0x180021db3  lea     rax, [r9+28h]
0x180021db7  add     rax, rcx
0x180021dba  cmp     qword ptr [rcx+r9+40h], 8
0x180021dc0  jb      short loc_180021DC5
0x180021dc2  mov     rax, [rax]
0x180021dc5  cmp     word ptr [rax], 44h ; 'D'
0x180021dc9  jz      short loc_180021DE7
0x180021dcb  cmp     word ptr [rax], 4Dh ; 'M'
0x180021dcf  jz      short loc_180021DDF
0x180021dd1  cmp     word ptr [rax], 53h ; 'S'
0x180021dd5  jnz     short loc_180021DED
0x180021dd7  mov     dword ptr [rbx], 1
0x180021ddd  jmp     short loc_180021DED
0x180021ddf  mov     dword ptr [rbx], 7
0x180021de5  jmp     short loc_180021DED
0x180021de7  mov     dword ptr [rbx], 4
0x180021ded  lea     rdx, [rsi+rsi*4]
0x180021df1  shl     rdx, 4
0x180021df5  add     rdx, r9
0x180021df8  mov     rcx, rdi
0x180021dfb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180021e00  nop
0x180021e01  lea     rcx, [rsp+58h+var_28]
0x180021e06  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@IEAAXXZ; std::vector<std::pair<std::wstring,std::wstring>>::_Tidy(void)
0x180021e0b  mov     rax, rdi
0x180021e0e  mov     rbx, [rsp+58h+arg_0]
0x180021e13  mov     rsi, [rsp+58h+arg_8]
0x180021e18  add     rsp, 50h
0x180021e1c  pop     rdi
0x180021e1d  retn
```
