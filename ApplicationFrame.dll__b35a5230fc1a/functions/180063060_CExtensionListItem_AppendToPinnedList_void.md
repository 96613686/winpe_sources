# CExtensionListItem::AppendToPinnedList(void)

- ea: `0x180063060`
- end: `0x1800630ca`
- name: `?AppendToPinnedList@CExtensionListItem@@UEAAJXZ`
- size: `106`
- prototype: `__int64 __fastcall(CExtensionListItem *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180062b64`
- `0x180063060`
- `0x180067400`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180063078`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180063078`

## string_xrefs

- `0x18006306d`: `__EXTENSION_POINTS_STATE_MUTEX__`

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
  CExtensionStateLock::~CExtensionStateLock((CExtensionStateLock *)&MutexW);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180063060  mov     [rsp+arg_0], rbx
0x180063065  push    rdi
0x180063066  sub     rsp, 20h
0x18006306a  mov     rdi, rcx
0x18006306d  lea     r8, Name; "__EXTENSION_POINTS_STATE_MUTEX__"
0x180063074  xor     ecx, ecx; lpMutexAttributes
0x180063076  xor     edx, edx; bInitialOwner
0x180063078  call    cs:__imp_CreateMutexW
0x18006307e  lea     rcx, [rsp+28h+arg_8]; this
0x180063083  mov     [rsp+28h+arg_8], rax
0x180063088  call    ?TryLock@CExtensionStateLock@@QEAAJXZ; CExtensionStateLock::TryLock(void)
0x18006308d  mov     ebx, eax
0x18006308f  test    eax, eax
0x180063091  js      short loc_1800630B3
0x180063093  mov     rcx, [rdi+28h]
0x180063097  lea     r8, [rdi+38h]
0x18006309b  mov     byte ptr [rdi+248h], 1
0x1800630a2  mov     rdx, rdi
0x1800630a5  mov     rax, [rcx]
0x1800630a8  mov     rax, [rax+28h]
0x1800630ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800630b1  mov     ebx, eax
0x1800630b3  lea     rcx, [rsp+28h+arg_8]; this
0x1800630b8  call    ??1CExtensionStateLock@@QEAA@XZ; CExtensionStateLock::~CExtensionStateLock(void)
0x1800630bd  mov     eax, ebx
0x1800630bf  mov     rbx, [rsp+28h+arg_0]
0x1800630c4  add     rsp, 20h
0x1800630c8  pop     rdi
0x1800630c9  retn
```
