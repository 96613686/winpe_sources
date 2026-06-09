# LogSqmOpenData

- ea: `0x18006b1d8`
- end: `0x18006b2d4`
- name: `LogSqmOpenData`
- size: `252`
- prototype: `__int64 __fastcall(LPCWSTR pszPath, IDataObject *pdo)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006b2dc`

## callees

- `0x1800034fc`
- `0x1800036e4`
- `0x18000cb74`
- `0x180033690`
- `0x18006b1d8`
- `0x180080010`

## import_xrefs

- `SHELL32!SHCreateShellItemArrayFromDataObject` at `0x18006b206`
- `SHELL32!SHCreateShellItemArrayFromDataObject` at `0x18006b206`
- `SHLWAPI!PathFindFileNameW` at `0x18006b244`
- `SHLWAPI!PathFindFileNameW` at `0x18006b244`
- `PhotoBase!?AddToStream@Sqm@@YAXKPEBU_SQM_STREAM_ENTRY@@_K@Z` at `0x18006b2b0`
- `PhotoBase!?AddToStream@Sqm@@YAXKPEBU_SQM_STREAM_ENTRY@@_K@Z` at `0x18006b2b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall LogSqmOpenData(LPCWSTR pszPath, IDataObject *pdo)
{
  unsigned int v3; // ebx
  LPWSTR FileNameW; // rax
  unsigned __int64 v5; // r9
  unsigned int v6; // edx
  _DWORD v7[2]; // [rsp+20h] [rbp-48h] BYREF
  LPWSTR v8; // [rsp+28h] [rbp-40h]
  _BYTE v9[16]; // [rsp+30h] [rbp-38h] BYREF
  __int128 v10; // [rsp+40h] [rbp-28h] BYREF
  __int64 v11; // [rsp+50h] [rbp-18h]
  int v12; // [rsp+58h] [rbp-10h]
  unsigned int v13; // [rsp+80h] [rbp+18h] BYREF
  void *v14; // [rsp+88h] [rbp+20h] BYREF

  v13 = 0;
  v14 = 0;
  if ( SHCreateShellItemArrayFromDataObject(pdo, &GUID_b63ea76d_1f85_456f_a19c_48159efa858b, &v14) >= 0 )
    (*(void (__fastcall **)(void *, unsigned int *))(*(_QWORD *)v14 + 56LL))(v14, &v13);
  v3 = v13;
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v14);
  FileNameW = PathFindFileNameW(pszPath);
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v7[1] = 0;
  if ( !FileNameW || !*FileNameW )
    FileNameW = L"(null)";
  v8 = FileNameW;
  v7[0] = 2;
  try
  {
    ATL::CAtlArray<_SQM_STREAM_ENTRY,ATL::CElementTraits<_SQM_STREAM_ENTRY>>::Add(&v10, v7);
    SqmTuple::Add((SqmTuple *)&v10, v3);
    v6 = 0;
    if ( *((_QWORD *)&v10 + 1) )
      v6 = v10;
    Sqm::AddToStream((Sqm *)0x77B, v6, *((const struct _SQM_STREAM_ENTRY **)&v10 + 1), v5);
    ATL::CAtlArray<_TASKDIALOG_BUTTON,ATL::CElementTraits<_TASKDIALOG_BUTTON>>::~CAtlArray<_TASKDIALOG_BUTTON,ATL::CElementTraits<_TASKDIALOG_BUTTON>>(&v10);
  }
  catch ( Base::Exception v9 )
  {
    Base::Exception::~Exception((Base::Exception *)v9);
  }
}

```

## disassembly

```asm
0x18006b1d8  mov     r11, rsp
0x18006b1db  mov     [r11+8], rbx
0x18006b1df  mov     [r11+10h], rsi
0x18006b1e3  push    rdi
0x18006b1e4  sub     rsp, 60h
0x18006b1e8  mov     rax, rdx
0x18006b1eb  mov     rdi, rcx
0x18006b1ee  xor     esi, esi
0x18006b1f0  mov     [r11+18h], esi
0x18006b1f4  mov     [r11+20h], rsi
0x18006b1f8  lea     r8, [r11+20h]; ppv
0x18006b1fc  lea     rdx, _GUID_b63ea76d_1f85_456f_a19c_48159efa858b; riid
0x18006b203  mov     rcx, rax; pdo
0x18006b206  call    cs:__imp_SHCreateShellItemArrayFromDataObject
0x18006b20c  test    eax, eax
0x18006b20e  js      short loc_18006B22C
0x18006b210  mov     rcx, [rsp+68h+arg_18]
0x18006b218  mov     rax, [rcx]
0x18006b21b  lea     rdx, [rsp+68h+arg_10]
0x18006b223  mov     rax, [rax+38h]
0x18006b227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b22c  mov     ebx, [rsp+68h+arg_10]
0x18006b233  lea     rcx, [rsp+68h+arg_18]
0x18006b23b  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18006b240  nop
0x18006b241  mov     rcx, rdi; pszPath
0x18006b244  call    cs:__imp_PathFindFileNameW
0x18006b24a  nop
0x18006b24b  xorps   xmm0, xmm0
0x18006b24e  movdqu  [rsp+68h+var_28], xmm0
0x18006b254  mov     [rsp+68h+var_18], rsi
0x18006b259  mov     [rsp+68h+var_10], esi
0x18006b25d  mov     [rsp+68h+var_44], esi
0x18006b261  test    rax, rax
0x18006b264  jz      short loc_18006B26B
0x18006b266  cmp     [rax], si
0x18006b269  jnz     short loc_18006B272
0x18006b26b  lea     rax, aNull; "(null)"
0x18006b272  mov     [rsp+68h+var_40], rax
0x18006b277  mov     [rsp+68h+var_48], 2
0x18006b27f  lea     rdx, [rsp+68h+var_48]
0x18006b284  lea     rcx, [rsp+68h+var_28]
0x18006b289  call    ?Add@?$CAtlArray@U_SQM_STREAM_ENTRY@@V?$CElementTraits@U_SQM_STREAM_ENTRY@@@ATL@@@ATL@@QEAA_KAEBU_SQM_STREAM_ENTRY@@@Z; ATL::CAtlArray<_SQM_STREAM_ENTRY,ATL::CElementTraits<_SQM_STREAM_ENTRY>>::Add(_SQM_STREAM_ENTRY const &)
0x18006b28e  mov     edx, ebx; unsigned int
0x18006b290  lea     rcx, [rsp+68h+var_28]; this
0x18006b295  call    ?Add@SqmTuple@@QEAAXK@Z; SqmTuple::Add(ulong)
0x18006b29a  mov     r8, qword ptr [rsp+68h+var_28+8]
0x18006b29f  mov     rdx, rsi
0x18006b2a2  test    r8, r8
0x18006b2a5  cmovnz  rdx, qword ptr [rsp+68h+var_28]
0x18006b2ab  mov     ecx, 77Bh
0x18006b2b0  call    cs:__imp_?AddToStream@Sqm@@YAXKPEBU_SQM_STREAM_ENTRY@@_K@Z; Sqm::AddToStream(ulong,_SQM_STREAM_ENTRY const *,unsigned __int64)
0x18006b2b6  nop
0x18006b2b7  lea     rcx, [rsp+68h+var_28]; void *
0x18006b2bc  call    ??1?$CAtlArray@U_TASKDIALOG_BUTTON@@V?$CElementTraits@U_TASKDIALOG_BUTTON@@@ATL@@@ATL@@QEAA@XZ; ATL::CAtlArray<_TASKDIALOG_BUTTON,ATL::CElementTraits<_TASKDIALOG_BUTTON>>::~CAtlArray<_TASKDIALOG_BUTTON,ATL::CElementTraits<_TASKDIALOG_BUTTON>>(void)
0x18006b2c1  nop
0x18006b2c2  jmp     short $+2
0x18006b2c4  mov     rbx, [rsp+68h+arg_0]
0x18006b2c9  mov     rsi, [rsp+68h+arg_8]
0x18006b2ce  add     rsp, 60h
0x18006b2d2  pop     rdi
0x18006b2d3  retn
```
