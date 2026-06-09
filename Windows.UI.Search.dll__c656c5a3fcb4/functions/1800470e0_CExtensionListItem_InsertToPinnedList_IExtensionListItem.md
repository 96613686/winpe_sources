# CExtensionListItem::InsertToPinnedList(IExtensionListItem *)

- ea: `0x1800470e0`
- end: `0x18004715a`
- name: `?InsertToPinnedList@CExtensionListItem@@UEAAJPEAUIExtensionListItem@@@Z`
- size: `122`
- prototype: `__int64 __fastcall(CExtensionListItem *__hidden this, struct IExtensionListItem *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180043e64`
- `0x1800470e0`
- `0x180048700`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180047100`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180047100`

## string_xrefs

- `0x1800470f2`: `__EXTENSION_POINTS_STATE_MUTEX__`

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
  CExtensionStateLock::~CExtensionStateLock(&MutexW);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800470e0  mov     [rsp+arg_0], rbx
0x1800470e5  mov     [rsp+arg_8], rsi
0x1800470ea  push    rdi
0x1800470eb  sub     rsp, 30h
0x1800470ef  mov     rsi, rdx
0x1800470f2  lea     r8, Name; "__EXTENSION_POINTS_STATE_MUTEX__"
0x1800470f9  mov     rdi, rcx
0x1800470fc  xor     edx, edx; bInitialOwner
0x1800470fe  xor     ecx, ecx; lpMutexAttributes
0x180047100  call    cs:__imp_CreateMutexW
0x180047106  lea     rcx, [rsp+38h+arg_10]; this
0x18004710b  mov     [rsp+38h+arg_10], rax
0x180047110  call    ?TryLock@CExtensionStateLock@@QEAAJXZ; CExtensionStateLock::TryLock(void)
0x180047115  mov     ebx, eax
0x180047117  test    eax, eax
0x180047119  js      short loc_18004713E
0x18004711b  mov     rcx, [rdi+28h]
0x18004711f  lea     r9, [rdi+38h]
0x180047123  mov     byte ptr [rdi+248h], 1
0x18004712a  mov     r8, rsi
0x18004712d  mov     rdx, rdi
0x180047130  mov     rax, [rcx]
0x180047133  mov     rax, [rax+20h]
0x180047137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004713c  mov     ebx, eax
0x18004713e  lea     rcx, [rsp+38h+arg_10]; this
0x180047143  call    ??1CExtensionStateLock@@QEAA@XZ; CExtensionStateLock::~CExtensionStateLock(void)
0x180047148  mov     rsi, [rsp+38h+arg_8]
0x18004714d  mov     eax, ebx
0x18004714f  mov     rbx, [rsp+38h+arg_0]
0x180047154  add     rsp, 30h
0x180047158  pop     rdi
0x180047159  retn
```
