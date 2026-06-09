# std::unique_ptr<std::unordered_map<ushort,HINSTANCE__ *,std::hash<ushort>,std::equal_to<ushort>,std::allocator<std::pair<ushort const,HINSTANCE__ *>>>,std::default_delete<std::unordered_map<ushort,HINSTANCE__ *,std::hash<ushort>,std::equal_to<ushort>,std::allocator<std::pair<ushort const,HINSTANCE__ *>>>>>::~unique_ptr<std::unordered_map<ushort,HINSTANCE__ *,std::hash<ushort>,std::equal_to<ushort>,std::allocator<std::pair<ushort const,HINSTANCE__ *>>>,std::default_delete<std::unordered_map<ushort,HINSTANCE__ *,std::hash<ushort>,std::equal_to<ushort>,std::allocator<std::pair<ushort const,HINSTANCE__ *>>>>>(void)

- ea: `0x140013044`
- end: `0x1400130b1`
- name: `??1?$unique_ptr@V?$unordered_map@GPEAUHINSTANCE__@@U?$hash@G@std@@U?$equal_to@G@3@V?$allocator@U?$pair@$$CBGPEAUHINSTANCE__@@@std@@@3@@std@@U?$default_delete@V?$unordered_map@GPEAUHINSTANCE__@@U?$hash@G@std@@U?$equal_to@G@3@V?$allocator@U?$pair@$$CBGPEAUHINSTANCE__@@@std@@@3@@std@@@2@@std@@QEAA@XZ`
- size: `109`
- prototype: `void __fastcall(void ***)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140015c70`

## callees

- `0x140001fac`
- `0x140013044`
- `0x14001382c`

## pseudocode

```c
void __fastcall std::unique_ptr<std::unordered_map<unsigned short,HINSTANCE__ *>>::~unique_ptr<std::unordered_map<unsigned short,HINSTANCE__ *>>(
        void ***a1)
{
  void **v1; // rdi
  _QWORD **v2; // rcx
  _QWORD *v3; // rcx
  _QWORD *v4; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>((__int64)(v1 + 3));
    v2 = (_QWORD **)v1[1];
    *v2[1] = 0;
    v3 = *v2;
    if ( v3 )
    {
      do
      {
        v4 = (_QWORD *)*v3;
        operator delete(v3);
        v3 = v4;
      }
      while ( v4 );
    }
    operator delete(v1[1]);
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x140013044  mov     [rsp+arg_8], rbx
0x140013049  push    rdi
0x14001304a  sub     rsp, 20h
0x14001304e  mov     rdi, [rcx]
0x140013051  test    rdi, rdi
0x140013054  jz      short loc_1400130A6
0x140013056  lea     rcx, [rdi+18h]
0x14001305a  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>(void)
0x14001305f  mov     rcx, [rdi+8]
0x140013063  mov     rax, [rcx+8]
0x140013067  mov     qword ptr [rax], 0
0x14001306e  mov     rcx, [rcx]; Block
0x140013071  test    rcx, rcx
0x140013074  jz      short loc_14001308B
0x140013076  mov     rbx, [rcx]
0x140013079  mov     edx, 20h ; ' '
0x14001307e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140013083  mov     rcx, rbx
0x140013086  test    rbx, rbx
0x140013089  jnz     short loc_140013076
0x14001308b  mov     rcx, [rdi+8]; Block
0x14001308f  mov     edx, 20h ; ' '
0x140013094  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140013099  mov     edx, 40h ; '@'
0x14001309e  mov     rcx, rdi; Block
0x1400130a1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400130a6  mov     rbx, [rsp+28h+arg_8]
0x1400130ab  add     rsp, 20h
0x1400130af  pop     rdi
0x1400130b0  retn
```
