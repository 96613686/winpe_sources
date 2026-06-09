# std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo,std::default_delete<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo,std::default_delete<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>>>,0>>::~_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo,std::default_delete<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo,std::default_delete<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>>>,0>>(void)

- ea: `0x14000f6cc`
- end: `0x14000f750`
- name: `??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@U?$default_delete@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@@std@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@U?$default_delete@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ`
- size: `132`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000fa04`

## callees

- `0x1400088f4`
- `0x14000a840`
- `0x14000ec68`
- `0x14000f6cc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000f70a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000f70a`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>>,0>>(
        void **a1)
{
  __int64 *v2; // rbx
  _QWORD *v3; // rbp
  _QWORD *v4; // rsi
  HMODULE v5; // rcx

  v2 = (__int64 *)*((_QWORD *)*a1 + 1);
  while ( !*((_BYTE *)v2 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>,void *>>>(
      (__int64)a1,
      (__int64)a1,
      (__int64 *)v2[2]);
    v3 = v2;
    v2 = (__int64 *)*v2;
    v4 = (_QWORD *)v3[8];
    if ( v4 )
    {
      v5 = (HMODULE)v4[2];
      if ( v5 )
        FreeLibrary(v5);
      operator delete(v4, 0x18u);
    }
    std::wstring::~wstring(v3 + 4);
    operator delete(v3, 0x48u);
  }
  operator delete(*a1, 0x48u);
}

```

## disassembly

```asm
0x14000f6cc  push    rbx
0x14000f6ce  push    rbp
0x14000f6cf  push    rsi
0x14000f6d0  push    rdi
0x14000f6d1  push    r14
0x14000f6d3  sub     rsp, 20h
0x14000f6d7  mov     rax, [rcx]
0x14000f6da  mov     rdi, rcx
0x14000f6dd  mov     rbx, [rax+8]
0x14000f6e1  jmp     short loc_14000F733
0x14000f6e3  mov     r8, [rbx+10h]
0x14000f6e7  mov     rdx, rdi
0x14000f6ea  mov     rcx, rdi
0x14000f6ed  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@U?$default_delete@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@@std@@@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@U?$default_delete@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@@std@@@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@U?$default_delete@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@@std@@@2@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@U?$default_delete@UDecoderInfo@UtcDecoderHostApiManager@Diagnostics@Microsoft@@@std@@@2@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>,void *>> &,std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<Microsoft::Diagnostics::UtcDecoderHostApiManager::DecoderInfo>>,void *> *)
0x14000f6f2  mov     rbp, rbx
0x14000f6f5  mov     rbx, [rbx]
0x14000f6f8  mov     rsi, [rbp+40h]
0x14000f6fc  test    rsi, rsi
0x14000f6ff  jz      short loc_14000F71D
0x14000f701  mov     rcx, [rsi+10h]; hLibModule
0x14000f705  test    rcx, rcx
0x14000f708  jz      short loc_14000F710
0x14000f70a  call    cs:__imp_FreeLibrary
0x14000f710  mov     edx, 18h; unsigned __int64
0x14000f715  mov     rcx, rsi; void *
0x14000f718  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000f71d  lea     rcx, [rbp+20h]; void *
0x14000f721  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000f726  mov     edx, 48h ; 'H'; unsigned __int64
0x14000f72b  mov     rcx, rbp; void *
0x14000f72e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000f733  cmp     byte ptr [rbx+19h], 0
0x14000f737  jz      short loc_14000F6E3
0x14000f739  mov     rcx, [rdi]; void *
0x14000f73c  mov     edx, 48h ; 'H'; unsigned __int64
0x14000f741  add     rsp, 20h
0x14000f745  pop     r14
0x14000f747  pop     rdi
0x14000f748  pop     rsi
0x14000f749  pop     rbp
0x14000f74a  pop     rbx
0x14000f74b  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
