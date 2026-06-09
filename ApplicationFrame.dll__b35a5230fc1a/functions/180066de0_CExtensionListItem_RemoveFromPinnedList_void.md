# CExtensionListItem::RemoveFromPinnedList(void)

- ea: `0x180066de0`
- end: `0x180066e4a`
- name: `?RemoveFromPinnedList@CExtensionListItem@@UEAAJXZ`
- size: `106`
- prototype: `__int64 __fastcall(CExtensionListItem *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180062b64`
- `0x180066de0`
- `0x180067400`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180066df8`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180066df8`

## string_xrefs

- `0x180066ded`: `__EXTENSION_POINTS_STATE_MUTEX__`

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
  CExtensionStateLock::~CExtensionStateLock((CExtensionStateLock *)&MutexW);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180066de0  mov     [rsp+arg_0], rbx
0x180066de5  push    rdi
0x180066de6  sub     rsp, 20h
0x180066dea  mov     rdi, rcx
0x180066ded  lea     r8, Name; "__EXTENSION_POINTS_STATE_MUTEX__"
0x180066df4  xor     ecx, ecx; lpMutexAttributes
0x180066df6  xor     edx, edx; bInitialOwner
0x180066df8  call    cs:__imp_CreateMutexW
0x180066dfe  lea     rcx, [rsp+28h+arg_8]; this
0x180066e03  mov     [rsp+28h+arg_8], rax
0x180066e08  call    ?TryLock@CExtensionStateLock@@QEAAJXZ; CExtensionStateLock::TryLock(void)
0x180066e0d  mov     ebx, eax
0x180066e0f  test    eax, eax
0x180066e11  js      short loc_180066E33
0x180066e13  mov     rcx, [rdi+28h]
0x180066e17  lea     r8, [rdi+38h]
0x180066e1b  mov     byte ptr [rdi+248h], 1
0x180066e22  mov     rdx, rdi
0x180066e25  mov     rax, [rcx]
0x180066e28  mov     rax, [rax+30h]
0x180066e2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066e31  mov     ebx, eax
0x180066e33  lea     rcx, [rsp+28h+arg_8]; this
0x180066e38  call    ??1CExtensionStateLock@@QEAA@XZ; CExtensionStateLock::~CExtensionStateLock(void)
0x180066e3d  mov     eax, ebx
0x180066e3f  mov     rbx, [rsp+28h+arg_0]
0x180066e44  add     rsp, 20h
0x180066e48  pop     rdi
0x180066e49  retn
```
