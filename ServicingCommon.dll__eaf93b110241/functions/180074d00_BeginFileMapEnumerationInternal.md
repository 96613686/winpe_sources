# BeginFileMapEnumerationInternal

- ea: `0x180074d00`
- end: `0x180074f5e`
- name: `BeginFileMapEnumerationInternal`
- size: `606`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002564`
- `0x180002748`
- `0x1800293a0`
- `0x180068edc`
- `0x180074818`
- `0x1800748c4`
- `0x180074928`
- `0x180074974`
- `0x180074b78`
- `0x180074bd0`
- `0x180074d00`

## import_xrefs

- `ntdll!NtOpenFile` at `0x180074edd`
- `ntdll!NtOpenFile` at `0x180074edd`
- `ntdll!RtlAllocateHeap` at `0x180074e14`
- `ntdll!RtlAllocateHeap` at `0x180074e14`
- `ntdll!RtlFreeHeap` at `0x180074f1e`
- `ntdll!RtlFreeHeap` at `0x180074f1e`

## pseudocode

```c
__int64 __fastcall BeginFileMapEnumerationInternal(__int64 a1, __int128 *a2, _QWORD *a3)
{
  NTSTATUS FileMapFile; // ebx
  __int64 v5; // rdx
  _QWORD *Heap; // rax
  _QWORD *v7; // rdi
  __int64 v8; // xmm1_8
  __int128 v10; // [rsp+30h] [rbp-59h] BYREF
  __int64 v11; // [rsp+40h] [rbp-49h]
  __int128 *v12; // [rsp+48h] [rbp-41h] BYREF
  __int128 v13; // [rsp+50h] [rbp-39h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-29h] BYREF
  __int128 v15; // [rsp+90h] [rbp+7h] BYREF
  __int64 v16; // [rsp+A0h] [rbp+17h]
  __int128 v17; // [rsp+B0h] [rbp+27h] BYREF

  v12 = a2;
  *(_QWORD *)&v13 = 3670070;
  v16 = 0;
  *((_QWORD *)&v13 + 1) = L"\\SystemRoot\\WinSxS\\FileMaps";
  *a3 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v17 = 0;
  v15 = 0;
  if ( a2 )
  {
    v11 = 0;
    v10 = 0;
    FileMapFile = Windows::StringUtil::Rtl::ConvertWin32FilePathToNtFilePath<wchar_t const *>(&v12, &v15);
    if ( FileMapFile < 0
      || (v12 = &v15,
          Windows::StringUtil::DropTrailingNtPathSlashes<Windows::AutoOperatorAmpersandHelper<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>>(&v12),
          FileMapFile = Windows::StringUtil::Rtl::CombineNtPaths<Windows::Auto<_LUNICODE_STRING>,wchar_t [16]>(
                          &v15,
                          v5,
                          &v10),
          FileMapFile < 0)
      || (LOWORD(v17) = 0,
          v12 = &v17,
          FileMapFile = Windows::StringUtil::Rtl::AppendString<Windows::Auto<_LUNICODE_STRING>,Windows::AutoOperatorAmpersandHelper<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>,0>(
                          &v10,
                          &v12),
          FileMapFile < 0) )
    {
      Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v10);
      goto LABEL_14;
    }
    v12 = &v15;
    Windows::StringUtil::DropTrailingNtPathSlashes<Windows::AutoOperatorAmpersandHelper<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>>(&v12);
    v13 = v17;
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v10);
  }
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x2E0u);
  v7 = Heap;
  if ( Heap )
  {
    Heap[1] = 0;
    *Heap = &CFilemapEnumerationLookupContext::`vftable';
    Heap[2] = 0;
    Heap[3] = 0;
    *((_OWORD *)Heap + 10) = 0;
    Heap[22] = 0;
    v8 = v16;
    v10 = v15;
    v16 = 0;
    v11 = v8;
    v15 = 0;
    FileMapFile = CCiFileMapEnumContext::Init(Heap, &v10);
    if ( FileMapFile < 0
      || (ObjectAttributes.ObjectName = (PUNICODE_STRING)&v13,
          ObjectAttributes.Length = 48,
          ObjectAttributes.RootDirectory = 0,
          ObjectAttributes.Attributes = 64,
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0,
          FileMapFile = NtOpenFile(
                          (PHANDLE)v7 + 5,
                          0x100001u,
                          &ObjectAttributes,
                          (PIO_STATUS_BLOCK)(v7 + 7),
                          7u,
                          0x4021u),
          FileMapFile < 0)
      || (FileMapFile = CCiFileMapEnumContext::MoveToNextFileMapFile((CCiFileMapEnumContext *)v7), FileMapFile < 0) )
    {
      CCiFileMapEnumContext::Close((CCiFileMapEnumContext *)v7);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
    }
    else
    {
      *a3 = v7;
      FileMapFile = 0;
    }
  }
  else
  {
    FileMapFile = -1073741801;
  }
LABEL_14:
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v15);
  Windows::Rtl::AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>::Close(&v17);
  return (unsigned int)FileMapFile;
}

```

## disassembly

```asm
0x180074d00  mov     [rsp-8+arg_0], rbx
0x180074d05  push    rbp
0x180074d06  push    rsi
0x180074d07  push    rdi
0x180074d08  lea     rbp, [rsp-47h]
0x180074d0d  sub     rsp, 0D0h
0x180074d14  mov     rax, cs:__security_cookie
0x180074d1b  xor     rax, rsp
0x180074d1e  mov     [rbp+57h+var_20], rax
0x180074d22  xorps   xmm0, xmm0
0x180074d25  mov     [rbp+57h+var_98], rdx
0x180074d29  xor     eax, eax
0x180074d2b  mov     qword ptr [rbp+57h+var_90], 380036h
0x180074d33  mov     [rbp+57h+var_40], rax
0x180074d37  lea     rax, aSystemrootWins_0; "\\SystemRoot\\WinSxS\\FileMaps"
0x180074d3e  mov     qword ptr [rbp+57h+var_90+8], rax
0x180074d42  xorps   xmm1, xmm1
0x180074d45  mov     qword ptr [r8], 0
0x180074d4c  mov     rsi, r8
0x180074d4f  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180074d53  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180074d57  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180074d5b  movups  [rbp+57h+var_30], xmm0
0x180074d5f  movups  [rbp+57h+var_50], xmm1
0x180074d63  test    rdx, rdx
0x180074d66  jz      loc_180074DFF
0x180074d6c  xor     eax, eax
0x180074d6e  lea     rdx, [rbp+57h+var_50]
0x180074d72  lea     rcx, [rbp+57h+var_98]
0x180074d76  mov     [rbp+57h+var_A0], rax
0x180074d7a  movups  [rbp+57h+var_B0], xmm0
0x180074d7e  call    ??$ConvertWin32FilePathToNtFilePath@PEB_W@Rtl@StringUtil@Windows@@YAJAEBQEB_WPEAV?$Auto@U_LUNICODE_STRING@@@2@@Z; Windows::StringUtil::Rtl::ConvertWin32FilePathToNtFilePath<wchar_t const *>(wchar_t const * const &,Windows::Auto<_LUNICODE_STRING> *)
0x180074d83  mov     ebx, eax
0x180074d85  test    eax, eax
0x180074d87  jns     short loc_180074D97
0x180074d89  lea     rcx, [rbp+57h+var_B0]
0x180074d8d  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x180074d92  jmp     loc_180074F2A
0x180074d97  lea     rax, [rbp+57h+var_50]
0x180074d9b  lea     rcx, [rbp+57h+var_98]
0x180074d9f  mov     [rbp+57h+var_98], rax
0x180074da3  call    ??$DropTrailingNtPathSlashes@V?$AutoOperatorAmpersandHelper@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@Windows@@@StringUtil@Windows@@YAXV?$AutoOperatorAmpersandHelper@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@1@@Z; Windows::StringUtil::DropTrailingNtPathSlashes<Windows::AutoOperatorAmpersandHelper<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>>(Windows::AutoOperatorAmpersandHelper<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>)
0x180074da8  lea     r8, [rbp+57h+var_B0]
0x180074dac  lea     rcx, [rbp+57h+var_50]
0x180074db0  call    ??$CombineNtPaths@V?$Auto@U_LUNICODE_STRING@@@Windows@@$$BY0BA@_W@Rtl@StringUtil@Windows@@YAJAEBV?$Auto@U_LUNICODE_STRING@@@2@AEAY0BA@$$CB_WPEAV32@@Z; Windows::StringUtil::Rtl::CombineNtPaths<Windows::Auto<_LUNICODE_STRING>,wchar_t [16]>(Windows::Auto<_LUNICODE_STRING> const &,wchar_t const (&)[16],Windows::Auto<_LUNICODE_STRING> *)
0x180074db5  lea     rcx, [rbp+57h+var_B0]
0x180074db9  mov     ebx, eax
0x180074dbb  test    eax, eax
0x180074dbd  js      short loc_180074D8D
0x180074dbf  xor     eax, eax
0x180074dc1  lea     rdx, [rbp+57h+var_98]
0x180074dc5  mov     word ptr [rbp+57h+var_30], ax
0x180074dc9  lea     rax, [rbp+57h+var_30]
0x180074dcd  mov     [rbp+57h+var_98], rax
0x180074dd1  call    ??$AppendString@V?$Auto@U_LUNICODE_STRING@@@Windows@@V?$AutoOperatorAmpersandHelper@U_UNICODE_STRING@@V?$Auto@U_UNICODE_STRING@@@Windows@@@2@$0A@@Rtl@StringUtil@Windows@@YAJAEBV?$Auto@U_LUNICODE_STRING@@@2@V?$AutoOperatorAmpersandHelper@U_UNICODE_STRING@@V?$Auto@U_UNICODE_STRING@@@Windows@@@2@@Z; Windows::StringUtil::Rtl::AppendString<Windows::Auto<_LUNICODE_STRING>,Windows::AutoOperatorAmpersandHelper<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>,0>(Windows::Auto<_LUNICODE_STRING> const &,Windows::AutoOperatorAmpersandHelper<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>)
0x180074dd6  mov     ebx, eax
0x180074dd8  test    eax, eax
0x180074dda  js      short loc_180074D89
0x180074ddc  lea     rax, [rbp+57h+var_50]
0x180074de0  lea     rcx, [rbp+57h+var_98]
0x180074de4  mov     [rbp+57h+var_98], rax
0x180074de8  call    ??$DropTrailingNtPathSlashes@V?$AutoOperatorAmpersandHelper@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@Windows@@@StringUtil@Windows@@YAXV?$AutoOperatorAmpersandHelper@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@1@@Z; Windows::StringUtil::DropTrailingNtPathSlashes<Windows::AutoOperatorAmpersandHelper<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>>(Windows::AutoOperatorAmpersandHelper<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>)
0x180074ded  movaps  xmm0, [rbp+57h+var_30]
0x180074df1  lea     rcx, [rbp+57h+var_B0]
0x180074df5  movdqa  [rbp+57h+var_90], xmm0
0x180074dfa  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x180074dff  mov     rcx, gs:60h
0x180074e08  xor     edx, edx; Flags
0x180074e0a  mov     r8d, 2E0h; Size
0x180074e10  mov     rcx, [rcx+30h]; HeapHandle
0x180074e14  call    cs:__imp_RtlAllocateHeap
0x180074e1b  nop     dword ptr [rax+rax+00h]
0x180074e20  mov     rdi, rax
0x180074e23  test    rax, rax
0x180074e26  jnz     short loc_180074E32
0x180074e28  mov     ebx, 0C0000017h
0x180074e2d  jmp     loc_180074F2A
0x180074e32  mov     qword ptr [rdi+8], 0
0x180074e3a  lea     rax, ??_7CFilemapEnumerationLookupContext@@6B@; const CFilemapEnumerationLookupContext::`vftable'
0x180074e41  mov     [rdi], rax
0x180074e44  lea     rdx, [rbp+57h+var_B0]
0x180074e48  mov     qword ptr [rdi+10h], 0
0x180074e50  xorps   xmm0, xmm0
0x180074e53  mov     qword ptr [rdi+18h], 0
0x180074e5b  xor     eax, eax
0x180074e5d  movups  xmmword ptr [rdi+0A0h], xmm0
0x180074e64  mov     [rdi+0B0h], rax
0x180074e6b  mov     rcx, rdi
0x180074e6e  movups  xmm0, [rbp+57h+var_50]
0x180074e72  movsd   xmm1, [rbp+57h+var_40]
0x180074e77  movups  [rbp+57h+var_B0], xmm0
0x180074e7b  mov     [rbp+57h+var_40], rax
0x180074e7f  xorps   xmm0, xmm0
0x180074e82  movsd   [rbp+57h+var_A0], xmm1
0x180074e87  movups  [rbp+57h+var_50], xmm0
0x180074e8b  call    ?Init@CCiFileMapEnumContext@@QEAAJV?$Auto@U_LUNICODE_STRING@@@Windows@@@Z; CCiFileMapEnumContext::Init(Windows::Auto<_LUNICODE_STRING>)
0x180074e90  mov     ebx, eax
0x180074e92  test    eax, eax
0x180074e94  js      short loc_180074F04
0x180074e96  lea     rax, [rbp+57h+var_90]
0x180074e9a  mov     [rsp+0E0h+OpenOptions], 4021h; OpenOptions
0x180074ea2  xorps   xmm0, xmm0
0x180074ea5  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180074ea9  lea     r9, [rdi+38h]; IoStatusBlock
0x180074ead  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180074eb4  lea     rcx, [rdi+28h]; FileHandle
0x180074eb8  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180074ec0  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180074ec4  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180074ecb  mov     edx, 100001h; DesiredAccess
0x180074ed0  mov     [rsp+0E0h+ShareAccess], 7; ShareAccess
0x180074ed8  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180074edd  call    cs:__imp_NtOpenFile
0x180074ee4  nop     dword ptr [rax+rax+00h]
0x180074ee9  mov     ebx, eax
0x180074eeb  test    eax, eax
0x180074eed  js      short loc_180074F04
0x180074eef  mov     rcx, rdi; this
0x180074ef2  call    ?MoveToNextFileMapFile@CCiFileMapEnumContext@@QEAAJXZ; CCiFileMapEnumContext::MoveToNextFileMapFile(void)
0x180074ef7  mov     ebx, eax
0x180074ef9  test    eax, eax
0x180074efb  js      short loc_180074F04
0x180074efd  mov     [rsi], rdi
0x180074f00  xor     ebx, ebx
0x180074f02  jmp     short loc_180074F2A
0x180074f04  mov     rcx, rdi; this
0x180074f07  call    ?Close@CCiFileMapEnumContext@@QEAAXXZ; CCiFileMapEnumContext::Close(void)
0x180074f0c  mov     rcx, gs:60h
0x180074f15  mov     r8, rdi; P
0x180074f18  xor     edx, edx; Flags
0x180074f1a  mov     rcx, [rcx+30h]; HeapHandle
0x180074f1e  call    cs:__imp_RtlFreeHeap
0x180074f25  nop     dword ptr [rax+rax+00h]
0x180074f2a  lea     rcx, [rbp+57h+var_50]
0x180074f2e  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x180074f33  lea     rcx, [rbp+57h+var_30]
0x180074f37  call    ?Close@?$AutoString@U_UNICODE_STRING@@V?$Auto@U_UNICODE_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>::Close(void)
0x180074f3c  mov     eax, ebx
0x180074f3e  mov     rcx, [rbp+57h+var_20]
0x180074f42  xor     rcx, rsp; StackCookie
0x180074f45  call    __security_check_cookie
0x180074f4a  mov     rbx, [rsp+0E0h+arg_0]
0x180074f52  add     rsp, 0D0h
0x180074f59  pop     rdi
0x180074f5a  pop     rsi
0x180074f5b  pop     rbp
0x180074f5c  retn
```
