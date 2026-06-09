# DedupUtil::GetVolumeHandleFromPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong,void * *,bool)

- ea: `0x1400668bc`
- end: `0x140066b53`
- name: `?GetVolumeHandleFromPath@DedupUtil@@YAKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KPEAPEAX_N@Z`
- size: `663`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `15`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400653fc`
- `0x1400656dc`
- `0x140065c7c`
- `0x140065fd4`
- `0x140066c88`
- `0x140067f64`
- `0x14006d410`
- `0x14006e690`
- `0x140078c9c`
- `0x14007a0e0`
- `0x14007ae04`

## callees

- `0x140004870`
- `0x140015f60`
- `0x140019504`
- `0x140019600`
- `0x14001983c`
- `0x140019d14`
- `0x140041dc4`
- `0x140055b90`
- `0x140064040`
- `0x140064c9c`
- `0x140065e44`
- `0x140066468`
- `0x1400667a0`
- `0x1400668bc`
- `0x140066b5c`

## import_xrefs

- `ntdll!NtCreateFile` at `0x140066acf`
- `ntdll!NtCreateFile` at `0x140066acf`
- `ntdll!RtlNtStatusToDosError` at `0x140066ae1`
- `ntdll!RtlNtStatusToDosError` at `0x140066ae1`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x140066973`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x140066973`
- `ntdll!RtlFreeUnicodeString` at `0x1400669c8`
- `ntdll!RtlFreeUnicodeString` at `0x1400669c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DedupUtil::GetVolumeHandleFromPath(__int64 a1, ACCESS_MASK a2, void **a3, char a4)
{
  void **v5; // rdi
  ULONG MdsPathFromCsv; // ebx
  const WCHAR *v9; // rax
  __int64 v10; // rcx
  int v11; // eax
  _DWORD v12[2]; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING NtPathName; // [rsp+68h] [rbp-98h] BYREF
  __int128 v14; // [rsp+78h] [rbp-88h] BYREF
  int v15; // [rsp+88h] [rbp-78h]
  char v16; // [rsp+8Ch] [rbp-74h]
  struct _UNICODE_STRING *p_NtPathName; // [rsp+90h] [rbp-70h] BYREF
  _DWORD *v18; // [rsp+98h] [rbp-68h] BYREF
  __int128 v19; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v20; // [rsp+B0h] [rbp-50h]
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B8h] [rbp-48h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v23[16]; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v24; // [rsp+108h] [rbp+8h]
  _BYTE v25[16]; // [rsp+118h] [rbp+18h] BYREF
  __int64 v26; // [rsp+128h] [rbp+28h]

  v5 = a3;
  if ( !a3 )
    return 87;
  *a3 = (void *)-1LL;
  LOBYTE(a3) = 1;
  DedupUtil::GetVolumeGuid(v25, a1, a3);
  if ( v26 )
  {
    std::wstring::wstring(v23);
    NtPathName = 0;
    if ( (unsigned __int8)DedupUtil::IsCsvVolume(v25) )
    {
      MdsPathFromCsv = DedupUtil::GetMdsPathFromCsv(v25, v23);
      if ( MdsPathFromCsv )
      {
LABEL_7:
        std::wstring::_Tidy_deallocate(v23);
        goto LABEL_16;
      }
    }
    else
    {
      v9 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v25);
      if ( !RtlDosPathNameToNtPathName_U(v9, &NtPathName, 0, 0) )
      {
        std::wstring::_Tidy_deallocate(v23);
        MdsPathFromCsv = 3;
        goto LABEL_16;
      }
      std::_WChar_traits<unsigned short>::length(NtPathName.Buffer);
      std::wstring::_Assign<unsigned short>(v23, v10);
      if ( !a4 )
        std::wstring::_Eos(v23);
      RtlFreeUnicodeString(&NtPathName);
    }
    v12[0] = 17;
    v12[1] = 18;
    v19 = 0;
    v20 = 0;
    p_NtPathName = &NtPathName;
    v18 = v12;
    std::vector<unsigned long>::_Construct_n<unsigned long const *,unsigned long const *>(&v19, 2, &v18, &p_NtPathName);
    v14 = 0;
    v15 = 0;
    v16 = 0;
    DedupUtil::ScopedPrivileges::EnablePrivileges(&v14, &v19);
    NtPathName.MaximumLength = 2 * v24;
    NtPathName.Length = 2 * v24;
    NtPathName.Buffer = (PWSTR)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v23);
    IoStatusBlock = 0;
    *(_QWORD *)&ObjectAttributes.Length = 48;
    *(_QWORD *)&ObjectAttributes.Attributes = 64;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.ObjectName = &NtPathName;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v11 = NtCreateFile(v5, a2, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 1u, 0, 0, 0);
    if ( v11 >= 0 )
    {
      DedupUtil::ScopedPrivileges::~ScopedPrivileges((DedupUtil::ScopedPrivileges *)&v14);
      std::vector<unsigned int>::_Tidy(&v19);
      std::wstring::_Tidy_deallocate(v23);
      MdsPathFromCsv = 0;
      goto LABEL_16;
    }
    MdsPathFromCsv = RtlNtStatusToDosError(v11);
    DedupUtil::ScopedPrivileges::~ScopedPrivileges((DedupUtil::ScopedPrivileges *)&v14);
    std::vector<unsigned int>::_Tidy(&v19);
    goto LABEL_7;
  }
  MdsPathFromCsv = 87;
LABEL_16:
  std::wstring::_Tidy_deallocate(v25);
  return MdsPathFromCsv;
}

```

## disassembly

```asm
0x1400668bc  mov     [rsp-8+arg_18], rbx
0x1400668c1  push    rbp
0x1400668c2  push    rsi
0x1400668c3  push    rdi
0x1400668c4  lea     rbp, [rsp-40h]
0x1400668c9  sub     rsp, 140h
0x1400668d0  mov     rax, cs:__security_cookie
0x1400668d7  xor     rax, rsp
0x1400668da  mov     [rbp+50h+var_18], rax
0x1400668de  mov     bl, r9b
0x1400668e1  mov     rdi, r8
0x1400668e4  mov     esi, edx
0x1400668e6  test    r8, r8
0x1400668e9  jnz     short loc_1400668F4
0x1400668eb  lea     eax, [r8+57h]
0x1400668ef  jmp     loc_140066B33
0x1400668f4  mov     qword ptr [r8], 0FFFFFFFFFFFFFFFFh
0x1400668fb  mov     r8b, 1
0x1400668fe  mov     rdx, rcx
0x140066901  lea     rcx, [rbp+50h+var_38]
0x140066905  call    ?GetVolumeGuid@DedupUtil@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@_N@Z; DedupUtil::GetVolumeGuid(std::wstring const &,bool)
0x14006690a  nop
0x14006690b  cmp     [rbp+50h+var_28], 0
0x140066910  jnz     short loc_14006691C
0x140066912  mov     ebx, 57h ; 'W'
0x140066917  jmp     loc_140066B28
0x14006691c  lea     rcx, [rbp+50h+var_58]
0x140066920  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140066925  nop
0x140066926  xorps   xmm1, xmm1
0x140066929  movups  xmmword ptr [rsp+150h+NtPathName.Length], xmm1
0x14006692e  lea     rcx, [rbp+50h+var_38]
0x140066932  call    ?IsCsvVolume@DedupUtil@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DedupUtil::IsCsvVolume(std::wstring const &)
0x140066937  lea     rcx, [rbp+50h+var_38]
0x14006693b  test    al, al
0x14006693d  jz      short loc_140066960
0x14006693f  lea     rdx, [rbp+50h+var_58]
0x140066943  call    ?GetMdsPathFromCsv@DedupUtil@@YAKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; DedupUtil::GetMdsPathFromCsv(std::wstring const &,std::wstring &)
0x140066948  mov     ebx, eax
0x14006694a  test    eax, eax
0x14006694c  jz      loc_1400669D4
0x140066952  lea     rcx, [rbp+50h+var_58]
0x140066956  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14006695b  jmp     loc_140066B28
0x140066960  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140066965  mov     rcx, rax; DosPathName
0x140066968  xor     r9d, r9d; DirectoryInfo
0x14006696b  xor     r8d, r8d; NtFileNamePart
0x14006696e  lea     rdx, [rsp+150h+NtPathName]; NtPathName
0x140066973  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x14006697a  nop     dword ptr [rax+rax+00h]
0x14006697f  test    al, al
0x140066981  jnz     short loc_140066996
0x140066983  lea     rcx, [rbp+50h+var_58]
0x140066987  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14006698c  mov     ebx, 3
0x140066991  jmp     loc_140066B28
0x140066996  mov     rcx, [rsp+150h+NtPathName.Buffer]
0x14006699b  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1400669a0  mov     r8, rax
0x1400669a3  mov     rdx, rcx
0x1400669a6  lea     rcx, [rbp+50h+var_58]
0x1400669aa  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1400669af  test    bl, bl
0x1400669b1  jnz     short loc_1400669C3
0x1400669b3  mov     rdx, [rbp+50h+var_48]
0x1400669b7  dec     rdx
0x1400669ba  lea     rcx, [rbp+50h+var_58]
0x1400669be  call    ?_Eos@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAX_K@Z; std::wstring::_Eos(unsigned __int64)
0x1400669c3  lea     rcx, [rsp+150h+NtPathName]; UnicodeString
0x1400669c8  call    cs:__imp_RtlFreeUnicodeString
0x1400669cf  nop     dword ptr [rax+rax+00h]
0x1400669d4  mov     [rsp+150h+var_F0], 11h
0x1400669dc  mov     [rsp+150h+var_EC], 12h
0x1400669e4  xorps   xmm0, xmm0
0x1400669e7  movdqu  [rbp+50h+var_B0], xmm0
0x1400669ec  mov     [rbp+50h+var_A0], 0
0x1400669f4  lea     rax, [rsp+150h+NtPathName]
0x1400669f9  mov     [rbp+50h+var_C0], rax
0x1400669fd  lea     rax, [rsp+150h+var_F0]
0x140066a02  mov     [rbp+50h+var_B8], rax
0x140066a06  lea     r9, [rbp+50h+var_C0]
0x140066a0a  lea     r8, [rbp+50h+var_B8]
0x140066a0e  mov     edx, 2
0x140066a13  lea     rcx, [rbp+50h+var_B0]
0x140066a17  call    ??$_Construct_n@PEBKPEBK@?$vector@KV?$allocator@K@std@@@std@@AEAAX_K$$QEAPEBK1@Z; std::vector<ulong>::_Construct_n<ulong const *,ulong const *>(unsigned __int64,ulong const * &&,ulong const * &&)
0x140066a1c  nop
0x140066a1d  xor     eax, eax
0x140066a1f  xorps   xmm0, xmm0
0x140066a22  movdqu  [rsp+150h+var_D8], xmm0
0x140066a28  mov     [rbp+50h+var_C8], eax
0x140066a2b  mov     [rbp+50h+var_C4], al
0x140066a2e  lea     rdx, [rbp+50h+var_B0]
0x140066a32  lea     rcx, [rsp+150h+var_D8]
0x140066a37  call    ?EnablePrivileges@ScopedPrivileges@DedupUtil@@QEAAKAEBV?$vector@KV?$allocator@K@std@@@std@@_N@Z; DedupUtil::ScopedPrivileges::EnablePrivileges(std::vector<ulong> const &,bool)
0x140066a3c  movzx   eax, word ptr [rbp+50h+var_48]
0x140066a40  add     ax, ax
0x140066a43  mov     [rsp+150h+NtPathName.MaximumLength], ax
0x140066a48  mov     [rsp+150h+NtPathName.Length], ax
0x140066a4d  lea     rcx, [rbp+50h+var_58]
0x140066a51  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140066a56  mov     [rsp+150h+NtPathName.Buffer], rax
0x140066a5b  xorps   xmm0, xmm0
0x140066a5e  movups  xmmword ptr [rbp+50h+IoStatusBlock], xmm0
0x140066a62  mov     qword ptr [rbp+50h+ObjectAttributes.Length], 30h ; '0'
0x140066a6a  mov     qword ptr [rbp+50h+ObjectAttributes.Attributes], 40h ; '@'
0x140066a72  mov     [rbp+50h+ObjectAttributes.RootDirectory], 0
0x140066a7a  lea     rax, [rsp+150h+NtPathName]
0x140066a7f  mov     [rbp+50h+ObjectAttributes.ObjectName], rax
0x140066a83  movdqu  xmmword ptr [rbp+50h+ObjectAttributes.SecurityDescriptor], xmm0
0x140066a88  mov     [rsp+150h+EaLength], 0; EaLength
0x140066a90  mov     [rsp+150h+EaBuffer], 0; EaBuffer
0x140066a99  mov     [rsp+150h+CreateOptions], 0; CreateOptions
0x140066aa1  mov     [rsp+150h+CreateDisposition], 1; CreateDisposition
0x140066aa9  mov     [rsp+150h+ShareAccess], 7; ShareAccess
0x140066ab1  mov     [rsp+150h+FileAttributes], 80h; FileAttributes
0x140066ab9  mov     [rsp+150h+AllocationSize], 0; AllocationSize
0x140066ac2  lea     r9, [rbp+50h+IoStatusBlock]; IoStatusBlock
0x140066ac6  lea     r8, [rbp+50h+ObjectAttributes]; ObjectAttributes
0x140066aca  mov     edx, esi; DesiredAccess
0x140066acc  mov     rcx, rdi; FileHandle
0x140066acf  call    cs:__imp_NtCreateFile
0x140066ad6  nop     dword ptr [rax+rax+00h]
0x140066adb  test    eax, eax
0x140066add  jns     short loc_140066B08
0x140066adf  mov     ecx, eax; Status
0x140066ae1  call    cs:__imp_RtlNtStatusToDosError
0x140066ae8  nop     dword ptr [rax+rax+00h]
0x140066aed  mov     ebx, eax
0x140066aef  lea     rcx, [rsp+150h+var_D8]; this
0x140066af4  call    ??1ScopedPrivileges@DedupUtil@@QEAA@XZ; DedupUtil::ScopedPrivileges::~ScopedPrivileges(void)
0x140066af9  nop
0x140066afa  lea     rcx, [rbp+50h+var_B0]
0x140066afe  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x140066b03  jmp     loc_140066952
0x140066b08  lea     rcx, [rsp+150h+var_D8]; this
0x140066b0d  call    ??1ScopedPrivileges@DedupUtil@@QEAA@XZ; DedupUtil::ScopedPrivileges::~ScopedPrivileges(void)
0x140066b12  nop
0x140066b13  lea     rcx, [rbp+50h+var_B0]
0x140066b17  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x140066b1c  nop
0x140066b1d  lea     rcx, [rbp+50h+var_58]
0x140066b21  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140066b26  xor     ebx, ebx
0x140066b28  lea     rcx, [rbp+50h+var_38]
0x140066b2c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140066b31  mov     eax, ebx
0x140066b33  mov     rcx, [rbp+50h+var_18]
0x140066b37  xor     rcx, rsp; StackCookie
0x140066b3a  call    __security_check_cookie
0x140066b3f  mov     rbx, [rsp+150h+arg_18]
0x140066b47  add     rsp, 140h
0x140066b4e  pop     rdi
0x140066b4f  pop     rsi
0x140066b50  pop     rbp
0x140066b51  retn
```
