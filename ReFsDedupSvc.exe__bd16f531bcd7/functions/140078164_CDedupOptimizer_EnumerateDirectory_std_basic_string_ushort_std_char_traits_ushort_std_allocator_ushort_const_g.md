# CDedupOptimizer::EnumerateDirectory(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,gsl::span<gsl::byte,-1>,std::stack<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::deque<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> &)

- ea: `0x140078164`
- end: `0x1400785e7`
- name: `?EnumerateDirectory@CDedupOptimizer@@AEAAKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$span@W4byte@gsl@@$0?0@gsl@@AEAV?$stack@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$deque@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@3@@Z`
- size: `1155`
- prototype: `__int64 __fastcall(CDedupOptimizer *this)`
- caller_count: `1`
- callee_count: `21`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400785f0`

## callees

- `0x140004870`
- `0x140014ff0`
- `0x1400150bc`
- `0x140019328`
- `0x140019600`
- `0x14001983c`
- `0x140019d14`
- `0x14001c194`
- `0x140023438`
- `0x140023d40`
- `0x140032f54`
- `0x140037990`
- `0x140048674`
- `0x140066e58`
- `0x140069dc8`
- `0x14006ce04`
- `0x1400736fc`
- `0x140078164`
- `0x140079bd4`
- `0x140079e54`
- `0x14007bd4c`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x14007820b`
- `ntdll!RtlInitUnicodeString` at `0x14007820b`
- `ntdll!NtQueryDirectoryFile` at `0x1400782d0`
- `ntdll!NtQueryDirectoryFile` at `0x1400782d0`
- `ntdll!NtOpenFile` at `0x14007825e`
- `ntdll!NtOpenFile` at `0x14007825e`
- `ntdll!RtlNtStatusToDosError` at `0x140078270`
- `ntdll!RtlNtStatusToDosError` at `0x14007859f`
- `ntdll!RtlNtStatusToDosError` at `0x140078270`
- `ntdll!RtlNtStatusToDosError` at `0x14007859f`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CDedupOptimizer::EnumerateDirectory(CDedupOptimizer *this, __int64 a2, __int64 a3, _QWORD *a4)
{
  __int64 v7; // rax
  __int64 v8; // rax
  const WCHAR *v9; // rax
  int v10; // eax
  ULONG v11; // ebx
  void *v12; // rbx
  BOOLEAN RestartScan; // al
  ULONG Length; // ecx
  _DWORD *v15; // rdi
  NTSTATUS v16; // eax
  unsigned __int64 v17; // rdx
  int v18; // r8d
  unsigned __int64 v19; // rdx
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // r13
  __int64 v23; // r12
  __int64 v24; // rsi
  __int64 v25; // rax
  __int64 v26; // rcx
  unsigned int v27; // eax
  unsigned int v28; // esi
  NTSTATUS v30; // ecx
  void *v31; // [rsp+68h] [rbp-98h] BYREF
  ULONG v32; // [rsp+70h] [rbp-90h]
  void *FileHandle; // [rsp+78h] [rbp-88h] BYREF
  _DWORD *v34; // [rsp+80h] [rbp-80h]
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-78h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v37[2]; // [rsp+A8h] [rbp-58h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v39; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v40[16]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v41; // [rsp+110h] [rbp+10h]
  _BYTE v42[16]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v43; // [rsp+130h] [rbp+30h]
  _BYTE v44[32]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v45[32]; // [rsp+160h] [rbp+60h] BYREF

  FileHandle = (void *)-1LL;
  DestinationString = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  std::wstring::wstring(v42, a2);
  v7 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v42);
  if ( *(_WORD *)(v7 + 2 * v43 - 2) != 92 )
  {
    v8 = std::_WChar_traits<unsigned short>::length(L"\\");
    std::wstring::_Append<unsigned short>(v42, L"\\", v8);
  }
  v9 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v42);
  RtlInitUnicodeString(&DestinationString, v9);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v10 = NtOpenFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 7u, 0x4021u);
  if ( v10 >= 0 )
  {
    v12 = FileHandle;
    v31 = FileHandle;
    RestartScan = 1;
    Length = *(_DWORD *)a3;
    v32 = *(_DWORD *)a3;
    v15 = *(_DWORD **)(a3 + 8);
    v34 = v15;
LABEL_6:
    v16 = NtQueryDirectoryFile(
            v12,
            0,
            0,
            0,
            &IoStatusBlock,
            v15,
            Length,
            FileIdFullDirectoryInformation,
            0,
            0,
            RestartScan);
    if ( v16 < 0 )
    {
      if ( v16 == -2147483642 )
        v30 = 0;
      else
        v30 = v16;
      v11 = RtlNtStatusToDosError(v30);
    }
    else
    {
      while ( 1 )
      {
        std::wstring::wstring(v40, v15 + 20, (unsigned __int64)(unsigned int)v15[15] >> 1);
        std::operator+<unsigned short>(v44, v42, v40);
        v39 = 0;
        v17 = *((_QWORD *)v15 + 9);
        v39 = 0;
        if ( v17 == -1 )
          break;
        if ( v17 )
        {
          v18 = 4 * (v17 >> 60);
          if ( !v18 )
            break;
          v19 = v17 & 0xFFFFFFFFFFFFFFFLL;
          if ( ((15LL << ((unsigned __int8)v18 - 4)) & v19) == 0 )
            break;
          *((_QWORD *)&v39 + 1) = v19 & ((1LL << v18) - 1);
          *(_QWORD *)&v39 = v19 >> v18;
        }
        if ( (v15[14] & 0x10) == 0
          || (std::_WChar_traits<unsigned short>::length(L"."),
              v20 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v40),
              (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v20, v41))
          || (std::_WChar_traits<unsigned short>::length(L".."),
              v21 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v40),
              (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v21, v41))
          || (unsigned __int8)DedupUtil::IsPathExcluded(v44, (char *)this + 784) )
        {
          if ( *((_QWORD *)v15 + 5) >= (__int64)*((unsigned int *)this + 60)
            && !(unsigned __int8)CDedupOptimizer::IsExcludedFile(this)
            && (v15[14] & 0x400) == 0 )
          {
            v37[0] = 0;
            v37[1] = *((_QWORD *)v15 + 5);
            v27 = CHashIndex::AddFileRange(
                    *((CHashIndex **)this + 29),
                    (const union SmsBigIdentifier *)&v39,
                    (const struct _RANGE *)v37);
            v28 = v27;
            if ( v27 )
            {
              if ( (unsigned __int8)IsFatalDedupError(v27) )
              {
                std::wstring::_Tidy_deallocate(v44);
                std::wstring::_Tidy_deallocate(v40);
                wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v31);
                std::wstring::_Tidy_deallocate(v42);
                return v28;
              }
            }
            else
            {
              _InterlockedIncrement64((volatile signed __int64 *)this + 52);
            }
          }
        }
        else
        {
          v22 = std::operator+<unsigned short>(v45, v44, L"\\");
          if ( a4[2] <= (unsigned __int64)(a4[4] + 1LL) )
            std::deque<std::wstring>::_Growmap(a4);
          a4[3] &= a4[2] - 1LL;
          v23 = a4[4] + a4[3];
          v24 = std::deque<Windows::FileSystem::ReFs::DataChangeListener<Windows::FileSystem::ReFs::ReFsDedupService>::DedupNotifyRecord,std::allocator<Windows::FileSystem::ReFs::DataChangeListener<Windows::FileSystem::ReFs::ReFsDedupService>::DedupNotifyRecord>>::_Getblock(
                  a4,
                  v23);
          if ( !*(_QWORD *)(a4[1] + 8 * v24) )
            *(_QWORD *)(a4[1] + 8 * v24) = std::_Allocate<16,std::_Default_allocate_traits>(0x20u);
          v25 = std::_Deque_val<std::_Deque_simple_types<Windows::FileSystem::ReFs::DataChangeListener<Windows::FileSystem::ReFs::ReFsDedupService>::DedupNotifyRecord>>::_Address_subscript(
                  a4,
                  v23);
          std::_Default_allocator_traits<std::allocator<std::_List_node<std::wstring,void *>>>::construct<std::wstring,std::wstring>(
            v26,
            v25,
            v22);
          ++a4[4];
          std::wstring::_Tidy_deallocate(v45);
        }
        if ( !*v15 )
        {
          std::wstring::_Tidy_deallocate(v44);
          std::wstring::_Tidy_deallocate(v40);
          RestartScan = 0;
          v15 = v34;
          Length = v32;
          goto LABEL_6;
        }
        v15 = (_DWORD *)((char *)v15 + (unsigned int)*v15);
        std::wstring::_Tidy_deallocate(v44);
        std::wstring::_Tidy_deallocate(v40);
      }
      v11 = 87;
      std::wstring::_Tidy_deallocate(v44);
      std::wstring::_Tidy_deallocate(v40);
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v31);
  }
  else
  {
    v11 = RtlNtStatusToDosError(v10);
  }
  std::wstring::_Tidy_deallocate(v42);
  return v11;
}

```

## disassembly

```asm
0x140078164  push    rbp
0x140078166  push    rbx
0x140078167  push    rsi
0x140078168  push    rdi
0x140078169  push    r12
0x14007816b  push    r13
0x14007816d  push    r14
0x14007816f  push    r15
0x140078171  lea     rbp, [rsp-98h]
0x140078179  sub     rsp, 198h
0x140078180  mov     rax, cs:__security_cookie
0x140078187  xor     rax, rsp
0x14007818a  mov     [rbp+0D0h+var_50], rax
0x140078191  mov     r14, r9
0x140078194  mov     rdi, r8
0x140078197  mov     r15, rcx
0x14007819a  mov     [rsp+1D0h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x1400781a3  xorps   xmm0, xmm0
0x1400781a6  movups  xmmword ptr [rbp+0D0h+DestinationString.Length], xmm0
0x1400781aa  xorps   xmm1, xmm1
0x1400781ad  movups  xmmword ptr [rbp+0D0h+IoStatusBlock], xmm1
0x1400781b1  movups  xmmword ptr [rbp+0D0h+ObjectAttributes.Length], xmm0
0x1400781b5  movups  xmmword ptr [rbp+0D0h+ObjectAttributes.ObjectName], xmm0
0x1400781b9  movups  xmmword ptr [rbp+0D0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400781bd  lea     rcx, [rbp+0D0h+var_B0]
0x1400781c1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1400781c6  nop
0x1400781c7  lea     rcx, [rbp+0D0h+var_B0]
0x1400781cb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1400781d0  mov     rcx, [rbp+0D0h+var_A0]
0x1400781d4  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x1400781da  jz      short loc_1400781FB
0x1400781dc  lea     rcx, StringValue; "\\"
0x1400781e3  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1400781e8  mov     r8, rax
0x1400781eb  lea     rdx, StringValue; "\\"
0x1400781f2  lea     rcx, [rbp+0D0h+var_B0]
0x1400781f6  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1400781fb  lea     rcx, [rbp+0D0h+var_B0]
0x1400781ff  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140078204  mov     rdx, rax; SourceString
0x140078207  lea     rcx, [rbp+0D0h+DestinationString]; DestinationString
0x14007820b  call    cs:__imp_RtlInitUnicodeString
0x140078212  nop     dword ptr [rax+rax+00h]
0x140078217  mov     [rbp+0D0h+ObjectAttributes.Length], 30h ; '0'
0x14007821e  xor     r12d, r12d
0x140078221  mov     [rbp+0D0h+ObjectAttributes.RootDirectory], r12
0x140078225  mov     [rbp+0D0h+ObjectAttributes.Attributes], 40h ; '@'
0x14007822c  lea     rax, [rbp+0D0h+DestinationString]
0x140078230  mov     [rbp+0D0h+ObjectAttributes.ObjectName], rax
0x140078234  xorps   xmm0, xmm0
0x140078237  movdqu  xmmword ptr [rbp+0D0h+ObjectAttributes.SecurityDescriptor], xmm0
0x14007823c  mov     [rsp+1D0h+OpenOptions], 4021h; OpenOptions
0x140078244  mov     [rsp+1D0h+ShareAccess], 7; ShareAccess
0x14007824c  lea     r9, [rbp+0D0h+IoStatusBlock]; IoStatusBlock
0x140078250  lea     r8, [rbp+0D0h+ObjectAttributes]; ObjectAttributes
0x140078254  mov     edx, 100001h; DesiredAccess
0x140078259  lea     rcx, [rsp+1D0h+FileHandle]; FileHandle
0x14007825e  call    cs:__imp_NtOpenFile
0x140078265  nop     dword ptr [rax+rax+00h]
0x14007826a  test    eax, eax
0x14007826c  jns     short loc_140078283
0x14007826e  mov     ecx, eax; Status
0x140078270  call    cs:__imp_RtlNtStatusToDosError
0x140078277  nop     dword ptr [rax+rax+00h]
0x14007827c  mov     ebx, eax
0x14007827e  jmp     loc_1400785B8
0x140078283  mov     rbx, [rsp+1D0h+FileHandle]
0x140078288  mov     [rsp+1D0h+var_168], rbx
0x14007828d  mov     al, 1
0x14007828f  mov     ecx, [rdi]
0x140078291  mov     [rsp+1D0h+var_160], ecx
0x140078295  mov     rdi, [rdi+8]
0x140078299  mov     [rbp+0D0h+var_150], rdi
0x14007829d  mov     [rsp+1D0h+RestartScan], al; RestartScan
0x1400782a1  mov     [rsp+1D0h+FileName], r12; FileName
0x1400782a6  mov     [rsp+1D0h+ReturnSingleEntry], r12b; ReturnSingleEntry
0x1400782ab  mov     [rsp+1D0h+FileInformationClass], 26h ; '&'; FileInformationClass
0x1400782b3  mov     [rsp+1D0h+Length], ecx; Length
0x1400782b7  mov     qword ptr [rsp+1D0h+OpenOptions], rdi; FileInformation
0x1400782bc  lea     rax, [rbp+0D0h+IoStatusBlock]
0x1400782c0  mov     qword ptr [rsp+1D0h+ShareAccess], rax; IoStatusBlock
0x1400782c5  xor     r9d, r9d; ApcContext
0x1400782c8  xor     r8d, r8d; ApcRoutine
0x1400782cb  xor     edx, edx; Event
0x1400782cd  mov     rcx, rbx; FileHandle
0x1400782d0  call    cs:__imp_NtQueryDirectoryFile
0x1400782d7  nop     dword ptr [rax+rax+00h]
0x1400782dc  test    eax, eax
0x1400782de  js      loc_140078592
0x1400782e4  mov     [rsp+1D0h+var_170], r12b
0x1400782e9  mov     r8d, [rdi+3Ch]
0x1400782ed  shr     r8, 1
0x1400782f0  lea     rdx, [rdi+50h]
0x1400782f4  lea     rcx, [rbp+0D0h+var_D0]
0x1400782f8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG_K@Z; std::wstring::wstring(ushort const * const,unsigned __int64)
0x1400782fd  nop
0x1400782fe  lea     r8, [rbp+0D0h+var_D0]
0x140078302  lea     rdx, [rbp+0D0h+var_B0]
0x140078306  lea     rcx, [rbp+0D0h+var_90]
0x14007830a  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@0@Z; std::operator+<ushort>(std::wstring const &,std::wstring const &)
0x14007830f  nop
0x140078310  xorps   xmm0, xmm0
0x140078313  movups  [rbp+0D0h+var_E0], xmm0
0x140078317  mov     rdx, [rdi+48h]
0x14007831b  xorps   xmm1, xmm1
0x14007831e  movdqa  [rbp+0D0h+var_E0], xmm1
0x140078323  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x140078327  jz      loc_140078578
0x14007832d  test    rdx, rdx
0x140078330  jz      short loc_140078388
0x140078332  mov     rax, rdx
0x140078335  shr     rax, 3Ch
0x140078339  lea     r8d, ds:0[rax*4]
0x140078341  test    r8d, r8d
0x140078344  jz      loc_140078578
0x14007834a  mov     rax, 0FFFFFFFFFFFFFFFh
0x140078354  and     rdx, rax
0x140078357  lea     ecx, [r8-4]
0x14007835b  mov     eax, 0Fh
0x140078360  shl     rax, cl
0x140078363  test    rdx, rax
0x140078366  jz      loc_140078578
0x14007836c  mov     ecx, r8d
0x14007836f  mov     eax, 1
0x140078374  shl     rax, cl
0x140078377  dec     rax
0x14007837a  and     rax, rdx
0x14007837d  mov     qword ptr [rbp+0D0h+var_E0+8], rax
0x140078381  shr     rdx, cl
0x140078384  mov     qword ptr [rbp+0D0h+var_E0], rdx
0x140078388  test    byte ptr [rdi+38h], 10h
0x14007838c  jz      loc_1400784A2
0x140078392  lea     rcx, asc_1401E89EC; "."
0x140078399  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x14007839e  mov     r9, rax
0x1400783a1  lea     rcx, [rbp+0D0h+var_D0]
0x1400783a5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1400783aa  mov     rcx, rax
0x1400783ad  lea     r8, asc_1401E89EC; "."
0x1400783b4  mov     rdx, [rbp+0D0h+var_C0]
0x1400783b8  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1400783bd  test    al, al
0x1400783bf  jnz     loc_1400784A2
0x1400783c5  lea     rcx, asc_1401E89F0; ".."
0x1400783cc  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1400783d1  mov     r9, rax
0x1400783d4  lea     rcx, [rbp+0D0h+var_D0]
0x1400783d8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1400783dd  mov     rcx, rax
0x1400783e0  lea     r8, asc_1401E89F0; ".."
0x1400783e7  mov     rdx, [rbp+0D0h+var_C0]
0x1400783eb  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1400783f0  test    al, al
0x1400783f2  jnz     loc_1400784A2
0x1400783f8  lea     rdx, [r15+310h]
0x1400783ff  lea     rcx, [rbp+0D0h+var_90]
0x140078403  call    ?IsPathExcluded@DedupUtil@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@3@@Z; DedupUtil::IsPathExcluded(std::wstring const &,std::unordered_set<std::wstring> const &)
0x140078408  test    al, al
0x14007840a  jnz     loc_1400784A2
0x140078410  lea     r8, StringValue; "\\"
0x140078417  lea     rdx, [rbp+0D0h+var_90]
0x14007841b  lea     rcx, [rbp+0D0h+var_70]
0x14007841f  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x140078424  mov     r13, rax
0x140078427  mov     rcx, [r14+20h]
0x14007842b  inc     rcx
0x14007842e  cmp     [r14+10h], rcx
0x140078432  ja      short loc_14007843C
0x140078434  mov     rcx, r14
0x140078437  call    ?_Growmap@?$deque@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAX_K@Z; std::deque<std::wstring>::_Growmap(unsigned __int64)
0x14007843c  mov     rax, [r14+10h]
0x140078440  dec     rax
0x140078443  and     [r14+18h], rax
0x140078447  mov     r12, [r14+18h]
0x14007844b  add     r12, [r14+20h]
0x14007844f  mov     rdx, r12
0x140078452  mov     rcx, r14
0x140078455  call    ?_Getblock@?$deque@UDedupNotifyRecord@?$DataChangeListener@VReFsDedupService@ReFs@FileSystem@Windows@@@ReFs@FileSystem@Windows@@V?$allocator@UDedupNotifyRecord@?$DataChangeListener@VReFsDedupService@ReFs@FileSystem@Windows@@@ReFs@FileSystem@Windows@@@std@@@std@@AEBA_J_K@Z; std::deque<Windows::FileSystem::ReFs::DataChangeListener<Windows::FileSystem::ReFs::ReFsDedupService>::DedupNotifyRecord,std::allocator<Windows::FileSystem::ReFs::DataChangeListener<Windows::FileSystem::ReFs::ReFsDedupService>::DedupNotifyRecord>>::_Getblock(unsigned __int64)
0x14007845a  mov     rsi, rax
0x14007845d  mov     rcx, [r14+8]
0x140078461  cmp     qword ptr [rcx+rax*8], 0
0x140078466  jnz     short loc_14007847A
0x140078468  mov     ecx, 20h ; ' '
0x14007846d  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x140078472  mov     rcx, [r14+8]
0x140078476  mov     [rcx+rsi*8], rax
0x14007847a  mov     rdx, r12
0x14007847d  mov     rcx, r14
0x140078480  call    ?_Address_subscript@?$_Deque_val@U?$_Deque_simple_types@UDedupNotifyRecord@?$DataChangeListener@VReFsDedupService@ReFs@FileSystem@Windows@@@ReFs@FileSystem@Windows@@@std@@@std@@QEAAPEAUDedupNotifyRecord@?$DataChangeListener@VReFsDedupService@ReFs@FileSystem@Windows@@@ReFs@FileSystem@Windows@@_K@Z; std::_Deque_val<std::_Deque_simple_types<Windows::FileSystem::ReFs::DataChangeListener<Windows::FileSystem::ReFs::ReFsDedupService>::DedupNotifyRecord>>::_Address_subscript(unsigned __int64)
0x140078485  mov     r8, r13
0x140078488  mov     rdx, rax
0x14007848b  call    ??$construct@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@?$_Default_allocator_traits@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV31@@Z; std::_Default_allocator_traits<std::allocator<std::_List_node<std::wstring,void *>>>::construct<std::wstring,std::wstring>(std::allocator<std::_List_node<std::wstring,void *>> &,std::wstring * const,std::wstring &&)
0x140078490  inc     qword ptr [r14+20h]
0x140078494  lea     rcx, [rbp+0D0h+var_70]
0x140078498  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14007849d  xor     r12d, r12d
0x1400784a0  jmp     short loc_140078506
0x1400784a2  mov     eax, [r15+0F0h]
0x1400784a9  cmp     [rdi+28h], rax
0x1400784ad  jl      short loc_140078506
0x1400784af  mov     r8, rdi
0x1400784b2  lea     rdx, [rbp+0D0h+var_90]
0x1400784b6  mov     rcx, r15; this
0x1400784b9  call    ?IsExcludedFile@CDedupOptimizer@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_FILE_ID_FULL_DIR_INFORMATION@@@Z; CDedupOptimizer::IsExcludedFile(std::wstring const &,_FILE_ID_FULL_DIR_INFORMATION const &)
0x1400784be  test    al, al
0x1400784c0  jnz     short loc_140078506
0x1400784c2  test    dword ptr [rdi+38h], 400h
0x1400784c9  jnz     short loc_140078506
0x1400784cb  mov     [rbp+0D0h+var_128], r12
0x1400784cf  mov     rax, [rdi+28h]
0x1400784d3  mov     [rbp+0D0h+var_120], rax
0x1400784d7  lea     r8, [rbp+0D0h+var_128]; struct _RANGE *
0x1400784db  lea     rdx, [rbp+0D0h+var_E0]; union SmsBigIdentifier *
0x1400784df  mov     rcx, [r15+0E8h]; this
0x1400784e6  call    ?AddFileRange@CHashIndex@@QEAAKAEBTSmsBigIdentifier@@AEBU_RANGE@@@Z; CHashIndex::AddFileRange(SmsBigIdentifier const &,_RANGE const &)
0x1400784eb  mov     esi, eax
0x1400784ed  test    eax, eax
0x1400784ef  jnz     short loc_1400784FB
0x1400784f1  lock inc qword ptr [r15+1A0h]
0x1400784f9  jmp     short loc_140078506
0x1400784fb  mov     ecx, esi
0x1400784fd  call    IsFatalDedupError
0x140078502  test    al, al
0x140078504  jnz     short loc_14007854C
0x140078506  cmp     [rdi], r12d
0x140078509  jz      short loc_140078528
0x14007850b  mov     eax, [rdi]
0x14007850d  add     rdi, rax
0x140078510  lea     rcx, [rbp+0D0h+var_90]
0x140078514  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140078519  nop
0x14007851a  lea     rcx, [rbp+0D0h+var_D0]
0x14007851e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140078523  jmp     loc_1400782E9
0x140078528  lea     rcx, [rbp+0D0h+var_90]
0x14007852c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140078531  nop
0x140078532  lea     rcx, [rbp+0D0h+var_D0]
0x140078536  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14007853b  mov     al, [rsp+1D0h+var_170]
0x14007853f  mov     rdi, [rbp+0D0h+var_150]
0x140078543  mov     ecx, [rsp+1D0h+var_160]
0x140078547  jmp     loc_14007829D
0x14007854c  lea     rcx, [rbp+0D0h+var_90]
0x140078550  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140078555  nop
0x140078556  lea     rcx, [rbp+0D0h+var_D0]
0x14007855a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14007855f  nop
0x140078560  lea     rcx, [rsp+1D0h+var_168]
0x140078565  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14007856a  nop
0x14007856b  lea     rcx, [rbp+0D0h+var_B0]
0x14007856f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140078574  mov     eax, esi
0x140078576  jmp     short loc_1400785C3
0x140078578  mov     ebx, 57h ; 'W'
0x14007857d  lea     rcx, [rbp+0D0h+var_90]
0x140078581  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140078586  nop
0x140078587  lea     rcx, [rbp+0D0h+var_D0]
0x14007858b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140078590  jmp     short loc_1400785AD
0x140078592  cmp     eax, 80000006h
0x140078597  jnz     short loc_14007859D
0x140078599  xor     ecx, ecx
0x14007859b  jmp     short loc_14007859F
0x14007859d  mov     ecx, eax; Status
0x14007859f  call    cs:__imp_RtlNtStatusToDosError
0x1400785a6  nop     dword ptr [rax+rax+00h]
0x1400785ab  mov     ebx, eax
0x1400785ad  lea     rcx, [rsp+1D0h+var_168]
0x1400785b2  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400785b7  nop
0x1400785b8  lea     rcx, [rbp+0D0h+var_B0]
0x1400785bc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400785c1  mov     eax, ebx
0x1400785c3  mov     rcx, [rbp+0D0h+var_50]
0x1400785ca  xor     rcx, rsp; StackCookie
0x1400785cd  call    __security_check_cookie
0x1400785d2  add     rsp, 198h
0x1400785d9  pop     r15
0x1400785db  pop     r14
0x1400785dd  pop     r13
0x1400785df  pop     r12
0x1400785e1  pop     rdi
0x1400785e2  pop     rsi
0x1400785e3  pop     rbx
0x1400785e4  pop     rbp
0x1400785e5  retn
```
