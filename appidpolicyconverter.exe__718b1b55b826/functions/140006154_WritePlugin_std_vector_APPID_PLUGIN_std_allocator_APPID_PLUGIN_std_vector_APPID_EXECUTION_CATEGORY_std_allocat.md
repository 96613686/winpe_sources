# WritePlugin(std::vector<APPID_PLUGIN_,std::allocator<APPID_PLUGIN_>> &,std::vector<APPID_EXECUTION_CATEGORY_,std::allocator<APPID_EXECUTION_CATEGORY_>> const &,std::vector<_GUID,std::allocator<_GUID>> const &,std::vector<std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>,std::allocator<std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>>> const &)

- ea: `0x140006154`
- end: `0x1400064f0`
- name: `?WritePlugin@@YAKAEAV?$vector@UAPPID_PLUGIN_@@V?$allocator@UAPPID_PLUGIN_@@@std@@@std@@AEBV?$vector@UAPPID_EXECUTION_CATEGORY_@@V?$allocator@UAPPID_EXECUTION_CATEGORY_@@@std@@@2@AEBV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@2@AEBV?$vector@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@V?$allocator@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@@2@@2@@Z`
- size: `924`
- prototype: `__int64 __fastcall(const void **, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x1400037c8`

## callees

- `0x140005634`
- `0x140006000`
- `0x140006154`
- `0x140006858`
- `0x140006fd8`
- `0x140007010`
- `0x140008d30`
- `0x140008ef4`
- `0x140013ab7`
- `0x140013acf`
- `0x140013b10`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140006226`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140006498`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400064c0`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140006226`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140006498`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400064c0`

## string_xrefs

- `0x1400061d1`: `Plugin.Config`

## pseudocode

```c
__int64 __fastcall WritePlugin(const void **a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  DWORD FilePathsAndHandle; // edi
  _DWORD *v9; // r8
  DWORD v10; // r15d
  unsigned int v11; // r9d
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rcx
  unsigned int *v16; // rax
  unsigned int *v17; // rsi
  unsigned int v18; // ecx
  unsigned int *v19; // rcx
  unsigned int v20; // edi
  unsigned int v21; // r12d
  __int64 v22; // r9
  __int64 v23; // rbx
  unsigned int v24; // ebx
  DWORD v26; // [rsp+30h] [rbp-D0h]
  HANDLE *v27; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR lpFileName; // [rsp+40h] [rbp-C0h] BYREF
  void *v29; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int *v30; // [rsp+50h] [rbp-B0h]
  unsigned __int16 v31[261]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR v32[264]; // [rsp+270h] [rbp+170h] BYREF

  memset_0(v32, 0, 0x20Au);
  memset_0(v31, 0, sizeof(v31));
  v29 = (void *)-1LL;
  v30 = 0;
  lpFileName = 0;
  v27 = 0;
  FilePathsAndHandle = GetFilePathsAndHandle(v32, (unsigned __int16 (*)[261])v31, L"Plugin.Config", &v29);
  std::unique_ptr<void *,release::Deleter<release::handle_tag>>::reset(&v27, &v29);
  std::unique_ptr<unsigned short,release::Deleter<release::delete_file_tag>>::reset(&lpFileName, v31);
  if ( FilePathsAndHandle )
  {
    std::unique_ptr<void *,release::Deleter<release::handle_tag>>::_Delete(&v27);
    if ( lpFileName )
      DeleteFileW(lpFileName);
    return FilePathsAndHandle;
  }
  v9 = *a1;
  v10 = 4 * ((__int64)(*(_QWORD *)(a2 + 8) - *(_QWORD *)a2) >> 2)
      + 16 * (((__int64)(*(_QWORD *)(a3 + 8) - *(_QWORD *)a3) >> 4) + 2)
      + 4 * (((_BYTE *)a1[1] - (_BYTE *)*a1) >> 2);
  v26 = v10;
  if ( 0x8E38E38E38E38E39uLL * (((_BYTE *)a1[1] - (_BYTE *)*a1) >> 2) )
  {
    v11 = 0;
    v12 = 0;
    do
    {
      v13 = 9 * v12;
      v9[9 * v12 + 5] = v10;
      v14 = *(_QWORD *)(*a4 + 8 * v12);
      v15 = -1;
      do
        ++v15;
      while ( *(_WORD *)(v14 + 2 * v15) );
      *((_DWORD *)*a1 + v13 + 6) = 2 * v15;
      v9 = *a1;
      v10 += *((_DWORD *)*a1 + v13 + 6);
      v12 = ++v11;
    }
    while ( v11 < 0x8E38E38E38E38E39uLL * (((_BYTE *)a1[1] - (_BYTE *)*a1) >> 2) );
    v26 = v10;
  }
  v16 = (unsigned int *)AiAlloc(v10);
  v17 = v16;
  if ( !v16 )
  {
    std::unique_ptr<void *,release::Deleter<release::handle_tag>>::_Delete(&v27);
    if ( lpFileName )
      DeleteFileW(lpFileName);
    return 14;
  }
  v30 = v16;
  *v16 = 1179414593;
  v16[1] = 1;
  v16[2] = 32;
  v16[3] = 954437177 * (((_BYTE *)a1[1] - (_BYTE *)*a1) >> 2);
  v18 = 4 * (((_BYTE *)a1[1] - (_BYTE *)*a1) >> 2) + 32;
  v16[4] = v18;
  v16[5] = -1227133513 * ((__int64)(*(_QWORD *)(a2 + 8) - *(_QWORD *)a2) >> 2);
  v16[6] = v18 + 4 * ((__int64)(*(_QWORD *)(a2 + 8) - *(_QWORD *)a2) >> 2);
  v16[7] = (__int64)(*(_QWORD *)(a3 + 8) - *(_QWORD *)a3) >> 4;
  memcpy_0(v16 + 8, *a1, 4 * (((_BYTE *)a1[1] - (_BYTE *)*a1) >> 2));
  memcpy_0((char *)v17 + v17[4], *(const void **)a2, 4 * ((__int64)(*(_QWORD *)(a2 + 8) - *(_QWORD *)a2) >> 2));
  memcpy_0((char *)v17 + v17[6], *(const void **)a3, (*(_QWORD *)(a3 + 8) - *(_QWORD *)a3) & 0xFFFFFFFFFFFFFFF0uLL);
  v19 = (unsigned int *)*a1;
  if ( 0x8E38E38E38E38E39uLL * (((_BYTE *)a1[1] - (_BYTE *)*a1) >> 2) )
  {
    v20 = v17[6] + ((*(_DWORD *)(a3 + 8) - *(_DWORD *)a3) & 0xFFFFFFF0);
    v21 = 0;
    v22 = 0;
    do
    {
      v23 = 9 * v22;
      memcpy_0((char *)v17 + v20, *(const void **)(*a4 + 8 * v22), v19[9 * v22 + 6]);
      v19 = (unsigned int *)*a1;
      v20 += *((_DWORD *)*a1 + v23 + 6);
      v22 = ++v21;
    }
    while ( v21 < 0x8E38E38E38E38E39uLL * (((_BYTE *)a1[1] - (_BYTE *)*a1) >> 2) );
    v10 = v26;
  }
  v24 = WriteAndReplaceFile(&v27, &lpFileName, v32, v17, v10);
  std::unique_ptr<void *,release::Deleter<release::handle_tag>>::_Delete(&v27);
  if ( lpFileName )
    DeleteFileW(lpFileName);
  AiFree(v17);
  return v24;
}

```

## disassembly

```asm
0x140006154  push    rbp
0x140006156  push    rbx
0x140006157  push    rsi
0x140006158  push    rdi
0x140006159  push    r12
0x14000615b  push    r13
0x14000615d  push    r14
0x14000615f  push    r15
0x140006161  lea     rbp, [rsp-398h]
0x140006169  sub     rsp, 498h
0x140006170  mov     rax, cs:__security_cookie
0x140006177  xor     rax, rsp
0x14000617a  mov     [rbp+3D0h+var_50], rax
0x140006181  mov     r13, r9
0x140006184  mov     rbx, r8
0x140006187  mov     r12, rdx
0x14000618a  mov     r14, rcx
0x14000618d  mov     edi, 20Ah
0x140006192  mov     r8d, edi; Size
0x140006195  xor     edx, edx; Val
0x140006197  lea     rcx, [rbp+3D0h+var_260]; void *
0x14000619e  call    memset_0
0x1400061a3  mov     r8d, edi; Size
0x1400061a6  xor     edx, edx; Val
0x1400061a8  lea     rcx, [rsp+4D0h+var_470]; void *
0x1400061ad  call    memset_0
0x1400061b2  mov     [rsp+4D0h+var_488], 0FFFFFFFFFFFFFFFFh
0x1400061bb  xor     esi, esi
0x1400061bd  mov     [rsp+4D0h+var_480], rsi
0x1400061c2  mov     [rsp+4D0h+lpFileName], rsi
0x1400061c7  mov     [rsp+4D0h+var_498], rsi
0x1400061cc  lea     r9, [rsp+4D0h+var_488]; void **
0x1400061d1  lea     r8, aPluginConfig; "Plugin.Config"
0x1400061d8  lea     rdx, [rsp+4D0h+var_470]; unsigned __int16 (*)[261]
0x1400061dd  lea     rcx, [rbp+3D0h+var_260]; unsigned __int16 (*)[261]
0x1400061e4  call    ?GetFilePathsAndHandle@@YAKAEAY0BAF@G0PEBGPEAPEAX@Z; GetFilePathsAndHandle(ushort (&)[261],ushort (&)[261],ushort const *,void * *)
0x1400061e9  mov     edi, eax
0x1400061eb  lea     rdx, [rsp+4D0h+var_488]
0x1400061f0  lea     rcx, [rsp+4D0h+var_498]
0x1400061f5  call    ?reset@?$unique_ptr@PEAXU?$Deleter@Uhandle_tag@release@@@release@@@std@@QEAAXPEAPEAX@Z; std::unique_ptr<void *,release::Deleter<release::handle_tag>>::reset(void * *)
0x1400061fa  lea     rdx, [rsp+4D0h+var_470]
0x1400061ff  lea     rcx, [rsp+4D0h+lpFileName]
0x140006204  call    ?reset@?$unique_ptr@GU?$Deleter@Udelete_file_tag@release@@@release@@@std@@QEAAXPEAG@Z; std::unique_ptr<ushort,release::Deleter<release::delete_file_tag>>::reset(ushort *)
0x140006209  test    edi, edi
0x14000620b  jz      short loc_140006231
0x14000620d  lea     rcx, [rsp+4D0h+var_498]
0x140006212  call    ?_Delete@?$unique_ptr@PEAXU?$Deleter@Uhandle_tag@release@@@release@@@std@@AEAAXXZ; std::unique_ptr<void *,release::Deleter<release::handle_tag>>::_Delete(void)
0x140006217  nop
0x140006218  mov     rcx, [rsp+4D0h+lpFileName]; lpFileName
0x14000621d  test    rcx, rcx
0x140006220  jz      loc_1400064CB
0x140006226  call    cs:__imp_DeleteFileW
0x14000622c  jmp     loc_1400064CB
0x140006231  mov     r8, [r14]
0x140006234  mov     rdx, [r14+8]
0x140006238  sub     rdx, r8
0x14000623b  sar     rdx, 2
0x14000623f  mov     rdi, 8E38E38E38E38E39h
0x140006249  imul    rdx, rdi
0x14000624d  mov     rcx, [rbx+8]
0x140006251  sub     rcx, [rbx]
0x140006254  sar     rcx, 4
0x140006258  add     ecx, 2
0x14000625b  shl     ecx, 4
0x14000625e  mov     rax, [r12+8]
0x140006263  sub     rax, [r12]
0x140006267  sar     rax, 2
0x14000626b  mov     r9, 6DB6DB6DB6DB6DB7h
0x140006275  imul    rax, r9
0x140006279  imul    eax, 1Ch
0x14000627c  add     ecx, eax
0x14000627e  lea     eax, [rdx+rdx*8]
0x140006281  lea     r15d, [rcx+rax*4]
0x140006285  mov     [rsp+4D0h+var_4A0], r15d
0x14000628a  test    rdx, rdx
0x14000628d  jz      short loc_1400062E4
0x14000628f  mov     r9d, esi
0x140006292  mov     rcx, rsi
0x140006295  lea     rdx, [rcx+rcx*8]
0x140006299  mov     [r8+rdx*4+14h], r15d
0x14000629e  mov     rax, [r13+0]
0x1400062a2  mov     r8, [rax+rcx*8]
0x1400062a6  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400062aa  inc     rcx
0x1400062ad  cmp     [r8+rcx*2], si
0x1400062b2  jnz     short loc_1400062AA
0x1400062b4  add     ecx, ecx
0x1400062b6  mov     rax, [r14]
0x1400062b9  mov     [rax+rdx*4+18h], ecx
0x1400062bd  mov     r8, [r14]
0x1400062c0  add     r15d, [r8+rdx*4+18h]
0x1400062c5  inc     r9d
0x1400062c8  mov     ecx, r9d
0x1400062cb  mov     rax, [r14+8]
0x1400062cf  sub     rax, r8
0x1400062d2  sar     rax, 2
0x1400062d6  imul    rax, rdi
0x1400062da  cmp     rcx, rax
0x1400062dd  jb      short loc_140006295
0x1400062df  mov     [rsp+4D0h+var_4A0], r15d
0x1400062e4  mov     ecx, r15d
0x1400062e7  call    AiAlloc
0x1400062ec  mov     rsi, rax
0x1400062ef  test    rax, rax
0x1400062f2  jz      loc_1400064AB
0x1400062f8  mov     [rsp+4D0h+var_480], rax
0x1400062fd  mov     dword ptr [rax], 464C7041h
0x140006303  mov     dword ptr [rax+4], 1
0x14000630a  mov     dword ptr [rax+8], 20h ; ' '
0x140006311  mov     rcx, [r14+8]
0x140006315  sub     rcx, [r14]
0x140006318  sar     rcx, 2
0x14000631c  imul    rcx, rdi
0x140006320  mov     [rax+0Ch], ecx
0x140006323  mov     rax, [r14+8]
0x140006327  sub     rax, [r14]
0x14000632a  sar     rax, 2
0x14000632e  imul    rax, rdi
0x140006332  lea     eax, [rax+rax*8]
0x140006335  lea     ecx, ds:20h[rax*4]
0x14000633c  mov     [rsi+10h], ecx
0x14000633f  mov     rax, [r12+8]
0x140006344  sub     rax, [r12]
0x140006348  sar     rax, 2
0x14000634c  mov     rdx, 6DB6DB6DB6DB6DB7h
0x140006356  imul    rax, rdx
0x14000635a  mov     [rsi+14h], eax
0x14000635d  mov     rax, [r12+8]
0x140006362  sub     rax, [r12]
0x140006366  sar     rax, 2
0x14000636a  imul    rax, rdx
0x14000636e  imul    eax, 1Ch
0x140006371  add     eax, ecx
0x140006373  mov     [rsi+18h], eax
0x140006376  mov     rax, [rbx+8]
0x14000637a  sub     rax, [rbx]
0x14000637d  sar     rax, 4
0x140006381  mov     [rsi+1Ch], eax
0x140006384  mov     rax, [r14+8]
0x140006388  sub     rax, [r14]
0x14000638b  sar     rax, 2
0x14000638f  imul    rax, rdi
0x140006393  lea     r8, [rax+rax*8]
0x140006397  shl     r8, 2; Size
0x14000639b  lea     rcx, [rsi+20h]; void *
0x14000639f  mov     rdx, [r14]; Src
0x1400063a2  call    memcpy_0
0x1400063a7  mov     rax, [r12+8]
0x1400063ac  sub     rax, [r12]
0x1400063b0  sar     rax, 2
0x1400063b4  mov     rcx, 6DB6DB6DB6DB6DB7h
0x1400063be  imul    rax, rcx
0x1400063c2  imul    r8, rax, 1Ch; Size
0x1400063c6  mov     ecx, [rsi+10h]
0x1400063c9  add     rcx, rsi; void *
0x1400063cc  mov     rdx, [r12]; Src
0x1400063d0  call    memcpy_0
0x1400063d5  mov     r8, [rbx+8]
0x1400063d9  sub     r8, [rbx]
0x1400063dc  and     r8, 0FFFFFFFFFFFFFFF0h; Size
0x1400063e0  mov     ecx, [rsi+18h]
0x1400063e3  add     rcx, rsi; void *
0x1400063e6  mov     rdx, [rbx]; Src
0x1400063e9  call    memcpy_0
0x1400063ee  mov     rcx, [r14]
0x1400063f1  mov     rax, [r14+8]
0x1400063f5  sub     rax, rcx
0x1400063f8  sar     rax, 2
0x1400063fc  imul    rax, rdi
0x140006400  test    rax, rax
0x140006403  jz      short loc_140006463
0x140006405  mov     rdi, [rbx+8]
0x140006409  sub     rdi, [rbx]
0x14000640c  and     edi, 0FFFFFFF0h
0x14000640f  add     edi, [rsi+18h]
0x140006412  xor     r12d, r12d
0x140006415  xor     r9d, r9d
0x140006418  mov     r15, 8E38E38E38E38E39h
0x140006422  lea     rbx, [r9+r9*8]
0x140006426  mov     r8d, [rcx+rbx*4+18h]; Size
0x14000642b  mov     rdx, [r13+0]
0x14000642f  mov     ecx, edi
0x140006431  add     rcx, rsi; void *
0x140006434  mov     rdx, [rdx+r9*8]; Src
0x140006438  call    memcpy_0
0x14000643d  mov     rcx, [r14]
0x140006440  add     edi, [rcx+rbx*4+18h]
0x140006444  inc     r12d
0x140006447  mov     r9d, r12d
0x14000644a  mov     rax, [r14+8]
0x14000644e  sub     rax, rcx
0x140006451  sar     rax, 2
0x140006455  imul    rax, r15
0x140006459  cmp     r9, rax
0x14000645c  jb      short loc_140006422
0x14000645e  mov     r15d, [rsp+4D0h+var_4A0]
0x140006463  mov     [rsp+4D0h+var_4B0], r15d
0x140006468  mov     r9, rsi
0x14000646b  lea     r8, [rbp+3D0h+var_260]
0x140006472  lea     rdx, [rsp+4D0h+lpFileName]
0x140006477  lea     rcx, [rsp+4D0h+var_498]
0x14000647c  call    ?WriteAndReplaceFile@@YAKAEAV?$unique_ptr@PEAXU?$Deleter@Uhandle_tag@release@@@release@@@std@@AEAV?$unique_ptr@GU?$Deleter@Udelete_file_tag@release@@@release@@@2@AEAY0BAF@$$CBGPEBXK@Z; WriteAndReplaceFile(std::unique_ptr<void *,release::Deleter<release::handle_tag>> &,std::unique_ptr<ushort,release::Deleter<release::delete_file_tag>> &,ushort const (&)[261],void const *,ulong)
0x140006481  mov     ebx, eax
0x140006483  lea     rcx, [rsp+4D0h+var_498]
0x140006488  call    ?_Delete@?$unique_ptr@PEAXU?$Deleter@Uhandle_tag@release@@@release@@@std@@AEAAXXZ; std::unique_ptr<void *,release::Deleter<release::handle_tag>>::_Delete(void)
0x14000648d  nop
0x14000648e  mov     rcx, [rsp+4D0h+lpFileName]; lpFileName
0x140006493  test    rcx, rcx
0x140006496  jz      short loc_14000649F
0x140006498  call    cs:__imp_DeleteFileW
0x14000649e  nop
0x14000649f  mov     rcx, rsi
0x1400064a2  call    AiFree
0x1400064a7  mov     eax, ebx
0x1400064a9  jmp     short loc_1400064CD
0x1400064ab  lea     rcx, [rsp+4D0h+var_498]
0x1400064b0  call    ?_Delete@?$unique_ptr@PEAXU?$Deleter@Uhandle_tag@release@@@release@@@std@@AEAAXXZ; std::unique_ptr<void *,release::Deleter<release::handle_tag>>::_Delete(void)
0x1400064b5  nop
0x1400064b6  mov     rcx, [rsp+4D0h+lpFileName]; lpFileName
0x1400064bb  test    rcx, rcx
0x1400064be  jz      short loc_1400064C6
0x1400064c0  call    cs:__imp_DeleteFileW
0x1400064c6  mov     edi, 0Eh
0x1400064cb  mov     eax, edi
0x1400064cd  mov     rcx, [rbp+3D0h+var_50]
0x1400064d4  xor     rcx, rsp; StackCookie
0x1400064d7  call    __security_check_cookie
0x1400064dc  add     rsp, 498h
0x1400064e3  pop     r15
0x1400064e5  pop     r14
0x1400064e7  pop     r13
0x1400064e9  pop     r12
0x1400064eb  pop     rdi
0x1400064ec  pop     rsi
0x1400064ed  pop     rbx
0x1400064ee  pop     rbp
0x1400064ef  retn
```
