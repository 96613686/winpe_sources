# CTreeWalker::QueryFileId(ushort const *,__int64 *)

- ea: `0x18004bd60`
- end: `0x18004bed2`
- name: `?QueryFileId@CTreeWalker@@QEAAJPEBGPEA_J@Z`
- size: `370`
- prototype: `int(CTreeWalker *__hidden this, const unsigned __int16 *, __int64 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003e090`
- `0x18004617c`

## callees

- `0x18000d030`
- `0x18001c208`
- `0x18001f634`
- `0x180028fdc`
- `0x18003fe70`
- `0x180041544`
- `0x18004b92c`
- `0x18004bd60`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004bdbf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004bdbf`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18004be04`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18004be04`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CTreeWalker::QueryFileId(CTreeWalker *this, const unsigned __int16 *a2, __int64 *a3)
{
  HANDLE v6; // rcx
  int Error; // edi
  __int64 v8; // rax
  __int64 v9; // rbx
  __int64 v10; // rax
  HANDLE hFile[2]; // [rsp+40h] [rbp-40h] BYREF
  __int128 FileInformation; // [rsp+50h] [rbp-30h] BYREF
  __int64 v14; // [rsp+60h] [rbp-20h]

  if ( *((_BYTE *)this + 314) )
  {
    hFile[0] = CreateFileW(a2, 0x80u, 3u, 0, 3u, 0x2000000u, 0);
    v6 = hFile[0];
    if ( (((unsigned __int64)hFile[0] + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      v6 = hFile[0];
    }
    if ( Error < 0 )
      goto LABEL_10;
    FileInformation = 0;
    v14 = 0;
    if ( GetFileInformationByHandleEx(v6, MaximumFileInfoByHandleClass, &FileInformation, 0x18u) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
      {
LABEL_10:
        CAutoHandle<void *>::~CAutoHandle<void *>(hFile);
        return (unsigned int)Error;
      }
    }
    *a3 = *((_QWORD *)&FileInformation + 1);
    goto LABEL_10;
  }
  Error = 0;
  v8 = std::wstring::wstring((__int64)&FileInformation, (__int64)a2);
  std::_Tree<std::_Tmap_traits<std::wstring,__int64,StringComparatorIgnoreCase,std::allocator<std::pair<std::wstring const,__int64>>,0>>::find(
    (char *)this + 264,
    hFile,
    v8);
  std::wstring::_Tidy_deallocate(&FileInformation);
  if ( hFile[0] == *((HANDLE *)this + 33) )
  {
    v9 = *((_QWORD *)this + 35);
    *((_QWORD *)this + 35) = v9 + 1;
    v10 = std::wstring::wstring((__int64)&FileInformation, (__int64)a2);
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,__int64,StringComparatorIgnoreCase,std::allocator<std::pair<std::wstring const,__int64>>>::_Try_emplace<std::wstring,>(
                             (__int64 *)this + 33,
                             (__int64)hFile,
                             v10)
              + 64LL) = v9;
    std::wstring::_Tidy_deallocate(&FileInformation);
    *a3 = v9;
  }
  else
  {
    *a3 = *((_QWORD *)hFile[0] + 8);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18004bd60  push    rbp
0x18004bd62  push    rbx
0x18004bd63  push    rsi
0x18004bd64  push    rdi
0x18004bd65  push    r12
0x18004bd67  push    r14
0x18004bd69  push    r15
0x18004bd6b  mov     rbp, rsp
0x18004bd6e  sub     rsp, 80h
0x18004bd75  mov     rax, cs:__security_cookie
0x18004bd7c  xor     rax, rsp
0x18004bd7f  mov     [rbp+var_10], rax
0x18004bd83  mov     rsi, r8
0x18004bd86  mov     r15, rdx
0x18004bd89  mov     r14, rcx
0x18004bd8c  cmp     byte ptr [rcx+13Ah], 0
0x18004bd93  jz      loc_18004BE32
0x18004bd99  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x18004bda2  mov     [rsp+80h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18004bdaa  mov     r8d, 3; dwShareMode
0x18004bdb0  mov     [rsp+80h+dwCreationDisposition], r8d; dwCreationDisposition
0x18004bdb5  xor     r9d, r9d; lpSecurityAttributes
0x18004bdb8  lea     edx, [r8+7Dh]; dwDesiredAccess
0x18004bdbc  mov     rcx, r15; lpFileName
0x18004bdbf  call    cs:__imp_CreateFileW
0x18004bdc5  mov     [rbp+hFile], rax
0x18004bdc9  mov     rcx, [rbp+hFile]; hFile
0x18004bdcd  lea     rax, [rcx+1]
0x18004bdd1  test    rax, 0FFFFFFFFFFFFFFFEh
0x18004bdd7  jnz     short loc_18004BDE6
0x18004bdd9  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18004bdde  mov     edi, eax
0x18004bde0  mov     rcx, [rbp+hFile]
0x18004bde4  jmp     short loc_18004BDE8
0x18004bde6  xor     edi, edi
0x18004bde8  test    edi, edi
0x18004bdea  js      short loc_18004BE24
0x18004bdec  xorps   xmm0, xmm0
0x18004bdef  xor     eax, eax
0x18004bdf1  movups  [rbp+FileInformation], xmm0
0x18004bdf5  mov     [rbp+var_20], rax
0x18004bdf9  lea     r9d, [rax+18h]; dwBufferSize
0x18004bdfd  lea     r8, [rbp+FileInformation]; lpFileInformation
0x18004be01  lea     edx, [rax+12h]; FileInformationClass
0x18004be04  call    cs:__imp_GetFileInformationByHandleEx
0x18004be0a  test    eax, eax
0x18004be0c  jz      short loc_18004BE12
0x18004be0e  xor     edi, edi
0x18004be10  jmp     short loc_18004BE1D
0x18004be12  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18004be17  mov     edi, eax
0x18004be19  test    eax, eax
0x18004be1b  js      short loc_18004BE24
0x18004be1d  mov     rax, qword ptr [rbp+FileInformation+8]
0x18004be21  mov     [rsi], rax
0x18004be24  lea     rcx, [rbp+hFile]
0x18004be28  call    ??1?$CAutoHandle@PEAX@@QEAA@XZ; CAutoHandle<void *>::~CAutoHandle<void *>(void)
0x18004be2d  jmp     loc_18004BEB2
0x18004be32  xor     edi, edi
0x18004be34  lea     rcx, [rbp+FileInformation]
0x18004be38  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004be3d  nop
0x18004be3e  lea     r12, [r14+108h]
0x18004be45  mov     r8, rax
0x18004be48  lea     rdx, [rbp+hFile]
0x18004be4c  mov     rcx, r12
0x18004be4f  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_JUStringComparatorIgnoreCase@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_J@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_J@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,__int64,StringComparatorIgnoreCase,std::allocator<std::pair<std::wstring const,__int64>>,0>>::find(std::wstring const &)
0x18004be54  nop
0x18004be55  lea     rcx, [rbp+FileInformation]
0x18004be59  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004be5e  mov     rax, [rbp+hFile]
0x18004be62  cmp     rax, [r12]
0x18004be66  jz      short loc_18004BE71
0x18004be68  mov     rcx, [rax+40h]
0x18004be6c  mov     [rsi], rcx
0x18004be6f  jmp     short loc_18004BEB2
0x18004be71  mov     rbx, [r14+118h]
0x18004be78  lea     rax, [rbx+1]
0x18004be7c  mov     [r14+118h], rax
0x18004be83  mov     rdx, r15
0x18004be86  lea     rcx, [rbp+FileInformation]
0x18004be8a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004be8f  nop
0x18004be90  mov     r8, rax
0x18004be93  lea     rdx, [rbp+hFile]
0x18004be97  mov     rcx, r12
0x18004be9a  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_JUStringComparatorIgnoreCase@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_J@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_J@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,__int64,StringComparatorIgnoreCase,std::allocator<std::pair<std::wstring const,__int64>>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x18004be9f  mov     rcx, [rax]
0x18004bea2  mov     [rcx+40h], rbx
0x18004bea6  lea     rcx, [rbp+FileInformation]
0x18004beaa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004beaf  mov     [rsi], rbx
0x18004beb2  mov     eax, edi
0x18004beb4  mov     rcx, [rbp+var_10]
0x18004beb8  xor     rcx, rsp; StackCookie
0x18004bebb  call    __security_check_cookie
0x18004bec0  add     rsp, 80h
0x18004bec7  pop     r15
0x18004bec9  pop     r14
0x18004becb  pop     r12
0x18004becd  pop     rdi
0x18004bece  pop     rsi
0x18004becf  pop     rbx
0x18004bed0  pop     rbp
0x18004bed1  retn
```
