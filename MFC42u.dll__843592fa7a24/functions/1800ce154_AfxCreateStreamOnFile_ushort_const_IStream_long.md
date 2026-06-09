# _AfxCreateStreamOnFile(ushort const *,IStream * *,long *)

- ea: `0x1800ce154`
- end: `0x1800ce2be`
- name: `?_AfxCreateStreamOnFile@@YAJPEBGPEAPEAUIStream@@PEAJ@Z`
- size: `362`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPSTREAM *ppstm, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800cd8c0`

## callees

- `0x180009910`
- `0x180038140`
- `0x18003a5a0`
- `0x1800ce154`
- `0x1800d1fe0`
- `0x1800d7010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800ce258`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800ce258`
- `KERNEL32!GlobalFree` at `0x1800ce277`
- `KERNEL32!GlobalFree` at `0x1800ce277`
- `KERNEL32!GlobalUnlock` at `0x1800ce243`
- `KERNEL32!GlobalUnlock` at `0x1800ce243`
- `KERNEL32!GlobalAlloc` at `0x1800ce204`
- `KERNEL32!GlobalAlloc` at `0x1800ce204`
- `KERNEL32!GlobalLock` at `0x1800ce21a`
- `KERNEL32!GlobalLock` at `0x1800ce21a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall _AfxCreateStreamOnFile(const unsigned __int16 *a1, LPSTREAM *ppstm, int *a3)
{
  unsigned int v6; // ebp
  HGLOBAL v7; // rax
  void *v8; // rsi
  HRESULT StreamOnHGlobal; // edi
  LPVOID v10; // rdx
  int v11; // ebx
  _QWORD v13[2]; // [rsp+20h] [rbp-288h] BYREF
  int v14; // [rsp+30h] [rbp-278h]
  LPCWSTR v15; // [rsp+38h] [rbp-270h]
  _BYTE v16[24]; // [rsp+40h] [rbp-268h] BYREF
  int v17; // [rsp+58h] [rbp-250h]

  *ppstm = 0;
  if ( a3 )
    *a3 = 0;
  v13[0] = &CFile::`vftable';
  v15 = _afxPchNil;
  v13[1] = -1;
  v14 = 0;
  if ( (unsigned int)CFile::Open((CFile *)v13, a1, 0, 0)
    && (unsigned int)CFile::GetStatus(a1, (struct CFileStatus *)v16)
    && (v6 = v17, v17 != -1) )
  {
    v7 = GlobalAlloc(2u, v17);
    v8 = v7;
    if ( v7 )
    {
      StreamOnHGlobal = -2147467259;
      v10 = GlobalLock(v7);
      if ( v10
        && (v11 = (*(__int64 (__fastcall **)(_QWORD *, LPVOID, _QWORD))(v13[0] + 120LL))(v13, v10, v6),
            GlobalUnlock(v8),
            v11 == v6)
        && (StreamOnHGlobal = CreateStreamOnHGlobal(v8, 1, ppstm), StreamOnHGlobal >= 0) )
      {
        if ( a3 )
          *a3 = v17;
        StreamOnHGlobal = 0;
      }
      else
      {
        GlobalFree(v8);
      }
    }
    else
    {
      StreamOnHGlobal = -2147024882;
    }
  }
  else
  {
    StreamOnHGlobal = -2147024891;
  }
  CFile::~CFile((CFile *)v13);
  return (unsigned int)StreamOnHGlobal;
}

```

## disassembly

```asm
0x1800ce154  mov     [rsp+arg_18], rbx
0x1800ce159  push    rbp
0x1800ce15a  push    rsi
0x1800ce15b  push    rdi
0x1800ce15c  push    r14
0x1800ce15e  push    r15
0x1800ce160  sub     rsp, 280h
0x1800ce167  mov     rax, cs:__security_cookie
0x1800ce16e  xor     rax, rsp
0x1800ce171  mov     [rsp+2A8h+var_38], rax
0x1800ce179  mov     r14, r8
0x1800ce17c  mov     r15, rdx
0x1800ce17f  mov     rbx, rcx
0x1800ce182  mov     qword ptr [rdx], 0
0x1800ce189  test    r8, r8
0x1800ce18c  jz      short loc_1800CE195
0x1800ce18e  mov     dword ptr [r8], 0
0x1800ce195  lea     rax, ??_7CFile@@6B@; const CFile::`vftable'
0x1800ce19c  mov     [rsp+2A8h+var_288], rax
0x1800ce1a1  mov     rax, cs:?_afxPchNil@@3PEBGEB; ushort const * const _afxPchNil
0x1800ce1a8  mov     [rsp+2A8h+var_270], rax
0x1800ce1ad  mov     [rsp+2A8h+var_280], 0FFFFFFFFFFFFFFFFh
0x1800ce1b6  mov     [rsp+2A8h+var_278], 0
0x1800ce1be  xor     r9d, r9d; struct CFileException *
0x1800ce1c1  xor     r8d, r8d; unsigned int
0x1800ce1c4  mov     rdx, rbx; unsigned __int16 *
0x1800ce1c7  lea     rcx, [rsp+2A8h+var_288]; this
0x1800ce1cc  call    ?Open@CFile@@UEAAHPEBGIPEAVCFileException@@@Z; CFile::Open(ushort const *,uint,CFileException *)
0x1800ce1d1  test    eax, eax
0x1800ce1d3  jz      loc_1800CE286
0x1800ce1d9  lea     rdx, [rsp+2A8h+var_268]; struct CFileStatus *
0x1800ce1de  mov     rcx, rbx; lpFileName
0x1800ce1e1  call    ?GetStatus@CFile@@SAHPEBGAEAUCFileStatus@@@Z; CFile::GetStatus(ushort const *,CFileStatus &)
0x1800ce1e6  test    eax, eax
0x1800ce1e8  jz      loc_1800CE286
0x1800ce1ee  movsxd  rbp, [rsp+2A8h+var_250]
0x1800ce1f3  cmp     ebp, 0FFFFFFFFh
0x1800ce1f6  jz      loc_1800CE286
0x1800ce1fc  mov     rdx, rbp; dwBytes
0x1800ce1ff  mov     ecx, 2; uFlags
0x1800ce204  call    cs:__imp_GlobalAlloc
0x1800ce20a  mov     rsi, rax
0x1800ce20d  test    rax, rax
0x1800ce210  jz      short loc_1800CE27F
0x1800ce212  mov     edi, 80004005h
0x1800ce217  mov     rcx, rax; hMem
0x1800ce21a  call    cs:__imp_GlobalLock
0x1800ce220  mov     rdx, rax
0x1800ce223  test    rax, rax
0x1800ce226  jz      short loc_1800CE274
0x1800ce228  mov     rcx, [rsp+2A8h+var_288]
0x1800ce22d  mov     rax, [rcx+78h]
0x1800ce231  mov     r8d, ebp
0x1800ce234  lea     rcx, [rsp+2A8h+var_288]
0x1800ce239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce23e  mov     ebx, eax
0x1800ce240  mov     rcx, rsi; hMem
0x1800ce243  call    cs:__imp_GlobalUnlock
0x1800ce249  cmp     ebx, ebp
0x1800ce24b  jnz     short loc_1800CE274
0x1800ce24d  mov     r8, r15; ppstm
0x1800ce250  mov     edx, 1; fDeleteOnRelease
0x1800ce255  mov     rcx, rsi; hGlobal
0x1800ce258  call    cs:__imp_CreateStreamOnHGlobal
0x1800ce25e  mov     edi, eax
0x1800ce260  test    eax, eax
0x1800ce262  js      short loc_1800CE274
0x1800ce264  test    r14, r14
0x1800ce267  jz      short loc_1800CE270
0x1800ce269  mov     eax, [rsp+2A8h+var_250]
0x1800ce26d  mov     [r14], eax
0x1800ce270  xor     edi, edi
0x1800ce272  jmp     short loc_1800CE28B
0x1800ce274  mov     rcx, rsi; hMem
0x1800ce277  call    cs:__imp_GlobalFree
0x1800ce27d  jmp     short loc_1800CE28B
0x1800ce27f  mov     edi, 8007000Eh
0x1800ce284  jmp     short loc_1800CE28B
0x1800ce286  mov     edi, 80070005h
0x1800ce28b  lea     rcx, [rsp+2A8h+var_288]; this
0x1800ce290  call    ??1CFile@@UEAA@XZ; CFile::~CFile(void)
0x1800ce295  mov     eax, edi
0x1800ce297  mov     rcx, [rsp+2A8h+var_38]
0x1800ce29f  xor     rcx, rsp; StackCookie
0x1800ce2a2  call    __security_check_cookie
0x1800ce2a7  mov     rbx, [rsp+2A8h+arg_18]
0x1800ce2af  add     rsp, 280h
0x1800ce2b6  pop     r15
0x1800ce2b8  pop     r14
0x1800ce2ba  pop     rdi
0x1800ce2bb  pop     rsi
0x1800ce2bc  pop     rbp
0x1800ce2bd  retn
```
