# BeginFileMapEnumerationInternal

- ea: `0x180074910`
- end: `0x180074bf6`
- name: `BeginFileMapEnumerationInternal`
- size: `742`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002034`
- `0x180004a8c`
- `0x18002d2b0`
- `0x180041a28`
- `0x18006930c`
- `0x18006967c`
- `0x180069f40`
- `0x1800745b8`
- `0x180074620`
- `0x180074658`
- `0x180074788`
- `0x1800747e0`
- `0x180074910`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180074aa8`
- `ntdll!RtlAllocateHeap` at `0x180074aa8`
- `ntdll!RtlFreeHeap` at `0x180074bb5`
- `ntdll!RtlFreeHeap` at `0x180074bb5`
- `ntdll!NtOpenFile` at `0x180074b74`
- `ntdll!NtOpenFile` at `0x180074b74`

## pseudocode

```c
__int64 __fastcall BeginFileMapEnumerationInternal(__int64 a1, __int64 a2, _QWORD *a3)
{
  int FileMapFile; // ebx
  __int64 v5; // rcx
  _QWORD *Heap; // rax
  _QWORD *v7; // rdi
  __int64 v8; // xmm1_8
  __int128 *v10; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v11; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v12; // [rsp+48h] [rbp-B8h]
  __int128 v13; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v14; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v15; // [rsp+70h] [rbp-90h]
  __int128 v16; // [rsp+78h] [rbp-88h] BYREF
  __int64 v17; // [rsp+88h] [rbp-78h]
  __int128 v18; // [rsp+90h] [rbp-70h]
  __int64 v19; // [rsp+A0h] [rbp-60h]
  __int128 v20; // [rsp+B0h] [rbp-50h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v22; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v23; // [rsp+100h] [rbp+0h]

  *(_QWORD *)&v20 = 3670070;
  *a3 = 0;
  v23 = 0;
  *((_QWORD *)&v20 + 1) = L"\\SystemRoot\\WinSxS\\FileMaps";
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v13 = 0;
  v22 = 0;
  if ( a2 )
  {
    v15 = 0;
    v14 = 0;
    Windows::StringUtil::AsLUnicode(&v16, a2);
    v11 = v16;
    v12 = v17;
    FileMapFile = RtlConvertWin32FilePathToNtFilePath((unsigned __int64 *)&v11, &v22);
    if ( FileMapFile < 0 )
      goto LABEL_3;
    v10 = &v22;
    Windows::StringUtil::DropTrailingNtPathSlashes<Windows::AutoOperatorAmpersandHelper<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>>(&v10);
    v16 = v22;
    v17 = v23;
    Windows::StringUtil::AsLUnicode(&v11, L"WinSxS\\FileMaps");
    v18 = v11;
    v19 = v12;
    FileMapFile = RtlCombineNtPathSegments(v5, (__int64)&v16, &v14);
    if ( FileMapFile < 0
      || (LOWORD(v13) = 0,
          v11 = v14,
          v12 = v15,
          FileMapFile = Windows::StringUtil::Rtl::EnsureRemainingBufferBytes<Windows::Auto<_UNICODE_STRING> *,unsigned __int64>(
                          &v13,
                          v14),
          FileMapFile < 0) )
    {
LABEL_3:
      Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v14);
      goto LABEL_14;
    }
    Windows::StringUtil::Rtl::Impl::AppendStringToPreallocatedBuffer<_LUNICODE_STRING,_UNICODE_STRING>(&v11, &v13);
    v10 = &v22;
    Windows::StringUtil::DropTrailingNtPathSlashes<Windows::AutoOperatorAmpersandHelper<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>>(&v10);
    v20 = v13;
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v14);
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
    v8 = v23;
    v11 = v22;
    v23 = 0;
    v12 = v8;
    v22 = 0;
    FileMapFile = CCiFileMapEnumContext::Init(Heap, &v11);
    if ( FileMapFile < 0
      || (ObjectAttributes.ObjectName = (PUNICODE_STRING)&v20,
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
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v22);
  Windows::Rtl::AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>::Close(&v13);
  return (unsigned int)FileMapFile;
}

```

## disassembly

```asm
0x180074910  mov     [rsp-8+arg_0], rbx
0x180074915  push    rbp
0x180074916  push    rsi
0x180074917  push    rdi
0x180074918  lea     rbp, [rsp-10h]
0x18007491d  sub     rsp, 110h
0x180074924  mov     rax, cs:__security_cookie
0x18007492b  xor     rax, rsp
0x18007492e  mov     [rbp+20h+var_18], rax
0x180074932  xorps   xmm0, xmm0
0x180074935  mov     qword ptr [rbp+20h+var_70], 380036h
0x18007493d  xor     eax, eax
0x18007493f  mov     qword ptr [r8], 0
0x180074946  mov     [rbp+20h+var_20], rax
0x18007494a  lea     rax, aSystemrootWins_0; "\\SystemRoot\\WinSxS\\FileMaps"
0x180074951  mov     qword ptr [rbp+20h+var_70+8], rax
0x180074955  xorps   xmm1, xmm1
0x180074958  mov     rsi, r8
0x18007495b  movups  xmmword ptr [rbp+20h+ObjectAttributes.Length], xmm0
0x18007495f  movups  xmmword ptr [rbp+20h+ObjectAttributes.ObjectName], xmm0
0x180074963  movups  xmmword ptr [rbp+20h+ObjectAttributes.SecurityDescriptor], xmm0
0x180074967  movups  [rsp+120h+var_D0], xmm0
0x18007496c  movups  [rbp+20h+var_30], xmm1
0x180074970  test    rdx, rdx
0x180074973  jz      loc_180074A93
0x180074979  xor     eax, eax
0x18007497b  lea     rcx, [rsp+120h+var_A8]
0x180074980  mov     [rsp+120h+var_B0], rax
0x180074985  movups  [rsp+120h+var_C0], xmm0
0x18007498a  call    ?AsLUnicode@StringUtil@Windows@@YA?AU_LUNICODE_STRING@@PEB_W@Z; Windows::StringUtil::AsLUnicode(wchar_t const *)
0x18007498f  movups  xmm1, [rsp+120h+var_A8]
0x180074994  lea     rdx, [rbp+20h+var_30]
0x180074998  movsd   xmm2, [rbp+20h+var_98]
0x18007499d  lea     rcx, [rsp+120h+var_E8]
0x1800749a2  movups  [rsp+120h+var_E8], xmm1
0x1800749a7  movsd   [rsp+120h+var_D8], xmm2
0x1800749ad  call    RtlConvertWin32FilePathToNtFilePath
0x1800749b2  mov     ebx, eax
0x1800749b4  test    eax, eax
0x1800749b6  jns     short loc_1800749C7
0x1800749b8  lea     rcx, [rsp+120h+var_C0]
0x1800749bd  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x1800749c2  jmp     loc_180074BC1
0x1800749c7  lea     rax, [rbp+20h+var_30]
0x1800749cb  lea     rcx, [rsp+120h+var_F0]
0x1800749d0  mov     [rsp+120h+var_F0], rax
0x1800749d5  call    ??$DropTrailingNtPathSlashes@V?$AutoOperatorAmpersandHelper@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@Windows@@@StringUtil@Windows@@YAXV?$AutoOperatorAmpersandHelper@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@1@@Z; Windows::StringUtil::DropTrailingNtPathSlashes<Windows::AutoOperatorAmpersandHelper<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>>(Windows::AutoOperatorAmpersandHelper<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>)
0x1800749da  movups  xmm0, [rbp+20h+var_30]
0x1800749de  lea     rdx, aWinsxsFilemaps; "WinSxS\\FileMaps"
0x1800749e5  movsd   xmm1, [rbp+20h+var_20]
0x1800749ea  lea     rcx, [rsp+120h+var_E8]
0x1800749ef  movups  [rsp+120h+var_A8], xmm0
0x1800749f4  movsd   [rbp+20h+var_98], xmm1
0x1800749f9  call    ?AsLUnicode@StringUtil@Windows@@YA?AU_LUNICODE_STRING@@PEB_W@Z; Windows::StringUtil::AsLUnicode(wchar_t const *)
0x1800749fe  movups  xmm1, [rsp+120h+var_E8]
0x180074a03  lea     r8, [rsp+120h+var_C0]
0x180074a08  movsd   xmm2, [rsp+120h+var_D8]
0x180074a0e  lea     rdx, [rsp+120h+var_A8]
0x180074a13  movups  [rbp+20h+var_90], xmm1
0x180074a17  movsd   [rbp+20h+var_80], xmm2
0x180074a1c  call    RtlCombineNtPathSegments
0x180074a21  mov     ebx, eax
0x180074a23  test    eax, eax
0x180074a25  js      short loc_1800749B8
0x180074a27  movups  xmm1, [rsp+120h+var_C0]
0x180074a2c  lea     rcx, [rsp+120h+var_D0]
0x180074a31  xor     eax, eax
0x180074a33  movsd   xmm0, [rsp+120h+var_B0]
0x180074a39  movq    rdx, xmm1
0x180074a3e  mov     word ptr [rsp+120h+var_D0], ax
0x180074a43  movups  [rsp+120h+var_E8], xmm1
0x180074a48  movsd   [rsp+120h+var_D8], xmm0
0x180074a4e  call    ??$EnsureRemainingBufferBytes@PEAV?$Auto@U_UNICODE_STRING@@@Windows@@_K@Rtl@StringUtil@Windows@@YAJPEAV?$Auto@U_UNICODE_STRING@@@2@_K@Z; Windows::StringUtil::Rtl::EnsureRemainingBufferBytes<Windows::Auto<_UNICODE_STRING> *,unsigned __int64>(Windows::Auto<_UNICODE_STRING> *,unsigned __int64)
0x180074a53  mov     ebx, eax
0x180074a55  test    eax, eax
0x180074a57  js      loc_1800749B8
0x180074a5d  lea     rdx, [rsp+120h+var_D0]
0x180074a62  lea     rcx, [rsp+120h+var_E8]
0x180074a67  call    ??$AppendStringToPreallocatedBuffer@U_LUNICODE_STRING@@U_UNICODE_STRING@@@Impl@Rtl@StringUtil@Windows@@YAXAEBU_LUNICODE_STRING@@PEAU_UNICODE_STRING@@@Z; Windows::StringUtil::Rtl::Impl::AppendStringToPreallocatedBuffer<_LUNICODE_STRING,_UNICODE_STRING>(_LUNICODE_STRING const &,_UNICODE_STRING *)
0x180074a6c  lea     rax, [rbp+20h+var_30]
0x180074a70  lea     rcx, [rsp+120h+var_F0]
0x180074a75  mov     [rsp+120h+var_F0], rax
0x180074a7a  call    ??$DropTrailingNtPathSlashes@V?$AutoOperatorAmpersandHelper@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@Windows@@@StringUtil@Windows@@YAXV?$AutoOperatorAmpersandHelper@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@1@@Z; Windows::StringUtil::DropTrailingNtPathSlashes<Windows::AutoOperatorAmpersandHelper<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>>(Windows::AutoOperatorAmpersandHelper<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>)
0x180074a7f  movaps  xmm0, [rsp+120h+var_D0]
0x180074a84  lea     rcx, [rsp+120h+var_C0]
0x180074a89  movdqa  [rbp+20h+var_70], xmm0
0x180074a8e  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x180074a93  mov     rcx, gs:60h
0x180074a9c  xor     edx, edx; Flags
0x180074a9e  mov     r8d, 2E0h; Size
0x180074aa4  mov     rcx, [rcx+30h]; HeapHandle
0x180074aa8  call    cs:__imp_RtlAllocateHeap
0x180074aaf  nop     dword ptr [rax+rax+00h]
0x180074ab4  mov     rdi, rax
0x180074ab7  test    rax, rax
0x180074aba  jnz     short loc_180074AC6
0x180074abc  mov     ebx, 0C0000017h
0x180074ac1  jmp     loc_180074BC1
0x180074ac6  mov     qword ptr [rdi+8], 0
0x180074ace  lea     rax, ??_7CFilemapEnumerationLookupContext@@6B@; const CFilemapEnumerationLookupContext::`vftable'
0x180074ad5  mov     [rdi], rax
0x180074ad8  lea     rdx, [rsp+120h+var_E8]
0x180074add  mov     qword ptr [rdi+10h], 0
0x180074ae5  xorps   xmm0, xmm0
0x180074ae8  mov     qword ptr [rdi+18h], 0
0x180074af0  xor     eax, eax
0x180074af2  movups  xmmword ptr [rdi+0A0h], xmm0
0x180074af9  mov     [rdi+0B0h], rax
0x180074b00  mov     rcx, rdi
0x180074b03  movups  xmm0, [rbp+20h+var_30]
0x180074b07  movsd   xmm1, [rbp+20h+var_20]
0x180074b0c  movups  [rsp+120h+var_E8], xmm0
0x180074b11  mov     [rbp+20h+var_20], rax
0x180074b15  xorps   xmm0, xmm0
0x180074b18  movsd   [rsp+120h+var_D8], xmm1
0x180074b1e  movups  [rbp+20h+var_30], xmm0
0x180074b22  call    ?Init@CCiFileMapEnumContext@@QEAAJV?$Auto@U_LUNICODE_STRING@@@Windows@@@Z; CCiFileMapEnumContext::Init(Windows::Auto<_LUNICODE_STRING>)
0x180074b27  mov     ebx, eax
0x180074b29  test    eax, eax
0x180074b2b  js      short loc_180074B9B
0x180074b2d  lea     rax, [rbp+20h+var_70]
0x180074b31  mov     [rsp+120h+OpenOptions], 4021h; OpenOptions
0x180074b39  xorps   xmm0, xmm0
0x180074b3c  mov     [rbp+20h+ObjectAttributes.ObjectName], rax
0x180074b40  lea     r9, [rdi+38h]; IoStatusBlock
0x180074b44  mov     [rbp+20h+ObjectAttributes.Length], 30h ; '0'
0x180074b4b  lea     rcx, [rdi+28h]; FileHandle
0x180074b4f  mov     [rbp+20h+ObjectAttributes.RootDirectory], 0
0x180074b57  lea     r8, [rbp+20h+ObjectAttributes]; ObjectAttributes
0x180074b5b  mov     [rbp+20h+ObjectAttributes.Attributes], 40h ; '@'
0x180074b62  mov     edx, 100001h; DesiredAccess
0x180074b67  mov     [rsp+120h+ShareAccess], 7; ShareAccess
0x180074b6f  movdqu  xmmword ptr [rbp+20h+ObjectAttributes.SecurityDescriptor], xmm0
0x180074b74  call    cs:__imp_NtOpenFile
0x180074b7b  nop     dword ptr [rax+rax+00h]
0x180074b80  mov     ebx, eax
0x180074b82  test    eax, eax
0x180074b84  js      short loc_180074B9B
0x180074b86  mov     rcx, rdi; this
0x180074b89  call    ?MoveToNextFileMapFile@CCiFileMapEnumContext@@QEAAJXZ; CCiFileMapEnumContext::MoveToNextFileMapFile(void)
0x180074b8e  mov     ebx, eax
0x180074b90  test    eax, eax
0x180074b92  js      short loc_180074B9B
0x180074b94  mov     [rsi], rdi
0x180074b97  xor     ebx, ebx
0x180074b99  jmp     short loc_180074BC1
0x180074b9b  mov     rcx, rdi; this
0x180074b9e  call    ?Close@CCiFileMapEnumContext@@QEAAXXZ; CCiFileMapEnumContext::Close(void)
0x180074ba3  mov     rcx, gs:60h
0x180074bac  mov     r8, rdi; P
0x180074baf  xor     edx, edx; Flags
0x180074bb1  mov     rcx, [rcx+30h]; HeapHandle
0x180074bb5  call    cs:__imp_RtlFreeHeap
0x180074bbc  nop     dword ptr [rax+rax+00h]
0x180074bc1  lea     rcx, [rbp+20h+var_30]
0x180074bc5  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x180074bca  lea     rcx, [rsp+120h+var_D0]
0x180074bcf  call    ?Close@?$AutoString@U_UNICODE_STRING@@V?$Auto@U_UNICODE_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>::Close(void)
0x180074bd4  mov     eax, ebx
0x180074bd6  mov     rcx, [rbp+20h+var_18]
0x180074bda  xor     rcx, rsp; StackCookie
0x180074bdd  call    __security_check_cookie
0x180074be2  mov     rbx, [rsp+120h+arg_0]
0x180074bea  add     rsp, 110h
0x180074bf1  pop     rdi
0x180074bf2  pop     rsi
0x180074bf3  pop     rbp
0x180074bf4  retn
```
