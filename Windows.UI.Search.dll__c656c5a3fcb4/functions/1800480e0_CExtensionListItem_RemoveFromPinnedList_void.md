# CExtensionListItem::RemoveFromPinnedList(void)

- ea: `0x1800480e0`
- end: `0x18004814a`
- name: `?RemoveFromPinnedList@CExtensionListItem@@UEAAJXZ`
- size: `106`
- prototype: `__int64 __fastcall(CExtensionListItem *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180043e64`
- `0x1800480e0`
- `0x180048700`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800480f8`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800480f8`

## string_xrefs

- `0x1800480ed`: `__EXTENSION_POINTS_STATE_MUTEX__`

## pseudocode

```c
__int64 __fastcall CExtensionListItem::RemoveFromPinnedList(CExtensionListItem *this)
{
  int v2; // ebx
  __int64 v3; // rcx
  HANDLE MutexW; // [rsp+38h] [rbp+10h] BYREF

  MutexW = CreateMutexW(0, 0, L"__EXTENSION_POINTS_STATE_MUTEX__");
  v2 = CExtensionStateLock::TryLock((CExtensionStateLock *)&MutexW);
  if ( v2 >= 0 )
  {
    v3 = *((_QWORD *)this + 5);
    *((_BYTE *)this + 584) = 1;
    v2 = (*(__int64 (__fastcall **)(__int64, CExtensionListItem *, char *))(*(_QWORD *)v3 + 48LL))(
           v3,
           this,
           (char *)this + 56);
  }
  CExtensionStateLock::~CExtensionStateLock(&MutexW);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800480e0  mov     [rsp+arg_0], rbx
0x1800480e5  push    rdi
0x1800480e6  sub     rsp, 20h
0x1800480ea  mov     rdi, rcx
0x1800480ed  lea     r8, Name; "__EXTENSION_POINTS_STATE_MUTEX__"
0x1800480f4  xor     ecx, ecx; lpMutexAttributes
0x1800480f6  xor     edx, edx; bInitialOwner
0x1800480f8  call    cs:__imp_CreateMutexW
0x1800480fe  lea     rcx, [rsp+28h+arg_8]; this
0x180048103  mov     [rsp+28h+arg_8], rax
0x180048108  call    ?TryLock@CExtensionStateLock@@QEAAJXZ; CExtensionStateLock::TryLock(void)
0x18004810d  mov     ebx, eax
0x18004810f  test    eax, eax
0x180048111  js      short loc_180048133
0x180048113  mov     rcx, [rdi+28h]
0x180048117  lea     r8, [rdi+38h]
0x18004811b  mov     byte ptr [rdi+248h], 1
0x180048122  mov     rdx, rdi
0x180048125  mov     rax, [rcx]
0x180048128  mov     rax, [rax+30h]
0x18004812c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048131  mov     ebx, eax
0x180048133  lea     rcx, [rsp+28h+arg_8]; this
0x180048138  call    ??1CExtensionStateLock@@QEAA@XZ; CExtensionStateLock::~CExtensionStateLock(void)
0x18004813d  mov     eax, ebx
0x18004813f  mov     rbx, [rsp+28h+arg_0]
0x180048144  add     rsp, 20h
0x180048148  pop     rdi
0x180048149  retn
```
