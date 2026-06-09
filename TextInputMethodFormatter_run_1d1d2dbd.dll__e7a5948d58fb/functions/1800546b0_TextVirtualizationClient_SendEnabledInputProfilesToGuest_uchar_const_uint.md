# TextVirtualizationClient::SendEnabledInputProfilesToGuest(uchar const *,uint)

- ea: `0x1800546b0`
- end: `0x180054739`
- name: `?SendEnabledInputProfilesToGuest@TextVirtualizationClient@@UEAAJPEBEI@Z`
- size: `137`
- prototype: `__int64 __fastcall(TextVirtualizationClient *__hidden this, const unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180006a14`
- `0x180012030`
- `0x1800546b0`
- `0x180054740`

## import_xrefs

- `CoreMessaging!MsgBlobCreateShared` at `0x1800546df`
- `CoreMessaging!MsgBlobCreateShared` at `0x1800546df`
- `CoreMessaging!MsgRelease` at `0x1800546d1`
- `CoreMessaging!MsgRelease` at `0x1800546d1`

## pseudocode

```c
__int64 __fastcall TextVirtualizationClient::SendEnabledInputProfilesToGuest(
        TextVirtualizationClient *this,
        const unsigned __int8 *a2,
        __int64 a3,
        __int64 a4)
{
  char *v4; // rdi
  __int64 v6; // rcx
  unsigned int v7; // esi
  int Shared; // eax
  int v10; // eax
  unsigned int v11; // ebx
  int v13; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v4 = (char *)this + 152;
  v6 = *((_QWORD *)this + 19);
  v7 = a3;
  if ( v6 )
    MsgRelease(v6, a2, a3, a4);
  Shared = MsgBlobCreateShared(a2, v7, v4);
  if ( Shared < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x175,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\textvirtualizationproxy\\TextVirtualizationClient.cpp",
      (const char *)(unsigned int)Shared,
      v13);
  v10 = TextVirtualizationClient::SendEnabledInputProfilesToGuestImpl(this);
  v11 = v10;
  if ( v10 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x177,
    (unsigned int)"mincore\\textinput\\dev\\virtualization\\textvirtualizationproxy\\TextVirtualizationClient.cpp",
    (const char *)(unsigned int)v10,
    v13);
  return v11;
}

```

## disassembly

```asm
0x1800546b0  push    rbx
0x1800546b2  push    rbp
0x1800546b3  push    rsi
0x1800546b4  push    rdi
0x1800546b5  sub     rsp, 28h
0x1800546b9  lea     rdi, [rcx+98h]
0x1800546c0  mov     rbx, rcx
0x1800546c3  mov     rcx, [rdi]
0x1800546c6  mov     esi, r8d
0x1800546c9  mov     rbp, rdx
0x1800546cc  test    rcx, rcx
0x1800546cf  jz      short loc_1800546D7
0x1800546d1  call    cs:__imp_MsgRelease
0x1800546d7  mov     r8, rdi
0x1800546da  mov     edx, esi
0x1800546dc  mov     rcx, rbp
0x1800546df  call    cs:__imp_MsgBlobCreateShared
0x1800546e5  test    eax, eax
0x1800546e7  js      short loc_18005471F
0x1800546e9  mov     rcx, rbx; this
0x1800546ec  call    ?SendEnabledInputProfilesToGuestImpl@TextVirtualizationClient@@AEAAJXZ; TextVirtualizationClient::SendEnabledInputProfilesToGuestImpl(void)
0x1800546f1  mov     ebx, eax
0x1800546f3  test    eax, eax
0x1800546f5  jns     short loc_180054714
0x1800546f7  mov     rcx, [rsp+48h]; this
0x1800546fc  lea     r8, aMincoreTextinp_10; "mincore\\textinput\\dev\\virtualization"...
0x180054703  mov     r9d, eax; char *
0x180054706  mov     edx, 177h; void *
0x18005470b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054710  mov     eax, ebx
0x180054712  jmp     short loc_180054716
0x180054714  xor     eax, eax
0x180054716  add     rsp, 28h
0x18005471a  pop     rdi
0x18005471b  pop     rsi
0x18005471c  pop     rbp
0x18005471d  pop     rbx
0x18005471e  retn
0x18005471f  mov     rcx, [rsp+48h]; this
0x180054724  lea     r8, aMincoreTextinp_10; "mincore\\textinput\\dev\\virtualization"...
0x18005472b  mov     r9d, eax; char *
0x18005472e  mov     edx, 175h; void *
0x180054733  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
