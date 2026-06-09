# CMapi2RowFilter::CBaseProps::AddSenderToPeopleDupCheck(CMapi2RowFilter::CBaseProps *,MapiFpsPropVal *)

- ea: `0x180019dc0`
- end: `0x180019e9b`
- name: `?AddSenderToPeopleDupCheck@CBaseProps@CMapi2RowFilter@@KAJPEAV12@PEAUMapiFpsPropVal@@@Z`
- size: `219`
- prototype: `__int64 __fastcall(PCNZWCH *, struct MapiFpsPropVal *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001cc10`
- `0x180021c70`

## callees

- `0x180002300`
- `0x180013fac`
- `0x180019dc0`
- `0x180019ea4`
- `0x180021d54`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180019e52`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180019e52`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CMapi2RowFilter::CBaseProps::AddSenderToPeopleDupCheck(PCNZWCH *a1, struct MapiFpsPropVal *a2)
{
  unsigned int v4; // ebx
  void **v6; // [rsp+30h] [rbp-838h] BYREF
  PCNZWCH lpString2; // [rsp+38h] [rbp-830h]
  __int64 v8; // [rsp+40h] [rbp-828h]
  __int16 v9; // [rsp+48h] [rbp-820h] BYREF

  lpString2 = (PCNZWCH)&v9;
  v8 = 1025;
  v9 = 0;
  v6 = &TLMString<1024,1024,1048576>::`vftable';
  CMapi2RowFilter::CBaseProps::SetUtilString(a1, *((_QWORD *)a2 + 1), &v6);
  if ( !*((_DWORD *)a1 + 3147) || (v4 = 1, HIDWORD(v8)) && CompareStringW(0x7Fu, 1u, a1[1572], -1, lpString2, -1) != 2 )
    v4 = CMapi2RowFilter::CBaseProps::AddToPeople((struct CMapi2RowFilter::CBaseProps *)a1, a2);
  TLMString<1024,1024,1048576>::~TLMString<1024,1024,1048576>((wchar_t *)&v6);
  return v4;
}

```

## disassembly

```asm
0x180019dc0  mov     [rsp+arg_10], rbx
0x180019dc5  mov     [rsp+arg_18], rsi
0x180019dca  push    rdi
0x180019dcb  sub     rsp, 860h
0x180019dd2  mov     rax, cs:__security_cookie
0x180019dd9  xor     rax, rsp
0x180019ddc  mov     [rsp+868h+var_18], rax
0x180019de4  mov     rsi, rdx
0x180019de7  mov     rdi, rcx
0x180019dea  lea     rax, [rsp+868h+var_820]
0x180019def  mov     [rsp+868h+var_830], rax
0x180019df4  mov     [rsp+868h+var_828], 401h
0x180019dfd  xor     eax, eax
0x180019dff  mov     [rsp+868h+var_820], ax
0x180019e04  lea     rax, ??_7?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@6B@; const TLMString<1024,1024,1048576>::`vftable'
0x180019e0b  mov     [rsp+868h+var_838], rax
0x180019e10  lea     r8, [rsp+868h+var_838]
0x180019e15  mov     rdx, [rdx+8]
0x180019e19  call    ?SetUtilString@CBaseProps@CMapi2RowFilter@@IEAAXPEAU_SPropValue@@AEAV?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@@Z; CMapi2RowFilter::CBaseProps::SetUtilString(_SPropValue *,TLMString<1024,1024,1048576> &)
0x180019e1e  cmp     dword ptr [rdi+312Ch], 0
0x180019e25  jz      short loc_180019E5D
0x180019e27  mov     ebx, 1
0x180019e2c  cmp     dword ptr [rsp+868h+var_828+4], 0
0x180019e31  jz      short loc_180019E6A
0x180019e33  or      r9d, 0FFFFFFFFh; cchCount1
0x180019e37  mov     [rsp+868h+cchCount2], r9d; cchCount2
0x180019e3c  mov     rax, [rsp+868h+var_830]
0x180019e41  mov     [rsp+868h+lpString2], rax; lpString2
0x180019e46  mov     r8, [rdi+3120h]; lpString1
0x180019e4d  mov     edx, ebx; dwCmpFlags
0x180019e4f  lea     ecx, [rbx+7Eh]; Locale
0x180019e52  call    cs:__imp_CompareStringW
0x180019e58  cmp     eax, 2
0x180019e5b  jz      short loc_180019E6A
0x180019e5d  mov     rdx, rsi; struct MapiFpsPropVal *
0x180019e60  mov     rcx, rdi; struct CMapi2RowFilter::CBaseProps *
0x180019e63  call    ?AddToPeople@CBaseProps@CMapi2RowFilter@@KAJPEAV12@PEAUMapiFpsPropVal@@@Z; CMapi2RowFilter::CBaseProps::AddToPeople(CMapi2RowFilter::CBaseProps *,MapiFpsPropVal *)
0x180019e68  mov     ebx, eax
0x180019e6a  lea     rcx, [rsp+868h+var_838]
0x180019e6f  call    ??1?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@UEAA@XZ; TLMString<1024,1024,1048576>::~TLMString<1024,1024,1048576>(void)
0x180019e74  mov     eax, ebx
0x180019e76  mov     rcx, [rsp+868h+var_18]
0x180019e7e  xor     rcx, rsp; StackCookie
0x180019e81  call    __security_check_cookie
0x180019e86  lea     r11, [rsp+868h+var_8]
0x180019e8e  mov     rbx, [r11+20h]
0x180019e92  mov     rsi, [r11+28h]
0x180019e96  mov     rsp, r11
0x180019e99  pop     rdi
0x180019e9a  retn
```
