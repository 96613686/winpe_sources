# CPersistErrorCache::AddHMODULEError(HINSTANCE__ *,long,ulong)

- ea: `0x1800158f8`
- end: `0x180015b70`
- name: `?AddHMODULEError@CPersistErrorCache@@QEAAXPEAUHINSTANCE__@@JK@Z`
- size: `632`
- prototype: `void __fastcall(CPersistErrorCache *__hidden this, HINSTANCE, int, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180021680`

## callees

- `0x18000266c`
- `0x1800153fc`
- `0x1800158f8`
- `0x18001a6c8`
- `0x18002cd54`
- `0x180030010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x180015944`
- `KERNEL32!FormatMessageW` at `0x180015944`
- `KERNEL32!LocalFree` at `0x180015b5a`
- `KERNEL32!LocalFree` at `0x180015b5a`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x180015969`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x180015969`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CPersistErrorCache::AddHMODULEError(CPersistErrorCache *this, ICreateErrorInfo *a2, DWORD a3)
{
  DWORD v5; // eax
  HRESULT v6; // eax
  int v7; // ebx
  int v8; // eax
  int v9; // ebx
  int v10; // eax
  int v11; // ebx
  int v12; // eax
  int v13; // ebx
  int v14; // eax
  int v15; // ebx
  struct IErrorInfo *v16; // [rsp+40h] [rbp-18h] BYREF
  HLOCAL hMem[2]; // [rsp+48h] [rbp-10h] BYREF
  ICreateErrorInfo *pperrinfo; // [rsp+68h] [rbp+10h] BYREF

  pperrinfo = a2;
  hMem[0] = 0;
  v5 = FormatMessageW(0x900u, CPersistSession::m_hURLMON, a3, 0x400u, (LPWSTR)hMem, 0, 0);
  try
  {
    if ( v5 )
    {
      pperrinfo = 0;
      v16 = 0;
      v6 = CreateErrorInfo(&pperrinfo);
      v7 = v6;
      if ( v6 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( off_180048AB0[0] )
            bidTraceW(off_1800481E8[0], 294912, off_180048AB0[0], (unsigned int)v6, 288);
        }
        ThrowHR(v7);
      }
      v8 = ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *))pperrinfo->lpVtbl->SetGUID)(pperrinfo, &GUID_NULL);
      v9 = v8;
      if ( v8 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180048AA8[0] )
          bidTraceW(off_1800481E8[0], 296960, off_180048AA8[0], (unsigned int)v8, 290);
        ThrowHR(v9);
      }
      v10 = ((__int64 (__fastcall *)(ICreateErrorInfo *, const wchar_t *))pperrinfo->lpVtbl->SetSource)(
              pperrinfo,
              L"Microsoft OLEDB Persistence Provider");
      v11 = v10;
      if ( v10 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180048AA0[0] )
          bidTraceW(off_1800481E8[0], 297984, off_180048AA0[0], (unsigned int)v10, 291);
        ThrowHR(v11);
      }
      v12 = ((__int64 (__fastcall *)(ICreateErrorInfo *, HLOCAL))pperrinfo->lpVtbl->SetDescription)(pperrinfo, hMem[0]);
      v13 = v12;
      if ( v12 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180048A98[0] )
          bidTraceW(off_1800481E8[0], 299008, off_180048A98[0], (unsigned int)v12, 292);
        ThrowHR(v13);
      }
      v14 = ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *, struct IErrorInfo **))pperrinfo->lpVtbl->QueryInterface)(
              pperrinfo,
              &IID_IErrorInfo,
              &v16);
      v15 = v14;
      if ( v14 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180048A90[0] )
          bidTraceW(off_1800481E8[0], 301056, off_180048A90[0], (unsigned int)v14, 294);
        ThrowHR(v15);
      }
      CPersistErrorCache::AddError(this, a3, a3, v16);
      CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v16);
      CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&pperrinfo);
    }
  }
  catch ( long )
  {
  }
  LocalFree(hMem[0]);
}

```

## disassembly

```asm
0x1800158f8  mov     rax, rsp
0x1800158fb  mov     [rax+8], rbx
0x1800158ff  mov     [rax+18h], rsi
0x180015903  mov     [rax+10h], rdx
0x180015907  push    rdi
0x180015908  sub     rsp, 50h
0x18001590c  mov     edi, r8d
0x18001590f  mov     rsi, rcx
0x180015912  mov     qword ptr [rax-10h], 0
0x18001591a  mov     qword ptr [rax-28h], 0
0x180015922  mov     dword ptr [rax-30h], 0
0x180015929  lea     rax, [rax-10h]
0x18001592d  mov     [rsp+58h+lpBuffer], rax; lpBuffer
0x180015932  mov     r9d, 400h; dwLanguageId
0x180015938  mov     rdx, cs:?m_hURLMON@CPersistSession@@0PEAUHINSTANCE__@@EA; lpSource
0x18001593f  mov     ecx, 900h; dwFlags
0x180015944  call    cs:__imp_FormatMessageW
0x18001594a  test    eax, eax
0x18001594c  jz      loc_180015B53
0x180015952  mov     [rsp+58h+pperrinfo], 0
0x18001595b  mov     [rsp+58h+var_18], 0
0x180015964  lea     rcx, [rsp+58h+pperrinfo]; pperrinfo
0x180015969  call    cs:__imp_CreateErrorInfo
0x18001596f  mov     ebx, eax
0x180015971  test    eax, eax
0x180015973  jns     short loc_1800159B4
0x180015975  test    byte ptr cs:_bidGblFlags, 2
0x18001597c  jz      short loc_1800159AD
0x18001597e  mov     rcx, cs:off_180048AB0; "<CPersistErrorCache::AddHMODULEError|AD"...
0x180015985  test    rcx, rcx
0x180015988  jz      short loc_1800159AD
0x18001598a  mov     dword ptr [rsp+58h+lpBuffer], 120h
0x180015992  mov     r9d, eax
0x180015995  mov     r8, cs:off_180048AB0; "<CPersistErrorCache::AddHMODULEError|AD"...
0x18001599c  mov     edx, 48000h
0x1800159a1  mov     rcx, cs:off_1800481E8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800159a8  call    _bidTraceW
0x1800159ad  mov     ecx, ebx; int
0x1800159af  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800159b4  mov     rcx, [rsp+58h+pperrinfo]
0x1800159b9  mov     rax, [rcx]
0x1800159bc  lea     rdx, GUID_NULL
0x1800159c3  mov     rax, [rax+18h]
0x1800159c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159cc  mov     ebx, eax
0x1800159ce  test    eax, eax
0x1800159d0  jns     short loc_180015A11
0x1800159d2  test    byte ptr cs:_bidGblFlags, 2
0x1800159d9  jz      short loc_180015A0A
0x1800159db  mov     rcx, cs:off_180048AA8; "<CPersistErrorCache::AddHMODULEError|AD"...
0x1800159e2  test    rcx, rcx
0x1800159e5  jz      short loc_180015A0A
0x1800159e7  mov     dword ptr [rsp+58h+lpBuffer], 122h
0x1800159ef  mov     r9d, eax
0x1800159f2  mov     r8, cs:off_180048AA8; "<CPersistErrorCache::AddHMODULEError|AD"...
0x1800159f9  mov     edx, 48800h
0x1800159fe  mov     rcx, cs:off_1800481E8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180015a05  call    _bidTraceW
0x180015a0a  mov     ecx, ebx; int
0x180015a0c  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180015a11  mov     rcx, [rsp+58h+pperrinfo]
0x180015a16  mov     rax, [rcx]
0x180015a19  lea     rdx, aMicrosoftOledb; "Microsoft OLEDB Persistence Provider"
0x180015a20  mov     rax, [rax+20h]
0x180015a24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a29  mov     ebx, eax
0x180015a2b  test    eax, eax
0x180015a2d  jns     short loc_180015A6E
0x180015a2f  test    byte ptr cs:_bidGblFlags, 2
0x180015a36  jz      short loc_180015A67
0x180015a38  mov     rcx, cs:off_180048AA0; "<CPersistErrorCache::AddHMODULEError|AD"...
0x180015a3f  test    rcx, rcx
0x180015a42  jz      short loc_180015A67
0x180015a44  mov     dword ptr [rsp+58h+lpBuffer], 123h
0x180015a4c  mov     r9d, eax
0x180015a4f  mov     r8, cs:off_180048AA0; "<CPersistErrorCache::AddHMODULEError|AD"...
0x180015a56  mov     edx, 48C00h
0x180015a5b  mov     rcx, cs:off_1800481E8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180015a62  call    _bidTraceW
0x180015a67  mov     ecx, ebx; int
0x180015a69  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180015a6e  mov     rcx, [rsp+58h+pperrinfo]
0x180015a73  mov     rax, [rcx]
0x180015a76  mov     rdx, [rsp+58h+hMem]
0x180015a7b  mov     rax, [rax+28h]
0x180015a7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a84  mov     ebx, eax
0x180015a86  test    eax, eax
0x180015a88  jns     short loc_180015AC9
0x180015a8a  test    byte ptr cs:_bidGblFlags, 2
0x180015a91  jz      short loc_180015AC2
0x180015a93  mov     rcx, cs:off_180048A98; "<CPersistErrorCache::AddHMODULEError|AD"...
0x180015a9a  test    rcx, rcx
0x180015a9d  jz      short loc_180015AC2
0x180015a9f  mov     dword ptr [rsp+58h+lpBuffer], 124h
0x180015aa7  mov     r9d, eax
0x180015aaa  mov     r8, cs:off_180048A98; "<CPersistErrorCache::AddHMODULEError|AD"...
0x180015ab1  mov     edx, 49000h
0x180015ab6  mov     rcx, cs:off_1800481E8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180015abd  call    _bidTraceW
0x180015ac2  mov     ecx, ebx; int
0x180015ac4  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180015ac9  mov     rcx, [rsp+58h+pperrinfo]
0x180015ace  mov     rax, [rcx]
0x180015ad1  lea     r8, [rsp+58h+var_18]
0x180015ad6  lea     rdx, IID_IErrorInfo
0x180015add  mov     rax, [rax]
0x180015ae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ae5  mov     ebx, eax
0x180015ae7  test    eax, eax
0x180015ae9  jns     short loc_180015B2A
0x180015aeb  test    byte ptr cs:_bidGblFlags, 2
0x180015af2  jz      short loc_180015B23
0x180015af4  mov     rcx, cs:off_180048A90; "<CPersistErrorCache::AddHMODULEError|AD"...
0x180015afb  test    rcx, rcx
0x180015afe  jz      short loc_180015B23
0x180015b00  mov     dword ptr [rsp+58h+lpBuffer], 126h
0x180015b08  mov     r9d, eax
0x180015b0b  mov     r8, cs:off_180048A90; "<CPersistErrorCache::AddHMODULEError|AD"...
0x180015b12  mov     edx, 49800h
0x180015b17  mov     rcx, cs:off_1800481E8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180015b1e  call    _bidTraceW
0x180015b23  mov     ecx, ebx; int
0x180015b25  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180015b2a  mov     r9, [rsp+58h+var_18]; struct IErrorInfo *
0x180015b2f  mov     r8d, edi; unsigned int
0x180015b32  mov     edx, edi; int
0x180015b34  mov     rcx, rsi; this
0x180015b37  call    ?AddError@CPersistErrorCache@@AEAAXJKPEAUIErrorInfo@@@Z; CPersistErrorCache::AddError(long,ulong,IErrorInfo *)
0x180015b3c  nop
0x180015b3d  lea     rcx, [rsp+58h+var_18]
0x180015b42  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180015b47  nop
0x180015b48  lea     rcx, [rsp+58h+pperrinfo]
0x180015b4d  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180015b52  nop
0x180015b53  jmp     short $+2
0x180015b55  mov     rcx, [rsp+58h+hMem]; hMem
0x180015b5a  call    cs:__imp_LocalFree
0x180015b60  mov     rbx, [rsp+58h+arg_0]
0x180015b65  mov     rsi, [rsp+58h+arg_10]
0x180015b6a  add     rsp, 50h
0x180015b6e  pop     rdi
0x180015b6f  retn
```
