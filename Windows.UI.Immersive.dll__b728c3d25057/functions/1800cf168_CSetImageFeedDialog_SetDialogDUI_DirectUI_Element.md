# CSetImageFeedDialog::_SetDialogDUI(DirectUI::Element *)

- ea: `0x1800cf168`
- end: `0x1800cf291`
- name: `?_SetDialogDUI@CSetImageFeedDialog@@AEAAJPEAVElement@DirectUI@@@Z`
- size: `297`
- prototype: `__int64 __fastcall(CSetImageFeedDialog *__hidden this, struct DirectUI::Element *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800cdfe0`

## callees

- `0x180050ba0`
- `0x1800cf168`
- `0x1800d95c8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800cf1b2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800cf1b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cf20a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cf264`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cf20a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cf264`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800cf1e7`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800cf257`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800cf1e7`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800cf257`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800cf1d9`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800cf249`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800cf1d9`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800cf249`
- `DUI70!StrToID` at `0x1800cf1cd`
- `DUI70!StrToID` at `0x1800cf23d`
- `DUI70!StrToID` at `0x1800cf1cd`
- `DUI70!StrToID` at `0x1800cf23d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSetImageFeedDialog::_SetDialogDUI(CSetImageFeedDialog *this, struct DirectUI::Element *a2)
{
  int v4; // ebx
  unsigned __int16 v5; // ax
  DirectUI::Element *Descendent; // rax
  int v7; // r8d
  unsigned __int16 v8; // ax
  DirectUI::Element *v9; // rax
  void *v11; // [rsp+20h] [rbp-248h]
  LPVOID pv[2]; // [rsp+30h] [rbp-238h] BYREF
  WCHAR Buffer[264]; // [rsp+40h] [rbp-228h] BYREF

  if ( *((_DWORD *)this + 6) == 38918 )
  {
    if ( LoadStringW(&_ImageBase, 0x95B7u, Buffer, 260) > 0 )
    {
      v5 = StrToID(L"idContent");
      Descendent = DirectUI::Element::FindDescendent(a2, v5);
      return (unsigned int)DirectUI::Element::SetContentString(Descendent, Buffer);
    }
    else
    {
      return (unsigned int)-2147467259;
    }
  }
  else
  {
    v4 = -2147467259;
    if ( *((_DWORD *)this + 6) == 38919 )
    {
      pv[0] = 0;
      CoTaskMemFree(0);
      v4 = TResourceStringAllocCopyEx<unsigned short *>(
             (int)&_ImageBase,
             *((_DWORD *)this + 9),
             v7,
             (int)&ResourceStringAllocCopyExCoAlloc,
             v11,
             pv);
      if ( v4 >= 0 )
      {
        v8 = StrToID(L"idContent");
        v9 = DirectUI::Element::FindDescendent(a2, v8);
        v4 = DirectUI::Element::SetContentString(v9, (const unsigned __int16 *)pv[0]);
      }
      CoTaskMemFree(pv[0]);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800cf168  mov     [rsp+arg_10], rbx
0x1800cf16d  mov     [rsp+arg_18], rsi
0x1800cf172  push    rdi
0x1800cf173  sub     rsp, 260h
0x1800cf17a  mov     rax, cs:__security_cookie
0x1800cf181  xor     rax, rsp
0x1800cf184  mov     [rsp+268h+var_18], rax
0x1800cf18c  mov     rsi, rdx
0x1800cf18f  mov     rdi, rcx
0x1800cf192  cmp     dword ptr [rcx+18h], 9806h
0x1800cf199  jnz     short loc_1800CF1F1
0x1800cf19b  mov     r9d, 104h; cchBufferMax
0x1800cf1a1  lea     r8, [rsp+268h+Buffer]; lpBuffer
0x1800cf1a6  mov     edx, 95B7h; uID
0x1800cf1ab  lea     rcx, __ImageBase; hInstance
0x1800cf1b2  call    cs:__imp_LoadStringW
0x1800cf1b8  test    eax, eax
0x1800cf1ba  jg      short loc_1800CF1C6
0x1800cf1bc  mov     ebx, 80004005h
0x1800cf1c1  jmp     loc_1800CF26A
0x1800cf1c6  lea     rcx, aIdcontent; "idContent"
0x1800cf1cd  call    cs:__imp_StrToID
0x1800cf1d3  movzx   edx, ax
0x1800cf1d6  mov     rcx, rsi
0x1800cf1d9  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800cf1df  lea     rdx, [rsp+268h+Buffer]
0x1800cf1e4  mov     rcx, rax
0x1800cf1e7  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x1800cf1ed  mov     ebx, eax
0x1800cf1ef  jmp     short loc_1800CF26A
0x1800cf1f1  mov     ebx, 80004005h
0x1800cf1f6  cmp     dword ptr [rcx+18h], 9807h
0x1800cf1fd  jnz     short loc_1800CF26A
0x1800cf1ff  mov     [rsp+268h+pv], 0
0x1800cf208  xor     ecx, ecx; pv
0x1800cf20a  call    cs:__imp_CoTaskMemFree
0x1800cf210  lea     rax, [rsp+268h+pv]
0x1800cf215  mov     [rsp+268h+var_240], rax; void *
0x1800cf21a  lea     r9, _ResourceStringAllocCopyExCoAlloc; int
0x1800cf221  mov     edx, [rdi+24h]; int
0x1800cf224  lea     rcx, __ImageBase; int
0x1800cf22b  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x1800cf230  mov     ebx, eax
0x1800cf232  test    eax, eax
0x1800cf234  js      short loc_1800CF25F
0x1800cf236  lea     rcx, aIdcontent; "idContent"
0x1800cf23d  call    cs:__imp_StrToID
0x1800cf243  movzx   edx, ax
0x1800cf246  mov     rcx, rsi
0x1800cf249  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800cf24f  mov     rdx, [rsp+268h+pv]
0x1800cf254  mov     rcx, rax
0x1800cf257  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x1800cf25d  mov     ebx, eax
0x1800cf25f  mov     rcx, [rsp+268h+pv]; pv
0x1800cf264  call    cs:__imp_CoTaskMemFree
0x1800cf26a  mov     eax, ebx
0x1800cf26c  mov     rcx, [rsp+268h+var_18]
0x1800cf274  xor     rcx, rsp; StackCookie
0x1800cf277  call    __security_check_cookie
0x1800cf27c  lea     r11, [rsp+268h+var_8]
0x1800cf284  mov     rbx, [r11+20h]
0x1800cf288  mov     rsi, [r11+28h]
0x1800cf28c  mov     rsp, r11
0x1800cf28f  pop     rdi
0x1800cf290  retn
```
