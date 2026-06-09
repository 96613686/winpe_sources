# Windows::Management::MdmAlert::ConvertMdmAlertToAlert(Windows::Management::IMdmAlert *,OMADMALERTINFO *)

- ea: `0x18009a8dc`
- end: `0x18009ab89`
- name: `?ConvertMdmAlertToAlert@MdmAlert@Management@Windows@@SAJPEAUIMdmAlert@23@PEAUOMADMALERTINFO@@@Z`
- size: `685`
- prototype: `static int(struct Windows::Management::IMdmAlert *, struct OMADMALERTINFO *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18009ab90`

## callees

- `0x180005904`
- `0x18000a2a4`
- `0x18009a8dc`
- `0x18009af00`
- `0x18009af34`
- `0x1800b7010`

## import_xrefs

- `DMCmnUtils!CopyString` at `0x18009a968`
- `DMCmnUtils!CopyString` at `0x18009a9df`
- `DMCmnUtils!CopyString` at `0x18009aa53`
- `DMCmnUtils!CopyString` at `0x18009aac7`
- `DMCmnUtils!CopyString` at `0x18009a968`
- `DMCmnUtils!CopyString` at `0x18009a9df`
- `DMCmnUtils!CopyString` at `0x18009aa53`
- `DMCmnUtils!CopyString` at `0x18009aac7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009a925`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009a982`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009a99c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009a9f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009aa10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009aa6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009aa84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ab49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ab73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009a925`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009a982`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009a99c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009a9f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009aa10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009aa6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009aa84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ab49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ab73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009a958`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009a9cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009aa43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009aab7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009a958`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009a9cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009aa43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009aab7`
- `omadmapi!__imp_OmaDmFreeAlertInfo` at `0x18009ab5a`
- `omadmapi!__imp_OmaDmFreeAlertInfo` at `0x18009ab5a`

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
0x18009a8dc  mov     [rsp-18h+arg_18], rbx
0x18009a8e1  push    rbp
0x18009a8e2  push    rsi
0x18009a8e3  push    rdi
0x18009a8e4  mov     rbp, rsp
0x18009a8e7  sub     rsp, 30h
0x18009a8eb  mov     rsi, rdx
0x18009a8ee  mov     rdi, rcx
0x18009a8f1  mov     [rbp+var_10], rdx
0x18009a8f5  mov     [rbp+var_8], 1
0x18009a8f9  mov     ebx, 40h ; '@'
0x18009a8fe  mov     r8d, ebx; Size
0x18009a901  xor     edx, edx; Val
0x18009a903  mov     rcx, rsi; void *
0x18009a906  call    memset_0
0x18009a90b  mov     [rsi], ebx
0x18009a90d  mov     dword ptr [rsi+4], 4CAh
0x18009a914  mov     [rbp+string], 0
0x18009a91c  mov     rax, [rdi]
0x18009a91f  mov     rbx, [rax+30h]
0x18009a923  xor     ecx, ecx; string
0x18009a925  call    cs:__imp_WindowsDeleteString
0x18009a92b  mov     [rbp+string], 0
0x18009a933  lea     rdx, [rbp+string]
0x18009a937  mov     rcx, rdi
0x18009a93a  mov     rax, rbx
0x18009a93d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a942  mov     ebx, eax
0x18009a944  test    eax, eax
0x18009a946  jns     short loc_18009A952
0x18009a948  mov     edx, 16Bh
0x18009a94d  jmp     loc_18009AB31
0x18009a952  xor     edx, edx; length
0x18009a954  mov     rcx, [rbp+string]; string
0x18009a958  call    cs:__imp_WindowsGetStringRawBuffer
0x18009a95e  lea     r8, [rsi+18h]
0x18009a962  or      edx, 0FFFFFFFFh
0x18009a965  mov     rcx, rax
0x18009a968  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18009a96e  mov     ebx, eax
0x18009a970  test    eax, eax
0x18009a972  jns     short loc_18009A97E
0x18009a974  mov     edx, 16Fh
0x18009a979  jmp     loc_18009AB31
0x18009a97e  mov     rcx, [rbp+string]; string
0x18009a982  call    cs:__imp_WindowsDeleteString
0x18009a988  mov     [rbp+string], 0
0x18009a990  mov     rax, [rdi]
0x18009a993  mov     rbx, [rax+88h]
0x18009a99a  xor     ecx, ecx; string
0x18009a99c  call    cs:__imp_WindowsDeleteString
0x18009a9a2  mov     [rbp+string], 0
0x18009a9aa  lea     rdx, [rbp+string]
0x18009a9ae  mov     rcx, rdi
0x18009a9b1  mov     rax, rbx
0x18009a9b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a9b9  mov     ebx, eax
0x18009a9bb  test    eax, eax
0x18009a9bd  jns     short loc_18009A9C9
0x18009a9bf  mov     edx, 172h
0x18009a9c4  jmp     loc_18009AB31
0x18009a9c9  xor     edx, edx; length
0x18009a9cb  mov     rcx, [rbp+string]; string
0x18009a9cf  call    cs:__imp_WindowsGetStringRawBuffer
0x18009a9d5  lea     r8, [rsi+8]
0x18009a9d9  or      edx, 0FFFFFFFFh
0x18009a9dc  mov     rcx, rax
0x18009a9df  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18009a9e5  mov     ebx, eax
0x18009a9e7  test    eax, eax
0x18009a9e9  jns     short loc_18009A9F5
0x18009a9eb  mov     edx, 176h
0x18009a9f0  jmp     loc_18009AB31
0x18009a9f5  mov     rcx, [rbp+string]; string
0x18009a9f9  call    cs:__imp_WindowsDeleteString
0x18009a9ff  mov     [rbp+string], 0
0x18009aa07  mov     rax, [rdi]
0x18009aa0a  mov     rbx, [rax+60h]
0x18009aa0e  xor     ecx, ecx; string
0x18009aa10  call    cs:__imp_WindowsDeleteString
0x18009aa16  mov     [rbp+string], 0
0x18009aa1e  lea     rdx, [rbp+string]
0x18009aa22  mov     rcx, rdi
0x18009aa25  mov     rax, rbx
0x18009aa28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009aa2d  mov     ebx, eax
0x18009aa2f  test    eax, eax
0x18009aa31  jns     short loc_18009AA3D
0x18009aa33  mov     edx, 179h
0x18009aa38  jmp     loc_18009AB31
0x18009aa3d  xor     edx, edx; length
0x18009aa3f  mov     rcx, [rbp+string]; string
0x18009aa43  call    cs:__imp_WindowsGetStringRawBuffer
0x18009aa49  lea     r8, [rsi+10h]
0x18009aa4d  or      edx, 0FFFFFFFFh
0x18009aa50  mov     rcx, rax
0x18009aa53  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18009aa59  mov     ebx, eax
0x18009aa5b  test    eax, eax
0x18009aa5d  jns     short loc_18009AA69
0x18009aa5f  mov     edx, 17Dh
0x18009aa64  jmp     loc_18009AB31
0x18009aa69  mov     rcx, [rbp+string]; string
0x18009aa6d  call    cs:__imp_WindowsDeleteString
0x18009aa73  mov     [rbp+string], 0
0x18009aa7b  mov     rax, [rdi]
0x18009aa7e  mov     rbx, [rax+78h]
0x18009aa82  xor     ecx, ecx; string
0x18009aa84  call    cs:__imp_WindowsDeleteString
0x18009aa8a  mov     [rbp+string], 0
0x18009aa92  lea     rdx, [rbp+string]
0x18009aa96  mov     rcx, rdi
0x18009aa99  mov     rax, rbx
0x18009aa9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009aaa1  mov     ebx, eax
0x18009aaa3  test    eax, eax
0x18009aaa5  jns     short loc_18009AAB1
0x18009aaa7  mov     edx, 180h
0x18009aaac  jmp     loc_18009AB31
0x18009aab1  xor     edx, edx; length
0x18009aab3  mov     rcx, [rbp+string]; string
0x18009aab7  call    cs:__imp_WindowsGetStringRawBuffer
0x18009aabd  lea     r8, [rsi+38h]
0x18009aac1  or      edx, 0FFFFFFFFh
0x18009aac4  mov     rcx, rax
0x18009aac7  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18009aacd  mov     ebx, eax
0x18009aacf  test    eax, eax
0x18009aad1  jns     short loc_18009AADA
0x18009aad3  mov     edx, 184h
0x18009aad8  jmp     short loc_18009AB31
0x18009aada  mov     [rbp+arg_0], 0
0x18009aae1  mov     rax, [rdi]
0x18009aae4  lea     rdx, [rbp+arg_0]
0x18009aae8  mov     rcx, rdi
0x18009aaeb  mov     rax, [rax+50h]
0x18009aaef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009aaf4  mov     ebx, eax
0x18009aaf6  test    eax, eax
0x18009aaf8  jns     short loc_18009AB01
0x18009aafa  mov     edx, 187h
0x18009aaff  jmp     short loc_18009AB31
0x18009ab01  mov     ecx, [rbp+arg_0]
0x18009ab04  call    ?GetOmaDmMarkFromMdmAlertMark@@YA?AW4OMADM_MARK@@W4MdmAlertMark@Management@Windows@@@Z; GetOmaDmMarkFromMdmAlertMark(Windows::Management::MdmAlertMark)
0x18009ab09  mov     [rsi+24h], eax
0x18009ab0c  mov     [rbp+arg_8], 0
0x18009ab13  mov     rax, [rdi]
0x18009ab16  lea     rdx, [rbp+arg_8]
0x18009ab1a  mov     rcx, rdi
0x18009ab1d  mov     rax, [rax+40h]
0x18009ab21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ab26  mov     ebx, eax
0x18009ab28  test    eax, eax
0x18009ab2a  jns     short loc_18009AB64
0x18009ab2c  mov     edx, 18Bh; void *
0x18009ab31  mov     r9d, eax; char *
0x18009ab34  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\enterprisemgmt\\winr"...
0x18009ab3b  mov     rcx, [rbp+18h]; this
0x18009ab3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009ab44  nop
0x18009ab45  mov     rcx, [rbp+string]; string
0x18009ab49  call    cs:__imp_WindowsDeleteString
0x18009ab4f  mov     [rbp+string], 0
0x18009ab57  mov     rcx, rsi
0x18009ab5a  call    cs:__imp_OmaDmFreeAlertInfo
0x18009ab60  mov     eax, ebx
0x18009ab62  jmp     short loc_18009AB7C
0x18009ab64  mov     ecx, [rbp+arg_8]
0x18009ab67  call    ?GetCfgDataTypeFromMdmAlertDataType@@YA?AW4ConfigDataType@@W4MdmAlertDataType@Management@Windows@@@Z; GetCfgDataTypeFromMdmAlertDataType(Windows::Management::MdmAlertDataType)
0x18009ab6c  mov     [rsi+20h], eax
0x18009ab6f  mov     rcx, [rbp+string]; string
0x18009ab73  call    cs:__imp_WindowsDeleteString
0x18009ab79  nop
0x18009ab7a  xor     eax, eax
0x18009ab7c  mov     rbx, [rsp+30h+arg_18]
0x18009ab81  add     rsp, 30h
0x18009ab85  pop     rdi
0x18009ab86  pop     rsi
0x18009ab87  pop     rbp
0x18009ab88  retn
```
