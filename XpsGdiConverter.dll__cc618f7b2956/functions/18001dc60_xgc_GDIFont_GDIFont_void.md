# xgc::GDIFont::~GDIFont(void)

- ea: `0x18001dc60`
- end: `0x18001dca5`
- name: `??1GDIFont@xgc@@QEAA@XZ`
- size: `69`
- prototype: `void __fastcall(xgc::GDIFont *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001e340`

## callees

- `0x18000e5ec`
- `0x180011b0c`
- `0x18001dc60`
- `0x180022b6c`

## import_xrefs

- `GDI32!RemoveFontMemResourceEx` at `0x18001dc71`
- `GDI32!RemoveFontMemResourceEx` at `0x18001dc71`

## pseudocode

```c
void __fastcall xgc::GDIFont::~GDIFont(HANDLE *this)
{
  RemoveFontMemResourceEx(this[7]);
  if ( this[2] )
    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::erase(
      this[4],
      this);
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(this + 4);
  std::wstring::~wstring(this);
}

```

## disassembly

```asm
0x18001dc60  mov     [rsp+arg_0], rbx
0x18001dc65  push    rdi
0x18001dc66  sub     rsp, 20h
0x18001dc6a  mov     rbx, rcx
0x18001dc6d  mov     rcx, [rcx+38h]; h
0x18001dc71  call    cs:__imp_RemoveFontMemResourceEx
0x18001dc77  cmp     qword ptr [rbx+10h], 0
0x18001dc7c  jz      short loc_18001DC8A
0x18001dc7e  mov     rcx, [rbx+20h]
0x18001dc82  mov     rdx, rbx
0x18001dc85  call    ?erase@?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@QEAA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::erase(std::wstring const &)
0x18001dc8a  lea     rcx, [rbx+20h]
0x18001dc8e  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x18001dc93  mov     rcx, rbx
0x18001dc96  mov     rbx, [rsp+28h+arg_0]
0x18001dc9b  add     rsp, 20h
0x18001dc9f  pop     rdi
0x18001dca0  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
