# DiagHubCommon::ResourceDll::EnsureInitialized(ushort const *,ushort)

- ea: `0x180042334`
- end: `0x1800425b7`
- name: `?EnsureInitialized@ResourceDll@DiagHubCommon@@CAJPEBGG@Z`
- size: `643`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180032470`

## callees

- `0x18000334c`
- `0x180009298`
- `0x180042334`
- `0x180042688`
- `0x180042880`
- `0x180042de0`
- `0x180049b50`
- `0x18004a03c`
- `0x18004a078`
- `0x18004ad26`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1800424e8`
- `KERNEL32!LoadLibraryExW` at `0x180042523`
- `KERNEL32!LoadLibraryExW` at `0x1800424e8`
- `KERNEL32!LoadLibraryExW` at `0x180042523`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180042582`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180042582`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180042395`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180042395`

## string_xrefs

- `0x1800424b8`: `%s\%d\DiagnosticsHubMsg.dll`
- `0x180042565`: `%s\%d\DiagnosticsHubMsg.dll`
- `0x180042508`: `%s\DiagnosticsHubMsg.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DiagHubCommon::ResourceDll::EnsureInitialized(const unsigned __int16 *a1, unsigned __int16 a2)
{
  int v2; // r15d
  unsigned int v4; // edi
  _QWORD *v6; // rbx
  unsigned int v7; // r13d
  _QWORD *v8; // rbx
  _QWORD *v9; // rax
  void **v10; // rsi
  _QWORD **v11; // rcx
  _QWORD *v12; // rcx
  _QWORD *v13; // rbx
  HMODULE Library; // rax
  int v15; // eax
  __int64 v16; // [rsp+20h] [rbp-298h]
  _QWORD v17[3]; // [rsp+30h] [rbp-288h] BYREF
  int v18; // [rsp+48h] [rbp-270h]
  _BYTE v19[16]; // [rsp+50h] [rbp-268h] BYREF
  _WORD v20[8]; // [rsp+60h] [rbp-258h] BYREF
  wchar_t Buffer[264]; // [rsp+70h] [rbp-248h] BYREF

  v2 = a2;
  v20[0] = a2;
  v4 = 0;
  if ( !a1 )
    return 2147942487LL;
  v17[2] = &SRWLock;
  v18 = 1;
  AcquireSRWLockExclusive(&SRWLock);
  v6 = qword_180077138;
  if ( qword_180077138 )
  {
    v17[0] = 0;
    std::_Hash<std::_Umap_traits<unsigned short,HINSTANCE__ *,std::_Uhash_compare<unsigned short,std::hash<unsigned short>,std::equal_to<unsigned short>>,std::allocator<std::pair<unsigned short const,HINSTANCE__ *>>,0>>::find(
      qword_180077138,
      v17,
      v20);
    if ( v17[0] != v6[1] )
      goto LABEL_22;
  }
  else
  {
    try
    {
      v7 = (_DWORD)qword_180077138 + 64;
      v8 = operator new((unsigned int)((_DWORD)qword_180077138 + 64));
      v17[0] = v8;
      memset_0(v8, 0, v7);
      *(_DWORD *)v8 = 0;
      _mm_lfence();
      v9 = operator new(v7 - 32);
      *v9 = v9;
      v9[1] = v9;
      v8[1] = v9;
      v8[3] = 0;
      v8[4] = 0;
      v8[5] = 0;
      v8[6] = 7;
      v8[7] = 8;
      *(_DWORD *)v8 = 1065353216;
      std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>::_Assign_grow(
        v8 + 3,
        v7 - 48,
        v8[1]);
      v10 = (void **)qword_180077138;
      qword_180077138 = v8;
      if ( v10 )
      {
        std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>(v10 + 3);
        v11 = (_QWORD **)v10[1];
        *v11[1] = 0;
        v12 = *v11;
        if ( v12 )
        {
          do
          {
            v13 = (_QWORD *)*v12;
            operator delete(v12);
            v12 = v13;
          }
          while ( v13 );
        }
        operator delete(v10[1]);
        operator delete(v10);
      }
    }
    catch ( std::bad_alloc )
    {
      v4 = -2147024882;
      goto LABEL_22;
    }
  }
  if ( swprintf_s(Buffer, 0x105u, L"%s\\%d\\DiagnosticsHubMsg.dll", a1, v2) == -1 )
    goto LABEL_21;
  Library = LoadLibraryExW(Buffer, 0, 2u);
  if ( Library )
  {
LABEL_16:
    if ( !DiagHubCommon::ResourceDll::s_hInstance )
      DiagHubCommon::ResourceDll::s_hInstance = Library;
    LOWORD(v17[0]) = v2;
    v17[1] = Library;
    std::unordered_map<unsigned short,HINSTANCE__ *>::insert<std::pair<unsigned short,HINSTANCE__ *>,0>(
      qword_180077138,
      v19,
      v17);
    goto LABEL_22;
  }
  if ( (_WORD)v2 == 1033 )
  {
    v15 = swprintf_s(Buffer, 0x105u, L"%s\\DiagnosticsHubMsg.dll", a1);
  }
  else
  {
    LODWORD(v16) = 1033;
    v15 = swprintf_s(Buffer, 0x105u, L"%s\\%d\\DiagnosticsHubMsg.dll", a1, v16);
  }
  if ( v15 == -1 )
  {
LABEL_21:
    v4 = -2147418113;
  }
  else
  {
    Library = LoadLibraryExW(Buffer, 0, 2u);
    if ( Library )
      goto LABEL_16;
    v4 = -2147023081;
  }
LABEL_22:
  ReleaseSRWLockExclusive(&SRWLock);
  return v4;
}

```

## disassembly

```asm
0x180042334  mov     [rsp+arg_10], rbx
0x180042339  mov     [rsp+arg_18], rsi
0x18004233e  push    rdi
0x18004233f  push    r12
0x180042341  push    r13
0x180042343  push    r14
0x180042345  push    r15
0x180042347  sub     rsp, 290h
0x18004234e  mov     rax, cs:__security_cookie
0x180042355  xor     rax, rsp
0x180042358  mov     [rsp+2B8h+var_38], rax
0x180042360  movzx   r15d, dx
0x180042364  mov     r12, rcx
0x180042367  mov     [rsp+2B8h+var_258], r15w
0x18004236d  xor     edi, edi
0x18004236f  test    rcx, rcx
0x180042372  jnz     short loc_18004237E
0x180042374  mov     eax, 80070057h
0x180042379  jmp     loc_18004258A
0x18004237e  lea     r14, SRWLock
0x180042385  mov     [rsp+2B8h+var_278], r14
0x18004238a  mov     [rsp+2B8h+var_270], 1
0x180042392  mov     rcx, r14; SRWLock
0x180042395  call    cs:__imp_AcquireSRWLockExclusive
0x18004239b  nop
0x18004239c  mov     rbx, cs:qword_180077138
0x1800423a3  test    rbx, rbx
0x1800423a6  jnz     loc_18004248A
0x1800423ac  lea     r13d, [rbx+40h]
0x1800423b0  mov     ecx, r13d; Size
0x1800423b3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800423b8  mov     rbx, rax
0x1800423bb  mov     [rsp+2B8h+var_288], rax
0x1800423c0  mov     r8d, r13d; Size
0x1800423c3  xor     edx, edx; Val
0x1800423c5  mov     rcx, rax; void *
0x1800423c8  call    memset_0
0x1800423cd  mov     [rbx], edi
0x1800423cf  lfence
0x1800423d2  lea     ecx, [r13-20h]; Size
0x1800423d6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800423db  mov     [rax], rax
0x1800423de  mov     [rax+8], rax
0x1800423e2  mov     [rbx+8], rax
0x1800423e6  lea     rcx, [rbx+18h]
0x1800423ea  mov     [rcx], rdi
0x1800423ed  mov     [rcx+8], rdi
0x1800423f1  mov     [rcx+10h], rdi
0x1800423f5  mov     qword ptr [rbx+30h], 7
0x1800423fd  mov     qword ptr [rbx+38h], 8
0x180042405  mov     dword ptr [rbx], 3F800000h
0x18004240b  mov     r8, [rbx+8]
0x18004240f  lea     edx, [r13-30h]
0x180042413  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@H@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,int>>>>)
0x180042418  nop
0x180042419  mov     rsi, cs:qword_180077138
0x180042420  mov     cs:qword_180077138, rbx
0x180042427  test    rsi, rsi
0x18004242a  jz      short loc_180042477
0x18004242c  lea     rcx, [rsi+18h]
0x180042430  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@U?$AgentContainer@UIStandardCollectorMessageAgent@@@AgentController@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,Microsoft::DiagnosticsHub::StandardCollector::AgentController::AgentContainer<IStandardCollectorMessageAgent>>>>>>>(void)
0x180042435  mov     rcx, [rsi+8]
0x180042439  mov     rax, [rcx+8]
0x18004243d  mov     [rax], rdi
0x180042440  mov     rcx, [rcx]; Block
0x180042443  test    rcx, rcx
0x180042446  jz      short loc_18004245D
0x180042448  mov     rbx, [rcx]
0x18004244b  mov     edx, 20h ; ' '
0x180042450  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180042455  mov     rcx, rbx
0x180042458  test    rbx, rbx
0x18004245b  jnz     short loc_180042448
0x18004245d  mov     edx, 20h ; ' '
0x180042462  mov     rcx, [rsi+8]; Block
0x180042466  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004246b  mov     rdx, r13
0x18004246e  mov     rcx, rsi; Block
0x180042471  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180042476  nop
0x180042477  jmp     short loc_1800424B0
0x180042479  mov     edi, 8007000Eh
0x18004247e  lea     r14, SRWLock
0x180042485  jmp     loc_18004257F
0x18004248a  mov     [rsp+2B8h+var_288], rdi
0x18004248f  lea     r8, [rsp+2B8h+var_258]
0x180042494  lea     rdx, [rsp+2B8h+var_288]
0x180042499  mov     rcx, rbx
0x18004249c  call    ?find@?$_Hash@V?$_Umap_traits@GPEAUHINSTANCE__@@V?$_Uhash_compare@GU?$hash@G@std@@U?$equal_to@G@2@@std@@V?$allocator@U?$pair@$$CBGPEAUHINSTANCE__@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBGPEAUHINSTANCE__@@@std@@@std@@@std@@@2@AEBG@Z; std::_Hash<std::_Umap_traits<ushort,HINSTANCE__ *,std::_Uhash_compare<ushort,std::hash<ushort>,std::equal_to<ushort>>,std::allocator<std::pair<ushort const,HINSTANCE__ *>>,0>>::find(ushort const &)
0x1800424a1  mov     r8, [rbx+8]
0x1800424a5  cmp     [rsp+2B8h+var_288], r8
0x1800424aa  jnz     loc_18004257F
0x1800424b0  mov     [rsp+2B8h+var_298], r15d
0x1800424b5  mov     r9, r12
0x1800424b8  lea     r8, aSDDiagnosticsh; "%s\\%d\\DiagnosticsHubMsg.dll"
0x1800424bf  mov     esi, 105h
0x1800424c4  mov     edx, esi; BufferCount
0x1800424c6  lea     rcx, [rsp+2B8h+Buffer]; Buffer
0x1800424cb  call    swprintf_s
0x1800424d0  cmp     eax, 0FFFFFFFFh
0x1800424d3  jz      loc_18004257A
0x1800424d9  mov     ebx, 2
0x1800424de  mov     r8d, ebx; dwFlags
0x1800424e1  xor     edx, edx; hFile
0x1800424e3  lea     rcx, [rsp+2B8h+Buffer]; lpLibFileName
0x1800424e8  call    cs:__imp_LoadLibraryExW
0x1800424ee  test    rax, rax
0x1800424f1  jnz     short loc_18004252E
0x1800424f3  mov     eax, 409h
0x1800424f8  mov     r9, r12
0x1800424fb  mov     edx, esi; BufferCount
0x1800424fd  lea     rcx, [rsp+2B8h+Buffer]; Buffer
0x180042502  cmp     r15w, ax
0x180042506  jnz     short loc_180042561
0x180042508  lea     r8, aSDiagnosticshu; "%s\\DiagnosticsHubMsg.dll"
0x18004250f  call    swprintf_s
0x180042514  cmp     eax, 0FFFFFFFFh
0x180042517  jz      short loc_18004257A
0x180042519  mov     r8d, ebx; dwFlags
0x18004251c  xor     edx, edx; hFile
0x18004251e  lea     rcx, [rsp+2B8h+Buffer]; lpLibFileName
0x180042523  call    cs:__imp_LoadLibraryExW
0x180042529  test    rax, rax
0x18004252c  jz      short loc_180042573
0x18004252e  cmp     cs:?s_hInstance@ResourceDll@DiagHubCommon@@0PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * DiagHubCommon::ResourceDll::s_hInstance
0x180042535  jnz     short loc_18004253E
0x180042537  mov     cs:?s_hInstance@ResourceDll@DiagHubCommon@@0PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * DiagHubCommon::ResourceDll::s_hInstance
0x18004253e  mov     word ptr [rsp+2B8h+var_288], r15w
0x180042544  mov     [rsp+2B8h+var_280], rax
0x180042549  lea     r8, [rsp+2B8h+var_288]
0x18004254e  lea     rdx, [rsp+2B8h+var_268]
0x180042553  mov     rcx, cs:qword_180077138
0x18004255a  call    ??$insert@U?$pair@GPEAUHINSTANCE__@@@std@@$0A@@?$unordered_map@GPEAUHINSTANCE__@@U?$hash@G@std@@U?$equal_to@G@3@V?$allocator@U?$pair@$$CBGPEAUHINSTANCE__@@@std@@@3@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBGPEAUHINSTANCE__@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@GPEAUHINSTANCE__@@@1@@Z; std::unordered_map<ushort,HINSTANCE__ *>::insert<std::pair<ushort,HINSTANCE__ *>,0>(std::pair<ushort,HINSTANCE__ *> &&)
0x18004255f  jmp     short loc_18004257F
0x180042561  mov     [rsp+2B8h+var_298], eax
0x180042565  lea     r8, aSDDiagnosticsh; "%s\\%d\\DiagnosticsHubMsg.dll"
0x18004256c  call    swprintf_s
0x180042571  jmp     short loc_180042514
0x180042573  mov     edi, 80070717h
0x180042578  jmp     short loc_18004257F
0x18004257a  mov     edi, 8000FFFFh
0x18004257f  mov     rcx, r14; SRWLock
0x180042582  call    cs:__imp_ReleaseSRWLockExclusive
0x180042588  mov     eax, edi
0x18004258a  mov     rcx, [rsp+2B8h+var_38]
0x180042592  xor     rcx, rsp; StackCookie
0x180042595  call    __security_check_cookie
0x18004259a  lea     r11, [rsp+2B8h+var_28]
0x1800425a2  mov     rbx, [r11+40h]
0x1800425a6  mov     rsi, [r11+48h]
0x1800425aa  mov     rsp, r11
0x1800425ad  pop     r15
0x1800425af  pop     r14
0x1800425b1  pop     r13
0x1800425b3  pop     r12
0x1800425b5  pop     rdi
0x1800425b6  retn
```
