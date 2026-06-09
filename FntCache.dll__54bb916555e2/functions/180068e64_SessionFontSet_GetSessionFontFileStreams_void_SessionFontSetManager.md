# SessionFontSet::GetSessionFontFileStreams(void *,SessionFontSetManager *)

- ea: `0x180068e64`
- end: `0x1800695c9`
- name: `?GetSessionFontFileStreams@SessionFontSet@@AEAA?AV?$vector@V?$ComPtr@UIDWriteFontFileStreamInternal@@@@V?$allocator@V?$ComPtr@UIDWriteFontFileStreamInternal@@@@@std@@@std@@PEAXPEAVSessionFontSetManager@@@Z`
- size: `1893`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x180011a60`

## callees

- `0x180004810`
- `0x180008780`
- `0x18000ee1c`
- `0x18000f354`
- `0x18000f7bc`
- `0x180028c50`
- `0x18002e118`
- `0x18004d664`
- `0x180068544`
- `0x18006868c`
- `0x180068e64`
- `0x180069650`
- `0x18009d96c`
- `0x1800a3238`
- `0x1800a371c`
- `0x1800a47d4`
- `0x1800a4d10`
- `0x1800a5658`
- `0x1800a596c`
- `0x1800a9f10`
- `0x1800aa650`
- `0x1800ab174`
- `0x1800ab180`
- `0x1800ab2e0`
- `0x1800b6498`
- `0x1800b6a98`
- `0x1800b6b98`
- `0x1800b6cb4`
- `0x1800b6ec8`
- `0x1800e6010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180069185`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180069185`
- `ntdll!RtlNtPathNameToDosPathName` at `0x1800693be`
- `ntdll!RtlNtPathNameToDosPathName` at `0x1800693be`
- `ntdll!RtlpEnsureBufferSize` at `0x18006928b`
- `ntdll!RtlpEnsureBufferSize` at `0x18006928b`
- `ntdll!RtlInitUnicodeString` at `0x180069208`
- `ntdll!RtlInitUnicodeString` at `0x18006923f`
- `ntdll!RtlInitUnicodeString` at `0x1800692b5`
- `ntdll!RtlInitUnicodeString` at `0x1800692c2`
- `ntdll!RtlInitUnicodeString` at `0x1800692f2`
- `ntdll!RtlInitUnicodeString` at `0x180069315`
- `ntdll!RtlInitUnicodeString` at `0x180069208`
- `ntdll!RtlInitUnicodeString` at `0x18006923f`
- `ntdll!RtlInitUnicodeString` at `0x1800692b5`
- `ntdll!RtlInitUnicodeString` at `0x1800692c2`
- `ntdll!RtlInitUnicodeString` at `0x1800692f2`
- `ntdll!RtlInitUnicodeString` at `0x180069315`
- `ext-ms-win-gdi-font-l1-1-2!GetProcessSessionFonts` at `0x180068f2d`
- `ext-ms-win-gdi-font-l1-1-2!GetProcessSessionFonts` at `0x180068f2d`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void *__fastcall SessionFontSet::GetSessionFontFileStreams(__int64 a1, void *a2, __int64 a3)
{
  void *v4; // rbx
  int v6; // r12d
  int ProcessSessionFonts; // r11d
  unsigned __int64 v8; // r8
  char *v9; // rbx
  PCWSTR v10; // rsi
  unsigned __int64 v11; // rcx
  const WCHAR *v12; // rax
  size_t v13; // rbx
  char *v14; // rbx
  PCWSTR v15; // rsi
  unsigned __int64 v16; // rcx
  const WCHAR *v17; // rax
  size_t v18; // rbx
  unsigned __int64 v19; // r13
  const WCHAR *v20; // rbx
  const WCHAR *v21; // rcx
  unsigned __int64 v22; // rax
  struct DWrite::RefString::Data *v23; // r14
  const char *v24; // rdx
  int v25; // r9d
  NtUnicodeString *v26; // rax
  int v27; // ebx
  NTSTATUS v28; // eax
  PWSTR Buffer; // rbx
  int v30; // eax
  __int64 v31; // rbx
  __int64 v33; // [rsp+30h] [rbp-D0h] BYREF
  PCWSTR SourceString[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v35; // [rsp+48h] [rbp-B8h]
  unsigned __int64 v36; // [rsp+50h] [rbp-B0h]
  char *v37; // [rsp+58h] [rbp-A8h] BYREF
  char *v38; // [rsp+60h] [rbp-A0h]
  __int64 v39; // [rsp+68h] [rbp-98h]
  __int64 v40; // [rsp+70h] [rbp-90h]
  const WCHAR *v41; // [rsp+78h] [rbp-88h] BYREF
  __int64 v42; // [rsp+80h] [rbp-80h] BYREF
  _QWORD *v43; // [rsp+88h] [rbp-78h]
  _QWORD *v44; // [rsp+90h] [rbp-70h]
  void *v45; // [rsp+98h] [rbp-68h]
  unsigned __int64 trivial_2; // [rsp+A0h] [rbp-60h]
  int v47; // [rsp+A8h] [rbp-58h]
  struct DWrite::RefString::Data *v48; // [rsp+B0h] [rbp-50h] BYREF
  PWSTR v49; // [rsp+B8h] [rbp-48h]
  _UNICODE_STRING DestinationString; // [rsp+C0h] [rbp-40h] BYREF
  struct _UNICODE_STRING v51; // [rsp+D0h] [rbp-30h] BYREF
  struct _UNICODE_STRING v52; // [rsp+E0h] [rbp-20h] BYREF
  struct _UNICODE_STRING v53; // [rsp+F0h] [rbp-10h] BYREF
  struct _UNICODE_STRING v54; // [rsp+100h] [rbp+0h] BYREF
  struct _UNICODE_STRING v55; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v56[40]; // [rsp+120h] [rbp+20h] BYREF
  char v57[24]; // [rsp+148h] [rbp+48h] BYREF
  _WORD v58[260]; // [rsp+160h] [rbp+60h] BYREF
  _RTL_UNICODE_STRING_BUFFER Path; // [rsp+368h] [rbp+268h] BYREF

  v4 = a2;
  v45 = a2;
  v40 = a1;
  trivial_2 = (unsigned __int64)a2;
  v6 = 0;
  v47 = 0;
  if ( !(unsigned __int8)IsGetProcessSessionFontsPresent() )
  {
    std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(v4);
    return v4;
  }
  EventSource<ComInterfaceList<SessionFontSet,ISessionFontSet>,ISessionFontSet>::LogEvent<>(a1, 0x73656C6966746567LL);
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(&v37);
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(SourceString);
  while ( 1 )
  {
    LODWORD(v33) = (v38 - v37) >> 3;
    LODWORD(v36) = SourceString[1] - SourceString[0];
    ProcessSessionFonts = GetProcessSessionFonts(a3, v37, &v33);
    v8 = (v38 - v37) >> 3;
    if ( (unsigned int)v33 > v8 )
    {
LABEL_9:
      if ( (unsigned int)v33 <= (unsigned __int64)((v39 - (__int64)v37) >> 3) )
        v38 = (char *)std::_Uninitialized_value_construct_n<std::allocator<Win32Handle>>(v38, (unsigned int)v33 - v8);
      else
        std::vector<Win32Handle>::_Resize_reallocate<std::_Value_init_tag>(&v37);
      goto LABEL_12;
    }
    if ( (unsigned int)v36 <= (unsigned __int64)(SourceString[1] - SourceString[0]) )
      break;
    if ( (unsigned int)v33 < v8 )
    {
      v9 = &v37[8 * (unsigned int)v33];
      std::_Destroy_range<std::allocator<Win32Handle>>(v9, v38);
      v38 = v9;
      goto LABEL_12;
    }
    if ( (unsigned int)v33 > v8 )
      goto LABEL_9;
LABEL_12:
    v10 = SourceString[1];
    v11 = SourceString[1] - SourceString[0];
    if ( (unsigned int)v36 < v11 )
    {
      v12 = &SourceString[0][(unsigned int)v36];
      goto LABEL_18;
    }
    if ( (unsigned int)v36 > v11 )
    {
      if ( (unsigned int)v36 <= (unsigned __int64)((signed __int64)(v35 - (unsigned __int64)SourceString[0]) >> 1) )
      {
        v13 = (unsigned int)v36 - v11;
        memset_0((void *)SourceString[1], 0, v13 * 2);
        v12 = &v10[v13];
LABEL_18:
        SourceString[1] = v12;
      }
      else
      {
        std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(SourceString, (unsigned int)v36);
      }
    }
  }
  if ( ProcessSessionFonts )
  {
    if ( (unsigned int)v33 < v8 )
    {
      v14 = &v37[8 * (unsigned int)v33];
      std::_Destroy_range<std::allocator<Win32Handle>>(v14, v38);
      v38 = v14;
    }
    v15 = SourceString[1];
    v16 = SourceString[1] - SourceString[0];
    if ( (unsigned int)v36 < v16 )
    {
      v17 = &SourceString[0][(unsigned int)v36];
      goto LABEL_28;
    }
    if ( (unsigned int)v36 > v16 )
    {
      if ( (unsigned int)v36 <= (unsigned __int64)((signed __int64)(v35 - (unsigned __int64)SourceString[0]) >> 1) )
      {
        v18 = (unsigned int)v36 - v16;
        memset_0((void *)SourceString[1], 0, v18 * 2);
        v17 = &v15[v18];
LABEL_28:
        SourceString[1] = v17;
      }
      else
      {
        std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(SourceString, (unsigned int)v36);
      }
    }
  }
  else
  {
    if ( v37 != v38 )
    {
      std::_Destroy_range<std::allocator<Win32Handle>>(v37, v38);
      v38 = v37;
    }
    if ( SourceString[0] != SourceString[1] )
      SourceString[1] = SourceString[0];
    EventSource<ComInterfaceList<SessionFontSet,ISessionFontSet>,ISessionFontSet>::LogLastError(
      a1,
      0x73656C6966746567LL,
      1215);
  }
  v19 = (v38 - v37) >> 3;
  if ( !v19 )
  {
    v4 = v45;
    std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(v45);
    goto LABEL_79;
  }
  GetFontsDirectory(&v48);
  Path.ByteBuffer.Buffer = (PUCHAR)v58;
  Path.ByteBuffer.Size = 520;
  Path.ByteBuffer.StaticBuffer = (PUCHAR)v58;
  Path.ByteBuffer.StaticSize = 520;
  Path.String.Buffer = v58;
  v58[0] = 0;
  *(_DWORD *)&Path.String.Length = 34078720;
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(&v42);
  v41 = (const WCHAR *)v19;
  if ( v19 > ((__int64)v44 - v42) >> 3 )
  {
    if ( v19 > 0x1FFFFFFFFFFFFFFFLL )
      std::_Xlength_error("vector too long");
    std::vector<ComPtr<IDWriteFontFileStreamInternal>>::_Reallocate<0>(&v42, &v41);
  }
  v20 = SourceString[0];
  v21 = &SourceString[0][SourceString[1] - SourceString[0]];
  v41 = v21;
  v22 = 0;
  v23 = v48;
  while ( 2 )
  {
    v36 = v22;
    if ( v22 < v19 )
    {
      trivial_2 = _std_find_trivial_2(v20, v21, 0);
      if ( trivial_2 >= (unsigned __int64)v41 )
      {
        FailAssert(0x4DAu, v24);
        __debugbreak();
      }
      Path.String.Length = 0;
      RtlInitUnicodeString(&DestinationString, v20);
      if ( Path.String.Length + (unsigned __int64)DestinationString.Length + 2 <= 0xFFFE )
      {
        v6 |= 2u;
        RtlInitUnicodeString(&v51, v20);
        if ( Path.String.Length + (unsigned __int64)v51.Length + 2 <= Path.ByteBuffer.Size
          || (v6 |= 4u,
              v26 = NtUnicodeString::NtUnicodeString((NtUnicodeString *)v57, v20),
              RtlpEnsureBufferSize(0, &Path.ByteBuffer, Path.String.Length + 2LL + *(unsigned __int16 *)v26) >= 0) )
        {
          Path.String.Buffer = (PWSTR)Path.ByteBuffer.Buffer;
          RtlInitUnicodeString(&v52, v20);
          RtlInitUnicodeString(&v53, v20);
          memmove_0(&Path.String.Buffer[(unsigned __int64)Path.String.Length >> 1], v53.Buffer, v52.Length);
          RtlInitUnicodeString(&v54, v20);
          Path.String.MaximumLength = Path.String.Length + v54.Length + 2;
          RtlInitUnicodeString(&v55, v20);
          Path.String.Length += v55.Length;
          *(PWSTR)((char *)Path.String.Buffer + (Path.String.Length & 0xFFFE)) = 0;
          v25 = 0;
          v6 |= 0x78u;
        }
        else
        {
          v25 = -1073741801;
        }
      }
      else
      {
        v25 = -1073741562;
      }
      if ( (v6 & 0x40) != 0 )
        v6 &= ~0x40u;
      if ( (v6 & 0x20) != 0 )
        v6 &= ~0x20u;
      if ( (v6 & 0x10) != 0 )
        v6 &= ~0x10u;
      if ( (v6 & 8) != 0 )
        v6 &= ~8u;
      if ( (v6 & 4) != 0 )
        v6 &= ~4u;
      if ( (v6 & 2) != 0 )
        v6 &= ~2u;
      v27 = v40;
      if ( v25 < 0 )
        EventLogger::LogEvent<long,EventTag,unsigned int>(
          v40 + 16,
          1936942419,
          1869771365,
          v25 | 0x10000000,
          0x73656C6966746567LL,
          1249);
      v28 = RtlNtPathNameToDosPathName(0, &Path, 0, 0);
      if ( v28 < 0 )
        EventLogger::LogEvent<long,EventTag,unsigned int>(
          v27 + 16,
          1936942419,
          1869771365,
          v28 | 0x10000000,
          0x73656C6966746567LL,
          1255);
      Buffer = Path.String.Buffer;
      v49 = Path.String.Buffer;
      if ( (unsigned int)Path.String.Length < *((_DWORD *)v23 + 1)
        || (unsigned int)CompareInvariantIgnoreCase(
                           Path.String.Buffer,
                           *((unsigned int *)v23 + 1),
                           (PCNZWCH)v23 + 4,
                           *((unsigned int *)v23 + 1)) )
      {
        File::File(v56, &v37[8 * v36]);
        v33 = 0;
        v30 = LocalFileLoader::CreateStreamFromFile(v56, Buffer, &v33);
        if ( v30 < 0 )
        {
          EventLogger::LogEvent<long,EventTag,unsigned int>(
            v40 + 16,
            1936942419,
            1869771365,
            v30,
            0x73656C6966746567LL,
            1296);
        }
        else
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 80LL))(v33);
          if ( v43 != v44 )
          {
            v31 = 0;
            *v43++ = v33;
            goto LABEL_73;
          }
          std::vector<ComPtr<IDWriteFontFileStreamInternal>>::_Emplace_reallocate<ComPtr<IDWriteFontFileStreamInternal>>(
            &v42,
            (__int64)v43,
            &v33);
        }
        v31 = v33;
LABEL_73:
        EventLogger::LogEvent<wchar_t const *>(v40 + 16, 0x6E6F6973736553LL, 0x73656C6966746567LL, v49);
        if ( v31 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
        File::Close((File *)v56);
      }
      v20 = (const WCHAR *)(trivial_2 + 2);
      v22 = v36 + 1;
      v21 = v41;
      continue;
    }
    break;
  }
  v4 = v45;
  std::vector<GlyphPaintData::GradientStop>::vector<GlyphPaintData::GradientStop>(v45, &v42);
  std::vector<ComPtr<IDWriteFontFileStreamInternal>>::_Tidy(&v42);
  NtUnicodeStringBuffer::~NtUnicodeStringBuffer((NtUnicodeStringBuffer *)v58);
  DWrite::RefString::DecrementRef(v23);
LABEL_79:
  if ( SourceString[0] )
  {
    std::_Deallocate<16>((void *)SourceString[0], 2 * ((signed __int64)(v35 - (unsigned __int64)SourceString[0]) >> 1));
    *(_OWORD *)SourceString = 0;
    v35 = 0;
  }
  if ( v37 )
  {
    std::_Destroy_range<std::allocator<Win32Handle>>(v37, v38);
    std::_Deallocate<16>(v37, (v39 - (_QWORD)v37) & 0xFFFFFFFFFFFFFFF8uLL);
  }
  return v4;
}

```

## disassembly

```asm
0x180068e64  mov     [rsp-8+arg_18], rbx
0x180068e69  push    rbp
0x180068e6a  push    rsi
0x180068e6b  push    rdi
0x180068e6c  push    r12
0x180068e6e  push    r13
0x180068e70  push    r14
0x180068e72  push    r15
0x180068e74  lea     rbp, [rsp-2B0h]
0x180068e7c  sub     rsp, 3B0h
0x180068e83  mov     rax, cs:__security_cookie
0x180068e8a  xor     rax, rsp
0x180068e8d  mov     [rbp+2E0h+Path.ByteBuffer.ReservedForIMalloc], rax
0x180068e94  mov     r15, r8
0x180068e97  mov     rbx, rdx
0x180068e9a  mov     [rbp+2E0h+var_348], rdx
0x180068e9e  mov     r14, rcx
0x180068ea1  mov     [rsp+3E0h+var_370], rcx
0x180068ea6  mov     [rbp+2E0h+var_340], rdx
0x180068eaa  xor     r12d, r12d
0x180068ead  mov     [rbp+2E0h+var_338], r12d
0x180068eb1  call    IsGetProcessSessionFontsPresent
0x180068eb6  test    al, al
0x180068eb8  jnz     short loc_180068EC7
0x180068eba  mov     rcx, rbx; void *
0x180068ebd  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x180068ec2  jmp     loc_18006959C
0x180068ec7  mov     rdi, 73656C6966746567h
0x180068ed1  mov     rdx, rdi
0x180068ed4  mov     rcx, r14
0x180068ed7  call    ??$LogEvent@$$V@?$EventSource@V?$ComInterfaceList@VSessionFontSet@@UISessionFontSet@@@@UISessionFontSet@@@@QEBAXVEventTag@@@Z; EventSource<ComInterfaceList<SessionFontSet,ISessionFontSet>,ISessionFontSet>::LogEvent<>(EventTag)
0x180068edc  lea     rcx, [rsp+3E0h+var_388]; void *
0x180068ee1  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x180068ee6  nop
0x180068ee7  lea     rcx, [rsp+3E0h+SourceString]; void *
0x180068eec  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x180068ef1  nop
0x180068ef2  mov     rdx, [rsp+3E0h+var_388]
0x180068ef7  mov     rax, [rsp+3E0h+var_380]
0x180068efc  sub     rax, rdx
0x180068eff  sar     rax, 3
0x180068f03  mov     dword ptr [rsp+3E0h+var_3B0], eax
0x180068f07  mov     r9, [rsp+3E0h+SourceString]
0x180068f0c  mov     rax, [rsp+3E0h+SourceString+8]
0x180068f11  sub     rax, r9
0x180068f14  sar     rax, 1
0x180068f17  mov     dword ptr [rsp+3E0h+var_390], eax
0x180068f1b  lea     rax, [rsp+3E0h+var_390]
0x180068f20  mov     [rsp+3E0h+var_3C0], rax
0x180068f25  lea     r8, [rsp+3E0h+var_3B0]
0x180068f2a  mov     rcx, r15
0x180068f2d  call    cs:__imp_GetProcessSessionFonts
0x180068f33  mov     r11d, eax
0x180068f36  mov     r9, [rsp+3E0h+var_388]
0x180068f3b  mov     r10, [rsp+3E0h+var_380]
0x180068f40  mov     r8, r10
0x180068f43  sub     r8, r9
0x180068f46  sar     r8, 3
0x180068f4a  mov     edx, dword ptr [rsp+3E0h+var_3B0]
0x180068f4e  cmp     rdx, r8
0x180068f51  ja      short loc_180068F8A
0x180068f53  mov     rcx, [rsp+3E0h+SourceString+8]
0x180068f58  sub     rcx, [rsp+3E0h+SourceString]
0x180068f5d  sar     rcx, 1
0x180068f60  mov     eax, dword ptr [rsp+3E0h+var_390]
0x180068f64  cmp     rax, rcx
0x180068f67  jbe     loc_180069022
0x180068f6d  cmp     rdx, r8
0x180068f70  jnb     short loc_180068F88
0x180068f72  lea     rbx, [r9+rdx*8]
0x180068f76  mov     rdx, r10
0x180068f79  mov     rcx, rbx
0x180068f7c  call    ??$_Destroy_range@V?$allocator@VWin32Handle@@@std@@@std@@YAXPEAVWin32Handle@@QEAV1@AEAV?$allocator@VWin32Handle@@@0@@Z; std::_Destroy_range<std::allocator<Win32Handle>>(Win32Handle *,Win32Handle * const,std::allocator<Win32Handle> &)
0x180068f81  mov     [rsp+3E0h+var_380], rbx
0x180068f86  jmp     short loc_180068FB7
0x180068f88  jbe     short loc_180068FB7
0x180068f8a  mov     rax, [rsp+3E0h+var_378]
0x180068f8f  sub     rax, r9
0x180068f92  sar     rax, 3
0x180068f96  cmp     rdx, rax
0x180068f99  jbe     short loc_180068FA7
0x180068f9b  lea     rcx, [rsp+3E0h+var_388]
0x180068fa0  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@VWin32Handle@@V?$allocator@VWin32Handle@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<Win32Handle>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180068fa5  jmp     short loc_180068FB7
0x180068fa7  sub     rdx, r8
0x180068faa  mov     rcx, r10
0x180068fad  call    ??$_Uninitialized_value_construct_n@V?$allocator@VWin32Handle@@@std@@@std@@YAPEAVWin32Handle@@PEAV1@_KAEAV?$allocator@VWin32Handle@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<Win32Handle>>(Win32Handle *,unsigned __int64,std::allocator<Win32Handle> &)
0x180068fb2  mov     [rsp+3E0h+var_380], rax
0x180068fb7  mov     ebx, dword ptr [rsp+3E0h+var_390]
0x180068fbb  mov     rdx, [rsp+3E0h+SourceString]
0x180068fc0  mov     rsi, [rsp+3E0h+SourceString+8]
0x180068fc5  mov     rcx, rsi
0x180068fc8  sub     rcx, rdx
0x180068fcb  sar     rcx, 1
0x180068fce  cmp     rbx, rcx
0x180068fd1  jnb     short loc_180068FD9
0x180068fd3  lea     rax, [rdx+rbx*2]
0x180068fd7  jmp     short loc_180069018
0x180068fd9  jbe     loc_180068EF2
0x180068fdf  mov     rax, [rsp+3E0h+var_398]
0x180068fe4  sub     rax, rdx
0x180068fe7  sar     rax, 1
0x180068fea  cmp     rbx, rax
0x180068fed  jbe     short loc_180069001
0x180068fef  mov     rdx, rbx
0x180068ff2  lea     rcx, [rsp+3E0h+SourceString]
0x180068ff7  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@_WV?$allocator@_W@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180068ffc  jmp     loc_180068EF2
0x180069001  sub     rbx, rcx
0x180069004  add     rbx, rbx
0x180069007  mov     r8, rbx; Size
0x18006900a  xor     edx, edx; Val
0x18006900c  mov     rcx, rsi; void *
0x18006900f  call    memset_0
0x180069014  lea     rax, [rbx+rsi]
0x180069018  mov     [rsp+3E0h+SourceString+8], rax
0x18006901d  jmp     loc_180068EF2
0x180069022  test    r11d, r11d
0x180069025  jz      short loc_1800690A1
0x180069027  cmp     rdx, r8
0x18006902a  jnb     short loc_180069040
0x18006902c  lea     rbx, [r9+rdx*8]
0x180069030  mov     rdx, r10
0x180069033  mov     rcx, rbx
0x180069036  call    ??$_Destroy_range@V?$allocator@VWin32Handle@@@std@@@std@@YAXPEAVWin32Handle@@QEAV1@AEAV?$allocator@VWin32Handle@@@0@@Z; std::_Destroy_range<std::allocator<Win32Handle>>(Win32Handle *,Win32Handle * const,std::allocator<Win32Handle> &)
0x18006903b  mov     [rsp+3E0h+var_380], rbx
0x180069040  mov     ebx, dword ptr [rsp+3E0h+var_390]
0x180069044  mov     rdx, [rsp+3E0h+SourceString]
0x180069049  mov     rsi, [rsp+3E0h+SourceString+8]
0x18006904e  mov     rcx, rsi
0x180069051  sub     rcx, rdx
0x180069054  sar     rcx, 1
0x180069057  cmp     rbx, rcx
0x18006905a  jnb     short loc_180069062
0x18006905c  lea     rax, [rdx+rbx*2]
0x180069060  jmp     short loc_18006909A
0x180069062  jbe     short loc_1800690DD
0x180069064  mov     rax, [rsp+3E0h+var_398]
0x180069069  sub     rax, rdx
0x18006906c  sar     rax, 1
0x18006906f  cmp     rbx, rax
0x180069072  jbe     short loc_180069083
0x180069074  mov     rdx, rbx
0x180069077  lea     rcx, [rsp+3E0h+SourceString]
0x18006907c  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@_WV?$allocator@_W@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180069081  jmp     short loc_1800690DD
0x180069083  sub     rbx, rcx
0x180069086  add     rbx, rbx
0x180069089  mov     r8, rbx; Size
0x18006908c  xor     edx, edx; Val
0x18006908e  mov     rcx, rsi; void *
0x180069091  call    memset_0
0x180069096  lea     rax, [rbx+rsi]
0x18006909a  mov     [rsp+3E0h+SourceString+8], rax
0x18006909f  jmp     short loc_1800690DD
0x1800690a1  cmp     r9, r10
0x1800690a4  jz      short loc_1800690BB
0x1800690a6  mov     rdx, r10
0x1800690a9  mov     rcx, r9
0x1800690ac  call    ??$_Destroy_range@V?$allocator@VWin32Handle@@@std@@@std@@YAXPEAVWin32Handle@@QEAV1@AEAV?$allocator@VWin32Handle@@@0@@Z; std::_Destroy_range<std::allocator<Win32Handle>>(Win32Handle *,Win32Handle * const,std::allocator<Win32Handle> &)
0x1800690b1  mov     rax, [rsp+3E0h+var_388]
0x1800690b6  mov     [rsp+3E0h+var_380], rax
0x1800690bb  mov     rax, [rsp+3E0h+SourceString]
0x1800690c0  cmp     rax, [rsp+3E0h+SourceString+8]
0x1800690c5  jz      short loc_1800690CC
0x1800690c7  mov     [rsp+3E0h+SourceString+8], rax
0x1800690cc  mov     r8d, 4BFh
0x1800690d2  mov     rdx, rdi
0x1800690d5  mov     rcx, r14
0x1800690d8  call    ?LogLastError@?$EventSource@V?$ComInterfaceList@VSessionFontSet@@UISessionFontSet@@@@UISessionFontSet@@@@QEBAJVEventTag@@I@Z; EventSource<ComInterfaceList<SessionFontSet,ISessionFontSet>,ISessionFontSet>::LogLastError(EventTag,uint)
0x1800690dd  mov     r13, [rsp+3E0h+var_380]
0x1800690e2  sub     r13, [rsp+3E0h+var_388]
0x1800690e7  sar     r13, 3
0x1800690eb  test    r13, r13
0x1800690ee  jnz     short loc_180069101
0x1800690f0  mov     rbx, [rbp+2E0h+var_348]
0x1800690f4  mov     rcx, rbx; void *
0x1800690f7  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x1800690fc  jmp     loc_180069543
0x180069101  lea     rcx, [rbp+2E0h+var_330]
0x180069105  call    ?GetFontsDirectory@@YA?AVRefString@DWrite@@XZ; GetFontsDirectory(void)
0x18006910a  nop
0x18006910b  lea     rax, [rbp+2E0h+var_280]
0x18006910f  mov     [rbp+2E0h+Path.ByteBuffer.Buffer], rax
0x180069116  mov     ecx, 208h
0x18006911b  mov     [rbp+2E0h+Path.ByteBuffer.Size], rcx
0x180069122  lea     rax, [rbp+2E0h+var_280]
0x180069126  mov     [rbp+2E0h+Path.ByteBuffer.StaticBuffer], rax
0x18006912d  mov     [rbp+2E0h+Path.ByteBuffer.StaticSize], rcx
0x180069134  lea     rax, [rbp+2E0h+var_280]
0x180069138  mov     [rbp+2E0h+Path.String.Buffer], rax
0x18006913f  xor     eax, eax
0x180069141  mov     [rbp+2E0h+var_280], ax
0x180069145  mov     dword ptr [rbp+2E0h+Path.String.Length], 2080000h
0x18006914f  lea     rcx, [rbp+2E0h+var_360]; void *
0x180069153  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x180069158  nop
0x180069159  mov     [rsp+3E0h+var_368], r13
0x18006915e  mov     rax, [rbp+2E0h+var_350]
0x180069162  sub     rax, [rbp+2E0h+var_360]
0x180069166  sar     rax, 3
0x18006916a  cmp     r13, rax
0x18006916d  jbe     short loc_18006919A
0x18006916f  mov     rax, 1FFFFFFFFFFFFFFFh
0x180069179  cmp     r13, rax
0x18006917c  jbe     short loc_18006918C
0x18006917e  lea     rcx, aVectorTooLong; "vector too long"
0x180069185  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18006918c  lea     rdx, [rsp+3E0h+var_368]
0x180069191  lea     rcx, [rbp+2E0h+var_360]
0x180069195  call    ??$_Reallocate@$0A@@?$vector@V?$ComPtr@UIDWriteFontFileStreamInternal@@@@V?$allocator@V?$ComPtr@UIDWriteFontFileStreamInternal@@@@@std@@@std@@AEAAXAEA_K@Z; std::vector<ComPtr<IDWriteFontFileStreamInternal>>::_Reallocate<0>(unsigned __int64 &)
0x18006919a  mov     rbx, [rsp+3E0h+SourceString]
0x18006919f  mov     rax, [rsp+3E0h+SourceString+8]
0x1800691a4  sub     rax, rbx
0x1800691a7  sar     rax, 1
0x1800691aa  lea     rcx, [rbx+rax*2]
0x1800691ae  mov     [rsp+3E0h+var_368], rcx
0x1800691b3  xor     eax, eax
0x1800691b5  mov     rsi, 6E6F6973736553h
0x1800691bf  mov     r15, 726F727265h
0x1800691c9  mov     r14, [rbp+2E0h+var_330]
0x1800691cd  mov     [rsp+3E0h+var_390], rax
0x1800691d2  cmp     rax, r13
0x1800691d5  jnb     loc_180069515
0x1800691db  xor     r8d, r8d
0x1800691de  mov     rdx, rcx
0x1800691e1  mov     rcx, rbx
0x1800691e4  call    __std_find_trivial_2
0x1800691e9  mov     [rbp+2E0h+var_340], rax
0x1800691ed  cmp     rax, [rsp+3E0h+var_368]
0x1800691f2  jnb     loc_18006950A
0x1800691f8  xor     ecx, ecx
0x1800691fa  mov     [rbp+2E0h+Path.String.Length], cx
0x180069201  mov     rdx, rbx; SourceString
0x180069204  lea     rcx, [rbp+2E0h+DestinationString]; DestinationString
0x180069208  call    cs:__imp_RtlInitUnicodeString
0x18006920e  movzx   edx, [rbp+2E0h+DestinationString.Length]
0x180069212  movzx   ecx, [rbp+2E0h+Path.String.Length]
0x180069219  add     rdx, 2
0x18006921d  add     rdx, rcx
0x180069220  cmp     rdx, 0FFFEh
0x180069227  jbe     short loc_180069234
0x180069229  mov     r9d, 0C0000106h
0x18006922f  jmp     loc_180069348
0x180069234  or      r12d, 2
0x180069238  mov     rdx, rbx; SourceString
0x18006923b  lea     rcx, [rbp+2E0h+var_310]; DestinationString
0x18006923f  call    cs:__imp_RtlInitUnicodeString
0x180069245  movzx   ecx, [rbp+2E0h+var_310.Length]
0x180069249  movzx   eax, [rbp+2E0h+Path.String.Length]
0x180069250  add     rcx, 2
0x180069254  add     rcx, rax
0x180069257  cmp     rcx, [rbp+2E0h+Path.ByteBuffer.Size]
0x18006925e  jbe     short loc_1800692A0
0x180069260  or      r12d, 4
0x180069264  mov     rdx, rbx; wchar_t *
0x180069267  lea     rcx, [rbp+2E0h+var_298]; this
0x18006926b  call    ??0NtUnicodeString@@QEAA@QEB_W@Z; NtUnicodeString::NtUnicodeString(wchar_t const * const)
0x180069270  movzx   ecx, [rbp+2E0h+Path.String.Length]
0x180069277  movzx   r8d, word ptr [rax]
0x18006927b  add     rcx, 2
0x18006927f  add     r8, rcx; RequiredSize
0x180069282  lea     rdx, [rbp+2E0h+Path.ByteBuffer]; Buffer
0x180069289  xor     ecx, ecx; Flags
0x18006928b  call    cs:__imp_RtlpEnsureBufferSize
0x180069291  test    eax, eax
0x180069293  jns     short loc_1800692A0
0x180069295  mov     r9d, 0C0000017h
0x18006929b  jmp     loc_180069348
0x1800692a0  mov     rax, [rbp+2E0h+Path.ByteBuffer.Buffer]
0x1800692a7  mov     [rbp+2E0h+Path.String.Buffer], rax
0x1800692ae  mov     rdx, rbx; SourceString
0x1800692b1  lea     rcx, [rbp+2E0h+var_300]; DestinationString
0x1800692b5  call    cs:__imp_RtlInitUnicodeString
0x1800692bb  mov     rdx, rbx; SourceString
0x1800692be  lea     rcx, [rbp+2E0h+var_2F0]; DestinationString
0x1800692c2  call    cs:__imp_RtlInitUnicodeString
0x1800692c8  movzx   r8d, [rbp+2E0h+var_300.Length]; Size
0x1800692cd  movzx   ecx, [rbp+2E0h+Path.String.Length]
0x1800692d4  shr     rcx, 1
0x1800692d7  mov     rax, [rbp+2E0h+Path.String.Buffer]
0x1800692de  lea     rcx, [rax+rcx*2]; void *
0x1800692e2  mov     rdx, [rbp+2E0h+var_2F0.Buffer]; Src
0x1800692e6  call    memmove_0
0x1800692eb  mov     rdx, rbx; SourceString
0x1800692ee  lea     rcx, [rbp+2E0h+var_2E0]; DestinationString
0x1800692f2  call    cs:__imp_RtlInitUnicodeString
0x1800692f8  movzx   eax, [rbp+2E0h+var_2E0.Length]
0x1800692fc  add     ax, 2
0x180069300  add     ax, [rbp+2E0h+Path.String.Length]
0x180069307  mov     [rbp+2E0h+Path.String.MaximumLength], ax
0x18006930e  mov     rdx, rbx; SourceString
0x180069311  lea     rcx, [rbp+2E0h+var_2D0]; DestinationString
0x180069315  call    cs:__imp_RtlInitUnicodeString
0x18006931b  movzx   eax, [rbp+2E0h+Path.String.Length]
0x180069322  add     ax, [rbp+2E0h+var_2D0.Length]
0x180069326  mov     [rbp+2E0h+Path.String.Length], ax
0x18006932d  movzx   edx, ax
0x180069330  and     rdx, 0FFFFFFFFFFFFFFFEh
0x180069334  xor     ecx, ecx
  ... truncated ...
```
