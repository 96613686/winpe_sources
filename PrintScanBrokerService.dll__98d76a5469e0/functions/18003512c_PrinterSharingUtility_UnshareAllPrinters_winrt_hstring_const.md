# PrinterSharingUtility::UnshareAllPrinters(winrt::hstring const &)

- ea: `0x18003512c`
- end: `0x180035217`
- name: `?UnshareAllPrinters@PrinterSharingUtility@@SAXAEBUhstring@winrt@@@Z`
- size: `235`
- prototype: `void __fastcall(const struct winrt::hstring *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000f160`

## callees

- `0x18000792c`
- `0x18000fa2c`
- `0x18000fb60`
- `0x18001d0e4`
- `0x18003512c`
- `0x180035220`

## import_xrefs

- `srvcli!NetShareEnum` at `0x18003518a`
- `srvcli!NetShareEnum` at `0x18003518a`
- `netutils!NetApiBufferFree` at `0x180035209`
- `netutils!NetApiBufferFree` at `0x180035209`

## string_xrefs

- `0x1800351a3`: `onecoreuap\printscan\print\printscanbroker\class\printersharingutility.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall PrinterSharingUtility::UnshareAllPrinters(const struct winrt::hstring *a1)
{
  WCHAR *v2; // rax
  DWORD v3; // eax
  __int64 v4; // rbx
  DWORD i; // ecx
  const char *totalentries; // [rsp+28h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  DWORD entriesread; // [rsp+70h] [rbp+20h] BYREF
  DWORD v9; // [rsp+78h] [rbp+28h] BYREF
  LPBYTE bufptr; // [rsp+80h] [rbp+30h] BYREF
  char v11; // [rsp+88h] [rbp+38h] BYREF

  bufptr = 0;
  entriesread = 0;
  v9 = 0;
  if ( *(_QWORD *)a1 )
    v2 = (WCHAR *)winrt::hstring::c_str(a1);
  else
    v2 = 0;
  v3 = NetShareEnum(v2, 1u, &bufptr, 0xFFFFFFFF, &entriesread, &v9, 0);
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)0x74,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\printersharingutility.cpp",
    (const char *)v3,
    (unsigned int)"Failed to enumerate printer shares!",
    totalentries);
  v4 = 0;
  for ( i = entriesread; (unsigned int)v4 < i; v4 = (unsigned int)(v4 + 1) )
  {
    if ( *(_DWORD *)&bufptr[24 * v4 + 8] == 1 )
    {
      winrt::hstring::hstring((winrt::hstring *)&v11, *(const unsigned __int16 **)&bufptr[24 * v4]);
      PrinterSharingUtility::UnsharePrinter((const struct winrt::hstring *)&v11, a1);
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v11);
      i = entriesread;
    }
  }
  NetApiBufferFree(bufptr);
}

```

## disassembly

```asm
0x18003512c  push    rbp
0x18003512e  push    rbx
0x18003512f  push    rdi
0x180035130  mov     rbp, rsp
0x180035133  sub     rsp, 50h
0x180035137  mov     rdi, rcx
0x18003513a  mov     [rbp+bufptr], 0
0x180035142  mov     [rbp+arg_0], 0
0x180035149  mov     [rbp+arg_8], 0
0x180035150  cmp     qword ptr [rcx], 0
0x180035154  jz      short loc_18003515D
0x180035156  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18003515b  jmp     short loc_18003515F
0x18003515d  xor     eax, eax
0x18003515f  mov     [rsp+50h+resume_handle], 0; resume_handle
0x180035168  lea     rcx, [rbp+arg_8]
0x18003516c  mov     [rsp+50h+totalentries], rcx; char *
0x180035171  lea     rcx, [rbp+arg_0]
0x180035175  mov     [rsp+50h+entriesread], rcx; entriesread
0x18003517a  or      r9d, 0FFFFFFFFh; prefmaxlen
0x18003517e  lea     r8, [rbp+bufptr]; bufptr
0x180035182  mov     edx, 1; level
0x180035187  mov     rcx, rax; servername
0x18003518a  call    cs:__imp_NetShareEnum
0x180035190  mov     r9d, eax; char *
0x180035193  mov     rcx, [rbp+18h]; this
0x180035197  lea     rax, aFailedToEnumer; "Failed to enumerate printer shares!"
0x18003519e  mov     [rsp+50h+entriesread], rax; unsigned int
0x1800351a3  lea     r8, aOnecoreuapPrin_3; "onecoreuap\\printscan\\print\\printscan"...
0x1800351aa  mov     edx, 74h ; 't'; void *
0x1800351af  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x1800351b4  lea     rax, [rbp+bufptr]
0x1800351b8  mov     [rbp+var_10], rax
0x1800351bc  mov     [rbp+var_8], 1
0x1800351c0  xor     ebx, ebx
0x1800351c2  mov     ecx, [rbp+arg_0]
0x1800351c5  test    ecx, ecx
0x1800351c7  jz      short loc_180035205
0x1800351c9  lea     rdx, [rbx+rbx*2]
0x1800351cd  mov     rax, [rbp+bufptr]
0x1800351d1  cmp     dword ptr [rax+rdx*8+8], 1
0x1800351d6  jnz     short loc_1800351FF
0x1800351d8  mov     rdx, [rax+rdx*8]; unsigned __int16 *
0x1800351dc  lea     rcx, [rbp+arg_18]; this
0x1800351e0  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x1800351e5  nop
0x1800351e6  mov     rdx, rdi; struct winrt::hstring *
0x1800351e9  lea     rcx, [rbp+arg_18]; this
0x1800351ed  call    ?UnsharePrinter@PrinterSharingUtility@@SAXAEBUhstring@winrt@@0@Z; PrinterSharingUtility::UnsharePrinter(winrt::hstring const &,winrt::hstring const &)
0x1800351f2  nop
0x1800351f3  lea     rcx, [rbp+arg_18]
0x1800351f7  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800351fc  mov     ecx, [rbp+arg_0]
0x1800351ff  inc     ebx
0x180035201  cmp     ebx, ecx
0x180035203  jb      short loc_1800351C9
0x180035205  mov     rcx, [rbp+bufptr]; Buffer
0x180035209  call    cs:__imp_NetApiBufferFree
0x18003520f  add     rsp, 50h
0x180035213  pop     rdi
0x180035214  pop     rbx
0x180035215  pop     rbp
0x180035216  retn
```
