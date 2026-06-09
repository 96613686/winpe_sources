# PrinterSharingUtility::IsSamePrinterShare(winrt::hstring const &,winrt::hstring const &,winrt::hstring const &,bool &)

- ea: `0x180034ff4`
- end: `0x1800350ec`
- name: `?IsSamePrinterShare@PrinterSharingUtility@@SAXAEBUhstring@winrt@@00AEA_N@Z`
- size: `248`
- prototype: `void __fastcall(const struct winrt::hstring *this, const struct winrt::hstring *, const struct winrt::hstring *, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000b5a0`

## callees

- `0x18000fa2c`
- `0x18001cfd4`
- `0x18001d0e4`
- `0x180034ff4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800350c9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800350c9`
- `srvcli!NetShareGetInfo` at `0x180035043`
- `srvcli!NetShareGetInfo` at `0x180035043`
- `netutils!NetApiBufferFree` at `0x1800350db`
- `netutils!NetApiBufferFree` at `0x1800350db`

## string_xrefs

- `0x18003505d`: `onecoreuap\printscan\print\printscanbroker\class\printersharingutility.cpp`
- `0x1800350a4`: `onecoreuap\printscan\print\printscanbroker\class\printersharingutility.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PrinterSharingUtility::IsSamePrinterShare(
        const struct winrt::hstring *this,
        const struct winrt::hstring *a2,
        const struct winrt::hstring *a3,
        bool *a4)
{
  winrt::hstring *v6; // rdx
  WCHAR *v7; // rax
  LPWSTR v8; // r10
  DWORD Info; // eax
  const unsigned __int16 *v10; // rax
  const char *v11; // [rsp+28h] [rbp-20h]
  char v12; // [rsp+38h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  LPBYTE bufptr; // [rsp+60h] [rbp+18h] BYREF

  v6 = this;
  *a4 = 0;
  bufptr = 0;
  if ( *(_QWORD *)a3 )
    winrt::hstring::c_str(a3);
  v7 = (WCHAR *)winrt::hstring::c_str(v6);
  Info = NetShareGetInfo(v8, v7, 0x1F7u, &bufptr);
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)0x8B,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\printersharingutility.cpp",
    (const char *)Info,
    (unsigned int)"NetShareGetInfo failed!",
    v11);
  v12 = 1;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x91,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\printersharingutility.cpp",
    (const char *)0x8000FFFFLL,
    *((_DWORD *)bufptr + 2) != 1,
    (bool)"Share type is not STYPE_PRINTQ!",
    (const char *)&bufptr,
    v12);
  v10 = winrt::hstring::c_str(a2);
  *a4 = (unsigned int)_o__wcsicmp(*((_QWORD *)bufptr + 5), v10) == 0;
  NetApiBufferFree(bufptr);
}

```

## disassembly

```asm
0x180034ff4  mov     [rsp+arg_0], rbx
0x180034ff9  push    rdi
0x180034ffa  sub     rsp, 40h
0x180034ffe  mov     rbx, r9
0x180035001  mov     rdi, rdx
0x180035004  mov     rdx, rcx
0x180035007  mov     byte ptr [r9], 0
0x18003500b  mov     [rsp+48h+bufptr], 0
0x180035014  cmp     qword ptr [r8], 0
0x180035018  jnz     short loc_18003501F
0x18003501a  xor     r10d, r10d
0x18003501d  jmp     short loc_18003502A
0x18003501f  mov     rcx, r8; this
0x180035022  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180035027  mov     r10, rax
0x18003502a  mov     rcx, rdx; this
0x18003502d  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180035032  mov     rdx, rax; netname
0x180035035  lea     r9, [rsp+48h+bufptr]; bufptr
0x18003503a  mov     r8d, 1F7h; level
0x180035040  mov     rcx, r10; servername
0x180035043  call    cs:__imp_NetShareGetInfo
0x180035049  mov     r9d, eax; char *
0x18003504c  mov     rcx, [rsp+48h]; this
0x180035051  lea     rax, aNetsharegetinf; "NetShareGetInfo failed!"
0x180035058  mov     qword ptr [rsp+48h+var_28], rax; unsigned int
0x18003505d  lea     r8, aOnecoreuapPrin_3; "onecoreuap\\printscan\\print\\printscan"...
0x180035064  mov     edx, 8Bh; void *
0x180035069  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18003506e  lea     rax, [rsp+48h+bufptr]
0x180035073  mov     [rsp+48h+var_18], rax; char *
0x180035078  mov     [rsp+48h+var_10], 1
0x18003507d  mov     rax, [rsp+48h+bufptr]
0x180035082  cmp     dword ptr [rax+8], 1
0x180035086  setnz   al
0x180035089  mov     rcx, [rsp+48h]; this
0x18003508e  lea     rdx, aShareTypeIsNot; "Share type is not STYPE_PRINTQ!"
0x180035095  mov     qword ptr [rsp+48h+var_20], rdx; bool
0x18003509a  mov     [rsp+48h+var_28], al; char
0x18003509e  mov     r9d, 8000FFFFh; char *
0x1800350a4  lea     r8, aOnecoreuapPrin_3; "onecoreuap\\printscan\\print\\printscan"...
0x1800350ab  mov     edx, 91h; void *
0x1800350b0  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800350b5  mov     rcx, rdi; this
0x1800350b8  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x1800350bd  mov     rdx, rax
0x1800350c0  mov     rcx, [rsp+48h+bufptr]
0x1800350c5  mov     rcx, [rcx+28h]
0x1800350c9  call    cs:__imp__o__wcsicmp
0x1800350cf  test    eax, eax
0x1800350d1  setz    al
0x1800350d4  mov     [rbx], al
0x1800350d6  mov     rcx, [rsp+48h+bufptr]; Buffer
0x1800350db  call    cs:__imp_NetApiBufferFree
0x1800350e1  mov     rbx, [rsp+48h+arg_0]
0x1800350e6  add     rsp, 40h
0x1800350ea  pop     rdi
0x1800350eb  retn
```
