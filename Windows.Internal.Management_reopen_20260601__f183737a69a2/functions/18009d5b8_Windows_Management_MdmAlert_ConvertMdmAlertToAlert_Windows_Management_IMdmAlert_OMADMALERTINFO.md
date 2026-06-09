# Windows::Management::MdmAlert::ConvertMdmAlertToAlert(Windows::Management::IMdmAlert *,OMADMALERTINFO *)

- ea: `0x18009d5b8`
- end: `0x18009d8d2`
- name: `?ConvertMdmAlertToAlert@MdmAlert@Management@Windows@@SAJPEAUIMdmAlert@23@PEAUOMADMALERTINFO@@@Z`
- size: `794`
- prototype: `static int(struct Windows::Management::IMdmAlert *, struct OMADMALERTINFO *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18009d8d8`

## callees

- `0x180005a74`
- `0x18000a5c4`
- `0x18009d5b8`
- `0x18009dc60`
- `0x18009dc9c`
- `0x1800bb010`

## import_xrefs

- `DMCmnUtils!CopyString` at `0x18009d650`
- `DMCmnUtils!CopyString` at `0x18009d6df`
- `DMCmnUtils!CopyString` at `0x18009d76b`
- `DMCmnUtils!CopyString` at `0x18009d7f7`
- `DMCmnUtils!CopyString` at `0x18009d650`
- `DMCmnUtils!CopyString` at `0x18009d6df`
- `DMCmnUtils!CopyString` at `0x18009d76b`
- `DMCmnUtils!CopyString` at `0x18009d7f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009d601`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009d670`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009d690`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009d6ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009d71c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009d78b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009d7a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009d87f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009d8b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009d601`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009d670`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009d690`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009d6ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009d71c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009d78b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009d7a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009d87f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009d8b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009d63a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009d6c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009d755`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009d7e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009d63a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009d6c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009d755`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009d7e1`
- `omadmapi!__imp_OmaDmFreeAlertInfo` at `0x18009d896`
- `omadmapi!__imp_OmaDmFreeAlertInfo` at `0x18009d896`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Management::MdmAlert::ConvertMdmAlertToAlert(
        struct Windows::Management::IMdmAlert *a1,
        unsigned __int16 **a2)
{
  __int64 (__fastcall *v4)(struct Windows::Management::IMdmAlert *, HSTRING *); // rbx
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  const unsigned __int16 *StringRawBuffer; // rax
  __int64 (__fastcall *v9)(struct Windows::Management::IMdmAlert *, HSTRING *); // rbx
  const unsigned __int16 *v10; // rax
  __int64 (__fastcall *v11)(struct Windows::Management::IMdmAlert *, HSTRING *); // rbx
  const unsigned __int16 *v12; // rax
  __int64 (__fastcall *v13)(struct Windows::Management::IMdmAlert *, HSTRING *); // rbx
  const unsigned __int16 *v14; // rax
  int v16; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  unsigned int v18; // [rsp+50h] [rbp+20h] BYREF
  unsigned int v19; // [rsp+58h] [rbp+28h] BYREF
  HSTRING string; // [rsp+60h] [rbp+30h] BYREF

  v16 = (int)a2;
  memset_0(a2, 0, 0x40u);
  *(_DWORD *)a2 = 64;
  *((_DWORD *)a2 + 1) = 1226;
  string = 0;
  v4 = *(__int64 (__fastcall **)(struct Windows::Management::IMdmAlert *, HSTRING *))(*(_QWORD *)a1 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  v5 = v4(a1, &string);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 363;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\winrt\\lib\\mdmsync\\mdmalert.cpp",
      (const char *)(unsigned int)v5,
      v16);
    WindowsDeleteString(string);
    string = 0;
    OmaDmFreeAlertInfo(a2);
    return v6;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v5 = CopyString(StringRawBuffer, 0xFFFFFFFF, a2 + 3);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 367;
    goto LABEL_21;
  }
  WindowsDeleteString(string);
  string = 0;
  v9 = *(__int64 (__fastcall **)(struct Windows::Management::IMdmAlert *, HSTRING *))(*(_QWORD *)a1 + 136LL);
  WindowsDeleteString(0);
  string = 0;
  v5 = v9(a1, &string);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 370;
    goto LABEL_21;
  }
  v10 = WindowsGetStringRawBuffer(string, 0);
  v5 = CopyString(v10, 0xFFFFFFFF, a2 + 1);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 374;
    goto LABEL_21;
  }
  WindowsDeleteString(string);
  string = 0;
  v11 = *(__int64 (__fastcall **)(struct Windows::Management::IMdmAlert *, HSTRING *))(*(_QWORD *)a1 + 96LL);
  WindowsDeleteString(0);
  string = 0;
  v5 = v11(a1, &string);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 377;
    goto LABEL_21;
  }
  v12 = WindowsGetStringRawBuffer(string, 0);
  v5 = CopyString(v12, 0xFFFFFFFF, a2 + 2);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 381;
    goto LABEL_21;
  }
  WindowsDeleteString(string);
  string = 0;
  v13 = *(__int64 (__fastcall **)(struct Windows::Management::IMdmAlert *, HSTRING *))(*(_QWORD *)a1 + 120LL);
  WindowsDeleteString(0);
  string = 0;
  v5 = v13(a1, &string);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 384;
    goto LABEL_21;
  }
  v14 = WindowsGetStringRawBuffer(string, 0);
  v5 = CopyString(v14, 0xFFFFFFFF, a2 + 7);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 388;
    goto LABEL_21;
  }
  v18 = 0;
  v5 = (*(__int64 (__fastcall **)(struct Windows::Management::IMdmAlert *, unsigned int *))(*(_QWORD *)a1 + 80LL))(
         a1,
         &v18);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 391;
    goto LABEL_21;
  }
  *((_DWORD *)a2 + 9) = GetOmaDmMarkFromMdmAlertMark(v18);
  v19 = 0;
  v5 = (*(__int64 (__fastcall **)(struct Windows::Management::IMdmAlert *, unsigned int *))(*(_QWORD *)a1 + 64LL))(
         a1,
         &v19);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 395;
    goto LABEL_21;
  }
  *((_DWORD *)a2 + 8) = GetCfgDataTypeFromMdmAlertDataType(v19);
  WindowsDeleteString(string);
  return 0;
}

```

## disassembly

```asm
0x18009d5b8  mov     [rsp-18h+arg_18], rbx
0x18009d5bd  push    rbp
0x18009d5be  push    rsi
0x18009d5bf  push    rdi
0x18009d5c0  mov     rbp, rsp
0x18009d5c3  sub     rsp, 30h
0x18009d5c7  mov     rsi, rdx
0x18009d5ca  mov     rdi, rcx
0x18009d5cd  mov     [rbp+var_10], rdx
0x18009d5d1  mov     [rbp+var_8], 1
0x18009d5d5  mov     ebx, 40h ; '@'
0x18009d5da  mov     r8d, ebx; Size
0x18009d5dd  xor     edx, edx; Val
0x18009d5df  mov     rcx, rsi; void *
0x18009d5e2  call    memset_0
0x18009d5e7  mov     [rsi], ebx
0x18009d5e9  mov     dword ptr [rsi+4], 4CAh
0x18009d5f0  mov     [rbp+string], 0
0x18009d5f8  mov     rax, [rdi]
0x18009d5fb  mov     rbx, [rax+30h]
0x18009d5ff  xor     ecx, ecx; string
0x18009d601  call    cs:__imp_WindowsDeleteString
0x18009d608  nop     dword ptr [rax+rax+00h]
0x18009d60d  mov     [rbp+string], 0
0x18009d615  lea     rdx, [rbp+string]
0x18009d619  mov     rcx, rdi
0x18009d61c  mov     rax, rbx
0x18009d61f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d624  mov     ebx, eax
0x18009d626  test    eax, eax
0x18009d628  jns     short loc_18009D634
0x18009d62a  mov     edx, 16Bh
0x18009d62f  jmp     loc_18009D867
0x18009d634  xor     edx, edx; length
0x18009d636  mov     rcx, [rbp+string]; string
0x18009d63a  call    cs:__imp_WindowsGetStringRawBuffer
0x18009d641  nop     dword ptr [rax+rax+00h]
0x18009d646  lea     r8, [rsi+18h]
0x18009d64a  or      edx, 0FFFFFFFFh
0x18009d64d  mov     rcx, rax
0x18009d650  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18009d657  nop     dword ptr [rax+rax+00h]
0x18009d65c  mov     ebx, eax
0x18009d65e  test    eax, eax
0x18009d660  jns     short loc_18009D66C
0x18009d662  mov     edx, 16Fh
0x18009d667  jmp     loc_18009D867
0x18009d66c  mov     rcx, [rbp+string]; string
0x18009d670  call    cs:__imp_WindowsDeleteString
0x18009d677  nop     dword ptr [rax+rax+00h]
0x18009d67c  mov     [rbp+string], 0
0x18009d684  mov     rax, [rdi]
0x18009d687  mov     rbx, [rax+88h]
0x18009d68e  xor     ecx, ecx; string
0x18009d690  call    cs:__imp_WindowsDeleteString
0x18009d697  nop     dword ptr [rax+rax+00h]
0x18009d69c  mov     [rbp+string], 0
0x18009d6a4  lea     rdx, [rbp+string]
0x18009d6a8  mov     rcx, rdi
0x18009d6ab  mov     rax, rbx
0x18009d6ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d6b3  mov     ebx, eax
0x18009d6b5  test    eax, eax
0x18009d6b7  jns     short loc_18009D6C3
0x18009d6b9  mov     edx, 172h
0x18009d6be  jmp     loc_18009D867
0x18009d6c3  xor     edx, edx; length
0x18009d6c5  mov     rcx, [rbp+string]; string
0x18009d6c9  call    cs:__imp_WindowsGetStringRawBuffer
0x18009d6d0  nop     dword ptr [rax+rax+00h]
0x18009d6d5  lea     r8, [rsi+8]
0x18009d6d9  or      edx, 0FFFFFFFFh
0x18009d6dc  mov     rcx, rax
0x18009d6df  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18009d6e6  nop     dword ptr [rax+rax+00h]
0x18009d6eb  mov     ebx, eax
0x18009d6ed  test    eax, eax
0x18009d6ef  jns     short loc_18009D6FB
0x18009d6f1  mov     edx, 176h
0x18009d6f6  jmp     loc_18009D867
0x18009d6fb  mov     rcx, [rbp+string]; string
0x18009d6ff  call    cs:__imp_WindowsDeleteString
0x18009d706  nop     dword ptr [rax+rax+00h]
0x18009d70b  mov     [rbp+string], 0
0x18009d713  mov     rax, [rdi]
0x18009d716  mov     rbx, [rax+60h]
0x18009d71a  xor     ecx, ecx; string
0x18009d71c  call    cs:__imp_WindowsDeleteString
0x18009d723  nop     dword ptr [rax+rax+00h]
0x18009d728  mov     [rbp+string], 0
0x18009d730  lea     rdx, [rbp+string]
0x18009d734  mov     rcx, rdi
0x18009d737  mov     rax, rbx
0x18009d73a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d73f  mov     ebx, eax
0x18009d741  test    eax, eax
0x18009d743  jns     short loc_18009D74F
0x18009d745  mov     edx, 179h
0x18009d74a  jmp     loc_18009D867
0x18009d74f  xor     edx, edx; length
0x18009d751  mov     rcx, [rbp+string]; string
0x18009d755  call    cs:__imp_WindowsGetStringRawBuffer
0x18009d75c  nop     dword ptr [rax+rax+00h]
0x18009d761  lea     r8, [rsi+10h]
0x18009d765  or      edx, 0FFFFFFFFh
0x18009d768  mov     rcx, rax
0x18009d76b  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18009d772  nop     dword ptr [rax+rax+00h]
0x18009d777  mov     ebx, eax
0x18009d779  test    eax, eax
0x18009d77b  jns     short loc_18009D787
0x18009d77d  mov     edx, 17Dh
0x18009d782  jmp     loc_18009D867
0x18009d787  mov     rcx, [rbp+string]; string
0x18009d78b  call    cs:__imp_WindowsDeleteString
0x18009d792  nop     dword ptr [rax+rax+00h]
0x18009d797  mov     [rbp+string], 0
0x18009d79f  mov     rax, [rdi]
0x18009d7a2  mov     rbx, [rax+78h]
0x18009d7a6  xor     ecx, ecx; string
0x18009d7a8  call    cs:__imp_WindowsDeleteString
0x18009d7af  nop     dword ptr [rax+rax+00h]
0x18009d7b4  mov     [rbp+string], 0
0x18009d7bc  lea     rdx, [rbp+string]
0x18009d7c0  mov     rcx, rdi
0x18009d7c3  mov     rax, rbx
0x18009d7c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d7cb  mov     ebx, eax
0x18009d7cd  test    eax, eax
0x18009d7cf  jns     short loc_18009D7DB
0x18009d7d1  mov     edx, 180h
0x18009d7d6  jmp     loc_18009D867
0x18009d7db  xor     edx, edx; length
0x18009d7dd  mov     rcx, [rbp+string]; string
0x18009d7e1  call    cs:__imp_WindowsGetStringRawBuffer
0x18009d7e8  nop     dword ptr [rax+rax+00h]
0x18009d7ed  lea     r8, [rsi+38h]
0x18009d7f1  or      edx, 0FFFFFFFFh
0x18009d7f4  mov     rcx, rax
0x18009d7f7  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18009d7fe  nop     dword ptr [rax+rax+00h]
0x18009d803  mov     ebx, eax
0x18009d805  test    eax, eax
0x18009d807  jns     short loc_18009D810
0x18009d809  mov     edx, 184h
0x18009d80e  jmp     short loc_18009D867
0x18009d810  mov     [rbp+arg_0], 0
0x18009d817  mov     rax, [rdi]
0x18009d81a  lea     rdx, [rbp+arg_0]
0x18009d81e  mov     rcx, rdi
0x18009d821  mov     rax, [rax+50h]
0x18009d825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d82a  mov     ebx, eax
0x18009d82c  test    eax, eax
0x18009d82e  jns     short loc_18009D837
0x18009d830  mov     edx, 187h
0x18009d835  jmp     short loc_18009D867
0x18009d837  mov     ecx, [rbp+arg_0]
0x18009d83a  call    ?GetOmaDmMarkFromMdmAlertMark@@YA?AW4OMADM_MARK@@W4MdmAlertMark@Management@Windows@@@Z; GetOmaDmMarkFromMdmAlertMark(Windows::Management::MdmAlertMark)
0x18009d83f  mov     [rsi+24h], eax
0x18009d842  mov     [rbp+arg_8], 0
0x18009d849  mov     rax, [rdi]
0x18009d84c  lea     rdx, [rbp+arg_8]
0x18009d850  mov     rcx, rdi
0x18009d853  mov     rax, [rax+40h]
0x18009d857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d85c  mov     ebx, eax
0x18009d85e  test    eax, eax
0x18009d860  jns     short loc_18009D8A6
0x18009d862  mov     edx, 18Bh; void *
0x18009d867  mov     r9d, eax; char *
0x18009d86a  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\enterprisemgmt\\winr"...
0x18009d871  mov     rcx, [rbp+18h]; this
0x18009d875  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009d87a  nop
0x18009d87b  mov     rcx, [rbp+string]; string
0x18009d87f  call    cs:__imp_WindowsDeleteString
0x18009d886  nop     dword ptr [rax+rax+00h]
0x18009d88b  mov     [rbp+string], 0
0x18009d893  mov     rcx, rsi
0x18009d896  call    cs:__imp_OmaDmFreeAlertInfo
0x18009d89d  nop     dword ptr [rax+rax+00h]
0x18009d8a2  mov     eax, ebx
0x18009d8a4  jmp     short loc_18009D8C4
0x18009d8a6  mov     ecx, [rbp+arg_8]
0x18009d8a9  call    ?GetCfgDataTypeFromMdmAlertDataType@@YA?AW4ConfigDataType@@W4MdmAlertDataType@Management@Windows@@@Z; GetCfgDataTypeFromMdmAlertDataType(Windows::Management::MdmAlertDataType)
0x18009d8ae  mov     [rsi+20h], eax
0x18009d8b1  mov     rcx, [rbp+string]; string
0x18009d8b5  call    cs:__imp_WindowsDeleteString
0x18009d8bc  nop     dword ptr [rax+rax+00h]
0x18009d8c1  nop
0x18009d8c2  xor     eax, eax
0x18009d8c4  mov     rbx, [rsp+30h+arg_18]
0x18009d8c9  add     rsp, 30h
0x18009d8cd  pop     rdi
0x18009d8ce  pop     rsi
0x18009d8cf  pop     rbp
0x18009d8d0  retn
```
