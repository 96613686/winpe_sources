# CExtensionListItem::AppendToPinnedList(void)

- ea: `0x180044240`
- end: `0x1800442aa`
- name: `?AppendToPinnedList@CExtensionListItem@@UEAAJXZ`
- size: `106`
- prototype: `__int64 __fastcall(CExtensionListItem *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180043e64`
- `0x180044240`
- `0x180048700`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180044258`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180044258`

## string_xrefs

- `0x18004424d`: `__EXTENSION_POINTS_STATE_MUTEX__`

## pseudocode

```c
__int64 __fastcall CExtensionListItem::AppendToPinnedList(CExtensionListItem *this)
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
    v2 = (*(__int64 (__fastcall **)(__int64, CExtensionListItem *, char *))(*(_QWORD *)v3 + 40LL))(
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
0x180044240  mov     [rsp+arg_0], rbx
0x180044245  push    rdi
0x180044246  sub     rsp, 20h
0x18004424a  mov     rdi, rcx
0x18004424d  lea     r8, Name; "__EXTENSION_POINTS_STATE_MUTEX__"
0x180044254  xor     ecx, ecx; lpMutexAttributes
0x180044256  xor     edx, edx; bInitialOwner
0x180044258  call    cs:__imp_CreateMutexW
0x18004425e  lea     rcx, [rsp+28h+arg_8]; this
0x180044263  mov     [rsp+28h+arg_8], rax
0x180044268  call    ?TryLock@CExtensionStateLock@@QEAAJXZ; CExtensionStateLock::TryLock(void)
0x18004426d  mov     ebx, eax
0x18004426f  test    eax, eax
0x180044271  js      short loc_180044293
0x180044273  mov     rcx, [rdi+28h]
0x180044277  lea     r8, [rdi+38h]
0x18004427b  mov     byte ptr [rdi+248h], 1
0x180044282  mov     rdx, rdi
0x180044285  mov     rax, [rcx]
0x180044288  mov     rax, [rax+28h]
0x18004428c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044291  mov     ebx, eax
0x180044293  lea     rcx, [rsp+28h+arg_8]; this
0x180044298  call    ??1CExtensionStateLock@@QEAA@XZ; CExtensionStateLock::~CExtensionStateLock(void)
0x18004429d  mov     eax, ebx
0x18004429f  mov     rbx, [rsp+28h+arg_0]
0x1800442a4  add     rsp, 20h
0x1800442a8  pop     rdi
0x1800442a9  retn
```
