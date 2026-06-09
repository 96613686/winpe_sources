# CExtensionListItem::SetHiddenState(int)

- ea: `0x1800670c0`
- end: `0x180067139`
- name: `?SetHiddenState@CExtensionListItem@@UEAAJH@Z`
- size: `121`
- prototype: `__int64 __fastcall(CExtensionListItem *__hidden this, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180062b64`
- `0x1800670c0`
- `0x180067400`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800670df`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800670df`

## string_xrefs

- `0x1800670d1`: `__EXTENSION_POINTS_STATE_MUTEX__`

## pseudocode

```c
__int64 __fastcall CExtensionListItem::SetHiddenState(CExtensionListItem *this, unsigned int a2)
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
    v4 = (*(__int64 (__fastcall **)(__int64, CExtensionListItem *, _QWORD, char *))(*(_QWORD *)v5 + 56LL))(
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
0x1800670c0  mov     [rsp+arg_0], rbx
0x1800670c5  mov     [rsp+arg_8], rsi
0x1800670ca  push    rdi
0x1800670cb  sub     rsp, 30h
0x1800670cf  mov     esi, edx
0x1800670d1  lea     r8, Name; "__EXTENSION_POINTS_STATE_MUTEX__"
0x1800670d8  mov     rdi, rcx
0x1800670db  xor     edx, edx; bInitialOwner
0x1800670dd  xor     ecx, ecx; lpMutexAttributes
0x1800670df  call    cs:__imp_CreateMutexW
0x1800670e5  lea     rcx, [rsp+38h+arg_10]; this
0x1800670ea  mov     [rsp+38h+arg_10], rax
0x1800670ef  call    ?TryLock@CExtensionStateLock@@QEAAJXZ; CExtensionStateLock::TryLock(void)
0x1800670f4  mov     ebx, eax
0x1800670f6  test    eax, eax
0x1800670f8  js      short loc_18006711D
0x1800670fa  mov     rcx, [rdi+28h]
0x1800670fe  lea     r9, [rdi+38h]
0x180067102  mov     byte ptr [rdi+248h], 1
0x180067109  mov     r8d, esi
0x18006710c  mov     rdx, rdi
0x18006710f  mov     rax, [rcx]
0x180067112  mov     rax, [rax+38h]
0x180067116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006711b  mov     ebx, eax
0x18006711d  lea     rcx, [rsp+38h+arg_10]; this
0x180067122  call    ??1CExtensionStateLock@@QEAA@XZ; CExtensionStateLock::~CExtensionStateLock(void)
0x180067127  mov     rsi, [rsp+38h+arg_8]
0x18006712c  mov     eax, ebx
0x18006712e  mov     rbx, [rsp+38h+arg_0]
0x180067133  add     rsp, 30h
0x180067137  pop     rdi
0x180067138  retn
```
