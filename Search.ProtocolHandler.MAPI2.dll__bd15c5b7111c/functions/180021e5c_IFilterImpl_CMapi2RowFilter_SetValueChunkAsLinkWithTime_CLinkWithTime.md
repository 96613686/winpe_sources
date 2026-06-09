# IFilterImpl<CMapi2RowFilter>::SetValueChunkAsLinkWithTime(CLinkWithTime *)

- ea: `0x180021e5c`
- end: `0x180021f8e`
- name: `?SetValueChunkAsLinkWithTime@?$IFilterImpl@VCMapi2RowFilter@@@@IEAAXPEAVCLinkWithTime@@@Z`
- size: `306`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001f140`
- `0x180023ba0`

## callees

- `0x180017870`
- `0x180021e5c`
- `0x180021f94`
- `0x1800227a0`
- `0x18003a0e4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021e73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021ea2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021eea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021e73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021ea2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021eea`

## string_xrefs

- `0x180021e8b`: `onecoreuap\base\appmodel\Search\common\include\prothndlrhelp.hxx`
- `0x180021eb7`: `onecoreuap\base\appmodel\Search\common\include\prothndlrhelp.hxx`
- `0x180021f02`: `onecoreuap\base\appmodel\Search\common\include\prothndlrhelp.hxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall IFilterImpl<CMapi2RowFilter>::SetValueChunkAsLinkWithTime(__int64 a1, __int64 a2)
{
  _DWORD *v4; // rbx
  const char *v5; // r9
  LPVOID v6; // rax
  const char *v7; // r9
  _WORD *v8; // rax
  const char *v9; // r9
  _WORD *v10; // rdi
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  LPVOID v13; // [rsp+60h] [rbp+18h] BYREF
  _DWORD *v14; // [rsp+68h] [rbp+20h] BYREF

  v4 = CoTaskMemAlloc(0x18u);
  v14 = v4;
  if ( !v4 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x191,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\prothndlrhelp.hxx",
      v5);
  v6 = CoTaskMemAlloc(0x30u);
  v13 = v6;
  if ( !v6 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x194,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\prothndlrhelp.hxx",
      v7);
  *(_WORD *)v4 = 4108;
  v4[2] = 2;
  v13 = 0;
  *((_QWORD *)v4 + 2) = v6;
  v8 = CoTaskMemAlloc(2LL * (unsigned int)(*(_DWORD *)(a2 + 20) + 1));
  v10 = v8;
  if ( !v8 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x19B,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\prothndlrhelp.hxx",
      v9);
  memcpy_0(v8, *(const void **)(a2 + 8), 2LL * *(unsigned int *)(a2 + 20));
  v10[*(unsigned int *)(a2 + 20)] = 0;
  **((_WORD **)v4 + 2) = 31;
  *(_QWORD *)(*((_QWORD *)v4 + 2) + 8LL) = v10;
  *(_WORD *)(*((_QWORD *)v4 + 2) + 24LL) = 64;
  *(_QWORD *)(*((_QWORD *)v4 + 2) + 32LL) = *(_QWORD *)(a2 + 416);
  IFilterImpl<CMapi2DirFilter>::SetValueChunkAsPropvariantAndTakeMemoryOwnership(a1, &v14);
  wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(&v13, 0);
  return wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
           &v14,
           0);
}

```

## disassembly

```asm
0x180021e5c  mov     [rsp+arg_0], rbx
0x180021e61  push    rbp
0x180021e62  push    rsi
0x180021e63  push    rdi
0x180021e64  sub     rsp, 30h
0x180021e68  mov     rsi, rdx
0x180021e6b  mov     rbp, rcx
0x180021e6e  mov     ecx, 18h; cb
0x180021e73  call    cs:__imp_CoTaskMemAlloc
0x180021e79  mov     rbx, rax
0x180021e7c  mov     [rsp+48h+arg_18], rax
0x180021e81  mov     rcx, [rsp+48h]; this
0x180021e86  test    rax, rax
0x180021e89  jnz     short loc_180021E9D
0x180021e8b  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180021e92  mov     edx, 191h; void *
0x180021e97  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180021e9d  mov     ecx, 30h ; '0'; cb
0x180021ea2  call    cs:__imp_CoTaskMemAlloc
0x180021ea8  mov     [rsp+48h+arg_10], rax
0x180021ead  mov     rcx, [rsp+48h]; this
0x180021eb2  test    rax, rax
0x180021eb5  jnz     short loc_180021EC9
0x180021eb7  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180021ebe  mov     edx, 194h; void *
0x180021ec3  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180021ec9  mov     word ptr [rbx], 100Ch
0x180021ece  mov     dword ptr [rbx+8], 2
0x180021ed5  mov     [rsp+48h+arg_10], 0
0x180021ede  mov     [rbx+10h], rax
0x180021ee2  mov     ecx, [rsi+14h]
0x180021ee5  inc     ecx
0x180021ee7  add     rcx, rcx; cb
0x180021eea  call    cs:__imp_CoTaskMemAlloc
0x180021ef0  mov     rdi, rax
0x180021ef3  mov     [rsp+48h+var_28], rax
0x180021ef8  mov     rcx, [rsp+48h]; this
0x180021efd  test    rax, rax
0x180021f00  jnz     short loc_180021F14
0x180021f02  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180021f09  mov     edx, 19Bh; void *
0x180021f0e  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180021f14  mov     r8d, [rsi+14h]
0x180021f18  add     r8, r8; Size
0x180021f1b  mov     rdx, [rsi+8]; Src
0x180021f1f  mov     rcx, rdi; void *
0x180021f22  call    memcpy_0
0x180021f27  mov     ecx, [rsi+14h]
0x180021f2a  xor     eax, eax
0x180021f2c  mov     [rdi+rcx*2], ax
0x180021f30  mov     rax, [rbx+10h]
0x180021f34  mov     word ptr [rax], 1Fh
0x180021f39  mov     rax, [rbx+10h]
0x180021f3d  mov     [rax+8], rdi
0x180021f41  mov     rax, [rbx+10h]
0x180021f45  mov     word ptr [rax+18h], 40h ; '@'
0x180021f4b  mov     rcx, [rbx+10h]
0x180021f4f  mov     rax, [rsi+1A0h]
0x180021f56  mov     [rcx+20h], rax
0x180021f5a  lea     rdx, [rsp+48h+arg_18]
0x180021f5f  mov     rcx, rbp
0x180021f62  call    ?SetValueChunkAsPropvariantAndTakeMemoryOwnership@?$IFilterImpl@VCMapi2DirFilter@@@@IEAAXAEAV?$unique_ptr@UtagPROPVARIANT@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@Z; IFilterImpl<CMapi2DirFilter>::SetValueChunkAsPropvariantAndTakeMemoryOwnership(wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &)
0x180021f67  nop
0x180021f68  xor     edx, edx
0x180021f6a  lea     rcx, [rsp+48h+arg_10]
0x180021f6f  call    ?reset@?$unique_ptr@UtagPROPVARIANT@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUtagPROPVARIANT@@@Z; wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(tagPROPVARIANT *)
0x180021f74  nop
0x180021f75  xor     edx, edx
0x180021f77  lea     rcx, [rsp+48h+arg_18]
0x180021f7c  call    ?reset@?$unique_ptr@UtagPROPVARIANT@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUtagPROPVARIANT@@@Z; wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(tagPROPVARIANT *)
0x180021f81  mov     rbx, [rsp+48h+arg_0]
0x180021f86  add     rsp, 30h
0x180021f8a  pop     rdi
0x180021f8b  pop     rsi
0x180021f8c  pop     rbp
0x180021f8d  retn
```
