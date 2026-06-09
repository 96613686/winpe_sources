# SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::~CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>(void)

- ea: `0x1800247bc`
- end: `0x180024889`
- name: `??1?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@UEAA@XZ`
- size: `205`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800248e0`
- `0x1800253d0`

## callees

- `0x18000282c`
- `0x180011d7c`
- `0x1800247bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002480f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180024819`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002480f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180024819`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024802`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024878`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024802`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024878`
- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x1800247d5`
- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x1800247d5`

## pseudocode

```c
int __fastcall SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::~CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>(
        __int64 a1)
{
  char *v2; // rcx
  _QWORD **v3; // rcx
  _QWORD *v4; // rcx
  _QWORD *v5; // rbx
  char *v6; // rcx
  int result; // eax

  if ( *(_QWORD *)(a1 + 216) )
  {
    CoDecrementMTAUsage();
    *(_QWORD *)(a1 + 216) = 0;
  }
  v2 = *(char **)(a1 + 200);
  *(_QWORD *)(a1 + 200) = 0;
  if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v2);
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 160));
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 112));
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>>,std::_Iterator_base0>>>(a1 + 64);
  v3 = *(_QWORD ***)(a1 + 48);
  *v3[1] = 0;
  v4 = *v3;
  if ( v4 )
  {
    do
    {
      v5 = (_QWORD *)*v4;
      operator delete(v4);
      v4 = v5;
    }
    while ( v5 );
  }
  operator delete(*(void **)(a1 + 48));
  v6 = *(char **)(a1 + 16);
  *(_QWORD *)(a1 + 16) = 0;
  result = (_DWORD)v6 - 1;
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    return CloseHandle(v6);
  return result;
}

```

## disassembly

```asm
0x1800247bc  mov     [rsp+arg_0], rbx
0x1800247c1  push    rdi
0x1800247c2  sub     rsp, 20h
0x1800247c6  mov     rdi, rcx
0x1800247c9  mov     rcx, [rcx+0D8h]
0x1800247d0  test    rcx, rcx
0x1800247d3  jz      short loc_1800247E6
0x1800247d5  call    cs:__imp_CoDecrementMTAUsage
0x1800247db  mov     qword ptr [rdi+0D8h], 0
0x1800247e6  mov     rcx, [rdi+0C8h]; hObject
0x1800247ed  mov     qword ptr [rdi+0C8h], 0
0x1800247f8  lea     rax, [rcx-1]
0x1800247fc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180024800  ja      short loc_180024808
0x180024802  call    cs:__imp_CloseHandle
0x180024808  lea     rcx, [rdi+0A0h]; lpCriticalSection
0x18002480f  call    cs:__imp_DeleteCriticalSection
0x180024815  lea     rcx, [rdi+70h]; lpCriticalSection
0x180024819  call    cs:__imp_DeleteCriticalSection
0x18002481f  lea     rcx, [rdi+40h]
0x180024823  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::CCallback *>>,std::_Iterator_base0>>>(void)
0x180024828  mov     rcx, [rdi+30h]
0x18002482c  mov     rax, [rcx+8]
0x180024830  mov     qword ptr [rax], 0
0x180024837  mov     rcx, [rcx]; Block
0x18002483a  test    rcx, rcx
0x18002483d  jz      short loc_180024854
0x18002483f  mov     rbx, [rcx]
0x180024842  mov     edx, 18h
0x180024847  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002484c  mov     rcx, rbx
0x18002484f  test    rbx, rbx
0x180024852  jnz     short loc_18002483F
0x180024854  mov     rcx, [rdi+30h]; Block
0x180024858  mov     edx, 18h
0x18002485d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180024862  mov     rcx, [rdi+10h]; hObject
0x180024866  mov     qword ptr [rdi+10h], 0
0x18002486e  lea     rax, [rcx-1]
0x180024872  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180024876  ja      short loc_18002487E
0x180024878  call    cs:__imp_CloseHandle
0x18002487e  mov     rbx, [rsp+28h+arg_0]
0x180024883  add     rsp, 20h
0x180024887  pop     rdi
0x180024888  retn
```
