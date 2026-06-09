# ConnectedStorage::VerifyFilePathHandler::_Move(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong)

- ea: `0x180050518`
- end: `0x1800506fc`
- name: `?_Move@VerifyFilePathHandler@ConnectedStorage@@AEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0K@Z`
- size: `484`
- prototype: `char __fastcall(__int64 **, __int64, const WCHAR *, char)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x18004f820`

## callees

- `0x180003c70`
- `0x18000460c`
- `0x180004754`
- `0x180005ec9`
- `0x18000aae4`
- `0x18001303c`
- `0x18001c090`
- `0x18004e038`
- `0x18004ed94`
- `0x18005043c`
- `0x1800504dc`
- `0x180050518`
- `0x180050704`
- `0x180050cc0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180050659`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180050659`
- `ntdll!NtSetInformationFile` at `0x180050639`
- `ntdll!NtSetInformationFile` at `0x180050675`
- `ntdll!NtSetInformationFile` at `0x180050639`
- `ntdll!NtSetInformationFile` at `0x180050675`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800505d1`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800505d1`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall ConnectedStorage::VerifyFilePathHandler::_Move(__int64 **a1, __int64 a2, const WCHAR *a3, char a4)
{
  __int64 *v7; // rbx
  __int64 v9; // rax
  ULONG v10; // r15d
  __int64 *v11; // r14
  int v12; // edi
  NTSTATUS v13; // eax
  const unsigned __int16 *v14; // r8
  int v15; // eax
  __int64 *v16; // [rsp+30h] [rbp-59h] BYREF
  struct _UNICODE_STRING NtPathName; // [rsp+38h] [rbp-51h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+48h] [rbp-41h] BYREF
  __int128 v19; // [rsp+60h] [rbp-29h] BYREF
  char v20[16]; // [rsp+70h] [rbp-19h] BYREF
  _BYTE v21[32]; // [rsp+80h] [rbp-9h] BYREF

  ConnectedStorage::VerifyFilePathHandler::_SanitizePath(a1, v21, a2);
  std::_Tree<std::_Tmap_traits<std::wstring,ConnectedStorage::Handle,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ConnectedStorage::Handle>>,0>>::find(
    a1,
    &v16,
    v21);
  v7 = v16;
  if ( v16 == *a1 )
  {
    std::wstring::_Tidy_deallocate(v21);
    return 0;
  }
  else
  {
    v9 = **a1;
LABEL_4:
    v16 = (__int64 *)v9;
    while ( (__int64 *)v9 != *a1 )
    {
      if ( (__int64 *)v9 != v7 )
      {
        v9 = std::_Tree<std::_Tmap_traits<std::wstring,ConnectedStorage::Handle,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ConnectedStorage::Handle>>,0>>::_Erase_unchecked(
               a1,
               v9);
        goto LABEL_4;
      }
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ConnectedStorage::SimpleHStringWrapper const,ConnectedStorage::ContainerIndexEntry const *>>>,std::_Iterator_base0>::operator++(&v16);
      v9 = (__int64)v16;
    }
    IoStatusBlock = 0;
    NtPathName = 0;
    if ( *((_QWORD *)a3 + 3) > 7u )
      a3 = *(const WCHAR **)a3;
    RtlDosPathNameToNtPathName_U(a3, &NtPathName, 0, 0);
    v10 = NtPathName.MaximumLength + 22;
    v11 = (__int64 *)operator new[](v10);
    v16 = v11;
    memset_0(v11, 0, v10);
    v12 = 0;
    v11[1] = 0;
    *(_BYTE *)v11 = a4 & 1;
    *((_DWORD *)v11 + 4) = NtPathName.Length;
    memcpy_0((char *)v11 + 20, NtPathName.Buffer, NtPathName.Length);
    v13 = NtSetInformationFile((HANDLE)v7[8], &IoStatusBlock, v11, v10, FileRenameInformation);
    if ( v13 == -1073741790 || v13 == -1073741757 )
    {
      do
      {
        Sleep(10 * (v12 + 1));
        v13 = NtSetInformationFile((HANDLE)v7[8], &IoStatusBlock, v11, v10, FileRenameInformation);
        if ( v13 != -1073741790 && v13 != -1073741757 )
          break;
        ++v12;
      }
      while ( v12 < 5 );
    }
    v15 = v13 | 0x10000000;
    if ( v15 < 0 )
      ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)(unsigned int)v15, (int)L"HRESULT_FROM_NT(status)", v14);
    v19 = *(_OWORD *)std::_Tree<std::_Tmap_traits<std::wstring,ConnectedStorage::Handle,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ConnectedStorage::Handle>>,0>>::_Eqrange<std::wstring>(
                       a1,
                       v20,
                       v21);
    std::_Tree<std::_Tmap_traits<std::wstring,ConnectedStorage::Handle,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ConnectedStorage::Handle>>,0>>::_Erase(
      a1,
      &v19);
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v16);
    std::wstring::_Tidy_deallocate(v21);
    return 1;
  }
}

```

## disassembly

```asm
0x180050518  push    rbp
0x18005051a  push    rbx
0x18005051b  push    rsi
0x18005051c  push    rdi
0x18005051d  push    r12
0x18005051f  push    r14
0x180050521  push    r15
0x180050523  lea     rbp, [rsp-27h]
0x180050528  sub     rsp, 0B0h
0x18005052f  mov     rax, cs:__security_cookie
0x180050536  xor     rax, rsp
0x180050539  mov     [rbp+57h+var_40], rax
0x18005053d  mov     r12d, r9d
0x180050540  mov     rdi, r8
0x180050543  mov     rsi, rcx
0x180050546  mov     r8, rdx
0x180050549  lea     rdx, [rbp+57h+var_60]
0x18005054d  call    ?_SanitizePath@VerifyFilePathHandler@ConnectedStorage@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@@Z; ConnectedStorage::VerifyFilePathHandler::_SanitizePath(std::wstring const &)
0x180050552  nop
0x180050553  lea     r8, [rbp+57h+var_60]
0x180050557  lea     rdx, [rbp+57h+var_B0]
0x18005055b  mov     rcx, rsi
0x18005055e  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHandle@ConnectedStorage@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHandle@ConnectedStorage@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHandle@ConnectedStorage@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,ConnectedStorage::Handle,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ConnectedStorage::Handle>>,0>>::find(std::wstring const &)
0x180050563  mov     rax, [rsi]
0x180050566  mov     rbx, [rbp+57h+var_B0]
0x18005056a  cmp     rbx, rax
0x18005056d  jnz     short loc_18005057F
0x18005056f  lea     rcx, [rbp+57h+var_60]
0x180050573  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180050578  xor     al, al
0x18005057a  jmp     loc_1800506CF
0x18005057f  mov     rax, [rax]
0x180050582  mov     [rbp+57h+var_B0], rax
0x180050586  cmp     rax, [rsi]
0x180050589  jz      short loc_1800505AC
0x18005058b  cmp     rax, rbx
0x18005058e  jnz     short loc_18005059F
0x180050590  lea     rcx, [rbp+57h+var_B0]
0x180050594  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVSimpleHStringWrapper@ConnectedStorage@@PEBVContainerIndexEntry@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ConnectedStorage::SimpleHStringWrapper const,ConnectedStorage::ContainerIndexEntry const *>>>,std::_Iterator_base0>::operator++(void)
0x180050599  mov     rax, [rbp+57h+var_B0]
0x18005059d  jmp     short loc_180050586
0x18005059f  mov     rdx, rax
0x1800505a2  mov     rcx, rsi
0x1800505a5  call    ?_Erase_unchecked@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHandle@ConnectedStorage@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHandle@ConnectedStorage@@@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHandle@ConnectedStorage@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHandle@ConnectedStorage@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,ConnectedStorage::Handle,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ConnectedStorage::Handle>>,0>>::_Erase_unchecked(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,ConnectedStorage::Handle>>>,std::_Iterator_base0>)
0x1800505aa  jmp     short loc_180050582
0x1800505ac  xorps   xmm0, xmm0
0x1800505af  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1800505b3  xorps   xmm1, xmm1
0x1800505b6  movups  xmmword ptr [rbp+57h+NtPathName.Length], xmm1
0x1800505ba  cmp     qword ptr [rdi+18h], 7
0x1800505bf  jbe     short loc_1800505C4
0x1800505c1  mov     rdi, [rdi]
0x1800505c4  xor     r9d, r9d; DirectoryInfo
0x1800505c7  xor     r8d, r8d; NtFileNamePart
0x1800505ca  lea     rdx, [rbp+57h+NtPathName]; NtPathName
0x1800505ce  mov     rcx, rdi; DosPathName
0x1800505d1  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800505d7  movzx   r15d, [rbp+57h+NtPathName.MaximumLength]
0x1800505dc  add     r15d, 16h
0x1800505e0  mov     ecx, r15d; unsigned __int64
0x1800505e3  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800505e8  mov     r14, rax
0x1800505eb  mov     [rbp+57h+var_B0], rax
0x1800505ef  mov     r8d, r15d; Size
0x1800505f2  xor     edx, edx; Val
0x1800505f4  mov     rcx, rax; void *
0x1800505f7  call    memset_0
0x1800505fc  xor     edi, edi
0x1800505fe  mov     [r14+8], rdi
0x180050602  and     r12b, 1
0x180050606  mov     [r14], r12b
0x180050609  movzx   ecx, [rbp+57h+NtPathName.Length]
0x18005060d  mov     [r14+10h], ecx
0x180050611  movzx   r8d, [rbp+57h+NtPathName.Length]; Size
0x180050616  lea     rcx, [r14+14h]; void *
0x18005061a  mov     rdx, [rbp+57h+NtPathName.Buffer]; Src
0x18005061e  call    memcpy_0
0x180050623  mov     [rsp+0E0h+FileInformationClass], 0Ah; FileInformationClass
0x18005062b  mov     r9d, r15d; Length
0x18005062e  mov     r8, r14; FileInformation
0x180050631  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180050635  mov     rcx, [rbx+40h]; FileHandle
0x180050639  call    cs:__imp_NtSetInformationFile
0x18005063f  mov     r12d, 0C0000043h
0x180050645  cmp     eax, 0C0000022h
0x18005064a  jz      short loc_180050651
0x18005064c  cmp     eax, r12d
0x18005064f  jnz     short loc_18005068E
0x180050651  lea     eax, [rdi+1]
0x180050654  lea     ecx, [rax+rax*4]
0x180050657  add     ecx, ecx; dwMilliseconds
0x180050659  call    cs:__imp_Sleep
0x18005065f  mov     [rsp+0E0h+FileInformationClass], 0Ah; FileInformationClass
0x180050667  mov     r9d, r15d; Length
0x18005066a  mov     r8, r14; FileInformation
0x18005066d  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180050671  mov     rcx, [rbx+40h]; FileHandle
0x180050675  call    cs:__imp_NtSetInformationFile
0x18005067b  cmp     eax, 0C0000022h
0x180050680  jz      short loc_180050687
0x180050682  cmp     eax, r12d
0x180050685  jnz     short loc_18005068E
0x180050687  inc     edi
0x180050689  cmp     edi, 5
0x18005068c  jl      short loc_180050651
0x18005068e  or      eax, 10000000h
0x180050693  jl      short loc_1800506ED
0x180050695  lea     r8, [rbp+57h+var_60]
0x180050699  lea     rdx, [rbp+57h+var_70]
0x18005069d  mov     rcx, rsi
0x1800506a0  call    ??$_Eqrange@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHandle@ConnectedStorage@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHandle@ConnectedStorage@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHandle@ConnectedStorage@@@std@@PEAX@std@@PEAU12@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,ConnectedStorage::Handle,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ConnectedStorage::Handle>>,0>>::_Eqrange<std::wstring>(std::wstring const &)
0x1800506a5  movups  xmm0, xmmword ptr [rax]
0x1800506a8  movdqu  [rbp+57h+var_80], xmm0
0x1800506ad  lea     rdx, [rbp+57h+var_80]
0x1800506b1  mov     rcx, rsi
0x1800506b4  call    ?_Erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHandle@ConnectedStorage@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHandle@ConnectedStorage@@@std@@@2@$0A@@std@@@std@@AEAA_KU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHandle@ConnectedStorage@@@std@@PEAX@std@@PEAU12@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,ConnectedStorage::Handle,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ConnectedStorage::Handle>>,0>>::_Erase(std::pair<std::_Tree_node<std::pair<std::wstring const,ConnectedStorage::Handle>,void *> *,std::_Tree_node<std::pair<std::wstring const,ConnectedStorage::Handle>,void *> *>)
0x1800506b9  nop
0x1800506ba  lea     rcx, [rbp+57h+var_B0]
0x1800506be  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1800506c3  nop
0x1800506c4  lea     rcx, [rbp+57h+var_60]
0x1800506c8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800506cd  mov     al, 1
0x1800506cf  mov     rcx, [rbp+57h+var_40]
0x1800506d3  xor     rcx, rsp; StackCookie
0x1800506d6  call    __security_check_cookie
0x1800506db  add     rsp, 0B0h
0x1800506e2  pop     r15
0x1800506e4  pop     r14
0x1800506e6  pop     r12
0x1800506e8  pop     rdi
0x1800506e9  pop     rsi
0x1800506ea  pop     rbx
0x1800506eb  pop     rbp
0x1800506ec  retn
0x1800506ed  lea     rdx, aHresultFromNtS; "HRESULT_FROM_NT(status)"
0x1800506f4  mov     ecx, eax; this
0x1800506f6  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
```
