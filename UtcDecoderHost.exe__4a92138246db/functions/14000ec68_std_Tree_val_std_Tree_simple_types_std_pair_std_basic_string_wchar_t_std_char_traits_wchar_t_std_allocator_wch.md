# std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo,std::default_delete<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo,std::default_delete<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo,std::default_delete<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>>,void *>> &,std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo,std::default_delete<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>>,void *> *)

- ea: `0x14000ec68`
- end: `0x14000ece8`
- name: `??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@U?$default_delete@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@@std@@@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@U?$default_delete@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@@std@@@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@U?$default_delete@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@@std@@@2@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@U?$default_delete@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@@std@@@2@@std@@PEAX@1@@Z`
- size: `128`
- prototype: `void __fastcall(__int64, __int64, __int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000ec68`
- `0x14000f6cc`

## callees

- `0x1400088f4`
- `0x14000a840`
- `0x14000ec68`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000ecac`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000ecac`

## pseudocode

```c
void __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>,void *>>>(
        __int64 a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 *v3; // rbx
  _QWORD *v6; // rsi
  _QWORD *v7; // rdi
  HMODULE v8; // rcx

  v3 = a3;
  while ( !*((_BYTE *)v3 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>,void *>>>(
      a1,
      a2,
      v3[2]);
    v6 = v3;
    v3 = (__int64 *)*v3;
    v7 = (_QWORD *)v6[8];
    if ( v7 )
    {
      v8 = (HMODULE)v7[2];
      if ( v8 )
        FreeLibrary(v8);
      operator delete(v7, 0x18u);
    }
    std::wstring::~wstring(v6 + 4);
    operator delete(v6, 0x48u);
  }
}

```

## disassembly

```asm
0x14000ec68  push    rbx
0x14000ec6a  push    rbp
0x14000ec6b  push    rsi
0x14000ec6c  push    rdi
0x14000ec6d  push    r14
0x14000ec6f  push    r15
0x14000ec71  sub     rsp, 28h
0x14000ec75  cmp     byte ptr [r8+19h], 0
0x14000ec7a  mov     rbx, r8
0x14000ec7d  mov     r14, rdx
0x14000ec80  mov     r15, rcx
0x14000ec83  jnz     short loc_14000ECDB
0x14000ec85  mov     r8, [rbx+10h]
0x14000ec89  mov     rdx, r14
0x14000ec8c  mov     rcx, r15
0x14000ec8f  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@U?$default_delete@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@@std@@@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@U?$default_delete@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@@std@@@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@U?$default_delete@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@@std@@@2@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@U?$default_delete@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@@std@@@2@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>,void *>> &,std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>,void *> *)
0x14000ec94  mov     rsi, rbx
0x14000ec97  mov     rbx, [rbx]
0x14000ec9a  mov     rdi, [rsi+40h]
0x14000ec9e  test    rdi, rdi
0x14000eca1  jz      short loc_14000ECBF
0x14000eca3  mov     rcx, [rdi+10h]; hLibModule
0x14000eca7  test    rcx, rcx
0x14000ecaa  jz      short loc_14000ECB2
0x14000ecac  call    cs:__imp_FreeLibrary
0x14000ecb2  mov     edx, 18h; unsigned __int64
0x14000ecb7  mov     rcx, rdi; void *
0x14000ecba  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000ecbf  lea     rcx, [rsi+20h]; void *
0x14000ecc3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000ecc8  mov     edx, 48h ; 'H'; unsigned __int64
0x14000eccd  mov     rcx, rsi; void *
0x14000ecd0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000ecd5  cmp     byte ptr [rbx+19h], 0
0x14000ecd9  jz      short loc_14000EC85
0x14000ecdb  add     rsp, 28h
0x14000ecdf  pop     r15
0x14000ece1  pop     r14
0x14000ece3  pop     rdi
0x14000ece4  pop     rsi
0x14000ece5  pop     rbp
0x14000ece6  pop     rbx
0x14000ece7  retn
```
