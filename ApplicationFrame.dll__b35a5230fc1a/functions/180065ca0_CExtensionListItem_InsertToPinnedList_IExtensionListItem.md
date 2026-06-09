# CExtensionListItem::InsertToPinnedList(IExtensionListItem *)

- ea: `0x180065ca0`
- end: `0x180065d1a`
- name: `?InsertToPinnedList@CExtensionListItem@@UEAAJPEAUIExtensionListItem@@@Z`
- size: `122`
- prototype: `__int64 __fastcall(CExtensionListItem *__hidden this, struct IExtensionListItem *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180062b64`
- `0x180065ca0`
- `0x180067400`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180065cc0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180065cc0`

## string_xrefs

- `0x180065cb2`: `__EXTENSION_POINTS_STATE_MUTEX__`

## pseudocode

```c
__int64 __fastcall CExtensionListItem::InsertToPinnedList(CExtensionListItem *this, struct IExtensionListItem *a2)
{
  int v4; // ebx
  __int64 v5; // rcx
  HANDLE MutexW; // [rsp+50h] [rbp+18h] BYREF

  MutexW = CreateMutexW(0, 0, L"__EXTENSION_POINTS_STATE_MUTEX__");
  v4 = CExtensionStateLock::TryLock((CExtensionStateLock *)&MutexW);
  if ( v4 >= 0 )
  {
    v5 = *((_QWORD *)this + 5);
    *((_BYTE *)this + 584) = 1;
    v4 = (*(__int64 (__fastcall **)(__int64, CExtensionListItem *, struct IExtensionListItem *, char *))(*(_QWORD *)v5 + 32LL))(
           v5,
           this,
           a2,
           (char *)this + 56);
  }
  CExtensionStateLock::~CExtensionStateLock((CExtensionStateLock *)&MutexW);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180065ca0  mov     [rsp+arg_0], rbx
0x180065ca5  mov     [rsp+arg_8], rsi
0x180065caa  push    rdi
0x180065cab  sub     rsp, 30h
0x180065caf  mov     rsi, rdx
0x180065cb2  lea     r8, Name; "__EXTENSION_POINTS_STATE_MUTEX__"
0x180065cb9  mov     rdi, rcx
0x180065cbc  xor     edx, edx; bInitialOwner
0x180065cbe  xor     ecx, ecx; lpMutexAttributes
0x180065cc0  call    cs:__imp_CreateMutexW
0x180065cc6  lea     rcx, [rsp+38h+arg_10]; this
0x180065ccb  mov     [rsp+38h+arg_10], rax
0x180065cd0  call    ?TryLock@CExtensionStateLock@@QEAAJXZ; CExtensionStateLock::TryLock(void)
0x180065cd5  mov     ebx, eax
0x180065cd7  test    eax, eax
0x180065cd9  js      short loc_180065CFE
0x180065cdb  mov     rcx, [rdi+28h]
0x180065cdf  lea     r9, [rdi+38h]
0x180065ce3  mov     byte ptr [rdi+248h], 1
0x180065cea  mov     r8, rsi
0x180065ced  mov     rdx, rdi
0x180065cf0  mov     rax, [rcx]
0x180065cf3  mov     rax, [rax+20h]
0x180065cf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065cfc  mov     ebx, eax
0x180065cfe  lea     rcx, [rsp+38h+arg_10]; this
0x180065d03  call    ??1CExtensionStateLock@@QEAA@XZ; CExtensionStateLock::~CExtensionStateLock(void)
0x180065d08  mov     rsi, [rsp+38h+arg_8]
0x180065d0d  mov     eax, ebx
0x180065d0f  mov     rbx, [rsp+38h+arg_0]
0x180065d14  add     rsp, 30h
0x180065d18  pop     rdi
0x180065d19  retn
```
