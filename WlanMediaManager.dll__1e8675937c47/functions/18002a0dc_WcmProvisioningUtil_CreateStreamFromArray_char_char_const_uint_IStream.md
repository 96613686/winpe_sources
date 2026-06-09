# WcmProvisioningUtil::CreateStreamFromArray<char>(char const *,uint,IStream * *)

- ea: `0x18002a0dc`
- end: `0x18002a188`
- name: `??$CreateStreamFromArray@D@WcmProvisioningUtil@@YAJPEBDIPEAPEAUIStream@@@Z`
- size: `172`
- prototype: `__int64 __fastcall(void *Src, size_t Size, LPSTREAM *ppstm)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002b488`

## callees

- `0x180006249`
- `0x180009794`
- `0x18001b230`
- `0x18002a0dc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18002a0f6`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18002a0f6`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002a15d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002a15d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18002a107`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18002a107`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18002a126`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18002a126`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18002a137`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18002a137`

## string_xrefs

- `0x18002a146`: `onecoreuap\private\net\inc\common\utils\WcmProvisioningUtil.h`
- `0x18002a168`: `onecoreuap\private\net\inc\common\utils\WcmProvisioningUtil.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WcmProvisioningUtil::CreateStreamFromArray<char>(void *Src, size_t Size, LPSTREAM *ppstm)
{
  unsigned int v4; // esi
  HGLOBAL v6; // rax
  void *v7; // rbx
  void *v8; // rax
  void *v9; // rdi
  HRESULT StreamOnHGlobal; // eax
  const char *v11; // r9
  int v13; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v4 = Size;
  v6 = GlobalAlloc(0x42u, (unsigned int)Size);
  v7 = v6;
  if ( v6 )
  {
    v8 = GlobalLock(v6);
    v9 = v8;
    if ( !v8 )
    {
LABEL_5:
      GlobalFree(v7);
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x26,
               (unsigned int)"onecoreuap\\private\\net\\inc\\common\\utils\\WcmProvisioningUtil.h",
               v11);
    }
    memcpy_0(v8, Src, v4);
    GlobalUnlock(v9);
    StreamOnHGlobal = CreateStreamOnHGlobal(v7, 1, ppstm);
    if ( StreamOnHGlobal < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x22,
        (unsigned int)"onecoreuap\\private\\net\\inc\\common\\utils\\WcmProvisioningUtil.h",
        (const char *)(unsigned int)StreamOnHGlobal,
        v13);
      goto LABEL_5;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18002a0dc  push    rbx
0x18002a0de  push    rbp
0x18002a0df  push    rsi
0x18002a0e0  push    rdi
0x18002a0e1  push    r14; int
0x18002a0e3  sub     rsp, 20h
0x18002a0e7  mov     r14, rcx
0x18002a0ea  mov     esi, edx
0x18002a0ec  mov     edx, edx; dwBytes
0x18002a0ee  mov     ecx, 42h ; 'B'; uFlags
0x18002a0f3  mov     rbp, r8
0x18002a0f6  call    cs:__imp_GlobalAlloc
0x18002a0fc  mov     rbx, rax
0x18002a0ff  test    rax, rax
0x18002a102  jz      short loc_18002A17B
0x18002a104  mov     rcx, rax; hMem
0x18002a107  call    cs:__imp_GlobalLock
0x18002a10d  mov     rdi, rax
0x18002a110  test    rax, rax
0x18002a113  jz      short loc_18002A15A
0x18002a115  mov     r8d, esi; Size
0x18002a118  mov     rdx, r14; Src
0x18002a11b  mov     rcx, rax; void *
0x18002a11e  call    memcpy_0
0x18002a123  mov     rcx, rdi; hMem
0x18002a126  call    cs:__imp_GlobalUnlock
0x18002a12c  mov     r8, rbp; ppstm
0x18002a12f  mov     edx, 1; fDeleteOnRelease
0x18002a134  mov     rcx, rbx; hGlobal
0x18002a137  call    cs:__imp_CreateStreamOnHGlobal
0x18002a13d  test    eax, eax
0x18002a13f  jns     short loc_18002A17B
0x18002a141  mov     rcx, [rsp+48h]; this
0x18002a146  lea     r8, aOnecoreuapPriv_0; "onecoreuap\\private\\net\\inc\\common\\"...
0x18002a14d  mov     r9d, eax; char *
0x18002a150  mov     edx, 22h ; '"'; void *
0x18002a155  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002a15a  mov     rcx, rbx; hMem
0x18002a15d  call    cs:__imp_GlobalFree
0x18002a163  mov     rcx, [rsp+48h]; this
0x18002a168  lea     r8, aOnecoreuapPriv_0; "onecoreuap\\private\\net\\inc\\common\\"...
0x18002a16f  mov     edx, 26h ; '&'; void *
0x18002a174  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002a179  jmp     short loc_18002A17D
0x18002a17b  xor     eax, eax
0x18002a17d  add     rsp, 20h
0x18002a181  pop     r14
0x18002a183  pop     rdi
0x18002a184  pop     rsi
0x18002a185  pop     rbp
0x18002a186  pop     rbx
0x18002a187  retn
```
