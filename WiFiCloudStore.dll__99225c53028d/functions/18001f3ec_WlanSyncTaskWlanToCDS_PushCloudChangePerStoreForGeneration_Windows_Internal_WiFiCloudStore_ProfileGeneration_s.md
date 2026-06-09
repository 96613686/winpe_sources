# WlanSyncTaskWlanToCDS::PushCloudChangePerStoreForGeneration(Windows::Internal::WiFiCloudStore::ProfileGeneration,std::function<void (ushort const *)>)

- ea: `0x18001f3ec`
- end: `0x18001f54d`
- name: `?PushCloudChangePerStoreForGeneration@WlanSyncTaskWlanToCDS@@CAXW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@V?$function@$$A6AXPEBG@Z@std@@@Z`
- size: `353`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18001314c`
- `0x180014d70`

## callees

- `0x180006afc`
- `0x18001e624`
- `0x18001f3ec`
- `0x180025308`
- `0x180033ef0`
- `0x180035bb8`
- `0x180041010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001f546`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001f546`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall WlanSyncTaskWlanToCDS::PushCloudChangePerStoreForGeneration(int a1, __int64 a2)
{
  __int64 v3; // rdx
  __int64 v4; // rcx
  unsigned int v5; // r8d
  __int64 v6; // rdi
  _QWORD *i; // rbx
  _QWORD *v8; // r8
  const unsigned __int16 **v9; // rbx
  const unsigned __int16 **v10; // rdi
  __int64 v11; // rcx
  __int64 v12; // rcx
  _QWORD v13[2]; // [rsp+20h] [rbp-30h] BYREF
  __int128 v14; // [rsp+30h] [rbp-20h] BYREF
  __int64 v15; // [rsp+40h] [rbp-10h]
  int v16; // [rsp+70h] [rbp+20h] BYREF
  __int64 v17; // [rsp+78h] [rbp+28h]
  const unsigned __int16 *v18; // [rsp+80h] [rbp+30h] BYREF
  __int64 v19; // [rsp+88h] [rbp+38h] BYREF

  v17 = a2;
  v16 = a1;
  std::vector<bond::blob>::vector<bond::blob>(&v14);
  if ( v5 == 0x80000000 )
  {
    v18 = c_wiFiCloudStoreDataReferenceDefaultCollectionName;
    goto LABEL_12;
  }
  if ( v5 <= 2 )
  {
    v18 = 0;
    v18 = *(const unsigned __int16 **)std::unordered_map<enum Windows::Internal::WiFiCloudStore::ProfileGeneration,unsigned short const *>::at(
                                        v4,
                                        &v16);
LABEL_12:
    v13[0] = &v18;
    v13[1] = &v19;
    std::vector<unsigned short const *>::operator=(&v14, v13);
    goto LABEL_13;
  }
  if ( v5 == 0x7FFFFFFF )
  {
    v6 = qword_180052A48;
    for ( i = *(_QWORD **)qword_180052A48; i != (_QWORD *)v6; i = (_QWORD *)*i )
    {
      v8 = i + 3;
      v3 = *((_QWORD *)&v14 + 1);
      if ( *((_QWORD *)&v14 + 1) == v15 )
      {
        std::vector<unsigned short const *>::_Emplace_reallocate<unsigned short const * const &>(
          &v14,
          *((_QWORD *)&v14 + 1),
          v8);
      }
      else
      {
        **((_QWORD **)&v14 + 1) = *v8;
        *((_QWORD *)&v14 + 1) += 8LL;
      }
    }
  }
LABEL_13:
  v10 = (const unsigned __int16 **)*((_QWORD *)&v14 + 1);
  v9 = (const unsigned __int16 **)v14;
  if ( (_QWORD)v14 != *((_QWORD *)&v14 + 1) )
  {
    do
    {
      v18 = *v9;
      v11 = *(_QWORD *)(a2 + 56);
      if ( !v11 )
      {
        std::_Xbad_function_call();
        JUMPOUT(0x18001F54DLL);
      }
      (*(void (__fastcall **)(__int64, const unsigned __int16 **))(*(_QWORD *)v11 + 16LL))(v11, &v18);
      ++v9;
    }
    while ( v9 != v10 );
    v9 = (const unsigned __int16 **)v14;
  }
  if ( v9 )
  {
    std::_Deallocate<16>(v9, (v15 - (_QWORD)v9) & 0xFFFFFFFFFFFFFFF8uLL);
    v14 = 0;
    v15 = 0;
  }
  v12 = *(_QWORD *)(a2 + 56);
  if ( v12 )
  {
    LOBYTE(v3) = v12 != a2;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v12 + 32LL))(v12, v3);
    *(_QWORD *)(a2 + 56) = 0;
  }
}

```

## disassembly

```asm
0x18001f3ec  mov     [rsp-18h+arg_18], rbx
0x18001f3f1  mov     [rsp-18h+arg_8], rdx
0x18001f3f6  mov     [rsp-18h+arg_0], ecx
0x18001f3fa  push    rbp
0x18001f3fb  push    rsi
0x18001f3fc  push    rdi
0x18001f3fd  mov     rbp, rsp
0x18001f400  sub     rsp, 50h
0x18001f404  mov     rsi, rdx
0x18001f407  mov     r8d, ecx
0x18001f40a  lea     rcx, [rbp+var_20]
0x18001f40e  call    ??0?$vector@Vblob@bond@@V?$allocator@Vblob@bond@@@std@@@std@@QEAA@AEBV?$allocator@Vblob@bond@@@1@@Z; std::vector<bond::blob>::vector<bond::blob>(std::allocator<bond::blob> const &)
0x18001f413  nop
0x18001f414  cmp     r8d, 80000000h
0x18001f41b  jz      short loc_18001F489
0x18001f41d  test    r8d, r8d
0x18001f420  jz      short loc_18001F46F
0x18001f422  cmp     r8d, 1
0x18001f426  jz      short loc_18001F46F
0x18001f428  cmp     r8d, 2
0x18001f42c  jz      short loc_18001F46F
0x18001f42e  cmp     r8d, 7FFFFFFFh
0x18001f435  jnz     short loc_18001F4B1
0x18001f437  mov     rdi, cs:qword_180052A48
0x18001f43e  mov     rbx, [rdi]
0x18001f441  cmp     rbx, rdi
0x18001f444  jz      short loc_18001F4B1
0x18001f446  lea     r8, [rbx+18h]
0x18001f44a  mov     rdx, qword ptr [rbp+var_20+8]
0x18001f44e  cmp     rdx, [rbp+var_10]
0x18001f452  jz      short loc_18001F461
0x18001f454  mov     rax, [r8]
0x18001f457  mov     [rdx], rax
0x18001f45a  add     qword ptr [rbp+var_20+8], 8
0x18001f45f  jmp     short loc_18001F46A
0x18001f461  lea     rcx, [rbp+var_20]
0x18001f465  call    ??$_Emplace_reallocate@AEBQEBG@?$vector@PEBGV?$allocator@PEBG@std@@@std@@AEAAPEAPEBGQEAPEBGAEBQEBG@Z; std::vector<ushort const *>::_Emplace_reallocate<ushort const * const &>(ushort const * * const,ushort const * const &)
0x18001f46a  mov     rbx, [rbx]
0x18001f46d  jmp     short loc_18001F441
0x18001f46f  mov     [rbp+arg_10], 0
0x18001f477  lea     rdx, [rbp+arg_0]
0x18001f47b  call    ?at@?$unordered_map@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@PEBGU?$hash@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@@std@@U?$equal_to@W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@@6@V?$allocator@U?$pair@$$CBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@PEBG@std@@@6@@std@@QEBAAEBQEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@@Z; std::unordered_map<Windows::Internal::WiFiCloudStore::ProfileGeneration,ushort const *>::at(Windows::Internal::WiFiCloudStore::ProfileGeneration const &)
0x18001f480  mov     rcx, [rax]
0x18001f483  mov     [rbp+arg_10], rcx
0x18001f487  jmp     short loc_18001F494
0x18001f489  mov     rax, cs:?c_wiFiCloudStoreDataReferenceDefaultCollectionName@@3PEBGEB; ushort const * const c_wiFiCloudStoreDataReferenceDefaultCollectionName
0x18001f490  mov     [rbp+arg_10], rax
0x18001f494  lea     rax, [rbp+arg_10]
0x18001f498  mov     [rbp+var_30], rax
0x18001f49c  lea     rax, [rbp+arg_18]
0x18001f4a0  mov     [rbp+var_28], rax
0x18001f4a4  lea     rdx, [rbp+var_30]
0x18001f4a8  lea     rcx, [rbp+var_20]
0x18001f4ac  call    ??4?$vector@PEBGV?$allocator@PEBG@std@@@std@@QEAAAEAV01@V?$initializer_list@PEBG@1@@Z; std::vector<ushort const *>::operator=(std::initializer_list<ushort const *>)
0x18001f4b1  mov     rbx, qword ptr [rbp+var_20]
0x18001f4b5  mov     rdi, qword ptr [rbp+var_20+8]
0x18001f4b9  cmp     rbx, rdi
0x18001f4bc  jz      short loc_18001F4EB
0x18001f4be  mov     rax, [rbx]
0x18001f4c1  mov     [rbp+arg_10], rax
0x18001f4c5  mov     rcx, [rsi+38h]
0x18001f4c9  test    rcx, rcx
0x18001f4cc  jz      short loc_18001F546
0x18001f4ce  mov     rax, [rcx]
0x18001f4d1  lea     rdx, [rbp+arg_10]
0x18001f4d5  mov     rax, [rax+10h]
0x18001f4d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f4de  add     rbx, 8
0x18001f4e2  cmp     rbx, rdi
0x18001f4e5  jnz     short loc_18001F4BE
0x18001f4e7  mov     rbx, qword ptr [rbp+var_20]
0x18001f4eb  test    rbx, rbx
0x18001f4ee  jz      short loc_18001F513
0x18001f4f0  mov     rdx, [rbp+var_10]
0x18001f4f4  sub     rdx, rbx
0x18001f4f7  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18001f4fb  mov     rcx, rbx
0x18001f4fe  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001f503  xorps   xmm0, xmm0
0x18001f506  movdqu  [rbp+var_20], xmm0
0x18001f50b  mov     [rbp+var_10], 0
0x18001f513  mov     rcx, [rsi+38h]
0x18001f517  test    rcx, rcx
0x18001f51a  jz      short loc_18001F536
0x18001f51c  mov     rax, [rcx]
0x18001f51f  cmp     rcx, rsi
0x18001f522  setnz   dl
0x18001f525  mov     rax, [rax+20h]
0x18001f529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f52e  mov     qword ptr [rsi+38h], 0
0x18001f536  mov     rbx, [rsp+50h+arg_18]
0x18001f53e  add     rsp, 50h
0x18001f542  pop     rdi
0x18001f543  pop     rsi
0x18001f544  pop     rbp
0x18001f545  retn
0x18001f546  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18001f54c  nop
```
