# CModule::SDKLoadLibraryW(ushort const *,CModule::CheckLibraryPath)

- ea: `0x18007ec90`
- end: `0x18007ef4e`
- name: `?SDKLoadLibraryW@CModule@@AEAAPEAUHINSTANCE__@@PEBGW4CheckLibraryPath@1@@Z`
- size: `702`
- prototype: `HINSTANCE __high(const unsigned __int16 *, enum CModule::CheckLibraryPath)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18007eb04`

## callees

- `0x180004a20`
- `0x18000bb58`
- `0x18007ec90`
- `0x1800b57f8`
- `0x1800bc088`
- `0x1800bc094`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007edba`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007ee3f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007eeca`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007edba`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007ee3f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007eeca`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
HMODULE __fastcall CModule::SDKLoadLibraryW(__int64 a1, _WORD *a2, int a3)
{
  HMODULE Library; // rsi
  __int64 v6; // r15
  __int64 v7; // rax
  unsigned __int64 v8; // rbx
  char *v9; // r12
  unsigned __int64 v10; // rcx
  char *v11; // rax
  size_t v12; // rbx
  unsigned int v13; // ecx
  __int64 v14; // rbx
  unsigned int v16; // ecx
  __int64 v17; // rbx
  unsigned int v18; // ecx
  __int64 v19; // rbx
  void *v20[2]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v21; // [rsp+30h] [rbp-38h]

  Library = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SGuid const,ApprovedMetaCommands::MetaCommandSupport>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SGuid const,ApprovedMetaCommands::MetaCommandSupport>>>>>>(v20);
  v7 = *(unsigned int *)(a1 + 836);
  if ( (unsigned int)v7 <= 1 )
    goto LABEL_28;
  v8 = v6 + v7 + 1;
  v9 = (char *)v20[1];
  v10 = ((char *)v20[1] - (char *)v20[0]) >> 1;
  if ( v8 < v10 )
  {
    v11 = (char *)v20[0] + 2 * v8;
LABEL_10:
    v20[1] = v11;
    goto LABEL_11;
  }
  if ( v8 > v10 )
  {
    if ( v8 <= (signed __int64)(v21 - (unsigned __int64)v20[0]) >> 1 )
    {
      v12 = 2 * (v8 - v10);
      memset_0(v20[1], 0, v12);
      v11 = &v9[v12];
      goto LABEL_10;
    }
    std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(v20, v8);
  }
LABEL_11:
  memmove_0((char *)v20[0] + 2 * *(unsigned int *)(a1 + 836) - 2, a2, 2 * v6 + 2);
  if ( !a3 )
  {
    v13 = *(_DWORD *)(a1 + 824);
    if ( v13 > 1 )
    {
      v14 = *(_DWORD *)(a1 + 836) - v13;
      memmove_0((char *)v20[0] + 2 * v14, *(const void **)(a1 + 800), 2LL * (v13 - 1));
      Library = LoadLibraryExW((LPCWSTR)v20[0] + v14, 0, 0);
      if ( Library )
      {
        if ( v20[0] )
        {
          std::_Deallocate<16>(v20[0], 2 * ((signed __int64)(v21 - (unsigned __int64)v20[0]) >> 1));
          *(_OWORD *)v20 = 0;
          v21 = 0;
        }
        return Library;
      }
    }
  }
  v16 = *(_DWORD *)(a1 + 828);
  if ( v16 > 1 )
  {
    v17 = *(_DWORD *)(a1 + 836) - v16;
    memmove_0((char *)v20[0] + 2 * v17, *(const void **)(a1 + 808), 2LL * (v16 - 1));
    Library = LoadLibraryExW((LPCWSTR)v20[0] + v17, 0, 0);
    if ( Library || a3 == 2 )
    {
      if ( v20[0] )
      {
        std::_Deallocate<16>(v20[0], 2 * ((signed __int64)(v21 - (unsigned __int64)v20[0]) >> 1));
        *(_OWORD *)v20 = 0;
        v21 = 0;
      }
      return Library;
    }
  }
  v18 = *(_DWORD *)(a1 + 832);
  if ( v18 > 1 )
  {
    v19 = *(_DWORD *)(a1 + 836) - v18;
    memmove_0((char *)v20[0] + 2 * v19, *(const void **)(a1 + 816), 2LL * (v18 - 1));
    Library = LoadLibraryExW((LPCWSTR)v20[0] + v19, 0, 0);
    if ( Library )
    {
      if ( v20[0] )
      {
        std::_Deallocate<16>(v20[0], 2 * ((signed __int64)(v21 - (unsigned __int64)v20[0]) >> 1));
        *(_OWORD *)v20 = 0;
        v21 = 0;
      }
      return Library;
    }
  }
LABEL_28:
  if ( v20[0] )
    std::_Deallocate<16>(v20[0], 2 * ((signed __int64)(v21 - (unsigned __int64)v20[0]) >> 1));
  return Library;
}

```

## disassembly

```asm
0x18007ec90  mov     [rsp+arg_8], rbx
0x18007ec95  mov     [rsp+arg_18], rsi
0x18007ec9a  mov     [rsp+arg_10], r8d
0x18007ec9f  push    rdi
0x18007eca0  push    r12
0x18007eca2  push    r13
0x18007eca4  push    r14
0x18007eca6  push    r15
0x18007eca8  sub     rsp, 40h
0x18007ecac  mov     r13, rdx
0x18007ecaf  mov     r14, rcx
0x18007ecb2  xor     edi, edi
0x18007ecb4  mov     esi, edi
0x18007ecb6  mov     [rsp+68h+arg_0], rdi
0x18007ecbb  or      r15, 0FFFFFFFFFFFFFFFFh
0x18007ecbf  inc     r15
0x18007ecc2  cmp     [rdx+r15*2], di
0x18007ecc7  jnz     short loc_18007ECBF
0x18007ecc9  lea     rcx, [rsp+68h+var_48]; void *
0x18007ecce  call    ??$?0AEBV?$allocator@U?$pair@$$CBUSGuid@@UMetaCommandSupport@ApprovedMetaCommands@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUSGuid@@UMetaCommandSupport@ApprovedMetaCommands@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBUSGuid@@UMetaCommandSupport@ApprovedMetaCommands@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SGuid const,ApprovedMetaCommands::MetaCommandSupport>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<SGuid const,ApprovedMetaCommands::MetaCommandSupport>>>>>>(std::allocator<std::pair<SGuid const,ApprovedMetaCommands::MetaCommandSupport>> const &)
0x18007ecd3  nop
0x18007ecd4  mov     eax, [r14+344h]
0x18007ecdb  cmp     eax, 1
0x18007ecde  jbe     loc_18007EF14
0x18007ece4  lea     rbx, [rax+1]
0x18007ece8  add     rbx, r15
0x18007eceb  mov     rdx, [rsp+68h+var_48]
0x18007ecf0  mov     r12, [rsp+68h+var_48+8]
0x18007ecf5  mov     rcx, r12
0x18007ecf8  sub     rcx, rdx
0x18007ecfb  sar     rcx, 1
0x18007ecfe  cmp     rbx, rcx
0x18007ed01  jnb     short loc_18007ED09
0x18007ed03  lea     rax, [rdx+rbx*2]
0x18007ed07  jmp     short loc_18007ED41
0x18007ed09  jbe     short loc_18007ED46
0x18007ed0b  mov     rax, [rsp+68h+var_38]
0x18007ed10  sub     rax, rdx
0x18007ed13  sar     rax, 1
0x18007ed16  cmp     rbx, rax
0x18007ed19  jbe     short loc_18007ED2A
0x18007ed1b  mov     rdx, rbx
0x18007ed1e  lea     rcx, [rsp+68h+var_48]
0x18007ed23  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18007ed28  jmp     short loc_18007ED46
0x18007ed2a  sub     rbx, rcx
0x18007ed2d  add     rbx, rbx
0x18007ed30  mov     r8, rbx; Size
0x18007ed33  xor     edx, edx; Val
0x18007ed35  mov     rcx, r12; void *
0x18007ed38  call    memset_0
0x18007ed3d  lea     rax, [rbx+r12]
0x18007ed41  mov     [rsp+68h+var_48+8], rax
0x18007ed46  lea     r8, ds:2[r15*2]; Size
0x18007ed4e  mov     ecx, [r14+344h]
0x18007ed55  mov     rax, [rsp+68h+var_48]
0x18007ed5a  sub     rax, 2
0x18007ed5e  lea     rcx, [rax+rcx*2]; void *
0x18007ed62  mov     rdx, r13; Src
0x18007ed65  call    memmove_0
0x18007ed6a  mov     r15d, [rsp+68h+arg_10]
0x18007ed72  test    r15d, r15d
0x18007ed75  jnz     loc_18007EE00
0x18007ed7b  mov     ecx, [r14+338h]
0x18007ed82  cmp     ecx, 1
0x18007ed85  jbe     short loc_18007EE00
0x18007ed87  mov     ebx, [r14+344h]
0x18007ed8e  sub     ebx, ecx
0x18007ed90  lea     r8d, [rcx-1]
0x18007ed94  add     r8, r8; Size
0x18007ed97  mov     rax, [rsp+68h+var_48]
0x18007ed9c  lea     rcx, [rax+rbx*2]; void *
0x18007eda0  mov     rdx, [r14+320h]; Src
0x18007eda7  call    memmove_0
0x18007edac  mov     rax, [rsp+68h+var_48]
0x18007edb1  lea     rcx, [rax+rbx*2]; lpLibFileName
0x18007edb5  xor     r8d, r8d; dwFlags
0x18007edb8  xor     edx, edx; hFile
0x18007edba  call    cs:__imp_LoadLibraryExW
0x18007edc0  mov     rsi, rax
0x18007edc3  mov     [rsp+68h+arg_0], rax
0x18007edc8  test    rax, rax
0x18007edcb  jz      short loc_18007EE00
0x18007edcd  mov     rcx, [rsp+68h+var_48]
0x18007edd2  test    rcx, rcx
0x18007edd5  jz      short loc_18007EDF8
0x18007edd7  mov     rdx, [rsp+68h+var_38]
0x18007eddc  sub     rdx, rcx
0x18007eddf  sar     rdx, 1
0x18007ede2  add     rdx, rdx
0x18007ede5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18007edea  xorps   xmm0, xmm0
0x18007eded  movdqu  xmmword ptr [rsp+68h+var_48], xmm0
0x18007edf3  mov     [rsp+68h+var_38], rdi
0x18007edf8  mov     rax, rsi
0x18007edfb  jmp     loc_18007EF34
0x18007ee00  mov     ecx, [r14+33Ch]
0x18007ee07  cmp     ecx, 1
0x18007ee0a  jbe     short loc_18007EE8B
0x18007ee0c  mov     ebx, [r14+344h]
0x18007ee13  sub     ebx, ecx
0x18007ee15  lea     r8d, [rcx-1]
0x18007ee19  add     r8, r8; Size
0x18007ee1c  mov     rax, [rsp+68h+var_48]
0x18007ee21  lea     rcx, [rax+rbx*2]; void *
0x18007ee25  mov     rdx, [r14+328h]; Src
0x18007ee2c  call    memmove_0
0x18007ee31  mov     rax, [rsp+68h+var_48]
0x18007ee36  lea     rcx, [rax+rbx*2]; lpLibFileName
0x18007ee3a  xor     r8d, r8d; dwFlags
0x18007ee3d  xor     edx, edx; hFile
0x18007ee3f  call    cs:__imp_LoadLibraryExW
0x18007ee45  mov     rsi, rax
0x18007ee48  mov     [rsp+68h+arg_0], rax
0x18007ee4d  test    rax, rax
0x18007ee50  jnz     short loc_18007EE58
0x18007ee52  cmp     r15d, 2
0x18007ee56  jnz     short loc_18007EE8B
0x18007ee58  mov     rcx, [rsp+68h+var_48]
0x18007ee5d  test    rcx, rcx
0x18007ee60  jz      short loc_18007EE83
0x18007ee62  mov     rdx, [rsp+68h+var_38]
0x18007ee67  sub     rdx, rcx
0x18007ee6a  sar     rdx, 1
0x18007ee6d  add     rdx, rdx
0x18007ee70  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18007ee75  xorps   xmm0, xmm0
0x18007ee78  movdqu  xmmword ptr [rsp+68h+var_48], xmm0
0x18007ee7e  mov     [rsp+68h+var_38], rdi
0x18007ee83  mov     rax, rsi
0x18007ee86  jmp     loc_18007EF34
0x18007ee8b  mov     ecx, [r14+340h]
0x18007ee92  cmp     ecx, 1
0x18007ee95  jbe     short loc_18007EF0D
0x18007ee97  mov     ebx, [r14+344h]
0x18007ee9e  sub     ebx, ecx
0x18007eea0  lea     r8d, [rcx-1]
0x18007eea4  add     r8, r8; Size
0x18007eea7  mov     rax, [rsp+68h+var_48]
0x18007eeac  lea     rcx, [rax+rbx*2]; void *
0x18007eeb0  mov     rdx, [r14+330h]; Src
0x18007eeb7  call    memmove_0
0x18007eebc  mov     rax, [rsp+68h+var_48]
0x18007eec1  lea     rcx, [rax+rbx*2]; lpLibFileName
0x18007eec5  xor     r8d, r8d; dwFlags
0x18007eec8  xor     edx, edx; hFile
0x18007eeca  call    cs:__imp_LoadLibraryExW
0x18007eed0  mov     rsi, rax
0x18007eed3  mov     [rsp+68h+arg_0], rax
0x18007eed8  test    rax, rax
0x18007eedb  jz      short loc_18007EF0D
0x18007eedd  mov     rcx, [rsp+68h+var_48]
0x18007eee2  test    rcx, rcx
0x18007eee5  jz      short loc_18007EF08
0x18007eee7  mov     rdx, [rsp+68h+var_38]
0x18007eeec  sub     rdx, rcx
0x18007eeef  sar     rdx, 1
0x18007eef2  add     rdx, rdx
0x18007eef5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18007eefa  xorps   xmm0, xmm0
0x18007eefd  movdqu  xmmword ptr [rsp+68h+var_48], xmm0
0x18007ef03  mov     [rsp+68h+var_38], rdi
0x18007ef08  mov     rax, rsi
0x18007ef0b  jmp     short loc_18007EF34
0x18007ef0d  jmp     short loc_18007EF14
0x18007ef0f  mov     rsi, [rsp+68h+arg_0]
0x18007ef14  mov     rcx, [rsp+68h+var_48]
0x18007ef19  test    rcx, rcx
0x18007ef1c  jz      short loc_18007EF31
0x18007ef1e  mov     rdx, [rsp+68h+var_38]
0x18007ef23  sub     rdx, rcx
0x18007ef26  sar     rdx, 1
0x18007ef29  add     rdx, rdx
0x18007ef2c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18007ef31  mov     rax, rsi
0x18007ef34  lea     r11, [rsp+68h+var_28]
0x18007ef39  mov     rbx, [r11+38h]
0x18007ef3d  mov     rsi, [r11+48h]
0x18007ef41  mov     rsp, r11
0x18007ef44  pop     r15
0x18007ef46  pop     r14
0x18007ef48  pop     r13
0x18007ef4a  pop     r12
0x18007ef4c  pop     rdi
0x18007ef4d  retn
```
