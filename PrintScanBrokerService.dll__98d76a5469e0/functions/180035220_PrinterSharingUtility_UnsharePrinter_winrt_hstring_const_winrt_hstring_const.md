# PrinterSharingUtility::UnsharePrinter(winrt::hstring const &,winrt::hstring const &)

- ea: `0x180035220`
- end: `0x1800352c1`
- name: `?UnsharePrinter@PrinterSharingUtility@@SAXAEBUhstring@winrt@@0@Z`
- size: `161`
- prototype: `void __fastcall(const struct winrt::hstring *this, const struct winrt::hstring *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000f190`
- `0x18003512c`

## callees

- `0x18000fa2c`
- `0x18002b2cc`
- `0x180035220`
- `0x18003542c`

## import_xrefs

- `srvcli!NetShareDel` at `0x180035253`
- `srvcli!NetShareDel` at `0x180035253`
- `srvcli!NetShareDelSticky` at `0x18003529f`
- `srvcli!NetShareDelSticky` at `0x18003529f`

## string_xrefs

- `0x180035276`: `onecoreuap\printscan\print\printscanbroker\class\printersharingutility.cpp`

## pseudocode

```c
void __fastcall PrinterSharingUtility::UnsharePrinter(
        const struct winrt::hstring *this,
        const struct winrt::hstring *a2)
{
  WCHAR *v3; // rbx
  WCHAR *v4; // rax
  DWORD v5; // eax
  WCHAR *v6; // rax
  signed int v7; // eax
  void *v8; // rdx
  unsigned int v9; // r8d
  unsigned int v10; // [rsp+20h] [rbp-18h]
  unsigned int v11; // [rsp+20h] [rbp-18h]
  const char *v12; // [rsp+30h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( *(_QWORD *)a2 )
    v3 = (WCHAR *)winrt::hstring::c_str(a2);
  else
    v3 = 0;
  v4 = (WCHAR *)winrt::hstring::c_str(this);
  v5 = NetShareDel(v3, v4, 0);
  if ( v5 )
  {
    LOBYTE(v10) = v5 != 2310;
    wil::details::in1diag3::Throw_Win32IfMsg(
      retaddr,
      (void *)0x65,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\printersharingutility.cpp",
      (const char *)v5,
      v10,
      (bool)"Failed to unshare printer!",
      v12);
    v6 = (WCHAR *)winrt::hstring::c_str(this);
    v7 = NetShareDelSticky(v3, v6, 0);
    if ( v7 < 0 )
      wil::details::in1diag3::_Log_NtStatus(retaddr, v8, v9, (const char *)(unsigned int)v7, v11);
  }
}

```

## disassembly

```asm
0x180035220  mov     [rsp+arg_0], rbx
0x180035225  push    rdi; char *
0x180035226  sub     rsp, 30h
0x18003522a  cmp     qword ptr [rdx], 0
0x18003522e  mov     rdi, rcx
0x180035231  jnz     short loc_180035237
0x180035233  xor     ebx, ebx
0x180035235  jmp     short loc_180035242
0x180035237  mov     rcx, rdx; this
0x18003523a  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18003523f  mov     rbx, rax
0x180035242  mov     rcx, rdi; this
0x180035245  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18003524a  mov     rdx, rax; netname
0x18003524d  xor     r8d, r8d; reserved
0x180035250  mov     rcx, rbx; servername
0x180035253  call    cs:__imp_NetShareDel
0x180035259  test    eax, eax
0x18003525b  jz      short loc_1800352B6
0x18003525d  mov     rcx, [rsp+38h]; this
0x180035262  lea     r8, aFailedToUnshar; "Failed to unshare printer!"
0x180035269  mov     qword ptr [rsp+38h+var_10], r8; bool
0x18003526e  cmp     eax, 906h
0x180035273  mov     r9d, eax; char *
0x180035276  lea     r8, aOnecoreuapPrin_3; "onecoreuap\\printscan\\print\\printscan"...
0x18003527d  setnz   dl
0x180035280  mov     byte ptr [rsp+38h+var_18], dl; int
0x180035284  mov     edx, 65h ; 'e'; void *
0x180035289  call    ?Throw_Win32IfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDK_N1ZZ; wil::details::in1diag3::Throw_Win32IfMsg(void *,uint,char const *,ulong,bool,char const *,...)
0x18003528e  mov     rcx, rdi; this
0x180035291  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180035296  mov     rdx, rax; netname
0x180035299  xor     r8d, r8d; reserved
0x18003529c  mov     rcx, rbx; servername
0x18003529f  call    cs:__imp_NetShareDelSticky
0x1800352a5  test    eax, eax
0x1800352a7  jns     short loc_1800352B6
0x1800352a9  mov     rcx, [rsp+38h]; this
0x1800352ae  mov     r9d, eax; char *
0x1800352b1  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x1800352b6  mov     rbx, [rsp+38h+arg_0]
0x1800352bb  add     rsp, 30h
0x1800352bf  pop     rdi
0x1800352c0  retn
```
