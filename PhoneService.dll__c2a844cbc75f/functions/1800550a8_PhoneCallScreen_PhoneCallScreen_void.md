# PhoneCallScreen::~PhoneCallScreen(void)

- ea: `0x1800550a8`
- end: `0x180055142`
- name: `??1PhoneCallScreen@@MEAA@XZ`
- size: `154`
- prototype: `void __fastcall(PhoneCallScreen *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180055220`
- `0x180055370`

## callees

- `0x1800550a8`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180055122`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180055136`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180055122`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180055136`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800550dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800550ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800550dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800550ee`

## pseudocode

```c
void __fastcall PhoneCallScreen::~PhoneCallScreen(PhoneCallScreen *this)
{
  __int64 v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx

  *(_QWORD *)this = &PhoneCallScreen::`vftable';
  v2 = *((_QWORD *)this + 14);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 40LL))(v2);
  v3 = (void *)*((_QWORD *)this + 20);
  if ( v3 )
    LocalFree(v3);
  v4 = (void *)*((_QWORD *)this + 17);
  if ( v4 )
    LocalFree(v4);
  v5 = *((_QWORD *)this + 14);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  v6 = *((_QWORD *)this + 13);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( *((_BYTE *)this + 56) )
  {
    *((_BYTE *)this + 56) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  }
}

```

## disassembly

```asm
0x1800550a8  push    rbx
0x1800550aa  sub     rsp, 20h
0x1800550ae  lea     rax, ??_7PhoneCallScreen@@6B@; const PhoneCallScreen::`vftable'
0x1800550b5  mov     rbx, rcx
0x1800550b8  mov     [rcx], rax
0x1800550bb  mov     rcx, [rcx+70h]
0x1800550bf  test    rcx, rcx
0x1800550c2  jz      short loc_1800550D0
0x1800550c4  mov     rax, [rcx]
0x1800550c7  mov     rax, [rax+28h]
0x1800550cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800550d0  mov     rcx, [rbx+0A0h]; hMem
0x1800550d7  test    rcx, rcx
0x1800550da  jz      short loc_1800550E2
0x1800550dc  call    cs:__imp_LocalFree
0x1800550e2  mov     rcx, [rbx+88h]; hMem
0x1800550e9  test    rcx, rcx
0x1800550ec  jz      short loc_1800550F4
0x1800550ee  call    cs:__imp_LocalFree
0x1800550f4  mov     rcx, [rbx+70h]
0x1800550f8  test    rcx, rcx
0x1800550fb  jz      short loc_180055109
0x1800550fd  mov     rax, [rcx]
0x180055100  mov     rax, [rax+10h]
0x180055104  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055109  mov     rcx, [rbx+68h]
0x18005510d  test    rcx, rcx
0x180055110  jz      short loc_18005511E
0x180055112  mov     rax, [rcx]
0x180055115  mov     rax, [rax+10h]
0x180055119  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005511e  lea     rcx, [rbx+40h]; lpCriticalSection
0x180055122  call    cs:__imp_DeleteCriticalSection
0x180055128  lea     rcx, [rbx+10h]; lpCriticalSection
0x18005512c  cmp     byte ptr [rcx+28h], 0
0x180055130  jz      short loc_18005513C
0x180055132  mov     byte ptr [rcx+28h], 0
0x180055136  call    cs:__imp_DeleteCriticalSection
0x18005513c  add     rsp, 20h
0x180055140  pop     rbx
0x180055141  retn
```
