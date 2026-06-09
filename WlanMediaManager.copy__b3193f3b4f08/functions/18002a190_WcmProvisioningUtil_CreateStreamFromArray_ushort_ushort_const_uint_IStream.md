# WcmProvisioningUtil::CreateStreamFromArray<ushort>(ushort const *,uint,IStream * *)

- ea: `0x18002a190`
- end: `0x18002a240`
- name: `??$CreateStreamFromArray@G@WcmProvisioningUtil@@YAJPEBGIPEAPEAUIStream@@@Z`
- size: `176`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002b488`

## callees

- `0x180006249`
- `0x180009794`
- `0x18001b230`
- `0x18002a190`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18002a1ae`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18002a1ae`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002a215`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002a215`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18002a1bf`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18002a1bf`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18002a1de`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18002a1de`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18002a1ef`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18002a1ef`

## string_xrefs

- `0x18002a1fe`: `onecoreuap\private\net\inc\common\utils\WcmProvisioningUtil.h`
- `0x18002a220`: `onecoreuap\private\net\inc\common\utils\WcmProvisioningUtil.h`

## pseudocode

```c
__int64 __fastcall WcmProvisioningUtil::CreateStreamFromArray<unsigned short>(void *Src, unsigned int a2, LPSTREAM *a3)
{
  SIZE_T v4; // rdi
  HGLOBAL v6; // rax
  void *v7; // rbx
  void *v8; // rax
  void *v9; // rsi
  HRESULT StreamOnHGlobal; // eax
  const char *v11; // r9
  int v13; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v4 = 2LL * a2;
  v6 = GlobalAlloc(0x42u, v4);
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
    StreamOnHGlobal = CreateStreamOnHGlobal(v7, 1, a3);
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
0x18002a190  push    rbx
0x18002a192  push    rbp
0x18002a193  push    rsi
0x18002a194  push    rdi
0x18002a195  push    r14; int
0x18002a197  sub     rsp, 20h
0x18002a19b  mov     edi, edx
0x18002a19d  mov     r14, rcx
0x18002a1a0  add     rdi, rdi
0x18002a1a3  mov     ecx, 42h ; 'B'; uFlags
0x18002a1a8  mov     rdx, rdi; dwBytes
0x18002a1ab  mov     rbp, r8
0x18002a1ae  call    cs:__imp_GlobalAlloc
0x18002a1b4  mov     rbx, rax
0x18002a1b7  test    rax, rax
0x18002a1ba  jz      short loc_18002A233
0x18002a1bc  mov     rcx, rax; hMem
0x18002a1bf  call    cs:__imp_GlobalLock
0x18002a1c5  mov     rsi, rax
0x18002a1c8  test    rax, rax
0x18002a1cb  jz      short loc_18002A212
0x18002a1cd  mov     r8, rdi; Size
0x18002a1d0  mov     rdx, r14; Src
0x18002a1d3  mov     rcx, rax; void *
0x18002a1d6  call    memcpy_0
0x18002a1db  mov     rcx, rsi; hMem
0x18002a1de  call    cs:__imp_GlobalUnlock
0x18002a1e4  mov     r8, rbp; ppstm
0x18002a1e7  mov     edx, 1; fDeleteOnRelease
0x18002a1ec  mov     rcx, rbx; hGlobal
0x18002a1ef  call    cs:__imp_CreateStreamOnHGlobal
0x18002a1f5  test    eax, eax
0x18002a1f7  jns     short loc_18002A233
0x18002a1f9  mov     rcx, [rsp+48h]; this
0x18002a1fe  lea     r8, aOnecoreuapPriv_0; "onecoreuap\\private\\net\\inc\\common\\"...
0x18002a205  mov     r9d, eax; char *
0x18002a208  mov     edx, 22h ; '"'; void *
0x18002a20d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002a212  mov     rcx, rbx; hMem
0x18002a215  call    cs:__imp_GlobalFree
0x18002a21b  mov     rcx, [rsp+48h]; this
0x18002a220  lea     r8, aOnecoreuapPriv_0; "onecoreuap\\private\\net\\inc\\common\\"...
0x18002a227  mov     edx, 26h ; '&'; void *
0x18002a22c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002a231  jmp     short loc_18002A235
0x18002a233  xor     eax, eax
0x18002a235  add     rsp, 20h
0x18002a239  pop     r14
0x18002a23b  pop     rdi
0x18002a23c  pop     rsi
0x18002a23d  pop     rbp
0x18002a23e  pop     rbx
0x18002a23f  retn
```
